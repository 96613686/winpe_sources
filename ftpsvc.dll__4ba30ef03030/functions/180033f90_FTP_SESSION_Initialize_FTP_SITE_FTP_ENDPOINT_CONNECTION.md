# FTP_SESSION::Initialize(FTP_SITE *,FTP_ENDPOINT_CONNECTION *)

- ea: `0x180033f90`
- end: `0x1800344b5`
- name: `?Initialize@FTP_SESSION@@UEAAJPEAVFTP_SITE@@PEAVFTP_ENDPOINT_CONNECTION@@@Z`
- size: `1317`
- prototype: `__int64 __fastcall(FTP_SESSION *__hidden this, struct FTP_SITE *, struct FTP_ENDPOINT_CONNECTION *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001210`
- `0x180009090`
- `0x180009468`
- `0x18000e230`
- `0x180033f90`
- `0x1800344bc`
- `0x180034794`
- `0x180035ea0`
- `0x18003f50c`
- `0x180041544`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18003420e`
- `KERNEL32!GetSystemTime` at `0x18003420e`
- `KERNEL32!GetTickCount` at `0x180034214`
- `KERNEL32!GetTickCount` at `0x18003422a`
- `KERNEL32!GetTickCount` at `0x18003446e`
- `KERNEL32!GetTickCount` at `0x180034214`
- `KERNEL32!GetTickCount` at `0x18003422a`
- `KERNEL32!GetTickCount` at `0x18003446e`
- `WS2_32!GetNameInfoW` at `0x1800340e4`
- `WS2_32!GetNameInfoW` at `0x18003412b`
- `WS2_32!GetNameInfoW` at `0x1800340e4`
- `WS2_32!GetNameInfoW` at `0x18003412b`
- `WS2_32!__imp_ntohs` at `0x18003417e`
- `WS2_32!__imp_ntohs` at `0x180034197`
- `WS2_32!__imp_ntohs` at `0x18003428f`
- `WS2_32!__imp_ntohs` at `0x18003417e`
- `WS2_32!__imp_ntohs` at `0x180034197`
- `WS2_32!__imp_ntohs` at `0x18003428f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034303`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034303`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180034457`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180034457`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18003406b`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18003406b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034053`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800340fc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034141`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034053`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800340fc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034141`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180034335`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180034335`
- `iisutil!WriteRefTraceLog` at `0x180034325`
- `iisutil!WriteRefTraceLog` at `0x18003443a`
- `iisutil!WriteRefTraceLog` at `0x180034325`
- `iisutil!WriteRefTraceLog` at `0x18003443a`
- `iisutil!IsLocalRequest` at `0x1800340a3`
- `iisutil!IsLocalRequest` at `0x1800340a3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800342e4`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800342e4`
- `RPCRT4!UuidToStringW` at `0x18003403d`
- `RPCRT4!UuidToStringW` at `0x18003403d`
- `RPCRT4!RpcStringFreeW` at `0x18003407d`
- `RPCRT4!RpcStringFreeW` at `0x18003407d`
- `RPCRT4!UuidCreate` at `0x180034025`
- `RPCRT4!UuidCreate` at `0x180034025`

## string_xrefs

