# MkvMfSourceLib::MkvMfSource::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800135f0`
- end: `0x180013b86`
- name: `?GetService@MkvMfSource@MkvMfSourceLib@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1430`
- prototype: `int(MkvMfSourceLib::MkvMfSource *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800023e0`
- `0x180007728`
- `0x1800097f0`
- `0x18000b3d0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000e3e4`
- `0x1800129b8`
- `0x1800135f0`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013844`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013844`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800136d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013894`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800139ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800136d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013894`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800139ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a8f`

## string_xrefs

- `0x180013630`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x18001373b`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x1800138fc`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x180013a56`: `MkvMfSourceLib::MkvMfSource::GetService`
- `0x180013af7`: `MkvMfSourceLib::MkvMfSource::GetService`

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
  int IsEqualGUID; // eax
  char *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  HRESULT Instance; // eax
  __int64 v25; // rax
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  void *v31; // r8
  char *v32; // r8
  int CanCastTo; // edi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 *v38; // r11
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  int v44; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v45[4]; // [rsp+34h] [rbp-2Ch] BYREF
  char *v46; // [rsp+38h] [rbp-28h]
  int *v47; // [rsp+40h] [rbp-20h]
  _QWORD v48[2]; // [rsp+48h] [rbp-18h] BYREF

  v44 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v45, "MkvMfSourceLib::MkvMfSource::GetService", 995);
  v12 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 82) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 82) + 296LL))(*((_QWORD *)this + 82));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 82) + 280LL))(
                                                            *((_QWORD *)this + 82),
                                                            v48);
    *((_DWORD *)ThreadRelativeContext + 504) = v14;
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v15 = (char *)this - 32;
  v46 = (char *)this - 32;
  v47 = &v44;
  if ( !a4 )
  {
    v44 = -2147467261;
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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( v44 < 0 && *((_DWORD *)v17 + 499) != v44 )
        CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::GetService", 997, v44);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        (char *)this - 32,
        v44);
    v18 = v44;
    goto LABEL_87;
  }
  *a4 = 0;
  v19 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 )
    v19 = *(_QWORD *)a2->Data4 - *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4;
  if ( v19 )
  {
    v22 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1 )
      v22 = *(_QWORD *)a2->Data4 - *(_QWORD *)MF_PROPERTY_HANDLER_SERVICE.Data4;
    if ( !v22 )
    {
      v23 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IInitializeWithStream.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IInitializeWithStream.Data1 )
        v23 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IInitializeWithStream.Data4;
      if ( !v23 )
      {
        Instance = CoCreateInstance(&CLSID_MFMKVPropertyHandler, 0, 1u, &IID_IInitializeWithStream, a4);
LABEL_86:
        v18 = Instance;
        goto LABEL_87;
      }
      v25 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
        v25 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
      if ( !v25 )
      {
        v48[0] = (char *)this - 32;
        v48[1] = &v44;
        Instance = MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(
                     (MkvMfSourceLib::MkvMfSource *)((char *)this - 32),
                     (struct IPropertyStore **)a4);
        goto LABEL_86;
      }
      v44 = -2147467262;
      if ( !v12 )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, v10, v11);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( v44 < 0 && *((_DWORD *)v27 + 499) != v44 )
          CallStackContext::TraceFailure(v27, "MkvMfSourceLib::MkvMfSource::GetService", 1019, v44);
      }
      if ( !g_wppLevels )
      {
LABEL_48:
        v18 = v44;
        goto LABEL_87;
      }
      v28 = 111;
