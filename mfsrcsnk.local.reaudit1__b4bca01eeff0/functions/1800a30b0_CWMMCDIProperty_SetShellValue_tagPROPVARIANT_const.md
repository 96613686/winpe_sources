# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x1800a30b0`
- end: `0x1800a3582`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1234`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x180079d08`
- `0x1800a30b0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3135`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a31ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a329d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a335c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a34c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3135`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a31ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a329d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a335c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a34c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3334`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3334`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800a31c5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800a31c5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a30ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a3113`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a30ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a3113`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  unsigned int v4; // r13d
  __int64 v5; // rdx
  HRESULT v6; // esi
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // eax
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  int v24; // edi
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  char v36; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp+50h] BYREF

  v37 = 0;
  if ( a2->vt == 31 )
  {
    v4 = 0;
    PropVariantClear(this + 5);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CWMMCDIProperty::SetShellValue", 372);
    v6 = PropVariantClear(this + 4);
    if ( v6 >= 0 )
    {
      v6 = PropVariantCopy(this + 4, a2);
      if ( v6 >= 0 )
      {
        this[5].vt = 65;
        v6 = StringCchLengthW(a2->bstrVal, 0x7FFFFFFFu, &v37);
        if ( v6 >= 0 )
        {
          v19 = 2 * v37 + 2;
          this[5].lVal = v19;
          v20 = (unsigned __int16 *)CoTaskMemAlloc(v19);
          this[5].bstrblobVal.pData = (BYTE *)v20;
          if ( v20 )
          {
            v24 = StringCchCopyW(v20, (unsigned __int64)this[5].ulVal >> 1, a2->bstrVal);
            if ( v24 >= 0 )
              goto LABEL_69;
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v24 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetShellValue", 398, v24);
            }
            if ( !g_wppLevels )
              goto LABEL_69;
            v26 = 33;
          }
          else
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
              {
                v22 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v22 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            v24 = -2147024882;
            if ( *((_BYTE *)v22 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v25 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v25, "CWMMCDIProperty::SetShellValue", 390, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_69;
            v26 = 32;
          }
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v26,
            WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            v24);
          goto LABEL_69;
        }
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != v6 )
            CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetShellValue", 386, v6);
        }
        if ( g_wppLevels )
        {
          v10 = 31;
          goto LABEL_13;
        }
      }
      else
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)v14 + 499) != v6 )
            CallStackContext::TraceFailure(v14, "CWMMCDIProperty::SetShellValue", 374, v6);
        }
        if ( g_wppLevels )
        {
          v10 = 30;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)v9 + 499) != v6 )
          CallStackContext::TraceFailure(v9, "CWMMCDIProperty::SetShellValue", 372, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 29;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v6);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CWMMCDIProperty::SetShellValue", 403);
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
    v4 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v34, "CWMMCDIProperty::SetShellValue", 403, -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -2147418113);
  }
LABEL_69:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return v4;
}

```

## disassembly

