# CTSThread::BindThread(void)

- ea: `0x1800234e0`
- end: `0x1800238dc`
- name: `?BindThread@CTSThread@@UEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000160c`
- `0x180005f9c`
- `0x18000f08c`
- `0x18001d114`
- `0x18001edc0`
- `0x18001f424`
- `0x180021770`
- `0x1800233b8`
- `0x1800234e0`
- `0x180023fec`
- `0x1800246ec`
- `0x1800259b4`
- `0x18002709c`
- `0x180027b6c`
- `0x180027b98`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18002367d`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180023852`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180023579`: `Failed to create thread signal`
- `0x180023611`: `thread descriptor creation failed in bind path`
- `0x180023664`: `BindThread`
- `0x180023839`: `BindThread`
- `0x18002368b`: `Failing BindThread - thread does not allow binding`
- `0x180023864`: `Failed to InitializeInThreadContext`
- `0x1800237b5`: `Unable to add the current thread to the descriptor`

## pseudocode

```c
__int64 __fastcall CTSThread::BindThread(CTSThread *this)
{
  CTSReaderWriterLock *v2; // r12
  __int64 v3; // rdx
  int Id; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  struct CTS_TLS_ThreadDescriptor *v10; // rsi
  int v11; // r15d
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  const char *v28; // [rsp+50h] [rbp-20h] BYREF
  const char *v29; // [rsp+58h] [rbp-18h] BYREF
  __int64 v30; // [rsp+60h] [rbp-10h] BYREF
  int v31; // [rsp+B0h] [rbp+40h] BYREF
  int v32; // [rsp+B8h] [rbp+48h] BYREF
  struct CTS_TLS_ThreadDescriptor *v33; // [rsp+C0h] [rbp+50h] BYREF
  const char *v34; // [rsp+C8h] [rbp+58h] BYREF

  v30 = 0;
  v33 = 0;
  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( !*((_QWORD *)this + 85) )
  {
    Id = (*(__int64 (__fastcall **)(_QWORD, char *, unsigned int (__fastcall *)(CTSThread *), CTSThread *))(**((_QWORD **)this + 92) + 32LL))(
           *((_QWORD *)this + 92),
           (char *)this + 680,
           CTSThread::OnNotifyThreadMessage,
           this);
    if ( Id < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3, v5, v6);
        v8 = 48;
        v9 = "Failed to create thread signal";
LABEL_16:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)v9,
          Id);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
  }
  if ( *((_DWORD *)this + 20) != 1 )
  {
    Id = -2147467259;
    goto LABEL_45;
  }
  v10 = TSGet_TLS_ThreadDescriptor();
  if ( v10 )
  {
    v11 = 0;
    TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v33);
    v12 = *((_QWORD *)v10 + 4);
    v33 = v10;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    goto LABEL_18;
  }
  Id = CTS_TLS_ThreadDescriptor::CreateInstance(1, &v33);
  if ( Id >= 0 )
  {
    v10 = v33;
    v11 = 1;
LABEL_18:
    if ( !*((_DWORD *)v10 + 124) )
    {
      Id = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v31 = 913;
        v34 = "BindThread";
        v32 = -2147467259;
        v28 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v29 = "Failing BindThread - thread does not allow binding";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (__int64)byte_18003FA69,
          v14,
          v15,
          (const unsigned __int16 **)&v29,
          (__int64)&v32,
          (const unsigned __int16 **)&v28,
          (__int64)&v31,
          (const unsigned __int16 **)&v34);
      }
      goto LABEL_43;
    }
    Id = PAL_System_ThreadGetId((char *)this + 56);
    if ( Id >= 0 )
    {
      Id = PAL_System_ThreadGetDeathCondition(*((_DWORD *)this + 14), (void **)this + 8);
      if ( Id >= 0 )
      {
        Id = CTSThread::InitializeInThreadContext(this, v19);
        if ( Id < 0 )
        {
          if ( (unsigned int)dword_180044008 > 2 )
          {
            v31 = 935;
            v34 = "BindThread";
            v32 = -2147467259;
            v29 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
            v28 = "Failed to InitializeInThreadContext";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v20,
              (__int64)&dword_18003FA24,
              v21,
              v22,
              (const unsigned __int16 **)&v28,
              (__int64)&v32,
              (const unsigned __int16 **)&v29,
              (__int64)&v31,
              (const unsigned __int16 **)&v34);
          }
        }
        else
        {
          *((_DWORD *)this + 20) = 3;
          Id = CTS_TLS_ThreadDescriptor::AddThreadToList(v10, this);
          if ( Id >= 0 )
          {
            *((_DWORD *)this + 46) = 1;
            if ( v10 != *((struct CTS_TLS_ThreadDescriptor **)this + 81) )
            {
              TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease((char *)this + 648);
              *((_QWORD *)this + 81) = v10;
              if ( v10 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 4) + 8LL))(*((_QWORD *)v10 + 4));
            }
            goto LABEL_45;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v23, v24, v25);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
              v26,
              (__int64)"Unable to add the current thread to the descriptor",
              Id);
          }
        }
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v18 = 51;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v18 = 50;
LABEL_26:
        WPP_SF_(v17[2], v18, &WPP_903e1551464439edae082eb88b6439cd_Traceguids);
      }
    }
