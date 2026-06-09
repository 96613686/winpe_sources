# DwAddLuidIfNotPresent

- ea: `0x180052e48`
- end: `0x18005300c`
- name: `DwAddLuidIfNotPresent`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000e340`

## callees

- `0x180052e48`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180052e6c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180052e6c`
- `KERNEL32!GetProcessHeap` at `0x180052efd`
- `KERNEL32!GetProcessHeap` at `0x180052fe2`
- `KERNEL32!GetProcessHeap` at `0x180052efd`
- `KERNEL32!GetProcessHeap` at `0x180052fe2`
- `KERNEL32!GetLastError` at `0x180052f20`
- `KERNEL32!GetLastError` at `0x180052f20`
- `KERNEL32!HeapFree` at `0x180052ff0`
- `KERNEL32!HeapFree` at `0x180052ff0`
- `KERNEL32!HeapAlloc` at `0x180052f0d`
- `KERNEL32!HeapAlloc` at `0x180052f0d`
- `ADVAPI32!RegCreateKeyExW` at `0x180052eb2`
- `ADVAPI32!RegCreateKeyExW` at `0x180052eb2`
- `ADVAPI32!RegCloseKey` at `0x180052fd7`
- `ADVAPI32!RegCloseKey` at `0x180052fd7`
- `ADVAPI32!RegQueryValueExW` at `0x180052ee1`
- `ADVAPI32!RegQueryValueExW` at `0x180052f50`
- `ADVAPI32!RegQueryValueExW` at `0x180052ee1`
- `ADVAPI32!RegQueryValueExW` at `0x180052f50`
- `ADVAPI32!RegSetValueExW` at `0x180052fc6`
- `ADVAPI32!RegSetValueExW` at `0x180052fc6`

## string_xrefs

- `0x180052e80`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x180052e77`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 __fastcall DwAddLuidIfNotPresent(int a1)
{
  BYTE *v1; // rbx
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int v4; // edi
  DWORD v5; // ecx
  int v6; // r15d
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  const BYTE *v9; // r14
  __int64 v10; // rsi
  DWORD LastError; // eax
  int v12; // r8d
  __int64 i; // rdx
  DWORD v14; // esi
  HANDLE v15; // rax
  int v17; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v17 = a1;
  v1 = 0;
  hKey = 0;
  cbData = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
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
        v12 = v17;
        v4 = LastError;
        v5 = cbData;
        goto LABEL_15;
      }
      v4 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, v1, &cbData);
      if ( v4 )
        goto LABEL_19;
      v5 = cbData;
    }
    v12 = v17;
    v10 = v5 >> 2;
    v9 = v1;
    for ( i = 0; (unsigned int)i < (unsigned int)v10; i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)&v1[4 * i] == v17 )
      {
        v6 = 1;
        break;
      }
    }
LABEL_15:
    if ( !v4 && !v6 )
    {
      if ( v5 )
      {
        *(_DWORD *)&v9[4 * v10] = v12;
        v14 = 4 * v10 + 4;
LABEL_21:
        v4 = RegSetValueExW(hKey, L"AllocatedLuids", 0, 3u, v9, v14);
        goto LABEL_22;
      }
LABEL_20:
      v9 = (const BYTE *)&v17;
      v14 = 4;
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
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v1);
  }
  return v4;
}

```

## disassembly

