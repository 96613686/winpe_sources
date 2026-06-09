# CMFPropHandlerBase::AddProperty(_tagpropertykey const &,tagPROPVARIANT const &,CMFProperty::MF_MDACCESS,CMFProperty::MF_MDVALUESOURCE)

- ea: `0x18003ac10`
- end: `0x18003b173`
- name: `?AddProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@W4MF_MDACCESS@CMFProperty@@W4MF_MDVALUESOURCE@5@@Z`
- size: `1379`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003abd0`
- `0x18003ac10`
- `0x18003d458`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ac89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003adf7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003af5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b00c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b09e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ac89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003adf7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003af5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b00c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b09e`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::AddProperty(__int64 *a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  _QWORD v42[2]; // [rsp+30h] [rbp-10h] BYREF
  int v43; // [rsp+70h] [rbp+30h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMFPropHandlerBase::AddProperty", 534);
  v9 = *a1;
  v42[0] = 0;
  v43 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD *))(v9 + 56))(a1, a2, v42);
  if ( v11 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::AddProperty", 540, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_81;
    v15 = 43;
    goto LABEL_12;
  }
  if ( a5 )
  {
    if ( a5 != 1 )
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v40, "CMFPropHandlerBase::AddProperty", 553, -2147418113);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v37 = 46;
      goto LABEL_80;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v42[0] + 296LL))(v42[0], a3);
    if ( v11 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != v11 )
          CallStackContext::TraceFailure(v23, "CMFPropHandlerBase::AddProperty", 548, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v15 = 45;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, a1, v11);
      goto LABEL_81;
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v42[0] + 288LL))(v42[0], a3);
    if ( v11 < 0 )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v11 )
          CallStackContext::TraceFailure(v19, "CMFPropHandlerBase::AddProperty", 544, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v15 = 44;
      goto LABEL_12;
    }
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(*(_QWORD *)v42[0] + 168LL))(v42[0], MF_MD_ACCESSTYPE, a4);
  if ( v11 < 0 )
  {
    v25 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != v11 )
        CallStackContext::TraceFailure(v27, "CMFPropHandlerBase::AddProperty", 556, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_81;
    v15 = 47;
    goto LABEL_12;
  }
  v28 = v42[0];
  *(_OWORD *)(v42[0] + 76LL) = *(_OWORD *)a2;
  *(_DWORD *)(v28 + 92) = *(_DWORD *)(a2 + 16);
  v11 = CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(a1 + 6, a2, v42);
  if ( v11 < 0 )
  {
    v30 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != v11 )
        CallStackContext::TraceFailure(v32, "CMFPropHandlerBase::AddProperty", 560, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_81;
    v15 = 48;
    goto LABEL_12;
  }
  if ( (unsigned int)CTDynArray<_tagpropertykey,20>::Add(a1 + 53, a2, &v43) )
    goto LABEL_83;
  v34 = (__int64 *)CallStackTracing::s_wpInstance;
  v11 = -2147418113;
  if ( !CallStackTracing::s_wpInstance )
  {
    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
    CallStackTracing::s_wpInstance = v35;
    if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
    {
      v34 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v34 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v34 + 8) )
  {
    v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
    if ( *((_DWORD *)v36 + 499) != -2147418113 )
      CallStackContext::TraceFailure(v36, "CMFPropHandlerBase::AddProperty", 564, -2147418113);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v37 = 49;
LABEL_80:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v37,
      WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
      a1,
      -2147418113);
  }
LABEL_81:
  if ( v42[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42[0] + 16LL))(v42[0]);
    v42[0] = 0;
  }
