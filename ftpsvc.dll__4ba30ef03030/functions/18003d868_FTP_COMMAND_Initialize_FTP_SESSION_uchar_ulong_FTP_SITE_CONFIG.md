# FTP_COMMAND::Initialize(FTP_SESSION *,uchar *,ulong,FTP_SITE_CONFIG *)

- ea: `0x18003d868`
- end: `0x18003dba5`
- name: `?Initialize@FTP_COMMAND@@QEAAJPEAVFTP_SESSION@@PEAEKPEAVFTP_SITE_CONFIG@@@Z`
- size: `829`
- prototype: `int __fastcall(FTP_COMMAND *this, struct FTP_SESSION *, const char *, unsigned int, struct FTP_SITE_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003553c`

## callees

- `0x18002b998`
- `0x18003d868`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003da13`
- `msvcrt!_wcsicmp` at `0x18003dab9`
- `msvcrt!_wcsicmp` at `0x18003da13`
- `msvcrt!_wcsicmp` at `0x18003dab9`
- `KERNEL32!GetTickCount` at `0x18003d89b`
- `KERNEL32!GetTickCount` at `0x18003d89b`
- `iisutil!PuDbgPrint` at `0x18003da86`
- `iisutil!PuDbgPrint` at `0x18003db22`
- `iisutil!PuDbgPrint` at `0x18003da86`
- `iisutil!PuDbgPrint` at `0x18003db22`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18003d914`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18003d9c2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18003db48`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18003d914`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18003d9c2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18003db48`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18003d9fd`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18003daa2`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18003d9fd`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18003daa2`

## string_xrefs

- `0x18003da7f`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x18003db1b`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x18003da61`: `Found denied command '%S'.\n`
- `0x18003da6d`: `COMMAND_FILTERING_CONFIG_ELEMENT::CheckForAllowedCommand`
- `0x18003db09`: `COMMAND_FILTERING_CONFIG_ELEMENT::CheckForAllowedCommand`
- `0x18003dafd`: `Command '%S' is not specifically allowed and will be rejected.\n`

## pseudocode

```c
int __fastcall FTP_COMMAND::Initialize(
        FTP_COMMAND *this,
        struct FTP_SESSION *a2,
        const char *a3,
        unsigned int a4,
        struct FTP_SITE_CONFIG *a5)
{
  unsigned int v6; // esi
  unsigned int v9; // ebp
  DWORD TickCount; // eax
  _BYTE *v11; // rax
  _WORD *v12; // rcx
  _BYTE *v13; // rax
  int result; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  int v17; // r13d
  unsigned int v18; // ebp
  const wchar_t *v19; // r14
  const unsigned __int16 *v20; // rsi
  __int64 v21; // rax
  const unsigned __int16 *v22; // rsi
  __int64 v23; // rax
  bool v24; // zf
  _BYTE *v25; // rax

