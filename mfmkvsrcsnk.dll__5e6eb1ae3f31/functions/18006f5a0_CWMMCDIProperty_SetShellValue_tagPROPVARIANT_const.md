# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18006f5a0`
- end: `0x18006fa57`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1207`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006c24`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18006f5a0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006f69a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006f69a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f794`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006f5ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006f5f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006f5ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006f5f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f6b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f7b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f864`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f9a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f6b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f7b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f864`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f9a4`

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
        v41 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v32 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v26 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v35 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18006f5a0  push    rbx
0x18006f5a2  push    rbp
0x18006f5a3  push    rsi
0x18006f5a4  push    rdi
0x18006f5a5  push    r12
0x18006f5a7  push    r13
0x18006f5a9  push    r14
0x18006f5ab  push    r15
0x18006f5ad  sub     rsp, 38h
0x18006f5b1  mov     eax, 1Fh
0x18006f5b6  mov     rbp, rdx
0x18006f5b9  mov     rsi, rcx
0x18006f5bc  cmp     [rdx], ax
0x18006f5bf  jnz     loc_18006F971
0x18006f5c5  xor     ebx, ebx
0x18006f5c7  add     rcx, 78h ; 'x'; pvar
0x18006f5cb  mov     r13d, ebx
0x18006f5ce  call    cs:__imp_PropVariantClear
0x18006f5d4  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x18006f5db  mov     r8d, 174h; int
0x18006f5e1  mov     rdx, r14; char *
0x18006f5e4  lea     rcx, [rsp+78h+arg_8]; this
0x18006f5ec  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006f5f1  lea     rcx, [rsi+60h]; pvar
0x18006f5f5  call    cs:__imp_PropVariantClear
0x18006f5fb  mov     edi, eax
0x18006f5fd  test    eax, eax
0x18006f5ff  jns     loc_18006F693
0x18006f605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f60c  test    rcx, rcx
0x18006f60f  jnz     short loc_18006F652
0x18006f611  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f617  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f61e  mov     rcx, rax
0x18006f621  test    rax, rax
0x18006f624  jz      short loc_18006F644
0x18006f626  mov     rax, [rax]
0x18006f629  mov     edx, 7F0h
0x18006f62e  mov     rax, [rax+8]
0x18006f632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f637  test    eax, eax
0x18006f639  jz      short loc_18006F644
0x18006f63b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f642  jmp     short loc_18006F652
0x18006f644  lea     rcx, qword_1800D6F70; this
0x18006f64b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f652  cmp     [rcx+8], bl
0x18006f655  jz      short loc_18006F678
0x18006f657  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f65c  cmp     [rax+7CCh], edi
0x18006f662  jz      short loc_18006F678
0x18006f664  mov     r9d, edi; int
0x18006f667  mov     r8d, 174h; int
0x18006f66d  mov     rdx, r14; char *
0x18006f670  mov     rcx, rax; this
0x18006f673  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f678  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f67f  jb      loc_18006FA36
0x18006f685  mov     edx, 1Dh
0x18006f68a  mov     [rsp+78h+var_58], edi
0x18006f68e  jmp     loc_18006FA1C
0x18006f693  mov     rdx, rbp; pvarSrc
0x18006f696  lea     rcx, [rsi+60h]; pvarDest
0x18006f69a  call    cs:__imp_PropVariantCopy
0x18006f6a0  mov     edi, eax
0x18006f6a2  test    eax, eax
0x18006f6a4  jns     loc_18006F734
0x18006f6aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f6b1  test    rcx, rcx
0x18006f6b4  jnz     short loc_18006F6F7
0x18006f6b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f6bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f6c3  mov     rcx, rax
0x18006f6c6  test    rax, rax
0x18006f6c9  jz      short loc_18006F6E9
0x18006f6cb  mov     rax, [rax]
0x18006f6ce  mov     edx, 7F0h
0x18006f6d3  mov     rax, [rax+8]
0x18006f6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6dc  test    eax, eax
0x18006f6de  jz      short loc_18006F6E9
0x18006f6e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f6e7  jmp     short loc_18006F6F7
0x18006f6e9  lea     rcx, qword_1800D6F70; this
0x18006f6f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f6f7  cmp     [rcx+8], bl
0x18006f6fa  jz      short loc_18006F71D
0x18006f6fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f701  cmp     [rax+7CCh], edi
0x18006f707  jz      short loc_18006F71D
0x18006f709  mov     r9d, edi; int
0x18006f70c  mov     r8d, 176h; int
0x18006f712  mov     rdx, r14; char *
0x18006f715  mov     rcx, rax; this
0x18006f718  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f71d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f724  jb      loc_18006FA36
0x18006f72a  mov     edx, 1Eh
0x18006f72f  jmp     loc_18006F68A
0x18006f734  mov     word ptr [rsi+78h], 41h ; 'A'
0x18006f73a  mov     rax, [rbp+8]
0x18006f73e  test    rax, rax
0x18006f741  jz      loc_18006F8E2
0x18006f747  mov     edx, 7FFFFFFFh
0x18006f74c  mov     ecx, edx
0x18006f74e  cmp     [rax], bx
0x18006f751  jz      short loc_18006F75D
0x18006f753  add     rax, 2
0x18006f757  sub     rcx, 1
0x18006f75b  jnz     short loc_18006F74E
0x18006f75d  mov     rax, rcx
0x18006f760  neg     rax
0x18006f763  mov     rax, rcx
0x18006f766  sbb     edi, edi
0x18006f768  sub     rdx, rcx
0x18006f76b  not     edi
0x18006f76d  and     edi, 80070057h
0x18006f773  neg     rax
0x18006f776  sbb     rax, rax
0x18006f779  and     rax, rdx
0x18006f77c  test    rcx, rcx
0x18006f77f  jz      loc_18006F8E7
0x18006f785  lea     eax, ds:2[rax*2]
0x18006f78c  mov     ecx, eax; cb
0x18006f78e  mov     [rsi+80h], eax
0x18006f794  call    cs:__imp_CoTaskMemAlloc
0x18006f79a  mov     [rsi+88h], rax
0x18006f7a1  test    rax, rax
0x18006f7a4  jnz     loc_18006F839
0x18006f7aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f7b1  test    rcx, rcx
0x18006f7b4  jnz     short loc_18006F7F7
0x18006f7b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f7bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f7c3  mov     rcx, rax
0x18006f7c6  test    rax, rax
0x18006f7c9  jz      short loc_18006F7E9
0x18006f7cb  mov     rax, [rax]
0x18006f7ce  mov     edx, 7F0h
0x18006f7d3  mov     rax, [rax+8]
0x18006f7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7dc  test    eax, eax
0x18006f7de  jz      short loc_18006F7E9
0x18006f7e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f7e7  jmp     short loc_18006F7F7
0x18006f7e9  lea     rcx, qword_1800D6F70; this
0x18006f7f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f7f7  mov     edi, 8007000Eh
0x18006f7fc  cmp     [rcx+8], bl
0x18006f7ff  jz      short loc_18006F822
0x18006f801  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f806  cmp     [rax+7CCh], edi
0x18006f80c  jz      short loc_18006F822
0x18006f80e  mov     r9d, edi; int
0x18006f811  mov     r8d, 186h; int
0x18006f817  mov     rdx, r14; char *
0x18006f81a  mov     rcx, rax; this
0x18006f81d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f822  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f829  jb      loc_18006FA36
0x18006f82f  mov     edx, 20h ; ' '
0x18006f834  jmp     loc_18006F68A
0x18006f839  mov     edx, [rsi+80h]
0x18006f83f  mov     rcx, rax; unsigned __int16 *
0x18006f842  mov     r8, [rbp+8]; unsigned __int16 *
0x18006f846  shr     rdx, 1; unsigned __int64
0x18006f849  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f84e  mov     edi, eax
0x18006f850  test    eax, eax
0x18006f852  jns     loc_18006FA36
0x18006f858  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f85f  test    rcx, rcx
0x18006f862  jnz     short loc_18006F8A5
0x18006f864  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f86a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f871  mov     rcx, rax
0x18006f874  test    rax, rax
0x18006f877  jz      short loc_18006F897
0x18006f879  mov     rax, [rax]
0x18006f87c  mov     edx, 7F0h
0x18006f881  mov     rax, [rax+8]
0x18006f885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f88a  test    eax, eax
0x18006f88c  jz      short loc_18006F897
0x18006f88e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f895  jmp     short loc_18006F8A5
0x18006f897  lea     rcx, qword_1800D6F70; this
0x18006f89e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f8a5  cmp     [rcx+8], bl
0x18006f8a8  jz      short loc_18006F8CB
0x18006f8aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f8af  cmp     [rax+7CCh], edi
0x18006f8b5  jz      short loc_18006F8CB
0x18006f8b7  mov     r9d, edi; int
0x18006f8ba  mov     r8d, 18Eh; int
0x18006f8c0  mov     rdx, r14; char *
0x18006f8c3  mov     rcx, rax; this
0x18006f8c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f8cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f8d2  jb      loc_18006FA36
0x18006f8d8  mov     edx, 21h ; '!'
0x18006f8dd  jmp     loc_18006F68A
0x18006f8e2  mov     edi, 80070057h
0x18006f8e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f8ee  test    rcx, rcx
0x18006f8f1  jnz     short loc_18006F934
0x18006f8f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f8f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f900  mov     rcx, rax
0x18006f903  test    rax, rax
0x18006f906  jz      short loc_18006F926
0x18006f908  mov     rax, [rax]
0x18006f90b  mov     edx, 7F0h
0x18006f910  mov     rax, [rax+8]
0x18006f914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f919  test    eax, eax
0x18006f91b  jz      short loc_18006F926
0x18006f91d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f924  jmp     short loc_18006F934
0x18006f926  lea     rcx, qword_1800D6F70; this
0x18006f92d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f934  cmp     [rcx+8], bl
0x18006f937  jz      short loc_18006F95A
0x18006f939  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f93e  cmp     [rax+7CCh], edi
0x18006f944  jz      short loc_18006F95A
0x18006f946  mov     r9d, edi; int
0x18006f949  mov     r8d, 182h; int
0x18006f94f  mov     rdx, r14; char *
0x18006f952  mov     rcx, rax; this
0x18006f955  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f95a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f961  jb      loc_18006FA36
0x18006f967  mov     edx, 1Fh
0x18006f96c  jmp     loc_18006F68A
0x18006f971  mov     edi, 193h
0x18006f976  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x18006f97d  mov     r8d, edi; int
0x18006f980  lea     rcx, [rsp+78h+arg_8]; this
0x18006f988  mov     rdx, r14; char *
0x18006f98b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006f990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f997  xor     ebx, ebx
0x18006f999  mov     r13d, 8000FFFFh
0x18006f99f  test    rcx, rcx
0x18006f9a2  jnz     short loc_18006F9E5
0x18006f9a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f9aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f9b1  mov     rcx, rax
0x18006f9b4  test    rax, rax
0x18006f9b7  jz      short loc_18006F9D7
0x18006f9b9  mov     rax, [rax]
0x18006f9bc  mov     edx, 7F0h
0x18006f9c1  mov     rax, [rax+8]
0x18006f9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9ca  test    eax, eax
0x18006f9cc  jz      short loc_18006F9D7
0x18006f9ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f9d5  jmp     short loc_18006F9E5
0x18006f9d7  lea     rcx, qword_1800D6F70; this
0x18006f9de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f9e5  cmp     [rcx+8], bl
0x18006f9e8  jz      short loc_18006FA09
0x18006f9ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f9ef  cmp     [rax+7CCh], r13d
0x18006f9f6  jz      short loc_18006FA09
0x18006f9f8  mov     r9d, r13d; int
0x18006f9fb  mov     r8d, edi; int
0x18006f9fe  mov     rdx, r14; char *
0x18006fa01  mov     rcx, rax; this
0x18006fa04  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fa09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fa10  jb      short loc_18006FA36
0x18006fa12  mov     edx, 22h ; '"'
0x18006fa17  mov     [rsp+78h+var_58], r13d
0x18006fa1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fa23  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18006fa2a  mov     r9, rsi
0x18006fa2d  mov     rcx, [rcx+10h]
0x18006fa31  call    WPP_SF_qD
0x18006fa36  lea     rcx, [rsp+78h+arg_8]; this
0x18006fa3e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006fa43  mov     eax, r13d
0x18006fa46  add     rsp, 38h
0x18006fa4a  pop     r15
0x18006fa4c  pop     r14
0x18006fa4e  pop     r13
0x18006fa50  pop     r12
0x18006fa52  pop     rdi
0x18006fa53  pop     rsi
0x18006fa54  pop     rbp
0x18006fa55  pop     rbx
0x18006fa56  retn
```