```asm
0x180052e48  mov     [rsp-28h+arg_18], rbx
0x180052e4d  mov     [rsp-28h+arg_0], ecx
0x180052e51  push    rbp
0x180052e52  push    rsi
0x180052e53  push    rdi
0x180052e54  push    r14
0x180052e56  push    r15
0x180052e58  mov     rbp, rsp
0x180052e5b  sub     rsp, 50h
0x180052e5f  xor     ebx, ebx
0x180052e61  mov     [rbp+hKey], 0
0x180052e69  mov     [rbp+cbData], ebx
0x180052e6c  call    cs:__imp_RtlIsStateSeparationEnabled
0x180052e72  mov     [rsp+50h+lpdwDisposition], rbx; lpdwDisposition
0x180052e77  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180052e7e  test    al, al
0x180052e80  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180052e87  lea     rax, [rbp+hKey]
0x180052e8b  mov     [rsp+50h+phkResult], rax; phkResult
0x180052e90  cmovz   rdx, rcx; lpSubKey
0x180052e94  mov     [rsp+50h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180052e99  xor     r9d, r9d; lpClass
0x180052e9c  mov     [rsp+50h+samDesired], 20007h; samDesired
0x180052ea4  xor     r8d, r8d; Reserved
0x180052ea7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052eae  mov     [rsp+50h+dwOptions], ebx; dwOptions
0x180052eb2  call    cs:__imp_RegCreateKeyExW
0x180052eb8  mov     edi, eax
0x180052eba  test    eax, eax
0x180052ebc  jnz     loc_180052FCE
0x180052ec2  mov     rcx, [rbp+hKey]; hKey
0x180052ec6  lea     rax, [rbp+cbData]
0x180052eca  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x180052ecf  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180052ed6  xor     r9d, r9d; lpType
0x180052ed9  mov     qword ptr [rsp+50h+dwOptions], rbx; lpData
0x180052ede  xor     r8d, r8d; lpReserved
0x180052ee1  call    cs:__imp_RegQueryValueExW
0x180052ee7  mov     edi, eax
0x180052ee9  test    eax, eax
0x180052eeb  jnz     loc_180052F9B
0x180052ef1  mov     ecx, [rbp+cbData]
0x180052ef4  xor     r15d, r15d
0x180052ef7  test    ecx, ecx
0x180052ef9  jz      short loc_180052F5F
0x180052efb  mov     ebx, ecx
0x180052efd  call    cs:__imp_GetProcessHeap
0x180052f03  mov     rcx, rax; hHeap
0x180052f06  lea     r8, [rbx+4]; dwBytes
0x180052f0a  lea     edx, [rdi+8]; dwFlags
0x180052f0d  call    cs:__imp_HeapAlloc
0x180052f13  mov     rbx, rax
0x180052f16  test    rax, rax
0x180052f19  jnz     short loc_180052F31
0x180052f1b  xor     r14d, r14d
0x180052f1e  xor     esi, esi
0x180052f20  call    cs:__imp_GetLastError
0x180052f26  mov     r8d, [rbp+arg_0]
0x180052f2a  mov     edi, eax
0x180052f2c  mov     ecx, [rbp+cbData]
0x180052f2f  jmp     short loc_180052F81
0x180052f31  mov     rcx, [rbp+hKey]; hKey
0x180052f35  lea     rax, [rbp+cbData]
0x180052f39  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x180052f3e  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180052f45  xor     r9d, r9d; lpType
0x180052f48  mov     qword ptr [rsp+50h+dwOptions], rbx; lpData
0x180052f4d  xor     r8d, r8d; lpReserved
0x180052f50  call    cs:__imp_RegQueryValueExW
0x180052f56  mov     edi, eax
0x180052f58  test    eax, eax
0x180052f5a  jnz     short loc_180052F9B
0x180052f5c  mov     ecx, [rbp+cbData]
0x180052f5f  mov     r8d, [rbp+arg_0]
0x180052f63  mov     esi, ecx
0x180052f65  shr     esi, 2
0x180052f68  mov     r14, rbx
0x180052f6b  xor     edx, edx
0x180052f6d  cmp     edx, esi
0x180052f6f  jnb     short loc_180052F81
0x180052f71  cmp     [rbx+rdx*4], r8d
0x180052f75  jz      short loc_180052F7B
0x180052f77  inc     edx
0x180052f79  jmp     short loc_180052F6D
0x180052f7b  mov     r15d, 1
0x180052f81  test    edi, edi
0x180052f83  jnz     short loc_180052F9B
0x180052f85  test    r15d, r15d
0x180052f88  jnz     short loc_180052F9B
0x180052f8a  test    ecx, ecx
0x180052f8c  jz      short loc_180052FA0
0x180052f8e  mov     [r14+rsi*4], r8d
0x180052f92  lea     esi, ds:4[rsi*4]
0x180052f99  jmp     short loc_180052FA9
0x180052f9b  cmp     edi, 2
0x180052f9e  jnz     short loc_180052FCE
0x180052fa0  lea     r14, [rbp+arg_0]
0x180052fa4  mov     esi, 4
0x180052fa9  mov     rcx, [rbp+hKey]; hKey
0x180052fad  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180052fb4  mov     [rsp+50h+samDesired], esi; cbData
0x180052fb8  mov     r9d, 3; dwType
0x180052fbe  xor     r8d, r8d; Reserved
0x180052fc1  mov     qword ptr [rsp+50h+dwOptions], r14; lpData
0x180052fc6  call    cs:__imp_RegSetValueExW
0x180052fcc  mov     edi, eax
0x180052fce  mov     rcx, [rbp+hKey]; hKey
0x180052fd2  test    rcx, rcx
0x180052fd5  jz      short loc_180052FDD
0x180052fd7  call    cs:__imp_RegCloseKey
0x180052fdd  test    rbx, rbx
0x180052fe0  jz      short loc_180052FF6
0x180052fe2  call    cs:__imp_GetProcessHeap
0x180052fe8  mov     r8, rbx; lpMem
0x180052feb  xor     edx, edx; dwFlags
0x180052fed  mov     rcx, rax; hHeap
0x180052ff0  call    cs:__imp_HeapFree
0x180052ff6  mov     rbx, [rsp+50h+arg_18]
0x180052ffe  mov     eax, edi
0x180053000  add     rsp, 50h
0x180053004  pop     r15
0x180053006  pop     r14
0x180053008  pop     rdi
0x180053009  pop     rsi
0x18005300a  pop     rbp
0x18005300b  retn
```
