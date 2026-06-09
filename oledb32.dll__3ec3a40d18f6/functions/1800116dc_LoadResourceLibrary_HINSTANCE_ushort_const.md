# LoadResourceLibrary(HINSTANCE__ *,ushort const *)

- ea: `0x1800116dc`
- end: `0x18001183c`
- name: `?LoadResourceLibrary@@YAPEAUHINSTANCE__@@PEAU1@PEBG@Z`
- size: `352`
- prototype: `HINSTANCE __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800115ac`
- `0x1800593d8`

## callees

- `0x1800116dc`
- `0x18003bcec`
- `0x18007e700`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x18001177e`
- `msvcrt!_wsplitpath_s` at `0x1800117c0`
- `msvcrt!_wsplitpath_s` at `0x18001177e`
- `msvcrt!_wsplitpath_s` at `0x1800117c0`
- `msvcrt!_wmakepath_s` at `0x1800117f8`
- `msvcrt!_wmakepath_s` at `0x1800117f8`
- `KERNEL32!GetModuleFileNameW` at `0x180011730`
- `KERNEL32!GetModuleFileNameW` at `0x180011730`

## string_xrefs

- `0x18001179b`: `OLEDB32R.DLL`

## pseudocode

```c
__int64 __fastcall LoadResourceLibrary(HINSTANCE a1, const unsigned __int16 *a2)
{
  __int64 v2; // rbx
  DWORD ModuleFileNameW; // eax
  wchar_t Drive[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Ext[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v7[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Dir[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR Filename[776]; // [rsp+690h] [rbp+590h] BYREF

  Drive[0] = 0;
  Dir[0] = 0;
  v2 = 0;
  v7[0] = 0;
  Ext[0] = 0;
  ModuleFileNameW = GetModuleFileNameW(a1, Filename, 0x304u);
  if ( ModuleFileNameW
    && ModuleFileNameW != 772
    && !_wsplitpath_s(Filename, Drive, 4u, Dir, 0x101u, 0, 0, 0, 0)
    && !_wsplitpath_s(L"OLEDB32R.DLL", 0, 0, 0, 0, v7, 0x101u, Ext, 0x101u)
    && !_wmakepath_s(Filename, 0x304u, Drive, Dir, v7, Ext) )
  {
    return IsolationAwareLoadLibraryExW(Filename);
  }
  return v2;
}

```

## disassembly

```asm
0x1800116dc  mov     [rsp-8+arg_8], rbx
0x1800116e1  mov     [rsp-8+arg_10], rsi
0x1800116e6  push    rbp
0x1800116e7  lea     rbp, [rsp-0BB0h]
0x1800116ef  sub     rsp, 0CB0h
0x1800116f6  mov     rax, cs:__security_cookie
0x1800116fd  xor     rax, rsp
0x180011700  mov     [rbp+0BB0h+var_10], rax
0x180011707  xor     eax, eax
0x180011709  lea     rdx, [rbp+0BB0h+Filename]; lpFilename
0x180011710  mov     r8d, 304h; nSize
0x180011716  mov     [rsp+0CB0h+Drive], ax
0x18001171b  mov     [rbp+0BB0h+Dir], ax
0x180011722  xor     ebx, ebx
0x180011724  mov     [rbp+0BB0h+var_A40], ax
0x18001172b  mov     [rsp+0CB0h+var_C50], ax
0x180011730  call    cs:__imp_GetModuleFileNameW
0x180011736  test    eax, eax
0x180011738  jz      loc_180011815
0x18001173e  cmp     eax, 304h
0x180011743  jz      loc_180011815
0x180011749  mov     [rsp+0CB0h+ExtCount], rbx; ExtCount
0x18001174e  lea     r9, [rbp+0BB0h+Dir]; Dir
0x180011755  mov     [rsp+0CB0h+Ext], rbx; Ext
0x18001175a  lea     r8d, [rbx+4]; DriveCount
0x18001175e  mov     [rsp+0CB0h+FilenameCount], rbx; FilenameCount
0x180011763  lea     rdx, [rsp+0CB0h+Drive]; Drive
0x180011768  mov     esi, 101h
0x18001176d  mov     [rsp+0CB0h+var_C88], rbx; Filename
0x180011772  lea     rcx, [rbp+0BB0h+Filename]; FullPath
0x180011779  mov     [rsp+0CB0h+DirCount], rsi; DirCount
0x18001177e  call    cs:__imp__wsplitpath_s
0x180011784  test    eax, eax
0x180011786  jnz     loc_180011815
0x18001178c  mov     [rsp+0CB0h+ExtCount], rsi; ExtCount
0x180011791  lea     rax, [rsp+0CB0h+var_C50]
0x180011796  mov     [rsp+0CB0h+Ext], rax; Ext
0x18001179b  lea     rcx, aOledb32rDll; "OLEDB32R.DLL"
0x1800117a2  lea     rax, [rbp+0BB0h+var_A40]
0x1800117a9  mov     [rsp+0CB0h+FilenameCount], rsi; FilenameCount
0x1800117ae  mov     [rsp+0CB0h+var_C88], rax; Filename
0x1800117b3  xor     r9d, r9d; Dir
0x1800117b6  xor     r8d, r8d; DriveCount
0x1800117b9  mov     [rsp+0CB0h+DirCount], rbx; DirCount
0x1800117be  xor     edx, edx; Drive
0x1800117c0  call    cs:__imp__wsplitpath_s
0x1800117c6  test    eax, eax
0x1800117c8  jnz     short loc_180011815
0x1800117ca  lea     rax, [rsp+0CB0h+var_C50]
0x1800117cf  mov     edx, 304h; BufferCount
0x1800117d4  mov     [rsp+0CB0h+var_C88], rax; Ext
0x1800117d9  lea     r9, [rbp+0BB0h+Dir]; Dir
0x1800117e0  lea     rax, [rbp+0BB0h+var_A40]
0x1800117e7  lea     r8, [rsp+0CB0h+Drive]; Drive
0x1800117ec  mov     [rsp+0CB0h+DirCount], rax; Filename
0x1800117f1  lea     rcx, [rbp+0BB0h+Filename]; Buffer
0x1800117f8  call    cs:__imp__wmakepath_s
0x1800117fe  test    eax, eax
0x180011800  jnz     short loc_180011815
0x180011802  lea     r8d, [rbx+60h]
0x180011806  lea     rcx, [rbp+0BB0h+Filename]; lpLibFileName
0x18001180d  call    IsolationAwareLoadLibraryExW
0x180011812  mov     rbx, rax
0x180011815  mov     rax, rbx
0x180011818  mov     rcx, [rbp+0BB0h+var_10]
0x18001181f  xor     rcx, rsp; StackCookie
0x180011822  call    __security_check_cookie
0x180011827  lea     r11, [rsp+0CB0h+var_s0]
0x18001182f  mov     rbx, [r11+18h]
0x180011833  mov     rsi, [r11+20h]
0x180011837  mov     rsp, r11
0x18001183a  pop     rbp
0x18001183b  retn
```
