# HwCfgGetRootKey

- ea: `0x18000480c`
- end: `0x1800049fb`
- name: `HwCfgGetRootKey`
- size: `495`
- prototype: `__int64 __fastcall(REGSAM samDesired, HKEY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800045b8`
- `0x18000474c`
- `0x180004a04`

## callees

- `0x18000480c`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800048bd`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180004933`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800048bd`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180004933`
- `KERNEL32!HeapFree` at `0x1800049c1`
- `KERNEL32!HeapFree` at `0x1800049c1`
- `KERNEL32!HeapAlloc` at `0x1800048df`
- `KERNEL32!HeapAlloc` at `0x1800048df`
- `KERNEL32!GetProcAddress` at `0x18000485b`
- `KERNEL32!GetProcAddress` at `0x18000485b`
- `KERNEL32!LoadLibraryExW` at `0x18000483f`
- `KERNEL32!LoadLibraryExW` at `0x18000483f`
- `KERNEL32!FreeLibrary` at `0x1800049e2`
- `KERNEL32!FreeLibrary` at `0x1800049e2`
- `KERNEL32!GetProcessHeap` at `0x1800048d1`
- `KERNEL32!GetProcessHeap` at `0x1800049b3`
- `KERNEL32!GetProcessHeap` at `0x1800048d1`
- `KERNEL32!GetProcessHeap` at `0x1800049b3`
- `ADVAPI32!RegOpenKeyExW` at `0x18000495a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000498b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000495a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000498b`
- `ADVAPI32!RegCloseKey` at `0x1800049d4`
- `ADVAPI32!RegCloseKey` at `0x1800049d4`

## string_xrefs

- `0x180004835`: `ntdll.dll`
- `0x18000487d`: `System\HardwareConfig`
- `0x180004905`: `System\HardwareConfig`
- `0x18000497b`: `System\HardwareConfig`
- `0x18000488c`: `HardwareConfigState`
- `0x180004913`: `HardwareConfigState`

## pseudocode

```c
__int64 __fastcall HwCfgGetRootKey(REGSAM samDesired, HKEY *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbp
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rdi
  NTSTATUS v13; // eax
  HANDLE v14; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  hKey = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v5 = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation"),
        (v7 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress) == 0) )
  {
    v12 = 0;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, samDesired, &hKey);
    if ( v9 )
      goto LABEL_16;
    goto LABEL_14;
  }
  v8 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const WCHAR *, _QWORD, _QWORD, _DWORD, SIZE_T *))ProcAddress)(
         L"HardwareConfigState",
         0,
         L"System\\HardwareConfig",
         0,
         0,
         0,
         &dwBytes);
  if ( v8 >= 0 )
  {
    v9 = 1359;
    goto LABEL_16;
  }
  if ( v8 != -2147483643 )
  {
    v9 = RtlNtStatusToDosErrorNoTeb(v8);
    goto LABEL_16;
  }
  v10 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v12 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v10);
  if ( !v12 )
  {
    v9 = 8;
    goto LABEL_16;
  }
  v13 = v7(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v12, dwBytes, &dwBytes);
  if ( v13 >= 0 )
  {
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, samDesired, &hKey);
    if ( v9 )
      goto LABEL_15;
LABEL_14:
    *a2 = hKey;
    hKey = 0;
    if ( !v12 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v9 = RtlNtStatusToDosErrorNoTeb(v13);
LABEL_15:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v12);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    FreeLibrary(v5);
  return v9;
}

```

## disassembly

