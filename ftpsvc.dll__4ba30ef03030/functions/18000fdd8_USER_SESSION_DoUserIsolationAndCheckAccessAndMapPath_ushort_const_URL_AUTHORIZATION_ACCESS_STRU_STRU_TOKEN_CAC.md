# USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)

- ea: `0x18000fdd8`
- end: `0x18001019a`
- name: `?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z`
- size: `962`
- prototype: `__int64 __fastcall(_QWORD *, __int64, int, const wchar_t **, STRU *, _QWORD *, int)`
- caller_count: `10`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ed00`
- `0x18000f370`
- `0x18000f560`
- `0x18000f7a0`
- `0x18000f930`
- `0x1800101a0`
- `0x180010370`
- `0x1800113d0`
- `0x1800123a0`
- `0x180012c90`

## callees

- `0x18000e5cc`
- `0x18000fdd8`
- `0x180011c38`
- `0x180014288`
- `0x18001ff3c`
- `0x18002ac94`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180010020`
- `msvcrt!_wcsnicmp` at `0x180010020`
- `msvcrt!wcschr` at `0x18000ffd5`
- `msvcrt!wcschr` at `0x18000ffd5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000fe96`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010100`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000fe96`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010100`
- `iisutil!PuDbgPrint` at `0x18000ff7d`
- `iisutil!PuDbgPrint` at `0x180010086`
- `iisutil!PuDbgPrint` at `0x1800100de`
- `iisutil!PuDbgPrint` at `0x18000ff7d`
- `iisutil!PuDbgPrint` at `0x180010086`
- `iisutil!PuDbgPrint` at `0x1800100de`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000fe56`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000fe7d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000fe56`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000fe7d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000febc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000febc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001015d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010168`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001015d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010168`

## string_xrefs

- `0x18000ff62`: `USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath`
- `0x18001006b`: `USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath`
- `0x1800100c3`: `USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath`
- `0x18001005f`: `Denied access due to the failure to check for the short file name\n`
- `0x1800100b7`: `Denied access due to the use of the short file name\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(
        _QWORD *a1,
        __int64 a2,
        int a3,
        const wchar_t **a4,
        STRU *a5,
        _QWORD *a6,
        int a7)
{
  int Metadata; // ebx
  __int64 v11; // rax
  const unsigned __int16 *v12; // rcx
  _DWORD *v13; // r12
  const wchar_t *v14; // rax
  TOKEN_CACHE_ENTRY *v15; // rcx
  void *ImpersonationToken; // rbx
  const wchar_t *v17; // rax
  __int64 v18; // rcx
  struct FTP_METADATA *v19; // rcx
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  struct FTP_METADATA *v22; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v23; // [rsp+50h] [rbp-B0h]
  _BYTE v24[32]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v28[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v21 = a3;
  v23 = a6;
  v22 = 0;
  memset_0(v27, 0, 0x208u);
  STRU::STRU((STRU *)v26, v27, 0x104u);
  memset_0(v28, 0, 0x208u);
  STRU::STRU((STRU *)v24, v28, 0x104u);
  if ( *((_DWORD *)a1 + 3) == 3 )
  {
    Metadata = STRU::Copy((STRU *)v24, (const unsigned __int16 *)a1[40]);
    if ( Metadata < 0 )
      goto LABEL_35;
    if ( *(_WORD *)a2 != 47 || *(_WORD *)(a2 + 2) )
    {
      Metadata = STRU::Append((STRU *)v24, (const unsigned __int16 *)a2);
      if ( Metadata < 0 )
        goto LABEL_35;
    }
    a2 = v25;
  }
  v11 = a1[2];
  v12 = (const unsigned __int16 *)&dword_18004D454;
  if ( *(_QWORD *)(v11 + 8) )
    v12 = *(const unsigned __int16 **)(v11 + 8);
  v13 = a1 + 139;
  Metadata = FTP_METADATA::GetMetadata(
               v12,
               (const unsigned __int16 *)a2,
               (const struct _GUID *)(a1 + 159),
               (unsigned int *)a1 + 278,
               (const unsigned __int16 **)a1 + 138,
               (struct STRU *)(a1 + 131),
               &v22);
  if ( Metadata < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v14 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 208LL))(a1);
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        347,
        "USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath",
        "GetMetadata(%S) failed. Error = 0x%x. Info = %S\n",
        (const wchar_t *)a2,
        Metadata,
        v14);
    }
    goto LABEL_35;
  }
  if ( !a7 )
  {
    Metadata = USER_SESSION::CheckAccess(a1, a2, v22, (unsigned int)v21);
    if ( Metadata < 0 )
      goto LABEL_35;
  }
  Metadata = USER_SESSION::MapPath((USER_SESSION *)a1, (const unsigned __int16 *)a2, v22, (struct STRU *)a4);
  if ( Metadata < 0 )
    goto LABEL_35;
  if ( !wcschr(a4[4], 0x7Eu) )
    goto LABEL_31;
  v21 = 0;
  v15 = (TOKEN_CACHE_ENTRY *)*((_QWORD *)v22 + 116);
  if ( !v15 )
  {
    ImpersonationToken = 0;
    goto LABEL_20;
  }
  ImpersonationToken = TOKEN_CACHE_ENTRY::QueryImpersonationToken(v15);
  if ( !ImpersonationToken )
  {
LABEL_20:
    if ( !_wcsnicmp(a4[4], L"\\\\?\\UNC\\", 8u) )
      ImpersonationToken = (void *)(*(__int64 (__fastcall **)(_QWORD *))(a1[3] + 56LL))(a1 + 3);
  }
  Metadata = CheckIfShortFileName((wchar_t *)a4[4], ImpersonationToken, &v21);
  if ( Metadata < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        409,
        "USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath",
        "Denied access due to the failure to check for the short file name\r\n");
    *v13 = 6;
    v17 = L"Short file name check has failed.";