- `0x1800343d9`: `ControlChannelOpened`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SESSION::Initialize(FTP_SESSION *this, struct FTP_SITE *a2, struct FTP_ENDPOINT_CONNECTION *a3)
{
  struct FTP_ENDPOINT_CONNECTION *v3; // rsi
  volatile signed __int32 *v4; // r15
  unsigned __int16 *v6; // rax
  USER_SESSION *v7; // rax
  int v8; // ebx
  socklen_t v9; // edi
  socklen_t v10; // edx
  __int64 v11; // rax
  char v12; // r14
  const unsigned __int16 *v13; // r15
  char v14; // di
  const unsigned __int16 *v15; // rsi
  const unsigned __int16 *v16; // rbx
  struct CEtwTracer *v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64, char *); // rbx
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rdi
  CReaderWriterLock3 *v23; // rbx
  __int64 v24; // rdx
  unsigned __int32 v25; // esi
  RPC_WSTR StringUuid; // [rsp+90h] [rbp-80h] BYREF
  struct FTP_SITE *v28; // [rsp+98h] [rbp-78h]
  struct FTP_ENDPOINT_CONNECTION *v29; // [rsp+A0h] [rbp-70h]
  WCHAR pNodeBuffer[56]; // [rsp+B0h] [rbp-60h] BYREF

  v3 = a3;
  v29 = a3;
  v4 = (volatile signed __int32 *)a2;
  v28 = a2;
  v6 = (unsigned __int16 *)operator new(0x508u);
  StringUuid = v6;
  if ( v6 )
    v7 = USER_SESSION::USER_SESSION((USER_SESSION *)v6);
  else
    v7 = 0;
  if ( !v7 )
  {
    v8 = -2147024888;
    goto LABEL_48;
  }
  *((_QWORD *)this + 132) = v7;
  v8 = FTP_SESSION::InitializeOrResetFtpSession(this, 1);
  if ( v8 < 0 )
    goto LABEL_48;
  StringUuid = 0;
  if ( UuidCreate((UUID *)this + 23) || UuidToStringW((const UUID *)this + 23, &StringUuid) )
  {
    v8 = -2147467259;
  }
  else
  {
    v8 = STRU::Copy((FTP_SESSION *)((char *)this + 136), StringUuid);
    if ( v8 >= 0 )
      v8 = STRA::CopyW((FTP_SESSION *)((char *)this + 272), StringUuid);
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( v8 < 0 )
    goto LABEL_48;
  *((_DWORD *)this + 1409) = IsLocalRequest((struct sockaddr *)v3 + 28, (struct sockaddr *)v3 + 20);
  v9 = 16;
  v10 = 16;
  if ( *((_WORD *)v3 + 160) != 2 )
    v10 = 28;
  if ( !GetNameInfoW((const SOCKADDR *)v3 + 20, v10, pNodeBuffer, 0x32u, 0, 0, 2) )
    STRU::Copy((FTP_SESSION *)((char *)this + 5704), pNodeBuffer);
  if ( *((_WORD *)v3 + 224) != 2 )
    v9 = 28;
  if ( !GetNameInfoW((const SOCKADDR *)v3 + 28, v9, pNodeBuffer, 0x32u, 0, 0, 2) )
    STRU::Copy((FTP_SESSION *)((char *)this + 5792), pNodeBuffer);
  v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v11 + 8) && (*(_BYTE *)(v11 + 40) & 1) != 0 && *(_DWORD *)(v11 + 44) >= 4u )
  {
    v12 = ntohs(*((_WORD *)v3 + 161));
    v13 = (const unsigned __int16 *)*((_QWORD *)this + 717);
    v14 = ntohs(*((_WORD *)v3 + 225));
    v15 = (const unsigned __int16 *)*((_QWORD *)this + 728);
    v16 = (const unsigned __int16 *)&dword_18004D454;
    if ( *((_QWORD *)v28 + 1) )
      v16 = (const unsigned __int16 *)*((_QWORD *)v28 + 1);
    v17 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpConnectionEvents::StartCtrlChannel::RaiseEvent(v17, (const struct _GUID *)this + 23, v16, v15, v14, v13, v12);
    v3 = v29;
    v4 = (volatile signed __int32 *)v28;
  }
  _InterlockedIncrement(v4 + 44);
  *((_QWORD *)this + 12) = v4;
  GetSystemTime((LPSYSTEMTIME)((char *)this + 4676));
  *((_DWORD *)this + 1166) = GetTickCount();
  *((_DWORD *)this + 516) = GetTickCount();
  *((_QWORD *)this + 135) = v3;
  *((_QWORD *)this + 134) = this;
  *((_QWORD *)this + 268) = this;
  v18 = *((_QWORD *)this + 132);
  v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, char *))(*(_QWORD *)v18 + 8LL);
  v20 = (*(__int64 (__fastcall **)(FTP_SESSION *))(*(_QWORD *)this + 64LL))(this);
  v8 = v19(v18, *((_QWORD *)this + 12), v20, (char *)this + 368);
  if ( v8 < 0 )
    goto LABEL_48;
  v21 = 0;
  if ( ntohs(*((_WORD *)v3 + 161)) != 990 )
    goto LABEL_37;
  *((_DWORD *)this + 1470) = 1;
  *((_DWORD *)this + 1471) = 1;
  v8 = FTP_CONTROL_CHANNEL::EnableSslSession((FTP_SESSION *)((char *)this + 1064), 0);
  if ( v8 < 0 || (*((_DWORD *)this + 1198) = 1, v8 = STRA::Copy((FTP_SESSION *)((char *)this + 5640), "P"), v8 < 0) )
  {
LABEL_48:
    *((_DWORD *)this + 516) = GetTickCount();
    *((_QWORD *)this + 135) = 0;
    *((_QWORD *)this + 134) = 0;
    return (unsigned int)v8;
  }
  v22 = *((_QWORD *)this + 12);
  v23 = (CReaderWriterLock3 *)(v22 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v22 + 208));
  v24 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v22 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v24);
  v21 = *(_QWORD *)(v22 + 192);
  CReaderWriterLock3::ReadUnlock(v23);
  if ( *(_DWORD *)(v21 + 116) == 2 )
    *((_DWORD *)this + 1424) = 1;
  v8 = FTP_DATA_CHANNEL::EnableSsl((struct _SecHandle *)((char *)this + 2072));
  if ( v8 >= 0 )
  {
LABEL_37:
    (**(void (__fastcall ***)(FTP_SESSION *))this)(this);
    v8 = FTP_SITE::AddToSessionList((FTP_SITE *)v4, this);
    if ( v8 >= 0 )
    {
      *((_DWORD *)this + 1405) = 1;
      FTP_SESSION::Log(
        this,
        4,
        *((_QWORD *)this + 38),
        *((_QWORD *)this + 135) + 448LL,
        *((_QWORD *)this + 135) + 320LL,
        &WideCharStr,
        &WideCharStr,
        &WideCharStr,
        0,
        0,
        L"ControlChannelOpened");
      v8 = 0;
    }
    else
    {
      (*(void (__fastcall **)(FTP_SESSION *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  if ( v21 )
  {
    v25 = _InterlockedDecrement((volatile signed __int32 *)v21);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v25);
    if ( !v25 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v21);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v21);
    }
  }
  if ( v8 < 0 )
    goto LABEL_48;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033f90  mov     [rsp-8+arg_18], rbx
0x180033f95  push    rbp
0x180033f96  push    rsi
0x180033f97  push    rdi
0x180033f98  push    r12
0x180033f9a  push    r13
0x180033f9c  push    r14
0x180033f9e  push    r15
0x180033fa0  lea     rbp, [rsp-20h]
0x180033fa5  sub     rsp, 130h
0x180033fac  mov     rax, cs:__security_cookie
0x180033fb3  xor     rax, rsp
0x180033fb6  mov     [rbp+50h+var_40], rax
0x180033fba  mov     rsi, r8
0x180033fbd  mov     [rbp+50h+var_C0], r8
0x180033fc1  mov     r15, rdx
0x180033fc4  mov     [rbp+50h+var_C8], rdx
0x180033fc8  mov     r12, rcx
0x180033fcb  mov     ecx, 508h; Size
0x180033fd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033fd5  mov     [rbp+50h+StringUuid], rax
0x180033fd9  xor     r14d, r14d
0x180033fdc  test    rax, rax
0x180033fdf  jz      short loc_180033FEB
0x180033fe1  mov     rcx, rax; this
0x180033fe4  call    ??0USER_SESSION@@QEAA@XZ; USER_SESSION::USER_SESSION(void)
0x180033fe9  jmp     short loc_180033FEE
0x180033feb  mov     rax, r14
0x180033fee  test    rax, rax
0x180033ff1  jz      loc_180034464
0x180033ff7  mov     [r12+420h], rax
0x180033fff  mov     edx, 1; int
0x180034004  mov     rcx, r12; this
0x180034007  call    ?InitializeOrResetFtpSession@FTP_SESSION@@QEAAJH@Z; FTP_SESSION::InitializeOrResetFtpSession(int)
0x18003400c  mov     ebx, eax
0x18003400e  test    eax, eax
0x180034010  js      loc_18003446E
0x180034016  mov     [rbp+50h+StringUuid], r14
0x18003401a  lea     r13, [r12+170h]
0x180034022  mov     rcx, r13; Uuid
0x180034025  call    cs:__imp_UuidCreate
0x18003402b  test    eax, eax
0x18003402d  jz      short loc_180034036
0x18003402f  mov     ebx, 80004005h
0x180034034  jmp     short loc_180034073
0x180034036  lea     rdx, [rbp+50h+StringUuid]; StringUuid
0x18003403a  mov     rcx, r13; Uuid
0x18003403d  call    cs:__imp_UuidToStringW
0x180034043  test    eax, eax
0x180034045  jnz     short loc_18003402F
0x180034047  lea     rcx, [r12+88h]
0x18003404f  mov     rdx, [rbp+50h+StringUuid]
0x180034053  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180034059  mov     ebx, eax
0x18003405b  test    eax, eax
0x18003405d  js      short loc_180034073
0x18003405f  lea     rcx, [r12+110h]
0x180034067  mov     rdx, [rbp+50h+StringUuid]
0x18003406b  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180034071  mov     ebx, eax
0x180034073  cmp     [rbp+50h+StringUuid], r14
0x180034077  jz      short loc_180034087
0x180034079  lea     rcx, [rbp+50h+StringUuid]; String
0x18003407d  call    cs:__imp_RpcStringFreeW
0x180034083  mov     [rbp+50h+StringUuid], r14
0x180034087  test    ebx, ebx
0x180034089  js      loc_18003446E
0x18003408f  lea     rbx, [rsi+140h]
0x180034096  lea     r14, [rsi+1C0h]
0x18003409d  mov     rdx, rbx
0x1800340a0  mov     rcx, r14
0x1800340a3  call    cs:__imp_?IsLocalRequest@@YAHPEAUsockaddr@@0@Z; IsLocalRequest(sockaddr *,sockaddr *)
0x1800340a9  mov     [r12+1604h], eax
0x1800340b1  mov     edi, 10h
0x1800340b6  mov     edx, edi
0x1800340b8  lea     ecx, [rdi+0Ch]
0x1800340bb  lea     eax, [rdi-0Eh]
0x1800340be  cmp     [rbx], ax
0x1800340c1  cmovnz  edx, ecx; SockaddrLength
0x1800340c4  mov     [rsp+160h+Flags], eax; Flags
0x1800340c8  mov     [rsp+160h+ServiceBufferSize], 0; ServiceBufferSize
0x1800340d0  mov     [rsp+160h+pServiceBuffer], 0; pServiceBuffer
0x1800340d9  lea     r9d, [rdi+22h]; NodeBufferSize
0x1800340dd  lea     r8, [rbp+50h+pNodeBuffer]; pNodeBuffer
0x1800340e1  mov     rcx, rbx; pSockaddr
0x1800340e4  call    cs:__imp_GetNameInfoW
0x1800340ea  xor     ebx, ebx
0x1800340ec  test    eax, eax
0x1800340ee  jnz     short loc_180034102
0x1800340f0  lea     rcx, [r12+1648h]
0x1800340f8  lea     rdx, [rbp+50h+pNodeBuffer]
0x1800340fc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180034102  mov     eax, 2
0x180034107  cmp     [r14], ax
0x18003410b  lea     ecx, [rax+1Ah]
0x18003410e  cmovnz  edi, ecx
0x180034111  mov     [rsp+160h+Flags], eax; Flags
0x180034115  mov     [rsp+160h+ServiceBufferSize], ebx; ServiceBufferSize
0x180034119  mov     [rsp+160h+pServiceBuffer], rbx; pServiceBuffer
0x18003411e  lea     r9d, [rax+30h]; NodeBufferSize
0x180034122  lea     r8, [rbp+50h+pNodeBuffer]; pNodeBuffer
0x180034126  mov     edx, edi; SockaddrLength
0x180034128  mov     rcx, r14; pSockaddr
0x18003412b  call    cs:__imp_GetNameInfoW
0x180034131  test    eax, eax
0x180034133  jnz     short loc_180034147
0x180034135  lea     rcx, [r12+16A0h]
0x18003413d  lea     rdx, [rbp+50h+pNodeBuffer]
0x180034141  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180034147  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003414e  mov     rax, [rcx]
0x180034151  mov     rax, [rax+20h]
0x180034155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003415a  cmp     [rax+8], ebx
0x18003415d  jz      loc_1800341F9
0x180034163  test    byte ptr [rax+28h], 1
0x180034167  jz      loc_1800341F9
0x18003416d  cmp     dword ptr [rax+2Ch], 4
0x180034171  jb      loc_1800341F9
0x180034177  movzx   ecx, word ptr [rsi+142h]; netshort
0x18003417e  call    cs:__imp_ntohs
0x180034184  movzx   r14d, ax
0x180034188  mov     r15, [r12+1668h]
0x180034190  movzx   ecx, word ptr [rsi+1C2h]; netshort
0x180034197  call    cs:__imp_ntohs
0x18003419d  movzx   edi, ax
0x1800341a0  mov     rsi, [r12+16C0h]
0x1800341a8  lea     rbx, dword_18004D454
0x1800341af  mov     rax, [rbp+50h+var_C8]
0x1800341b3  cmp     qword ptr [rax+8], 0
0x1800341b8  cmovnz  rbx, [rax+8]
0x1800341bd  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800341c4  mov     rdx, [rcx]
0x1800341c7  mov     rax, [rdx+20h]
0x1800341cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341d0  mov     word ptr [rsp+160h+Flags], r14w; char
0x1800341d6  mov     qword ptr [rsp+160h+ServiceBufferSize], r15; unsigned __int16 *
0x1800341db  mov     word ptr [rsp+160h+pServiceBuffer], di; char
0x1800341e0  mov     r9, rsi; unsigned __int16 *
0x1800341e3  mov     r8, rbx; unsigned __int16 *
0x1800341e6  mov     rdx, r13; struct _GUID *
0x1800341e9  mov     rcx, rax; struct CEtwTracer *
0x1800341ec  call    ?RaiseEvent@StartCtrlChannel@FtpConnectionEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG2G2G@Z; FtpConnectionEvents::StartCtrlChannel::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *,ushort const *,ushort,ushort const *,ushort)
0x1800341f1  mov     rsi, [rbp+50h+var_C0]
0x1800341f5  mov     r15, [rbp+50h+var_C8]
0x1800341f9  lock inc dword ptr [r15+0B0h]
0x180034201  mov     [r12+60h], r15
0x180034206  lea     rcx, [r12+1244h]; lpSystemTime
0x18003420e  call    cs:__imp_GetSystemTime
0x180034214  call    cs:__imp_GetTickCount
0x18003421a  mov     [r12+1238h], eax
0x180034222  lea     r14, [r12+428h]
0x18003422a  call    cs:__imp_GetTickCount
0x180034230  mov     [r14+3E8h], eax
0x180034237  mov     [r14+10h], rsi
0x18003423b  mov     [r14+8], r12
0x18003423f  mov     [r12+860h], r12
0x180034247  mov     rdi, [r12+420h]
0x18003424f  mov     rax, [rdi]
0x180034252  mov     rbx, [rax+8]
0x180034256  mov     rdx, [r12]
0x18003425a  mov     rcx, r12
0x18003425d  mov     rax, [rdx+40h]
0x180034261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034266  mov     r9, r13
0x180034269  mov     r8, rax
0x18003426c  mov     rdx, [r12+60h]
0x180034271  mov     rcx, rdi
0x180034274  mov     rax, rbx
0x180034277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003427c  mov     ebx, eax
0x18003427e  test    eax, eax
0x180034280  js      loc_18003446B
0x180034286  xor     edi, edi
0x180034288  movzx   ecx, word ptr [rsi+142h]; netshort
0x18003428f  call    cs:__imp_ntohs
0x180034295  mov     ecx, 3DEh
0x18003429a  lea     esi, [rdi+1]
0x18003429d  cmp     ax, cx
0x1800342a0  jnz     loc_180034362
0x1800342a6  mov     [r12+16F8h], esi
0x1800342ae  mov     [r12+16FCh], esi
0x1800342b6  xor     edx, edx; int
0x1800342b8  mov     rcx, r14; this
0x1800342bb  call    ?EnableSslSession@FTP_CONTROL_CHANNEL@@QEAAJH@Z; FTP_CONTROL_CHANNEL::EnableSslSession(int)
0x1800342c0  mov     ebx, eax
0x1800342c2  xor     r14d, r14d
0x1800342c5  test    eax, eax
0x1800342c7  js      loc_18003446E
0x1800342cd  mov     [r12+12B8h], esi
0x1800342d5  lea     rcx, [r12+1608h]
0x1800342dd  lea     rdx, aP; "P"
0x1800342e4  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800342ea  mov     ebx, eax
0x1800342ec  test    eax, eax
0x1800342ee  js      loc_18003446E
0x1800342f4  mov     rdi, [r12+60h]
0x1800342f9  lea     rbx, [rdi+0D0h]
0x180034300  mov     rcx, rbx
0x180034303  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180034309  mov     r8, [rdi+0C0h]
0x180034310  mov     edx, esi
0x180034312  lock xadd [r8], edx
0x180034317  add     edx, esi
0x180034319  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180034320  test    rcx, rcx
0x180034323  jz      short loc_18003432B
0x180034325  call    cs:__imp_WriteRefTraceLog
0x18003432b  mov     rdi, [rdi+0C0h]
0x180034332  mov     rcx, rbx
0x180034335  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003433b  cmp     dword ptr [rdi+74h], 2
0x18003433f  jnz     short loc_180034349
0x180034341  mov     [r12+1640h], esi
0x180034349  lea     rcx, [r12+818h]; this
0x180034351  call    ?EnableSsl@FTP_DATA_CHANNEL@@QEAAJXZ; FTP_DATA_CHANNEL::EnableSsl(void)
0x180034356  mov     ebx, eax
0x180034358  test    eax, eax
0x18003435a  js      loc_18003441B
0x180034360  jmp     short loc_180034365
0x180034362  xor     r14d, r14d
0x180034365  mov     rax, [r12]
0x180034369  mov     rcx, r12
0x18003436c  mov     rax, [rax]
0x18003436f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034374  mov     rdx, r12; struct FTP_SESSION_PUBLIC *
0x180034377  mov     rcx, r15; this
0x18003437a  call    ?AddToSessionList@FTP_SITE@@QEAAJPEAVFTP_SESSION_PUBLIC@@@Z; FTP_SITE::AddToSessionList(FTP_SESSION_PUBLIC *)
0x18003437f  mov     ebx, eax
0x180034381  test    eax, eax
0x180034383  jns     short loc_18003439A
0x180034385  mov     rax, [r12]
0x180034389  mov     rcx, r12
0x18003438c  mov     rax, [rax+8]
0x180034390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034395  jmp     loc_18003441B
0x18003439a  mov     [r12+15F4h], esi
0x1800343a2  mov     r9, [r12+438h]
0x1800343aa  lea     rax, [r9+140h]
0x1800343b1  add     r9, 1C0h
0x1800343b8  lea     r8, WideCharStr
0x1800343bf  mov     [rsp+160h+var_D8], r8
0x1800343c7  mov     [rsp+160h+var_E0], r14d
0x1800343cf  mov     [rsp+160h+var_E8], r14d
0x1800343d4  mov     [rsp+160h+var_F0], r14d
0x1800343d9  lea     rcx, aControlchannel_2; "ControlChannelOpened"
0x1800343e0  mov     [rsp+160h+var_110], rcx
0x1800343e5  mov     [rsp+160h+var_118], r14
0x1800343ea  mov     [rsp+160h+var_120], r14
0x1800343ef  mov     [rsp+160h+var_128], r8
0x1800343f4  mov     qword ptr [rsp+160h+Flags], r8
0x1800343f9  mov     qword ptr [rsp+160h+ServiceBufferSize], r8
0x1800343fe  mov     [rsp+160h+pServiceBuffer], rax
0x180034403  mov     r8, [r12+130h]
0x18003440b  mov     edx, 4
0x180034410  mov     rcx, r12
0x180034413  call    ?Log@FTP_SESSION@@QEAAJW4_LOG_ENTRY_TYPE@@PEBDPEBUsockaddr@@2PEBG33_K43331KJK3@Z; FTP_SESSION::Log(_LOG_ENTRY_TYPE,char const *,sockaddr const *,sockaddr const *,ushort const *,ushort const *,ushort const *,unsigned __int64,unsigned __int64,ushort const *,ushort const *,ushort const *,char const *,ulong,long,ulong,ushort const *)
0x180034418  mov     ebx, r14d
0x18003441b  test    rdi, rdi
0x18003441e  jz      short loc_18003445E
0x180034420  or      esi, 0FFFFFFFFh
0x180034423  lock xadd [rdi], esi
0x180034427  dec     esi
0x180034429  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180034430  test    rcx, rcx
0x180034433  jz      short loc_180034440
0x180034435  mov     r8, rdi
0x180034438  mov     edx, esi
0x18003443a  call    cs:__imp_WriteRefTraceLog
0x180034440  test    esi, esi
0x180034442  jnz     short loc_18003445E
0x180034444  mov     rcx, rdi; this
0x180034447  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003444c  nop
0x18003444d  mov     rdx, rdi
0x180034450  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180034457  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003445d  nop
0x18003445e  test    ebx, ebx
0x180034460  jns     short loc_18003448C
0x180034462  jmp     short loc_18003446E
0x180034464  mov     ebx, 80070008h
0x180034469  jmp     short loc_18003446E
0x18003446b  xor     r14d, r14d
0x18003446e  call    cs:__imp_GetTickCount
0x180034474  mov     [r12+810h], eax
0x18003447c  mov     [r12+438h], r14
0x180034484  mov     [r12+430h], r14
0x18003448c  mov     eax, ebx
0x18003448e  mov     rcx, [rbp+50h+var_40]
0x180034492  xor     rcx, rsp; StackCookie
0x180034495  call    __security_check_cookie
0x18003449a  mov     rbx, [rsp+160h+arg_18]
0x1800344a2  add     rsp, 130h
0x1800344a9  pop     r15
0x1800344ab  pop     r14
0x1800344ad  pop     r13
0x1800344af  pop     r12
0x1800344b1  pop     rdi
0x1800344b2  pop     rsi
  ... truncated ...
```