```asm
0x18000480c  mov     rax, rsp
0x18000480f  mov     [rax+8], rbx
0x180004813  push    rbp
0x180004814  push    rsi
0x180004815  push    rdi
0x180004816  push    r14
0x180004818  push    r15
0x18000481a  sub     rsp, 40h
0x18000481e  mov     r15, rdx
0x180004821  mov     dword ptr [rax+18h], 0
0x180004828  mov     r14d, ecx
0x18000482b  mov     qword ptr [rax+20h], 0
0x180004833  xor     edx, edx; hFile
0x180004835  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000483c  xor     r8d, r8d; dwFlags
0x18000483f  call    cs:__imp_LoadLibraryExW
0x180004845  mov     rsi, rax
0x180004848  test    rax, rax
0x18000484b  jz      loc_180004968
0x180004851  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180004858  mov     rcx, rax; hModule
0x18000485b  call    cs:__imp_GetProcAddress
0x180004861  mov     rbp, rax
0x180004864  test    rax, rax
0x180004867  jz      loc_180004968
0x18000486d  lea     rax, [rsp+68h+dwBytes]
0x180004875  xor     r9d, r9d
0x180004878  mov     [rsp+68h+var_38], rax
0x18000487d  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180004884  mov     [rsp+68h+var_40], 0
0x18000488c  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x180004893  mov     rax, rbp
0x180004896  mov     [rsp+68h+phkResult], 0
0x18000489f  xor     edx, edx
0x1800048a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a6  test    eax, eax
0x1800048a8  js      short loc_1800048B4
0x1800048aa  mov     ebx, 54Fh
0x1800048af  jmp     loc_1800049C7
0x1800048b4  cmp     eax, 80000005h
0x1800048b9  jz      short loc_1800048CA
0x1800048bb  mov     ecx, eax; Status
0x1800048bd  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800048c3  mov     ebx, eax
0x1800048c5  jmp     loc_1800049C7
0x1800048ca  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x1800048d1  call    cs:__imp_GetProcessHeap
0x1800048d7  mov     r8d, ebx; dwBytes
0x1800048da  xor     edx, edx; dwFlags
0x1800048dc  mov     rcx, rax; hHeap
0x1800048df  call    cs:__imp_HeapAlloc
0x1800048e5  mov     rdi, rax
0x1800048e8  test    rax, rax
0x1800048eb  jnz     short loc_1800048F5
0x1800048ed  lea     ebx, [rax+8]
0x1800048f0  jmp     loc_1800049C7
0x1800048f5  lea     rax, [rsp+68h+dwBytes]
0x1800048fd  xor     r9d, r9d
0x180004900  mov     [rsp+68h+var_38], rax
0x180004905  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x18000490c  mov     eax, dword ptr [rsp+68h+dwBytes]
0x180004913  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x18000491a  mov     [rsp+68h+var_40], eax
0x18000491e  xor     edx, edx
0x180004920  mov     rax, rbp
0x180004923  mov     [rsp+68h+phkResult], rdi
0x180004928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492d  test    eax, eax
0x18000492f  jns     short loc_18000493D
0x180004931  mov     ecx, eax; Status
0x180004933  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180004939  mov     ebx, eax
0x18000493b  jmp     short loc_1800049B3
0x18000493d  lea     rax, [rsp+68h+hKey]
0x180004945  mov     r9d, r14d; samDesired
0x180004948  xor     r8d, r8d; ulOptions
0x18000494b  mov     [rsp+68h+phkResult], rax; phkResult
0x180004950  mov     rdx, rdi; lpSubKey
0x180004953  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000495a  call    cs:__imp_RegOpenKeyExW
0x180004960  mov     ebx, eax
0x180004962  test    eax, eax
0x180004964  jnz     short loc_1800049B3
0x180004966  jmp     short loc_180004997
0x180004968  lea     rax, [rsp+68h+hKey]
0x180004970  mov     r9d, r14d; samDesired
0x180004973  xor     r8d, r8d; ulOptions
0x180004976  mov     [rsp+68h+phkResult], rax; phkResult
0x18000497b  lea     rdx, aSystemHardware; "System\\HardwareConfig"
0x180004982  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004989  xor     edi, edi
0x18000498b  call    cs:__imp_RegOpenKeyExW
0x180004991  mov     ebx, eax
0x180004993  test    eax, eax
0x180004995  jnz     short loc_1800049C7
0x180004997  mov     rax, [rsp+68h+hKey]
0x18000499f  mov     [r15], rax
0x1800049a2  mov     [rsp+68h+hKey], 0
0x1800049ae  test    rdi, rdi
0x1800049b1  jz      short loc_1800049C7
0x1800049b3  call    cs:__imp_GetProcessHeap
0x1800049b9  mov     r8, rdi; lpMem
0x1800049bc  xor     edx, edx; dwFlags
0x1800049be  mov     rcx, rax; hHeap
0x1800049c1  call    cs:__imp_HeapFree
0x1800049c7  mov     rcx, [rsp+68h+hKey]; hKey
0x1800049cf  test    rcx, rcx
0x1800049d2  jz      short loc_1800049DA
0x1800049d4  call    cs:__imp_RegCloseKey
0x1800049da  test    rsi, rsi
0x1800049dd  jz      short loc_1800049E8
0x1800049df  mov     rcx, rsi; hLibModule
0x1800049e2  call    cs:__imp_FreeLibrary
0x1800049e8  mov     eax, ebx
0x1800049ea  mov     rbx, [rsp+68h+arg_0]
0x1800049ef  add     rsp, 40h
0x1800049f3  pop     r15
0x1800049f5  pop     r14
0x1800049f7  pop     rdi
0x1800049f8  pop     rsi
0x1800049f9  pop     rbp
0x1800049fa  retn
```
