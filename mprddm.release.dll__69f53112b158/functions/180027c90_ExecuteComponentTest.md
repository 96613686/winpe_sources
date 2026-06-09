# ExecuteComponentTest

- ea: `0x180027c90`
- end: `0x180027eb8`
- name: `ExecuteComponentTest`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047350`

## callees

- `0x180027c90`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027e6f`
- `KERNEL32!GetProcAddress` at `0x180027e6f`
- `KERNEL32!LoadLibraryExW` at `0x180027e31`
- `KERNEL32!LoadLibraryExW` at `0x180027e31`
- `KERNEL32!HeapAlloc` at `0x180027d8b`
- `KERNEL32!HeapAlloc` at `0x180027d8b`
- `KERNEL32!GetLastError` at `0x180027e49`
- `KERNEL32!GetLastError` at `0x180027e49`
- `KERNEL32!HeapFree` at `0x180027ea1`
- `KERNEL32!HeapFree` at `0x180027ea1`
- `ADVAPI32!RegOpenKeyExW` at `0x180027ccf`
- `ADVAPI32!RegOpenKeyExW` at `0x180027ccf`
- `ADVAPI32!RegQueryValueExW` at `0x180027d22`
- `ADVAPI32!RegQueryValueExW` at `0x180027d67`
- `ADVAPI32!RegQueryValueExW` at `0x180027dca`
- `ADVAPI32!RegQueryValueExW` at `0x180027e04`
- `ADVAPI32!RegQueryValueExW` at `0x180027d22`
- `ADVAPI32!RegQueryValueExW` at `0x180027d67`
- `ADVAPI32!RegQueryValueExW` at `0x180027dca`
- `ADVAPI32!RegQueryValueExW` at `0x180027e04`

## string_xrefs

- `0x180027cc1`: `System\CurrentControlSet\Services\RemoteAccess\Test`
- `0x180027d44`: `SimulateCollisionDllPath`
- `0x180027dc3`: `SimulateCollisionDllPath`

## pseudocode