  v6 = a4;
  v9 = *((_DWORD *)a5 + 263);
  *((_QWORD *)this + 104) = a4;
  TickCount = GetTickCount();
  *((_QWORD *)this + 132) = a2;
  *((_DWORD *)this + 270) = TickCount;
  if ( v6 > v9 )
  {
    v6 = v9;
    *((_DWORD *)this + 266) = 1;
  }
  if ( !v6 )
  {
    **((_WORD **)this + 43) = 0;
    v11 = (_BYTE *)*((_QWORD *)this + 20);
    *((_DWORD *)this + 90) = 0;
    *v11 = 0;
    v12 = (_WORD *)*((_QWORD *)this + 13);
    *((_DWORD *)this + 44) = 0;
    *v12 = 0;
    v13 = (_BYTE *)*((_QWORD *)this + 6);
    *((_DWORD *)this + 30) = 0;
    *v13 = 0;
    *((_DWORD *)this + 16) = 0;
LABEL_5:
    result = 0;
LABEL_11:
    *((_DWORD *)this + 293) = result;
    return 0;
  }
  if ( v6 > 2 )
  {
    v15 = 0;
    while ( 1 )
    {
      v16 = v15 + 1;
      if ( a3[v15] == 13 && a3[v16] == 10 )
        break;
      ++v15;
      if ( (unsigned int)v16 >= v6 )
      {
        if ( *((_DWORD *)this + 266) )
        {
          v15 = v6;
          v17 = 0;
          v18 = 0;
          goto LABEL_22;
        }
        result = -2147024809;
        goto LABEL_11;
      }
    }
    v17 = 0;
    v18 = 0;
    if ( v15 )
    {
LABEL_22:
      while ( a3[v18] != 32 )
      {
        if ( ++v18 >= v15 )
          goto LABEL_26;
      }
      v17 = 1;
    }
LABEL_26:
    result = STRA::Copy((FTP_COMMAND *)((char *)this + 16), a3, v18);
    if ( result < 0 )
      goto LABEL_9;
    result = ConvertToUnicode(
               *((LPCCH *)this + 6),
               *(_DWORD *)(*((_QWORD *)this + 132) + 4788LL),
               (FTP_COMMAND *)((char *)this + 72));
    if ( result < 0 )
      goto LABEL_9;
    v19 = (const wchar_t *)*((_QWORD *)this + 13);
    v20 = MULTISZ::First((struct FTP_SITE_CONFIG *)((char *)a5 + 992));
    if ( v20 )
    {
      while ( _wcsicmp(v20, v19) )
      {
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        v20 += v21 + 1;
        if ( !*v20 )
          goto LABEL_33;
      }
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
          2054,
          "COMMAND_FILTERING_CONFIG_ELEMENT::CheckForAllowedCommand",
          "Found denied command '%S'.\r\n",
          v19);
      *((_DWORD *)this + 267) = 1;
LABEL_45:
      if ( !v17 )
      {
        **((_WORD **)this + 43) = 0;
        v25 = (_BYTE *)*((_QWORD *)this + 20);
        *((_DWORD *)this + 90) = 0;
        *v25 = 0;
        *((_DWORD *)this + 44) = 0;
        goto LABEL_5;
      }
      result = STRA::Copy((FTP_COMMAND *)((char *)this + 128), &a3[v18 + 1], v15 - v18 - 1);
      if ( result >= 0 )
      {
        result = ConvertToUnicode(
                   *((LPCCH *)this + 20),
                   *(_DWORD *)(*((_QWORD *)this + 132) + 4788LL),
                   (FTP_COMMAND *)((char *)this + 312));
        if ( result >= 0 )
          goto LABEL_5;
      }
      goto LABEL_9;
    }
LABEL_33:
    if ( !*((_DWORD *)a5 + 262) )
    {
      v22 = MULTISZ::First((struct FTP_SITE_CONFIG *)((char *)a5 + 936));
      if ( !v22 )
      {
LABEL_43:
        v24 = (g_dwDebugFlags & 3) == 0;
        *((_DWORD *)this + 267) = 1;
        if ( !v24 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
            2103,
            "COMMAND_FILTERING_CONFIG_ELEMENT::CheckForAllowedCommand",
            "Command '%S' is not specifically allowed and will be rejected.\r\n",
            v19);
        goto LABEL_45;
      }
      while ( _wcsicmp(v22, v19) )
      {
        v23 = -1;
        do
          ++v23;
        while ( v22[v23] );
        v22 += v23 + 1;
        if ( !*v22 )
          goto LABEL_43;
      }
    }
    *((_DWORD *)this + 267) = 0;
    goto LABEL_45;
  }
  result = STRA::Copy((FTP_COMMAND *)((char *)this + 16), a3, v6);
  if ( result >= 0 )
  {
    result = ConvertToUnicode(
               *((LPCCH *)this + 6),
               *(_DWORD *)(*((_QWORD *)this + 132) + 4788LL),
               (FTP_COMMAND *)((char *)this + 72));
    if ( result >= 0 )
      goto LABEL_5;
  }
