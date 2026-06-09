# HHGetWindowsDirectory(char *,unsigned __int64,uint)

- ea: `0x18004eea0`
- end: `0x18004efee`
- name: `?HHGetWindowsDirectory@@YAKPEAD_KI@Z`
- size: `334`
- prototype: `unsigned int __fastcall(LPBYTE lpData, unsigned __int64, unsigned int)`
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001dd04`
- `0x1800269d0`
- `0x18002fb58`
- `0x180030704`
- `0x180037594`
- `0x180038028`
- `0x180038640`
- `0x180041e20`
- `0x18004ed04`
- `0x1800591ac`
- `0x180067c20`
- `0x180067e60`

## callees

- `0x180002a64`
- `0x18004eea0`
- `0x180078010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18004ef27`
- `KERNEL32!FreeLibrary` at `0x18004ef27`
- `KERNEL32!GetProcAddress` at `0x18004eeef`
- `KERNEL32!GetProcAddress` at `0x18004ef06`
- `KERNEL32!GetProcAddress` at `0x18004eeef`
- `KERNEL32!GetProcAddress` at `0x18004ef06`
- `KERNEL32!GetLastError` at `0x18004eeda`
- `KERNEL32!GetLastError` at `0x18004efd4`
- `KERNEL32!GetLastError` at `0x18004eeda`
- `KERNEL32!GetLastError` at `0x18004efd4`
- `ADVAPI32!RegCloseKey` at `0x18004ef9b`
- `ADVAPI32!RegCloseKey` at `0x18004ef9b`
- `ADVAPI32!RegQueryValueExA` at `0x18004ef90`
- `ADVAPI32!RegQueryValueExA` at `0x18004ef90`
- `ADVAPI32!RegOpenKeyExA` at `0x18004ef60`
- `ADVAPI32!RegOpenKeyExA` at `0x18004ef60`

## string_xrefs

- `0x18004eee5`: `GetSystemWindowsDirectoryA`
- `0x18004eef5`: `GetWindowsDirectoryA`

## pseudocode

```c
DWORD __fastcall HHGetWindowsDirectory(LPBYTE lpData, __int64 a2, int a3)
{
  HMODULE LibraryA; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  int v10; // ebx
  int v11; // eax
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  if ( !qword_18008C850 || !qword_18008C848 )
  {
    LibraryA = (HMODULE)IsolationAwareLoadLibraryA("Kernel32");
    v7 = LibraryA;
    if ( !LibraryA )
      return GetLastError();
    qword_18008C850 = (__int64)GetProcAddress(LibraryA, "GetSystemWindowsDirectoryA");
    ProcAddress = GetProcAddress(v7, "GetWindowsDirectoryA");
    qword_18008C848 = (__int64)ProcAddress;
    if ( !qword_18008C850 )
      qword_18008C850 = (__int64)ProcAddress;
    FreeLibrary(v7);
  }
  v10 = 0;
  cbData = a2;
  hKey = 0;
  Type = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows\\CurrentVersion\\Setup", 0, 0x20019u, &hKey) )
  {
    RegQueryValueExA(hKey, "SharedDir", 0, &Type, lpData, &cbData);
    RegCloseKey(hKey);
  }
  if ( cbData == a2 )
  {
    if ( !a3 )
    {
      v11 = ((__int64 (__fastcall *)(LPBYTE, _QWORD))qword_18008C850)(lpData, (unsigned int)a2);
      goto LABEL_15;
    }
    if ( a3 == 1 )
    {
      v11 = ((__int64 (__fastcall *)(LPBYTE, _QWORD))qword_18008C848)(lpData, (unsigned int)a2);
LABEL_15:
      if ( !v11 )
        return GetLastError();
      return v10;
    }
    return -2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x18004eea0  push    rbx
0x18004eea2  push    rbp
0x18004eea3  push    rsi
0x18004eea4  push    rdi
0x18004eea5  sub     rsp, 48h
0x18004eea9  cmp     cs:qword_18008C850, 0
0x18004eeb1  mov     esi, r8d
0x18004eeb4  mov     rdi, rdx
0x18004eeb7  mov     rbp, rcx
0x18004eeba  jz      short loc_18004EEC6
0x18004eebc  cmp     cs:qword_18008C848, 0
0x18004eec4  jnz     short loc_18004EF2D
0x18004eec6  lea     rcx, aKernel32; "Kernel32"
0x18004eecd  call    IsolationAwareLoadLibraryA
0x18004eed2  mov     rbx, rax
0x18004eed5  test    rax, rax
0x18004eed8  jnz     short loc_18004EEE5
0x18004eeda  call    cs:__imp_GetLastError
0x18004eee0  jmp     loc_18004EFE5
0x18004eee5  lea     rdx, aGetsystemwindo; "GetSystemWindowsDirectoryA"
0x18004eeec  mov     rcx, rbx; hModule
0x18004eeef  call    cs:__imp_GetProcAddress
0x18004eef5  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryA"
0x18004eefc  mov     rcx, rbx; hModule
0x18004eeff  mov     cs:qword_18008C850, rax
0x18004ef06  call    cs:__imp_GetProcAddress
0x18004ef0c  cmp     cs:qword_18008C850, 0
0x18004ef14  mov     cs:qword_18008C848, rax
0x18004ef1b  jnz     short loc_18004EF24
0x18004ef1d  mov     cs:qword_18008C850, rax
0x18004ef24  mov     rcx, rbx; hLibModule
0x18004ef27  call    cs:__imp_FreeLibrary
0x18004ef2d  xor     ebx, ebx
0x18004ef2f  mov     [rsp+68h+cbData], edi
0x18004ef36  lea     rax, [rsp+68h+hKey]
0x18004ef3b  mov     [rsp+68h+hKey], rbx
0x18004ef40  mov     r9d, 20019h; samDesired
0x18004ef46  mov     [rsp+68h+Type], ebx
0x18004ef4a  xor     r8d, r8d; ulOptions
0x18004ef4d  mov     [rsp+68h+phkResult], rax; phkResult
0x18004ef52  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004ef59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ef60  call    cs:__imp_RegOpenKeyExA
0x18004ef66  test    eax, eax
0x18004ef68  jnz     short loc_18004EFA1
0x18004ef6a  mov     rcx, [rsp+68h+hKey]; hKey
0x18004ef6f  lea     rax, [rsp+68h+cbData]
0x18004ef77  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18004ef7c  lea     r9, [rsp+68h+Type]; lpType
0x18004ef81  xor     r8d, r8d; lpReserved
0x18004ef84  mov     [rsp+68h+phkResult], rbp; lpData
0x18004ef89  lea     rdx, aShareddir; "SharedDir"
0x18004ef90  call    cs:__imp_RegQueryValueExA
0x18004ef96  mov     rcx, [rsp+68h+hKey]; hKey
0x18004ef9b  call    cs:__imp_RegCloseKey
0x18004efa1  mov     eax, [rsp+68h+cbData]
0x18004efa8  cmp     rax, rdi
0x18004efab  jnz     short loc_18004EFE3
0x18004efad  test    esi, esi
0x18004efaf  jnz     short loc_18004EFBA
0x18004efb1  mov     rax, cs:qword_18008C850
0x18004efb8  jmp     short loc_18004EFC6
0x18004efba  cmp     esi, 1
0x18004efbd  jnz     short loc_18004EFDE
0x18004efbf  mov     rax, cs:qword_18008C848
0x18004efc6  mov     rcx, rbp
0x18004efc9  mov     edx, edi
0x18004efcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efd0  test    eax, eax
0x18004efd2  jnz     short loc_18004EFE3
0x18004efd4  call    cs:__imp_GetLastError
0x18004efda  mov     ebx, eax
0x18004efdc  jmp     short loc_18004EFE3
0x18004efde  mov     ebx, 80070057h
0x18004efe3  mov     eax, ebx
0x18004efe5  add     rsp, 48h
0x18004efe9  pop     rdi
0x18004efea  pop     rsi
0x18004efeb  pop     rbp
0x18004efec  pop     rbx
0x18004efed  retn
```
