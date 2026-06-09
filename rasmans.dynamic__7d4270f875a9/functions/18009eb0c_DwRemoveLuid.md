# DwRemoveLuid

- ea: `0x18009eb0c`
- end: `0x18009ed65`
- name: `DwRemoveLuid`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001a8d0`

## callees

- `0x18009eb0c`
- `0x1800e8e7e`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18009eb31`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18009eb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ebe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ebe7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ebd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ec75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ebd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ec75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ed20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ed45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ed20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ed45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ebbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ec5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ed0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ed31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ebbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ec5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ed0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ed31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009eb6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009eb6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ece4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ece4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ecfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ecfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009eb9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ec17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009eb9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ec17`

## string_xrefs

- `0x18009eb4c`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18009eb3d`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 __fastcall DwRemoveLuid(__int64 a1)
{
  BYTE *v1; // rsi
  int v2; // edi
  BYTE *v3; // r15
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int v6; // ebx
  DWORD v7; // ecx
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  unsigned int v11; // ecx
  __int64 v12; // r14
  __int64 v13; // rbx
  HANDLE v14; // rax
  BYTE *v15; // rax
  unsigned int v16; // ebx
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  v1 = 0;
  hKey = 0;
  cbData = 0;
  v2 = a1;
  v3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20007u, &hKey);
  if ( !v6 )
  {
    v6 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, 0, &cbData);
    if ( !v6 )
    {
      v7 = cbData;
      if ( cbData )
      {
        v8 = cbData;
        ProcessHeap = GetProcessHeap();
        v1 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v8);
        if ( !v1 )
          goto LABEL_7;
        v6 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, v1, &cbData);
        if ( v6 )
          goto LABEL_17;
        v7 = cbData;
      }
      v11 = v7 >> 2;
      v12 = 0;
      if ( !v11 )
        goto LABEL_17;
      while ( *(_DWORD *)&v1[4 * v12] != v2 )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v11 )
          goto LABEL_17;
      }
      cbData = 4 * v11;
      v13 = 4 * v11;
      v14 = GetProcessHeap();
      v15 = (BYTE *)HeapAlloc(v14, 8u, v13 - 4);
      v3 = v15;
      if ( v15 )
      {
        v16 = cbData - 4 * v12 - 4;
        memcpy_0(v15, v1, (unsigned int)(4 * v12));
        memcpy_0(&v3[(unsigned int)(4 * v12)], &v1[4 * (unsigned int)(v12 + 1)], v16);
        LastError = RegSetValueExW(hKey, L"AllocatedLuids", 0, 3u, v3, cbData - 4);
        goto LABEL_16;
      }
LABEL_7:
      LastError = GetLastError();
