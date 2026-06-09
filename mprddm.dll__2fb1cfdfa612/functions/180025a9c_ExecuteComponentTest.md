# ExecuteComponentTest

- ea: `0x180025a9c`
- end: `0x180025c92`
- name: `ExecuteComponentTest`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180046270`

## callees

- `0x180025a9c`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025c56`
- `KERNEL32!GetProcAddress` at `0x180025c56`
- `KERNEL32!LoadLibraryExW` at `0x180025c24`
- `KERNEL32!LoadLibraryExW` at `0x180025c24`
- `KERNEL32!HeapAlloc` at `0x180025b94`
- `KERNEL32!HeapAlloc` at `0x180025b94`
- `KERNEL32!GetLastError` at `0x180025c36`
- `KERNEL32!GetLastError` at `0x180025c36`
- `KERNEL32!HeapFree` at `0x180025c82`
- `KERNEL32!HeapFree` at `0x180025c82`
- `ADVAPI32!RegOpenKeyExW` at `0x180025ad9`
- `ADVAPI32!RegOpenKeyExW` at `0x180025ad9`
- `ADVAPI32!RegQueryValueExW` at `0x180025b34`
- `ADVAPI32!RegQueryValueExW` at `0x180025b76`
- `ADVAPI32!RegQueryValueExW` at `0x180025bcd`
- `ADVAPI32!RegQueryValueExW` at `0x180025c01`
- `ADVAPI32!RegQueryValueExW` at `0x180025b34`
- `ADVAPI32!RegQueryValueExW` at `0x180025b76`
- `ADVAPI32!RegQueryValueExW` at `0x180025bcd`
- `ADVAPI32!RegQueryValueExW` at `0x180025c01`

## string_xrefs

