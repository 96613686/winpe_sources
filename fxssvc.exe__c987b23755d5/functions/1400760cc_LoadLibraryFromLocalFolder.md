# LoadLibraryFromLocalFolder

- ea: `0x1400760cc`
- end: `0x140076329`
- name: `LoadLibraryFromLocalFolder`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140075fb4`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x1400760cc`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14007617d`
- `KERNEL32!GetModuleFileNameW` at `0x14007617d`
- `KERNEL32!GetLastError` at `0x1400761c5`
- `KERNEL32!GetLastError` at `0x1400762e0`
- `KERNEL32!GetLastError` at `0x1400761c5`
- `KERNEL32!GetLastError` at `0x1400762e0`
- `KERNEL32!LoadLibraryW` at `0x1400762bf`
- `KERNEL32!LoadLibraryW` at `0x1400762bf`
- `KERNEL32!SetLastError` at `0x14007619d`
- `KERNEL32!SetLastError` at `0x14007619d`
- `msvcrt!_wsplitpath_s` at `0x140076210`
- `msvcrt!_wsplitpath_s` at `0x140076210`

## string_xrefs

- `0x140076255`: `FXSRESM.DLL`

## pseudocode

```c
HMODULE LoadLibraryFromLocalFolder()
{
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  CMapDeviceId *v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  HMODULE result; // rax
  char v6; // al
  wchar_t Drive[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v8; // [rsp+54h] [rbp-ACh]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR LibFileName[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Dir[264]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(LibFileName, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  *(_DWORD *)Drive = 0;
  v8 = 0;
  memset_0(Dir, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids);
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
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
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v2 = WPP_GLOBAL_Control;
    v3 = 14;
    goto LABEL_18;
  }
  Filename[259] = 0;
  LastError = _wsplitpath_s(Filename, Drive, 3u, Dir, 0x104u, 0, 0, 0, 0);
  if ( LastError )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v3 = 15;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids, LastError);
    return 0;
  }
  v4 = StringCchPrintfW(LibFileName, 0x104u, L"%s%s%s", Drive, Dir, L"FXSRESM.DLL");
  if ( v4 >= 0 )
  {
    result = LoadLibraryW(LibFileName);
    if ( result )
      return result;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
        (unsigned int)LibFileName,
        v6);
    }
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids, (unsigned int)v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1400760cc  push    rbp
0x1400760ce  push    rbx
0x1400760cf  push    rsi
0x1400760d0  push    r14
0x1400760d2  push    r15
0x1400760d4  lea     rbp, [rsp-5A0h]
0x1400760dc  sub     rsp, 6A0h
0x1400760e3  mov     rax, cs:__security_cookie
0x1400760ea  xor     rax, rsp
0x1400760ed  mov     [rbp+5C0h+var_30], rax
0x1400760f4  mov     ebx, 208h
0x1400760f9  lea     rcx, [rbp+5C0h+LibFileName]; void *
0x140076100  mov     r8d, ebx; Size
0x140076103  xor     edx, edx; Val
0x140076105  call    memset_0
0x14007610a  mov     r8d, ebx; Size
0x14007610d  lea     rcx, [rsp+6C0h+Filename]; void *
0x140076112  xor     edx, edx; Val
0x140076114  call    memset_0
0x140076119  xor     eax, eax
0x14007611b  lea     rcx, [rbp+5C0h+Dir]; void *
0x140076122  mov     r8d, ebx; Size
0x140076125  mov     dword ptr [rsp+6C0h+Drive], eax
0x140076129  xor     edx, edx; Val
0x14007612b  mov     [rsp+6C0h+var_66C], ax
0x140076130  call    memset_0
0x140076135  mov     rcx, cs:WPP_GLOBAL_Control
0x14007613c  lea     rsi, WPP_GLOBAL_Control
0x140076143  lea     r14, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x14007614a  mov     bl, 2
0x14007614c  cmp     rcx, rsi
0x14007614f  jz      short loc_14007616D
0x140076151  test    [rcx+1Ch], bl
0x140076154  jz      short loc_14007616D
0x140076156  cmp     byte ptr [rcx+19h], 5
0x14007615a  jb      short loc_14007616D
0x14007615c  mov     rcx, [rcx+10h]
0x140076160  mov     edx, 0Dh
0x140076165  mov     r8, r14
0x140076168  call    WPP_SF_
0x14007616d  mov     r15d, 104h
0x140076173  lea     rdx, [rsp+6C0h+Filename]; lpFilename
0x140076178  mov     r8d, r15d; nSize
0x14007617b  xor     ecx, ecx; hModule
0x14007617d  call    cs:__imp_GetModuleFileNameW
0x140076183  test    eax, eax
0x140076185  jnz     short loc_14007618E
0x140076187  mov     [rsp+6C0h+Filename], ax
0x14007618c  jmp     short loc_1400761A3
0x14007618e  cmp     eax, r15d
0x140076191  jnz     short loc_1400761D9
0x140076193  xor     eax, eax
0x140076195  mov     [rsp+6C0h+Filename], ax
0x14007619a  lea     ecx, [rax+7Ah]; dwErrCode
0x14007619d  call    cs:__imp_SetLastError
0x1400761a3  mov     rax, cs:WPP_GLOBAL_Control
0x1400761aa  cmp     rax, rsi
0x1400761ad  jz      loc_140076309
0x1400761b3  test    [rax+1Ch], bl
0x1400761b6  jz      loc_140076309
0x1400761bc  cmp     [rax+19h], bl
0x1400761bf  jb      loc_140076309
0x1400761c5  call    cs:__imp_GetLastError
0x1400761cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400761d2  mov     edx, 0Eh
0x1400761d7  jmp     short loc_140076241
0x1400761d9  xor     eax, eax
0x1400761db  mov     [rbp+5C0h+var_45A], ax
0x1400761e2  mov     [rsp+6C0h+ExtCount], rax; ExtCount
0x1400761e7  lea     r9, [rbp+5C0h+Dir]; Dir
0x1400761ee  mov     [rsp+6C0h+Ext], rax; Ext
0x1400761f3  lea     r8d, [rax+3]; DriveCount
0x1400761f7  mov     [rsp+6C0h+FilenameCount], rax; FilenameCount
0x1400761fc  lea     rdx, [rsp+6C0h+Drive]; Drive
0x140076201  mov     [rsp+6C0h+var_698], rax; Filename
0x140076206  lea     rcx, [rsp+6C0h+Filename]; FullPath
0x14007620b  mov     [rsp+6C0h+DirCount], r15; DirCount
0x140076210  call    cs:__imp__wsplitpath_s
0x140076216  test    eax, eax
0x140076218  jz      short loc_140076255
0x14007621a  mov     rcx, cs:WPP_GLOBAL_Control
0x140076221  cmp     rcx, rsi
0x140076224  jz      loc_140076309
0x14007622a  test    [rcx+1Ch], bl
0x14007622d  jz      loc_140076309
0x140076233  cmp     [rcx+19h], bl
0x140076236  jb      loc_140076309
0x14007623c  mov     edx, 0Fh
0x140076241  mov     rcx, [rcx+10h]
0x140076245  mov     r8, r14
0x140076248  mov     r9d, eax
0x14007624b  call    WPP_SF_d
0x140076250  jmp     loc_140076309
0x140076255  lea     rax, aFxsresmDll; "FXSRESM.DLL"
0x14007625c  mov     rdx, r15; unsigned __int64
0x14007625f  mov     [rsp+6C0h+var_698], rax
0x140076264  lea     r9, [rsp+6C0h+Drive]
0x140076269  lea     rax, [rbp+5C0h+Dir]
0x140076270  lea     r8, aSSS; "%s%s%s"
0x140076277  mov     [rsp+6C0h+DirCount], rax
0x14007627c  lea     rcx, [rbp+5C0h+LibFileName]; unsigned __int16 *
0x140076283  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140076288  test    eax, eax
0x14007628a  jns     short loc_1400762B8
0x14007628c  mov     rcx, cs:WPP_GLOBAL_Control
0x140076293  cmp     rcx, rsi
0x140076296  jz      short loc_140076309
0x140076298  test    [rcx+1Ch], bl
0x14007629b  jz      short loc_140076309
0x14007629d  cmp     [rcx+19h], bl
0x1400762a0  jb      short loc_140076309
0x1400762a2  mov     rcx, [rcx+10h]
0x1400762a6  mov     edx, 10h
0x1400762ab  mov     r9d, eax
0x1400762ae  mov     r8, r14
0x1400762b1  call    WPP_SF_d
0x1400762b6  jmp     short loc_140076309
0x1400762b8  lea     rcx, [rbp+5C0h+LibFileName]; lpLibFileName
0x1400762bf  call    cs:__imp_LoadLibraryW
0x1400762c5  test    rax, rax
0x1400762c8  jnz     short loc_14007630B
0x1400762ca  mov     rax, cs:WPP_GLOBAL_Control
0x1400762d1  cmp     rax, rsi
0x1400762d4  jz      short loc_140076309
0x1400762d6  test    [rax+1Ch], bl
0x1400762d9  jz      short loc_140076309
0x1400762db  cmp     [rax+19h], bl
0x1400762de  jb      short loc_140076309
0x1400762e0  call    cs:__imp_GetLastError
0x1400762e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400762ed  lea     r9, [rbp+5C0h+LibFileName]
0x1400762f4  mov     edx, 11h
0x1400762f9  mov     dword ptr [rsp+6C0h+DirCount], eax
0x1400762fd  mov     r8, r14
0x140076300  mov     rcx, [rcx+10h]
0x140076304  call    WPP_SF_Sd
0x140076309  xor     eax, eax
0x14007630b  mov     rcx, [rbp+5C0h+var_30]
0x140076312  xor     rcx, rsp; StackCookie
0x140076315  call    __security_check_cookie
0x14007631a  add     rsp, 6A0h
0x140076321  pop     r15
0x140076323  pop     r14
0x140076325  pop     rsi
0x140076326  pop     rbx
0x140076327  pop     rbp
0x140076328  retn
```
