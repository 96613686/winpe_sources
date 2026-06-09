# HelperClassRepository::GetClassFactory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> *,_GUID *,bool,SQMSession *)

- ea: `0x18001dfa4`
- end: `0x18001e6b4`
- name: `?GetClassFactory@HelperClassRepository@@QEAAPEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@PEAU_GUID@@_NPEAVSQMSession@@@Z`
- size: `1808`
- prototype: `char *__fastcall(__int64, _QWORD *, __int64, _OWORD *, char, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800121d0`

## callees

- `0x1800035a8`
- `0x1800056bc`
- `0x18000579c`
- `0x180006d58`
- `0x180006fa0`
- `0x180007014`
- `0x180007c80`
- `0x180008c84`
- `0x180009328`
- `0x18000bca0`
- `0x18000bda4`
- `0x180011b70`
- `0x18001b3a8`
- `0x18001dfa4`
- `0x18001ec48`
- `0x18001f1d8`
- `0x18001f2f8`
- `0x180020f8c`
- `0x180026474`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e5e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e5e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e1ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e1ff`

## string_xrefs

- `0x18001e2cd`: `GetClassFactory:ArrayToList failed for LookupExtension call, out of memory.`
- `0x18001e3b1`: `Successfully loaded extension %s.`
- `0x18001e405`: `GetClassObject failed for extension %s of extensible class %s, HR: %x`
- `0x18001e498`: `Did not find extension for extensible class %s.`
- `0x18001e50c`: `GetClassFactory:CoTaskMemAlloc failed for NDFClassFactoryData, out of memory.`

## pseudocode

```c
char *__fastcall HelperClassRepository::GetClassFactory(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _OWORD *a4,
        char a5,
        __int64 a6)
{
  _QWORD *v6; // r13
  __int64 v7; // rdi
  _QWORD *v8; // r14
  __int64 v9; // rsi
  __int64 v10; // rbx
  int ClassObject; // ebx
  struct IClassFactory *v12; // rdi
  struct IClassFactory *v13; // r12
  unsigned __int16 *v14; // r8
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, LPVOID, unsigned int *, struct tagHELPER_ATTRIBUTE **); // rbx
  unsigned int v17; // eax
  int v18; // ebx
  CExtensionHelperInfo *v19; // r13
  int v20; // eax
  char *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rbx
  int v25; // ebx
  char *v26; // rbx
  char *v27; // rbx
  char *v28; // rax
  char *v29; // rbx
  unsigned __int16 **v30; // rsi
  const unsigned __int16 *v31; // rdi
  LPVOID v32; // r15
  unsigned __int16 *v33; // rax
  const unsigned __int16 *v34; // rdi
  LPVOID v35; // r14
  unsigned __int16 *v36; // rax
  char *v38; // rbx
  __int64 v39; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  struct IClassFactory *v43; // [rsp+48h] [rbp-B8h] BYREF
  struct tagHELPER_ATTRIBUTE *v44; // [rsp+50h] [rbp-B0h] BYREF
  struct IClassFactory *v45; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v47; // [rsp+68h] [rbp-98h]
  __int64 v48; // [rsp+70h] [rbp-90h]
  __int64 v49; // [rsp+78h] [rbp-88h]
  struct IClassFactory *v50; // [rsp+80h] [rbp-80h]
  _OWORD *v51; // [rsp+88h] [rbp-78h]
  unsigned __int16 v52[128]; // [rsp+90h] [rbp-70h] BYREF

  v51 = a4;
  v46 = a3;
  v6 = a2;
  v47 = a2;
  v48 = a1;
  v49 = a6;
  v7 = a1 + 8;
  v8 = *(_QWORD **)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                     a1 + 8,
                     a2);
  if ( !v8 )
    v8 = *(_QWORD **)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                       v7 + 16,
                       v6);
  v9 = 0;
  if ( NetworkDiagnosticsEngine::Instance() )
    v9 = *(_QWORD *)NetworkDiagnosticsEngine::Instance();
  if ( !v8 )
  {
    if ( a6 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a6 + 56LL))(a6, *v6, 0, 0);
    if ( !v9 )
      return 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v42);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&v42,
      (__int64)L"GetClassFactory failed for %s. The HC is not registered with NDF",
      *v6);
    v10 = v42;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 96LL))(v9, 1, v42);
    goto LABEL_14;
  }
  if ( !*((_BYTE *)v8 + 48) && a5 )
  {
    if ( !v9 )
      return 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v42);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&v42,
      (__int64)L"GetClassFactory::GetClassObject failed for %s. The non-published class was requested as an entry point, t"
                "his is not allowed.",
      *v6);
    v10 = v42;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 96LL))(v9, 1, v42);
