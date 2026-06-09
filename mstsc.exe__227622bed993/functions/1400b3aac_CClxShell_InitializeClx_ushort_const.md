# CClxShell::InitializeClx(ushort const *)

- ea: `0x1400b3aac`
- end: `0x1400b3e68`
- name: `?InitializeClx@CClxShell@@AEAAJPEBG@Z`
- size: `956`
- prototype: `__int64 __fastcall(CClxShell *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1400b3390`

## callees

- `0x140004703`
- `0x140008940`
- `0x140008a34`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14009d824`
- `0x1400b3aac`
- `0x1400b3e70`
- `0x1400b43d0`
- `0x140107998`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400b3d3a`
- `KERNEL32!WideCharToMultiByte` at `0x1400b3d3a`
- `KERNEL32!LoadLibraryW` at `0x1400b3c0d`
- `KERNEL32!LoadLibraryW` at `0x1400b3c0d`
- `KERNEL32!GetLastError` at `0x1400b3d44`
- `KERNEL32!GetLastError` at `0x1400b3d44`

## string_xrefs

- `0x1400b3b9c`: `ClxDllPath`
- `0x1400b3c51`: `Init() Error loading CLx DLL.`

## pseudocode

```c
__int64 __fastcall CClxShell::InitializeClx(CClxShell *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int ActivityIdPrefix; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  HMODULE LibraryW; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  signed int LastError; // edi
  __int64 v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  void (__fastcall *v25)(_QWORD, _QWORD); // rax
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B0h]
  CHAR MultiByteStr[272]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR LibFileName[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR WideCharStr[264]; // [rsp+380h] [rbp+280h] BYREF

  v27 = 0;
  v28 = 0;
  memset_0(LibFileName, 0, 0x208u);
  memset_0(WideCharStr, 0, 0x208u);
  memset_0(MultiByteStr, 0, 0x104u);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v4, v5);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids,
        ActivityIdPrefix,
        (__int64)"Cookie");
    }
    v7 = -2147467261;
    goto LABEL_39;
  }
  CUT::UT_ReadRegistryStringCb(&pszPassword, L"ClxDllPath", &pszPassword, LibFileName, 520, 1);
  if ( !LibFileName[0] )
  {
    v7 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8, v9);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids, v10);
    }
    goto LABEL_39;
  }
  LibraryW = LoadLibraryW(LibFileName);
  *((_QWORD *)this + 6) = LibraryW;
  if ( !LibraryW )
  {
    v7 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v12, v13);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids,
        v14,
        (__int64)"Init() Error loading CLx DLL.",
        5);
    }
    goto LABEL_39;
  }
  if ( !(unsigned int)CClxShell::LoadProcs(this) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v17 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15, v16);
    v18 = 36;
LABEL_37:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids,
      v17,
      -2147467259);
LABEL_38:
    v7 = -2147467259;
LABEL_39:
    CClxShell::Terminate((CClxShell *)((char *)this + 8));
    return v7;
  }
  *(_QWORD *)&v27 = 0x200000020LL;
  StringCchCopyW(WideCharStr, 0x104u, L"cookie=");
  StringCchCatW(WideCharStr, 0x104u, a2);
  if ( !WideCharToMultiByte(0, 0x400u, WideCharStr, -1, MultiByteStr, 260, 0, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v19, v21);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids,
        v22,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v7 = LastError;
    goto LABEL_39;
  }
  *(_QWORD *)&v28 = MultiByteStr;
  if ( !(*((unsigned int (__fastcall **)(__int128 *, char *))this + 8))(&v27, (char *)this + 56) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v17 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v23, v24);
    v18 = 38;
    goto LABEL_37;
  }
  v25 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 9);
  if ( v25 )
    v25(*((_QWORD *)this + 7), 0);
  return 0;
}

```

## disassembly

