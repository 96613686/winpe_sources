# LoadResourceLibrary(HINSTANCE__ *,ushort const *)

- ea: `0x1800ca5bc`
- end: `0x1800ca73e`
- name: `?LoadResourceLibrary@@YAPEAUHINSTANCE__@@PEAU1@PEBG@Z`
- size: `386`
- prototype: `HINSTANCE __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800ca578`

## callees

- `0x1800ca5bc`
- `0x1800cdb20`

## import_xrefs

- `msvcrt!_wmakepath_s` at `0x1800ca6ea`
- `msvcrt!_wmakepath_s` at `0x1800ca6ea`
- `msvcrt!_wsplitpath_s` at `0x1800ca664`
- `msvcrt!_wsplitpath_s` at `0x1800ca6ac`
- `msvcrt!_wsplitpath_s` at `0x1800ca664`
- `msvcrt!_wsplitpath_s` at `0x1800ca6ac`
- `KERNEL32!LoadLibraryExW` at `0x1800ca707`
- `KERNEL32!LoadLibraryExW` at `0x1800ca707`
- `KERNEL32!GetModuleFileNameW` at `0x1800ca610`
- `KERNEL32!GetModuleFileNameW` at `0x1800ca610`

## string_xrefs

- `0x1800ca687`: `msader15.dll`

## pseudocode

```c
HINSTANCE __fastcall LoadResourceLibrary(HINSTANCE a1, const unsigned __int16 *a2)
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
    && !_wsplitpath_s(L"msader15.dll", 0, 0, 0, 0, v7, 0x101u, Ext, 0x101u)
    && !_wmakepath_s(Filename, 0x304u, Drive, Dir, v7, Ext) )
  {
    return LoadLibraryExW(Filename, 0, 0x60u);
  }
  return (HINSTANCE)v2;
}

```

## disassembly

```asm
0x1800ca5bc  mov     [rsp-8+arg_8], rbx
0x1800ca5c1  mov     [rsp-8+arg_10], rsi
0x1800ca5c6  push    rbp
0x1800ca5c7  lea     rbp, [rsp-0BB0h]
0x1800ca5cf  sub     rsp, 0CB0h
0x1800ca5d6  mov     rax, cs:__security_cookie
0x1800ca5dd  xor     rax, rsp
0x1800ca5e0  mov     [rbp+0BB0h+var_10], rax
0x1800ca5e7  xor     eax, eax
0x1800ca5e9  lea     rdx, [rbp+0BB0h+Filename]; lpFilename
0x1800ca5f0  mov     r8d, 304h; nSize
0x1800ca5f6  mov     [rsp+0CB0h+Drive], ax
0x1800ca5fb  mov     [rbp+0BB0h+Dir], ax
0x1800ca602  xor     ebx, ebx
0x1800ca604  mov     [rbp+0BB0h+var_A40], ax
0x1800ca60b  mov     [rsp+0CB0h+var_C50], ax
0x1800ca610  call    cs:__imp_GetModuleFileNameW
0x1800ca617  nop     dword ptr [rax+rax+00h]
0x1800ca61c  test    eax, eax
0x1800ca61e  jz      loc_1800CA716
0x1800ca624  cmp     eax, 304h
0x1800ca629  jz      loc_1800CA716
0x1800ca62f  mov     [rsp+0CB0h+ExtCount], rbx; ExtCount
0x1800ca634  lea     r9, [rbp+0BB0h+Dir]; Dir
0x1800ca63b  mov     [rsp+0CB0h+Ext], rbx; Ext
0x1800ca640  lea     r8d, [rbx+4]; DriveCount
0x1800ca644  mov     [rsp+0CB0h+FilenameCount], rbx; FilenameCount
0x1800ca649  lea     rdx, [rsp+0CB0h+Drive]; Drive
0x1800ca64e  mov     esi, 101h
0x1800ca653  mov     [rsp+0CB0h+var_C88], rbx; Filename
0x1800ca658  lea     rcx, [rbp+0BB0h+Filename]; FullPath
0x1800ca65f  mov     [rsp+0CB0h+DirCount], rsi; DirCount
0x1800ca664  call    cs:__imp__wsplitpath_s
0x1800ca66b  nop     dword ptr [rax+rax+00h]
0x1800ca670  test    eax, eax
0x1800ca672  jnz     loc_1800CA716
0x1800ca678  mov     [rsp+0CB0h+ExtCount], rsi; ExtCount
0x1800ca67d  lea     rax, [rsp+0CB0h+var_C50]
0x1800ca682  mov     [rsp+0CB0h+Ext], rax; Ext
0x1800ca687  lea     rcx, ?szADOERRDLLW@@3QBGB; "msader15.dll"
0x1800ca68e  lea     rax, [rbp+0BB0h+var_A40]
0x1800ca695  mov     [rsp+0CB0h+FilenameCount], rsi; FilenameCount
0x1800ca69a  mov     [rsp+0CB0h+var_C88], rax; Filename
0x1800ca69f  xor     r9d, r9d; Dir
0x1800ca6a2  xor     r8d, r8d; DriveCount
0x1800ca6a5  mov     [rsp+0CB0h+DirCount], rbx; DirCount
0x1800ca6aa  xor     edx, edx; Drive
0x1800ca6ac  call    cs:__imp__wsplitpath_s
0x1800ca6b3  nop     dword ptr [rax+rax+00h]
0x1800ca6b8  test    eax, eax
0x1800ca6ba  jnz     short loc_1800CA716
0x1800ca6bc  lea     rax, [rsp+0CB0h+var_C50]
0x1800ca6c1  mov     edx, 304h; BufferCount
0x1800ca6c6  mov     [rsp+0CB0h+var_C88], rax; Ext
0x1800ca6cb  lea     r9, [rbp+0BB0h+Dir]; Dir
0x1800ca6d2  lea     rax, [rbp+0BB0h+var_A40]
0x1800ca6d9  lea     r8, [rsp+0CB0h+Drive]; Drive
0x1800ca6de  mov     [rsp+0CB0h+DirCount], rax; Filename
0x1800ca6e3  lea     rcx, [rbp+0BB0h+Filename]; Buffer
0x1800ca6ea  call    cs:__imp__wmakepath_s
0x1800ca6f1  nop     dword ptr [rax+rax+00h]
0x1800ca6f6  test    eax, eax
0x1800ca6f8  jnz     short loc_1800CA716
0x1800ca6fa  xor     edx, edx; hFile
0x1800ca6fc  lea     r8d, [rbx+60h]; dwFlags
0x1800ca700  lea     rcx, [rbp+0BB0h+Filename]; lpLibFileName
0x1800ca707  call    cs:__imp_LoadLibraryExW
0x1800ca70e  nop     dword ptr [rax+rax+00h]
0x1800ca713  mov     rbx, rax
0x1800ca716  mov     rax, rbx
0x1800ca719  mov     rcx, [rbp+0BB0h+var_10]
0x1800ca720  xor     rcx, rsp; StackCookie
0x1800ca723  call    __security_check_cookie
0x1800ca728  lea     r11, [rsp+0CB0h+var_s0]
0x1800ca730  mov     rbx, [r11+18h]
0x1800ca734  mov     rsi, [r11+20h]
0x1800ca738  mov     rsp, r11
0x1800ca73b  pop     rbp
0x1800ca73c  retn
```