LABEL_43:
    if ( v11 )
      CTS_TLS_ThreadDescriptor::DetachThread(v10, this);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16, v14, v15);
    v8 = 49;
    v9 = "thread descriptor creation failed in bind path";
    goto LABEL_16;
  }
LABEL_45:
  CTSReaderWriterLock::WriteUnlock(v2);
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v33);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v30);
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x1800234e0  push    rbp
0x1800234e2  push    rbx
0x1800234e3  push    rsi
0x1800234e4  push    rdi
0x1800234e5  push    r12
0x1800234e7  push    r14
0x1800234e9  push    r15
0x1800234eb  mov     rbp, rsp
0x1800234ee  sub     rsp, 70h
0x1800234f2  mov     rdi, rcx
0x1800234f5  mov     [rbp+var_10], 0
0x1800234fd  mov     [rbp+arg_10], 0
0x180023505  lea     r12, [rcx+94h]
0x18002350c  mov     rcx, r12; this
0x18002350f  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180023514  lea     rdx, [rdi+2A8h]
0x18002351b  cmp     qword ptr [rdx], 0
0x18002351f  jnz     short loc_180023585
0x180023521  mov     rcx, [rdi+2E0h]
0x180023528  lea     r8, ?OnNotifyThreadMessage@CTSThread@@KAIPEAX@Z; CTSThread::OnNotifyThreadMessage(void *)
0x18002352f  mov     r9, rdi
0x180023532  mov     rax, [rcx]
0x180023535  mov     rax, [rax+20h]
0x180023539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002353e  mov     ebx, eax
0x180023540  test    eax, eax
0x180023542  jns     short loc_180023585
0x180023544  mov     rcx, cs:WPP_GLOBAL_Control
0x18002354b  lea     rax, WPP_GLOBAL_Control
0x180023552  cmp     rcx, rax
0x180023555  jz      loc_1800238B1
0x18002355b  test    byte ptr [rcx+1Ch], 8
0x18002355f  jz      loc_1800238B1
0x180023565  cmp     byte ptr [rcx+19h], 2
0x180023569  jb      loc_1800238B1
0x18002356f  call    RdpX_GetActivityIdPrefix
0x180023574  mov     edx, 30h ; '0'
0x180023579  lea     rcx, aFailedToCreate_11; "Failed to create thread signal"
0x180023580  jmp     loc_180023618
0x180023585  mov     r14d, 1
0x18002358b  cmp     [rdi+50h], r14d
0x18002358f  jz      short loc_18002359B
0x180023591  mov     ebx, 80004005h
0x180023596  jmp     loc_1800238B1
0x18002359b  call    ?TSGet_TLS_ThreadDescriptor@@YAPEAVCTS_TLS_ThreadDescriptor@@XZ; TSGet_TLS_ThreadDescriptor(void)
0x1800235a0  mov     rsi, rax
0x1800235a3  test    rax, rax
0x1800235a6  jz      short loc_1800235CA
0x1800235a8  lea     rcx, [rbp+arg_10]
0x1800235ac  xor     r15d, r15d
0x1800235af  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x1800235b4  mov     rcx, [rsi+20h]
0x1800235b8  mov     [rbp+arg_10], rsi
0x1800235bc  mov     rax, [rcx]
0x1800235bf  mov     rax, [rax+8]
0x1800235c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235c8  jmp     short loc_180023647
0x1800235ca  lea     rdx, [rbp+arg_10]; struct CTS_TLS_ThreadDescriptor **
0x1800235ce  mov     ecx, r14d; int
0x1800235d1  call    ?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z; CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)
0x1800235d6  mov     ebx, eax
0x1800235d8  test    eax, eax
0x1800235da  jns     short loc_180023640
0x1800235dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235e3  lea     rax, WPP_GLOBAL_Control
0x1800235ea  cmp     rcx, rax
0x1800235ed  jz      loc_1800238B1
0x1800235f3  test    byte ptr [rcx+1Ch], 8
0x1800235f7  jz      loc_1800238B1
0x1800235fd  cmp     byte ptr [rcx+19h], 2
0x180023601  jb      loc_1800238B1
0x180023607  call    RdpX_GetActivityIdPrefix
0x18002360c  mov     edx, 31h ; '1'
0x180023611  lea     rcx, aThreadDescript_0; "thread descriptor creation failed in bi"...
0x180023618  mov     dword ptr [rsp+70h+var_48], ebx
0x18002361c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180023623  mov     [rsp+70h+var_50], rcx
0x180023628  mov     r9d, eax
0x18002362b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023632  mov     rcx, [rcx+10h]
0x180023636  call    WPP_SF_DsD
0x18002363b  jmp     loc_1800238B1
0x180023640  mov     rsi, [rbp+arg_10]
0x180023644  mov     r15d, r14d
0x180023647  cmp     dword ptr [rsi+1F0h], 0
0x18002364e  jnz     short loc_1800236C3
0x180023650  mov     eax, cs:dword_180044008
0x180023656  mov     ebx, 80004005h
0x18002365b  cmp     eax, 2
0x18002365e  jbe     loc_1800238A1
0x180023664  lea     rax, aBindthread; "BindThread"
0x18002366b  mov     [rbp+arg_0], 391h
0x180023672  mov     [rbp+arg_18], rax
0x180023676  lea     rdx, byte_18003FA69
0x18002367d  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180023684  mov     [rbp+arg_8], ebx
0x180023687  mov     [rbp+var_20], rax
0x18002368b  lea     rax, aFailingBindthr; "Failing BindThread - thread does not al"...
0x180023692  mov     [rbp+var_18], rax
0x180023696  lea     rax, [rbp+arg_18]
0x18002369a  mov     [rsp+70h+var_30], rax
0x18002369f  lea     rax, [rbp+arg_0]
0x1800236a3  mov     [rsp+70h+var_38], rax
0x1800236a8  lea     rax, [rbp+var_20]
0x1800236ac  mov     [rsp+70h+var_40], rax
0x1800236b1  lea     rax, [rbp+arg_8]
0x1800236b5  mov     [rsp+70h+var_48], rax
0x1800236ba  lea     rax, [rbp+var_18]
0x1800236be  jmp     loc_180023897
0x1800236c3  lea     rcx, [rdi+38h]
0x1800236c7  call    PAL_System_ThreadGetId
0x1800236cc  mov     ebx, eax
0x1800236ce  test    eax, eax
0x1800236d0  jns     short loc_180023717
0x1800236d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236d9  lea     rax, WPP_GLOBAL_Control
0x1800236e0  cmp     rcx, rax
0x1800236e3  jz      loc_1800238A1
0x1800236e9  test    [rcx+1Ch], r14b
0x1800236ed  jz      loc_1800238A1
0x1800236f3  cmp     [rcx+19h], r14b
0x1800236f7  jb      loc_1800238A1
0x1800236fd  mov     edx, 32h ; '2'
0x180023702  mov     rcx, [rcx+10h]
0x180023706  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18002370d  call    WPP_SF_
0x180023712  jmp     loc_1800238A1
0x180023717  mov     ecx, [rdi+38h]; dwThreadId
0x18002371a  lea     rdx, [rdi+40h]; void **
0x18002371e  call    ?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z; PAL_System_ThreadGetDeathCondition(ulong,void * *)
0x180023723  mov     ebx, eax
0x180023725  test    eax, eax
0x180023727  jns     short loc_18002375B
0x180023729  mov     rcx, cs:WPP_GLOBAL_Control
0x180023730  lea     rax, WPP_GLOBAL_Control
0x180023737  cmp     rcx, rax
0x18002373a  jz      loc_1800238A1
0x180023740  test    [rcx+1Ch], r14b
0x180023744  jz      loc_1800238A1
0x18002374a  cmp     [rcx+19h], r14b
0x18002374e  jb      loc_1800238A1
0x180023754  mov     edx, 33h ; '3'
0x180023759  jmp     short loc_180023702
0x18002375b  mov     rcx, rdi; this
0x18002375e  call    ?InitializeInThreadContext@CTSThread@@AEAAJH@Z; CTSThread::InitializeInThreadContext(int)
0x180023763  mov     ebx, eax
0x180023765  test    eax, eax
0x180023767  js      loc_18002382E
0x18002376d  mov     rdx, rdi; struct ITSThread *
0x180023770  mov     dword ptr [rdi+50h], 3
0x180023777  mov     rcx, rsi; this
0x18002377a  call    ?AddThreadToList@CTS_TLS_ThreadDescriptor@@AEAAJPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::AddThreadToList(ITSThread *)
0x18002377f  mov     ebx, eax
0x180023781  test    eax, eax
0x180023783  jns     short loc_1800237E9
0x180023785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002378c  lea     rax, WPP_GLOBAL_Control
0x180023793  cmp     rcx, rax
0x180023796  jz      loc_1800238A1
0x18002379c  test    byte ptr [rcx+1Ch], 8
0x1800237a0  jz      loc_1800238A1
0x1800237a6  cmp     byte ptr [rcx+19h], 2
0x1800237aa  jb      loc_1800238A1
0x1800237b0  call    RdpX_GetActivityIdPrefix
0x1800237b5  lea     rcx, aUnableToAddThe; "Unable to add the current thread to the"...
0x1800237bc  mov     dword ptr [rsp+70h+var_48], ebx
0x1800237c0  mov     [rsp+70h+var_50], rcx
0x1800237c5  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800237cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237d3  mov     edx, 34h ; '4'
0x1800237d8  mov     r9d, eax
0x1800237db  mov     rcx, [rcx+10h]
0x1800237df  call    WPP_SF_DsD
0x1800237e4  jmp     loc_1800238A1
0x1800237e9  mov     [rdi+0B8h], r14d
0x1800237f0  cmp     rsi, [rdi+288h]
0x1800237f7  jz      loc_1800238B1
0x1800237fd  lea     rcx, [rdi+288h]
0x180023804  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180023809  mov     [rdi+288h], rsi
0x180023810  test    rsi, rsi
0x180023813  jz      loc_1800238B1
0x180023819  mov     rcx, [rsi+20h]
0x18002381d  mov     rax, [rcx]
0x180023820  mov     rax, [rax+8]
0x180023824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023829  jmp     loc_1800238B1
0x18002382e  mov     eax, cs:dword_180044008
0x180023834  cmp     eax, 2
0x180023837  jbe     short loc_1800238A1
0x180023839  lea     rax, aBindthread; "BindThread"
0x180023840  mov     [rbp+arg_0], 3A7h
0x180023847  mov     [rbp+arg_18], rax
0x18002384b  lea     rdx, dword_18003FA24
0x180023852  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180023859  mov     [rbp+arg_8], 80004005h
0x180023860  mov     [rbp+var_18], rax
0x180023864  lea     rax, aFailedToInitia; "Failed to InitializeInThreadContext"
0x18002386b  mov     [rbp+var_20], rax
0x18002386f  lea     rax, [rbp+arg_18]
0x180023873  mov     [rsp+70h+var_30], rax
0x180023878  lea     rax, [rbp+arg_0]
0x18002387c  mov     [rsp+70h+var_38], rax
0x180023881  lea     rax, [rbp+var_18]
0x180023885  mov     [rsp+70h+var_40], rax
0x18002388a  lea     rax, [rbp+arg_8]
0x18002388e  mov     [rsp+70h+var_48], rax
0x180023893  lea     rax, [rbp+var_20]
0x180023897  mov     [rsp+70h+var_50], rax
0x18002389c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800238a1  test    r15d, r15d
0x1800238a4  jz      short loc_1800238B1
0x1800238a6  mov     rdx, rdi; struct ITSThread *
0x1800238a9  mov     rcx, rsi; this
0x1800238ac  call    ?DetachThread@CTS_TLS_ThreadDescriptor@@QEAAXPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::DetachThread(ITSThread *)
0x1800238b1  mov     rcx, r12; this
0x1800238b4  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x1800238b9  lea     rcx, [rbp+arg_10]
0x1800238bd  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x1800238c2  lea     rcx, [rbp+var_10]
0x1800238c6  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800238cb  mov     eax, ebx
0x1800238cd  add     rsp, 70h
0x1800238d1  pop     r15
0x1800238d3  pop     r14
0x1800238d5  pop     r12
0x1800238d7  pop     rdi
0x1800238d8  pop     rsi
0x1800238d9  pop     rbx
0x1800238da  pop     rbp
0x1800238db  retn
```
