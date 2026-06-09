# RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(void)

- ea: `0x180012238`
- end: `0x18001291d`
- name: `?ResetStateOnSessionReconnect@RdsDWMDirectUpdateProcessor@@IEAAXXZ`
- size: `1765`
- prototype: `void __fastcall(RdsDWMDirectUpdateProcessor *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000fb78`
- `0x18000fcb8`
- `0x1800108a8`

## callees

- `0x1800010f8`
- `0x180001188`
- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x180005f6c`
- `0x18000f068`
- `0x18000f08c`
- `0x180011c84`
- `0x180012238`
- `0x180012924`
- `0x180013444`
- `0x1800138a8`
- `0x1800157dc`
- `0x1800176dc`
- `0x180018658`
- `0x1800196a4`
- `0x180019d58`
- `0x18002c010`

## string_xrefs

- `0x1800123b4`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180012497`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18001256c`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800125df`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18001227c`: `Reseting update processor state on reconnect for session.`
- `0x1800123a5`: `RdpRemoteAppGfxRedirectionHandler::CreateInstance failed`
- `0x18001255d`: `RdpRemoteAppGfxRedirectionHandler::CreateInstance failed`
- `0x180012729`: `RdpRemoteAppAuxRedirectionHandler::CreateInstance failed`

## pseudocode

```c
void __fastcall RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(
        RdsDWMDirectUpdateProcessor *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // esi
  int refreshed; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  struct _GUID v13; // xmm0
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  struct RdpRemoteAppGfxRedirectionHandler *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  struct _GUID v22; // xmm0
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  char *v27; // rdx
  const unsigned __int16 **v28; // rax
  struct RdpRemoteAppGfxRedirectionHandler *v29; // rbx
  int v30; // eax
  __int64 v31; // rdx
  struct RdpRemoteAppAuxRedirectionHandler *v32; // rbx
  __int64 v33; // rcx
  unsigned __int16 *v34; // r8
  __int64 v35; // r9
  struct _GUID *v36; // rdx
  const char **v37; // [rsp+30h] [rbp-50h]
  const char **v38; // [rsp+40h] [rbp-40h]
  const unsigned __int16 **v39; // [rsp+48h] [rbp-38h]
  struct RdpRemoteAppGfxRedirectionHandler *v40; // [rsp+50h] [rbp-30h] BYREF
  const char *v41; // [rsp+58h] [rbp-28h] BYREF
  const char *v42; // [rsp+60h] [rbp-20h] BYREF
  const char *v43; // [rsp+68h] [rbp-18h] BYREF
  struct _GUID v44; // [rsp+70h] [rbp-10h] BYREF
  const char *v45; // [rsp+C0h] [rbp+40h] BYREF
  int v46; // [rsp+C8h] [rbp+48h] BYREF
  struct RdpRemoteAppGfxRedirectionHandler *v47; // [rsp+D0h] [rbp+50h] BYREF
  struct RdpRemoteAppAuxRedirectionHandler *v48; // [rsp+D8h] [rbp+58h] BYREF

  v5 = 0;
  if ( !*((_DWORD *)this + 28) )
    goto LABEL_54;
  LODWORD(v45) = 0;
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v46 = *((_DWORD *)this + 27);
    v47 = (struct RdpRemoteAppGfxRedirectionHandler *)"Reseting update processor state on reconnect for session.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_18003B8BD,
      a3,
      a4,
      (const unsigned __int16 **)&v47,
      (__int64)&v46);
  }
  *((_DWORD *)this + 41) = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8);
  refreshed = RdsDWMDirectUpdateProcessor::RefreshWTSConnectionProperties(this);
  v5 = refreshed;
  if ( refreshed >= 0 )
  {
    *((_QWORD *)this + 17) = RDSDWMDirectTraceLogging::GetCurrentMsTime(*((RDSDWMDirectTraceLogging **)this + 16), v7);
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
    *((_DWORD *)this + 40) = 0;
  }
  else if ( (unsigned int)dword_180044008 > 3 )
  {
    v46 = refreshed;
    v47 = (struct RdpRemoteAppGfxRedirectionHandler *)"ResetStateOnSessionReconnect";
    v48 = (struct RdpRemoteAppAuxRedirectionHandler *)"Failed to refresh the WTS connection properties";
    v40 = (struct RdpRemoteAppGfxRedirectionHandler *)"HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)word_18003B882,
      v8,
      v9,
      (const unsigned __int16 **)&v40,
      (const unsigned __int16 **)&v48,
      (__int64)&v46,
      (const unsigned __int16 **)&v47);
  }
  if ( (unsigned int)(*((_DWORD *)this + 29) - 2) <= 1 )
  {
    v47 = 0;
    v22 = *(struct _GUID *)((char *)this + 92);
    v40 = 0;
    v48 = 0;
    v44 = v22;
    v5 = RdpRemoteAppGfxRedirectionHandler::CreateInstance(&v44, &v40, v8, v9);
    if ( v5 >= 0 )
    {
      v29 = v40;
      v30 = RdpRemoteAppGfxRedirectionHandler::OnSessionConnect((LARGE_INTEGER *)v40, v23, v25, v26);
      if ( v30 < 0 )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          LODWORD(v45) = 354;
          v42 = "OnSessionConnect failed. Container redirection mode is not enabled";
          *(_QWORD *)&v44.Data1 = "ResetStateOnSessionReconnect";
          v43 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
          v46 = v30;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)v30,
            (__int64)word_18003B782,
            v25,
            v26,
            (const unsigned __int16 **)&v42,
            (__int64)&v46,
            (const unsigned __int16 **)&v43,
            (__int64)&v45,
            (const unsigned __int16 **)&v44);
        }
      }
      else
      {
        v5 = (**((__int64 (__fastcall ***)(__int64, GUID *, struct RdpRemoteAppGfxRedirectionHandler **))v29 + 6))(
               (__int64)v29 + 48,
               &IID_IRdsDWMDirectDriverIO,
               &v47);
        if ( v5 < 0 )
        {
          if ( (unsigned int)dword_180044008 <= 2 )
            goto LABEL_53;
          LODWORD(v45) = 346;
          *(_QWORD *)&v44.Data1 = "Failed to query I/O processor interface";
          v43 = "ResetStateOnSessionReconnect";
          v41 = "Error HResult failed";
          v27 = (char *)qword_18003B7E8;
          v42 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
          v39 = (const unsigned __int16 **)&v44;
          v38 = &v43;
          v37 = &v42;
          v28 = (const unsigned __int16 **)&v41;
          goto LABEL_27;
        }
        if ( v47 != *((struct RdpRemoteAppGfxRedirectionHandler **)this + 5) )
        {
          TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 40);
          *((_QWORD *)this + 5) = v47;
          TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 40);
        }
        if ( v29 != *((struct RdpRemoteAppGfxRedirectionHandler **)this + 6) )
        {
          TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease((char *)this + 48);
          *((_QWORD *)this + 6) = v29;
          TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef((char *)this + 48);
        }
        if ( (unsigned int)dword_180044008 > 4 )
        {
          v45 = "Container redirection mode is successfully enabled";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v24,
            (__int64)&byte_18003B7C7,
            v25,
            v26,
            (const unsigned __int16 **)&v45);
        }
      }
      v44 = *(struct _GUID *)((char *)this + 92);
      v5 = RdpRemoteAppAuxRedirectionHandler::CreateInstance(&v44, &v48, v25, v26);
      if ( v5 >= 0 )
      {
        v32 = v48;
        if ( (int)RdpRemoteAppAuxRedirectionHandler::OnSessionConnect(v48, v31, v25, v26) < 0 )
        {
          if ( (unsigned int)dword_180044008 > 2 )
          {
            LODWORD(v45) = 373;
            *(_QWORD *)&v44.Data1 = "ResetStateOnSessionReconnect";
            v43 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
            v42 = "OnSessionConnect failed. Container auxiliary redirection channel is not enabled";
            v46 = v5;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v33,
              (__int64)&byte_18003B6CF,
              (__int64)v34,
              v35,
              (const unsigned __int16 **)&v42,
              (__int64)&v46,
              (const unsigned __int16 **)&v43,
              (__int64)&v45,
              (const unsigned __int16 **)&v44);
          }
        }
        else
        {
          if ( v32 != *((struct RdpRemoteAppAuxRedirectionHandler **)this + 7) )
          {
            TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease((char *)this + 56);
            *((_QWORD *)this + 7) = v32;
            TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef((char *)this + 56);
          }
          if ( (unsigned int)dword_180044008 > 4 )
          {
            v45 = "Container auxiliary redirection channel is successfully enabled";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v33,
              (__int64)&dword_18003B714,
              (__int64)v34,
              v35,
              (const unsigned __int16 **)&v45);
          }
        }
        v36 = (struct _GUID *)L"VAILModeDisabledByClient";
        if ( *((_DWORD *)this + 29) != 2 )
          v36 = (struct _GUID *)&stru_180031568;
        RDSDWMDirectTraceLogging::LogVAILModeState((RdsDWMDirectUpdateProcessor *)((char *)this + 92), v36, v34);
        v5 = 0;
        goto LABEL_53;
      }
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v43 = "ResetStateOnSessionReconnect";
        *(_QWORD *)&v44.Data1 = "RdpRemoteAppAuxRedirectionHandler::CreateInstance failed";
        v27 = byte_18003B735;
        LODWORD(v45) = 364;
        v41 = "Error HResult failed";
        v39 = (const unsigned __int16 **)&v44;
        v38 = &v43;
        v37 = &v42;
        v28 = (const unsigned __int16 **)&v41;
        v42 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        goto LABEL_27;
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v41 = "ResetStateOnSessionReconnect";
      v42 = "RdpRemoteAppGfxRedirectionHandler::CreateInstance failed";
      LODWORD(v45) = 338;
      *(_QWORD *)&v44.Data1 = "Error HResult failed";
      v27 = byte_18003B835;
      v43 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v39 = (const unsigned __int16 **)&v42;
      v38 = &v41;
      v37 = &v43;
      v28 = (const unsigned __int16 **)&v44;
