# _pSpUtilsHwCfgGetRootKey

- ea: `0x180006c54`
- end: `0x180006e20`
- name: `_pSpUtilsHwCfgGetRootKey`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006590`

## callees

- `0x180006c54`
- `0x18000b010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180006cff`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180006d68`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180006cff`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180006d68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006d8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006dbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006d8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006dbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006dfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006dfc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006e0a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006e0a`
- `KERNEL32!HeapFree` at `0x180006dec`
- `KERNEL32!HeapFree` at `0x180006dec`
- `KERNEL32!HeapAlloc` at `0x180006d1a`
- `KERNEL32!HeapAlloc` at `0x180006d1a`
- `KERNEL32!LoadLibraryExW` at `0x180006c84`
- `KERNEL32!LoadLibraryExW` at `0x180006c84`
- `KERNEL32!GetProcAddress` at `0x180006ca0`
- `KERNEL32!GetProcAddress` at `0x180006ca0`

## string_xrefs

- `0x180006c7d`: `ntdll.dll`
- `0x180006cbf`: `System\HardwareConfig`
- `0x180006d3d`: `System\HardwareConfig`
- `0x180006dac`: `System\HardwareConfig`
- `0x180006cce`: `HardwareConfigState`
- `0x180006d48`: `HardwareConfigState`

## pseudocode

```c
__int64 __fastcall pSpUtilsHwCfgGetRootKey(__int64 a1, HKEY *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbx
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  WCHAR *v9; // rdi
  NTSTATUS v10; // eax
  SIZE_T dwBytes; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  hKey = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v4 = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation"),
        (v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress) == 0) )
  {
    v9 = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, 1u, &hKey);
    if ( v8 )
      goto LABEL_16;
    goto LABEL_14;
  }
  v7 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const WCHAR *, _QWORD, _QWORD, _DWORD, SIZE_T *))ProcAddress)(
         L"HardwareConfigState",
         0,
         L"System\\HardwareConfig",
         0,
         0,
         0,
         &dwBytes);
  if ( v7 >= 0 )
  {
    v8 = 1359;
    goto LABEL_16;
  }
  if ( v7 != -2147483643 )
  {
    v8 = RtlNtStatusToDosErrorNoTeb(v7);
    goto LABEL_16;
  }
  v9 = (WCHAR *)HeapAlloc(hHeap, 0, (unsigned int)dwBytes);
  if ( !v9 )
  {
    v8 = 8;
    goto LABEL_16;
  }
  v10 = v6(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v9, dwBytes, &dwBytes);
  if ( v10 >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 1u, &hKey);
    if ( v8 )
      goto LABEL_15;
LABEL_14:
    *a2 = hKey;
    hKey = 0;
    if ( !v9 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v8 = RtlNtStatusToDosErrorNoTeb(v10);
LABEL_15:
  HeapFree(hHeap, 0, v9);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    FreeLibrary(v4);
  return v8;
}

```

## disassembly