```c
__int64 __fastcall ExecuteComponentTest(DWORD a1)
{
  HKEY v1; // rcx
  unsigned int v2; // ebx
  BYTE *v3; // rdi
  HMODULE Library; // rax
  void (__fastcall *v5)(_QWORD); // rdx
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  int Data; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+38h] BYREF

  cbData = a1;
  v1 = gblHKeyTest;
  v2 = 0;
  if ( !gblHKeyTest )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\Test",
           0,
           0x20019u,
           &gblHKeyTest) )
    {
      gblHKeyTest = 0;
      return v2;
    }
    v1 = gblHKeyTest;
  }
  Type = 0;
  Data = 0;
  v10 = 0;
  cbData = 4;
  v2 = RegQueryValueExW(v1, L"SimulateCollision", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( !v2 )
  {
    if ( Data )
    {
      cbData = 0;
      v2 = RegQueryValueExW(gblHKeyTest, L"SimulateCollisionDllPath", 0, 0, 0, &cbData);
      if ( !v2 )
      {
        v3 = (BYTE *)HeapAlloc(hHeap, 8u, cbData);
        if ( v3 )
        {
          RegQueryValueExW(gblHKeyTest, L"SimulateCollisionDllPath", 0, &Type, v3, &cbData);
          cbData = 4;
          v2 = RegQueryValueExW(gblHKeyTest, L"SimulateCollisionSleepTime", 0, &Type, (LPBYTE)&v10, &cbData);
          if ( !v2 )
          {
            Library = hSimulateCollisionTestDll;
            if ( (hSimulateCollisionTestDll
               || (Library = LoadLibraryExW((LPCWSTR)v3, 0, 0x800u), (hSimulateCollisionTestDll = Library) != 0))
              && ((v5 = (void (__fastcall *)(_QWORD))pfnSimulateCollisonTestFunc) != 0
               || (pfnSimulateCollisonTestFunc = (__int64)GetProcAddress(Library, "SimulateCollision"),
                   (v5 = (void (__fastcall *)(_QWORD))pfnSimulateCollisonTestFunc) != 0)) )
            {
              v5(v10);
              HeapFree(hHeap, 0, v3);
            }
            else
            {
              return GetLastError();
            }
          }
        }
        else
        {
          return 14;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180027c90  mov     [rsp-18h+cbData], ecx
0x180027c94  push    rbp
0x180027c95  push    rbx
0x180027c96  push    rdi
0x180027c97  mov     rbp, rsp
0x180027c9a  sub     rsp, 30h
0x180027c9e  mov     rcx, cs:gblHKeyTest
0x180027ca5  xor     ebx, ebx
0x180027ca7  test    rcx, rcx
0x180027caa  jnz     short loc_180027CF2
0x180027cac  lea     rax, gblHKeyTest
0x180027cb3  mov     r9d, 20019h; samDesired
0x180027cb9  xor     r8d, r8d; ulOptions
0x180027cbc  mov     [rsp+30h+phkResult], rax; phkResult
0x180027cc1  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Re"...
0x180027cc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027ccf  call    cs:__imp_RegOpenKeyExW
0x180027cd6  nop     dword ptr [rax+rax+00h]
0x180027cdb  test    eax, eax
0x180027cdd  jz      short loc_180027CEB
0x180027cdf  and     cs:gblHKeyTest, rbx
0x180027ce6  jmp     loc_180027EAD
0x180027ceb  mov     rcx, cs:gblHKeyTest; hKey
0x180027cf2  and     [rbp+Type], ebx
0x180027cf5  lea     rax, [rbp+cbData]
0x180027cf9  and     [rbp+Data], ebx
0x180027cfc  lea     r9, [rbp+Type]; lpType
0x180027d00  and     [rbp+arg_18], ebx
0x180027d03  lea     rdx, aSimulatecollis_2; "SimulateCollision"
0x180027d0a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027d0f  xor     r8d, r8d; lpReserved
0x180027d12  lea     rax, [rbp+Data]
0x180027d16  mov     [rbp+cbData], 4
0x180027d1d  mov     [rsp+30h+phkResult], rax; lpData
0x180027d22  call    cs:__imp_RegQueryValueExW
0x180027d29  nop     dword ptr [rax+rax+00h]
0x180027d2e  mov     ebx, eax
0x180027d30  test    eax, eax
0x180027d32  jnz     loc_180027EAD
0x180027d38  cmp     [rbp+Data], eax
0x180027d3b  jz      loc_180027EAD
0x180027d41  and     [rbp+cbData], eax
0x180027d44  lea     rdx, aSimulatecollis_0; "SimulateCollisionDllPath"
0x180027d4b  mov     rcx, cs:gblHKeyTest; hKey
0x180027d52  lea     rax, [rbp+cbData]
0x180027d56  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027d5b  xor     r9d, r9d; lpType
0x180027d5e  and     [rsp+30h+phkResult], 0
0x180027d64  xor     r8d, r8d; lpReserved
0x180027d67  call    cs:__imp_RegQueryValueExW
0x180027d6e  nop     dword ptr [rax+rax+00h]
0x180027d73  mov     ebx, eax
0x180027d75  test    eax, eax
0x180027d77  jnz     loc_180027EAD
0x180027d7d  mov     r8d, [rbp+cbData]; dwBytes
0x180027d81  lea     edx, [rax+8]; dwFlags
0x180027d84  mov     rcx, cs:hHeap; hHeap
0x180027d8b  call    cs:__imp_HeapAlloc
0x180027d92  nop     dword ptr [rax+rax+00h]
0x180027d97  mov     rdi, rax
0x180027d9a  test    rax, rax
0x180027d9d  jnz     short loc_180027DA7
0x180027d9f  lea     ebx, [rax+0Eh]
0x180027da2  jmp     loc_180027EAD
0x180027da7  mov     rcx, cs:gblHKeyTest; hKey
0x180027dae  lea     rax, [rbp+cbData]
0x180027db2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027db7  lea     r9, [rbp+Type]; lpType
0x180027dbb  xor     r8d, r8d; lpReserved
0x180027dbe  mov     [rsp+30h+phkResult], rdi; lpData
0x180027dc3  lea     rdx, aSimulatecollis_0; "SimulateCollisionDllPath"
0x180027dca  call    cs:__imp_RegQueryValueExW
0x180027dd1  nop     dword ptr [rax+rax+00h]
0x180027dd6  mov     rcx, cs:gblHKeyTest; hKey
0x180027ddd  lea     rax, [rbp+cbData]
0x180027de1  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027de6  lea     r9, [rbp+Type]; lpType
0x180027dea  lea     rax, [rbp+arg_18]
0x180027dee  mov     [rbp+cbData], 4
0x180027df5  xor     r8d, r8d; lpReserved
0x180027df8  mov     [rsp+30h+phkResult], rax; lpData
0x180027dfd  lea     rdx, aSimulatecollis; "SimulateCollisionSleepTime"
0x180027e04  call    cs:__imp_RegQueryValueExW
0x180027e0b  nop     dword ptr [rax+rax+00h]
0x180027e10  mov     ebx, eax
0x180027e12  test    eax, eax
0x180027e14  jnz     loc_180027EAD
0x180027e1a  mov     rax, cs:hSimulateCollisionTestDll
0x180027e21  test    rax, rax
0x180027e24  jnz     short loc_180027E59
0x180027e26  xor     edx, edx; hFile
0x180027e28  mov     r8d, 800h; dwFlags
0x180027e2e  mov     rcx, rdi; lpLibFileName
0x180027e31  call    cs:__imp_LoadLibraryExW
0x180027e38  nop     dword ptr [rax+rax+00h]
0x180027e3d  mov     cs:hSimulateCollisionTestDll, rax
0x180027e44  test    rax, rax
0x180027e47  jnz     short loc_180027E59
0x180027e49  call    cs:__imp_GetLastError
0x180027e50  nop     dword ptr [rax+rax+00h]
0x180027e55  mov     ebx, eax
0x180027e57  jmp     short loc_180027EAD
0x180027e59  mov     rdx, cs:pfnSimulateCollisonTestFunc
0x180027e60  test    rdx, rdx
0x180027e63  jnz     short loc_180027E8A
0x180027e65  lea     rdx, aSimulatecollis_1; "SimulateCollision"
0x180027e6c  mov     rcx, rax; hModule
0x180027e6f  call    cs:__imp_GetProcAddress
0x180027e76  nop     dword ptr [rax+rax+00h]
0x180027e7b  mov     cs:pfnSimulateCollisonTestFunc, rax
0x180027e82  mov     rdx, rax
0x180027e85  test    rax, rax
0x180027e88  jz      short loc_180027E49
0x180027e8a  mov     ecx, [rbp+arg_18]
0x180027e8d  mov     rax, rdx
0x180027e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e95  mov     rcx, cs:hHeap; hHeap
0x180027e9c  mov     r8, rdi; lpMem
0x180027e9f  xor     edx, edx; dwFlags
0x180027ea1  call    cs:__imp_HeapFree
0x180027ea8  nop     dword ptr [rax+rax+00h]
0x180027ead  mov     eax, ebx
0x180027eaf  add     rsp, 30h
0x180027eb3  pop     rdi
0x180027eb4  pop     rbx
0x180027eb5  pop     rbp
0x180027eb6  retn
```