LABEL_14:
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    return 0;
  }
  v45 = 0;
  ClassObject = CHelperInfo::GetClassObject((CHelperInfo *)v8, &v45);
  if ( ClassObject < 0 || (v12 = v45, (v50 = v45) == 0) )
  {
    if ( v9 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&pv);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)&pv,
        (__int64)L"GetClassFactory::GetClassObject failed for %s, HR: %x",
        *v6,
        (unsigned int)ClassObject);
      v38 = (char *)pv;
      (*(void (__fastcall **)(__int64, __int64, LPVOID))(*(_QWORD *)v9 + 96LL))(v9, 1, pv);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    }
    goto LABEL_75;
  }
  v13 = 0;
  v43 = 0;
  if ( *((_BYTE *)v8 + 24) )
  {
    v41 = 0;
    v44 = 0;
    v42 = 0;
    if ( ((int (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64 *))v45->lpVtbl->CreateInstance)(
           v45,
           0,
           &IID_INetDiagExtensibleHelper,
           &v42) >= 0 )
    {
      pv = ListToArray<tagHELPER_ATTRIBUTE>(v46);
      if ( !pv )
      {
        if ( v9 )
        {
          v14 = L"GetClassFactory:ListToArray failed for ResolveAttributes call, out of memory.";
LABEL_22:
          (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v9 + 96LL))(v9, 1, v14);
LABEL_52:
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&pv);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)&pv,
            (__int64)L"Did not find extension for extensible class %s.",
            *v6);
          v27 = (char *)pv;
          (*(void (__fastcall **)(__int64, __int64, LPVOID))(*(_QWORD *)v9 + 96LL))(v9, 1, pv);
          ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
          goto LABEL_53;
        }
        goto LABEL_53;
      }
      v15 = v42;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, LPVOID, unsigned int *, struct tagHELPER_ATTRIBUTE **))(*(_QWORD *)v42 + 24LL);
      v17 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(v46 + 8));
      v18 = v16(v15, v17, pv, &v41, &v44);
      CoTaskMemFree(pv);
      if ( v18 < 0 )
      {
        if ( v9 )
        {
          memset_0(v52, 0, sizeof(v52));
          StringCchPrintfW(v52, 0x80u, L"ResolveAttributes call failed. HR: %x", (unsigned int)v18);
          v14 = v52;
          goto LABEL_22;
        }
LABEL_53:
        ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v42);
        v12 = v50;
        goto LABEL_54;
      }
      v19 = 0;
      if ( v41 && v44 )
      {
        if ( v9 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&pv);
          v20 = AttributeConverter::MultiToString(v41, v44, &pv);
          v21 = (char *)pv;
          if ( v20 >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v46);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              (__int64)&v46,
              (__int64)L"%s returned the following matching attributes: %s",
              *v47,
              v21);
            v22 = v46;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 96LL))(v9, 1, v46);
            ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
          }
          ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
        }
        v23 = ArrayToList<tagHELPER_ATTRIBUTE>();
        v24 = v23;
        if ( v23 )
        {
          v19 = (CExtensionHelperInfo *)CHelperMetaDataStore::LookupExtension(v48, *v8, v23);
          std::list<tagHELPER_ATTRIBUTE>::`scalar deleting destructor'(v24);
          if ( !v19 && v49 )
            (*(void (__fastcall **)(__int64, _QWORD, struct tagHELPER_ATTRIBUTE *, _QWORD))(*(_QWORD *)v49 + 56LL))(
              v49,
              *v47,
              v44,
              v41);
        }
        else if ( v9 )
        {
          (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v9 + 96LL))(
            v9,
            1,
            L"GetClassFactory:ArrayToList failed for LookupExtension call, out of memory.");
        }
        FreeHelperAttributes(v44, v41, 1);
        v41 = 0;
      }
      else
      {
        if ( !v9 )
          goto LABEL_53;
        (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v9 + 96LL))(
          v9,
          1,
          L"ResolveAttributes call did not return any attributes.");
      }
      if ( v19 )
      {
        v25 = CExtensionHelperInfo::GetClassObject(v19, &v43);
        if ( v25 < 0 )
        {
          if ( v9 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&pv);
            LODWORD(v39) = v25;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              (__int64)&pv,
              (__int64)L"GetClassObject failed for extension %s of extensible class %s, HR: %x",
              *(_QWORD *)v19,
              *v47,
              v39);
            v26 = (char *)pv;
            (*(void (__fastcall **)(__int64, __int64, LPVOID))(*(_QWORD *)v9 + 96LL))(v9, 1, pv);
            ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
          }
          v13 = v43;
        }
        else
        {
          v13 = v43;
          if ( v43 )
          {
            if ( v9 )
            {
              memset_0(v52, 0, sizeof(v52));
              StringCchPrintfW(v52, 0x80u, L"Successfully loaded extension %s.", *(_QWORD *)v19);
              (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v9 + 96LL))(v9, 1, v52);
            }
            v8[4] = v19;
          }
        }
        goto LABEL_53;
      }
      v6 = v47;
    }
    if ( v9 )
      goto LABEL_52;
    goto LABEL_53;
  }
LABEL_54:
  if ( v51 )
    *v51 = *(_OWORD *)(v8 + 1);
  v28 = (char *)CoTaskMemAlloc(0x20u);
  v29 = v28;
  if ( !v28 )
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v9 + 96LL))(
        v9,
        1,
        L"GetClassFactory:CoTaskMemAlloc failed for NDFClassFactoryData, out of memory.");
    ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v43);
LABEL_75:
    ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v45);
    return 0;
  }
  v30 = (unsigned __int16 **)(v28 + 16);
  if ( v13 )
  {
    v43 = 0;
    *(_QWORD *)v28 = v13;
    *((_DWORD *)v28 + 2) = *(_DWORD *)(v8[4] + 68LL);
    if ( v28 != (char *)-16LL )
    {
      v31 = *(const unsigned __int16 **)v8[4];
      if ( v31 )
      {
        pv = 0;
        if ( (int)StringCchLengthW(v31, 0xFFFEu, (unsigned __int64 *)&pv) >= 0 )
        {
          v32 = pv;
          v33 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (_QWORD)pv + 2);
          *v30 = v33;
          if ( v33 )
            StringCchCopyW(v33, (unsigned __int64)v32 + 1, v31);
        }
      }
    }
    if ( v29 != (char *)-24LL )
    {
      v34 = *(const unsigned __int16 **)(v8[4] + 32LL);
      if ( v34 )
      {
        pv = 0;
        if ( (int)StringCchLengthW(v34, 0xFFFEu, (unsigned __int64 *)&pv) >= 0 )
        {
          v35 = pv;
          v36 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (_QWORD)pv + 2);
          *((_QWORD *)v29 + 3) = v36;
          if ( v36 )
            StringCchCopyW(v36, (unsigned __int64)v35 + 1, v34);
        }
      }
    }
  }
  else
  {
    v45 = 0;
    *(_QWORD *)v28 = v12;
    *((_DWORD *)v28 + 2) = *((_DWORD *)v8 + 16);
    *v30 = 0;
    *((_QWORD *)v28 + 3) = 0;
  }
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v43);
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v45);
  return v29;
}

```

## disassembly

```asm
0x18001dfa4  push    rbp
0x18001dfa6  push    rbx
0x18001dfa7  push    rsi
0x18001dfa8  push    rdi
0x18001dfa9  push    r12
0x18001dfab  push    r13
0x18001dfad  push    r14
0x18001dfaf  push    r15
0x18001dfb1  lea     rbp, [rsp-0A8h]
0x18001dfb9  sub     rsp, 1A8h
0x18001dfc0  mov     rax, cs:__security_cookie
0x18001dfc7  xor     rax, rsp
0x18001dfca  mov     [rbp+0E0h+var_50], rax
0x18001dfd1  mov     [rbp+0E0h+var_158], r9
0x18001dfd5  mov     [rsp+1E0h+var_180], r8
0x18001dfda  mov     r13, rdx
0x18001dfdd  mov     [rsp+1E0h+var_178], rdx
0x18001dfe2  mov     [rsp+1E0h+var_170], rcx
0x18001dfe7  mov     rbx, [rbp+0E0h+arg_28]
0x18001dfee  mov     [rsp+1E0h+var_168], rbx
0x18001dff3  lea     rdi, [rcx+8]
0x18001dff7  mov     rcx, rdi
0x18001dffa  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@@std@@QEAAAEAPEAVCHelperInfo@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001dfff  mov     r14, [rax]
0x18001e002  xor     r15d, r15d
0x18001e005  test    r14, r14
0x18001e008  jnz     short loc_18001E019
0x18001e00a  lea     rcx, [rdi+10h]
0x18001e00e  mov     rdx, r13
0x18001e011  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@@std@@QEAAAEAPEAVCHelperInfo@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001e016  mov     r14, [rax]
0x18001e019  mov     rsi, r15
0x18001e01c  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x18001e021  test    rax, rax
0x18001e024  jz      short loc_18001E02E
0x18001e026  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x18001e02b  mov     rsi, [rax]
0x18001e02e  test    r14, r14
0x18001e031  jnz     short loc_18001E099
0x18001e033  test    rbx, rbx
0x18001e036  jz      short loc_18001E051
0x18001e038  mov     rax, [rbx]
0x18001e03b  xor     r9d, r9d
0x18001e03e  xor     r8d, r8d
0x18001e041  mov     rdx, [r13+0]
0x18001e045  mov     rcx, rbx
0x18001e048  mov     rax, [rax+38h]
0x18001e04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e051  test    rsi, rsi
0x18001e054  jz      loc_18001E68F
0x18001e05a  lea     rcx, [rsp+1E0h+var_1A0]
0x18001e05f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e064  nop
0x18001e065  mov     r8, [r13+0]
0x18001e069  lea     rdx, aGetclassfactor_3; "GetClassFactory failed for %s. The HC i"...
0x18001e070  lea     rcx, [rsp+1E0h+var_1A0]
0x18001e075  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001e07a  mov     rax, [rsi]
0x18001e07d  mov     rbx, [rsp+1E0h+var_1A0]
0x18001e082  mov     r8, rbx
0x18001e085  mov     edx, 1
0x18001e08a  mov     rcx, rsi
0x18001e08d  mov     rax, [rax+60h]
0x18001e091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e096  nop
0x18001e097  jmp     short loc_18001E0EE
0x18001e099  cmp     [r14+30h], r15b
0x18001e09d  jnz     short loc_18001E0FC
0x18001e09f  cmp     [rbp+0E0h+arg_20], r15b
0x18001e0a6  jz      short loc_18001E0FC
0x18001e0a8  test    rsi, rsi
0x18001e0ab  jz      loc_18001E68F
0x18001e0b1  lea     rcx, [rsp+1E0h+var_1A0]
0x18001e0b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e0bb  nop
0x18001e0bc  mov     r8, [r13+0]
0x18001e0c0  lea     rdx, aGetclassfactor_2; "GetClassFactory::GetClassObject failed "...
0x18001e0c7  lea     rcx, [rsp+1E0h+var_1A0]
0x18001e0cc  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001e0d1  mov     rax, [rsi]
0x18001e0d4  mov     rbx, [rsp+1E0h+var_1A0]
0x18001e0d9  mov     r8, rbx
0x18001e0dc  mov     edx, 1
0x18001e0e1  mov     rcx, rsi
0x18001e0e4  mov     rax, [rax+60h]
0x18001e0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0ed  nop
0x18001e0ee  lea     rcx, [rbx-18h]; this
0x18001e0f2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e0f7  jmp     loc_18001E68F
0x18001e0fc  mov     [rsp+1E0h+var_188], r15
0x18001e101  lea     rdx, [rsp+1E0h+var_188]; struct IClassFactory **
0x18001e106  mov     rcx, r14; this
0x18001e109  call    ?GetClassObject@CHelperInfo@@QEAAJPEAPEAUIClassFactory@@@Z; CHelperInfo::GetClassObject(IClassFactory * *)
0x18001e10e  mov     ebx, eax
0x18001e110  test    eax, eax
0x18001e112  js      loc_18001E636
0x18001e118  mov     rdi, [rsp+1E0h+var_188]
0x18001e11d  mov     [rbp+0E0h+var_160], rdi
0x18001e121  test    rdi, rdi
0x18001e124  jz      loc_18001E636
0x18001e12a  mov     r12, r15
0x18001e12d  mov     [rsp+1E0h+var_198], r15
0x18001e132  mov     r15d, 1
0x18001e138  cmp     byte ptr [r14+18h], 0
0x18001e13d  jz      loc_18001E4DC
0x18001e143  mov     [rsp+1E0h+var_1A8], 0
0x18001e14b  mov     [rsp+1E0h+var_190], 0
0x18001e154  mov     [rsp+1E0h+var_1A0], 0
0x18001e15d  mov     rax, [rdi]
0x18001e160  lea     r9, [rsp+1E0h+var_1A0]
0x18001e165  lea     r8, IID_INetDiagExtensibleHelper
0x18001e16c  xor     edx, edx
0x18001e16e  mov     rcx, rdi
0x18001e171  mov     rax, [rax+18h]
0x18001e175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e17a  test    eax, eax
0x18001e17c  js      loc_18001E484
0x18001e182  mov     rcx, [rsp+1E0h+var_180]
0x18001e187  call    ??$ListToArray@UtagHELPER_ATTRIBUTE@@@@YAPEAUtagHELPER_ATTRIBUTE@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; ListToArray<tagHELPER_ATTRIBUTE>(std::list<tagHELPER_ATTRIBUTE> *)
0x18001e18c  mov     [rsp+1E0h+pv], rax
0x18001e191  test    rax, rax
0x18001e194  jnz     short loc_18001E1BD
0x18001e196  test    rsi, rsi
0x18001e199  jz      loc_18001E4CE
0x18001e19f  lea     r8, aGetclassfactor_0; "GetClassFactory:ListToArray failed for "...
0x18001e1a6  mov     rax, [rsi]
0x18001e1a9  mov     edx, r15d
0x18001e1ac  mov     rcx, rsi
0x18001e1af  mov     rax, [rax+60h]
0x18001e1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1b8  jmp     loc_18001E489
0x18001e1bd  mov     rdi, [rsp+1E0h+var_1A0]
0x18001e1c2  mov     rax, [rdi]
0x18001e1c5  mov     rbx, [rax+18h]
0x18001e1c9  mov     rax, [rsp+1E0h+var_180]
0x18001e1ce  mov     rcx, [rax+8]
0x18001e1d2  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001e1d7  lea     rcx, [rsp+1E0h+var_190]
0x18001e1dc  mov     [rsp+1E0h+var_1C0], rcx
0x18001e1e1  lea     r9, [rsp+1E0h+var_1A8]
0x18001e1e6  mov     r8, [rsp+1E0h+pv]
0x18001e1eb  mov     edx, eax
0x18001e1ed  mov     rcx, rdi
0x18001e1f0  mov     rax, rbx
0x18001e1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1f8  mov     ebx, eax
0x18001e1fa  mov     rcx, [rsp+1E0h+pv]; pv
0x18001e1ff  call    cs:__imp_CoTaskMemFree
0x18001e205  test    ebx, ebx
0x18001e207  js      loc_18001E444
0x18001e20d  xor     r13d, r13d
0x18001e210  mov     ecx, [rsp+1E0h+var_1A8]
0x18001e214  test    ecx, ecx
0x18001e216  jz      loc_18001E34B
0x18001e21c  mov     rdx, [rsp+1E0h+var_190]
0x18001e221  test    rdx, rdx
0x18001e224  jz      loc_18001E34B
0x18001e22a  test    rsi, rsi
0x18001e22d  jz      loc_18001E2B8
0x18001e233  lea     rcx, [rsp+1E0h+pv]
0x18001e238  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e23d  nop
0x18001e23e  lea     r8, [rsp+1E0h+pv]
0x18001e243  mov     rdx, [rsp+1E0h+var_190]
0x18001e248  mov     ecx, [rsp+1E0h+var_1A8]
0x18001e24c  call    ?MultiToString@AttributeConverter@@SAJKPEAUtagHELPER_ATTRIBUTE@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::MultiToString(ulong,tagHELPER_ATTRIBUTE *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001e251  mov     rdi, [rsp+1E0h+pv]
0x18001e256  test    eax, eax
0x18001e258  js      short loc_18001E2A6
0x18001e25a  lea     rcx, [rsp+1E0h+var_180]
0x18001e25f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e264  nop
0x18001e265  mov     r9, rdi
0x18001e268  mov     rax, [rsp+1E0h+var_178]
0x18001e26d  mov     r8, [rax]
0x18001e270  lea     rdx, aSReturnedTheFo; "%s returned the following matching attr"...
0x18001e277  lea     rcx, [rsp+1E0h+var_180]
0x18001e27c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001e281  mov     rax, [rsi]
0x18001e284  mov     rbx, [rsp+1E0h+var_180]
0x18001e289  mov     r8, rbx
0x18001e28c  mov     edx, r15d
0x18001e28f  mov     rcx, rsi
0x18001e292  mov     rax, [rax+60h]
0x18001e296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e29b  nop
0x18001e29c  lea     rcx, [rbx-18h]; this
0x18001e2a0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e2a5  nop
0x18001e2a6  lea     rcx, [rdi-18h]; this
0x18001e2aa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e2af  mov     ecx, [rsp+1E0h+var_1A8]
0x18001e2b3  mov     rdx, [rsp+1E0h+var_190]
0x18001e2b8  call    ??$ArrayToList@UtagHELPER_ATTRIBUTE@@@@YAPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@KPEAUtagHELPER_ATTRIBUTE@@@Z; ArrayToList<tagHELPER_ATTRIBUTE>(ulong,tagHELPER_ATTRIBUTE *)
0x18001e2bd  mov     rbx, rax
0x18001e2c0  test    rax, rax
0x18001e2c3  jnz     short loc_18001E2E5
0x18001e2c5  test    rsi, rsi
0x18001e2c8  jz      short loc_18001E330
0x18001e2ca  mov     rax, [rsi]
0x18001e2cd  lea     r8, aGetclassfactor_1; "GetClassFactory:ArrayToList failed for "...
0x18001e2d4  mov     edx, r15d
0x18001e2d7  mov     rcx, rsi
0x18001e2da  mov     rax, [rax+60h]
0x18001e2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2e3  jmp     short loc_18001E330
0x18001e2e5  mov     r8, rbx
0x18001e2e8  mov     rdx, [r14]
0x18001e2eb  mov     rcx, [rsp+1E0h+var_170]
0x18001e2f0  call    ?LookupExtension@CHelperMetaDataStore@@QEAAPEBVCExtensionHelperInfo@@PEBGPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; CHelperMetaDataStore::LookupExtension(ushort const *,std::list<tagHELPER_ATTRIBUTE> *)
0x18001e2f5  mov     r13, rax
0x18001e2f8  mov     rcx, rbx
0x18001e2fb  call    ??_G?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@QEAAPEAXI@Z; std::list<tagHELPER_ATTRIBUTE>::`scalar deleting destructor'(uint)
0x18001e300  test    r13, r13
0x18001e303  jnz     short loc_18001E330
0x18001e305  mov     r10, [rsp+1E0h+var_168]
0x18001e30a  test    r10, r10
0x18001e30d  jz      short loc_18001E330
0x18001e30f  mov     rcx, [r10]
0x18001e312  mov     rax, [rcx+38h]
0x18001e316  mov     r9d, [rsp+1E0h+var_1A8]
0x18001e31b  mov     r8, [rsp+1E0h+var_190]
0x18001e320  mov     rdx, [rsp+1E0h+var_178]
0x18001e325  mov     rdx, [rdx]
0x18001e328  mov     rcx, r10
0x18001e32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e330  mov     r8d, r15d; int
0x18001e333  mov     edx, [rsp+1E0h+var_1A8]; unsigned int
0x18001e337  mov     rcx, [rsp+1E0h+var_190]; pv
0x18001e33c  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18001e341  mov     [rsp+1E0h+var_1A8], 0
0x18001e349  jmp     short loc_18001E36D
0x18001e34b  test    rsi, rsi
0x18001e34e  jz      loc_18001E4CE
0x18001e354  mov     rax, [rsi]
0x18001e357  lea     r8, aResolveattribu; "ResolveAttributes call did not return a"...
0x18001e35e  mov     edx, r15d
0x18001e361  mov     rcx, rsi
0x18001e364  mov     rax, [rax+60h]
0x18001e368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36d  test    r13, r13
0x18001e370  jz      loc_18001E47F
0x18001e376  lea     rdx, [rsp+1E0h+var_198]; struct IClassFactory **
0x18001e37b  mov     rcx, r13; this
0x18001e37e  call    ?GetClassObject@CExtensionHelperInfo@@QEAAJPEAPEAUIClassFactory@@@Z; CExtensionHelperInfo::GetClassObject(IClassFactory * *)
0x18001e383  mov     ebx, eax
0x18001e385  test    eax, eax
0x18001e387  js      short loc_18001E3E5
0x18001e389  mov     r12, [rsp+1E0h+var_198]
0x18001e38e  test    r12, r12
0x18001e391  jz      loc_18001E4CE
0x18001e397  test    rsi, rsi
0x18001e39a  jz      short loc_18001E3DC
0x18001e39c  xor     edx, edx; Val
0x18001e39e  mov     r8d, 100h; Size
0x18001e3a4  lea     rcx, [rbp+0E0h+var_150]; void *
0x18001e3a8  call    memset_0
0x18001e3ad  mov     r9, [r13+0]
0x18001e3b1  lea     r8, aSuccessfullyLo; "Successfully loaded extension %s."
0x18001e3b8  mov     edx, 80h; unsigned __int64
0x18001e3bd  lea     rcx, [rbp+0E0h+var_150]; unsigned __int16 *
0x18001e3c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e3c6  mov     rax, [rsi]
0x18001e3c9  lea     r8, [rbp+0E0h+var_150]
0x18001e3cd  mov     edx, r15d
0x18001e3d0  mov     rcx, rsi
0x18001e3d3  mov     rax, [rax+60h]
0x18001e3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3dc  mov     [r14+20h], r13
0x18001e3e0  jmp     loc_18001E4CE
0x18001e3e5  test    rsi, rsi
0x18001e3e8  jz      short loc_18001E43A
0x18001e3ea  lea     rcx, [rsp+1E0h+pv]
0x18001e3ef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e3f4  nop
0x18001e3f5  mov     dword ptr [rsp+1E0h+var_1C0], ebx
0x18001e3f9  mov     rax, [rsp+1E0h+var_178]
0x18001e3fe  mov     r9, [rax]
0x18001e401  mov     r8, [r13+0]
0x18001e405  lea     rdx, aGetclassobject; "GetClassObject failed for extension %s "...
0x18001e40c  lea     rcx, [rsp+1E0h+pv]
0x18001e411  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001e416  mov     rax, [rsi]
0x18001e419  mov     rbx, [rsp+1E0h+pv]
0x18001e41e  mov     r8, rbx
0x18001e421  mov     edx, r15d
0x18001e424  mov     rcx, rsi
0x18001e427  mov     rax, [rax+60h]
0x18001e42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e430  nop
0x18001e431  lea     rcx, [rbx-18h]; this
0x18001e435  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e43a  mov     r12, [rsp+1E0h+var_198]
0x18001e43f  jmp     loc_18001E4CE
0x18001e444  test    rsi, rsi
0x18001e447  jz      loc_18001E4CE
0x18001e44d  xor     edx, edx; Val
0x18001e44f  mov     r8d, 100h; Size
0x18001e455  lea     rcx, [rbp+0E0h+var_150]; void *
  ... truncated ...
```