LABEL_26:
    a1[138] = v17;
    goto LABEL_35;
  }
  if ( v21 )
  {
    Metadata = -2147024891;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        424,
        "USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath",
        "Denied access due to the use of the short file name\r\n");
    *v13 = 7;
    v17 = L"Short file names are forbidden.";
    goto LABEL_26;
  }
LABEL_31:
  if ( a5 )
    STRU::Copy(a5, (const unsigned __int16 *)a2);
  v18 = *((_QWORD *)v22 + 116);
  *v23 = v18;
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 20));
LABEL_35:
  v19 = v22;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 3, 0xFFFFFFFF) == 1 && v19 )
      (**(void (__fastcall ***)(struct FTP_METADATA *, __int64))v19)(v19, 1);
    v22 = 0;
  }
  STRU::~STRU(v24);
  STRU::~STRU(v26);
  return (unsigned int)Metadata;
}

```

## disassembly

```asm
0x18000fdd8  mov     [rsp-8+arg_10], rbx
0x18000fddd  push    rbp
0x18000fdde  push    rsi
0x18000fddf  push    rdi
0x18000fde0  push    r12
0x18000fde2  push    r13
0x18000fde4  push    r14
0x18000fde6  push    r15
0x18000fde8  lea     rbp, [rsp-400h]
0x18000fdf0  sub     rsp, 500h
0x18000fdf7  mov     rax, cs:__security_cookie
0x18000fdfe  xor     rax, rsp
0x18000fe01  mov     [rbp+430h+var_40], rax
0x18000fe08  mov     r14, r9
0x18000fe0b  mov     [rsp+530h+var_4F0], r8d
0x18000fe10  mov     rdi, rdx
0x18000fe13  mov     rsi, rcx
0x18000fe16  mov     r13, [rbp+430h+arg_20]
0x18000fe1d  mov     rax, [rbp+430h+arg_28]
0x18000fe24  mov     [rsp+530h+var_4E0], rax
0x18000fe29  mov     [rsp+530h+var_4E8], 0
0x18000fe32  mov     r15d, 208h
0x18000fe38  mov     r8d, r15d; Size
0x18000fe3b  xor     edx, edx; Val
0x18000fe3d  lea     rcx, [rbp+430h+var_460]; void *
0x18000fe41  call    memset_0
0x18000fe46  mov     ebx, 104h
0x18000fe4b  mov     r8d, ebx
0x18000fe4e  lea     rdx, [rbp+430h+var_460]
0x18000fe52  lea     rcx, [rbp+430h+var_4A0]
0x18000fe56  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000fe5c  nop
0x18000fe5d  mov     r8d, r15d; Size
0x18000fe60  xor     edx, edx; Val
0x18000fe62  lea     rcx, [rbp+430h+var_250]; void *
0x18000fe69  call    memset_0
0x18000fe6e  mov     r8d, ebx
0x18000fe71  lea     rdx, [rbp+430h+var_250]
0x18000fe78  lea     rcx, [rsp+530h+var_4D8]
0x18000fe7d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000fe83  nop
0x18000fe84  cmp     dword ptr [rsi+0Ch], 3
0x18000fe88  jnz     short loc_18000FED1
0x18000fe8a  mov     rdx, [rsi+140h]
0x18000fe91  lea     rcx, [rsp+530h+var_4D8]
0x18000fe96  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000fe9c  mov     ebx, eax
0x18000fe9e  xor     ecx, ecx
0x18000fea0  test    eax, eax
0x18000fea2  js      loc_180010123
0x18000fea8  cmp     word ptr [rdi], 2Fh ; '/'
0x18000feac  jnz     short loc_18000FEB4
0x18000feae  cmp     [rdi+2], cx
0x18000feb2  jz      short loc_18000FECC
0x18000feb4  mov     rdx, rdi
0x18000feb7  lea     rcx, [rsp+530h+var_4D8]
0x18000febc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000fec2  mov     ebx, eax
0x18000fec4  test    eax, eax
0x18000fec6  js      loc_180010123
0x18000fecc  mov     rdi, [rsp+530h+var_4B8]
0x18000fed1  mov     rax, [rsi+10h]
0x18000fed5  lea     rcx, dword_18004D454
0x18000fedc  cmp     qword ptr [rax+8], 0
0x18000fee1  cmovnz  rcx, [rax+8]; unsigned __int16 *
0x18000fee6  lea     r15, [rsi+450h]
0x18000feed  lea     r12, [rsi+458h]
0x18000fef4  lea     rax, [rsi+418h]
0x18000fefb  lea     r8, [rsi+4F8h]; struct _GUID *
0x18000ff02  lea     rdx, [rsp+530h+var_4E8]
0x18000ff07  mov     [rsp+530h+var_500], rdx; struct FTP_METADATA **
0x18000ff0c  mov     [rsp+530h+var_508], rax; struct STRU *
0x18000ff11  mov     [rsp+530h+var_510], r15; unsigned __int16 **
0x18000ff16  mov     r9, r12; unsigned int *
0x18000ff19  mov     rdx, rdi; unsigned __int16 *
0x18000ff1c  call    ?GetMetadata@FTP_METADATA@@SAJPEBG0PEBU_GUID@@PEAKPEAPEBGPEAVSTRU@@PEAPEAV1@@Z; FTP_METADATA::GetMetadata(ushort const *,ushort const *,_GUID const *,ulong *,ushort const * *,STRU *,FTP_METADATA * *)
0x18000ff21  mov     ebx, eax
0x18000ff23  xor     ecx, ecx
0x18000ff25  test    eax, eax
0x18000ff27  jns     short loc_18000FF88
0x18000ff29  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ff30  jz      loc_180010123
0x18000ff36  mov     rax, [rsi]
0x18000ff39  mov     rcx, rsi
0x18000ff3c  mov     rax, [rax+0D0h]
0x18000ff43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff48  mov     [rsp+530h+var_4F8], rax
0x18000ff4d  mov     dword ptr [rsp+530h+var_500], ebx
0x18000ff51  mov     [rsp+530h+var_508], rdi
0x18000ff56  lea     rax, aGetmetadataSFa; "GetMetadata(%S) failed. Error = 0x%x. I"...
0x18000ff5d  mov     [rsp+530h+var_510], rax
0x18000ff62  lea     r9, aUserSessionDou; "USER_SESSION::DoUserIsolationAndCheckAc"...
0x18000ff69  mov     r8d, 15Bh
0x18000ff6f  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000ff76  mov     rcx, cs:g_pDebug
0x18000ff7d  call    cs:__imp_PuDbgPrint
0x18000ff83  jmp     loc_180010123
0x18000ff88  cmp     [rbp+430h+arg_30], ecx
0x18000ff8e  jnz     short loc_18000FFAF
0x18000ff90  mov     r9d, [rsp+530h+var_4F0]
0x18000ff95  mov     r8, [rsp+530h+var_4E8]
0x18000ff9a  mov     rdx, rdi
0x18000ff9d  mov     rcx, rsi
0x18000ffa0  call    ?CheckAccess@USER_SESSION@@AEAAJPEBGPEAVFTP_METADATA@@W4URL_AUTHORIZATION_ACCESS@@@Z; USER_SESSION::CheckAccess(ushort const *,FTP_METADATA *,URL_AUTHORIZATION_ACCESS)
0x18000ffa5  mov     ebx, eax
0x18000ffa7  test    eax, eax
0x18000ffa9  js      loc_180010123
0x18000ffaf  mov     r9, r14; struct STRU *
0x18000ffb2  mov     r8, [rsp+530h+var_4E8]; struct FTP_METADATA *
0x18000ffb7  mov     rdx, rdi; unsigned __int16 *
0x18000ffba  mov     rcx, rsi; this
0x18000ffbd  call    ?MapPath@USER_SESSION@@AEAAJPEBGPEAVFTP_METADATA@@PEAVSTRU@@@Z; USER_SESSION::MapPath(ushort const *,FTP_METADATA *,STRU *)
0x18000ffc2  mov     ebx, eax
0x18000ffc4  test    eax, eax
0x18000ffc6  js      loc_180010123
0x18000ffcc  mov     edx, 7Eh ; '~'; Ch
0x18000ffd1  mov     rcx, [r14+20h]; Str
0x18000ffd5  call    cs:__imp_wcschr
0x18000ffdb  xor     ecx, ecx
0x18000ffdd  test    rax, rax
0x18000ffe0  jz      loc_1800100F5
0x18000ffe6  mov     [rsp+530h+var_4F0], ecx
0x18000ffea  mov     rax, [rsp+530h+var_4E8]
0x18000ffef  mov     rcx, [rax+3A0h]; this
0x18000fff6  xor     eax, eax
0x18000fff8  test    rcx, rcx
0x18000fffb  jz      short loc_18001000C
0x18000fffd  call    ?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)
0x180010002  mov     rbx, rax
0x180010005  test    rax, rax
0x180010008  jnz     short loc_18001003D
0x18001000a  jmp     short loc_18001000F
0x18001000c  mov     rbx, rax
0x18001000f  mov     r8d, 8; MaxCount
0x180010015  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x18001001c  mov     rcx, [r14+20h]; String1
0x180010020  call    cs:__imp__wcsnicmp
0x180010026  test    eax, eax
0x180010028  jnz     short loc_18001003D
0x18001002a  lea     rcx, [rsi+18h]
0x18001002e  mov     rax, [rcx]
0x180010031  mov     rax, [rax+38h]
0x180010035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001003a  mov     rbx, rax
0x18001003d  lea     r8, [rsp+530h+var_4F0]; int *
0x180010042  mov     rdx, rbx; Token
0x180010045  mov     rcx, [r14+20h]; Str
0x180010049  call    ?CheckIfShortFileName@@YAJPEBGPEAXPEAH@Z; CheckIfShortFileName(ushort const *,void *,int *)
0x18001004e  mov     ebx, eax
0x180010050  xor     ecx, ecx
0x180010052  test    eax, eax
0x180010054  jns     short loc_1800100A3
0x180010056  test    byte ptr cs:g_dwDebugFlags, 3
0x18001005d  jz      short loc_18001008C
0x18001005f  lea     rax, aDeniedAccessDu; "Denied access due to the failure to che"...
0x180010066  mov     [rsp+530h+var_510], rax
0x18001006b  lea     r9, aUserSessionDou; "USER_SESSION::DoUserIsolationAndCheckAc"...
0x180010072  mov     r8d, 199h
0x180010078  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001007f  mov     rcx, cs:g_pDebug
0x180010086  call    cs:__imp_PuDbgPrint
0x18001008c  mov     dword ptr [r12], 6
0x180010094  lea     rax, aShortFileNameC; "Short file name check has failed."
0x18001009b  mov     [r15], rax
0x18001009e  jmp     loc_180010123
0x1800100a3  cmp     [rsp+530h+var_4F0], ecx
0x1800100a7  jz      short loc_1800100F5
0x1800100a9  mov     ebx, 80070005h
0x1800100ae  test    byte ptr cs:g_dwDebugFlags, 3
0x1800100b5  jz      short loc_1800100E4
0x1800100b7  lea     rax, aDeniedAccessDu_0; "Denied access due to the use of the sho"...
0x1800100be  mov     [rsp+530h+var_510], rax
0x1800100c3  lea     r9, aUserSessionDou; "USER_SESSION::DoUserIsolationAndCheckAc"...
0x1800100ca  mov     r8d, 1A8h
0x1800100d0  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800100d7  mov     rcx, cs:g_pDebug
0x1800100de  call    cs:__imp_PuDbgPrint
0x1800100e4  mov     dword ptr [r12], 7
0x1800100ec  lea     rax, aShortFileNames; "Short file names are forbidden."
0x1800100f3  jmp     short loc_18001009B
0x1800100f5  test    r13, r13
0x1800100f8  jz      short loc_180010106
0x1800100fa  mov     rdx, rdi
0x1800100fd  mov     rcx, r13
0x180010100  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010106  mov     rax, [rsp+530h+var_4E8]
0x18001010b  mov     rcx, [rax+3A0h]
0x180010112  mov     rax, [rsp+530h+var_4E0]
0x180010117  mov     [rax], rcx
0x18001011a  test    rcx, rcx
0x18001011d  jz      short loc_180010123
0x18001011f  lock inc dword ptr [rcx+14h]
0x180010123  mov     rcx, [rsp+530h+var_4E8]
0x180010128  test    rcx, rcx
0x18001012b  jz      short loc_180010158
0x18001012d  or      eax, 0FFFFFFFFh
0x180010130  lock xadd [rcx+0Ch], eax
0x180010135  cmp     eax, 1
0x180010138  jnz     short loc_18001014F
0x18001013a  test    rcx, rcx
0x18001013d  jz      short loc_18001014F
0x18001013f  mov     rax, [rcx]
0x180010142  mov     edx, 1
0x180010147  mov     rax, [rax]
0x18001014a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001014f  mov     [rsp+530h+var_4E8], 0
0x180010158  lea     rcx, [rsp+530h+var_4D8]
0x18001015d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010163  nop
0x180010164  lea     rcx, [rbp+430h+var_4A0]
0x180010168  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001016e  mov     eax, ebx
0x180010170  mov     rcx, [rbp+430h+var_40]
0x180010177  xor     rcx, rsp; StackCookie
0x18001017a  call    __security_check_cookie
0x18001017f  mov     rbx, [rsp+530h+arg_10]
0x180010187  add     rsp, 500h
0x18001018e  pop     r15
0x180010190  pop     r14
0x180010192  pop     r13
0x180010194  pop     r12
0x180010196  pop     rdi
0x180010197  pop     rsi
0x180010198  pop     rbp
0x180010199  retn
```
