# LoadLibraryPD

- ea: `0x180013c7c`
- end: `0x180013dac`
- name: `LoadLibraryPD`
- size: `304`
- prototype: `HMODULE __fastcall(LPCWSTR lpLibFileName, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002f80`
- `0x180007394`
- `0x18000d0f0`
- `0x18000ea9c`

## callees

- `0x180013c7c`
- `0x180013f00`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x180013cf3`
- `msvcrt!_wsplitpath_s` at `0x180013cf3`
- `msvcrt!_snwprintf_s` at `0x180013d5b`
- `msvcrt!_snwprintf_s` at `0x180013d5b`
- `KERNEL32!LoadLibraryExW` at `0x180013d6e`
- `KERNEL32!LoadLibraryExW` at `0x180013d81`
- `KERNEL32!LoadLibraryExW` at `0x180013d6e`
- `KERNEL32!LoadLibraryExW` at `0x180013d81`

## pseudocode

```c
HMODULE __fastcall LoadLibraryPD(LPCWSTR lpLibFileName, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v5; // ebx
  HMODULE result; // rax
  wchar_t Drive[8]; // [rsp+50h] [rbp-838h] BYREF
  wchar_t Filename[256]; // [rsp+60h] [rbp-828h] BYREF
  wchar_t Dir[256]; // [rsp+260h] [rbp-628h] BYREF
  wchar_t Ext[256]; // [rsp+460h] [rbp-428h] BYREF
  wchar_t Buffer[264]; // [rsp+660h] [rbp-228h] BYREF

  v5 = a3;
  PrivateDriverRootInitialized(hinst, a2, a3, a4);
  if ( _wsplitpath_s(lpLibFileName, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u) )
    return LoadLibraryExW(lpLibFileName, 0, v5);
  if ( Drive[0] )
    return LoadLibraryExW(lpLibFileName, 0, v5);
  if ( Dir[0] )
    return LoadLibraryExW(lpLibFileName, 0, v5);
  if ( !Filename[0] )
    return LoadLibraryExW(lpLibFileName, 0, v5);
  if ( !PrivateDriverRootInitialized )
    return LoadLibraryExW(lpLibFileName, 0, v5);
  _snwprintf_s(Buffer, 0x104u, 0xFFFFFFFFFFFFFFFFuLL, L"%ls\\%ls%ls", &szODBCDriverModuleRoot, Filename, Ext);
  result = LoadLibraryExW(Buffer, 0, v5);
  if ( !result )
    return LoadLibraryExW(lpLibFileName, 0, v5);
  return result;
}

```

## disassembly

```asm
0x180013c7c  mov     [rsp+arg_8], rbx
0x180013c81  mov     [rsp+arg_18], rsi
0x180013c86  push    rdi
0x180013c87  sub     rsp, 880h
0x180013c8e  mov     rax, cs:__security_cookie
0x180013c95  xor     rax, rsp
0x180013c98  mov     [rsp+888h+var_18], rax
0x180013ca0  mov     rdi, rcx
0x180013ca3  mov     ebx, r8d
0x180013ca6  mov     rcx, cs:hinst
0x180013cad  call    PrivateDriverRootInitialized
0x180013cb2  mov     ecx, 100h
0x180013cb7  lea     rax, [rsp+888h+var_428]
0x180013cbf  mov     [rsp+888h+ExtCount], rcx; ExtCount
0x180013cc4  lea     r9, [rsp+888h+Dir]; Dir
0x180013ccc  mov     [rsp+888h+Ext], rax; Ext
0x180013cd1  lea     rdx, [rsp+888h+Drive]; Drive
0x180013cd6  mov     [rsp+888h+FilenameCount], rcx; FilenameCount
0x180013cdb  lea     rax, [rsp+888h+var_828]
0x180013ce0  mov     [rsp+888h+Filename], rax; Filename
0x180013ce5  mov     r8d, 3; DriveCount
0x180013ceb  mov     [rsp+888h+DirCount], rcx; DirCount
0x180013cf0  mov     rcx, rdi; FullPath
0x180013cf3  call    cs:__imp__wsplitpath_s
0x180013cf9  xor     esi, esi
0x180013cfb  test    eax, eax
0x180013cfd  jnz     short loc_180013D79
0x180013cff  cmp     [rsp+888h+Drive], si
0x180013d04  jnz     short loc_180013D79
0x180013d06  cmp     [rsp+888h+Dir], si
0x180013d0e  jnz     short loc_180013D79
0x180013d10  cmp     [rsp+888h+var_828], si
0x180013d15  jz      short loc_180013D79
0x180013d17  cmp     cs:_PrivateDriverRootInitialized, sil
0x180013d1e  jz      short loc_180013D79
0x180013d20  lea     rax, [rsp+888h+var_428]
0x180013d28  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180013d2c  mov     [rsp+888h+FilenameCount], rax
0x180013d31  lea     r9, aLsLsLs; "%ls\\%ls%ls"
0x180013d38  lea     rax, [rsp+888h+var_828]
0x180013d3d  mov     edx, 104h; BufferCount
0x180013d42  mov     [rsp+888h+Filename], rax
0x180013d47  lea     rcx, [rsp+888h+Buffer]; Buffer
0x180013d4f  lea     rax, szODBCDriverModuleRoot
0x180013d56  mov     [rsp+888h+DirCount], rax
0x180013d5b  call    cs:__imp__snwprintf_s
0x180013d61  mov     r8d, ebx; dwFlags
0x180013d64  lea     rcx, [rsp+888h+Buffer]; lpLibFileName
0x180013d6c  xor     edx, edx; hFile
0x180013d6e  call    cs:__imp_LoadLibraryExW
0x180013d74  test    rax, rax
0x180013d77  jnz     short loc_180013D87
0x180013d79  mov     r8d, ebx; dwFlags
0x180013d7c  xor     edx, edx; hFile
0x180013d7e  mov     rcx, rdi; lpLibFileName
0x180013d81  call    cs:__imp_LoadLibraryExW
0x180013d87  mov     rcx, [rsp+888h+var_18]
0x180013d8f  xor     rcx, rsp; StackCookie
0x180013d92  call    __security_check_cookie
0x180013d97  lea     r11, [rsp+888h+var_8]
0x180013d9f  mov     rbx, [r11+18h]
0x180013da3  mov     rsi, [r11+28h]
0x180013da7  mov     rsp, r11
0x180013daa  pop     rdi
0x180013dab  retn
```
