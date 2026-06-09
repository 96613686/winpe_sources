# FTP_COMMAND::Process(int *)

- ea: `0x18003dbac`
- end: `0x18003e03e`
- name: `?Process@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `1170`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180035240`
- `0x18003553c`

## callees

- `0x18003732c`
- `0x180037f14`
- `0x18003dbac`
- `0x18003e564`
- `0x18003e980`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_stricmp` at `0x18003dc71`
- `msvcrt!_stricmp` at `0x18003de9a`
- `msvcrt!_stricmp` at `0x18003dc71`
- `msvcrt!_stricmp` at `0x18003de9a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003ddab`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003de14`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003dfb1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003ddab`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003de14`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003dfb1`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18003dd38`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18003dd38`

## string_xrefs

- `0x18003dda4`: `Command filtering rules denied the access.`
- `0x18003de0d`: `Command filtering rules denied the access.`
- `0x18003ddbf`: `Command not allowed.`
- `0x18003dfc9`: `Command not allowed.`
- `0x18003decc`: `Command not understood.`

## pseudocode

```c
void __fastcall FTP_COMMAND::Process(FTP_COMMAND *this, int *a2)
{
  __int64 v4; // rax
  const char *v5; // r15
  __int64 v6; // r12
  __int64 v7; // rbx
  CEtwTracer *v8; // r13
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  const char *v14; // r8
  const char *v15; // rdx
  __int64 i; // rbx
  const char *v17; // r15
  unsigned int v18; // r8d
  char v19; // al
  char *v20; // rdx
  int v21; // ecx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  struct _EVENT_TRACE_HEADER v24; // [rsp+30h] [rbp-49h] BYREF
  __int64 v25; // [rsp+60h] [rbp-19h]
  int v26; // [rsp+68h] [rbp-11h]
  __int64 v27; // [rsp+70h] [rbp-9h]
  int v28; // [rsp+78h] [rbp-1h]
  const char *v29; // [rsp+80h] [rbp+7h]
  int v30; // [rsp+88h] [rbp+Fh]

  (***((void (__fastcall ****)(_QWORD))this + 132))(*((_QWORD *)this + 132));
  if ( !*((_DWORD *)this + 16) && *((int *)this + 293) >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const OLECHAR *, _DWORD))(**((_QWORD **)this + 132) + 32LL))(
      *((_QWORD *)this + 132),
      0,
      0,
      &WideCharStr,
      0);
    *a2 = 1;
    return;
  }
  v4 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v4 + 8) && (*(_BYTE *)(v4 + 40) & 2) != 0 && *(_DWORD *)(v4 + 44) >= 4u )
  {
    v5 = "***";
    if ( _stricmp(*((const char **)this + 6), "PASS") )
      v5 = (const char *)*((_QWORD *)this + 20);
    v6 = *((_QWORD *)this + 6);
    v7 = *((_QWORD *)this + 132) + 368LL;
    v8 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    memset_0(&v24.FieldTypeFlags, 0, 0x5Eu);
    v24.UserTime = 1703936;
    v24.Size = 96;
    v24.GuidPtr = (ULONGLONG)&`FtpCommandsEvents::GetAreaGuid'::`2'::AreaGuid;
    v9 = -1;
    v24.Class.Version = 1;
    v24.Class.Type = 1;
    v25 = v7;
    v26 = 16;
    v27 = v6;
    if ( v6 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_BYTE *)(v6 + v11) );
      v10 = v11 + 1;
    }
    else
    {
      v10 = 0;
    }
    v28 = v10;
    v29 = v5;
    if ( v5 )
    {
      do
        ++v9;
      while ( v5[v9] );
      v12 = v9 + 1;
    }
    else
    {
      v12 = 0;
    }
    v30 = v12;
    CEtwTracer::EtwTraceEvent(v8, &v24);
  }
  v13 = *((_DWORD *)this + 293);
  if ( v13 < 0 )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = v13;
    FTP_COMMAND::WriteResponseWithErrorTextAndLog(this, "451");
    goto LABEL_23;
  }
  if ( *((_DWORD *)this + 267) )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024891;
    if ( !*((_DWORD *)this + 274) )
    {
      *((_DWORD *)this + 274) = 51;
      STRU::Copy((FTP_COMMAND *)((char *)this + 1112), L"Command filtering rules denied the access.");
      *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
    }
    v14 = "Command not allowed.";
LABEL_30:
    v15 = "500";
