# CClxShell::InitializeClx(ushort const *)

- ea: `0x1400b5c1c`
- end: `0x1400b5fd8`
- name: `?InitializeClx@CClxShell@@AEAAJPEBG@Z`
- size: `956`
- prototype: `__int64 __fastcall(CClxShell *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1400b5500`

## callees

- `0x140004703`
- `0x140008940`
- `0x140008a34`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14009f994`
- `0x1400b5c1c`
- `0x1400b5fe0`
- `0x1400b6540`
- `0x140109b08`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400b5eaa`
- `KERNEL32!WideCharToMultiByte` at `0x1400b5eaa`
- `KERNEL32!LoadLibraryW` at `0x1400b5d7d`
- `KERNEL32!LoadLibraryW` at `0x1400b5d7d`
- `KERNEL32!GetLastError` at `0x1400b5eb4`
- `KERNEL32!GetLastError` at `0x1400b5eb4`

## string_xrefs

- `0x1400b5dc1`: `Init() Error loading CLx DLL.`
- `0x1400b5d0c`: `ClxDllPath`

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
0x1400b5c1c  mov     [rsp-8+arg_10], rbx
0x1400b5c21  mov     [rsp-8+arg_18], rsi
0x1400b5c26  push    rbp
0x1400b5c27  push    rdi
0x1400b5c28  push    r14
0x1400b5c2a  lea     rbp, [rsp-4A0h]
0x1400b5c32  sub     rsp, 5A0h
0x1400b5c39  mov     rax, cs:__security_cookie
0x1400b5c40  xor     rax, rsp
0x1400b5c43  mov     [rbp+4B0h+var_20], rax
0x1400b5c4a  xorps   xmm0, xmm0
0x1400b5c4d  mov     rbx, rdx
0x1400b5c50  mov     rsi, rcx
0x1400b5c53  mov     edi, 208h
0x1400b5c58  mov     r8d, edi; Size
0x1400b5c5b  lea     rcx, [rbp+4B0h+LibFileName]; void *
0x1400b5c5f  xor     edx, edx; Val
0x1400b5c61  movups  [rsp+5B0h+var_570], xmm0
0x1400b5c66  movups  [rsp+5B0h+var_560], xmm0
0x1400b5c6b  call    memset_0
0x1400b5c70  mov     r8d, edi; Size
0x1400b5c73  lea     rcx, [rbp+4B0h+WideCharStr]; void *
0x1400b5c7a  xor     edx, edx; Val
0x1400b5c7c  call    memset_0
0x1400b5c81  mov     r14d, 104h
0x1400b5c87  lea     rcx, [rsp+5B0h+MultiByteStr]; void *
0x1400b5c8c  mov     r8d, r14d; Size
0x1400b5c8f  xor     edx, edx; Val
0x1400b5c91  call    memset_0
0x1400b5c96  test    rbx, rbx
0x1400b5c99  jnz     short loc_1400B5CF2
0x1400b5c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5ca2  lea     rax, WPP_GLOBAL_Control
0x1400b5ca9  cmp     rcx, rax
0x1400b5cac  jz      short loc_1400B5CE8
0x1400b5cae  test    byte ptr [rcx+1Ch], 8
0x1400b5cb2  jz      short loc_1400B5CE8
0x1400b5cb4  cmp     byte ptr [rcx+19h], 2
0x1400b5cb8  jb      short loc_1400B5CE8
0x1400b5cba  call    RdpX_GetActivityIdPrefix
0x1400b5cbf  lea     rcx, aCookie_0; "Cookie"
0x1400b5cc6  mov     r9d, eax
0x1400b5cc9  mov     [rsp+5B0h+lpMultiByteStr], rcx
0x1400b5cce  lea     edx, [rbx+21h]
0x1400b5cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5cd8  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b5cdf  mov     rcx, [rcx+10h]
0x1400b5ce3  call    WPP_SF_Ds
0x1400b5ce8  mov     ebx, 80004003h
0x1400b5ced  jmp     loc_1400B5F8E
0x1400b5cf2  lea     rcx, pszPassword
0x1400b5cf9  mov     [rsp+5B0h+cbMultiByte], 1
0x1400b5d01  mov     r8, rcx
0x1400b5d04  mov     dword ptr [rsp+5B0h+lpMultiByteStr], edi
0x1400b5d08  lea     r9, [rbp+4B0h+LibFileName]
0x1400b5d0c  lea     rdx, aClxdllpath; "ClxDllPath"
0x1400b5d13  call    ?UT_ReadRegistryStringCb@CUT@@SAXPEBG00PEAGHW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryStringCb(ushort const *,ushort const *,ushort const *,ushort *,int,UT_REGREAD_LOCATION)
0x1400b5d18  xor     eax, eax
0x1400b5d1a  cmp     ax, [rbp+4B0h+LibFileName]
0x1400b5d1e  jnz     short loc_1400B5D79
0x1400b5d20  mov     ebx, 80004005h
0x1400b5d25  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5d2c  lea     rax, WPP_GLOBAL_Control
0x1400b5d33  cmp     rcx, rax
0x1400b5d36  jz      loc_1400B5F8E
0x1400b5d3c  test    byte ptr [rcx+1Ch], 1
0x1400b5d40  jz      loc_1400B5F8E
0x1400b5d46  cmp     byte ptr [rcx+19h], 4
0x1400b5d4a  jb      loc_1400B5F8E
0x1400b5d50  call    RdpX_GetActivityIdPrefix
0x1400b5d55  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5d5c  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b5d63  mov     edx, 22h ; '"'
0x1400b5d68  mov     r9d, eax
0x1400b5d6b  mov     rcx, [rcx+10h]
0x1400b5d6f  call    WPP_SF_d
0x1400b5d74  jmp     loc_1400B5F8E
0x1400b5d79  lea     rcx, [rbp+4B0h+LibFileName]; lpLibFileName
0x1400b5d7d  call    cs:__imp_LoadLibraryW
0x1400b5d83  mov     [rsi+30h], rax
0x1400b5d87  test    rax, rax
0x1400b5d8a  jnz     short loc_1400B5DF9
0x1400b5d8c  mov     ebx, 80004005h
0x1400b5d91  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5d98  lea     rax, WPP_GLOBAL_Control
0x1400b5d9f  cmp     rcx, rax
0x1400b5da2  jz      loc_1400B5F8E
0x1400b5da8  test    byte ptr [rcx+1Ch], 8
0x1400b5dac  jz      loc_1400B5F8E
0x1400b5db2  cmp     byte ptr [rcx+19h], 2
0x1400b5db6  jb      loc_1400B5F8E
0x1400b5dbc  call    RdpX_GetActivityIdPrefix
0x1400b5dc1  lea     rcx, aInitErrorLoadi; "Init() Error loading CLx DLL."
0x1400b5dc8  mov     [rsp+5B0h+cbMultiByte], 80004005h
0x1400b5dd0  mov     [rsp+5B0h+lpMultiByteStr], rcx
0x1400b5dd5  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b5ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5de3  mov     edx, 23h ; '#'
0x1400b5de8  mov     r9d, eax
0x1400b5deb  mov     rcx, [rcx+10h]
0x1400b5def  call    WPP_SF_DsD
0x1400b5df4  jmp     loc_1400B5F8E
0x1400b5df9  mov     rcx, rsi; this
0x1400b5dfc  call    ?LoadProcs@CClxShell@@QEAAHXZ; CClxShell::LoadProcs(void)
0x1400b5e01  test    eax, eax
0x1400b5e03  jnz     short loc_1400B5E3F
0x1400b5e05  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5e0c  lea     rax, WPP_GLOBAL_Control
0x1400b5e13  cmp     rcx, rax
0x1400b5e16  jz      loc_1400B5F89
0x1400b5e1c  test    byte ptr [rcx+1Ch], 8
0x1400b5e20  jz      loc_1400B5F89
0x1400b5e26  cmp     byte ptr [rcx+19h], 2
0x1400b5e2a  jb      loc_1400B5F89
0x1400b5e30  call    RdpX_GetActivityIdPrefix
0x1400b5e35  mov     edx, 24h ; '$'
0x1400b5e3a  jmp     loc_1400B5F67
0x1400b5e3f  lea     r8, aCookie; "cookie="
0x1400b5e46  mov     dword ptr [rsp+5B0h+var_570], 20h ; ' '
0x1400b5e4e  mov     rdx, r14; unsigned __int64
0x1400b5e51  mov     dword ptr [rsp+5B0h+var_570+4], 2
0x1400b5e59  lea     rcx, [rbp+4B0h+WideCharStr]; unsigned __int16 *
0x1400b5e60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400b5e65  mov     r8, rbx; unsigned __int16 *
0x1400b5e68  lea     rcx, [rbp+4B0h+WideCharStr]; unsigned __int16 *
0x1400b5e6f  mov     rdx, r14; unsigned __int64
0x1400b5e72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400b5e77  mov     [rsp+5B0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400b5e80  lea     rax, [rsp+5B0h+MultiByteStr]
0x1400b5e85  mov     [rsp+5B0h+lpDefaultChar], 0; lpDefaultChar
0x1400b5e8e  lea     r8, [rbp+4B0h+WideCharStr]; lpWideCharStr
0x1400b5e95  mov     [rsp+5B0h+cbMultiByte], r14d; cbMultiByte
0x1400b5e9a  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400b5e9e  mov     edx, 400h; dwFlags
0x1400b5ea3  mov     [rsp+5B0h+lpMultiByteStr], rax; lpMultiByteStr
0x1400b5ea8  xor     ecx, ecx; CodePage
0x1400b5eaa  call    cs:__imp_WideCharToMultiByte
0x1400b5eb0  test    eax, eax
0x1400b5eb2  jnz     short loc_1400B5F1E
0x1400b5eb4  call    cs:__imp_GetLastError
0x1400b5eba  mov     edi, eax
0x1400b5ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5ec3  lea     rax, WPP_GLOBAL_Control
0x1400b5eca  cmp     rcx, rax
0x1400b5ecd  jz      short loc_1400B5F03
0x1400b5ecf  test    byte ptr [rcx+1Ch], 8
0x1400b5ed3  jz      short loc_1400B5F03
0x1400b5ed5  cmp     byte ptr [rcx+19h], 2
0x1400b5ed9  jb      short loc_1400B5F03
0x1400b5edb  call    RdpX_GetActivityIdPrefix
0x1400b5ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5ee7  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b5eee  mov     edx, 25h ; '%'
0x1400b5ef3  mov     dword ptr [rsp+5B0h+lpMultiByteStr], edi
0x1400b5ef7  mov     r9d, eax
0x1400b5efa  mov     rcx, [rcx+10h]
0x1400b5efe  call    WPP_SF_Dd
0x1400b5f03  test    edi, edi
0x1400b5f05  jle     short loc_1400B5F10
0x1400b5f07  movzx   edi, di
0x1400b5f0a  or      edi, 80070000h
0x1400b5f10  mov     ebx, 80004005h
0x1400b5f15  test    edi, edi
0x1400b5f17  cmovns  edi, ebx
0x1400b5f1a  mov     ebx, edi
0x1400b5f1c  jmp     short loc_1400B5F8E
0x1400b5f1e  lea     rax, [rsp+5B0h+MultiByteStr]
0x1400b5f23  mov     qword ptr [rsp+5B0h+var_560], rax
0x1400b5f28  lea     rdx, [rsi+38h]
0x1400b5f2c  mov     rax, [rsi+40h]
0x1400b5f30  lea     rcx, [rsp+5B0h+var_570]
0x1400b5f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b5f3a  test    eax, eax
0x1400b5f3c  jnz     short loc_1400B5F99
0x1400b5f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5f45  lea     rax, WPP_GLOBAL_Control
0x1400b5f4c  cmp     rcx, rax
0x1400b5f4f  jz      short loc_1400B5F89
0x1400b5f51  test    byte ptr [rcx+1Ch], 8
0x1400b5f55  jz      short loc_1400B5F89
0x1400b5f57  cmp     byte ptr [rcx+19h], 2
0x1400b5f5b  jb      short loc_1400B5F89
0x1400b5f5d  call    RdpX_GetActivityIdPrefix
0x1400b5f62  mov     edx, 26h ; '&'
0x1400b5f67  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5f6e  lea     r8, WPP_fb1ffa79ceb43e4f67a7f2c4422588ec_Traceguids
0x1400b5f75  mov     r9d, eax
0x1400b5f78  mov     dword ptr [rsp+5B0h+lpMultiByteStr], 80004005h
0x1400b5f80  mov     rcx, [rcx+10h]
0x1400b5f84  call    WPP_SF_Dd
0x1400b5f89  mov     ebx, 80004005h
0x1400b5f8e  lea     rcx, [rsi+8]; this
0x1400b5f92  call    ?Terminate@CClxShell@@UEAAJXZ; CClxShell::Terminate(void)
0x1400b5f97  jmp     short loc_1400B5FAF
0x1400b5f99  mov     rax, [rsi+48h]
0x1400b5f9d  test    rax, rax
0x1400b5fa0  jz      short loc_1400B5FAD
0x1400b5fa2  mov     rcx, [rsi+38h]
0x1400b5fa6  xor     edx, edx
0x1400b5fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b5fad  xor     ebx, ebx
0x1400b5faf  mov     eax, ebx
0x1400b5fb1  mov     rcx, [rbp+4B0h+var_20]
0x1400b5fb8  xor     rcx, rsp; StackCookie
0x1400b5fbb  call    __security_check_cookie
0x1400b5fc0  lea     r11, [rsp+5B0h+var_10]
0x1400b5fc8  mov     rbx, [r11+30h]
0x1400b5fcc  mov     rsi, [r11+38h]
0x1400b5fd0  mov     rsp, r11
0x1400b5fd3  pop     r14
0x1400b5fd5  pop     rdi
0x1400b5fd6  pop     rbp
0x1400b5fd7  retn
```