LABEL_16:
      v6 = LastError;
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v1);
  }
  if ( v3 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x18009eb0c  mov     [rsp-28h+arg_0], rbx
0x18009eb11  push    rbp
0x18009eb12  push    rsi
0x18009eb13  push    rdi
0x18009eb14  push    r14
0x18009eb16  push    r15
0x18009eb18  mov     rbp, rsp
0x18009eb1b  sub     rsp, 30h
0x18009eb1f  xor     esi, esi
0x18009eb21  mov     [rbp+hKey], 0
0x18009eb29  mov     [rbp+cbData], esi
0x18009eb2c  mov     edi, ecx
0x18009eb2e  xor     r15d, r15d
0x18009eb31  call    cs:__imp_RtlIsStateSeparationEnabled
0x18009eb38  nop     dword ptr [rax+rax+00h]
0x18009eb3d  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18009eb44  mov     r9d, 20007h; samDesired
0x18009eb4a  test    al, al
0x18009eb4c  lea     rdx, aOsdataSystemCu_3; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18009eb53  lea     rax, [rbp+hKey]
0x18009eb57  cmovz   rdx, rcx; lpSubKey
0x18009eb5b  mov     [rsp+30h+phkResult], rax; phkResult
0x18009eb60  xor     r8d, r8d; ulOptions
0x18009eb63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009eb6a  call    cs:__imp_RegOpenKeyExW
0x18009eb71  nop     dword ptr [rax+rax+00h]
0x18009eb76  mov     ebx, eax
0x18009eb78  test    eax, eax
0x18009eb7a  jnz     loc_18009ECF2
0x18009eb80  mov     rcx, [rbp+hKey]; hKey
0x18009eb84  lea     rax, [rbp+cbData]
0x18009eb88  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18009eb8d  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x18009eb94  xor     r9d, r9d; lpType
0x18009eb97  mov     [rsp+30h+phkResult], rsi; lpData
0x18009eb9c  xor     r8d, r8d; lpReserved
0x18009eb9f  call    cs:__imp_RegQueryValueExW
0x18009eba6  nop     dword ptr [rax+rax+00h]
0x18009ebab  mov     ebx, eax
0x18009ebad  test    eax, eax
0x18009ebaf  jnz     loc_18009ECF2
0x18009ebb5  mov     ecx, [rbp+cbData]
0x18009ebb8  test    ecx, ecx
0x18009ebba  jz      short loc_18009EC30
0x18009ebbc  mov     ebx, ecx
0x18009ebbe  call    cs:__imp_GetProcessHeap
0x18009ebc5  nop     dword ptr [rax+rax+00h]
0x18009ebca  mov     r8d, ebx; dwBytes
0x18009ebcd  lea     edx, [rsi+8]; dwFlags
0x18009ebd0  mov     rcx, rax; hHeap
0x18009ebd3  call    cs:__imp_HeapAlloc
0x18009ebda  nop     dword ptr [rax+rax+00h]
0x18009ebdf  mov     rsi, rax
0x18009ebe2  test    rax, rax
0x18009ebe5  jnz     short loc_18009EBF8
0x18009ebe7  call    cs:__imp_GetLastError
0x18009ebee  nop     dword ptr [rax+rax+00h]
0x18009ebf3  jmp     loc_18009ECF0
0x18009ebf8  mov     rcx, [rbp+hKey]; hKey
0x18009ebfc  lea     rax, [rbp+cbData]
0x18009ec00  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18009ec05  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x18009ec0c  xor     r9d, r9d; lpType
0x18009ec0f  mov     [rsp+30h+phkResult], rsi; lpData
0x18009ec14  xor     r8d, r8d; lpReserved
0x18009ec17  call    cs:__imp_RegQueryValueExW
0x18009ec1e  nop     dword ptr [rax+rax+00h]
0x18009ec23  mov     ebx, eax
0x18009ec25  test    eax, eax
0x18009ec27  jnz     loc_18009ECF2
0x18009ec2d  mov     ecx, [rbp+cbData]
0x18009ec30  shr     ecx, 2
0x18009ec33  xor     r14d, r14d
0x18009ec36  test    ecx, ecx
0x18009ec38  jz      loc_18009ECF2
0x18009ec3e  cmp     [rsi+r14*4], edi
0x18009ec42  jz      short loc_18009EC51
0x18009ec44  inc     r14d
0x18009ec47  cmp     r14d, ecx
0x18009ec4a  jb      short loc_18009EC3E
0x18009ec4c  jmp     loc_18009ECF2
0x18009ec51  lea     eax, ds:0[rcx*4]
0x18009ec58  mov     [rbp+cbData], eax
0x18009ec5b  mov     ebx, eax
0x18009ec5d  call    cs:__imp_GetProcessHeap
0x18009ec64  nop     dword ptr [rax+rax+00h]
0x18009ec69  lea     r8, [rbx-4]; dwBytes
0x18009ec6d  mov     edx, 8; dwFlags
0x18009ec72  mov     rcx, rax; hHeap
0x18009ec75  call    cs:__imp_HeapAlloc
0x18009ec7c  nop     dword ptr [rax+rax+00h]
0x18009ec81  mov     r15, rax
0x18009ec84  test    rax, rax
0x18009ec87  jz      loc_18009EBE7
0x18009ec8d  mov     ebx, [rbp+cbData]
0x18009ec90  lea     ecx, ds:0[r14*4]
0x18009ec98  sub     ebx, ecx
0x18009ec9a  mov     edi, ecx
0x18009ec9c  mov     r8d, ecx; Size
0x18009ec9f  mov     rdx, rsi; Src
0x18009eca2  mov     rcx, rax; void *
0x18009eca5  add     ebx, 0FFFFFFFCh
0x18009eca8  call    memcpy_0
0x18009ecad  lea     eax, [r14+1]
0x18009ecb1  mov     r8d, ebx; Size
0x18009ecb4  lea     rcx, [rdi+r15]; void *
0x18009ecb8  lea     rdx, [rsi+rax*4]; Src
0x18009ecbc  call    memcpy_0
0x18009ecc1  mov     eax, [rbp+cbData]
0x18009ecc4  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x18009eccb  mov     rcx, [rbp+hKey]; hKey
0x18009eccf  add     eax, 0FFFFFFFCh
0x18009ecd2  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x18009ecd6  mov     r9d, 3; dwType
0x18009ecdc  xor     r8d, r8d; Reserved
0x18009ecdf  mov     [rsp+30h+phkResult], r15; lpData
0x18009ece4  call    cs:__imp_RegSetValueExW
0x18009eceb  nop     dword ptr [rax+rax+00h]
0x18009ecf0  mov     ebx, eax
0x18009ecf2  mov     rcx, [rbp+hKey]; hKey
0x18009ecf6  test    rcx, rcx
0x18009ecf9  jz      short loc_18009ED07
0x18009ecfb  call    cs:__imp_RegCloseKey
0x18009ed02  nop     dword ptr [rax+rax+00h]
0x18009ed07  test    rsi, rsi
0x18009ed0a  jz      short loc_18009ED2C
0x18009ed0c  call    cs:__imp_GetProcessHeap
0x18009ed13  nop     dword ptr [rax+rax+00h]
0x18009ed18  mov     r8, rsi; lpMem
0x18009ed1b  xor     edx, edx; dwFlags
0x18009ed1d  mov     rcx, rax; hHeap
0x18009ed20  call    cs:__imp_HeapFree
0x18009ed27  nop     dword ptr [rax+rax+00h]
0x18009ed2c  test    r15, r15
0x18009ed2f  jz      short loc_18009ED51
0x18009ed31  call    cs:__imp_GetProcessHeap
0x18009ed38  nop     dword ptr [rax+rax+00h]
0x18009ed3d  mov     r8, r15; lpMem
0x18009ed40  xor     edx, edx; dwFlags
0x18009ed42  mov     rcx, rax; hHeap
0x18009ed45  call    cs:__imp_HeapFree
0x18009ed4c  nop     dword ptr [rax+rax+00h]
0x18009ed51  mov     eax, ebx
0x18009ed53  mov     rbx, [rsp+30h+arg_0]
0x18009ed58  add     rsp, 30h
0x18009ed5c  pop     r15
0x18009ed5e  pop     r14
0x18009ed60  pop     rdi
0x18009ed61  pop     rsi
0x18009ed62  pop     rbp
0x18009ed63  retn
```