```asm
0x1800a30b0  mov     [rsp-38h+arg_0], rbx
0x1800a30b5  push    rbp
0x1800a30b6  push    rsi
0x1800a30b7  push    rdi
0x1800a30b8  push    r12
0x1800a30ba  push    r13
0x1800a30bc  push    r14
0x1800a30be  push    r15
0x1800a30c0  mov     rbp, rsp
0x1800a30c3  sub     rsp, 30h
0x1800a30c7  mov     eax, 1Fh
0x1800a30cc  mov     [rbp+arg_10], 0
0x1800a30d4  mov     rdi, rdx
0x1800a30d7  mov     rbx, rcx
0x1800a30da  cmp     [rdx], ax
0x1800a30dd  jnz     loc_1800A349A
0x1800a30e3  add     rcx, 78h ; 'x'; pvar
0x1800a30e7  xor     r13d, r13d
0x1800a30ea  call    cs:__imp_PropVariantClear
0x1800a30f1  nop     dword ptr [rax+rax+00h]
0x1800a30f6  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x1800a30fd  mov     r8d, 174h; int
0x1800a3103  mov     rdx, r14; char *
0x1800a3106  lea     rcx, [rbp+arg_8]; this
0x1800a310a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a310f  lea     rcx, [rbx+60h]; pvar
0x1800a3113  call    cs:__imp_PropVariantClear
0x1800a311a  nop     dword ptr [rax+rax+00h]
0x1800a311f  mov     esi, eax
0x1800a3121  test    eax, eax
0x1800a3123  jns     loc_1800A31BE
0x1800a3129  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3130  test    rcx, rcx
0x1800a3133  jnz     short loc_1800A317C
0x1800a3135  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a313c  nop     dword ptr [rax+rax+00h]
0x1800a3141  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3148  mov     rcx, rax
0x1800a314b  test    rax, rax
0x1800a314e  jz      short loc_1800A316E
0x1800a3150  mov     rax, [rax]
0x1800a3153  mov     edx, 7F0h
0x1800a3158  mov     rax, [rax+8]
0x1800a315c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3161  test    eax, eax
0x1800a3163  jz      short loc_1800A316E
0x1800a3165  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a316c  jmp     short loc_1800A317C
0x1800a316e  lea     rcx, qword_1801B97E0; this
0x1800a3175  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a317c  cmp     [rcx+8], r13b
0x1800a3180  jz      short loc_1800A31A3
0x1800a3182  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3187  cmp     [rax+7CCh], esi
0x1800a318d  jz      short loc_1800A31A3
0x1800a318f  mov     r9d, esi; int
0x1800a3192  mov     r8d, 174h; int
0x1800a3198  mov     rdx, r14; char *
0x1800a319b  mov     rcx, rax; this
0x1800a319e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a31a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a31aa  jb      loc_1800A3560
0x1800a31b0  mov     edx, 1Dh
0x1800a31b5  mov     [rsp+30h+var_10], esi
0x1800a31b9  jmp     loc_1800A3546
0x1800a31be  mov     rdx, rdi; pvarSrc
0x1800a31c1  lea     rcx, [rbx+60h]; pvarDest
0x1800a31c5  call    cs:__imp_PropVariantCopy
0x1800a31cc  nop     dword ptr [rax+rax+00h]
0x1800a31d1  xor     r15d, r15d
0x1800a31d4  mov     esi, eax
0x1800a31d6  test    eax, eax
0x1800a31d8  jns     loc_1800A326F
0x1800a31de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a31e5  test    rcx, rcx
0x1800a31e8  jnz     short loc_1800A3231
0x1800a31ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a31f1  nop     dword ptr [rax+rax+00h]
0x1800a31f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a31fd  mov     rcx, rax
0x1800a3200  test    rax, rax
0x1800a3203  jz      short loc_1800A3223
0x1800a3205  mov     rax, [rax]
0x1800a3208  mov     edx, 7F0h
0x1800a320d  mov     rax, [rax+8]
0x1800a3211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3216  test    eax, eax
0x1800a3218  jz      short loc_1800A3223
0x1800a321a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3221  jmp     short loc_1800A3231
0x1800a3223  lea     rcx, qword_1801B97E0; this
0x1800a322a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3231  cmp     [rcx+8], r15b
0x1800a3235  jz      short loc_1800A3258
0x1800a3237  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a323c  cmp     [rax+7CCh], esi
0x1800a3242  jz      short loc_1800A3258
0x1800a3244  mov     r9d, esi; int
0x1800a3247  mov     r8d, 176h; int
0x1800a324d  mov     rdx, r14; char *
0x1800a3250  mov     rcx, rax; this
0x1800a3253  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3258  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a325f  jb      loc_1800A3560
0x1800a3265  mov     edx, 1Eh
0x1800a326a  jmp     loc_1800A31B5
0x1800a326f  mov     word ptr [rbx+78h], 41h ; 'A'
0x1800a3275  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x1800a3279  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800a327d  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800a3282  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a3287  mov     esi, eax
0x1800a3289  test    eax, eax
0x1800a328b  jns     loc_1800A3322
0x1800a3291  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3298  test    rcx, rcx
0x1800a329b  jnz     short loc_1800A32E4
0x1800a329d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a32a4  nop     dword ptr [rax+rax+00h]
0x1800a32a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a32b0  mov     rcx, rax
0x1800a32b3  test    rax, rax
0x1800a32b6  jz      short loc_1800A32D6
0x1800a32b8  mov     rax, [rax]
0x1800a32bb  mov     edx, 7F0h
0x1800a32c0  mov     rax, [rax+8]
0x1800a32c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a32c9  test    eax, eax
0x1800a32cb  jz      short loc_1800A32D6
0x1800a32cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a32d4  jmp     short loc_1800A32E4
0x1800a32d6  lea     rcx, qword_1801B97E0; this
0x1800a32dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a32e4  cmp     [rcx+8], r15b
0x1800a32e8  jz      short loc_1800A330B
0x1800a32ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a32ef  cmp     [rax+7CCh], esi
0x1800a32f5  jz      short loc_1800A330B
0x1800a32f7  mov     r9d, esi; int
0x1800a32fa  mov     r8d, 182h; int
0x1800a3300  mov     rdx, r14; char *
0x1800a3303  mov     rcx, rax; this
0x1800a3306  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a330b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3312  jb      loc_1800A3560
0x1800a3318  mov     edx, 1Fh
0x1800a331d  jmp     loc_1800A31B5
0x1800a3322  mov     eax, dword ptr [rbp+arg_10]
0x1800a3325  lea     eax, ds:2[rax*2]
0x1800a332c  mov     ecx, eax; cb
0x1800a332e  mov     [rbx+80h], eax
0x1800a3334  call    cs:__imp_CoTaskMemAlloc
0x1800a333b  nop     dword ptr [rax+rax+00h]
0x1800a3340  mov     [rbx+88h], rax
0x1800a3347  test    rax, rax
0x1800a334a  jnz     loc_1800A33EA
0x1800a3350  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3357  test    rcx, rcx
0x1800a335a  jnz     short loc_1800A33A3
0x1800a335c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3363  nop     dword ptr [rax+rax+00h]
0x1800a3368  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a336f  mov     rcx, rax
0x1800a3372  test    rax, rax
0x1800a3375  jz      short loc_1800A3395
0x1800a3377  mov     rax, [rax]
0x1800a337a  mov     edx, 7F0h
0x1800a337f  mov     rax, [rax+8]
0x1800a3383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3388  test    eax, eax
0x1800a338a  jz      short loc_1800A3395
0x1800a338c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3393  jmp     short loc_1800A33A3
0x1800a3395  lea     rcx, qword_1801B97E0; this
0x1800a339c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a33a3  mov     edi, 8007000Eh
0x1800a33a8  cmp     [rcx+8], r15b
0x1800a33ac  jz      short loc_1800A33CF
0x1800a33ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a33b3  cmp     [rax+7CCh], edi
0x1800a33b9  jz      short loc_1800A33CF
0x1800a33bb  mov     r9d, edi; int
0x1800a33be  mov     r8d, 186h; int
0x1800a33c4  mov     rdx, r14; char *
0x1800a33c7  mov     rcx, rax; this
0x1800a33ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a33cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a33d6  jb      loc_1800A3560
0x1800a33dc  mov     edx, 20h ; ' '
0x1800a33e1  mov     [rsp+30h+var_10], edi
0x1800a33e5  jmp     loc_1800A3546
0x1800a33ea  mov     edx, [rbx+80h]
0x1800a33f0  mov     rcx, rax; unsigned __int16 *
0x1800a33f3  mov     r8, [rdi+8]; unsigned __int16 *
0x1800a33f7  shr     rdx, 1; unsigned __int64
0x1800a33fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a33ff  mov     edi, eax
0x1800a3401  test    eax, eax
0x1800a3403  jns     loc_1800A3560
0x1800a3409  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3410  test    rcx, rcx
0x1800a3413  jnz     short loc_1800A345C
0x1800a3415  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a341c  nop     dword ptr [rax+rax+00h]
0x1800a3421  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3428  mov     rcx, rax
0x1800a342b  test    rax, rax
0x1800a342e  jz      short loc_1800A344E
0x1800a3430  mov     rax, [rax]
0x1800a3433  mov     edx, 7F0h
0x1800a3438  mov     rax, [rax+8]
0x1800a343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3441  test    eax, eax
0x1800a3443  jz      short loc_1800A344E
0x1800a3445  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a344c  jmp     short loc_1800A345C
0x1800a344e  lea     rcx, qword_1801B97E0; this
0x1800a3455  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a345c  cmp     [rcx+8], r15b
0x1800a3460  jz      short loc_1800A3483
0x1800a3462  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3467  cmp     [rax+7CCh], edi
0x1800a346d  jz      short loc_1800A3483
0x1800a346f  mov     r9d, edi; int
0x1800a3472  mov     r8d, 18Eh; int
0x1800a3478  mov     rdx, r14; char *
0x1800a347b  mov     rcx, rax; this
0x1800a347e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3483  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a348a  jb      loc_1800A3560
0x1800a3490  mov     edx, 21h ; '!'
0x1800a3495  jmp     loc_1800A33E1
0x1800a349a  mov     edi, 193h
0x1800a349f  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x1800a34a6  mov     r8d, edi; int
0x1800a34a9  lea     rcx, [rbp+arg_8]; this
0x1800a34ad  mov     rdx, r14; char *
0x1800a34b0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a34b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a34bc  mov     r13d, 8000FFFFh
0x1800a34c2  test    rcx, rcx
0x1800a34c5  jnz     short loc_1800A350E
0x1800a34c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a34ce  nop     dword ptr [rax+rax+00h]
0x1800a34d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a34da  mov     rcx, rax
0x1800a34dd  test    rax, rax
0x1800a34e0  jz      short loc_1800A3500
0x1800a34e2  mov     rax, [rax]
0x1800a34e5  mov     edx, 7F0h
0x1800a34ea  mov     rax, [rax+8]
0x1800a34ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a34f3  test    eax, eax
0x1800a34f5  jz      short loc_1800A3500
0x1800a34f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a34fe  jmp     short loc_1800A350E
0x1800a3500  lea     rcx, qword_1801B97E0; this
0x1800a3507  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a350e  cmp     byte ptr [rcx+8], 0
0x1800a3512  jz      short loc_1800A3533
0x1800a3514  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3519  cmp     [rax+7CCh], r13d
0x1800a3520  jz      short loc_1800A3533
0x1800a3522  mov     r9d, r13d; int
0x1800a3525  mov     r8d, edi; int
0x1800a3528  mov     rdx, r14; char *
0x1800a352b  mov     rcx, rax; this
0x1800a352e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3533  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a353a  jb      short loc_1800A3560
0x1800a353c  mov     edx, 22h ; '"'
0x1800a3541  mov     [rsp+30h+var_10], r13d
0x1800a3546  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a354d  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800a3554  mov     r9, rbx
0x1800a3557  mov     rcx, [rcx+10h]
0x1800a355b  call    WPP_SF_qD
0x1800a3560  lea     rcx, [rbp+arg_8]; this
0x1800a3564  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a3569  mov     rbx, [rsp+30h+arg_0]
0x1800a356e  mov     eax, r13d
0x1800a3571  add     rsp, 30h
0x1800a3575  pop     r15
0x1800a3577  pop     r14
0x1800a3579  pop     r13
0x1800a357b  pop     r12
0x1800a357d  pop     rdi
0x1800a357e  pop     rsi
0x1800a357f  pop     rbp
0x1800a3580  retn
```
