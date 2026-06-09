# ThreadDispatch(ServerCall *)

- ea: `0x1800907c0`
- end: `0x180090f3b`
- name: `?ThreadDispatch@@YAXPEAVServerCall@@@Z`
- size: `1915`
- prototype: `void __fastcall(ServerCall *pServerCall)`
- caller_count: `6`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180090594`
- `0x1800919d0`
- `0x18009e0d8`
- `0x1800ecb90`
- `0x180169690`
- `0x1801b7b10`

## callees

- `0x180004d50`
- `0x180006250`
- `0x180006390`
- `0x18000712c`
- `0x180007200`
- `0x18000ee90`
- `0x180012dd4`
- `0x1800157dc`
- `0x1800158a0`
- `0x180015918`
- `0x1800188a0`
- `0x180038028`
- `0x18007340c`
- `0x18007b38c`
- `0x1800865f4`
- `0x18008a26c`
- `0x1800907c0`
- `0x1800921d0`
- `0x1800b4cb4`
- `0x1800ce300`
- `0x180155ae0`
- `0x18016e704`
- `0x1801999b0`
- `0x1802135dd`
- `0x180255010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180090bbd`
- `RPCRT4!UuidCreate` at `0x180090bbd`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x180090ef6`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x180090f07`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x180090ef6`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x180090f07`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x18009087e`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180090ed4`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x18009087e`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180090ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090ac8`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180090ce9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180090ce9`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180090aba`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180090aba`

## string_xrefs

