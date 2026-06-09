# MFMkvPropertyHandler::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)

- ea: `0x18004eff0`
- end: `0x18004f75f`
- name: `?AddPresentationDescriptorProperties@MFMkvPropertyHandler@@EEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `1903`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180005c68`
- `0x180009b04`
- `0x18004eff0`
- `0x18005b110`
- `0x180065424`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f729`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f713`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f713`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f053`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f1e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f277`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f2e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f372`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f4f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f5fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f69c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f053`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f1e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f277`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f2e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f372`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f4f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f5fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f69c`

## string_xrefs

- `0x18004f0be`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`
- `0x18004f243`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`
- `0x18004f4b0`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`
- `0x18004f6ff`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MFMkvPropertyHandler::AddPresentationDescriptorProperties(
        MFMkvPropertyHandler *this,
        struct IMFPresentationDescriptor *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v11; // r8d
  unsigned int i; // r14d
  HRESULT (__stdcall *GetStreamDescriptorByIndex)(IMFPresentationDescriptor *, DWORD, BOOL *, IMFStreamDescriptor **); // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  PROPVARIANT *v17; // rdi
  __int64 (__fastcall *v18)(PROPVARIANT *, __int64 *); // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  int v28; // r8d
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  int v45; // r8d
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  int v57; // r8d
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  __int64 v64; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v65; // [rsp+38h] [rbp-61h] BYREF
  PROPVARIANT *p_pvar; // [rsp+40h] [rbp-59h] BYREF
  char v67; // [rsp+48h] [rbp-51h]
  LPVOID pv[2]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v69; // [rsp+60h] [rbp-39h]
  int v70; // [rsp+68h] [rbp-31h] BYREF
  PROPVARIANT pvar; // [rsp+70h] [rbp-29h] BYREF
  __int128 v72; // [rsp+88h] [rbp-11h] BYREF
  __int64 v73; // [rsp+98h] [rbp-1h]
  __int128 Buf1; // [rsp+A0h] [rbp+7h] BYREF

  v65 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))a2->lpVtbl->GetStreamDescriptorCount)(
         a2,
         &v65);
  if ( v5 < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
      {
        v11 = 169;
LABEL_10:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MFMkvPropertyHandler::AddPresentationDescriptorProperties",
          v11,
          v5);
        return (unsigned int)v5;
      }
    }
    return (unsigned int)v5;
  }
  for ( i = 0; i < v65; ++i )
  {
    p_pvar = 0;
    v64 = 0;
    v70 = 0;
    Buf1 = 0;
    GetStreamDescriptorByIndex = a2->lpVtbl->GetStreamDescriptorByIndex;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&p_pvar);
    v5 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, PROPVARIANT **))GetStreamDescriptorByIndex)(
           a2,
           i,
           &v70,
           &p_pvar);
    if ( v5 < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( !*((_BYTE *)v31 + 8) )
        goto LABEL_30;
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v27 + 499) == v5 )
        goto LABEL_30;
      v28 = 176;
LABEL_29:
      CallStackContext::TraceFailure(v27, "MFMkvPropertyHandler::AddPresentationDescriptorProperties", v28, v5);
      goto LABEL_30;
    }
    v17 = p_pvar;
    v18 = *(__int64 (__fastcall **)(PROPVARIANT *, __int64 *))(*(_QWORD *)&p_pvar->vt + 272LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    v5 = v18(v17, &v64);
    if ( v5 < 0 )
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( !*((_BYTE *)v29 + 8) )
        goto LABEL_30;
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v27 + 499) == v5 )
        goto LABEL_30;
      v28 = 177;
      goto LABEL_29;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v64 + 64LL))(v64, &Buf1);
    if ( v5 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != v5 )
        {
          v28 = 178;
          goto LABEL_29;
        }
      }
LABEL_30:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&p_pvar);
      return (unsigned int)v5;
    }
    if ( !memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) )
    {
      *((_DWORD *)this + 225) = 1;
    }
    else if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
    {
      *((_DWORD *)this + 226) = 1;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&p_pvar);
  }
  v5 = CWMPropHandlerBase::AddPresentationDescriptorProperties(this, a2);
  if ( v5 >= 0 )
  {
    pv[0] = (LPVOID)31;
    v69 = 0;
    pv[1] = 0;
    *(_QWORD *)&Buf1 = pv;
    BYTE8(Buf1) = 1;
    v5 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, LPVOID *, _QWORD))a2->lpVtbl->GetAllocatedString)(
           a2,
           &MF_PD_MIME_TYPE,
           &pv[1],
           0);
    if ( v5 >= 0 )
    {
      if ( !pv[1] )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v40, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v5 = -2147024882;
        if ( !*((_BYTE *)v42 + 8) )
          goto LABEL_99;
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) == -2147024882 )
          goto LABEL_99;
        v45 = 216;
        goto LABEL_66;
      }
      v5 = (*(__int64 (__fastcall **)(MFMkvPropertyHandler *, const PROPERTYKEY *, LPVOID *, _QWORD, int))(*(_QWORD *)this + 40LL))(
             this,
             &PKEY_MIMEType,
             pv,
             0,
             1);
      if ( v5 < 0 )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( !*((_BYTE *)v49 + 8) )
          goto LABEL_99;
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v44 + 499) == v5 )
          goto LABEL_99;
        v45 = 217;
LABEL_66:
        CallStackContext::TraceFailure(v44, "MFMkvPropertyHandler::AddPresentationDescriptorProperties", v45, v5);
        goto LABEL_99;
      }
    }
    memset(&pvar, 0, sizeof(pvar));
    p_pvar = &pvar;
    v67 = 1;
    if ( (int)MFGetDLNAProfileID(v39, a2, &pvar) >= 0 && pvar.vt == 4127 && pvar.lVal )
    {
      v72 = 0;
      v73 = 0;
      LOWORD(v72) = 31;
      *((_QWORD *)&v72 + 1) = *pvar.cabstr.pElems;
      v5 = (*(__int64 (__fastcall **)(MFMkvPropertyHandler *, const PROPERTYKEY *, __int128 *, _QWORD, int))(*(_QWORD *)this + 40LL))(
             this,
             &MFPKEY_Content_DLNA_Profile_ID,
             &v72,
             0,
             1);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(MFMkvPropertyHandler *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
               this,
               &PKEY_Media_DlnaProfileID,
               &pvar,
               0,
               1);
        if ( v5 >= 0 )
          goto LABEL_98;
        v61 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( !*((_BYTE *)v61 + 8) )
          goto LABEL_98;
        v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)v56 + 499) == v5 )
          goto LABEL_98;
        v57 = 235;
      }
      else
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( !*((_BYTE *)v54 + 8) )
          goto LABEL_98;
        v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
        if ( *((_DWORD *)v56 + 499) == v5 )
          goto LABEL_98;
        v57 = 234;
      }
      CallStackContext::TraceFailure(v56, "MFMkvPropertyHandler::AddPresentationDescriptorProperties", v57, v5);
    }
LABEL_98:
    PropVariantClear(&pvar);
LABEL_99:
    if ( pv[1] )
      CoTaskMemFree(pv[1]);
    return (unsigned int)v5;
  }
  v36 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
    CallStackTracing::s_wpInstance = v37;
    if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v36 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v36 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
    {
      v11 = 195;
      goto LABEL_10;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004eff0  mov     [rsp-8+arg_10], rbx
0x18004eff5  push    rbp
0x18004eff6  push    rsi
0x18004eff7  push    rdi
0x18004eff8  push    r12
0x18004effa  push    r13
0x18004effc  push    r14
0x18004effe  push    r15
0x18004f000  lea     rbp, [rsp-27h]
0x18004f005  sub     rsp, 0C0h
0x18004f00c  mov     rax, cs:__security_cookie
0x18004f013  xor     rax, rsp
0x18004f016  mov     [rbp+57h+var_40], rax
0x18004f01a  mov     r15, rdx
0x18004f01d  mov     rsi, rcx
0x18004f020  xor     r12d, r12d
0x18004f023  mov     [rbp+57h+var_B8], r12d
0x18004f027  mov     rax, [rdx]
0x18004f02a  lea     rdx, [rbp+57h+var_B8]
0x18004f02e  mov     rcx, r15
0x18004f031  mov     rax, [rax+108h]
0x18004f038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f03d  mov     ebx, eax
0x18004f03f  test    eax, eax
0x18004f041  jns     loc_18004F0D2
0x18004f047  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f04e  test    rcx, rcx
0x18004f051  jnz     short loc_18004F09A
0x18004f053  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f05a  nop     dword ptr [rax+rax+00h]
0x18004f05f  mov     rcx, rax
0x18004f062  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f069  test    rax, rax
0x18004f06c  jz      short loc_18004F08C
0x18004f06e  mov     rax, [rax]
0x18004f071  mov     edx, 7F0h
0x18004f076  mov     rax, [rax+8]
0x18004f07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f07f  test    eax, eax
0x18004f081  jz      short loc_18004F08C
0x18004f083  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f08a  jmp     short loc_18004F09A
0x18004f08c  lea     rcx, qword_1800DBF70; this
0x18004f093  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f09a  cmp     [rcx+8], r12b
0x18004f09e  jz      loc_18004F735
0x18004f0a4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f0a9  cmp     [rax+7CCh], ebx
0x18004f0af  jz      loc_18004F735
0x18004f0b5  mov     r8d, 0A9h; int
0x18004f0bb  mov     r9d, ebx; int
0x18004f0be  lea     rdx, aMfmkvpropertyh_3; "MFMkvPropertyHandler::AddPresentationDe"...
0x18004f0c5  mov     rcx, rax; this
0x18004f0c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f0cd  jmp     loc_18004F735
0x18004f0d2  mov     r14d, r12d
0x18004f0d5  mov     r13d, 1
0x18004f0db  cmp     r14d, [rbp+57h+var_B8]
0x18004f0df  jnb     loc_18004F355
0x18004f0e5  mov     [rbp+57h+var_B0], r12
0x18004f0e9  mov     [rbp+57h+var_C0], r12
0x18004f0ed  mov     [rbp+57h+var_88], r12d
0x18004f0f1  xorps   xmm0, xmm0
0x18004f0f4  movups  [rbp+57h+Buf1], xmm0
0x18004f0f8  mov     rax, [r15]
0x18004f0fb  mov     rbx, [rax+110h]
0x18004f102  lea     rcx, [rbp+57h+var_B0]
0x18004f106  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f10b  lea     r9, [rbp+57h+var_B0]
0x18004f10f  lea     r8, [rbp+57h+var_88]
0x18004f113  mov     edx, r14d
0x18004f116  mov     rcx, r15
0x18004f119  mov     rax, rbx
0x18004f11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f121  mov     ebx, eax
0x18004f123  test    eax, eax
0x18004f125  js      loc_18004F2DC
0x18004f12b  mov     rdi, [rbp+57h+var_B0]
0x18004f12f  mov     rax, [rdi]
0x18004f132  mov     rbx, [rax+110h]
0x18004f139  lea     rcx, [rbp+57h+var_C0]
0x18004f13d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f142  lea     rdx, [rbp+57h+var_C0]
0x18004f146  mov     rcx, rdi
0x18004f149  mov     rax, rbx
0x18004f14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f151  mov     ebx, eax
0x18004f153  test    eax, eax
0x18004f155  js      loc_18004F26B
0x18004f15b  mov     rcx, [rbp+57h+var_C0]
0x18004f15f  mov     rax, [rcx]
0x18004f162  lea     rdx, [rbp+57h+Buf1]
0x18004f166  mov     rax, [rax+40h]
0x18004f16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f16f  mov     ebx, eax
0x18004f171  test    eax, eax
0x18004f173  js      short loc_18004F1D4
0x18004f175  mov     r8d, 10h; Size
0x18004f17b  lea     rdx, MFMediaType_Audio; Buf2
0x18004f182  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004f186  call    memcmp_0
0x18004f18b  test    eax, eax
0x18004f18d  jnz     short loc_18004F198
0x18004f18f  mov     [rsi+384h], r13d
0x18004f196  jmp     short loc_18004F1B9
0x18004f198  mov     r8d, 10h; Size
0x18004f19e  lea     rdx, MFMediaType_Video; Buf2
0x18004f1a5  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004f1a9  call    memcmp_0
0x18004f1ae  test    eax, eax
0x18004f1b0  jnz     short loc_18004F1B9
0x18004f1b2  mov     [rsi+388h], r13d
0x18004f1b9  lea     rcx, [rbp+57h+var_C0]
0x18004f1bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f1c2  nop
0x18004f1c3  lea     rcx, [rbp+57h+var_B0]
0x18004f1c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f1cc  add     r14d, r13d
0x18004f1cf  jmp     loc_18004F0DB
0x18004f1d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f1db  test    rcx, rcx
0x18004f1de  jnz     short loc_18004F227
0x18004f1e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f1e7  nop     dword ptr [rax+rax+00h]
0x18004f1ec  mov     rcx, rax
0x18004f1ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f1f6  test    rax, rax
0x18004f1f9  jz      short loc_18004F219
0x18004f1fb  mov     rax, [rax]
0x18004f1fe  mov     edx, 7F0h
0x18004f203  mov     rax, [rax+8]
0x18004f207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f20c  test    eax, eax
0x18004f20e  jz      short loc_18004F219
0x18004f210  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f217  jmp     short loc_18004F227
0x18004f219  lea     rcx, qword_1800DBF70; this
0x18004f220  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f227  cmp     [rcx+8], r12b
0x18004f22b  jz      short loc_18004F253
0x18004f22d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f232  cmp     [rax+7CCh], ebx
0x18004f238  jz      short loc_18004F253
0x18004f23a  mov     r8d, 0B2h; int
0x18004f240  mov     r9d, ebx; int
0x18004f243  lea     rdx, aMfmkvpropertyh_3; "MFMkvPropertyHandler::AddPresentationDe"...
0x18004f24a  mov     rcx, rax; this
0x18004f24d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f252  nop
0x18004f253  lea     rcx, [rbp+57h+var_C0]
0x18004f257  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f25c  nop
0x18004f25d  lea     rcx, [rbp+57h+var_B0]
0x18004f261  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f266  jmp     loc_18004F735
0x18004f26b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f272  test    rcx, rcx
0x18004f275  jnz     short loc_18004F2BE
0x18004f277  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f27e  nop     dword ptr [rax+rax+00h]
0x18004f283  mov     rcx, rax
0x18004f286  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f28d  test    rax, rax
0x18004f290  jz      short loc_18004F2B0
0x18004f292  mov     rax, [rax]
0x18004f295  mov     edx, 7F0h
0x18004f29a  mov     rax, [rax+8]
0x18004f29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2a3  test    eax, eax
0x18004f2a5  jz      short loc_18004F2B0
0x18004f2a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2ae  jmp     short loc_18004F2BE
0x18004f2b0  lea     rcx, qword_1800DBF70; this
0x18004f2b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2be  cmp     [rcx+8], r12b
0x18004f2c2  jz      short loc_18004F253
0x18004f2c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f2c9  cmp     [rax+7CCh], ebx
0x18004f2cf  jz      short loc_18004F253
0x18004f2d1  mov     r8d, 0B1h
0x18004f2d7  jmp     loc_18004F240
0x18004f2dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2e3  test    rcx, rcx
0x18004f2e6  jnz     short loc_18004F32F
0x18004f2e8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f2ef  nop     dword ptr [rax+rax+00h]
0x18004f2f4  mov     rcx, rax
0x18004f2f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2fe  test    rax, rax
0x18004f301  jz      short loc_18004F321
0x18004f303  mov     rax, [rax]
0x18004f306  mov     edx, 7F0h
0x18004f30b  mov     rax, [rax+8]
0x18004f30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f314  test    eax, eax
0x18004f316  jz      short loc_18004F321
0x18004f318  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f31f  jmp     short loc_18004F32F
0x18004f321  lea     rcx, qword_1800DBF70; this
0x18004f328  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f32f  cmp     [rcx+8], r12b
0x18004f333  jz      loc_18004F253
0x18004f339  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f33e  cmp     [rax+7CCh], ebx
0x18004f344  jz      loc_18004F253
0x18004f34a  mov     r8d, 0B0h
0x18004f350  jmp     loc_18004F240
0x18004f355  mov     rdx, r15; struct IMFPresentationDescriptor *
0x18004f358  mov     rcx, rsi; this
0x18004f35b  call    ?AddPresentationDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@@Z; CWMPropHandlerBase::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)
0x18004f360  mov     ebx, eax
0x18004f362  test    eax, eax
0x18004f364  jns     short loc_18004F3DF
0x18004f366  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f36d  test    rcx, rcx
0x18004f370  jnz     short loc_18004F3B9
0x18004f372  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f379  nop     dword ptr [rax+rax+00h]
0x18004f37e  mov     rcx, rax
0x18004f381  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f388  test    rax, rax
0x18004f38b  jz      short loc_18004F3AB
0x18004f38d  mov     rax, [rax]
0x18004f390  mov     edx, 7F0h
0x18004f395  mov     rax, [rax+8]
0x18004f399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f39e  test    eax, eax
0x18004f3a0  jz      short loc_18004F3AB
0x18004f3a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f3a9  jmp     short loc_18004F3B9
0x18004f3ab  lea     rcx, qword_1800DBF70; this
0x18004f3b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f3b9  cmp     [rcx+8], r12b
0x18004f3bd  jz      loc_18004F735
0x18004f3c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f3c8  cmp     [rax+7CCh], ebx
0x18004f3ce  jz      loc_18004F735
0x18004f3d4  mov     r8d, 0C3h
0x18004f3da  jmp     loc_18004F0BB
0x18004f3df  xorps   xmm0, xmm0
0x18004f3e2  xor     eax, eax
0x18004f3e4  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18004f3e8  mov     [rbp+57h+var_90], rax
0x18004f3ec  lea     edi, [rax+1Fh]
0x18004f3ef  mov     word ptr [rbp+57h+pv], di
0x18004f3f3  mov     [rbp+57h+pv+8], r12
0x18004f3f7  lea     rax, [rbp+57h+pv]
0x18004f3fb  mov     qword ptr [rbp+57h+Buf1], rax
0x18004f3ff  mov     byte ptr [rbp+57h+Buf1+8], r13b
0x18004f403  mov     rax, [r15]
0x18004f406  xor     r9d, r9d
0x18004f409  lea     r8, [rbp+57h+pv+8]
0x18004f40d  lea     rdx, MF_PD_MIME_TYPE
0x18004f414  mov     rcx, r15
0x18004f417  mov     rax, [rax+68h]
0x18004f41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f420  mov     ebx, eax
0x18004f422  test    eax, eax
0x18004f424  js      loc_18004F565
0x18004f42a  cmp     [rbp+57h+pv+8], r12
0x18004f42e  jnz     loc_18004F4C4
0x18004f434  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f43b  test    rcx, rcx
0x18004f43e  jnz     short loc_18004F487
0x18004f440  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f447  nop     dword ptr [rax+rax+00h]
0x18004f44c  mov     rcx, rax
0x18004f44f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f456  test    rax, rax
0x18004f459  jz      short loc_18004F479
0x18004f45b  mov     rax, [rax]
0x18004f45e  mov     edx, 7F0h
0x18004f463  mov     rax, [rax+8]
0x18004f467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f46c  test    eax, eax
0x18004f46e  jz      short loc_18004F479
0x18004f470  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f477  jmp     short loc_18004F487
0x18004f479  lea     rcx, qword_1800DBF70; this
0x18004f480  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f487  mov     ebx, 8007000Eh
0x18004f48c  cmp     [rcx+8], r12b
0x18004f490  jz      loc_18004F720
0x18004f496  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f49b  cmp     [rax+7CCh], ebx
0x18004f4a1  jz      loc_18004F720
0x18004f4a7  mov     r8d, 0D8h; int
0x18004f4ad  mov     r9d, ebx; int
0x18004f4b0  lea     rdx, aMfmkvpropertyh_3; "MFMkvPropertyHandler::AddPresentationDe"...
0x18004f4b7  mov     rcx, rax; this
0x18004f4ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f4bf  jmp     loc_18004F720
0x18004f4c4  mov     rax, [rsi]
0x18004f4c7  mov     [rsp+0F0h+var_D0], r13d
0x18004f4cc  xor     r9d, r9d
0x18004f4cf  lea     r8, [rbp+57h+pv]
0x18004f4d3  lea     rdx, PKEY_MIMEType
0x18004f4da  mov     rcx, rsi
0x18004f4dd  mov     rax, [rax+28h]
0x18004f4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
