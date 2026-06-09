# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180072580`
- end: `0x180072a74`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1268`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e70`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180072580`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007268c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007268c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072792`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800725ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800725db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800725ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800725db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800725fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800726ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800727ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007286e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072903`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800729ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800725fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800726ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800727ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007286e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072903`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800729ba`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  unsigned int v4; // r13d
  __int64 v5; // rdx
  HRESULT v6; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  BSTR bstrVal; // rax
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v45; // [rsp+88h] [rbp+10h] BYREF

  if ( a2->vt != 31 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v45, "CWMMCDIProperty::SetShellValue", 403);
    v41 = (__int64 *)CallStackTracing::s_wpInstance;
    v4 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
      CallStackTracing::s_wpInstance = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetShellValue", 403, -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -2147418113);
    goto LABEL_73;
  }
  v4 = 0;
  PropVariantClear(this + 5);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v45, "CWMMCDIProperty::SetShellValue", 372);
  v6 = PropVariantClear(this + 4);
  if ( v6 >= 0 )
  {
    v6 = PropVariantCopy(this + 4, a2);
    if ( v6 >= 0 )
    {
      this[5].vt = 65;
      bstrVal = a2->bstrVal;
      if ( bstrVal )
      {
        v20 = 0x7FFFFFFF;
        do
        {
          if ( !*bstrVal )
            break;
          ++bstrVal;
          --v20;
        }
        while ( v20 );
        v13 = 0x7FFFFFFF - v20;
        v6 = v20 == 0 ? 0x80070057 : 0;
        if ( v20 )
        {
          v21 = 2 * (v20 != 0 ? 0x7FFFFFFF - v20 : 0) + 2;
          this[5].lVal = v21;
          v22 = (unsigned __int16 *)CoTaskMemAlloc(v21);
          this[5].bstrblobVal.pData = (BYTE *)v22;
          if ( v22 )
          {
            v6 = StringCchCopyW(v22, (unsigned __int64)this[5].ulVal >> 1, a2->bstrVal);
            if ( v6 < 0 )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
                CallStackTracing::s_wpInstance = v33;
                if ( v33
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                {
                  v32 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v32 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v32 + 8) )
              {
                v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                if ( *((_DWORD *)v34 + 499) != v6 )
                  CallStackContext::TraceFailure(v34, "CWMMCDIProperty::SetShellValue", 398, v6);
              }
              if ( g_wppLevels )
              {
                v12 = 33;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            v6 = -2147024882;
            if ( *((_BYTE *)v26 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v28 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v28, "CWMMCDIProperty::SetShellValue", 390, -2147024882);
            }
            if ( g_wppLevels )
            {
              v12 = 32;
              goto LABEL_13;
            }
          }
          goto LABEL_73;
        }
      }
      else
      {
        v6 = -2147024809;
      }
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != v6 )
          CallStackContext::TraceFailure(v37, "CWMMCDIProperty::SetShellValue", 386, v6);
      }
      if ( g_wppLevels )
      {
        v12 = 31;
        goto LABEL_13;
      }
      goto LABEL_73;
    }
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != v6 )
        CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetShellValue", 374, v6);
    }
    if ( g_wppLevels )
    {
      v12 = 30;
      goto LABEL_13;
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v6 )
        CallStackContext::TraceFailure(v11, "CWMMCDIProperty::SetShellValue", 372, v6);
    }
    if ( g_wppLevels )
    {
      v12 = 29;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v6);
    }
  }
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v45);
  return v4;
}

```

## disassembly