LABEL_9:
  if ( result != -2147024888 && result != -2147024882 )
    goto LABEL_11;
  return result;
}

```

## disassembly

```asm
0x18003d868  push    rbx
0x18003d86a  push    rbp
0x18003d86b  push    rsi
0x18003d86c  push    rdi
0x18003d86d  push    r12
0x18003d86f  push    r13
0x18003d871  push    r14
0x18003d873  push    r15
0x18003d875  sub     rsp, 38h
0x18003d879  mov     r15, [rsp+78h+arg_20]
0x18003d881  mov     r12, r8
0x18003d884  mov     esi, r9d
0x18003d887  mov     rbx, rdx
0x18003d88a  mov     rdi, rcx
0x18003d88d  mov     ebp, [r15+41Ch]
0x18003d894  mov     [rcx+340h], rsi
0x18003d89b  call    cs:__imp_GetTickCount
0x18003d8a1  mov     [rdi+420h], rbx
0x18003d8a8  mov     edx, 1
0x18003d8ad  mov     [rdi+438h], eax
0x18003d8b3  cmp     esi, ebp
0x18003d8b5  jbe     short loc_18003D8BF
0x18003d8b7  mov     esi, ebp
0x18003d8b9  mov     [rdi+428h], edx
0x18003d8bf  xor     r14d, r14d
0x18003d8c2  test    esi, esi
0x18003d8c4  jnz     short loc_18003D905
0x18003d8c6  mov     rcx, [rdi+158h]
0x18003d8cd  mov     [rcx], r14w
0x18003d8d1  mov     rax, [rdi+0A0h]
0x18003d8d8  mov     [rdi+168h], r14d
0x18003d8df  mov     [rax], r14b
0x18003d8e2  mov     rcx, [rdi+68h]
0x18003d8e6  mov     [rdi+0B0h], r14d
0x18003d8ed  mov     [rcx], r14w
0x18003d8f1  mov     rax, [rdi+30h]
0x18003d8f5  mov     [rdi+78h], r14d
0x18003d8f9  mov     [rax], r14b
0x18003d8fc  mov     [rdi+40h], r14d
0x18003d900  mov     eax, r14d
0x18003d903  jmp     short loc_18003D94A
0x18003d905  cmp     esi, 2
0x18003d908  ja      short loc_18003D964
0x18003d90a  lea     rcx, [rdi+10h]
0x18003d90e  mov     r8d, esi
0x18003d911  mov     rdx, r12
0x18003d914  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18003d91a  test    eax, eax
0x18003d91c  js      short loc_18003D93C
0x18003d91e  mov     rdx, [rdi+420h]
0x18003d925  lea     r8, [rdi+48h]; struct STRU *
0x18003d929  mov     rcx, [rdi+30h]; lpMultiByteStr
0x18003d92d  mov     edx, [rdx+12B4h]; CodePage
0x18003d933  call    ?ConvertToUnicode@@YAJPEBDKPEAVSTRU@@@Z; ConvertToUnicode(char const *,ulong,STRU *)
0x18003d938  test    eax, eax
0x18003d93a  jns     short loc_18003D900
0x18003d93c  cmp     eax, 80070008h
0x18003d941  jz      short loc_18003D953
0x18003d943  cmp     eax, 8007000Eh
0x18003d948  jz      short loc_18003D953
0x18003d94a  mov     [rdi+494h], eax
0x18003d950  mov     eax, r14d
0x18003d953  add     rsp, 38h
0x18003d957  pop     r15
0x18003d959  pop     r14
0x18003d95b  pop     r13
0x18003d95d  pop     r12
0x18003d95f  pop     rdi
0x18003d960  pop     rsi
0x18003d961  pop     rbp
0x18003d962  pop     rbx
0x18003d963  retn
0x18003d964  mov     ebx, r14d
0x18003d967  mov     eax, ebx
0x18003d969  lea     ecx, [rbx+1]
0x18003d96c  cmp     byte ptr [rax+r12], 0Dh
0x18003d971  jnz     short loc_18003D97A
0x18003d973  cmp     byte ptr [rcx+r12], 0Ah
0x18003d978  jz      short loc_18003D990
0x18003d97a  mov     ebx, ecx
0x18003d97c  cmp     ecx, esi
0x18003d97e  jb      short loc_18003D967
0x18003d980  cmp     [rdi+428h], r14d
0x18003d987  jnz     short loc_18003D99C
0x18003d989  mov     eax, 80070057h
0x18003d98e  jmp     short loc_18003D94A
0x18003d990  mov     r13d, r14d
0x18003d993  mov     ebp, r14d
0x18003d996  test    ebx, ebx
0x18003d998  jz      short loc_18003D9B8
0x18003d99a  jmp     short loc_18003D9A4
0x18003d99c  mov     ebx, esi
0x18003d99e  mov     r13d, r14d
0x18003d9a1  mov     ebp, r14d
0x18003d9a4  mov     eax, ebp
0x18003d9a6  cmp     byte ptr [rax+r12], 20h ; ' '
0x18003d9ab  jz      short loc_18003D9B5
0x18003d9ad  add     ebp, edx
0x18003d9af  cmp     ebp, ebx
0x18003d9b1  jb      short loc_18003D9A4
0x18003d9b3  jmp     short loc_18003D9B8
0x18003d9b5  mov     r13d, edx
0x18003d9b8  lea     rcx, [rdi+10h]
0x18003d9bc  mov     r8d, ebp
0x18003d9bf  mov     rdx, r12
0x18003d9c2  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18003d9c8  test    eax, eax
0x18003d9ca  js      loc_18003D93C
0x18003d9d0  mov     rdx, [rdi+420h]
0x18003d9d7  lea     r8, [rdi+48h]; struct STRU *
0x18003d9db  mov     rcx, [rdi+30h]; lpMultiByteStr
0x18003d9df  mov     edx, [rdx+12B4h]; CodePage
0x18003d9e5  call    ?ConvertToUnicode@@YAJPEBDKPEAVSTRU@@@Z; ConvertToUnicode(char const *,ulong,STRU *)
0x18003d9ea  test    eax, eax
0x18003d9ec  js      loc_18003D93C
0x18003d9f2  mov     r14, [rdi+68h]
0x18003d9f6  lea     rcx, [r15+3E0h]
0x18003d9fd  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18003da03  xor     ecx, ecx
0x18003da05  mov     rsi, rax
0x18003da08  test    rax, rax
0x18003da0b  jz      short loc_18003DA39
0x18003da0d  mov     rdx, r14; String2
0x18003da10  mov     rcx, rsi; String1
0x18003da13  call    cs:__imp__wcsicmp
0x18003da19  xor     ecx, ecx
0x18003da1b  test    eax, eax
0x18003da1d  jz      short loc_18003DA51
0x18003da1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003da23  inc     rax
0x18003da26  cmp     [rsi+rax*2], cx
0x18003da2a  jnz     short loc_18003DA23
0x18003da2c  lea     rsi, [rsi+rax*2]
0x18003da30  add     rsi, 2
0x18003da34  cmp     [rsi], cx
0x18003da37  jnz     short loc_18003DA0D
0x18003da39  cmp     [r15+418h], ecx
0x18003da40  jz      short loc_18003DA9B
0x18003da42  xor     r14d, r14d
0x18003da45  mov     [rdi+42Ch], r14d
0x18003da4c  jmp     loc_18003DB2B
0x18003da51  test    byte ptr cs:g_dwDebugFlags, 3
0x18003da58  jz      short loc_18003DA8C
0x18003da5a  mov     rcx, cs:g_pDebug
0x18003da61  lea     rax, aFoundDeniedCom; "Found denied command '%S'.\r\n"
0x18003da68  mov     [rsp+78h+var_50], r14
0x18003da6d  lea     r9, aCommandFilteri; "COMMAND_FILTERING_CONFIG_ELEMENT::Check"...
0x18003da74  mov     r8d, 806h
0x18003da7a  mov     [rsp+78h+var_58], rax
0x18003da7f  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18003da86  call    cs:__imp_PuDbgPrint
0x18003da8c  mov     dword ptr [rdi+42Ch], 1
0x18003da96  jmp     loc_18003DB28
0x18003da9b  lea     rcx, [r15+3A8h]
0x18003daa2  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18003daa8  xor     r15d, r15d
0x18003daab  mov     rsi, rax
0x18003daae  test    rax, rax
0x18003dab1  jz      short loc_18003DAE3
0x18003dab3  mov     rdx, r14; String2
0x18003dab6  mov     rcx, rsi; String1
0x18003dab9  call    cs:__imp__wcsicmp
0x18003dabf  test    eax, eax
0x18003dac1  jz      loc_18003DA42
0x18003dac7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003dacb  inc     rax
0x18003dace  cmp     [rsi+rax*2], r15w
0x18003dad3  jnz     short loc_18003DACB
0x18003dad5  lea     rsi, [rsi+rax*2]
0x18003dad9  add     rsi, 2
0x18003dadd  cmp     [rsi], r15w
0x18003dae1  jnz     short loc_18003DAB3
0x18003dae3  test    byte ptr cs:g_dwDebugFlags, 3
0x18003daea  mov     dword ptr [rdi+42Ch], 1
0x18003daf4  jz      short loc_18003DB28
0x18003daf6  mov     rcx, cs:g_pDebug
0x18003dafd  lea     rax, aCommandSIsNotS; "Command '%S' is not specifically allowe"...
0x18003db04  mov     [rsp+78h+var_50], r14
0x18003db09  lea     r9, aCommandFilteri; "COMMAND_FILTERING_CONFIG_ELEMENT::Check"...
0x18003db10  mov     r8d, 837h
0x18003db16  mov     [rsp+78h+var_58], rax
0x18003db1b  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18003db22  call    cs:__imp_PuDbgPrint
0x18003db28  xor     r14d, r14d
0x18003db2b  lea     r9, [rdi+80h]
0x18003db32  test    r13d, r13d
0x18003db35  jz      short loc_18003DB83
0x18003db37  sub     ebx, ebp
0x18003db39  mov     edx, ebp
0x18003db3b  inc     rdx
0x18003db3e  mov     rcx, r9
0x18003db41  add     rdx, r12
0x18003db44  lea     r8d, [rbx-1]
0x18003db48  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18003db4e  test    eax, eax
0x18003db50  js      loc_18003D93C
0x18003db56  mov     rdx, [rdi+420h]
0x18003db5d  lea     r8, [rdi+138h]; struct STRU *
0x18003db64  mov     rcx, [rdi+0A0h]; lpMultiByteStr
0x18003db6b  mov     edx, [rdx+12B4h]; CodePage
0x18003db71  call    ?ConvertToUnicode@@YAJPEBDKPEAVSTRU@@@Z; ConvertToUnicode(char const *,ulong,STRU *)
0x18003db76  test    eax, eax
0x18003db78  jns     loc_18003D900
0x18003db7e  jmp     loc_18003D93C
0x18003db83  mov     rcx, [rdi+158h]
0x18003db8a  mov     [rcx], r14w
0x18003db8e  mov     rax, [r9+20h]
0x18003db92  mov     [rdi+168h], r14d
0x18003db99  mov     [rax], r14b
0x18003db9c  mov     [r9+30h], r14d
0x18003dba0  jmp     loc_18003D900
```