LABEL_83:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003ac10  mov     [rsp-28h+arg_8], rbx
0x18003ac15  mov     [rsp-28h+arg_10], rsi
0x18003ac1a  push    rbp
0x18003ac1b  push    rdi
0x18003ac1c  push    r13
0x18003ac1e  push    r14
0x18003ac20  push    r15
0x18003ac22  mov     rbp, rsp
0x18003ac25  sub     rsp, 40h
0x18003ac29  mov     r14, r8
0x18003ac2c  lea     r13, aCmfprophandler_14; "CMFPropHandlerBase::AddProperty"
0x18003ac33  mov     rdi, rdx
0x18003ac36  mov     rsi, rcx
0x18003ac39  mov     rdx, r13; char *
0x18003ac3c  lea     rcx, [rbp+arg_0]; this
0x18003ac40  mov     r8d, 216h; int
0x18003ac46  mov     r15d, r9d
0x18003ac49  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ac4e  mov     rax, [rsi]
0x18003ac51  lea     r8, [rbp+var_10]
0x18003ac55  mov     rdx, rdi
0x18003ac58  mov     [rbp+var_10], 0
0x18003ac60  mov     rcx, rsi
0x18003ac63  mov     [rbp+arg_0], 0
0x18003ac6a  mov     rax, [rax+38h]
0x18003ac6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac73  mov     ebx, eax
0x18003ac75  test    eax, eax
0x18003ac77  jns     loc_18003AD0C
0x18003ac7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ac84  test    rcx, rcx
0x18003ac87  jnz     short loc_18003ACCA
0x18003ac89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ac8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ac96  mov     rcx, rax
0x18003ac99  test    rax, rax
0x18003ac9c  jz      short loc_18003ACBC
0x18003ac9e  mov     rax, [rax]
0x18003aca1  mov     edx, 7F0h
0x18003aca6  mov     rax, [rax+8]
0x18003acaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acaf  test    eax, eax
0x18003acb1  jz      short loc_18003ACBC
0x18003acb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003acba  jmp     short loc_18003ACCA
0x18003acbc  lea     rcx, qword_18006EB20; this
0x18003acc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003acca  cmp     byte ptr [rcx+8], 0
0x18003acce  jz      short loc_18003ACF1
0x18003acd0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003acd5  cmp     [rax+7CCh], ebx
0x18003acdb  jz      short loc_18003ACF1
0x18003acdd  mov     r9d, ebx; int
0x18003ace0  mov     r8d, 21Ch; int
0x18003ace6  mov     rdx, r13; char *
0x18003ace9  mov     rcx, rax; this
0x18003acec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003acf1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003acf6  cmp     al, 1
0x18003acf8  jb      loc_18003B132
0x18003acfe  mov     edx, 2Bh ; '+'
0x18003ad03  mov     [rsp+40h+var_20], ebx
0x18003ad07  jmp     loc_18003B118
0x18003ad0c  mov     eax, [rbp+arg_20]
0x18003ad0f  test    eax, eax
0x18003ad11  jnz     loc_18003ADC2
0x18003ad17  mov     rcx, [rbp+var_10]
0x18003ad1b  mov     rdx, r14
0x18003ad1e  mov     rax, [rcx]
0x18003ad21  mov     rax, [rax+120h]
0x18003ad28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad2d  mov     ebx, eax
0x18003ad2f  test    eax, eax
0x18003ad31  jns     loc_18003AE76
0x18003ad37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad3e  test    rcx, rcx
0x18003ad41  jnz     short loc_18003AD84
0x18003ad43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ad49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad50  mov     rcx, rax
0x18003ad53  test    rax, rax
0x18003ad56  jz      short loc_18003AD76
0x18003ad58  mov     rax, [rax]
0x18003ad5b  mov     edx, 7F0h
0x18003ad60  mov     rax, [rax+8]
0x18003ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad69  test    eax, eax
0x18003ad6b  jz      short loc_18003AD76
0x18003ad6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad74  jmp     short loc_18003AD84
0x18003ad76  lea     rcx, qword_18006EB20; this
0x18003ad7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad84  cmp     byte ptr [rcx+8], 0
0x18003ad88  jz      short loc_18003ADAB
0x18003ad8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ad8f  cmp     [rax+7CCh], ebx
0x18003ad95  jz      short loc_18003ADAB
0x18003ad97  mov     r9d, ebx; int
0x18003ad9a  mov     r8d, 220h; int
0x18003ada0  mov     rdx, r13; char *
0x18003ada3  mov     rcx, rax; this
0x18003ada6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003adab  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003adb0  cmp     al, 1
0x18003adb2  jb      loc_18003B132
0x18003adb8  mov     edx, 2Ch ; ','
0x18003adbd  jmp     loc_18003AD03
0x18003adc2  cmp     eax, 1
0x18003adc5  jnz     loc_18003B08B
0x18003adcb  mov     rcx, [rbp+var_10]
0x18003adcf  mov     rdx, r14
0x18003add2  mov     rax, [rcx]
0x18003add5  mov     rax, [rax+128h]
0x18003addc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ade1  mov     ebx, eax
0x18003ade3  test    eax, eax
0x18003ade5  jns     loc_18003AE76
0x18003adeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003adf2  test    rcx, rcx
0x18003adf5  jnz     short loc_18003AE38
0x18003adf7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003adfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae04  mov     rcx, rax
0x18003ae07  test    rax, rax
0x18003ae0a  jz      short loc_18003AE2A
0x18003ae0c  mov     rax, [rax]
0x18003ae0f  mov     edx, 7F0h
0x18003ae14  mov     rax, [rax+8]
0x18003ae18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae1d  test    eax, eax
0x18003ae1f  jz      short loc_18003AE2A
0x18003ae21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae28  jmp     short loc_18003AE38
0x18003ae2a  lea     rcx, qword_18006EB20; this
0x18003ae31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae38  cmp     byte ptr [rcx+8], 0
0x18003ae3c  jz      short loc_18003AE5F
0x18003ae3e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ae43  cmp     [rax+7CCh], ebx
0x18003ae49  jz      short loc_18003AE5F
0x18003ae4b  mov     r9d, ebx; int
0x18003ae4e  mov     r8d, 224h; int
0x18003ae54  mov     rdx, r13; char *
0x18003ae57  mov     rcx, rax; this
0x18003ae5a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ae5f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ae64  cmp     al, 1
0x18003ae66  jb      loc_18003B132
0x18003ae6c  mov     edx, 2Dh ; '-'
0x18003ae71  jmp     loc_18003AD03
0x18003ae76  mov     rcx, [rbp+var_10]
0x18003ae7a  lea     rdx, MF_MD_ACCESSTYPE
0x18003ae81  mov     r8d, r15d
0x18003ae84  mov     rax, [rcx]
0x18003ae87  mov     rax, [rax+0A8h]
0x18003ae8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae93  mov     ebx, eax
0x18003ae95  test    eax, eax
0x18003ae97  jns     loc_18003AF28
0x18003ae9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aea4  test    rcx, rcx
0x18003aea7  jnz     short loc_18003AEEA
0x18003aea9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003aeaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aeb6  mov     rcx, rax
0x18003aeb9  test    rax, rax
0x18003aebc  jz      short loc_18003AEDC
0x18003aebe  mov     rax, [rax]
0x18003aec1  mov     edx, 7F0h
0x18003aec6  mov     rax, [rax+8]
0x18003aeca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aecf  test    eax, eax
0x18003aed1  jz      short loc_18003AEDC
0x18003aed3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aeda  jmp     short loc_18003AEEA
0x18003aedc  lea     rcx, qword_18006EB20; this
0x18003aee3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aeea  cmp     byte ptr [rcx+8], 0
0x18003aeee  jz      short loc_18003AF11
0x18003aef0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003aef5  cmp     [rax+7CCh], ebx
0x18003aefb  jz      short loc_18003AF11
0x18003aefd  mov     r9d, ebx; int
0x18003af00  mov     r8d, 22Ch; int
0x18003af06  mov     rdx, r13; char *
0x18003af09  mov     rcx, rax; this
0x18003af0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003af11  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003af16  cmp     al, 1
0x18003af18  jb      loc_18003B132
0x18003af1e  mov     edx, 2Fh ; '/'
0x18003af23  jmp     loc_18003AD03
0x18003af28  mov     rcx, [rbp+var_10]
0x18003af2c  lea     r8, [rbp+var_10]
0x18003af30  movups  xmm0, xmmword ptr [rdi]
0x18003af33  mov     rdx, rdi
0x18003af36  movups  xmmword ptr [rcx+4Ch], xmm0
0x18003af3a  mov     eax, [rdi+10h]
0x18003af3d  mov     [rcx+5Ch], eax
0x18003af40  lea     rcx, [rsi+30h]
0x18003af44  call    ?Insert@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJAEBU_tagpropertykey@@AEBQEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(_tagpropertykey const &,CMFProperty * const &)
0x18003af49  mov     ebx, eax
0x18003af4b  test    eax, eax
0x18003af4d  jns     loc_18003AFDE
0x18003af53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003af5a  test    rcx, rcx
0x18003af5d  jnz     short loc_18003AFA0
0x18003af5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003af65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003af6c  mov     rcx, rax
0x18003af6f  test    rax, rax
0x18003af72  jz      short loc_18003AF92
0x18003af74  mov     rax, [rax]
0x18003af77  mov     edx, 7F0h
0x18003af7c  mov     rax, [rax+8]
0x18003af80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af85  test    eax, eax
0x18003af87  jz      short loc_18003AF92
0x18003af89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003af90  jmp     short loc_18003AFA0
0x18003af92  lea     rcx, qword_18006EB20; this
0x18003af99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003afa0  cmp     byte ptr [rcx+8], 0
0x18003afa4  jz      short loc_18003AFC7
0x18003afa6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003afab  cmp     [rax+7CCh], ebx
0x18003afb1  jz      short loc_18003AFC7
0x18003afb3  mov     r9d, ebx; int
0x18003afb6  mov     r8d, 230h; int
0x18003afbc  mov     rdx, r13; char *
0x18003afbf  mov     rcx, rax; this
0x18003afc2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003afc7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003afcc  cmp     al, 1
0x18003afce  jb      loc_18003B132
0x18003afd4  mov     edx, 30h ; '0'
0x18003afd9  jmp     loc_18003AD03
0x18003afde  lea     rcx, [rsi+1A8h]
0x18003afe5  mov     rdx, rdi
0x18003afe8  lea     r8, [rbp+arg_0]
0x18003afec  call    ?Add@?$CTDynArray@U_tagpropertykey@@$0BE@@@QEAAHAEBU_tagpropertykey@@PEAK@Z; CTDynArray<_tagpropertykey,20>::Add(_tagpropertykey const &,ulong *)
0x18003aff1  test    eax, eax
0x18003aff3  jnz     loc_18003B14F
0x18003aff9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b000  mov     edi, 8000FFFFh
0x18003b005  mov     ebx, edi
0x18003b007  test    rcx, rcx
0x18003b00a  jnz     short loc_18003B04D
0x18003b00c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b012  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b019  mov     rcx, rax
0x18003b01c  test    rax, rax
0x18003b01f  jz      short loc_18003B03F
0x18003b021  mov     rax, [rax]
0x18003b024  mov     edx, 7F0h
0x18003b029  mov     rax, [rax+8]
0x18003b02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b032  test    eax, eax
0x18003b034  jz      short loc_18003B03F
0x18003b036  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b03d  jmp     short loc_18003B04D
0x18003b03f  lea     rcx, qword_18006EB20; this
0x18003b046  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b04d  cmp     byte ptr [rcx+8], 0
0x18003b051  jz      short loc_18003B074
0x18003b053  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b058  cmp     [rax+7CCh], edi
0x18003b05e  jz      short loc_18003B074
0x18003b060  mov     r9d, edi; int
0x18003b063  mov     r8d, 234h; int
0x18003b069  mov     rdx, r13; char *
0x18003b06c  mov     rcx, rax; this
0x18003b06f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b074  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b079  cmp     al, 1
0x18003b07b  jb      loc_18003B132
0x18003b081  mov     edx, 31h ; '1'
0x18003b086  jmp     loc_18003B114
0x18003b08b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b092  mov     edi, 8000FFFFh
0x18003b097  mov     ebx, edi
0x18003b099  test    rcx, rcx
0x18003b09c  jnz     short loc_18003B0DF
0x18003b09e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b0a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b0ab  mov     rcx, rax
0x18003b0ae  test    rax, rax
0x18003b0b1  jz      short loc_18003B0D1
0x18003b0b3  mov     rax, [rax]
0x18003b0b6  mov     edx, 7F0h
0x18003b0bb  mov     rax, [rax+8]
0x18003b0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0c4  test    eax, eax
0x18003b0c6  jz      short loc_18003B0D1
0x18003b0c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b0cf  jmp     short loc_18003B0DF
0x18003b0d1  lea     rcx, qword_18006EB20; this
0x18003b0d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b0df  cmp     byte ptr [rcx+8], 0
0x18003b0e3  jz      short loc_18003B106
  ... truncated ...
```
