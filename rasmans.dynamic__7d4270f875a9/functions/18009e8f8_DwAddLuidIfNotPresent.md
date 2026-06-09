# DwAddLuidIfNotPresent

- ea: `0x18009e8f8`
- end: `0x18009eb04`
- name: `DwAddLuidIfNotPresent`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800130e0`

## callees

- `0x18009e8f8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18009e91c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18009e91c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e9ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e9d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e9d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009eae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009eae1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e9bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009eacd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e9bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009eacd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009eaa5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009eaa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009eabc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009eabc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e968`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e968`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009e99d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ea20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009e99d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ea20`

## string_xrefs

- `0x18009e936`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18009e92d`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 __fastcall DwAddLuidIfNotPresent(__int64 a1)
{
  BYTE *v1; // rsi
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int v4; // ebx
  DWORD v5; // edx
  int v6; // r15d
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  const BYTE *v9; // r14
  __int64 v10; // rdi
  DWORD LastError; // eax
  __int64 v12; // r8
  DWORD v13; // edi
  HANDLE v14; // rax
  int v16; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v16 = a1;
  v1 = 0;
  hKey = 0;
  cbData = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v3 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  if ( !IsStateSeparationEnabled )
    v3 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0x20007u, 0, &hKey, 0);
  if ( !v4 )
  {
    v4 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, 0, &cbData);
    if ( v4 )
      goto LABEL_19;
    v5 = cbData;
    v6 = 0;
    if ( cbData )
    {
      v7 = cbData;
      ProcessHeap = GetProcessHeap();
      v1 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7 + 4);
      if ( !v1 )
      {
        v9 = 0;
        v10 = 0;
        LastError = GetLastError();
        v5 = cbData;
        v4 = LastError;
        goto LABEL_15;
      }
      v4 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, v1, &cbData);
      if ( v4 )
        goto LABEL_19;
      v5 = cbData;
    }
    v12 = 0;
    v10 = v5 >> 2;
    v9 = v1;
    if ( !(_DWORD)v10 )
      goto LABEL_17;
    while ( *(_DWORD *)&v1[4 * v12] != v16 )
    {
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= (unsigned int)v10 )
        goto LABEL_15;
    }
    v6 = 1;
LABEL_15:
    if ( !v4 && !v6 )
    {
LABEL_17:
      if ( v5 )
      {
        *(_DWORD *)&v9[4 * v10] = v16;
        v13 = 4 * v10 + 4;
LABEL_21:
        v4 = RegSetValueExW(hKey, L"AllocatedLuids", 0, 3u, v9, v13);
        goto LABEL_22;
      }
LABEL_20:
      v9 = (const BYTE *)&v16;
      v13 = 4;
      goto LABEL_21;
    }
LABEL_19:
    if ( v4 != 2 )
      goto LABEL_22;
    goto LABEL_20;
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v1);
  }
  return v4;
}