- `0x180025acb`: `System\CurrentControlSet\Services\RemoteAccess\Test`
- `0x180025b54`: `SimulateCollisionDllPath`
- `0x180025bc6`: `SimulateCollisionDllPath`

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
  if ( !gblHKeyTest )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\Test",
           0,
           0x20019u,
           &gblHKeyTest) )
    {
      v2 = 0;
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
0x180025a9c  mov     [rsp-18h+cbData], ecx
0x180025aa0  push    rbp
0x180025aa1  push    rbx
0x180025aa2  push    rdi
0x180025aa3  mov     rbp, rsp
0x180025aa6  sub     rsp, 30h
0x180025aaa  mov     rcx, cs:gblHKeyTest
0x180025ab1  test    rcx, rcx
0x180025ab4  jnz     short loc_180025AF8
0x180025ab6  lea     rax, gblHKeyTest
0x180025abd  mov     r9d, 20019h; samDesired
0x180025ac3  xor     r8d, r8d; ulOptions
0x180025ac6  mov     [rsp+30h+phkResult], rax; phkResult
0x180025acb  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Re"...
0x180025ad2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025ad9  call    cs:__imp_RegOpenKeyExW
0x180025adf  test    eax, eax
0x180025ae1  jz      short loc_180025AF1
0x180025ae3  xor     ebx, ebx
0x180025ae5  mov     cs:gblHKeyTest, rbx
0x180025aec  jmp     loc_180025C88
0x180025af1  mov     rcx, cs:gblHKeyTest; hKey
0x180025af8  lea     rax, [rbp+cbData]
0x180025afc  mov     [rbp+Type], 0
0x180025b03  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025b08  lea     r9, [rbp+Type]; lpType
0x180025b0c  lea     rax, [rbp+Data]
0x180025b10  mov     [rbp+Data], 0
0x180025b17  xor     r8d, r8d; lpReserved
0x180025b1a  mov     [rsp+30h+phkResult], rax; lpData
0x180025b1f  lea     rdx, aSimulatecollis_2; "SimulateCollision"
0x180025b26  mov     [rbp+arg_18], 0
0x180025b2d  mov     [rbp+cbData], 4
0x180025b34  call    cs:__imp_RegQueryValueExW
0x180025b3a  mov     ebx, eax
0x180025b3c  test    eax, eax
0x180025b3e  jnz     loc_180025C88
0x180025b44  cmp     [rbp+Data], eax
0x180025b47  jz      loc_180025C88
0x180025b4d  mov     rcx, cs:gblHKeyTest; hKey
0x180025b54  lea     rdx, aSimulatecollis_0; "SimulateCollisionDllPath"
0x180025b5b  mov     [rbp+cbData], eax
0x180025b5e  xor     r9d, r9d; lpType
0x180025b61  lea     rax, [rbp+cbData]
0x180025b65  xor     r8d, r8d; lpReserved
0x180025b68  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025b6d  mov     [rsp+30h+phkResult], 0; lpData
0x180025b76  call    cs:__imp_RegQueryValueExW
0x180025b7c  mov     ebx, eax
0x180025b7e  test    eax, eax
0x180025b80  jnz     loc_180025C88
0x180025b86  mov     r8d, [rbp+cbData]; dwBytes
0x180025b8a  lea     edx, [rax+8]; dwFlags
0x180025b8d  mov     rcx, cs:hHeap; hHeap
0x180025b94  call    cs:__imp_HeapAlloc
0x180025b9a  mov     rdi, rax
0x180025b9d  test    rax, rax
0x180025ba0  jnz     short loc_180025BAA
0x180025ba2  lea     ebx, [rax+0Eh]
0x180025ba5  jmp     loc_180025C88
0x180025baa  mov     rcx, cs:gblHKeyTest; hKey
0x180025bb1  lea     rax, [rbp+cbData]
0x180025bb5  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025bba  lea     r9, [rbp+Type]; lpType
0x180025bbe  xor     r8d, r8d; lpReserved
0x180025bc1  mov     [rsp+30h+phkResult], rdi; lpData
0x180025bc6  lea     rdx, aSimulatecollis_0; "SimulateCollisionDllPath"
0x180025bcd  call    cs:__imp_RegQueryValueExW
0x180025bd3  mov     rcx, cs:gblHKeyTest; hKey
0x180025bda  lea     rax, [rbp+cbData]
0x180025bde  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025be3  lea     r9, [rbp+Type]; lpType
0x180025be7  lea     rax, [rbp+arg_18]
0x180025beb  mov     [rbp+cbData], 4
0x180025bf2  xor     r8d, r8d; lpReserved
0x180025bf5  mov     [rsp+30h+phkResult], rax; lpData
0x180025bfa  lea     rdx, aSimulatecollis; "SimulateCollisionSleepTime"
0x180025c01  call    cs:__imp_RegQueryValueExW
0x180025c07  mov     ebx, eax
0x180025c09  test    eax, eax
0x180025c0b  jnz     short loc_180025C88
0x180025c0d  mov     rax, cs:hSimulateCollisionTestDll
0x180025c14  test    rax, rax
0x180025c17  jnz     short loc_180025C40
0x180025c19  xor     edx, edx; hFile
0x180025c1b  mov     r8d, 800h; dwFlags
0x180025c21  mov     rcx, rdi; lpLibFileName
0x180025c24  call    cs:__imp_LoadLibraryExW
0x180025c2a  mov     cs:hSimulateCollisionTestDll, rax
0x180025c31  test    rax, rax
0x180025c34  jnz     short loc_180025C40
0x180025c36  call    cs:__imp_GetLastError
0x180025c3c  mov     ebx, eax
0x180025c3e  jmp     short loc_180025C88
0x180025c40  mov     rdx, cs:pfnSimulateCollisonTestFunc
0x180025c47  test    rdx, rdx
0x180025c4a  jnz     short loc_180025C6B
0x180025c4c  lea     rdx, aSimulatecollis_1; "SimulateCollision"
0x180025c53  mov     rcx, rax; hModule
0x180025c56  call    cs:__imp_GetProcAddress
0x180025c5c  mov     cs:pfnSimulateCollisonTestFunc, rax
0x180025c63  mov     rdx, rax
0x180025c66  test    rax, rax
0x180025c69  jz      short loc_180025C36
0x180025c6b  mov     ecx, [rbp+arg_18]
0x180025c6e  mov     rax, rdx
0x180025c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c76  mov     rcx, cs:hHeap; hHeap
0x180025c7d  mov     r8, rdi; lpMem
0x180025c80  xor     edx, edx; dwFlags
0x180025c82  call    cs:__imp_HeapFree
0x180025c88  mov     eax, ebx
0x180025c8a  add     rsp, 30h
0x180025c8e  pop     rdi
0x180025c8f  pop     rbx
0x180025c90  pop     rbp
0x180025c91  retn
```
