# MFMkvPropertyHandler::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)

- ea: `0x18004cff0`
- end: `0x18004d71c`
- name: `?AddPresentationDescriptorProperties@MFMkvPropertyHandler@@EEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `1836`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x180005ab8`
- `0x1800097f0`
- `0x18004cff0`
- `0x180058b70`
- `0x180062a04`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d6ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d6ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d6dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d6dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d053`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d1da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d26b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d35a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d422`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d4d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d5d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d66c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d053`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d1da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d26b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d35a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d422`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d4d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d5d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d66c`

## string_xrefs

- `0x18004d0b8`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`
- `0x18004d237`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`
- `0x18004d48c`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`
- `0x18004d6c9`: `MFMkvPropertyHandler::AddPresentationDescriptorProperties`

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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v31 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v29 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v25 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v42 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v49 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v61 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v54 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v36 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18004cff0  mov     [rsp-8+arg_10], rbx
0x18004cff5  push    rbp
0x18004cff6  push    rsi
0x18004cff7  push    rdi
0x18004cff8  push    r12
0x18004cffa  push    r13
0x18004cffc  push    r14
0x18004cffe  push    r15
0x18004d000  lea     rbp, [rsp-27h]
0x18004d005  sub     rsp, 0C0h
0x18004d00c  mov     rax, cs:__security_cookie
0x18004d013  xor     rax, rsp
0x18004d016  mov     [rbp+57h+var_40], rax
0x18004d01a  mov     r15, rdx
0x18004d01d  mov     rsi, rcx
0x18004d020  xor     r12d, r12d
0x18004d023  mov     [rbp+57h+var_B8], r12d
0x18004d027  mov     rax, [rdx]
0x18004d02a  lea     rdx, [rbp+57h+var_B8]
0x18004d02e  mov     rcx, r15
0x18004d031  mov     rax, [rax+108h]
0x18004d038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d03d  mov     ebx, eax
0x18004d03f  test    eax, eax
0x18004d041  jns     loc_18004D0CC
0x18004d047  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d04e  test    rcx, rcx
0x18004d051  jnz     short loc_18004D094
0x18004d053  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d059  mov     rcx, rax
0x18004d05c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d063  test    rax, rax
0x18004d066  jz      short loc_18004D086
0x18004d068  mov     rax, [rax]
0x18004d06b  mov     edx, 7F0h
0x18004d070  mov     rax, [rax+8]
0x18004d074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d079  test    eax, eax
0x18004d07b  jz      short loc_18004D086
0x18004d07d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d084  jmp     short loc_18004D094
0x18004d086  lea     rcx, qword_1800D6F70; this
0x18004d08d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d094  cmp     [rcx+8], r12b
0x18004d098  jz      loc_18004D6F3
0x18004d09e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d0a3  cmp     [rax+7CCh], ebx
0x18004d0a9  jz      loc_18004D6F3
0x18004d0af  mov     r8d, 0A9h; int
0x18004d0b5  mov     r9d, ebx; int
0x18004d0b8  lea     rdx, aMfmkvpropertyh_3; "MFMkvPropertyHandler::AddPresentationDe"...
0x18004d0bf  mov     rcx, rax; this
0x18004d0c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d0c7  jmp     loc_18004D6F3
0x18004d0cc  mov     r14d, r12d
0x18004d0cf  mov     r13d, 1
0x18004d0d5  cmp     r14d, [rbp+57h+var_B8]
0x18004d0d9  jnb     loc_18004D33D
0x18004d0df  mov     [rbp+57h+var_B0], r12
0x18004d0e3  mov     [rbp+57h+var_C0], r12
0x18004d0e7  mov     [rbp+57h+var_88], r12d
0x18004d0eb  xorps   xmm0, xmm0
0x18004d0ee  movups  [rbp+57h+Buf1], xmm0
0x18004d0f2  mov     rax, [r15]
0x18004d0f5  mov     rbx, [rax+110h]
0x18004d0fc  lea     rcx, [rbp+57h+var_B0]
0x18004d100  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d105  lea     r9, [rbp+57h+var_B0]
0x18004d109  lea     r8, [rbp+57h+var_88]
0x18004d10d  mov     edx, r14d
0x18004d110  mov     rcx, r15
0x18004d113  mov     rax, rbx
0x18004d116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d11b  mov     ebx, eax
0x18004d11d  test    eax, eax
0x18004d11f  js      loc_18004D2CA
0x18004d125  mov     rdi, [rbp+57h+var_B0]
0x18004d129  mov     rax, [rdi]
0x18004d12c  mov     rbx, [rax+110h]
0x18004d133  lea     rcx, [rbp+57h+var_C0]
0x18004d137  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d13c  lea     rdx, [rbp+57h+var_C0]
0x18004d140  mov     rcx, rdi
0x18004d143  mov     rax, rbx
0x18004d146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d14b  mov     ebx, eax
0x18004d14d  test    eax, eax
0x18004d14f  js      loc_18004D25F
0x18004d155  mov     rcx, [rbp+57h+var_C0]
0x18004d159  mov     rax, [rcx]
0x18004d15c  lea     rdx, [rbp+57h+Buf1]
0x18004d160  mov     rax, [rax+40h]
0x18004d164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d169  mov     ebx, eax
0x18004d16b  test    eax, eax
0x18004d16d  js      short loc_18004D1CE
0x18004d16f  mov     r8d, 10h; Size
0x18004d175  lea     rdx, MFMediaType_Audio; Buf2
0x18004d17c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004d180  call    memcmp_0
0x18004d185  test    eax, eax
0x18004d187  jnz     short loc_18004D192
0x18004d189  mov     [rsi+384h], r13d
0x18004d190  jmp     short loc_18004D1B3
0x18004d192  mov     r8d, 10h; Size
0x18004d198  lea     rdx, MFMediaType_Video; Buf2
0x18004d19f  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004d1a3  call    memcmp_0
0x18004d1a8  test    eax, eax
0x18004d1aa  jnz     short loc_18004D1B3
0x18004d1ac  mov     [rsi+388h], r13d
0x18004d1b3  lea     rcx, [rbp+57h+var_C0]
0x18004d1b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d1bc  nop
0x18004d1bd  lea     rcx, [rbp+57h+var_B0]
0x18004d1c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d1c6  add     r14d, r13d
0x18004d1c9  jmp     loc_18004D0D5
0x18004d1ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1d5  test    rcx, rcx
0x18004d1d8  jnz     short loc_18004D21B
0x18004d1da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d1e0  mov     rcx, rax
0x18004d1e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1ea  test    rax, rax
0x18004d1ed  jz      short loc_18004D20D
0x18004d1ef  mov     rax, [rax]
0x18004d1f2  mov     edx, 7F0h
0x18004d1f7  mov     rax, [rax+8]
0x18004d1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d200  test    eax, eax
0x18004d202  jz      short loc_18004D20D
0x18004d204  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d20b  jmp     short loc_18004D21B
0x18004d20d  lea     rcx, qword_1800D6F70; this
0x18004d214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d21b  cmp     [rcx+8], r12b
0x18004d21f  jz      short loc_18004D247
0x18004d221  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d226  cmp     [rax+7CCh], ebx
0x18004d22c  jz      short loc_18004D247
0x18004d22e  mov     r8d, 0B2h; int
0x18004d234  mov     r9d, ebx; int
0x18004d237  lea     rdx, aMfmkvpropertyh_3; "MFMkvPropertyHandler::AddPresentationDe"...
0x18004d23e  mov     rcx, rax; this
0x18004d241  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d246  nop
0x18004d247  lea     rcx, [rbp+57h+var_C0]
0x18004d24b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d250  nop
0x18004d251  lea     rcx, [rbp+57h+var_B0]
0x18004d255  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d25a  jmp     loc_18004D6F3
0x18004d25f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d266  test    rcx, rcx
0x18004d269  jnz     short loc_18004D2AC
0x18004d26b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d271  mov     rcx, rax
0x18004d274  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d27b  test    rax, rax
0x18004d27e  jz      short loc_18004D29E
0x18004d280  mov     rax, [rax]
0x18004d283  mov     edx, 7F0h
0x18004d288  mov     rax, [rax+8]
0x18004d28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d291  test    eax, eax
0x18004d293  jz      short loc_18004D29E
0x18004d295  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d29c  jmp     short loc_18004D2AC
0x18004d29e  lea     rcx, qword_1800D6F70; this
0x18004d2a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2ac  cmp     [rcx+8], r12b
0x18004d2b0  jz      short loc_18004D247
0x18004d2b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d2b7  cmp     [rax+7CCh], ebx
0x18004d2bd  jz      short loc_18004D247
0x18004d2bf  mov     r8d, 0B1h
0x18004d2c5  jmp     loc_18004D234
0x18004d2ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2d1  test    rcx, rcx
0x18004d2d4  jnz     short loc_18004D317
0x18004d2d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d2dc  mov     rcx, rax
0x18004d2df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2e6  test    rax, rax
0x18004d2e9  jz      short loc_18004D309
0x18004d2eb  mov     rax, [rax]
0x18004d2ee  mov     edx, 7F0h
0x18004d2f3  mov     rax, [rax+8]
0x18004d2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2fc  test    eax, eax
0x18004d2fe  jz      short loc_18004D309
0x18004d300  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d307  jmp     short loc_18004D317
0x18004d309  lea     rcx, qword_1800D6F70; this
0x18004d310  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d317  cmp     [rcx+8], r12b
0x18004d31b  jz      loc_18004D247
0x18004d321  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d326  cmp     [rax+7CCh], ebx
0x18004d32c  jz      loc_18004D247
0x18004d332  mov     r8d, 0B0h
0x18004d338  jmp     loc_18004D234
0x18004d33d  mov     rdx, r15; struct IMFPresentationDescriptor *
0x18004d340  mov     rcx, rsi; this
0x18004d343  call    ?AddPresentationDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@@Z; CWMPropHandlerBase::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)
0x18004d348  mov     ebx, eax
0x18004d34a  test    eax, eax
0x18004d34c  jns     short loc_18004D3C1
0x18004d34e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d355  test    rcx, rcx
0x18004d358  jnz     short loc_18004D39B
0x18004d35a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d360  mov     rcx, rax
0x18004d363  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d36a  test    rax, rax
0x18004d36d  jz      short loc_18004D38D
0x18004d36f  mov     rax, [rax]
0x18004d372  mov     edx, 7F0h
0x18004d377  mov     rax, [rax+8]
0x18004d37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d380  test    eax, eax
0x18004d382  jz      short loc_18004D38D
0x18004d384  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d38b  jmp     short loc_18004D39B
0x18004d38d  lea     rcx, qword_1800D6F70; this
0x18004d394  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d39b  cmp     [rcx+8], r12b
0x18004d39f  jz      loc_18004D6F3
0x18004d3a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d3aa  cmp     [rax+7CCh], ebx
0x18004d3b0  jz      loc_18004D6F3
0x18004d3b6  mov     r8d, 0C3h
0x18004d3bc  jmp     loc_18004D0B5
0x18004d3c1  xorps   xmm0, xmm0
0x18004d3c4  xor     eax, eax
0x18004d3c6  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18004d3ca  mov     [rbp+57h+var_90], rax
0x18004d3ce  lea     edi, [rax+1Fh]
0x18004d3d1  mov     word ptr [rbp+57h+pv], di
0x18004d3d5  mov     [rbp+57h+pv+8], r12
0x18004d3d9  lea     rax, [rbp+57h+pv]
0x18004d3dd  mov     qword ptr [rbp+57h+Buf1], rax
0x18004d3e1  mov     byte ptr [rbp+57h+Buf1+8], r13b
0x18004d3e5  mov     rax, [r15]
0x18004d3e8  xor     r9d, r9d
0x18004d3eb  lea     r8, [rbp+57h+pv+8]
0x18004d3ef  lea     rdx, MF_PD_MIME_TYPE
0x18004d3f6  mov     rcx, r15
0x18004d3f9  mov     rax, [rax+68h]
0x18004d3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d402  mov     ebx, eax
0x18004d404  test    eax, eax
0x18004d406  js      loc_18004D53B
0x18004d40c  cmp     [rbp+57h+pv+8], r12
0x18004d410  jnz     loc_18004D4A0
0x18004d416  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d41d  test    rcx, rcx
0x18004d420  jnz     short loc_18004D463
0x18004d422  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d428  mov     rcx, rax
0x18004d42b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d432  test    rax, rax
0x18004d435  jz      short loc_18004D455
0x18004d437  mov     rax, [rax]
0x18004d43a  mov     edx, 7F0h
0x18004d43f  mov     rax, [rax+8]
0x18004d443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d448  test    eax, eax
0x18004d44a  jz      short loc_18004D455
0x18004d44c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d453  jmp     short loc_18004D463
0x18004d455  lea     rcx, qword_1800D6F70; this
0x18004d45c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d463  mov     ebx, 8007000Eh
0x18004d468  cmp     [rcx+8], r12b
0x18004d46c  jz      loc_18004D6E4
0x18004d472  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d477  cmp     [rax+7CCh], ebx
0x18004d47d  jz      loc_18004D6E4
0x18004d483  mov     r8d, 0D8h; int
0x18004d489  mov     r9d, ebx; int
0x18004d48c  lea     rdx, aMfmkvpropertyh_3; "MFMkvPropertyHandler::AddPresentationDe"...
0x18004d493  mov     rcx, rax; this
0x18004d496  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d49b  jmp     loc_18004D6E4
0x18004d4a0  mov     rax, [rsi]
0x18004d4a3  mov     [rsp+0F0h+var_D0], r13d
0x18004d4a8  xor     r9d, r9d
0x18004d4ab  lea     r8, [rbp+57h+pv]
0x18004d4af  lea     rdx, PKEY_MIMEType
0x18004d4b6  mov     rcx, rsi
0x18004d4b9  mov     rax, [rax+28h]
0x18004d4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4c2  mov     ebx, eax
0x18004d4c4  test    eax, eax
0x18004d4c6  jns     short loc_18004D53B
0x18004d4c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d4cf  test    rcx, rcx
0x18004d4d2  jnz     short loc_18004D515
  ... truncated ...
```
