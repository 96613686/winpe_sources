# MkvMfSourceLib::MkvMfSource::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x180013ed0`
- end: `0x1800144a3`
- name: `?GetService@MkvMfSource@MkvMfSourceLib@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1491`
- prototype: `int(MkvMfSourceLib::MkvMfSource *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002400`
- `0x180007a34`
- `0x180009b04`
- `0x18000b81c`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000ea14`
- `0x180013248`
- `0x180013ed0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014148`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014148`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013fb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001419e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800142fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800143a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013fb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001419e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800142fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800143a5`

## string_xrefs

- `0x180013f10`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x180014021`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x18001420c`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x18001436c`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x180014413`: `MkvMfSourceLib::MkvMfSource::GetService`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MkvMfSourceLib::MkvMfSource::GetService(
        MkvMfSourceLib::MkvMfSource *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // r11
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v14; // ebx
  char *v15; // rbx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  HRESULT Instance; // eax
  __int64 v24; // rax
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  void *v30; // r8
  char *v31; // r8
  int CanCastTo; // edi
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // r11
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  int v43; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v44[4]; // [rsp+34h] [rbp-2Ch] BYREF
  char *v45; // [rsp+38h] [rbp-28h]
  int *v46; // [rsp+40h] [rbp-20h]
  _QWORD v47[2]; // [rsp+48h] [rbp-18h] BYREF

  v43 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "MkvMfSourceLib::MkvMfSource::GetService", 995);
  v12 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 82) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 82) + 296LL))(*((_QWORD *)this + 82));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 82) + 280LL))(
                                                            *((_QWORD *)this + 82),
                                                            v47);
    *((_DWORD *)ThreadRelativeContext + 504) = v14;
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v15 = (char *)this - 32;
  v45 = (char *)this - 32;
  v46 = &v43;
  if ( !a4 )
  {
    v43 = -2147467261;
    if ( !v12 )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, v10, v11);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( v43 < 0 && *((_DWORD *)v17 + 499) != v43 )
        CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::GetService", 997, v43);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        (char *)this - 32,
        v43);
    v18 = v43;
    goto LABEL_89;
  }
  *a4 = 0;
  v19 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 )
    v19 = *(_QWORD *)a2->Data4 - *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4;
  if ( v19 )
  {
    v21 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1 )
      v21 = *(_QWORD *)a2->Data4 - *(_QWORD *)MF_PROPERTY_HANDLER_SERVICE.Data4;
    if ( !v21 )
    {
      v22 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IInitializeWithStream.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IInitializeWithStream.Data1 )
        v22 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IInitializeWithStream.Data4;
      if ( !v22 )
      {
        Instance = CoCreateInstance(&CLSID_MFMKVPropertyHandler, 0, 1u, &IID_IInitializeWithStream, a4);
LABEL_88:
        v18 = Instance;
        goto LABEL_89;
      }
      v24 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
        v24 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
      if ( !v24 )
      {
        v47[0] = (char *)this - 32;
        v47[1] = &v43;
        Instance = MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(
                     (MkvMfSourceLib::MkvMfSource *)((char *)this - 32),
                     (struct IPropertyStore **)a4);
        goto LABEL_88;
      }
      v43 = -2147467262;
      if ( !v12 )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, v10, v11);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( v43 < 0 && *((_DWORD *)v26 + 499) != v43 )
          CallStackContext::TraceFailure(v26, "MkvMfSourceLib::MkvMfSource::GetService", 1019, v43);
      }
      if ( !g_wppLevels )
      {
LABEL_50:
        v18 = v43;
        goto LABEL_89;
      }
      v27 = 111;
LABEL_49:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        (char *)this - 32,
        v43);
      goto LABEL_50;
    }
    v28 = *(_QWORD *)&a2->Data1 - MF_MEDIA_ENGINE_TIMEDTEXTDATASOURCE;
    if ( *(_QWORD *)&a2->Data1 == MF_MEDIA_ENGINE_TIMEDTEXTDATASOURCE )
      v28 = *(_QWORD *)a2->Data4 + 0x3FD99E9A0CA3FD75LL;
    if ( v28 )
    {
      Instance = -1072875846;
      v43 = -1072875846;
      if ( g_wppLevels )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          (char *)this - 32,
          -1072875846);
        Instance = v43;
      }
      goto LABEL_88;
    }
    if ( !*((_QWORD *)this + 51) )
    {
      v43 = -2147467262;
      if ( !v12 )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, 0, v11);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( v43 < 0 && *((_DWORD *)v41 + 499) != v43 )
          CallStackContext::TraceFailure(v41, "MkvMfSourceLib::MkvMfSource::GetService", 1031, v43);
      }
      if ( !g_wppLevels )
        goto LABEL_50;
      v27 = 113;
      goto LABEL_49;
    }
    if ( (unsigned int)InlineIsEqualGUID(a3, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a4 = v30;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 8LL))(v30);
      CanCastTo = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v29, &GUID_5a0d8439_09d0_40f3_8dc3_d8b695bb1ecc) )
      {
        *a4 = v31;
        CanCastTo = 0;
      }
      else
      {
        CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                      v31 + 8,
                      a3,
                      a4);
        if ( CanCastTo < 0 )
        {
LABEL_62:
          v43 = CanCastTo;
          if ( CanCastTo >= 0 )
          {
            v18 = 0;
            goto LABEL_89;
          }
          if ( !v37 )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v34, v33, v35, v36);
            CallStackTracing::s_wpInstance = v38;
            if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
            {
              v37 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v37 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v37 + 8) )
          {
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
            if ( v43 < 0 && *((_DWORD *)v39 + 499) != v43 )
              CallStackContext::TraceFailure(v39, "MkvMfSourceLib::MkvMfSource::GetService", 1026, v43);
          }
          if ( !g_wppLevels )
            goto LABEL_50;
          v27 = 112;
          goto LABEL_49;
        }
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
    }
    v37 = (__int64 *)CallStackTracing::s_wpInstance;
    goto LABEL_62;
  }
  if ( (unsigned int)InlineIsEqualGUID(a3, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *a4 = v15;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))((char *)this - 32);
    v18 = 0;
    goto LABEL_89;
  }
  if ( (unsigned int)InlineIsEqualGUID(v20, &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66) )
  {
    *a4 = v15;
    v18 = 0;
  }
  else
  {
    v18 = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFMediaSourceEx,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::CanCastTo(
            v15 + 8,
            a3,
            a4);
    if ( v18 < 0 )
      goto LABEL_89;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
LABEL_89:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180013ed0  mov     [rsp-28h+arg_8], rbx
0x180013ed5  mov     [rsp-28h+arg_10], rsi
0x180013eda  push    rbp
0x180013edb  push    rdi
0x180013edc  push    r13
0x180013ede  push    r14
0x180013ee0  push    r15
0x180013ee2  mov     rbp, rsp
0x180013ee5  sub     rsp, 60h
0x180013ee9  mov     rax, cs:__security_cookie
0x180013ef0  xor     rax, rsp
0x180013ef3  mov     [rbp+var_8], rax
0x180013ef7  mov     rsi, r9
0x180013efa  mov     r14, r8
0x180013efd  mov     r15, rdx
0x180013f00  mov     r13, rcx
0x180013f03  mov     [rbp+var_30], 0
0x180013f0a  mov     r8d, 3E3h; int
0x180013f10  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180013f17  lea     rcx, [rbp+var_2C]; this
0x180013f1b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180013f20  nop
0x180013f21  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013f28  cmp     byte ptr [r11+8], 0
0x180013f2d  jz      short loc_180013F8E
0x180013f2f  cmp     qword ptr [r13+290h], 0
0x180013f37  jz      short loc_180013F8E
0x180013f39  mov     rcx, r11; this
0x180013f3c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013f41  mov     rdi, rax
0x180013f44  mov     rcx, [r13+290h]
0x180013f4b  mov     rdx, [rcx]
0x180013f4e  mov     rax, [rdx+128h]
0x180013f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f5a  mov     ebx, eax
0x180013f5c  mov     rcx, [r13+290h]
0x180013f63  mov     rdx, [rcx]
0x180013f66  mov     rax, [rdx+118h]
0x180013f6d  lea     rdx, [rbp+var_18]
0x180013f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f76  movups  xmm0, xmmword ptr [rax]
0x180013f79  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180013f81  mov     [rdi+7E0h], ebx
0x180013f87  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013f8e  lea     rbx, [r13-20h]
0x180013f92  mov     [rbp+var_28], rbx
0x180013f96  lea     rax, [rbp+var_30]
0x180013f9a  mov     [rbp+var_20], rax
0x180013f9e  test    rsi, rsi
0x180013fa1  jnz     loc_180014067
0x180013fa7  mov     [rbp+var_30], 80004003h
0x180013fae  test    r11, r11
0x180013fb1  jnz     short loc_180013FFA
0x180013fb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013fba  nop     dword ptr [rax+rax+00h]
0x180013fbf  mov     rcx, rax
0x180013fc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013fc9  test    rax, rax
0x180013fcc  jz      short loc_180013FEC
0x180013fce  mov     rax, [rax]
0x180013fd1  mov     edx, 7F0h
0x180013fd6  mov     rax, [rax+8]
0x180013fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fdf  test    eax, eax
0x180013fe1  jz      short loc_180013FEC
0x180013fe3  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013fea  jmp     short loc_180013FFA
0x180013fec  lea     r11, qword_1800DBF70
0x180013ff3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r11; CallStackTracing * CallStackTracing::s_wpInstance
0x180013ffa  cmp     byte ptr [r11+8], 0
0x180013fff  jz      short loc_180014030
0x180014001  mov     rcx, r11; this
0x180014004  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180014009  mov     r9d, [rbp+var_30]; int
0x18001400d  test    r9d, r9d
0x180014010  jns     short loc_180014030
0x180014012  cmp     [rax+7CCh], r9d
0x180014019  jz      short loc_180014030
0x18001401b  mov     r8d, 3E5h; int
0x180014021  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180014028  mov     rcx, rax; this
0x18001402b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180014030  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014037  jb      short loc_18001405F
0x180014039  mov     edx, 6Ch ; 'l'
0x18001403e  mov     eax, [rbp+var_30]
0x180014041  mov     dword ptr [rsp+60h+ppv], eax
0x180014045  mov     r9, rbx
0x180014048  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001404f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014056  mov     rcx, [rcx+10h]
0x18001405a  call    WPP_SF_qD
0x18001405f  mov     ebx, [rbp+var_30]
0x180014062  jmp     loc_1800140EE
0x180014067  mov     qword ptr [rsi], 0
0x18001406e  mov     rax, [r15]
0x180014071  sub     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x180014078  jnz     short loc_180014085
0x18001407a  mov     rax, [r15+8]
0x18001407e  sub     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x180014085  test    rax, rax
0x180014088  jnz     short loc_1800140F3
0x18001408a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180014091  mov     rcx, r14
0x180014094  call    InlineIsEqualGUID
0x180014099  test    eax, eax
0x18001409b  jnz     short loc_1800140DA
0x18001409d  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x1800140a4  call    InlineIsEqualGUID
0x1800140a9  test    eax, eax
0x1800140ab  jz      short loc_1800140B4
0x1800140ad  mov     [rsi], rbx
0x1800140b0  xor     ebx, ebx
0x1800140b2  jmp     short loc_1800140C9
0x1800140b4  lea     rcx, [rbx+8]
0x1800140b8  mov     r8, rsi
0x1800140bb  mov     rdx, r14
0x1800140be  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFMediaSourceEx@@UIMFRateSupport@@UIMFRateControl@@UIMFGetService@@UIMFMediaEventGenerator@@UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFMediaSourceEx,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x1800140c3  mov     ebx, eax
0x1800140c5  test    eax, eax
0x1800140c7  js      short loc_1800140EE
0x1800140c9  mov     rcx, [rsi]
0x1800140cc  mov     rdx, [rcx]
0x1800140cf  mov     rax, [rdx+8]
0x1800140d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140d8  jmp     short loc_1800140EE
0x1800140da  mov     [rsi], rbx
0x1800140dd  mov     rax, [rbx]
0x1800140e0  mov     rcx, rbx
0x1800140e3  mov     rax, [rax+8]
0x1800140e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ec  xor     ebx, ebx
0x1800140ee  jmp     loc_180014472
0x1800140f3  mov     rax, [r15]
0x1800140f6  sub     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data1
0x1800140fd  jnz     short loc_18001410A
0x1800140ff  mov     rax, [r15+8]
0x180014103  sub     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data4
0x18001410a  test    rax, rax
0x18001410d  jnz     loc_180014253
0x180014113  mov     rax, [r14]
0x180014116  sub     rax, qword ptr cs:IID_IInitializeWithStream.Data1
0x18001411d  jnz     short loc_18001412A
0x18001411f  mov     rax, [r14+8]
0x180014123  sub     rax, qword ptr cs:IID_IInitializeWithStream.Data4
0x18001412a  test    rax, rax
0x18001412d  jnz     short loc_180014159
0x18001412f  mov     [rsp+60h+ppv], rsi; ppv
0x180014134  lea     r9, IID_IInitializeWithStream; riid
0x18001413b  xor     edx, edx; pUnkOuter
0x18001413d  lea     r8d, [rax+1]; dwClsContext
0x180014141  lea     rcx, CLSID_MFMKVPropertyHandler; rclsid
0x180014148  call    cs:__imp_CoCreateInstance
0x18001414f  nop     dword ptr [rax+rax+00h]
0x180014154  jmp     loc_180014470
0x180014159  mov     rax, [r14]
0x18001415c  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180014163  jnz     short loc_180014170
0x180014165  mov     rax, [r14+8]
0x180014169  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180014170  test    rax, rax
0x180014173  jnz     short loc_180014192
0x180014175  mov     [rbp+var_18], rbx
0x180014179  lea     rax, [rbp+var_30]
0x18001417d  mov     [rbp+var_10], rax
0x180014181  mov     rdx, rsi; struct IPropertyStore **
0x180014184  mov     rcx, rbx; this
0x180014187  call    ?GetMetadataPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z; MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(IPropertyStore * *)
0x18001418c  nop
0x18001418d  jmp     loc_180014470
0x180014192  mov     [rbp+var_30], 80004002h
0x180014199  test    r11, r11
0x18001419c  jnz     short loc_1800141E5
0x18001419e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800141a5  nop     dword ptr [rax+rax+00h]
0x1800141aa  mov     rcx, rax
0x1800141ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800141b4  test    rax, rax
0x1800141b7  jz      short loc_1800141D7
0x1800141b9  mov     rax, [rax]
0x1800141bc  mov     edx, 7F0h
0x1800141c1  mov     rax, [rax+8]
0x1800141c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141ca  test    eax, eax
0x1800141cc  jz      short loc_1800141D7
0x1800141ce  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800141d5  jmp     short loc_1800141E5
0x1800141d7  lea     r11, qword_1800DBF70
0x1800141de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r11; CallStackTracing * CallStackTracing::s_wpInstance
0x1800141e5  cmp     byte ptr [r11+8], 0
0x1800141ea  jz      short loc_18001421B
0x1800141ec  mov     rcx, r11; this
0x1800141ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800141f4  mov     r9d, [rbp+var_30]; int
0x1800141f8  test    r9d, r9d
0x1800141fb  jns     short loc_18001421B
0x1800141fd  cmp     [rax+7CCh], r9d
0x180014204  jz      short loc_18001421B
0x180014206  mov     r8d, 3FBh; int
0x18001420c  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180014213  mov     rcx, rax; this
0x180014216  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001421b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014222  jb      short loc_18001424B
0x180014224  mov     edx, 6Fh ; 'o'
0x180014229  mov     eax, [rbp+var_30]
0x18001422c  mov     dword ptr [rsp+60h+ppv], eax
0x180014230  mov     r9, rbx
0x180014233  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001423a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014241  mov     rcx, [rcx+10h]
0x180014245  call    WPP_SF_qD
0x18001424a  nop
0x18001424b  mov     ebx, [rbp+var_30]
0x18001424e  jmp     loc_180014472
0x180014253  mov     rax, [r15]
0x180014256  sub     rax, cs:MF_MEDIA_ENGINE_TIMEDTEXTDATASOURCE
0x18001425d  jnz     short loc_18001426A
0x18001425f  mov     rax, [r15+8]
0x180014263  sub     rax, cs:qword_1800BC148
0x18001426a  test    rax, rax
0x18001426d  jnz     loc_180014439
0x180014273  mov     r8, [r13+198h]
0x18001427a  test    r8, r8
0x18001427d  jz      loc_180014399
0x180014283  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001428a  mov     rcx, r14
0x18001428d  call    InlineIsEqualGUID
0x180014292  test    eax, eax
0x180014294  jnz     short loc_1800142D3
0x180014296  lea     rdx, _GUID_5a0d8439_09d0_40f3_8dc3_d8b695bb1ecc
0x18001429d  call    InlineIsEqualGUID
0x1800142a2  test    eax, eax
0x1800142a4  jz      short loc_1800142AD
0x1800142a6  mov     [rsi], r8
0x1800142a9  xor     edi, edi
0x1800142ab  jmp     short loc_1800142C2
0x1800142ad  lea     rcx, [r8+8]
0x1800142b1  mov     r8, rsi
0x1800142b4  mov     rdx, r14
0x1800142b7  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x1800142bc  mov     edi, eax
0x1800142be  test    eax, eax
0x1800142c0  js      short loc_1800142EE
0x1800142c2  mov     rcx, [rsi]
0x1800142c5  mov     rdx, [rcx]
0x1800142c8  mov     rax, [rdx+8]
0x1800142cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142d1  jmp     short loc_1800142E7
0x1800142d3  mov     [rsi], r8
0x1800142d6  mov     rax, [r8]
0x1800142d9  mov     rcx, r8
0x1800142dc  mov     rax, [rax+8]
0x1800142e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e5  xor     edi, edi
0x1800142e7  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800142ee  mov     [rbp+var_30], edi
0x1800142f1  test    edi, edi
0x1800142f3  jns     loc_180014392
0x1800142f9  test    r11, r11
0x1800142fc  jnz     short loc_180014345
0x1800142fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014305  nop     dword ptr [rax+rax+00h]
0x18001430a  mov     rcx, rax
0x18001430d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014314  test    rax, rax
0x180014317  jz      short loc_180014337
0x180014319  mov     rax, [rax]
0x18001431c  mov     edx, 7F0h
0x180014321  mov     rax, [rax+8]
0x180014325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001432a  test    eax, eax
0x18001432c  jz      short loc_180014337
0x18001432e  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014335  jmp     short loc_180014345
0x180014337  lea     r11, qword_1800DBF70
0x18001433e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r11; CallStackTracing * CallStackTracing::s_wpInstance
0x180014345  cmp     byte ptr [r11+8], 0
0x18001434a  jz      short loc_18001437B
0x18001434c  mov     rcx, r11; this
0x18001434f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180014354  mov     r9d, [rbp+var_30]; int
0x180014358  test    r9d, r9d
0x18001435b  jns     short loc_18001437B
0x18001435d  cmp     [rax+7CCh], r9d
0x180014364  jz      short loc_18001437B
0x180014366  mov     r8d, 402h; int
0x18001436c  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180014373  mov     rcx, rax; this
0x180014376  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001437b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014382  jb      loc_18001424B
0x180014388  mov     edx, 70h ; 'p'
0x18001438d  jmp     loc_180014229
0x180014392  xor     ebx, ebx
0x180014394  jmp     loc_180014472
0x180014399  mov     [rbp+var_30], 80004002h
0x1800143a0  test    r11, r11
0x1800143a3  jnz     short loc_1800143EC
0x1800143a5  call    cs:__imp_MFGetCallStackTracingWeakReference
  ... truncated ...
```
