# LoadLibraryFromLocalFolder

- ea: `0x18000f3e4`
- end: `0x18000f653`
- name: `LoadLibraryFromLocalFolder`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000f2c4`

## callees

- `0x180005168`
- `0x180005eac`
- `0x180005ed4`
- `0x18000d6bc`
- `0x18000f3e4`
- `0x180015cbe`
- `0x180015cf0`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x18000f533`
- `msvcrt!_wsplitpath_s` at `0x18000f533`
- `KERNEL32!SetLastError` at `0x18000f4be`
- `KERNEL32!SetLastError` at `0x18000f4be`
- `KERNEL32!GetLastError` at `0x18000f4e8`
- `KERNEL32!GetLastError` at `0x18000f609`
- `KERNEL32!GetLastError` at `0x18000f4e8`
- `KERNEL32!GetLastError` at `0x18000f609`
- `KERNEL32!GetModuleFileNameW` at `0x18000f49c`
- `KERNEL32!GetModuleFileNameW` at `0x18000f49c`
- `KERNEL32!LoadLibraryW` at `0x18000f5e6`
- `KERNEL32!LoadLibraryW` at `0x18000f5e6`

## string_xrefs

- `0x18000f57a`: `FXSRESM.DLL`

## pseudocode

```c
HMODULE __fastcall LoadLibraryFromLocalFolder(__int64 a1, HMODULE a2)
{
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  HMODULE result; // rax
  char v9; // al
  wchar_t Drive[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v11; // [rsp+54h] [rbp-ACh]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR LibFileName[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Dir[264]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(LibFileName, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  *(_DWORD *)Drive = 0;
  v11 = 0;
  memset_0(Dir, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids);
  }
  ModuleFileNameW = GetModuleFileNameW(a2, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Filename[0] = 0;
    goto LABEL_9;
  }
  if ( ModuleFileNameW == 260 )
  {
    Filename[0] = 0;
    SetLastError(0x7Au);
LABEL_9:
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    v6 = 14;
    goto LABEL_18;
  }
  Filename[259] = 0;
  LastError = _wsplitpath_s(Filename, Drive, 3u, Dir, 0x104u, 0, 0, 0, 0);
  if ( LastError )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = 15;
LABEL_18:
    WPP_SF_d(v5[2], v6, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids, LastError);
    return 0;
  }
  v7 = StringCchPrintfW(LibFileName, 0x104u, L"%s%s%s", Drive, Dir, L"FXSRESM.DLL");
  if ( v7 >= 0 )
  {
    result = LoadLibraryW(LibFileName);
    if ( result )
      return result;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
        (unsigned int)LibFileName,
        v9);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids, (unsigned int)v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f3e4  push    rbp
0x18000f3e6  push    rbx
0x18000f3e7  push    rsi
0x18000f3e8  push    rdi
0x18000f3e9  push    r14
0x18000f3eb  push    r15
0x18000f3ed  lea     rbp, [rsp-5A8h]
0x18000f3f5  sub     rsp, 6A8h
0x18000f3fc  mov     rax, cs:__security_cookie
0x18000f403  xor     rax, rsp
0x18000f406  mov     [rbp+5D0h+var_40], rax
0x18000f40d  mov     rbx, rdx
0x18000f410  lea     rcx, [rbp+5D0h+LibFileName]; void *
0x18000f417  mov     edi, 208h
0x18000f41c  xor     edx, edx; Val
0x18000f41e  mov     r8d, edi; Size
0x18000f421  call    memset_0
0x18000f426  mov     r8d, edi; Size
0x18000f429  lea     rcx, [rsp+6D0h+Filename]; void *
0x18000f42e  xor     edx, edx; Val
0x18000f430  call    memset_0
0x18000f435  xor     eax, eax
0x18000f437  lea     rcx, [rbp+5D0h+Dir]; void *
0x18000f43e  mov     r8d, edi; Size
0x18000f441  mov     dword ptr [rsp+6D0h+Drive], eax
0x18000f445  xor     edx, edx; Val
0x18000f447  mov     [rsp+6D0h+var_67C], ax
0x18000f44c  call    memset_0
0x18000f451  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f458  lea     rsi, WPP_GLOBAL_Control
0x18000f45f  lea     r14, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x18000f466  mov     dil, 2
0x18000f469  cmp     rcx, rsi
0x18000f46c  jz      short loc_18000F48B
0x18000f46e  test    [rcx+1Ch], dil
0x18000f472  jz      short loc_18000F48B
0x18000f474  cmp     byte ptr [rcx+19h], 5
0x18000f478  jb      short loc_18000F48B
0x18000f47a  mov     rcx, [rcx+10h]
0x18000f47e  mov     edx, 0Dh
0x18000f483  mov     r8, r14
0x18000f486  call    WPP_SF_
0x18000f48b  mov     r15d, 104h
0x18000f491  lea     rdx, [rsp+6D0h+Filename]; lpFilename
0x18000f496  mov     r8d, r15d; nSize
0x18000f499  mov     rcx, rbx; hModule
0x18000f49c  call    cs:__imp_GetModuleFileNameW
0x18000f4a2  xor     ebx, ebx
0x18000f4a4  test    eax, eax
0x18000f4a6  jnz     short loc_18000F4AF
0x18000f4a8  mov     [rsp+6D0h+Filename], bx
0x18000f4ad  jmp     short loc_18000F4C4
0x18000f4af  cmp     eax, r15d
0x18000f4b2  jnz     short loc_18000F4FC
0x18000f4b4  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000f4b9  mov     [rsp+6D0h+Filename], bx
0x18000f4be  call    cs:__imp_SetLastError
0x18000f4c4  mov     rax, cs:WPP_GLOBAL_Control
0x18000f4cb  cmp     rax, rsi
0x18000f4ce  jz      loc_18000F632
0x18000f4d4  test    [rax+1Ch], dil
0x18000f4d8  jz      loc_18000F632
0x18000f4de  cmp     [rax+19h], dil
0x18000f4e2  jb      loc_18000F632
0x18000f4e8  call    cs:__imp_GetLastError
0x18000f4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4f5  mov     edx, 0Eh
0x18000f4fa  jmp     short loc_18000F566
0x18000f4fc  mov     [rbp+5D0h+var_46A], bx
0x18000f503  mov     [rsp+6D0h+ExtCount], rbx; ExtCount
0x18000f508  lea     r9, [rbp+5D0h+Dir]; Dir
0x18000f50f  mov     [rsp+6D0h+Ext], rbx; Ext
0x18000f514  lea     rdx, [rsp+6D0h+Drive]; Drive
0x18000f519  mov     [rsp+6D0h+FilenameCount], rbx; FilenameCount
0x18000f51e  lea     rcx, [rsp+6D0h+Filename]; FullPath
0x18000f523  mov     [rsp+6D0h+var_6A8], rbx; Filename
0x18000f528  mov     r8d, 3; DriveCount
0x18000f52e  mov     [rsp+6D0h+DirCount], r15; DirCount
0x18000f533  call    cs:__imp__wsplitpath_s
0x18000f539  test    eax, eax
0x18000f53b  jz      short loc_18000F57A
0x18000f53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f544  cmp     rcx, rsi
0x18000f547  jz      loc_18000F632
0x18000f54d  test    [rcx+1Ch], dil
0x18000f551  jz      loc_18000F632
0x18000f557  cmp     [rcx+19h], dil
0x18000f55b  jb      loc_18000F632
0x18000f561  mov     edx, 0Fh
0x18000f566  mov     rcx, [rcx+10h]
0x18000f56a  mov     r8, r14
0x18000f56d  mov     r9d, eax
0x18000f570  call    WPP_SF_d
0x18000f575  jmp     loc_18000F632
0x18000f57a  lea     rax, aFxsresmDll; "FXSRESM.DLL"
0x18000f581  mov     rdx, r15; unsigned __int64
0x18000f584  mov     [rsp+6D0h+var_6A8], rax
0x18000f589  lea     r9, [rsp+6D0h+Drive]
0x18000f58e  lea     rax, [rbp+5D0h+Dir]
0x18000f595  lea     r8, aSSS; "%s%s%s"
0x18000f59c  mov     [rsp+6D0h+DirCount], rax
0x18000f5a1  lea     rcx, [rbp+5D0h+LibFileName]; unsigned __int16 *
0x18000f5a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f5ad  test    eax, eax
0x18000f5af  jns     short loc_18000F5DF
0x18000f5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5b8  cmp     rcx, rsi
0x18000f5bb  jz      short loc_18000F632
0x18000f5bd  test    [rcx+1Ch], dil
0x18000f5c1  jz      short loc_18000F632
0x18000f5c3  cmp     [rcx+19h], dil
0x18000f5c7  jb      short loc_18000F632
0x18000f5c9  mov     rcx, [rcx+10h]
0x18000f5cd  mov     edx, 10h
0x18000f5d2  mov     r9d, eax
0x18000f5d5  mov     r8, r14
0x18000f5d8  call    WPP_SF_d
0x18000f5dd  jmp     short loc_18000F632
0x18000f5df  lea     rcx, [rbp+5D0h+LibFileName]; lpLibFileName
0x18000f5e6  call    cs:__imp_LoadLibraryW
0x18000f5ec  test    rax, rax
0x18000f5ef  jnz     short loc_18000F634
0x18000f5f1  mov     rax, cs:WPP_GLOBAL_Control
0x18000f5f8  cmp     rax, rsi
0x18000f5fb  jz      short loc_18000F632
0x18000f5fd  test    [rax+1Ch], dil
0x18000f601  jz      short loc_18000F632
0x18000f603  cmp     [rax+19h], dil
0x18000f607  jb      short loc_18000F632
0x18000f609  call    cs:__imp_GetLastError
0x18000f60f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f616  lea     r9, [rbp+5D0h+LibFileName]
0x18000f61d  mov     edx, 11h
0x18000f622  mov     dword ptr [rsp+6D0h+DirCount], eax
0x18000f626  mov     r8, r14
0x18000f629  mov     rcx, [rcx+10h]
0x18000f62d  call    WPP_SF_Sd
0x18000f632  xor     eax, eax
0x18000f634  mov     rcx, [rbp+5D0h+var_40]
0x18000f63b  xor     rcx, rsp; StackCookie
0x18000f63e  call    __security_check_cookie
0x18000f643  add     rsp, 6A8h
0x18000f64a  pop     r15
0x18000f64c  pop     r14
0x18000f64e  pop     rdi
0x18000f64f  pop     rsi
0x18000f650  pop     rbx
0x18000f651  pop     rbp
0x18000f652  retn
```