LABEL_31:
    FTP_COMMAND::WriteResponseAndLog(this, v15, v14);
LABEL_23:
    *a2 = 1;
    return;
  }
  if ( *((_DWORD *)this + 266) )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024809;
    if ( !*((_DWORD *)this + 274) )
    {
      *((_DWORD *)this + 274) = 51;
      STRU::Copy((FTP_COMMAND *)((char *)this + 1112), L"Command filtering rules denied the access.");
      *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
    }
    v14 = "Parameter too long.";
LABEL_39:
    v15 = "501";
    goto LABEL_31;
  }
  i = *((_QWORD *)this + 101);
  if ( !i )
  {
    v17 = (const char *)*((_QWORD *)this + 6);
    v18 = 0;
    v19 = *v17;
    if ( *v17 )
    {
      v20 = (char *)*((_QWORD *)this + 6);
      do
      {
        ++v20;
        v21 = v19 & 0xDF;
        v19 = *v20;
        v18 = v21 + 101 * v18;
      }
      while ( *v20 );
    }
    for ( i = *((_QWORD *)FTP_COMMAND_TABLE::sm_pFtpCommandTable + v18 % 0x83 + 1);
          i && _stricmp(v17, *(const char **)i);
          i = *(_QWORD *)(i + 8) )
    {
      ;
    }
    *((_QWORD *)this + 101) = i;
    if ( !i )
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024809;
      v14 = "Command not understood.";
      goto LABEL_30;
    }
  }
  if ( (*(_BYTE *)(i + 32) & 8) != 0
    && !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 132) + 1056LL) + 40LL))(*(_QWORD *)(*((_QWORD *)this + 132) + 1056LL)) )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024120;
    FTP_COMMAND::WriteResponseAndLog(this, "530", "Please login with USER and PASS.");
    goto LABEL_23;
  }
  v22 = *((_QWORD *)this + 101);
  if ( *(_DWORD *)(v22 + 16)
    && ((*(_BYTE *)(v22 + 32) & 1) != 0 && *((_DWORD *)this + 44)
     || (*(_BYTE *)(v22 + 32) & 4) != 0 && !*((_DWORD *)this + 44)) )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024809;
    v14 = "Invalid number of parameters.";
    goto LABEL_39;
  }
  FTP_COMMAND::CallPreProcessProvider(this);
  if ( *((_DWORD *)this + 294) )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024891;
    if ( !*((_DWORD *)this + 274) )
    {
      *((_DWORD *)this + 274) = 58;
      STRU::Copy((FTP_COMMAND *)((char *)this + 1112), L"Custom provider denied request.");
      *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
    }
    FTP_COMMAND::WriteResponseAndLog(this, "550", "Command not allowed.", *((_QWORD *)this + 6));
    goto LABEL_23;
  }
  v23 = (_QWORD *)*((_QWORD *)this + 132);
  *((_QWORD *)this + 107) = v23[9];
  *((_QWORD *)this + 106) = v23[8];
  *((_QWORD *)this + 105) = v23[10];
  FTP_COMMAND::CallHandler(this, a2);
}