```asm
0x180072580  push    rbx
0x180072582  push    rbp
0x180072583  push    rsi
0x180072584  push    rdi
0x180072585  push    r12
0x180072587  push    r13
0x180072589  push    r14
0x18007258b  push    r15
0x18007258d  sub     rsp, 38h
0x180072591  mov     eax, 1Fh
0x180072596  mov     rbp, rdx
0x180072599  mov     rsi, rcx
0x18007259c  cmp     [rdx], ax
0x18007259f  jnz     loc_180072987
0x1800725a5  xor     ebx, ebx
0x1800725a7  add     rcx, 78h ; 'x'; pvar
0x1800725ab  mov     r13d, ebx
0x1800725ae  call    cs:__imp_PropVariantClear
0x1800725b5  nop     dword ptr [rax+rax+00h]
0x1800725ba  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x1800725c1  mov     r8d, 174h; int
0x1800725c7  mov     rdx, r14; char *
0x1800725ca  lea     rcx, [rsp+78h+arg_8]; this
0x1800725d2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800725d7  lea     rcx, [rsi+60h]; pvar
0x1800725db  call    cs:__imp_PropVariantClear
0x1800725e2  nop     dword ptr [rax+rax+00h]
0x1800725e7  mov     edi, eax
0x1800725e9  test    eax, eax
0x1800725eb  jns     loc_180072685
0x1800725f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800725f8  test    rcx, rcx
0x1800725fb  jnz     short loc_180072644
0x1800725fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072604  nop     dword ptr [rax+rax+00h]
0x180072609  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072610  mov     rcx, rax
0x180072613  test    rax, rax
0x180072616  jz      short loc_180072636
0x180072618  mov     rax, [rax]
0x18007261b  mov     edx, 7F0h
0x180072620  mov     rax, [rax+8]
0x180072624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072629  test    eax, eax
0x18007262b  jz      short loc_180072636
0x18007262d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072634  jmp     short loc_180072644
0x180072636  lea     rcx, qword_1800DBF70; this
0x18007263d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072644  cmp     [rcx+8], bl
0x180072647  jz      short loc_18007266A
0x180072649  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007264e  cmp     [rax+7CCh], edi
0x180072654  jz      short loc_18007266A
0x180072656  mov     r9d, edi; int
0x180072659  mov     r8d, 174h; int
0x18007265f  mov     rdx, r14; char *
0x180072662  mov     rcx, rax; this
0x180072665  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007266a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072671  jb      loc_180072A52
0x180072677  mov     edx, 1Dh
0x18007267c  mov     [rsp+78h+var_58], edi
0x180072680  jmp     loc_180072A38
0x180072685  mov     rdx, rbp; pvarSrc
0x180072688  lea     rcx, [rsi+60h]; pvarDest
0x18007268c  call    cs:__imp_PropVariantCopy
0x180072693  nop     dword ptr [rax+rax+00h]
0x180072698  mov     edi, eax
0x18007269a  test    eax, eax
0x18007269c  jns     loc_180072732
0x1800726a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726a9  test    rcx, rcx
0x1800726ac  jnz     short loc_1800726F5
0x1800726ae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800726b5  nop     dword ptr [rax+rax+00h]
0x1800726ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726c1  mov     rcx, rax
0x1800726c4  test    rax, rax
0x1800726c7  jz      short loc_1800726E7
0x1800726c9  mov     rax, [rax]
0x1800726cc  mov     edx, 7F0h
0x1800726d1  mov     rax, [rax+8]
0x1800726d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800726da  test    eax, eax
0x1800726dc  jz      short loc_1800726E7
0x1800726de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726e5  jmp     short loc_1800726F5
0x1800726e7  lea     rcx, qword_1800DBF70; this
0x1800726ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726f5  cmp     [rcx+8], bl
0x1800726f8  jz      short loc_18007271B
0x1800726fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800726ff  cmp     [rax+7CCh], edi
0x180072705  jz      short loc_18007271B
0x180072707  mov     r9d, edi; int
0x18007270a  mov     r8d, 176h; int
0x180072710  mov     rdx, r14; char *
0x180072713  mov     rcx, rax; this
0x180072716  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007271b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072722  jb      loc_180072A52
0x180072728  mov     edx, 1Eh
0x18007272d  jmp     loc_18007267C
0x180072732  mov     word ptr [rsi+78h], 41h ; 'A'
0x180072738  mov     rax, [rbp+8]
0x18007273c  test    rax, rax
0x18007273f  jz      loc_1800728F2
0x180072745  mov     edx, 7FFFFFFFh
0x18007274a  mov     ecx, edx
0x18007274c  cmp     [rax], bx
0x18007274f  jz      short loc_18007275B
0x180072751  add     rax, 2
0x180072755  sub     rcx, 1
0x180072759  jnz     short loc_18007274C
0x18007275b  mov     rax, rcx
0x18007275e  neg     rax
0x180072761  mov     rax, rcx
0x180072764  sbb     edi, edi
0x180072766  sub     rdx, rcx
0x180072769  not     edi
0x18007276b  and     edi, 80070057h
0x180072771  neg     rax
0x180072774  sbb     rax, rax
0x180072777  and     rax, rdx
0x18007277a  test    rcx, rcx
0x18007277d  jz      loc_1800728F7
0x180072783  lea     eax, ds:2[rax*2]
0x18007278a  mov     ecx, eax; cb
0x18007278c  mov     [rsi+80h], eax
0x180072792  call    cs:__imp_CoTaskMemAlloc
0x180072799  nop     dword ptr [rax+rax+00h]
0x18007279e  mov     [rsi+88h], rax
0x1800727a5  test    rax, rax
0x1800727a8  jnz     loc_180072843
0x1800727ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800727b5  test    rcx, rcx
0x1800727b8  jnz     short loc_180072801
0x1800727ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800727c1  nop     dword ptr [rax+rax+00h]
0x1800727c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800727cd  mov     rcx, rax
0x1800727d0  test    rax, rax
0x1800727d3  jz      short loc_1800727F3
0x1800727d5  mov     rax, [rax]
0x1800727d8  mov     edx, 7F0h
0x1800727dd  mov     rax, [rax+8]
0x1800727e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727e6  test    eax, eax
0x1800727e8  jz      short loc_1800727F3
0x1800727ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800727f1  jmp     short loc_180072801
0x1800727f3  lea     rcx, qword_1800DBF70; this
0x1800727fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072801  mov     edi, 8007000Eh
0x180072806  cmp     [rcx+8], bl
0x180072809  jz      short loc_18007282C
0x18007280b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072810  cmp     [rax+7CCh], edi
0x180072816  jz      short loc_18007282C
0x180072818  mov     r9d, edi; int
0x18007281b  mov     r8d, 186h; int
0x180072821  mov     rdx, r14; char *
0x180072824  mov     rcx, rax; this
0x180072827  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007282c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072833  jb      loc_180072A52
0x180072839  mov     edx, 20h ; ' '
0x18007283e  jmp     loc_18007267C
0x180072843  mov     edx, [rsi+80h]
0x180072849  mov     rcx, rax; unsigned __int16 *
0x18007284c  mov     r8, [rbp+8]; unsigned __int16 *
0x180072850  shr     rdx, 1; unsigned __int64
0x180072853  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072858  mov     edi, eax
0x18007285a  test    eax, eax
0x18007285c  jns     loc_180072A52
0x180072862  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072869  test    rcx, rcx
0x18007286c  jnz     short loc_1800728B5
0x18007286e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072875  nop     dword ptr [rax+rax+00h]
0x18007287a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072881  mov     rcx, rax
0x180072884  test    rax, rax
0x180072887  jz      short loc_1800728A7
0x180072889  mov     rax, [rax]
0x18007288c  mov     edx, 7F0h
0x180072891  mov     rax, [rax+8]
0x180072895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007289a  test    eax, eax
0x18007289c  jz      short loc_1800728A7
0x18007289e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800728a5  jmp     short loc_1800728B5
0x1800728a7  lea     rcx, qword_1800DBF70; this
0x1800728ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800728b5  cmp     [rcx+8], bl
0x1800728b8  jz      short loc_1800728DB
0x1800728ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800728bf  cmp     [rax+7CCh], edi
0x1800728c5  jz      short loc_1800728DB
0x1800728c7  mov     r9d, edi; int
0x1800728ca  mov     r8d, 18Eh; int
0x1800728d0  mov     rdx, r14; char *
0x1800728d3  mov     rcx, rax; this
0x1800728d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800728db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800728e2  jb      loc_180072A52
0x1800728e8  mov     edx, 21h ; '!'
0x1800728ed  jmp     loc_18007267C
0x1800728f2  mov     edi, 80070057h
0x1800728f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800728fe  test    rcx, rcx
0x180072901  jnz     short loc_18007294A
0x180072903  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007290a  nop     dword ptr [rax+rax+00h]
0x18007290f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072916  mov     rcx, rax
0x180072919  test    rax, rax
0x18007291c  jz      short loc_18007293C
0x18007291e  mov     rax, [rax]
0x180072921  mov     edx, 7F0h
0x180072926  mov     rax, [rax+8]
0x18007292a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007292f  test    eax, eax
0x180072931  jz      short loc_18007293C
0x180072933  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007293a  jmp     short loc_18007294A
0x18007293c  lea     rcx, qword_1800DBF70; this
0x180072943  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007294a  cmp     [rcx+8], bl
0x18007294d  jz      short loc_180072970
0x18007294f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072954  cmp     [rax+7CCh], edi
0x18007295a  jz      short loc_180072970
0x18007295c  mov     r9d, edi; int
0x18007295f  mov     r8d, 182h; int
0x180072965  mov     rdx, r14; char *
0x180072968  mov     rcx, rax; this
0x18007296b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072970  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072977  jb      loc_180072A52
0x18007297d  mov     edx, 1Fh
0x180072982  jmp     loc_18007267C
0x180072987  mov     edi, 193h
0x18007298c  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x180072993  mov     r8d, edi; int
0x180072996  lea     rcx, [rsp+78h+arg_8]; this
0x18007299e  mov     rdx, r14; char *
0x1800729a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800729a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800729ad  xor     ebx, ebx
0x1800729af  mov     r13d, 8000FFFFh
0x1800729b5  test    rcx, rcx
0x1800729b8  jnz     short loc_180072A01
0x1800729ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800729c1  nop     dword ptr [rax+rax+00h]
0x1800729c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800729cd  mov     rcx, rax
0x1800729d0  test    rax, rax
0x1800729d3  jz      short loc_1800729F3
0x1800729d5  mov     rax, [rax]
0x1800729d8  mov     edx, 7F0h
0x1800729dd  mov     rax, [rax+8]
0x1800729e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729e6  test    eax, eax
0x1800729e8  jz      short loc_1800729F3
0x1800729ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800729f1  jmp     short loc_180072A01
0x1800729f3  lea     rcx, qword_1800DBF70; this
0x1800729fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072a01  cmp     [rcx+8], bl
0x180072a04  jz      short loc_180072A25
0x180072a06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072a0b  cmp     [rax+7CCh], r13d
0x180072a12  jz      short loc_180072A25
0x180072a14  mov     r9d, r13d; int
0x180072a17  mov     r8d, edi; int
0x180072a1a  mov     rdx, r14; char *
0x180072a1d  mov     rcx, rax; this
0x180072a20  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072a25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072a2c  jb      short loc_180072A52
0x180072a2e  mov     edx, 22h ; '"'
0x180072a33  mov     [rsp+78h+var_58], r13d
0x180072a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180072a3f  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180072a46  mov     r9, rsi
0x180072a49  mov     rcx, [rcx+10h]
0x180072a4d  call    WPP_SF_qD
0x180072a52  lea     rcx, [rsp+78h+arg_8]; this
0x180072a5a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180072a5f  mov     eax, r13d
0x180072a62  add     rsp, 38h
0x180072a66  pop     r15
0x180072a68  pop     r14
0x180072a6a  pop     r13
0x180072a6c  pop     r12
0x180072a6e  pop     rdi
0x180072a6f  pop     rsi
  ... truncated ...
```