LABEL_27:
      v46 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (__int64)v27,
        v25,
        v26,
        v28,
        (__int64)&v46,
        (const unsigned __int16 **)v37,
        (__int64)&v45,
        (const unsigned __int16 **)v38,
        v39);
    }
LABEL_53:
    TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v48);
    TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v40);
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v47);
    goto LABEL_54;
  }
  if ( (int)RdpRemoteAppGfxRedirectionHandler::GetChannelRegistrySetting((int *)&v45) >= 0 && (_DWORD)v45 )
  {
    v13 = *(struct _GUID *)((char *)this + 92);
    v47 = 0;
    v44 = v13;
    v5 = RdpRemoteAppGfxRedirectionHandler::CreateInstance(&v44, &v47, v11, v12);
    if ( v5 >= 0 )
    {
      v18 = v47;
      if ( (int)RdpRemoteAppGfxRedirectionHandler::OnSessionConnect((LARGE_INTEGER *)v47, v14, v16, v17) < 0 )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v48 = (struct RdpRemoteAppAuxRedirectionHandler *)"ResetStateOnSessionReconnect";
          v41 = "OnSessionConnect failed. Container graphics redirection channel is not enabled";
          LODWORD(v45) = 407;
          v42 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
          v46 = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v19,
            (__int64)&dword_18003B61C,
            v20,
            v21,
            (const unsigned __int16 **)&v41,
            (__int64)&v46,
            (const unsigned __int16 **)&v42,
            (__int64)&v45,
            (const unsigned __int16 **)&v48);
        }
      }
      else
      {
        if ( v18 != *((struct RdpRemoteAppGfxRedirectionHandler **)this + 6) )
        {
          TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease((char *)this + 48);
          *((_QWORD *)this + 6) = v18;
          TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef((char *)this + 48);
        }
        if ( (unsigned int)dword_180044008 > 4 )
        {
          v45 = "Container redirection channel is enabled with no graphics redirection";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v19,
            (__int64)byte_18003B661,
            v20,
            v21,
            (const unsigned __int16 **)&v45);
        }
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v40 = (struct RdpRemoteAppGfxRedirectionHandler *)"ResetStateOnSessionReconnect";
      v48 = (struct RdpRemoteAppAuxRedirectionHandler *)"RdpRemoteAppGfxRedirectionHandler::CreateInstance failed";
      LODWORD(v45) = 398;
      v42 = "Error HResult failed";
      v41 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v46 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v15,
        (__int64)word_18003B682,
        v16,
        v17,
        (const unsigned __int16 **)&v42,
        (__int64)&v46,
        (const unsigned __int16 **)&v41,
        (__int64)&v45,
        (const unsigned __int16 **)&v40,
        (const unsigned __int16 **)&v48);
    }
    TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v47);
  }
  else if ( (unsigned int)dword_180044008 > 4 )
  {
    v45 = "Container redirection mode is not enabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (__int64)byte_18003B5FB,
      v11,
      v12,
      (const unsigned __int16 **)&v45);
  }