LABEL_47:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        (char *)this - 32,
        v44);
      goto LABEL_48;
    }
    v29 = *(_QWORD *)&a2->Data1 - MF_MEDIA_ENGINE_TIMEDTEXTDATASOURCE;
    if ( *(_QWORD *)&a2->Data1 == MF_MEDIA_ENGINE_TIMEDTEXTDATASOURCE )
      v29 = *(_QWORD *)a2->Data4 + 0x3FD99E9A0CA3FD75LL;
    if ( v29 )
    {
      Instance = -1072875846;
      v44 = -1072875846;
      if ( g_wppLevels )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          (char *)this - 32,
          -1072875846);
        Instance = v44;
      }
      goto LABEL_86;
    }
    if ( !*((_QWORD *)this + 51) )
    {
      v44 = -2147467262;
      if ( !v12 )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, 0, v11);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( v44 < 0 && *((_DWORD *)v42 + 499) != v44 )
          CallStackContext::TraceFailure(v42, "MkvMfSourceLib::MkvMfSource::GetService", 1031, v44);
      }
      if ( !g_wppLevels )
        goto LABEL_48;
      v28 = 113;
      goto LABEL_47;
    }
    if ( (unsigned int)InlineIsEqualGUID(a3, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a4 = v31;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 8LL))(v31);
      CanCastTo = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v30, &GUID_5a0d8439_09d0_40f3_8dc3_d8b695bb1ecc) )
      {
        *a4 = v32;
        CanCastTo = 0;
      }
      else
      {
        CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                      v32 + 8,
                      a3,
                      a4);
        if ( CanCastTo < 0 )
        {
LABEL_60:
          v44 = CanCastTo;
          if ( CanCastTo >= 0 )
          {
            v18 = 0;
            goto LABEL_87;
          }
          if ( !v38 )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v35, v34, v36, v37);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( v44 < 0 && *((_DWORD *)v40 + 499) != v44 )
              CallStackContext::TraceFailure(v40, "MkvMfSourceLib::MkvMfSource::GetService", 1026, v44);
          }
          if ( !g_wppLevels )
            goto LABEL_48;
          v28 = 112;
          goto LABEL_47;
        }
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
    }
    v38 = (__int64 *)CallStackTracing::s_wpInstance;
    goto LABEL_60;
  }
  IsEqualGUID = InlineIsEqualGUID(a3, &GUID_00000000_0000_0000_c000_000000000046);
  v21 = (char *)this - 32;
  if ( IsEqualGUID )
  {
    *a4 = v15;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v21);
    v18 = 0;
  }
  else
  {
    v18 = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,IMFMediaSource,IMFMediaSourceEx,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::CanCastTo(
            v21,
            a3,
            a4);
    if ( v18 >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
  }
LABEL_87:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v45);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800135f0  mov     [rsp-28h+arg_8], rbx
0x1800135f5  mov     [rsp-28h+arg_10], rsi
0x1800135fa  push    rbp
0x1800135fb  push    rdi
0x1800135fc  push    r13
0x1800135fe  push    r14
0x180013600  push    r15
0x180013602  mov     rbp, rsp
0x180013605  sub     rsp, 60h
0x180013609  mov     rax, cs:__security_cookie
0x180013610  xor     rax, rsp
0x180013613  mov     [rbp+var_8], rax
0x180013617  mov     rsi, r9
0x18001361a  mov     r14, r8
0x18001361d  mov     r15, rdx
0x180013620  mov     r13, rcx
0x180013623  mov     [rbp+var_30], 0
0x18001362a  mov     r8d, 3E3h; int
0x180013630  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180013637  lea     rcx, [rbp+var_2C]; this
0x18001363b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180013640  nop
0x180013641  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013648  cmp     byte ptr [r11+8], 0
0x18001364d  jz      short loc_1800136AE
0x18001364f  cmp     qword ptr [r13+290h], 0
0x180013657  jz      short loc_1800136AE
0x180013659  mov     rcx, r11; this
0x18001365c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013661  mov     rdi, rax
0x180013664  mov     rcx, [r13+290h]
0x18001366b  mov     rdx, [rcx]
0x18001366e  mov     rax, [rdx+128h]
0x180013675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001367a  mov     ebx, eax
0x18001367c  mov     rcx, [r13+290h]
0x180013683  mov     rdx, [rcx]
0x180013686  mov     rax, [rdx+118h]
0x18001368d  lea     rdx, [rbp+var_18]
0x180013691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013696  movups  xmm0, xmmword ptr [rax]
0x180013699  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800136a1  mov     [rdi+7E0h], ebx
0x1800136a7  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800136ae  lea     rbx, [r13-20h]
0x1800136b2  mov     [rbp+var_28], rbx
0x1800136b6  lea     rax, [rbp+var_30]
0x1800136ba  mov     [rbp+var_20], rax
0x1800136be  test    rsi, rsi
0x1800136c1  jnz     loc_18001377E
0x1800136c7  mov     [rbp+var_30], 80004003h
0x1800136ce  test    r11, r11
0x1800136d1  jnz     short loc_180013714
0x1800136d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800136d9  mov     rcx, rax
0x1800136dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800136e3  test    rax, rax
0x1800136e6  jz      short loc_180013706
0x1800136e8  mov     rax, [rax]
0x1800136eb  mov     edx, 7F0h
0x1800136f0  mov     rax, [rax+8]
0x1800136f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136f9  test    eax, eax
0x1800136fb  jz      short loc_180013706
0x1800136fd  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013704  jmp     short loc_180013714
0x180013706  lea     r11, qword_1800D6F70
0x18001370d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r11; CallStackTracing * CallStackTracing::s_wpInstance
0x180013714  cmp     byte ptr [r11+8], 0
0x180013719  jz      short loc_18001374A
0x18001371b  mov     rcx, r11; this
0x18001371e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013723  mov     r9d, [rbp+var_30]; int
0x180013727  test    r9d, r9d
0x18001372a  jns     short loc_18001374A
0x18001372c  cmp     [rax+7CCh], r9d
0x180013733  jz      short loc_18001374A
0x180013735  mov     r8d, 3E5h; int
0x18001373b  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180013742  mov     rcx, rax; this
0x180013745  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001374a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013751  jb      short loc_180013779
0x180013753  mov     edx, 6Ch ; 'l'
0x180013758  mov     eax, [rbp+var_30]
0x18001375b  mov     dword ptr [rsp+60h+ppv], eax
0x18001375f  mov     r9, rbx
0x180013762  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180013769  mov     rcx, cs:WPP_GLOBAL_Control
0x180013770  mov     rcx, [rcx+10h]
0x180013774  call    WPP_SF_qD
0x180013779  mov     ebx, [rbp+var_30]
0x18001377c  jmp     short loc_1800137EA
0x18001377e  mov     qword ptr [rsi], 0
0x180013785  mov     rax, [r15]
0x180013788  sub     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x18001378f  jnz     short loc_18001379C
0x180013791  mov     rax, [r15+8]
0x180013795  sub     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x18001379c  test    rax, rax
0x18001379f  jnz     short loc_1800137EF
0x1800137a1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800137a8  mov     rcx, r14
0x1800137ab  call    InlineIsEqualGUID
0x1800137b0  mov     rcx, rbx
0x1800137b3  test    eax, eax
0x1800137b5  jnz     short loc_1800137D9
0x1800137b7  mov     r8, rsi
0x1800137ba  mov     rdx, r14
0x1800137bd  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@UIMFMediaSource@@UIMFMediaSourceEx@@UIMFRateSupport@@UIMFRateControl@@UIMFGetService@@UIMFMediaEventGenerator@@UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,IMFMediaSource,IMFMediaSourceEx,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x1800137c2  mov     ebx, eax
0x1800137c4  test    eax, eax
0x1800137c6  js      short loc_1800137EA
0x1800137c8  mov     rcx, [rsi]
0x1800137cb  mov     rdx, [rcx]
0x1800137ce  mov     rax, [rdx+8]
0x1800137d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137d7  jmp     short loc_1800137EA
0x1800137d9  mov     [rsi], rbx
0x1800137dc  mov     rax, [rbx]
0x1800137df  mov     rax, [rax+8]
0x1800137e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e8  xor     ebx, ebx
0x1800137ea  jmp     loc_180013B56
0x1800137ef  mov     rax, [r15]
0x1800137f2  sub     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data1
0x1800137f9  jnz     short loc_180013806
0x1800137fb  mov     rax, [r15+8]
0x1800137ff  sub     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data4
0x180013806  test    rax, rax
0x180013809  jnz     loc_180013943
0x18001380f  mov     rax, [r14]
0x180013812  sub     rax, qword ptr cs:IID_IInitializeWithStream.Data1
0x180013819  jnz     short loc_180013826
0x18001381b  mov     rax, [r14+8]
0x18001381f  sub     rax, qword ptr cs:IID_IInitializeWithStream.Data4
0x180013826  test    rax, rax
0x180013829  jnz     short loc_18001384F
0x18001382b  mov     [rsp+60h+ppv], rsi; ppv
0x180013830  lea     r9, IID_IInitializeWithStream; riid
0x180013837  xor     edx, edx; pUnkOuter
0x180013839  lea     r8d, [rax+1]; dwClsContext
0x18001383d  lea     rcx, CLSID_MFMKVPropertyHandler; rclsid
0x180013844  call    cs:__imp_CoCreateInstance
0x18001384a  jmp     loc_180013B54
0x18001384f  mov     rax, [r14]
0x180013852  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180013859  jnz     short loc_180013866
0x18001385b  mov     rax, [r14+8]
0x18001385f  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180013866  test    rax, rax
0x180013869  jnz     short loc_180013888
0x18001386b  mov     [rbp+var_18], rbx
0x18001386f  lea     rax, [rbp+var_30]
0x180013873  mov     [rbp+var_10], rax
0x180013877  mov     rdx, rsi; struct IPropertyStore **
0x18001387a  mov     rcx, rbx; this
0x18001387d  call    ?GetMetadataPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z; MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(IPropertyStore * *)
0x180013882  nop
0x180013883  jmp     loc_180013B54
0x180013888  mov     [rbp+var_30], 80004002h
0x18001388f  test    r11, r11
0x180013892  jnz     short loc_1800138D5
0x180013894  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001389a  mov     rcx, rax
0x18001389d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800138a4  test    rax, rax
0x1800138a7  jz      short loc_1800138C7
0x1800138a9  mov     rax, [rax]
0x1800138ac  mov     edx, 7F0h
0x1800138b1  mov     rax, [rax+8]
0x1800138b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ba  test    eax, eax
0x1800138bc  jz      short loc_1800138C7
0x1800138be  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800138c5  jmp     short loc_1800138D5
0x1800138c7  lea     r11, qword_1800D6F70
0x1800138ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r11; CallStackTracing * CallStackTracing::s_wpInstance
0x1800138d5  cmp     byte ptr [r11+8], 0
0x1800138da  jz      short loc_18001390B
0x1800138dc  mov     rcx, r11; this
0x1800138df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800138e4  mov     r9d, [rbp+var_30]; int
0x1800138e8  test    r9d, r9d
0x1800138eb  jns     short loc_18001390B
0x1800138ed  cmp     [rax+7CCh], r9d
0x1800138f4  jz      short loc_18001390B
0x1800138f6  mov     r8d, 3FBh; int
0x1800138fc  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180013903  mov     rcx, rax; this
0x180013906  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001390b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013912  jb      short loc_18001393B
0x180013914  mov     edx, 6Fh ; 'o'
0x180013919  mov     eax, [rbp+var_30]
0x18001391c  mov     dword ptr [rsp+60h+ppv], eax
0x180013920  mov     r9, rbx
0x180013923  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001392a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013931  mov     rcx, [rcx+10h]
0x180013935  call    WPP_SF_qD
0x18001393a  nop
0x18001393b  mov     ebx, [rbp+var_30]
0x18001393e  jmp     loc_180013B56
0x180013943  mov     rax, [r15]
0x180013946  sub     rax, cs:MF_MEDIA_ENGINE_TIMEDTEXTDATASOURCE
0x18001394d  jnz     short loc_18001395A
0x18001394f  mov     rax, [r15+8]
0x180013953  sub     rax, cs:qword_1800B7148
0x18001395a  test    rax, rax
0x18001395d  jnz     loc_180013B1D
0x180013963  mov     r8, [r13+198h]
0x18001396a  test    r8, r8
0x18001396d  jz      loc_180013A83
0x180013973  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001397a  mov     rcx, r14
0x18001397d  call    InlineIsEqualGUID
0x180013982  test    eax, eax
0x180013984  jnz     short loc_1800139C3
0x180013986  lea     rdx, _GUID_5a0d8439_09d0_40f3_8dc3_d8b695bb1ecc
0x18001398d  call    InlineIsEqualGUID
0x180013992  test    eax, eax
0x180013994  jz      short loc_18001399D
0x180013996  mov     [rsi], r8
0x180013999  xor     edi, edi
0x18001399b  jmp     short loc_1800139B2
0x18001399d  lea     rcx, [r8+8]
0x1800139a1  mov     r8, rsi
0x1800139a4  mov     rdx, r14
0x1800139a7  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x1800139ac  mov     edi, eax
0x1800139ae  test    eax, eax
0x1800139b0  js      short loc_1800139DE
0x1800139b2  mov     rcx, [rsi]
0x1800139b5  mov     rdx, [rcx]
0x1800139b8  mov     rax, [rdx+8]
0x1800139bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139c1  jmp     short loc_1800139D7
0x1800139c3  mov     [rsi], r8
0x1800139c6  mov     rax, [r8]
0x1800139c9  mov     rcx, r8
0x1800139cc  mov     rax, [rax+8]
0x1800139d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d5  xor     edi, edi
0x1800139d7  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800139de  mov     [rbp+var_30], edi
0x1800139e1  test    edi, edi
0x1800139e3  jns     loc_180013A7C
0x1800139e9  test    r11, r11
0x1800139ec  jnz     short loc_180013A2F
0x1800139ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800139f4  mov     rcx, rax
0x1800139f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800139fe  test    rax, rax
0x180013a01  jz      short loc_180013A21
0x180013a03  mov     rax, [rax]
0x180013a06  mov     edx, 7F0h
0x180013a0b  mov     rax, [rax+8]
0x180013a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a14  test    eax, eax
0x180013a16  jz      short loc_180013A21
0x180013a18  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a1f  jmp     short loc_180013A2F
0x180013a21  lea     r11, qword_1800D6F70
0x180013a28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r11; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a2f  cmp     byte ptr [r11+8], 0
0x180013a34  jz      short loc_180013A65
0x180013a36  mov     rcx, r11; this
0x180013a39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013a3e  mov     r9d, [rbp+var_30]; int
0x180013a42  test    r9d, r9d
0x180013a45  jns     short loc_180013A65
0x180013a47  cmp     [rax+7CCh], r9d
0x180013a4e  jz      short loc_180013A65
0x180013a50  mov     r8d, 402h; int
0x180013a56  lea     rdx, aMkvmfsourcelib_59; "MkvMfSourceLib::MkvMfSource::GetService"
0x180013a5d  mov     rcx, rax; this
0x180013a60  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013a65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013a6c  jb      loc_18001393B
0x180013a72  mov     edx, 70h ; 'p'
0x180013a77  jmp     loc_180013919
0x180013a7c  xor     ebx, ebx
0x180013a7e  jmp     loc_180013B56
0x180013a83  mov     [rbp+var_30], 80004002h
0x180013a8a  test    r11, r11
0x180013a8d  jnz     short loc_180013AD0
0x180013a8f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013a95  mov     rcx, rax
0x180013a98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a9f  test    rax, rax
0x180013aa2  jz      short loc_180013AC2
0x180013aa4  mov     rax, [rax]
0x180013aa7  mov     edx, 7F0h
0x180013aac  mov     rax, [rax+8]
0x180013ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab5  test    eax, eax
0x180013ab7  jz      short loc_180013AC2
0x180013ab9  mov     r11, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013ac0  jmp     short loc_180013AD0
  ... truncated ...
```