- `0x180090960`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180090b27`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180090df7`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18009088c`: `onecore\com\combase\dcomrem\WorkOnBehalfTicket.hpp`
- `0x180090ee2`: `onecore\com\combase\dcomrem\WorkOnBehalfTicket.hpp`
- `0x180090b12`: `ThreadDispatch`
- `0x180090de2`: `ThreadDispatch`

## pseudocode

```c
void __fastcall ThreadDispatch(ServerCall *pServerCall)
{
  ServerCall *v1; // r14
  CMessageCall *(__fastcall *GetTransportCall)(ServerCall *); // rax
  void (__fastcall ***v3)(_QWORD); // rax
  void (__fastcall ***v4)(_QWORD); // rdi
  int v5; // eax
  unsigned __int64 ReservedForOle; // rbx
  HRESULT v7; // esi
  int v8; // eax
  _GUID *v9; // rax
  bool v10; // al
  const char *v11; // r9
  tagIPIDEntry *v12; // rax
  _GUID ipid; // xmm0
  _GUID *v14; // rax
  unsigned int Data1; // esi
  unsigned int v16; // r8d
  int v17; // r13d
  tagIPIDEntry *EntryPtr; // rax
  bool v19; // r12
  tagIPIDEntry *v20; // r15
  OXIDEntry *pOXIDEntry; // rsi
  void *hSxsActCtx; // rcx
  signed int LastError; // eax
  HRESULT v24; // esi
  bool v25; // zf
  CObjectContext *v26; // rax
  CObjectContext *ThreadDefaultContext; // rax
  __int128 v28; // xmm1
  tagIPIDEntry *v29; // rdx
  _OWORD *v30; // rcx
  __int64 v31; // r13
  __int64 v32; // r15
  int v33; // r12d
  int v34; // esi
  char v35; // r14
  HRESULT v36; // eax
  _QWORD *v37; // r8
  unsigned __int64 v38; // rcx
  tagIPIDEntry *v39; // r10
  OXIDEntry *v40; // rcx
  tagIPIDEntry *v41; // rax
  _GUID v42; // xmm0
  _GUID *p_ripid; // rax
  int v44; // eax
  __int64 v45; // rcx
  char tls; // [rsp+48h] [rbp-49h]
  char tls_1; // [rsp+49h] [rbp-48h]
  int tls_4; // [rsp+4Ch] [rbp-45h]
  int tls_4a; // [rsp+4Ch] [rbp-45h]
  HRESULT tls_4b; // [rsp+4Ch] [rbp-45h]
  unsigned __int64 ulActCtxCookie; // [rsp+50h] [rbp-41h] BYREF
  PushThreadWorkOnBehalfTicket pushThreadWorkOnBehalfTicket; // [rsp+58h] [rbp-39h] BYREF
  __int64 Buf2; // [rsp+60h] [rbp-31h] BYREF
  tagIPIDEntry *pIPIDEntry; // [rsp+68h] [rbp-29h] BYREF
  ServerCall *v55; // [rsp+70h] [rbp-21h]
  _GUID v56; // [rsp+78h] [rbp-19h] BYREF
  _GUID ripid; // [rsp+88h] [rbp-9h] BYREF
  _GUID v58; // [rsp+98h] [rbp+7h] BYREF
  char v59; // [rsp+A8h] [rbp+17h]
  IRCEntry *v60; // [rsp+B0h] [rbp+1Fh]
  void *retaddr; // [rsp+F0h] [rbp+5Fh]

  v1 = pServerCall;
  GetTransportCall = pServerCall->GetTransportCall;
  v55 = pServerCall;
  v3 = (void (__fastcall ***)(_QWORD))GetTransportCall(pServerCall);
  v4 = v3;
  if ( v3 )
    (**v3)(v3);
  ulActCtxCookie = (unsigned __int64)v4[36];
  Buf2 = *(_QWORD *)NtCurrentTeb()->WorkingOnBehalfTicket;
  if ( memcmp_0(&ulActCtxCookie, &NullWorkOnBehalfTicket, 8u) )
  {
    pushThreadWorkOnBehalfTicket = *(PushThreadWorkOnBehalfTicket *)NtCurrentTeb()->WorkingOnBehalfTicket;
    if ( memcmp_0(&pushThreadWorkOnBehalfTicket, &ulActCtxCookie, 8u) )
    {
      v5 = RtlSetThreadWorkOnBehalfTicket(&ulActCtxCookie);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          0x26u,
          "onecore\\com\\combase\\dcomrem\\WorkOnBehalfTicket.hpp",
          v5);
    }
  }
  ReservedForOle = (unsigned __int64)NtCurrentTeb()->ReservedForOle;
  ulActCtxCookie = ReservedForOle;
  if ( ReservedForOle )
  {
    v7 = 0;
  }
  else
  {
    v8 = COleTls::TLSAllocData((COleTls *)&ulActCtxCookie);
    ReservedForOle = ulActCtxCookie;
    v7 = v8;
    if ( v8 < 0 )
      v7 = -2147467258;
  }
  v10 = 0;
  if ( (*(_BYTE *)(ReservedForOle + 20) & 2) != 0 )
  {
    v9 = v1->GetDcomCausalityId(v1, &ripid);
    if ( !memcmp_0((const void *)(ReservedForOle + 208), v9, 0x10u) )
      v10 = 1;
  }
  v1->_isLogicalThreadCallback = v10;
  if ( v7 >= 0 )
  {
    if ( !v1->IsProcessLocal(v1) || (v7 = v1->CanDispatch(v1), v7 >= 0) )
    {
      pushThreadWorkOnBehalfTicket = 0;
      COleStaticMutexSem::Request(&gIPIDLock, "onecore\\com\\combase\\dcomrem\\channelb.cxx", 0x621u, v11);
      v12 = v1->_pIPIDEntry;
      if ( v12 )
      {
        ipid = v12->ipid;
        v14 = &v56;
        v56 = ipid;
      }
      else
      {
        v14 = v1->GetServerIpidFromTransport(v1, &ripid);
      }
      Data1 = v14->Data1;
      v16 = v14->Data1 & 0xFFFF03FF;
      if ( (unsigned __int64)v16 >> 16 >= CIPIDTable::_palloc._pgalloc._cPages
        || (unsigned __int16)v16 >= CIPIDTable::_palloc._pgalloc._cEntriesPerPage )
      {
        v19 = 0;
      }
      else
      {
        v17 = *(_DWORD *)&v14->Data2;
        tls_4 = *(_DWORD *)v14->Data4;
        LODWORD(ulActCtxCookie) = *(_DWORD *)&v14->Data4[4];
        EntryPtr = (tagIPIDEntry *)CPageAllocator::GetEntryPtr(&CIPIDTable::_palloc, v16);
        v19 = 0;
        pIPIDEntry = EntryPtr;
        v20 = EntryPtr;
        if ( EntryPtr && (tagIPIDEntry::GetFlags(EntryPtr) & 0x80u) == 0 )
        {
          if ( tagIPIDEntry::IsConnected(v20) )
          {
            if ( v20->ipid.Data1 == Data1
              && *(_DWORD *)&v20->ipid.Data2 == v17
              && *(_DWORD *)v20->ipid.Data4 == tls_4
              && *(_DWORD *)&v20->ipid.Data4[4] == (_DWORD)ulActCtxCookie )
            {
              if ( v20->pChnl && !v20->pOXIDEntry->_stopped._Storage._Value )
              {
                pOXIDEntry = v20->pOXIDEntry;
                *(_QWORD *)&ripid.Data1 = pOXIDEntry;
                OXIDEntry::IncRefCnt(pOXIDEntry);
                hSxsActCtx = v1->GetTransportCall(v1)->_hSxsActCtx;
                if ( hSxsActCtx != (void *)-1LL
                  && !ActivateActCtx(hSxsActCtx, (ULONG_PTR *)&pushThreadWorkOnBehalfTicket) )
                {
                  LastError = GetLastError();
                  tls_4a = LastError;
                  v24 = LastError;
                  if ( LastError > 0 )
                  {
                    v24 = (unsigned __int16)LastError | 0x80070000;
                    tls_4a = v24;
                  }
                  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                    || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
                  {
                    ComTraceMessage(
                      v24,
                      "onecore\\com\\combase\\dcomrem\\channelb.cxx",
                      "ThreadDispatch",
                      1585,
                      ERRORS,
                      L"ActivateActCtx failed: %!HRESULT!",
                      v24);
                  }
                  if ( v24 >= 0 )
                    tls_4a = -2147467259;
                  COleStaticMutexSem::Release(&gIPIDLock);
                  OXIDEntry::DecRefCnt(*(OXIDEntry **)&ripid.Data1);
                  v7 = tls_4a;
                  goto LABEL_83;
                }
                v25 = (pOXIDEntry->_info.dwFlags & 0x2000000) == 0;
                tls = 0;
                tls_1 = 0;
                ulActCtxCookie = 0;
                if ( v25 )
                {
                  if ( IsThreadInNTA() )
                  {
                    ThreadDefaultContext = GetThreadDefaultContext();
                    v26 = LeaveNTA(ThreadDefaultContext);
                    tls_1 = 1;
                    goto LABEL_48;
                  }
                }
                else if ( !IsThreadInNTA() )
                {
                  v26 = EnterNTA(g_pNTAEmptyCtx);
                  tls = 1;
LABEL_48:
                  ulActCtxCookie = (unsigned __int64)v26;
                }
                if ( (*(_BYTE *)(ReservedForOle + 20) & 2) == 0 )
                {
                  UuidCreate((UUID *)(ReservedForOle + 208));
                  *(_DWORD *)(ReservedForOle + 20) |= 2u;
                }
                v28 = *(_OWORD *)((char *)v4 + 452);
                v29 = pIPIDEntry;
                v59 = 0;
                v30 = NtCurrentTeb()->ReservedForOle;
                v58 = (_GUID)v30[13];
                v60 = (IRCEntry *)*((_QWORD *)v30 + 60);
                *((_QWORD *)v30 + 60) = &v58;
                v30[13] = v28;
                v31 = *(_QWORD *)(ReservedForOle + 136);
                v32 = *(_QWORD *)(ReservedForOle + 56);
                v33 = *(_DWORD *)(ReservedForOle + 88);
                v34 = *(_DWORD *)(ReservedForOle + 428);
                v35 = *(_BYTE *)(ReservedForOle + 20);
                v36 = ComInvokeWithLockAndIPID(v55, v29);
                *(_QWORD *)(ReservedForOle + 136) = v31;
                *(_QWORD *)(ReservedForOle + 56) = v32;
                *(_DWORD *)(ReservedForOle + 428) = v34;
                *(_DWORD *)(ReservedForOle + 88) = v33;
                tls_4b = v36;
                if ( (v35 & 1) != 0 )
                  *(_DWORD *)(ReservedForOle + 20) |= 1u;
                else
                  *(_DWORD *)(ReservedForOle + 20) &= ~1u;
                if ( tls )
                {
                  v37 = NtCurrentTeb()->ReservedForOle;
                  v38 = ulActCtxCookie;
                  v37[13] = ulActCtxCookie;
                  if ( v38 )
                  {
                    v37[12] = v38;
                    v37[15] = *(_QWORD *)(v38 + 152);
                    if ( *(CComApartment **)(v38 + 120) != gpNTAApartment )
                      *((_DWORD *)v37 + 5) &= ~0x800u;
                  }
                  else
                  {
                    v37[12] = g_pMTAEmptyCtx;
                    v37[15] = -1;
                    *((_DWORD *)v37 + 5) &= ~0x800u;
                  }
                }
                else if ( tls_1 )
                {
                  EnterNTA((CObjectContext *)ulActCtxCookie);
                }
                if ( pushThreadWorkOnBehalfTicket )
                  DeactivateActCtx(0, *(_QWORD *)&pushThreadWorkOnBehalfTicket);
                v39 = (tagIPIDEntry *)NtCurrentTeb()->ReservedForOle;
                pIPIDEntry = v39;
                if ( v59 )
                  TLSExplicitSetLogicalThreadId((COleTls *)&pIPIDEntry, &v58);
                else
                  *(_GUID *)v39[1].iid.Data4 = v58;
                v40 = *(OXIDEntry **)&ripid.Data1;
                v1 = v55;
                v39[3].pIRCEntry = v60;
                OXIDEntry::DecRefCnt(v40);
                v7 = tls_4b;
                goto LABEL_83;
              }
              v7 = -2147417848;
              if ( !v20->pStub )
                v7 = -2147467262;
              goto LABEL_74;
            }
          }
          else
          {
            v19 = v20->pStub == 0;
          }
        }
      }
      v7 = -2147417848;
      if ( v19 )
        v7 = -2147467262;
LABEL_74:
      v41 = v1->_pIPIDEntry;
      if ( v41 )
      {
        v42 = v41->ipid;
        p_ripid = &ripid;
        ripid = v42;
      }
      else
      {
        p_ripid = v1->GetServerIpidFromTransport(v1, &ripid);
      }
      ripid = *p_ripid;
      if ( CIPIDTable::IsIPIDRunDown(&ripid, 0) )
      {
        if ( gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
          ComTraceMessage(
            v7,
            "onecore\\com\\combase\\dcomrem\\channelb.cxx",
            "ThreadDispatch",
            1689,
            VERBOSE,
            L"Transforming result from %!HRESULT! to CO_E_PREMATURE_STUB_RUNDOWN",
            v7);
        v7 = -2147467211;
      }
      COleStaticMutexSem::Release(&gIPIDLock);
    }
  }
LABEL_83:
  CMessageCall::ServerFreeRequestMessage((CMessageCall *)v4);
  if ( (*((_BYTE *)v1 + 264) & 1) == 0 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD))(*v4)[19])(v4, (unsigned int)v7);
  if ( (*(_DWORD *)(ReservedForOle + 20) & 0x8000) != 0 && !*(_DWORD *)(ReservedForOle + 48) )
  {
    if ( *(_DWORD *)(ReservedForOle + 40) == 1 )
      CoVrfNotifyExtraUninit();
    CoUninitialize();
  }
  *(_QWORD *)&ripid.Data1 = *(_QWORD *)NtCurrentTeb()->WorkingOnBehalfTicket;
  if ( memcmp_0(&ripid, &Buf2, 8u) )
  {
    if ( !memcmp_0(&Buf2, &NullWorkOnBehalfTicket, 8u) )
    {
      if ( (int)RtlClearThreadWorkOnBehalfTicket() < 0 )
LABEL_96:
        MicrosoftTelemetryAssertTriggeredNoArgs(v45);
    }
    else
    {
      v44 = RtlSetThreadWorkOnBehalfTicket(&Buf2);
      if ( v44 < 0 )
      {
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          0x31u,
          "onecore\\com\\combase\\dcomrem\\WorkOnBehalfTicket.hpp",
          v44);
        if ( (int)RtlClearThreadWorkOnBehalfTicket() < 0 )
          goto LABEL_96;
      }
    }
  }
  (*v4)[1](v4);
}