LABEL_54:
  if ( *((_DWORD *)this + 28) )
  {
    if ( v5 >= 0 )
      *((_DWORD *)this + 28) = 0;
  }
}

```

## disassembly

```asm
0x180012238  push    rbp
0x18001223a  push    rbx
0x18001223b  push    rsi
0x18001223c  push    rdi
0x18001223d  push    r12
0x18001223f  push    r14
0x180012241  push    r15
0x180012243  mov     rbp, rsp
0x180012246  sub     rsp, 80h
0x18001224d  xor     r12d, r12d
0x180012250  mov     rdi, rcx
0x180012253  mov     esi, r12d
0x180012256  cmp     [rcx+70h], r12d
0x18001225a  jz      loc_1800128FD
0x180012260  mov     eax, cs:dword_180044008
0x180012266  mov     dword ptr [rbp+arg_0], r12d
0x18001226a  cmp     eax, 4
0x18001226d  jbe     short loc_18001229E
0x18001226f  mov     eax, [rcx+6Ch]
0x180012272  lea     rdx, byte_18003B8BD
0x180012279  mov     [rbp+arg_8], eax
0x18001227c  lea     rax, aResetingUpdate; "Reseting update processor state on reco"...
0x180012283  mov     [rbp+arg_10], rax
0x180012287  lea     rax, [rbp+arg_8]
0x18001228b  mov     [rsp+80h+var_58], rax
0x180012290  lea     rax, [rbp+arg_10]
0x180012294  mov     [rsp+80h+var_60], rax
0x180012299  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001229e  lea     rcx, [rdi+8]
0x1800122a2  mov     [rdi+0A4h], r12d
0x1800122a9  mov     rax, [rcx]
0x1800122ac  mov     rax, [rax+18h]
0x1800122b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b5  mov     rcx, rdi; this
0x1800122b8  call    ?RefreshWTSConnectionProperties@RdsDWMDirectUpdateProcessor@@IEAAJXZ; RdsDWMDirectUpdateProcessor::RefreshWTSConnectionProperties(void)
0x1800122bd  lea     r14, aResetstateonse; "ResetStateOnSessionReconnect"
0x1800122c4  mov     esi, eax
0x1800122c6  test    eax, eax
0x1800122c8  jns     short loc_180012324
0x1800122ca  mov     ecx, cs:dword_180044008
0x1800122d0  cmp     ecx, 3
0x1800122d3  jbe     short loc_18001234C
0x1800122d5  mov     [rbp+arg_8], eax
0x1800122d8  lea     rdx, word_18003B882
0x1800122df  lea     rax, aFailedToRefres; "Failed to refresh the WTS connection pr"...
0x1800122e6  mov     [rbp+arg_10], r14
0x1800122ea  mov     [rbp+arg_18], rax
0x1800122ee  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800122f5  mov     [rbp+var_30], rax
0x1800122f9  lea     rax, [rbp+arg_10]
0x1800122fd  mov     [rsp+80h+var_48], rax
0x180012302  lea     rax, [rbp+arg_8]
0x180012306  mov     [rsp+80h+var_50], rax
0x18001230b  lea     rax, [rbp+arg_18]
0x18001230f  mov     [rsp+80h+var_58], rax
0x180012314  lea     rax, [rbp+var_30]
0x180012318  mov     [rsp+80h+var_60], rax
0x18001231d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180012322  jmp     short loc_18001234C
0x180012324  mov     rcx, [rdi+80h]; this
0x18001232b  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x180012330  mov     [rdi+88h], rax
0x180012337  mov     [rdi+90h], r12
0x18001233e  mov     [rdi+98h], r12
0x180012345  mov     [rdi+0A0h], r12d
0x18001234c  mov     eax, [rdi+74h]
0x18001234f  sub     eax, 2
0x180012352  cmp     eax, 1
0x180012355  jbe     loc_18001251E
0x18001235b  lea     rcx, [rbp+arg_0]; int *
0x18001235f  call    ?GetChannelRegistrySetting@RdpRemoteAppGfxRedirectionHandler@@SAJPEAH@Z; RdpRemoteAppGfxRedirectionHandler::GetChannelRegistrySetting(int *)
0x180012364  test    eax, eax
0x180012366  js      loc_1800124EA
0x18001236c  cmp     dword ptr [rbp+arg_0], r12d
0x180012370  jz      loc_1800124EA
0x180012376  movups  xmm0, xmmword ptr [rdi+5Ch]
0x18001237a  lea     rdx, [rbp+arg_10]; struct RdpRemoteAppGfxRedirectionHandler **
0x18001237e  mov     [rbp+arg_10], r12
0x180012382  lea     rcx, [rbp+var_10]; struct _GUID
0x180012386  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001238b  call    ?CreateInstance@RdpRemoteAppGfxRedirectionHandler@@SAJU_GUID@@PEAPEAV1@@Z; RdpRemoteAppGfxRedirectionHandler::CreateInstance(_GUID,RdpRemoteAppGfxRedirectionHandler * *)
0x180012390  mov     esi, eax
0x180012392  test    eax, eax
0x180012394  jns     loc_180012424
0x18001239a  mov     eax, cs:dword_180044008
0x1800123a0  cmp     eax, 2
0x1800123a3  jbe     short loc_180012416
0x1800123a5  lea     rax, aRdpremoteappgf_3; "RdpRemoteAppGfxRedirectionHandler::Crea"...
0x1800123ac  mov     [rbp+var_30], r14
0x1800123b0  mov     [rbp+arg_18], rax
0x1800123b4  lea     r14, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800123bb  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800123c2  mov     dword ptr [rbp+arg_0], 18Eh
0x1800123c9  mov     [rbp+var_20], rax
0x1800123cd  lea     rdx, word_18003B682
0x1800123d4  lea     rax, [rbp+arg_18]
0x1800123d8  mov     [rbp+var_28], r14
0x1800123dc  mov     [rsp+80h+var_38], rax
0x1800123e1  lea     rax, [rbp+var_30]
0x1800123e5  mov     [rsp+80h+var_40], rax
0x1800123ea  lea     rax, [rbp+arg_0]
0x1800123ee  mov     [rsp+80h+var_48], rax
0x1800123f3  lea     rax, [rbp+var_28]
0x1800123f7  mov     [rsp+80h+var_50], rax
0x1800123fc  lea     rax, [rbp+arg_8]
0x180012400  mov     [rsp+80h+var_58], rax
0x180012405  lea     rax, [rbp+var_20]
0x180012409  mov     [rsp+80h+var_60], rax
0x18001240e  mov     [rbp+arg_8], esi
0x180012411  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180012416  lea     rcx, [rbp+arg_10]
0x18001241a  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x18001241f  jmp     loc_1800128FD
0x180012424  mov     rbx, [rbp+arg_10]
0x180012428  mov     rcx, rbx; this
0x18001242b  call    ?OnSessionConnect@RdpRemoteAppGfxRedirectionHandler@@QEAAJXZ; RdpRemoteAppGfxRedirectionHandler::OnSessionConnect(void)
0x180012430  test    eax, eax
0x180012432  js      short loc_18001247D
0x180012434  lea     r14, [rdi+30h]
0x180012438  cmp     rbx, [r14]
0x18001243b  jz      short loc_180012450
0x18001243d  mov     rcx, r14
0x180012440  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x180012445  mov     rcx, r14
0x180012448  mov     [r14], rbx
0x18001244b  call    ?SafeAddRef@?$TCntPtr@VRdpRemoteAppAuxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(void)
0x180012450  mov     eax, cs:dword_180044008
0x180012456  cmp     eax, 4
0x180012459  jbe     short loc_180012416
0x18001245b  lea     rax, aContainerRedir_1; "Container redirection channel is enable"...
0x180012462  mov     [rbp+arg_0], rax
0x180012466  lea     rdx, byte_18003B661
0x18001246d  lea     rax, [rbp+arg_0]
0x180012471  mov     [rsp+80h+var_60], rax
0x180012476  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001247b  jmp     short loc_180012416
0x18001247d  mov     eax, cs:dword_180044008
0x180012483  cmp     eax, 2
0x180012486  jbe     short loc_180012416
0x180012488  lea     rax, aOnsessionconne_0; "OnSessionConnect failed. Container grap"...
0x18001248f  mov     [rbp+arg_18], r14
0x180012493  mov     [rbp+var_28], rax
0x180012497  lea     r14, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18001249e  lea     rax, [rbp+arg_18]
0x1800124a2  mov     dword ptr [rbp+arg_0], 197h
0x1800124a9  mov     [rsp+80h+var_40], rax
0x1800124ae  lea     rdx, dword_18003B61C
0x1800124b5  lea     rax, [rbp+arg_0]
0x1800124b9  mov     [rbp+var_20], r14
0x1800124bd  mov     [rsp+80h+var_48], rax
0x1800124c2  lea     rax, [rbp+var_20]
0x1800124c6  mov     [rsp+80h+var_50], rax
0x1800124cb  lea     rax, [rbp+arg_8]
0x1800124cf  mov     [rsp+80h+var_58], rax
0x1800124d4  lea     rax, [rbp+var_28]
0x1800124d8  mov     [rsp+80h+var_60], rax
0x1800124dd  mov     [rbp+arg_8], esi
0x1800124e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800124e5  jmp     loc_180012416
0x1800124ea  mov     eax, cs:dword_180044008
0x1800124f0  cmp     eax, 4
0x1800124f3  jbe     loc_1800128FD
0x1800124f9  lea     rax, aContainerRedir; "Container redirection mode is not enabl"...
0x180012500  mov     [rbp+arg_0], rax
0x180012504  lea     rdx, byte_18003B5FB
0x18001250b  lea     rax, [rbp+arg_0]
0x18001250f  mov     [rsp+80h+var_60], rax
0x180012514  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180012519  jmp     loc_1800128FD
0x18001251e  lea     r15, [rdi+5Ch]
0x180012522  mov     [rbp+arg_10], r12
0x180012526  movups  xmm0, xmmword ptr [r15]
0x18001252a  lea     rdx, [rbp+var_30]; struct RdpRemoteAppGfxRedirectionHandler **
0x18001252e  mov     [rbp+var_30], r12
0x180012532  lea     rcx, [rbp+var_10]; struct _GUID
0x180012536  mov     [rbp+arg_18], r12
0x18001253a  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001253f  call    ?CreateInstance@RdpRemoteAppGfxRedirectionHandler@@SAJU_GUID@@PEAPEAV1@@Z; RdpRemoteAppGfxRedirectionHandler::CreateInstance(_GUID,RdpRemoteAppGfxRedirectionHandler * *)
0x180012544  mov     esi, eax
0x180012546  test    eax, eax
0x180012548  jns     loc_1800125D3
0x18001254e  mov     eax, cs:dword_180044008
0x180012554  cmp     eax, 2
0x180012557  jbe     loc_1800128E2
0x18001255d  lea     rax, aRdpremoteappgf_3; "RdpRemoteAppGfxRedirectionHandler::Crea"...
0x180012564  mov     [rbp+var_28], r14
0x180012568  mov     [rbp+var_20], rax
0x18001256c  lea     r14, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180012573  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001257a  mov     dword ptr [rbp+arg_0], 152h
0x180012581  mov     qword ptr [rbp+var_10.Data1], rax
0x180012585  lea     rdx, byte_18003B835
0x18001258c  lea     rax, [rbp+var_20]
0x180012590  mov     [rbp+var_18], r14
0x180012594  mov     [rsp+80h+var_38], rax
0x180012599  lea     rax, [rbp+var_28]
0x18001259d  mov     [rsp+80h+var_40], rax
0x1800125a2  lea     rax, [rbp+arg_0]
0x1800125a6  mov     [rsp+80h+var_48], rax
0x1800125ab  lea     rax, [rbp+var_18]
0x1800125af  mov     [rsp+80h+var_50], rax
0x1800125b4  lea     rax, [rbp+arg_8]
0x1800125b8  mov     [rsp+80h+var_58], rax
0x1800125bd  lea     rax, [rbp+var_10]
0x1800125c1  mov     [rbp+arg_8], esi
0x1800125c4  mov     [rsp+80h+var_60], rax
0x1800125c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800125ce  jmp     loc_1800128E2
0x1800125d3  mov     rbx, [rbp+var_30]
0x1800125d7  mov     rcx, rbx; this
0x1800125da  call    ?OnSessionConnect@RdpRemoteAppGfxRedirectionHandler@@QEAAJXZ; RdpRemoteAppGfxRedirectionHandler::OnSessionConnect(void)
0x1800125df  lea     r14, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800125e6  mov     ecx, eax
0x1800125e8  test    eax, eax
0x1800125ea  js      loc_18001278B
0x1800125f0  lea     rcx, [rbx+30h]
0x1800125f4  mov     rax, [rcx]
0x1800125f7  lea     r8, [rbp+arg_10]
0x1800125fb  lea     rdx, IID_IRdsDWMDirectDriverIO
0x180012602  mov     rax, [rax]
0x180012605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001260a  mov     esi, eax
0x18001260c  test    eax, eax
0x18001260e  jns     short loc_180012688
0x180012610  mov     eax, cs:dword_180044008
0x180012616  cmp     eax, 2
0x180012619  jbe     loc_1800128E2
0x18001261f  lea     rax, aFailedToQueryI; "Failed to query I/O processor interface"
0x180012626  mov     dword ptr [rbp+arg_0], 15Ah
0x18001262d  mov     qword ptr [rbp+var_10.Data1], rax
0x180012631  lea     rbx, aResetstateonse; "ResetStateOnSessionReconnect"
0x180012638  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001263f  mov     [rbp+var_18], rbx
0x180012643  mov     [rbp+var_28], rax
0x180012647  lea     rdx, qword_18003B7E8
0x18001264e  lea     rax, [rbp+var_10]
0x180012652  mov     [rbp+var_20], r14
0x180012656  mov     [rsp+80h+var_38], rax
0x18001265b  lea     rax, [rbp+var_18]
0x18001265f  mov     [rsp+80h+var_40], rax
0x180012664  lea     rax, [rbp+arg_0]
0x180012668  mov     [rsp+80h+var_48], rax
0x18001266d  lea     rax, [rbp+var_20]
0x180012671  mov     [rsp+80h+var_50], rax
0x180012676  lea     rax, [rbp+arg_8]
0x18001267a  mov     [rsp+80h+var_58], rax
0x18001267f  lea     rax, [rbp+var_28]
0x180012683  jmp     loc_1800125C1
0x180012688  lea     rsi, [rdi+28h]
0x18001268c  mov     rax, [rsi]
0x18001268f  cmp     [rbp+arg_10], rax
0x180012693  jz      short loc_1800126AC
0x180012695  mov     rcx, rsi
0x180012698  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18001269d  mov     rax, [rbp+arg_10]
0x1800126a1  mov     rcx, rsi
0x1800126a4  mov     [rsi], rax
0x1800126a7  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800126ac  lea     rsi, [rdi+30h]
0x1800126b0  cmp     rbx, [rsi]
0x1800126b3  jz      short loc_1800126C8
0x1800126b5  mov     rcx, rsi
0x1800126b8  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x1800126bd  mov     rcx, rsi
0x1800126c0  mov     [rsi], rbx
0x1800126c3  call    ?SafeAddRef@?$TCntPtr@VRdpRemoteAppAuxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(void)
0x1800126c8  mov     eax, cs:dword_180044008
0x1800126ce  cmp     eax, 4
0x1800126d1  jbe     short loc_1800126F3
0x1800126d3  lea     rax, aContainerRedir_0; "Container redirection mode is successfu"...
0x1800126da  mov     [rbp+arg_0], rax
0x1800126de  lea     rdx, byte_18003B7C7
0x1800126e5  lea     rax, [rbp+arg_0]
0x1800126e9  mov     [rsp+80h+var_60], rax
0x1800126ee  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800126f3  lea     rbx, aResetstateonse; "ResetStateOnSessionReconnect"
0x1800126fa  movups  xmm0, xmmword ptr [r15]
0x1800126fe  lea     rdx, [rbp+arg_18]; struct RdpRemoteAppAuxRedirectionHandler **
0x180012702  lea     rcx, [rbp+var_10]; struct _GUID
0x180012706  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001270b  call    ?CreateInstance@RdpRemoteAppAuxRedirectionHandler@@SAJU_GUID@@PEAPEAV1@@Z; RdpRemoteAppAuxRedirectionHandler::CreateInstance(_GUID,RdpRemoteAppAuxRedirectionHandler * *)
0x180012710  mov     esi, eax
0x180012712  test    eax, eax
0x180012714  jns     loc_1800127FC
0x18001271a  mov     eax, cs:dword_180044008
0x180012720  cmp     eax, 2
0x180012723  jbe     loc_1800128E2
0x180012729  lea     rax, aRdpremoteappau_2; "RdpRemoteAppAuxRedirectionHandler::Crea"...
0x180012730  mov     [rbp+var_18], rbx
0x180012734  mov     qword ptr [rbp+var_10.Data1], rax
0x180012738  lea     rdx, byte_18003B735
0x18001273f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180012746  mov     dword ptr [rbp+arg_0], 16Ch
0x18001274d  mov     [rbp+var_28], rax
0x180012751  lea     rax, [rbp+var_10]
0x180012755  mov     [rsp+80h+var_38], rax
0x18001275a  lea     rax, [rbp+var_18]
0x18001275e  mov     [rsp+80h+var_40], rax
0x180012763  lea     rax, [rbp+arg_0]
0x180012767  mov     [rsp+80h+var_48], rax
  ... truncated ...
```