```asm
0x180006c54  mov     rax, rsp
0x180006c57  mov     [rax+10h], rbx
0x180006c5b  mov     [rax+8], ecx
0x180006c5e  push    rsi
0x180006c5f  push    rdi
0x180006c60  push    r14
0x180006c62  sub     rsp, 40h
0x180006c66  mov     r14, rdx
0x180006c69  mov     dword ptr [rax+8], 0
0x180006c70  xor     edx, edx; hFile
0x180006c72  mov     qword ptr [rax+18h], 0
0x180006c7a  xor     r8d, r8d; dwFlags
0x180006c7d  lea     rcx, ModuleName; "ntdll.dll"
0x180006c84  call    cs:__imp_LoadLibraryExW
0x180006c8a  mov     rsi, rax
0x180006c8d  test    rax, rax
0x180006c90  jz      loc_180006D9D
0x180006c96  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x180006c9d  mov     rcx, rax; hModule
0x180006ca0  call    cs:__imp_GetProcAddress
0x180006ca6  mov     rbx, rax
0x180006ca9  test    rax, rax
0x180006cac  jz      loc_180006D9D
0x180006cb2  lea     rax, [rsp+58h+dwBytes]
0x180006cb7  xor     r9d, r9d
0x180006cba  mov     [rsp+58h+var_28], rax
0x180006cbf  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180006cc6  mov     [rsp+58h+var_30], 0
0x180006cce  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x180006cd5  mov     rax, rbx
0x180006cd8  mov     [rsp+58h+phkResult], 0
0x180006ce1  xor     edx, edx
0x180006ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce8  test    eax, eax
0x180006cea  js      short loc_180006CF6
0x180006cec  mov     ebx, 54Fh
0x180006cf1  jmp     loc_180006DF2
0x180006cf6  cmp     eax, 80000005h
0x180006cfb  jz      short loc_180006D0C
0x180006cfd  mov     ecx, eax; Status
0x180006cff  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180006d05  mov     ebx, eax
0x180006d07  jmp     loc_180006DF2
0x180006d0c  mov     r8d, dword ptr [rsp+58h+dwBytes]; dwBytes
0x180006d11  xor     edx, edx; dwFlags
0x180006d13  mov     rcx, cs:hHeap; hHeap
0x180006d1a  call    cs:__imp_HeapAlloc
0x180006d20  mov     rdi, rax
0x180006d23  test    rax, rax
0x180006d26  jnz     short loc_180006D30
0x180006d28  lea     ebx, [rax+8]
0x180006d2b  jmp     loc_180006DF2
0x180006d30  lea     rax, [rsp+58h+dwBytes]
0x180006d35  xor     r9d, r9d
0x180006d38  mov     [rsp+58h+var_28], rax
0x180006d3d  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180006d44  mov     eax, dword ptr [rsp+58h+dwBytes]
0x180006d48  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x180006d4f  mov     [rsp+58h+var_30], eax
0x180006d53  xor     edx, edx
0x180006d55  mov     rax, rbx
0x180006d58  mov     [rsp+58h+phkResult], rdi
0x180006d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d62  test    eax, eax
0x180006d64  jns     short loc_180006D72
0x180006d66  mov     ecx, eax; Status
0x180006d68  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180006d6e  mov     ebx, eax
0x180006d70  jmp     short loc_180006DE0
0x180006d72  lea     rax, [rsp+58h+hKey]
0x180006d77  mov     r9d, 1; samDesired
0x180006d7d  xor     r8d, r8d; ulOptions
0x180006d80  mov     [rsp+58h+phkResult], rax; phkResult
0x180006d85  mov     rdx, rdi; lpSubKey
0x180006d88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006d8f  call    cs:__imp_RegOpenKeyExW
0x180006d95  mov     ebx, eax
0x180006d97  test    eax, eax
0x180006d99  jnz     short loc_180006DE0
0x180006d9b  jmp     short loc_180006DCA
0x180006d9d  lea     rax, [rsp+58h+hKey]
0x180006da2  xor     edi, edi
0x180006da4  xor     r8d, r8d; ulOptions
0x180006da7  mov     [rsp+58h+phkResult], rax; phkResult
0x180006dac  lea     rdx, aSystemHardware; "System\\HardwareConfig"
0x180006db3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006dba  lea     r9d, [rdi+1]; samDesired
0x180006dbe  call    cs:__imp_RegOpenKeyExW
0x180006dc4  mov     ebx, eax
0x180006dc6  test    eax, eax
0x180006dc8  jnz     short loc_180006DF2
0x180006dca  mov     rax, [rsp+58h+hKey]
0x180006dcf  mov     [r14], rax
0x180006dd2  mov     [rsp+58h+hKey], 0
0x180006ddb  test    rdi, rdi
0x180006dde  jz      short loc_180006DF2
0x180006de0  mov     rcx, cs:hHeap; hHeap
0x180006de7  mov     r8, rdi; lpMem
0x180006dea  xor     edx, edx; dwFlags
0x180006dec  call    cs:__imp_HeapFree
0x180006df2  mov     rcx, [rsp+58h+hKey]; hKey
0x180006df7  test    rcx, rcx
0x180006dfa  jz      short loc_180006E02
0x180006dfc  call    cs:__imp_RegCloseKey
0x180006e02  test    rsi, rsi
0x180006e05  jz      short loc_180006E10
0x180006e07  mov     rcx, rsi; hLibModule
0x180006e0a  call    cs:__imp_FreeLibrary
0x180006e10  mov     eax, ebx
0x180006e12  mov     rbx, [rsp+58h+arg_8]
0x180006e17  add     rsp, 40h
0x180006e1b  pop     r14
0x180006e1d  pop     rdi
0x180006e1e  pop     rsi
0x180006e1f  retn
```
