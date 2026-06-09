# LoadDLL(ushort const *)

- ea: `0x180019c4c`
- end: `0x180019daa`
- name: `?LoadDLL@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `350`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18019f264`
- `0x1801a03ec`

## callees

- `0x180019c4c`
- `0x180021340`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019cb3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019d1f`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019cb3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019d1f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180019d7c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180019d7c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180019ce3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180019ce3`

## pseudocode

```c
HINSTANCE __fastcall LoadDLL(const unsigned __int16 *a1)
{
  wchar_t Drive[16]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Dir[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FullPath[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t Ext[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t Filename[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  _wsplitpath_s(a1, Drive, 0xAu, Dir, 0x105u, Filename, 0x105u, Ext, 0x105u);
  if ( Dir[0] )
    return 0;
  if ( Drive[0] )
    return 0;
  if ( !GetModuleFileNameW(g_Globals, FullPath, 0x104u) )
    return 0;
  _wsplitpath_s(FullPath, Drive, 0xAu, Dir, 0x105u, 0, 0, 0, 0);
  if ( !Drive[0] && !Dir[0] )
    return 0;
  swprintf_s(FullPath, 0x105u, L"%s%s%s%s", Drive, Dir, Filename, Ext);
  return LoadLibraryExW(FullPath, 0, 0);
}

```

## disassembly

```asm
0x180019c4c  mov     [rsp-8+arg_8], rbx
0x180019c51  mov     [rsp-8+arg_10], rdi
0x180019c56  push    rbp
0x180019c57  lea     rbp, [rsp-7C0h]
0x180019c5f  sub     rsp, 8C0h
0x180019c66  mov     rax, cs:__security_cookie
0x180019c6d  xor     rax, rsp
0x180019c70  mov     [rbp+7C0h+var_10], rax
0x180019c77  mov     edi, 105h
0x180019c7c  lea     rax, [rbp+7C0h+var_430]
0x180019c83  mov     [rsp+8C0h+ExtCount], rdi; ExtCount
0x180019c88  lea     r9, [rsp+8C0h+Dir]; Dir
0x180019c8d  mov     [rsp+8C0h+Ext], rax; Ext
0x180019c92  lea     rdx, [rsp+8C0h+Drive]; Drive
0x180019c97  lea     rax, [rbp+7C0h+var_220]
0x180019c9e  mov     [rsp+8C0h+FilenameCount], rdi; FilenameCount
0x180019ca3  mov     [rsp+8C0h+Filename], rax; Filename
0x180019ca8  mov     r8d, 0Ah; DriveCount
0x180019cae  mov     [rsp+8C0h+DirCount], rdi; DirCount
0x180019cb3  call    cs:__imp__wsplitpath_s
0x180019cb9  xor     ebx, ebx
0x180019cbb  cmp     [rsp+8C0h+Dir], bx
0x180019cc0  jnz     loc_180019D84
0x180019cc6  cmp     [rsp+8C0h+Drive], bx
0x180019ccb  jnz     loc_180019D84
0x180019cd1  mov     rcx, cs:?g_Globals@@3UGLOBALS@@A; hModule
0x180019cd8  lea     r8d, [rdi-1]; nSize
0x180019cdc  lea     rdx, [rbp+7C0h+FullPath]; lpFilename
0x180019ce3  call    cs:__imp_GetModuleFileNameW
0x180019ce9  test    eax, eax
0x180019ceb  jz      loc_180019D84
0x180019cf1  mov     [rsp+8C0h+ExtCount], rbx; ExtCount
0x180019cf6  lea     r9, [rsp+8C0h+Dir]; Dir
0x180019cfb  mov     [rsp+8C0h+Ext], rbx; Ext
0x180019d00  lea     r8d, [rbx+0Ah]; DriveCount
0x180019d04  mov     [rsp+8C0h+FilenameCount], rbx; FilenameCount
0x180019d09  lea     rdx, [rsp+8C0h+Drive]; Drive
0x180019d0e  mov     [rsp+8C0h+Filename], rbx; Filename
0x180019d13  lea     rcx, [rbp+7C0h+FullPath]; FullPath
0x180019d1a  mov     [rsp+8C0h+DirCount], rdi; DirCount
0x180019d1f  call    cs:__imp__wsplitpath_s
0x180019d25  cmp     [rsp+8C0h+Drive], bx
0x180019d2a  jnz     short loc_180019D33
0x180019d2c  cmp     [rsp+8C0h+Dir], bx
0x180019d31  jz      short loc_180019D84
0x180019d33  lea     rax, [rbp+7C0h+var_430]
0x180019d3a  mov     rdx, rdi; BufferCount
0x180019d3d  mov     [rsp+8C0h+FilenameCount], rax
0x180019d42  lea     r9, [rsp+8C0h+Drive]
0x180019d47  lea     rax, [rbp+7C0h+var_220]
0x180019d4e  mov     [rsp+8C0h+Filename], rax
0x180019d53  lea     r8, aSSSS_0; "%s%s%s%s"
0x180019d5a  lea     rax, [rsp+8C0h+Dir]
0x180019d5f  lea     rcx, [rbp+7C0h+FullPath]; Buffer
0x180019d66  mov     [rsp+8C0h+DirCount], rax
0x180019d6b  call    swprintf_s
0x180019d70  xor     r8d, r8d; dwFlags
0x180019d73  lea     rcx, [rbp+7C0h+FullPath]; lpLibFileName
0x180019d7a  xor     edx, edx; hFile
0x180019d7c  call    cs:__imp_LoadLibraryExW
0x180019d82  jmp     short loc_180019D86
0x180019d84  xor     eax, eax
0x180019d86  mov     rcx, [rbp+7C0h+var_10]
0x180019d8d  xor     rcx, rsp; StackCookie
0x180019d90  call    __security_check_cookie
0x180019d95  lea     r11, [rsp+8C0h+var_s0]
0x180019d9d  mov     rbx, [r11+18h]
0x180019da1  mov     rdi, [r11+20h]
0x180019da5  mov     rsp, r11
0x180019da8  pop     rbp
0x180019da9  retn
```