```asm
0x1400b3aac  mov     [rsp-8+arg_10], rbx
0x1400b3ab1  mov     [rsp-8+arg_18], rsi
0x1400b3ab6  push    rbp
0x1400b3ab7  push    rdi
0x1400b3ab8  push    r14
0x1400b3aba  lea     rbp, [rsp-4A0h]
0x1400b3ac2  sub     rsp, 5A0h
0x1400b3ac9  mov     rax, cs:__security_cookie
0x1400b3ad0  xor     rax, rsp
0x1400b3ad3  mov     [rbp+4B0h+var_20], rax
0x1400b3ada  xorps   xmm0, xmm0
0x1400b3add  mov     rbx, rdx
0x1400b3ae0  mov     rsi, rcx
0x1400b3ae3  mov     edi, 208h
0x1400b3ae8  mov     r8d, edi; Size
0x1400b3aeb  lea     rcx, [rbp+4B0h+LibFileName]; void *
0x1400b3aef  xor     edx, edx; Val
0x1400b3af1  movups  [rsp+5B0h+var_570], xmm0
0x1400b3af6  movups  [rsp+5B0h+var_560], xmm0
0x1400b3afb  call    memset_0
0x1400b3b00  mov     r8d, edi; Size
0x1400b3b03  lea     rcx, [rbp+4B0h+WideCharStr]; void *
0x1400b3b0a  xor     edx, edx; Val
0x1400b3b0c  call    memset_0
0x1400b3b11  mov     r14d, 104h
0x1400b3b17  lea     rcx, [rsp+5B0h+MultiByteStr]; void *
0x1400b3b1c  mov     r8d, r14d; Size
0x1400b3b1f  xor     edx, edx; Val
0x1400b3b21  call    memset_0
0x1400b3b26  test    rbx, rbx
0x1400b3b29  jnz     short loc_1400B3B82
0x1400b3b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3b32  lea     rax, WPP_GLOBAL_Control
0x1400b3b39  cmp     rcx, rax
0x1400b3b3c  jz      short loc_1400B3B78
0x1400b3b3e  test    byte ptr [rcx+1Ch], 8
0x1400b3b42  jz      short loc_1400B3B78
0x1400b3b44  cmp     byte ptr [rcx+19h], 2
0x1400b3b48  jb      short loc_1400B3B78
0x1400b3b4a  call    RdpX_GetActivityIdPrefix
0x1400b3b4f  lea     rcx, aCookie_0; "Cookie"
0x1400b3b56  mov     r9d, eax
0x1400b3b59  mov     [rsp+5B0h+lpMultiByteStr], rcx
0x1400b3b5e  lea     edx, [rbx+21h]
0x1400b3b61  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3b68  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b3b6f  mov     rcx, [rcx+10h]
0x1400b3b73  call    WPP_SF_Ds
0x1400b3b78  mov     ebx, 80004003h
0x1400b3b7d  jmp     loc_1400B3E1E
0x1400b3b82  lea     rcx, pszPassword
0x1400b3b89  mov     [rsp+5B0h+cbMultiByte], 1
0x1400b3b91  mov     r8, rcx
0x1400b3b94  mov     dword ptr [rsp+5B0h+lpMultiByteStr], edi
0x1400b3b98  lea     r9, [rbp+4B0h+LibFileName]
0x1400b3b9c  lea     rdx, aClxdllpath; "ClxDllPath"
0x1400b3ba3  call    ?UT_ReadRegistryStringCb@CUT@@SAXPEBG00PEAGHW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryStringCb(ushort const *,ushort const *,ushort const *,ushort *,int,UT_REGREAD_LOCATION)
0x1400b3ba8  xor     eax, eax
0x1400b3baa  cmp     ax, [rbp+4B0h+LibFileName]
0x1400b3bae  jnz     short loc_1400B3C09
0x1400b3bb0  mov     ebx, 80004005h
0x1400b3bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3bbc  lea     rax, WPP_GLOBAL_Control
0x1400b3bc3  cmp     rcx, rax
0x1400b3bc6  jz      loc_1400B3E1E
0x1400b3bcc  test    byte ptr [rcx+1Ch], 1
0x1400b3bd0  jz      loc_1400B3E1E
0x1400b3bd6  cmp     byte ptr [rcx+19h], 4
0x1400b3bda  jb      loc_1400B3E1E
0x1400b3be0  call    RdpX_GetActivityIdPrefix
0x1400b3be5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3bec  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b3bf3  mov     edx, 22h ; '"'
0x1400b3bf8  mov     r9d, eax
0x1400b3bfb  mov     rcx, [rcx+10h]
0x1400b3bff  call    WPP_SF_d
0x1400b3c04  jmp     loc_1400B3E1E
0x1400b3c09  lea     rcx, [rbp+4B0h+LibFileName]; lpLibFileName
0x1400b3c0d  call    cs:__imp_LoadLibraryW
0x1400b3c13  mov     [rsi+30h], rax
0x1400b3c17  test    rax, rax
0x1400b3c1a  jnz     short loc_1400B3C89
0x1400b3c1c  mov     ebx, 80004005h
0x1400b3c21  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c28  lea     rax, WPP_GLOBAL_Control
0x1400b3c2f  cmp     rcx, rax
0x1400b3c32  jz      loc_1400B3E1E
0x1400b3c38  test    byte ptr [rcx+1Ch], 8
0x1400b3c3c  jz      loc_1400B3E1E
0x1400b3c42  cmp     byte ptr [rcx+19h], 2
0x1400b3c46  jb      loc_1400B3E1E
0x1400b3c4c  call    RdpX_GetActivityIdPrefix
0x1400b3c51  lea     rcx, aInitErrorLoadi; "Init() Error loading CLx DLL."
0x1400b3c58  mov     [rsp+5B0h+cbMultiByte], 80004005h
0x1400b3c60  mov     [rsp+5B0h+lpMultiByteStr], rcx
0x1400b3c65  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b3c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c73  mov     edx, 23h ; '#'
0x1400b3c78  mov     r9d, eax
0x1400b3c7b  mov     rcx, [rcx+10h]
0x1400b3c7f  call    WPP_SF_DsD
0x1400b3c84  jmp     loc_1400B3E1E
0x1400b3c89  mov     rcx, rsi; this
0x1400b3c8c  call    ?LoadProcs@CClxShell@@QEAAHXZ; CClxShell::LoadProcs(void)
0x1400b3c91  test    eax, eax
0x1400b3c93  jnz     short loc_1400B3CCF
0x1400b3c95  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c9c  lea     rax, WPP_GLOBAL_Control
0x1400b3ca3  cmp     rcx, rax
0x1400b3ca6  jz      loc_1400B3E19
0x1400b3cac  test    byte ptr [rcx+1Ch], 8
0x1400b3cb0  jz      loc_1400B3E19
0x1400b3cb6  cmp     byte ptr [rcx+19h], 2
0x1400b3cba  jb      loc_1400B3E19
0x1400b3cc0  call    RdpX_GetActivityIdPrefix
0x1400b3cc5  mov     edx, 24h ; '$'
0x1400b3cca  jmp     loc_1400B3DF7
0x1400b3ccf  lea     r8, aCookie; "cookie="
0x1400b3cd6  mov     dword ptr [rsp+5B0h+var_570], 20h ; ' '
0x1400b3cde  mov     rdx, r14; unsigned __int64
0x1400b3ce1  mov     dword ptr [rsp+5B0h+var_570+4], 2
0x1400b3ce9  lea     rcx, [rbp+4B0h+WideCharStr]; unsigned __int16 *
0x1400b3cf0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400b3cf5  mov     r8, rbx; unsigned __int16 *
0x1400b3cf8  lea     rcx, [rbp+4B0h+WideCharStr]; unsigned __int16 *
0x1400b3cff  mov     rdx, r14; unsigned __int64
0x1400b3d02  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400b3d07  mov     [rsp+5B0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400b3d10  lea     rax, [rsp+5B0h+MultiByteStr]
0x1400b3d15  mov     [rsp+5B0h+lpDefaultChar], 0; lpDefaultChar
0x1400b3d1e  lea     r8, [rbp+4B0h+WideCharStr]; lpWideCharStr
0x1400b3d25  mov     [rsp+5B0h+cbMultiByte], r14d; cbMultiByte
0x1400b3d2a  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400b3d2e  mov     edx, 400h; dwFlags
0x1400b3d33  mov     [rsp+5B0h+lpMultiByteStr], rax; lpMultiByteStr
0x1400b3d38  xor     ecx, ecx; CodePage
0x1400b3d3a  call    cs:__imp_WideCharToMultiByte
0x1400b3d40  test    eax, eax
0x1400b3d42  jnz     short loc_1400B3DAE
0x1400b3d44  call    cs:__imp_GetLastError
0x1400b3d4a  mov     edi, eax
0x1400b3d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3d53  lea     rax, WPP_GLOBAL_Control
0x1400b3d5a  cmp     rcx, rax
0x1400b3d5d  jz      short loc_1400B3D93
0x1400b3d5f  test    byte ptr [rcx+1Ch], 8
0x1400b3d63  jz      short loc_1400B3D93
0x1400b3d65  cmp     byte ptr [rcx+19h], 2
0x1400b3d69  jb      short loc_1400B3D93
0x1400b3d6b  call    RdpX_GetActivityIdPrefix
0x1400b3d70  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3d77  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b3d7e  mov     edx, 25h ; '%'
0x1400b3d83  mov     dword ptr [rsp+5B0h+lpMultiByteStr], edi
0x1400b3d87  mov     r9d, eax
0x1400b3d8a  mov     rcx, [rcx+10h]
0x1400b3d8e  call    WPP_SF_Dd
0x1400b3d93  test    edi, edi
0x1400b3d95  jle     short loc_1400B3DA0
0x1400b3d97  movzx   edi, di
0x1400b3d9a  or      edi, 80070000h
0x1400b3da0  mov     ebx, 80004005h
0x1400b3da5  test    edi, edi
0x1400b3da7  cmovns  edi, ebx
0x1400b3daa  mov     ebx, edi
0x1400b3dac  jmp     short loc_1400B3E1E
0x1400b3dae  lea     rax, [rsp+5B0h+MultiByteStr]
0x1400b3db3  mov     qword ptr [rsp+5B0h+var_560], rax
0x1400b3db8  lea     rdx, [rsi+38h]
0x1400b3dbc  mov     rax, [rsi+40h]
0x1400b3dc0  lea     rcx, [rsp+5B0h+var_570]
0x1400b3dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b3dca  test    eax, eax
0x1400b3dcc  jnz     short loc_1400B3E29
0x1400b3dce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3dd5  lea     rax, WPP_GLOBAL_Control
0x1400b3ddc  cmp     rcx, rax
0x1400b3ddf  jz      short loc_1400B3E19
0x1400b3de1  test    byte ptr [rcx+1Ch], 8
0x1400b3de5  jz      short loc_1400B3E19
0x1400b3de7  cmp     byte ptr [rcx+19h], 2
0x1400b3deb  jb      short loc_1400B3E19
0x1400b3ded  call    RdpX_GetActivityIdPrefix
0x1400b3df2  mov     edx, 26h ; '&'
0x1400b3df7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3dfe  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b3e05  mov     r9d, eax
0x1400b3e08  mov     dword ptr [rsp+5B0h+lpMultiByteStr], 80004005h
0x1400b3e10  mov     rcx, [rcx+10h]
0x1400b3e14  call    WPP_SF_Dd
0x1400b3e19  mov     ebx, 80004005h
0x1400b3e1e  lea     rcx, [rsi+8]; this
0x1400b3e22  call    ?Terminate@CClxShell@@UEAAJXZ; CClxShell::Terminate(void)
0x1400b3e27  jmp     short loc_1400B3E3F
0x1400b3e29  mov     rax, [rsi+48h]
0x1400b3e2d  test    rax, rax
0x1400b3e30  jz      short loc_1400B3E3D
0x1400b3e32  mov     rcx, [rsi+38h]
0x1400b3e36  xor     edx, edx
0x1400b3e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b3e3d  xor     ebx, ebx
0x1400b3e3f  mov     eax, ebx
0x1400b3e41  mov     rcx, [rbp+4B0h+var_20]
0x1400b3e48  xor     rcx, rsp; StackCookie
0x1400b3e4b  call    __security_check_cookie
0x1400b3e50  lea     r11, [rsp+5B0h+var_10]
0x1400b3e58  mov     rbx, [r11+30h]
0x1400b3e5c  mov     rsi, [r11+38h]
0x1400b3e60  mov     rsp, r11
0x1400b3e63  pop     r14
0x1400b3e65  pop     rdi
0x1400b3e66  pop     rbp
0x1400b3e67  retn
```