```

## disassembly

```asm
0x18003dbac  mov     [rsp-8+arg_10], rbx
0x18003dbb1  push    rbp
0x18003dbb2  push    rsi
0x18003dbb3  push    rdi
0x18003dbb4  push    r12
0x18003dbb6  push    r13
0x18003dbb8  push    r14
0x18003dbba  push    r15
0x18003dbbc  lea     rbp, [rsp-27h]
0x18003dbc1  sub     rsp, 0A0h
0x18003dbc8  mov     rax, cs:__security_cookie
0x18003dbcf  xor     rax, rsp
0x18003dbd2  mov     [rbp+57h+var_40], rax
0x18003dbd6  mov     rdi, rcx
0x18003dbd9  mov     r14, rdx
0x18003dbdc  mov     rcx, [rcx+420h]
0x18003dbe3  mov     rax, [rcx]
0x18003dbe6  mov     rax, [rax]
0x18003dbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbee  xor     r12d, r12d
0x18003dbf1  cmp     [rdi+40h], r12d
0x18003dbf5  jnz     short loc_18003DC30
0x18003dbf7  cmp     [rdi+494h], r12d
0x18003dbfe  jl      short loc_18003DC30
0x18003dc00  mov     rcx, [rdi+420h]
0x18003dc07  lea     r9, WideCharStr
0x18003dc0e  xor     r8d, r8d
0x18003dc11  mov     [rsp+0D0h+var_B0], r12d
0x18003dc16  xor     edx, edx
0x18003dc18  mov     rax, [rcx]
0x18003dc1b  mov     rax, [rax+20h]
0x18003dc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc24  mov     dword ptr [r14], 1
0x18003dc2b  jmp     loc_18003E017
0x18003dc30  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003dc37  mov     rax, [rcx]
0x18003dc3a  mov     rax, [rax+20h]
0x18003dc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc43  mov     esi, 1
0x18003dc48  cmp     [rax+8], r12d
0x18003dc4c  jz      loc_18003DD3E
0x18003dc52  test    byte ptr [rax+28h], 2
0x18003dc56  jz      loc_18003DD3E
0x18003dc5c  cmp     dword ptr [rax+2Ch], 4
0x18003dc60  jb      loc_18003DD3E
0x18003dc66  mov     rcx, [rdi+30h]; String1
0x18003dc6a  lea     rdx, aPass; "PASS"
0x18003dc71  call    cs:__imp__stricmp
0x18003dc77  lea     r15, asc_180053DFC; "***"
0x18003dc7e  test    eax, eax
0x18003dc80  jz      short loc_18003DC89
0x18003dc82  mov     r15, [rdi+0A0h]
0x18003dc89  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003dc90  mov     rbx, [rdi+420h]
0x18003dc97  mov     r12, [rdi+30h]
0x18003dc9b  add     rbx, 170h
0x18003dca2  mov     rax, [rcx]
0x18003dca5  mov     rax, [rax+20h]
0x18003dca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcae  xor     edx, edx; Val
0x18003dcb0  lea     rcx, [rbp+57h+var_9E]; void *
0x18003dcb4  mov     r13, rax
0x18003dcb7  lea     r8d, [rdx+5Eh]; Size
0x18003dcbb  call    memset_0
0x18003dcc0  mov     eax, 60h ; '`'
0x18003dcc5  mov     [rbp+57h+var_74], 1A0000h
0x18003dccc  mov     [rbp+57h+var_A0], ax
0x18003dcd0  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpCommandsEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpCommandsEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18003dcd7  mov     [rbp+57h+var_88], rax
0x18003dcdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003dcdf  mov     [rbp+57h+var_9A], si
0x18003dce3  mov     [rbp+57h+var_9C], sil
0x18003dce7  mov     [rbp+57h+var_70], rbx
0x18003dceb  mov     [rbp+57h+var_68], 10h
0x18003dcf2  mov     [rbp+57h+var_60], r12
0x18003dcf6  test    r12, r12
0x18003dcf9  jnz     short loc_18003DD00
0x18003dcfb  mov     ecx, r12d
0x18003dcfe  jmp     short loc_18003DD12
0x18003dd00  mov     rcx, rax
0x18003dd03  inc     rcx
0x18003dd06  cmp     byte ptr [r12+rcx], 0
0x18003dd0b  jnz     short loc_18003DD03
0x18003dd0d  inc     ecx
0x18003dd0f  xor     r12d, r12d
0x18003dd12  mov     [rbp+57h+var_58], ecx
0x18003dd15  mov     [rbp+57h+var_50], r15
0x18003dd19  test    r15, r15
0x18003dd1c  jnz     short loc_18003DD23
0x18003dd1e  mov     eax, r12d
0x18003dd21  jmp     short loc_18003DD2E
0x18003dd23  inc     rax
0x18003dd26  cmp     [r15+rax], r12b
0x18003dd2a  jnz     short loc_18003DD23
0x18003dd2c  inc     eax
0x18003dd2e  lea     rdx, [rbp+57h+var_A0]
0x18003dd32  mov     [rbp+57h+var_48], eax
0x18003dd35  mov     rcx, r13
0x18003dd38  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18003dd3e  mov     eax, [rdi+494h]
0x18003dd44  test    eax, eax
0x18003dd46  jns     short loc_18003DD6E
0x18003dd48  cmp     [rdi+490h], r12d
0x18003dd4f  jnz     short loc_18003DD57
0x18003dd51  mov     [rdi+490h], eax
0x18003dd57  lea     rdx, a451; "451"
0x18003dd5e  mov     rcx, rdi; this
0x18003dd61  call    ?WriteResponseWithErrorTextAndLog@FTP_COMMAND@@QEAAJPEBD@Z; FTP_COMMAND::WriteResponseWithErrorTextAndLog(char const *)
0x18003dd66  mov     [r14], esi
0x18003dd69  jmp     loc_18003E017
0x18003dd6e  cmp     [rdi+42Ch], r12d
0x18003dd75  jz      short loc_18003DDD7
0x18003dd77  cmp     [rdi+490h], r12d
0x18003dd7e  jnz     short loc_18003DD8A
0x18003dd80  mov     dword ptr [rdi+490h], 80070005h
0x18003dd8a  cmp     [rdi+448h], r12d
0x18003dd91  jnz     short loc_18003DDBF
0x18003dd93  lea     rcx, [rdi+458h]
0x18003dd9a  mov     dword ptr [rdi+448h], 33h ; '3'
0x18003dda4  lea     rdx, aCommandFilteri_1; "Command filtering rules denied the acce"...
0x18003ddab  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003ddb1  mov     rax, [rdi+478h]
0x18003ddb8  mov     [rdi+450h], rax
0x18003ddbf  lea     r8, aCommandNotAllo; "Command not allowed."
0x18003ddc6  lea     rdx, a500; "500"
0x18003ddcd  mov     rcx, rdi; this
0x18003ddd0  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003ddd5  jmp     short loc_18003DD66
0x18003ddd7  cmp     [rdi+428h], r12d
0x18003ddde  jz      short loc_18003DE38
0x18003dde0  cmp     [rdi+490h], r12d
0x18003dde7  jnz     short loc_18003DDF3
0x18003dde9  mov     dword ptr [rdi+490h], 80070057h
0x18003ddf3  cmp     [rdi+448h], r12d
0x18003ddfa  jnz     short loc_18003DE28
0x18003ddfc  lea     rcx, [rdi+458h]
0x18003de03  mov     dword ptr [rdi+448h], 33h ; '3'
0x18003de0d  lea     rdx, aCommandFilteri_1; "Command filtering rules denied the acce"...
0x18003de14  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003de1a  mov     rax, [rdi+478h]
0x18003de21  mov     [rdi+450h], rax
0x18003de28  lea     r8, aParameterTooLo; "Parameter too long."
0x18003de2f  lea     rdx, a501; "501"
0x18003de36  jmp     short loc_18003DDCD
0x18003de38  mov     rbx, [rdi+328h]
0x18003de3f  test    rbx, rbx
0x18003de42  jnz     loc_18003DED8
0x18003de48  mov     r15, [rdi+30h]
0x18003de4c  mov     r8d, r12d
0x18003de4f  mov     rbx, cs:?sm_pFtpCommandTable@FTP_COMMAND_TABLE@@0PEAV1@EA; FTP_COMMAND_TABLE * FTP_COMMAND_TABLE::sm_pFtpCommandTable
0x18003de56  mov     al, [r15]
0x18003de59  test    al, al
0x18003de5b  jz      short loc_18003DE79
0x18003de5d  mov     rdx, r15
0x18003de60  imul    r8d, 65h ; 'e'
0x18003de64  add     rdx, rsi
0x18003de67  movzx   ecx, al
0x18003de6a  and     ecx, 0DFh
0x18003de70  mov     al, [rdx]
0x18003de72  add     r8d, ecx
0x18003de75  test    al, al
0x18003de77  jnz     short loc_18003DE60
0x18003de79  mov     eax, 0FA232CF3h
0x18003de7e  mul     r8d
0x18003de81  shr     edx, 7
0x18003de84  imul    eax, edx, 83h
0x18003de8a  sub     r8d, eax
0x18003de8d  mov     rbx, [rbx+r8*8+8]
0x18003de92  jmp     short loc_18003DEA8
0x18003de94  mov     rdx, [rbx]; String2
0x18003de97  mov     rcx, r15; String1
0x18003de9a  call    cs:__imp__stricmp
0x18003dea0  test    eax, eax
0x18003dea2  jz      short loc_18003DEAD
0x18003dea4  mov     rbx, [rbx+8]
0x18003dea8  test    rbx, rbx
0x18003deab  jnz     short loc_18003DE94
0x18003dead  mov     [rdi+328h], rbx
0x18003deb4  test    rbx, rbx
0x18003deb7  jnz     short loc_18003DED8
0x18003deb9  cmp     [rdi+490h], r12d
0x18003dec0  jnz     short loc_18003DECC
0x18003dec2  mov     dword ptr [rdi+490h], 80070057h
0x18003decc  lea     r8, aCommandNotUnde; "Command not understood."
0x18003ded3  jmp     loc_18003DDC6
0x18003ded8  test    byte ptr [rbx+20h], 8
0x18003dedc  jz      short loc_18003DF22
0x18003dede  mov     rax, [rdi+420h]
0x18003dee5  mov     rcx, [rax+420h]
0x18003deec  mov     rax, [rcx]
0x18003deef  mov     rax, [rax+28h]
0x18003def3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003def8  test    eax, eax
0x18003defa  jnz     short loc_18003DF22
0x18003defc  cmp     [rdi+490h], r12d
0x18003df03  jnz     short loc_18003DF0F
0x18003df05  mov     dword ptr [rdi+490h], 80070308h
0x18003df0f  lea     r8, aPleaseLoginWit; "Please login with USER and PASS."
0x18003df16  lea     rdx, a530; "530"
0x18003df1d  jmp     loc_18003DDCD
0x18003df22  mov     rax, [rdi+328h]
0x18003df29  cmp     [rax+10h], r12d
0x18003df2d  jz      short loc_18003DF6C
0x18003df2f  test    [rax+20h], sil
0x18003df33  jz      short loc_18003DF3E
0x18003df35  cmp     [rdi+0B0h], r12d
0x18003df3c  jnz     short loc_18003DF4D
0x18003df3e  test    byte ptr [rax+20h], 4
0x18003df42  jz      short loc_18003DF6C
0x18003df44  cmp     [rdi+0B0h], r12d
0x18003df4b  jnz     short loc_18003DF6C
0x18003df4d  cmp     [rdi+490h], r12d
0x18003df54  jnz     short loc_18003DF60
0x18003df56  mov     dword ptr [rdi+490h], 80070057h
0x18003df60  lea     r8, aInvalidNumberO; "Invalid number of parameters."
0x18003df67  jmp     loc_18003DE2F
0x18003df6c  mov     rcx, rdi; this
0x18003df6f  call    ?CallPreProcessProvider@FTP_COMMAND@@QEAAJXZ; FTP_COMMAND::CallPreProcessProvider(void)
0x18003df74  cmp     [rdi+498h], r12d
0x18003df7b  jz      short loc_18003DFE4
0x18003df7d  cmp     [rdi+490h], r12d
0x18003df84  jnz     short loc_18003DF90
0x18003df86  mov     dword ptr [rdi+490h], 80070005h
0x18003df90  cmp     [rdi+448h], r12d
0x18003df97  jnz     short loc_18003DFC5
0x18003df99  lea     rcx, [rdi+458h]
0x18003dfa0  mov     dword ptr [rdi+448h], 3Ah ; ':'
0x18003dfaa  lea     rdx, aCustomProvider_2; "Custom provider denied request."
0x18003dfb1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003dfb7  mov     rax, [rdi+478h]
0x18003dfbe  mov     [rdi+450h], rax
0x18003dfc5  mov     r9, [rdi+30h]
0x18003dfc9  lea     r8, aCommandNotAllo; "Command not allowed."
0x18003dfd0  lea     rdx, a550; "550"
0x18003dfd7  mov     rcx, rdi; this
0x18003dfda  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003dfdf  jmp     loc_18003DD66
0x18003dfe4  mov     rcx, [rdi+420h]
0x18003dfeb  mov     rdx, r14; int *
0x18003dfee  mov     rax, [rcx+48h]
0x18003dff2  mov     [rdi+358h], rax
0x18003dff9  mov     rax, [rcx+40h]
0x18003dffd  mov     [rdi+350h], rax
0x18003e004  mov     rax, [rcx+50h]
0x18003e008  mov     rcx, rdi; this
0x18003e00b  mov     [rdi+348h], rax
0x18003e012  call    ?CallHandler@FTP_COMMAND@@QEAAXPEAH@Z; FTP_COMMAND::CallHandler(int *)
0x18003e017  mov     rcx, [rbp+57h+var_40]
0x18003e01b  xor     rcx, rsp; StackCookie
0x18003e01e  call    __security_check_cookie
0x18003e023  mov     rbx, [rsp+0D0h+arg_10]
0x18003e02b  add     rsp, 0A0h
0x18003e032  pop     r15
0x18003e034  pop     r14
0x18003e036  pop     r13
0x18003e038  pop     r12
0x18003e03a  pop     rdi
0x18003e03b  pop     rsi
0x18003e03c  pop     rbp
0x18003e03d  retn
```
