# DwRemoveLuid

- ea: `0x180053014`
- end: `0x18005320b`
- name: `DwRemoveLuid`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000f2ac`

## callees

- `0x180053014`
- `0x18005852a`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180053039`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180053039`
- `KERNEL32!GetProcessHeap` at `0x1800530b4`
- `KERNEL32!GetProcessHeap` at `0x180053134`
- `KERNEL32!GetProcessHeap` at `0x1800531cb`
- `KERNEL32!GetProcessHeap` at `0x1800531e4`
- `KERNEL32!GetProcessHeap` at `0x1800530b4`
- `KERNEL32!GetProcessHeap` at `0x180053134`
- `KERNEL32!GetProcessHeap` at `0x1800531cb`
- `KERNEL32!GetProcessHeap` at `0x1800531e4`
- `KERNEL32!GetLastError` at `0x1800530d1`
- `KERNEL32!GetLastError` at `0x1800530d1`
- `KERNEL32!HeapFree` at `0x1800531d9`
- `KERNEL32!HeapFree` at `0x1800531f2`
- `KERNEL32!HeapFree` at `0x1800531d9`
- `KERNEL32!HeapFree` at `0x1800531f2`
- `KERNEL32!HeapAlloc` at `0x1800530c3`
- `KERNEL32!HeapAlloc` at `0x180053146`
- `KERNEL32!HeapAlloc` at `0x1800530c3`
- `KERNEL32!HeapAlloc` at `0x180053146`
- `ADVAPI32!RegCloseKey` at `0x1800531c0`
- `ADVAPI32!RegCloseKey` at `0x1800531c0`
- `ADVAPI32!RegOpenKeyExW` at `0x18005306c`
- `ADVAPI32!RegOpenKeyExW` at `0x18005306c`
- `ADVAPI32!RegQueryValueExW` at `0x18005309b`
- `ADVAPI32!RegQueryValueExW` at `0x1800530fb`
- `ADVAPI32!RegQueryValueExW` at `0x18005309b`
- `ADVAPI32!RegQueryValueExW` at `0x1800530fb`
- `ADVAPI32!RegSetValueExW` at `0x1800531af`
- `ADVAPI32!RegSetValueExW` at `0x1800531af`

## string_xrefs

- `0x18005304e`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18005303f`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 __fastcall DwRemoveLuid(int a1)
{
  BYTE *v1; // rsi
  BYTE *v3; // r15
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int v6; // ebx
  DWORD v7; // ecx
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  unsigned int v11; // ecx
  __int64 i; // r14
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
  v3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20007u, &hKey);
  if ( v6 )
    goto LABEL_17;
  v6 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, 0, &cbData);
  if ( v6 )
    goto LABEL_17;
  v7 = cbData;
  if ( cbData )
  {
    v8 = cbData;
    ProcessHeap = GetProcessHeap();
    v1 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v8);
    if ( !v1 )
    {
LABEL_7:
      LastError = GetLastError();
LABEL_16:
      v6 = LastError;
      goto LABEL_17;
    }
    v6 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, v1, &cbData);
    if ( v6 )
      goto LABEL_17;
    v7 = cbData;
  }
  v11 = v7 >> 2;
  for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
  {
    if ( *(_DWORD *)&v1[4 * i] == a1 )
    {
      cbData = 4 * v11;
      v13 = 4 * v11;
      v14 = GetProcessHeap();
      v15 = (BYTE *)HeapAlloc(v14, 8u, v13 - 4);
      v3 = v15;
      if ( !v15 )
        goto LABEL_7;
      v16 = cbData - 4 * i - 4;
      memcpy_0(v15, v1, (unsigned int)(4 * i));
      memcpy_0(&v3[(unsigned int)(4 * i)], &v1[4 * (unsigned int)(i + 1)], v16);
      LastError = RegSetValueExW(hKey, L"AllocatedLuids", 0, 3u, v3, cbData - 4);
      goto LABEL_16;
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
0x180053014  mov     [rsp-28h+arg_0], rbx
0x180053019  push    rbp
0x18005301a  push    rsi
0x18005301b  push    rdi
0x18005301c  push    r14
0x18005301e  push    r15
0x180053020  mov     rbp, rsp
0x180053023  sub     rsp, 30h
0x180053027  xor     esi, esi
0x180053029  mov     [rbp+hKey], 0
0x180053031  mov     [rbp+cbData], esi
0x180053034  mov     edi, ecx
0x180053036  xor     r15d, r15d
0x180053039  call    cs:__imp_RtlIsStateSeparationEnabled
0x18005303f  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180053046  mov     r9d, 20007h; samDesired
0x18005304c  test    al, al
0x18005304e  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180053055  lea     rax, [rbp+hKey]
0x180053059  cmovz   rdx, rcx; lpSubKey
0x18005305d  mov     [rsp+30h+phkResult], rax; phkResult
0x180053062  xor     r8d, r8d; ulOptions
0x180053065  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005306c  call    cs:__imp_RegOpenKeyExW
0x180053072  mov     ebx, eax
0x180053074  test    eax, eax
0x180053076  jnz     loc_1800531B7
0x18005307c  mov     rcx, [rbp+hKey]; hKey
0x180053080  lea     rax, [rbp+cbData]
0x180053084  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180053089  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180053090  xor     r9d, r9d; lpType
0x180053093  mov     [rsp+30h+phkResult], rsi; lpData
0x180053098  xor     r8d, r8d; lpReserved
0x18005309b  call    cs:__imp_RegQueryValueExW
0x1800530a1  mov     ebx, eax
0x1800530a3  test    eax, eax
0x1800530a5  jnz     loc_1800531B7
0x1800530ab  mov     ecx, [rbp+cbData]
0x1800530ae  test    ecx, ecx
0x1800530b0  jz      short loc_18005310E
0x1800530b2  mov     ebx, ecx
0x1800530b4  call    cs:__imp_GetProcessHeap
0x1800530ba  mov     r8d, ebx; dwBytes
0x1800530bd  lea     edx, [rsi+8]; dwFlags
0x1800530c0  mov     rcx, rax; hHeap
0x1800530c3  call    cs:__imp_HeapAlloc
0x1800530c9  mov     rsi, rax
0x1800530cc  test    rax, rax
0x1800530cf  jnz     short loc_1800530DC
0x1800530d1  call    cs:__imp_GetLastError
0x1800530d7  jmp     loc_1800531B5
0x1800530dc  mov     rcx, [rbp+hKey]; hKey
0x1800530e0  lea     rax, [rbp+cbData]
0x1800530e4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800530e9  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x1800530f0  xor     r9d, r9d; lpType
0x1800530f3  mov     [rsp+30h+phkResult], rsi; lpData
0x1800530f8  xor     r8d, r8d; lpReserved
0x1800530fb  call    cs:__imp_RegQueryValueExW
0x180053101  mov     ebx, eax
0x180053103  test    eax, eax
0x180053105  jnz     loc_1800531B7
0x18005310b  mov     ecx, [rbp+cbData]
0x18005310e  shr     ecx, 2
0x180053111  xor     r14d, r14d
0x180053114  cmp     r14d, ecx
0x180053117  jnb     loc_1800531B7
0x18005311d  cmp     [rsi+r14*4], edi
0x180053121  jz      short loc_180053128
0x180053123  inc     r14d
0x180053126  jmp     short loc_180053114
0x180053128  lea     eax, ds:0[rcx*4]
0x18005312f  mov     [rbp+cbData], eax
0x180053132  mov     ebx, eax
0x180053134  call    cs:__imp_GetProcessHeap
0x18005313a  lea     r8, [rbx-4]; dwBytes
0x18005313e  mov     edx, 8; dwFlags
0x180053143  mov     rcx, rax; hHeap
0x180053146  call    cs:__imp_HeapAlloc
0x18005314c  mov     r15, rax
0x18005314f  test    rax, rax
0x180053152  jz      loc_1800530D1
0x180053158  mov     ebx, [rbp+cbData]
0x18005315b  lea     ecx, ds:0[r14*4]
0x180053163  sub     ebx, ecx
0x180053165  mov     edi, ecx
0x180053167  mov     r8d, ecx; Size
0x18005316a  mov     rdx, rsi; Src
0x18005316d  mov     rcx, rax; void *
0x180053170  add     ebx, 0FFFFFFFCh
0x180053173  call    memcpy_0
0x180053178  lea     eax, [r14+1]
0x18005317c  mov     r8d, ebx; Size
0x18005317f  lea     rcx, [rdi+r15]; void *
0x180053183  lea     rdx, [rsi+rax*4]; Src
0x180053187  call    memcpy_0
0x18005318c  mov     eax, [rbp+cbData]
0x18005318f  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180053196  mov     rcx, [rbp+hKey]; hKey
0x18005319a  add     eax, 0FFFFFFFCh
0x18005319d  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x1800531a1  mov     r9d, 3; dwType
0x1800531a7  xor     r8d, r8d; Reserved
0x1800531aa  mov     [rsp+30h+phkResult], r15; lpData
0x1800531af  call    cs:__imp_RegSetValueExW
0x1800531b5  mov     ebx, eax
0x1800531b7  mov     rcx, [rbp+hKey]; hKey
0x1800531bb  test    rcx, rcx
0x1800531be  jz      short loc_1800531C6
0x1800531c0  call    cs:__imp_RegCloseKey
0x1800531c6  test    rsi, rsi
0x1800531c9  jz      short loc_1800531DF
0x1800531cb  call    cs:__imp_GetProcessHeap
0x1800531d1  mov     r8, rsi; lpMem
0x1800531d4  xor     edx, edx; dwFlags
0x1800531d6  mov     rcx, rax; hHeap
0x1800531d9  call    cs:__imp_HeapFree
0x1800531df  test    r15, r15
0x1800531e2  jz      short loc_1800531F8
0x1800531e4  call    cs:__imp_GetProcessHeap
0x1800531ea  mov     r8, r15; lpMem
0x1800531ed  xor     edx, edx; dwFlags
0x1800531ef  mov     rcx, rax; hHeap
0x1800531f2  call    cs:__imp_HeapFree
0x1800531f8  mov     eax, ebx
0x1800531fa  mov     rbx, [rsp+30h+arg_0]
0x1800531ff  add     rsp, 30h
0x180053203  pop     r15
0x180053205  pop     r14
0x180053207  pop     rdi
0x180053208  pop     rsi
0x180053209  pop     rbp
0x18005320a  retn
```