```

## disassembly

```asm
0x1800907c0  mov     r11, rsp
0x1800907c3  push    rbp
0x1800907c4  push    rdi
0x1800907c5  lea     rbp, [r11-5Fh]
0x1800907c9  sub     rsp, 0D8h
0x1800907d0  mov     rax, cs:__security_cookie
0x1800907d7  xor     rax, rsp
0x1800907da  mov     [rbp+57h+var_30], rax
0x1800907de  mov     rax, [pServerCall]
0x1800907e1  mov     [r11+10h], rbx
0x1800907e5  mov     [r11+18h], rsi
0x1800907e9  mov     [r11-20h], r14
0x1800907ed  mov     r14, pServerCall
0x1800907f0  mov     rax, [rax+0F0h]
0x1800907f7  mov     [rbp+57h+var_78], pServerCall
0x1800907fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090800  mov     rdi, rax
0x180090803  test    rax, rax
0x180090806  jz      short loc_180090816
0x180090808  mov     rax, [rax]
0x18009080b  mov     pServerCall, rdi
0x18009080e  mov     rax, [rax]
0x180090811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090816  mov     rax, [rdi+120h]
0x18009081d  lea     rdx, ?NullWorkOnBehalfTicket@@3U_RTL_WORK_ON_BEHALF_TICKET@@B; Buf2
0x180090824  mov     [rbp+57h+ulActCtxCookie], rax
0x180090828  mov     r8d, 8; Size
0x18009082e  mov     rax, gs:30h
0x180090837  mov     pServerCall, [rax+2B8h]
0x18009083e  mov     [rbp+57h+Buf2], pServerCall
0x180090842  lea     pServerCall, [rbp+57h+ulActCtxCookie]; Buf1
0x180090846  call    memcmp_0
0x18009084b  test    eax, eax
0x18009084d  jz      short loc_1800908A0
0x18009084f  mov     rax, gs:30h
0x180090858  lea     rdx, [rbp+57h+ulActCtxCookie]; Buf2
0x18009085c  mov     r8d, 8; Size
0x180090862  mov     pServerCall, [rax+2B8h]
0x180090869  mov     qword ptr [rbp+57h+pushThreadWorkOnBehalfTicket.m_savedTicket.ThreadId], pServerCall
0x18009086d  lea     pServerCall, [rbp+57h+pushThreadWorkOnBehalfTicket]; Buf1
0x180090871  call    memcmp_0
0x180090876  test    eax, eax
0x180090878  jz      short loc_1800908A0
0x18009087a  lea     pServerCall, [rbp+57h+ulActCtxCookie]
0x18009087e  call    cs:__imp_RtlSetThreadWorkOnBehalfTicket
0x180090884  test    eax, eax
0x180090886  jns     short loc_1800908A0
0x180090888  mov     pServerCall, [rbp+5Fh]; callerReturnAddress
0x18009088c  lea     r8, aOnecoreComComb_48; "onecore\\com\\combase\\dcomrem\\WorkOnB"...
0x180090893  mov     r9d, eax; status
0x180090896  mov     edx, 26h ; '&'; lineNumber
0x18009089b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800908a0  mov     rbx, gs:30h
0x1800908a9  mov     rbx, [rbx+1758h]
0x1800908b0  mov     [rbp+57h+ulActCtxCookie], rbx
0x1800908b4  test    rbx, rbx
0x1800908b7  jz      short loc_1800908BD
0x1800908b9  xor     esi, esi
0x1800908bb  jmp     short loc_1800908D6
0x1800908bd  lea     pServerCall, [rbp+57h+ulActCtxCookie]; this
0x1800908c1  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x1800908c6  mov     rbx, [rbp+57h+ulActCtxCookie]
0x1800908ca  mov     esi, eax
0x1800908cc  test    esi, esi
0x1800908ce  mov     eax, 80004006h
0x1800908d3  cmovs   esi, eax
0x1800908d6  test    byte ptr [rbx+14h], 2
0x1800908da  jz      short loc_18009090F
0x1800908dc  mov     rax, [r14]
0x1800908df  lea     rdx, [rbp+57h+ripid]
0x1800908e3  mov     pServerCall, r14
0x1800908e6  mov     rax, [rax+98h]
0x1800908ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800908f2  lea     pServerCall, [rbx+0D0h]; Buf1
0x1800908f9  mov     r8d, 10h; Size
0x1800908ff  mov     rdx, rax; Buf2
0x180090902  call    memcmp_0
0x180090907  test    eax, eax
0x180090909  jnz     short loc_18009090F
0x18009090b  mov     al, 1
0x18009090d  jmp     short loc_180090911
0x18009090f  xor     al, al
0x180090911  mov     [r14+130h], al
0x180090918  test    esi, esi
0x18009091a  js      loc_180090E2E
0x180090920  mov     rax, [r14]
0x180090923  mov     pServerCall, r14
0x180090926  mov     rax, [rax+0D0h]
0x18009092d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090932  test    al, al
0x180090934  jz      short loc_180090952
0x180090936  mov     rax, [r14]
0x180090939  mov     pServerCall, r14
0x18009093c  mov     rax, [rax+108h]
0x180090943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090948  mov     esi, eax
0x18009094a  test    eax, eax
0x18009094c  js      loc_180090E2E
0x180090952  mov     r8d, 621h; dwLine
0x180090958  mov     qword ptr [rbp+57h+pushThreadWorkOnBehalfTicket.m_savedTicket.ThreadId], 0
0x180090960  lea     rdx, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180090967  lea     pServerCall, ?gIPIDLock@@3VCOleStaticMutexSem@@A; this
0x18009096e  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180090973  mov     rax, [r14+0A8h]
0x18009097a  test    rax, rax
0x18009097d  jz      short loc_18009098D
0x18009097f  movups  xmm0, xmmword ptr [rax+38h]
0x180090983  lea     rax, [rbp+57h+var_70]
0x180090987  movups  [rbp+57h+var_70], xmm0
0x18009098b  jmp     short loc_1800909A3
0x18009098d  mov     rax, [r14]
0x180090990  lea     rdx, [rbp+57h+ripid]
0x180090994  mov     pServerCall, r14
0x180090997  mov     rax, [rax+128h]
0x18009099e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800909a3  mov     esi, [rax]
0x1800909a5  mov     ecx, esi
0x1800909a7  and     ecx, 0FFFF03FFh
0x1800909ad  mov     [rsp+0E0h+arg_18], r12
0x1800909b5  mov     r8d, ecx
0x1800909b8  shr     pServerCall, 10h
0x1800909bc  cmp     pServerCall, cs:?_palloc@CIPIDTable@@0VCPageAllocator@@A._pgalloc._cPages; CPageAllocator CIPIDTable::_palloc ...
0x1800909c3  mov     [rsp+0D0h], r13
0x1800909cb  mov     [rsp+0E0h+var_20], r15
0x1800909d3  jnb     loc_180090D63
0x1800909d9  cmp     r8w, cs:?_palloc@CIPIDTable@@0VCPageAllocator@@A._pgalloc._cEntriesPerPage; CPageAllocator CIPIDTable::_palloc ...
0x1800909e1  jnb     loc_180090D63
0x1800909e7  mov     ecx, [rax+8]
0x1800909ea  mov     edx, r8d; iEntry
0x1800909ed  mov     r13d, [rax+4]
0x1800909f1  mov     eax, [rax+0Ch]
0x1800909f4  mov     dword ptr [rbp+57h+tls._pData+4], ecx
0x1800909f7  lea     pServerCall, ?_palloc@CIPIDTable@@0VCPageAllocator@@A; this
0x1800909fe  mov     dword ptr [rbp+57h+ulActCtxCookie], eax
0x180090a01  call    ?GetEntryPtr@CPageAllocator@@QEAAPEAUtagPageEntry@@K@Z; CPageAllocator::GetEntryPtr(ulong)
0x180090a06  xor     r12b, r12b
0x180090a09  mov     [rbp+57h+pIPIDEntry], rax
0x180090a0d  mov     r15, rax
0x180090a10  test    rax, rax
0x180090a13  jz      loc_180090D66
0x180090a19  mov     pServerCall, rax; this
0x180090a1c  call    ?GetFlags@tagIPIDEntry@@QEBAKXZ; tagIPIDEntry::GetFlags(void)
0x180090a21  test    al, al
0x180090a23  js      loc_180090D66
0x180090a29  mov     pServerCall, r15; this
0x180090a2c  call    ?IsConnected@tagIPIDEntry@@QEBA_NXZ; tagIPIDEntry::IsConnected(void)
0x180090a31  test    al, al
0x180090a33  jz      loc_180090D58
0x180090a39  cmp     [r15+38h], esi
0x180090a3d  jnz     loc_180090D66
0x180090a43  cmp     [r15+3Ch], r13d
0x180090a47  jnz     loc_180090D66
0x180090a4d  mov     eax, dword ptr [rbp+57h+tls._pData+4]
0x180090a50  cmp     [r15+40h], eax
0x180090a54  jnz     loc_180090D66
0x180090a5a  mov     eax, dword ptr [rbp+57h+ulActCtxCookie]
0x180090a5d  cmp     [r15+44h], eax
0x180090a61  jnz     loc_180090D66
0x180090a67  cmp     qword ptr [r15+58h], 0
0x180090a6c  jz      loc_180090D44
0x180090a72  mov     rax, [r15+30h]
0x180090a76  movzx   ecx, byte ptr [rax+0D9h]
0x180090a7d  nop
0x180090a7e  test    cl, cl
0x180090a80  jnz     loc_180090D44
0x180090a86  mov     rsi, [r15+30h]
0x180090a8a  mov     pServerCall, rsi; this
0x180090a8d  mov     qword ptr [rbp+57h+ripid.Data1], rsi
0x180090a91  call    ?IncRefCnt@OXIDEntry@@QEAAKXZ; OXIDEntry::IncRefCnt(void)
0x180090a96  mov     rax, [r14]
0x180090a99  mov     pServerCall, r14
0x180090a9c  mov     rax, [rax+0F0h]
0x180090aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090aa8  mov     pServerCall, [rax+30h]; hActCtx
0x180090aac  cmp     pServerCall, 0FFFFFFFFFFFFFFFFh
0x180090ab0  jz      loc_180090B5E
0x180090ab6  lea     rdx, [rbp+57h+pushThreadWorkOnBehalfTicket]; lpCookie
0x180090aba  call    cs:__imp_ActivateActCtx
0x180090ac0  test    eax, eax
0x180090ac2  jnz     loc_180090B5E
0x180090ac8  call    cs:__imp_GetLastError
0x180090ace  mov     dword ptr [rbp+57h+tls._pData+4], eax
0x180090ad1  mov     esi, eax
0x180090ad3  test    eax, eax
0x180090ad5  jle     short loc_180090AE3
0x180090ad7  movzx   esi, ax
0x180090ada  or      esi, 80070000h
0x180090ae0  mov     dword ptr [rbp+57h+tls._pData+4], esi
0x180090ae3  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180090ae9  test    eax, eax
0x180090aeb  jnz     short loc_180090B02
0x180090aed  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180090af3  jz      short loc_180090B35
0x180090af5  mov     rax, cs:WPP_GLOBAL_Control
0x180090afc  test    byte ptr [rax+1Ch], 1
0x180090b00  jz      short loc_180090B35
0x180090b02  lea     rax, aActivateactctx; "ActivateActCtx failed: %!HRESULT!"
0x180090b09  mov     [rsp+30h], esi
0x180090b0d  mov     [rsp+0E0h+format], rax; format
0x180090b12  lea     r8, aThreaddispatch; "ThreadDispatch"
0x180090b19  mov     r9d, 631h; line
0x180090b1f  mov     [rsp+0E0h+level], 0; level
0x180090b27  lea     rdx, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180090b2e  mov     ecx, esi; hr
0x180090b30  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180090b35  test    esi, esi
0x180090b37  js      short loc_180090B41
0x180090b39  mov     eax, 80004005h
0x180090b3e  mov     dword ptr [rbp+57h+tls._pData+4], eax
0x180090b41  lea     pServerCall, ?gIPIDLock@@3VCOleStaticMutexSem@@A; this
0x180090b48  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180090b4d  mov     pServerCall, qword ptr [rbp+57h+ripid.Data1]; this
0x180090b51  call    ?DecRefCnt@OXIDEntry@@QEAAKXZ; OXIDEntry::DecRefCnt(void)
0x180090b56  mov     esi, dword ptr [rbp+57h+tls._pData+4]
0x180090b59  jmp     loc_180090E16
0x180090b5e  test    dword ptr [rsi+50h], 2000000h
0x180090b65  mov     byte ptr [rbp+57h+tls._pData], r12b
0x180090b69  mov     byte ptr [rbp+57h+tls._pData+1], r12b
0x180090b6d  mov     [rbp+57h+ulActCtxCookie], 0
0x180090b75  jz      short loc_180090B92
0x180090b77  call    ?IsThreadInNTA@@YAHXZ; IsThreadInNTA(void)
0x180090b7c  test    eax, eax
0x180090b7e  jnz     short loc_180090BB0
0x180090b80  mov     pServerCall, cs:?g_pNTAEmptyCtx@@3PEAVCObjectContext@@EA; pChangeCtx
0x180090b87  call    ?EnterNTA@@YAPEAVCObjectContext@@PEAV1@@Z; EnterNTA(CObjectContext *)
0x180090b8c  mov     byte ptr [rbp+57h+tls._pData], 1
0x180090b90  jmp     short loc_180090BAC
0x180090b92  call    ?IsThreadInNTA@@YAHXZ; IsThreadInNTA(void)
0x180090b97  test    eax, eax
0x180090b99  jz      short loc_180090BB0
0x180090b9b  call    ?GetThreadDefaultContext@@YAPEAVCObjectContext@@XZ; GetThreadDefaultContext(void)
0x180090ba0  mov     pServerCall, rax; pChangeCtx
0x180090ba3  call    ?LeaveNTA@@YAPEAVCObjectContext@@PEAV1@@Z; LeaveNTA(CObjectContext *)
0x180090ba8  mov     byte ptr [rbp+57h+tls._pData+1], 1
0x180090bac  mov     [rbp+57h+ulActCtxCookie], rax
0x180090bb0  test    byte ptr [rbx+14h], 2
0x180090bb4  jnz     short loc_180090BC7
0x180090bb6  lea     pServerCall, [rbx+0D0h]; Uuid
0x180090bbd  call    cs:__imp_UuidCreate
0x180090bc3  or      dword ptr [rbx+14h], 2
0x180090bc7  movups  xmm1, xmmword ptr [rdi+1C4h]
0x180090bce  mov     rdx, [rbp+57h+pIPIDEntry]; pIPIDEntry
0x180090bd2  mov     [rbp+57h+var_40], r12b
0x180090bd6  mov     rax, gs:30h
0x180090bdf  mov     pServerCall, [rax+1758h]
0x180090be6  movups  xmm0, xmmword ptr [pServerCall+0D0h]
0x180090bed  movups  [rbp+57h+var_50], xmm0
0x180090bf1  mov     rax, [pServerCall+1E0h]
0x180090bf8  mov     [rbp+57h+var_38], rax
0x180090bfc  lea     rax, [rbp+57h+var_50]
0x180090c00  mov     [pServerCall+1E0h], rax
0x180090c07  movups  xmmword ptr [pServerCall+0D0h], xmm1
0x180090c0e  mov     pServerCall, [rbp+57h+var_78]; pServerCall
0x180090c12  mov     r13, [rbx+88h]
0x180090c19  mov     r15, [rbx+38h]
0x180090c1d  mov     r12d, [rbx+58h]
0x180090c21  mov     esi, [rbx+1ACh]
0x180090c27  movzx   r14d, byte ptr [rbx+14h]
0x180090c2c  call    ?ComInvokeWithLockAndIPID@@YAJPEAVServerCall@@PEAUtagIPIDEntry@@@Z; ComInvokeWithLockAndIPID(ServerCall *,tagIPIDEntry *)
0x180090c31  mov     [rbx+88h], r13
0x180090c38  mov     [rbx+38h], r15
0x180090c3c  mov     [rbx+1ACh], esi
0x180090c42  mov     [rbx+58h], r12d
0x180090c46  mov     dword ptr [rbp+57h+tls._pData+4], eax
0x180090c49  test    r14b, 1
0x180090c4d  jz      short loc_180090C55
0x180090c4f  or      dword ptr [rbx+14h], 1
0x180090c53  jmp     short loc_180090C59
0x180090c55  and     dword ptr [rbx+14h], 0FFFFFFFEh
0x180090c59  cmp     byte ptr [rbp+57h+tls._pData], 0
0x180090c5d  jz      short loc_180090CCF
0x180090c5f  mov     rax, gs:30h
0x180090c68  mov     r8, [rax+1758h]
0x180090c6f  mov     rax, gs:30h
0x180090c78  mov     pServerCall, [rbp+57h+ulActCtxCookie]
0x180090c7c  mov     rdx, [rax+1758h]
0x180090c83  mov     [rdx+68h], pServerCall
0x180090c87  test    pServerCall, pServerCall
0x180090c8a  jz      short loc_180090CB2
0x180090c8c  mov     [rdx+60h], pServerCall
0x180090c90  mov     rax, [pServerCall+98h]
0x180090c97  mov     [rdx+78h], rax
0x180090c9b  mov     rax, cs:?gpNTAApartment@@3PEAVCComApartment@@EA; CComApartment * gpNTAApartment
0x180090ca2  cmp     [pServerCall+78h], rax
0x180090ca6  jz      short loc_180090CDE
0x180090ca8  and     dword ptr [r8+14h], 0FFFFF7FFh
0x180090cb0  jmp     short loc_180090CDE
0x180090cb2  mov     rax, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x180090cb9  mov     [rdx+60h], rax
0x180090cbd  mov     qword ptr [rdx+78h], 0FFFFFFFFFFFFFFFFh
0x180090cc5  and     dword ptr [r8+14h], 0FFFFF7FFh
0x180090ccd  jmp     short loc_180090CDE
0x180090ccf  cmp     byte ptr [rbp+57h+tls._pData+1], 0
0x180090cd3  jz      short loc_180090CDE
0x180090cd5  mov     pServerCall, [rbp+57h+ulActCtxCookie]; pChangeCtx
0x180090cd9  call    ?EnterNTA@@YAPEAVCObjectContext@@PEAV1@@Z; EnterNTA(CObjectContext *)
0x180090cde  mov     rdx, qword ptr [rbp+57h+pushThreadWorkOnBehalfTicket.m_savedTicket.ThreadId]; ulCookie
0x180090ce2  test    rdx, rdx
0x180090ce5  jz      short loc_180090CEF
0x180090ce7  xor     ecx, ecx; dwFlags
  ... truncated ...
```