```

## disassembly

```asm
0x18009e8f8  mov     [rsp-28h+arg_18], rbx
0x18009e8fd  mov     [rsp-28h+arg_0], ecx
0x18009e901  push    rbp
0x18009e902  push    rsi
0x18009e903  push    rdi
0x18009e904  push    r14
0x18009e906  push    r15
0x18009e908  mov     rbp, rsp
0x18009e90b  sub     rsp, 50h
0x18009e90f  xor     esi, esi
0x18009e911  mov     [rbp+hKey], 0
0x18009e919  mov     [rbp+cbData], esi
0x18009e91c  call    cs:__imp_RtlIsStateSeparationEnabled
0x18009e923  nop     dword ptr [rax+rax+00h]
0x18009e928  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x18009e92d  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18009e934  test    al, al
0x18009e936  lea     rdx, aOsdataSystemCu_3; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18009e93d  lea     rax, [rbp+hKey]
0x18009e941  mov     [rsp+50h+phkResult], rax; phkResult
0x18009e946  cmovz   rdx, rcx; lpSubKey
0x18009e94a  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18009e94f  xor     r9d, r9d; lpClass
0x18009e952  mov     [rsp+50h+samDesired], 20007h; samDesired
0x18009e95a  xor     r8d, r8d; Reserved
0x18009e95d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009e964  mov     [rsp+50h+dwOptions], esi; dwOptions
0x18009e968  call    cs:__imp_RegCreateKeyExW
0x18009e96f  nop     dword ptr [rax+rax+00h]
0x18009e974  mov     ebx, eax
0x18009e976  test    eax, eax
0x18009e978  jnz     loc_18009EAB3
0x18009e97e  mov     rcx, [rbp+hKey]; hKey
0x18009e982  lea     rax, [rbp+cbData]
0x18009e986  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x18009e98b  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x18009e992  xor     r9d, r9d; lpType
0x18009e995  mov     qword ptr [rsp+50h+dwOptions], rsi; lpData
0x18009e99a  xor     r8d, r8d; lpReserved
0x18009e99d  call    cs:__imp_RegQueryValueExW
0x18009e9a4  nop     dword ptr [rax+rax+00h]
0x18009e9a9  mov     ebx, eax
0x18009e9ab  test    eax, eax
0x18009e9ad  jnz     loc_18009EA7A
0x18009e9b3  mov     edx, [rbp+cbData]
0x18009e9b6  xor     r15d, r15d
0x18009e9b9  test    edx, edx
0x18009e9bb  jz      short loc_18009EA35
0x18009e9bd  mov     ebx, edx
0x18009e9bf  call    cs:__imp_GetProcessHeap
0x18009e9c6  nop     dword ptr [rax+rax+00h]
0x18009e9cb  mov     rcx, rax; hHeap
0x18009e9ce  lea     r8, [rbx+4]; dwBytes
0x18009e9d2  lea     edx, [rsi+8]; dwFlags
0x18009e9d5  call    cs:__imp_HeapAlloc
0x18009e9dc  nop     dword ptr [rax+rax+00h]
0x18009e9e1  mov     rsi, rax
0x18009e9e4  test    rax, rax
0x18009e9e7  jnz     short loc_18009EA01
0x18009e9e9  xor     r14d, r14d
0x18009e9ec  xor     edi, edi
0x18009e9ee  call    cs:__imp_GetLastError
0x18009e9f5  nop     dword ptr [rax+rax+00h]
0x18009e9fa  mov     edx, [rbp+cbData]
0x18009e9fd  mov     ebx, eax
0x18009e9ff  jmp     short loc_18009EA5D
0x18009ea01  mov     rcx, [rbp+hKey]; hKey
0x18009ea05  lea     rax, [rbp+cbData]
0x18009ea09  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x18009ea0e  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x18009ea15  xor     r9d, r9d; lpType
0x18009ea18  mov     qword ptr [rsp+50h+dwOptions], rsi; lpData
0x18009ea1d  xor     r8d, r8d; lpReserved
0x18009ea20  call    cs:__imp_RegQueryValueExW
0x18009ea27  nop     dword ptr [rax+rax+00h]
0x18009ea2c  mov     ebx, eax
0x18009ea2e  test    eax, eax
0x18009ea30  jnz     short loc_18009EA7A
0x18009ea32  mov     edx, [rbp+cbData]
0x18009ea35  mov     edi, edx
0x18009ea37  xor     r8d, r8d
0x18009ea3a  shr     edi, 2
0x18009ea3d  mov     r14, rsi
0x18009ea40  test    edi, edi
0x18009ea42  jz      short loc_18009EA66
0x18009ea44  mov     eax, [rbp+arg_0]
0x18009ea47  cmp     [rsi+r8*4], eax
0x18009ea4b  jz      short loc_18009EA57
0x18009ea4d  inc     r8d
0x18009ea50  cmp     r8d, edi
0x18009ea53  jb      short loc_18009EA44
0x18009ea55  jmp     short loc_18009EA5D
0x18009ea57  mov     r15d, 1
0x18009ea5d  test    ebx, ebx
0x18009ea5f  jnz     short loc_18009EA7A
0x18009ea61  test    r15d, r15d
0x18009ea64  jnz     short loc_18009EA7A
0x18009ea66  test    edx, edx
0x18009ea68  jz      short loc_18009EA7F
0x18009ea6a  mov     eax, [rbp+arg_0]
0x18009ea6d  mov     [r14+rdi*4], eax
0x18009ea71  lea     edi, ds:4[rdi*4]
0x18009ea78  jmp     short loc_18009EA88
0x18009ea7a  cmp     ebx, 2
0x18009ea7d  jnz     short loc_18009EAB3
0x18009ea7f  lea     r14, [rbp+arg_0]
0x18009ea83  mov     edi, 4
0x18009ea88  mov     rcx, [rbp+hKey]; hKey
0x18009ea8c  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x18009ea93  mov     [rsp+50h+samDesired], edi; cbData
0x18009ea97  mov     r9d, 3; dwType
0x18009ea9d  xor     r8d, r8d; Reserved
0x18009eaa0  mov     qword ptr [rsp+50h+dwOptions], r14; lpData
0x18009eaa5  call    cs:__imp_RegSetValueExW
0x18009eaac  nop     dword ptr [rax+rax+00h]
0x18009eab1  mov     ebx, eax
0x18009eab3  mov     rcx, [rbp+hKey]; hKey
0x18009eab7  test    rcx, rcx
0x18009eaba  jz      short loc_18009EAC8
0x18009eabc  call    cs:__imp_RegCloseKey
0x18009eac3  nop     dword ptr [rax+rax+00h]
0x18009eac8  test    rsi, rsi
0x18009eacb  jz      short loc_18009EAED
0x18009eacd  call    cs:__imp_GetProcessHeap
0x18009ead4  nop     dword ptr [rax+rax+00h]
0x18009ead9  mov     r8, rsi; lpMem
0x18009eadc  xor     edx, edx; dwFlags
0x18009eade  mov     rcx, rax; hHeap
0x18009eae1  call    cs:__imp_HeapFree
0x18009eae8  nop     dword ptr [rax+rax+00h]
0x18009eaed  mov     eax, ebx
0x18009eaef  mov     rbx, [rsp+50h+arg_18]
0x18009eaf7  add     rsp, 50h
0x18009eafb  pop     r15
0x18009eafd  pop     r14
0x18009eaff  pop     rdi
0x18009eb00  pop     rsi
0x18009eb01  pop     rbp
0x18009eb02  retn
```
