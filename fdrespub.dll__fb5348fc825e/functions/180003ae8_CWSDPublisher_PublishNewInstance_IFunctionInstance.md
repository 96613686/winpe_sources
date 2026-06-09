# CWSDPublisher::PublishNewInstance(IFunctionInstance *)

- ea: `0x180003ae8`
- end: `0x180004164`
- name: `?PublishNewInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z`
- size: `1660`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this, struct IFunctionInstance *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800036b0`
- `0x18000399c`
- `0x180004640`

## callees

- `0x180001014`
- `0x180001020`
- `0x1800020f8`
- `0x180002930`
- `0x180002ad0`
- `0x180003404`
- `0x180003ae8`
- `0x180004348`
- `0x18000440c`
- `0x180005270`
- `0x180006010`

## import_xrefs

- `wsdapi!WSDFreeLinkedMemory` at `0x180003e22`
- `wsdapi!WSDFreeLinkedMemory` at `0x180003e49`
- `wsdapi!WSDFreeLinkedMemory` at `0x1800040b6`
- `wsdapi!WSDFreeLinkedMemory` at `0x180003e22`
- `wsdapi!WSDFreeLinkedMemory` at `0x180003e49`
- `wsdapi!WSDFreeLinkedMemory` at `0x1800040b6`
- `wsdapi!WSDXMLAddSibling` at `0x180004080`
- `wsdapi!WSDXMLAddSibling` at `0x180004080`
- `wsdapi!WSDXMLCleanupElement` at `0x180003e39`
- `wsdapi!WSDXMLCleanupElement` at `0x18000409e`
- `wsdapi!WSDXMLCleanupElement` at `0x180003e39`
- `wsdapi!WSDXMLCleanupElement` at `0x18000409e`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x180004027`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x18000404c`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x180004027`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x18000404c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003e5c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003e66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003e5c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003e66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ea2`

## string_xrefs

- `0x180003dca`: `http://schemas.microsoft.com/windows/pub/2005/07`
- `0x180003ff2`: `http://schemas.microsoft.com/windows/pub/2005/07`
- `0x180003ded`: `IWSDXMLContext::AddNameToNamespace -- type`
- `0x180004115`: `IWSDDeviceHost::AddDynamicService`
- `0x180004143`: `IWSDDeviceHost::SetServiceDiscoverable`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::PublishNewInstance(CWSDPublisher *this, struct IFunctionInstance *a2)
{
  WSDXML_ELEMENT *v2; // r12
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetID)(IFunctionInstance *, WCHAR **); // rax
  unsigned int v8; // esi
  unsigned int v9; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rcx
  int v11; // r9d
  const unsigned __int16 *v12; // r8
  int v13; // edx
  unsigned __int16 *v14; // r15
  _WORD *v15; // rax
  unsigned __int64 v16; // r8
  unsigned __int64 i; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // r12
  unsigned __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  unsigned __int16 *v24; // rax
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  unsigned __int64 v27; // r8
  unsigned __int16 *v28; // rdx
  unsigned __int16 *v29; // rcx
  int v30; // eax
  const struct _EVENT_DESCRIPTOR *v31; // rcx
  WCHAR *v32; // r14
  __int64 v33; // rdi
  __int64 v34; // rax
  unsigned int v35; // ebx
  unsigned __int16 *v36; // rax
  unsigned int v37; // ebx
  WCHAR *v38; // rdi
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  const wchar_t *v42; // r8
  unsigned __int16 *v43; // rax
  unsigned __int16 *v44; // rcx
  HRESULT v45; // eax
  const WCHAR *v46; // rdx
  WCHAR v47; // bx
  int v48; // eax
  const struct _EVENT_DESCRIPTOR *v49; // rcx
  int v50; // r9d
  const unsigned __int16 *v51; // r8
  WSDXML_ELEMENT *ppAny; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-B8h]
  WSDXML_NAME *pElementName; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h]
  void *pVoid; // [rsp+70h] [rbp-90h] BYREF
  int v59; // [rsp+78h] [rbp-88h]
  LPCWSTR pszText; // [rsp+80h] [rbp-80h]
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v62; // [rsp+98h] [rbp-68h]
  PROPVARIANT v63[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v65[32]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = 0;
  if ( !a2 )
    return 2147942487LL;
  pv = 0;
  v62 = 0;
  v64 = 0;
  lpVtbl = a2->lpVtbl;
  v56 = 0;
  v57 = 0;
  *(_OWORD *)pvar = 0;
  GetID = lpVtbl->GetID;
  *(_OWORD *)v63 = 0;
  v8 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))GetID)(a2, &pv);
  if ( v8 )
    goto LABEL_26;
  v8 = ((__int64 (__fastcall *)(struct IFunctionInstance *, _QWORD, __int64 *))a2->lpVtbl->OpenPropertyStore)(
         a2,
         0,
         &v56);
  if ( v8 )
    goto LABEL_26;
  v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v56 + 40LL))(
         v56,
         &PKEY_PUBSVCS_METADATA,
         pvar);
  v8 = v9;
  if ( !v9 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v56 + 40LL))(
           v56,
           &PKEY_PUBSVCS_TYPE,
           v63);
    v8 = v9;
    if ( v9 )
    {
      v11 = 1118;
      v12 = L"IPropertyStore::GetValue( PKEY_PUBSVCS_TYPE )";
      goto LABEL_9;
    }
    if ( LOWORD(pvar[0]) != 31 || (v15 = pvar[1]) == 0 || LOWORD(v63[0]) != 31 || !v63[1] )
    {
      v8 = -2147024809;
      v12 = L"PROPVARIANT type";
      v11 = 1131;
      v13 = -2147024809;
      goto LABEL_10;
    }
    v16 = *((unsigned int *)this + 22);
    for ( i = v16 >> 1; i; --i )
    {
      if ( !*v15 )
        break;
      ++v15;
    }
    v8 = i == 0 ? 0x80070057 : 0;
    if ( i )
      v18 = (v16 >> 1) - i;
    else
      v18 = 0;
    if ( i )
    {
      v19 = 2 * v18;
      v20 = 2 * v18 + *((unsigned int *)this + 23);
      v57 = 2 * v18;
      if ( v20 > v16 )
      {
        v8 = -2147467259;
        v2 = 0;
        goto LABEL_11;
      }
      v21 = CWSDPublisher::AddInstanceInfo(this, (const unsigned __int16 *)pv, v19);
      v57 = v19;
      v8 = v21;
      v2 = 0;
    }
    else
    {
      v57 = 0;
    }
LABEL_26:
    v14 = 0;
    if ( !v8 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)pv + v22) );
      v23 = (unsigned int)(v22 + 6);
      v24 = (unsigned __int16 *)operator new[](saturated_mul(v23, 2u));
      v14 = v24;
      if ( v24 )
      {
        if ( v23 )
        {
          if ( v23 <= 0x7FFFFFFF )
          {
            v25 = 2147483646;
            v26 = L"fdid:";
            v27 = v23;
            v28 = v14;
            do
            {
              if ( !v25 )
                break;
              if ( !*v26 )
                break;
              *v28++ = *v26++;
              --v25;
              --v27;
            }
            while ( v27 );
            v29 = v28 - 1;
            v8 = v27 == 0 ? 0x8007007A : 0;
            if ( v27 )
              v29 = v28;
            *v29 = 0;
            if ( v27 )
              v8 = StringCchCatW(v14, v23, (const unsigned __int16 *)pv);
          }
          else
          {
            v8 = -2147024809;
            *v24 = 0;
          }
        }
        else
        {
          v8 = -2147024809;
        }
      }
      else
      {
        v8 = -2147024882;
      }
    }
    goto LABEL_45;
  }
  v11 = 1110;
  v12 = L"IPropertyStore::GetValue( PKEY_PUBSVCS_METADATA )";
LABEL_9:
  v13 = v9;
LABEL_10:
  LogError(v10, v13, v12, v11);
LABEL_11:
  v14 = 0;
LABEL_45:
  pVoid = 0;
  pElementName = 0;
  if ( v8 )
  {
LABEL_48:
    v32 = 0;
    goto LABEL_49;
  }
  v30 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, PROPVARIANT, void **))(**((_QWORD **)this + 1) + 32LL))(
          *((_QWORD *)this + 1),
          L"http://schemas.microsoft.com/windows/pub/2005/07",
          v63[1],
          &pVoid);
  v8 = v30;
  if ( v30 )
  {
    LogError(v31, v30, L"IWSDXMLContext::AddNameToNamespace -- type", 1174);
    goto LABEL_48;
  }
  v33 = -1;
  v34 = -1;
  do
    ++v34;
  while ( *((_WORD *)pvar[1] + v34) );
  v35 = 2 * v34 + 1;
  v36 = (unsigned __int16 *)operator new[](saturated_mul(v35, 2u));
  v32 = v36;
  if ( !v36 )
  {
    v8 = -2147024882;
    goto LABEL_49;
  }
  v8 = EscapeString((const unsigned __int16 *)pvar[1], v36, v35);
  if ( v8 )
  {
LABEL_49:
    CWSDPublisher::FreeInstanceInfo(this, (const unsigned __int16 *)pv);
    goto LABEL_50;
  }
  do
    ++v33;
  while ( v32[v33] );
  v37 = v33 + 1;
  pszText = v32;
  v53 = v33 + 1;
  v38 = v32;
  v39 = 0;
  while ( v37 )
  {
    if ( !*v38 )
      goto LABEL_98;
    ppAny = 0;
    v40 = 32;
    v59 = v39 + 1;
    if ( v39 )
    {
      v8 = StringCchPrintfW(v65, 0x20u, L"Resource%d");
    }
    else
    {
      v41 = 2147483646;
      v42 = L"Resource";
      v43 = v65;
      do
      {
        if ( !v41 )
          break;
        if ( !*v42 )
          break;
        *v43++ = *v42++;
        --v41;
        --v40;
      }
      while ( v40 );
      v44 = v43 - 1;
      if ( v40 )
        v44 = v43;
      v8 = v40 == 0 ? 0x8007007A : 0;
      *v44 = 0;
    }
    if ( !v8 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 *, WSDXML_NAME **))(**((_QWORD **)this + 1)
                                                                                                  + 32LL))(
             *((_QWORD *)this + 1),
             L"http://schemas.microsoft.com/windows/pub/2005/07",
             v65,
             &pElementName);
      if ( !v8 )
      {
        if ( v37 >= 0x1FFE )
        {
          v46 = pszText;
          v38 += 8190;
          v47 = *v38;
          *v38 = 0;
          v45 = WSDXMLBuildAnyForSingleElement(pElementName, v46, &ppAny);
          *v38 = v47;
          v37 = v53 - 8190;
          pszText = v38;
        }
        else
        {
          v45 = WSDXMLBuildAnyForSingleElement(pElementName, v38, &ppAny);
          v37 = 0;
        }
        v53 = v37;
        v8 = v45;
        if ( !v2 )
        {
          v2 = ppAny;
LABEL_94:
          ppAny = 0;
          goto LABEL_95;
        }
        v8 = WSDXMLAddSibling(v2, ppAny);
        if ( !v8 )
          ppAny = 0;
      }
    }
    if ( ppAny )
    {
      WSDXMLCleanupElement(ppAny);
      goto LABEL_94;
    }
LABEL_95:
    if ( pElementName )
    {
      WSDFreeLinkedMemory(pElementName);
      pElementName = 0;
    }
    v39 = v59;
    if ( v8 )
    {
LABEL_98:
      if ( v8 )
        goto LABEL_49;
      break;
    }
  }
  v48 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, void *, WSDXML_ELEMENT *, _QWORD))(**((_QWORD **)this + 9) + 88LL))(
          *((_QWORD *)this + 9),
          v14,
          *((_QWORD *)this + 8),
          0,
          pVoid,
          v2,
          0);
  v8 = v48;
  if ( v48 )
  {
    v50 = 1272;
    v51 = L"IWSDDeviceHost::AddDynamicService";
    goto LABEL_103;
  }
  v48 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 9) + 104LL))(
          *((_QWORD *)this + 9),
          v14,
          1);
  v8 = v48;
  if ( v48 )
  {
    v50 = 1280;
    v51 = L"IWSDDeviceHost::SetServiceDiscoverable";
LABEL_103:
    LogError(v49, v48, v51, v50);
    goto LABEL_49;
  }
  *((_DWORD *)this + 23) += v57;
LABEL_50:
  if ( v14 )
    operator delete[](v14);
  if ( pVoid )
  {
    WSDFreeLinkedMemory(pVoid);
    pVoid = 0;
  }
  if ( v2 )
    WSDXMLCleanupElement(v2);
  if ( pElementName )
  {
    WSDFreeLinkedMemory(pElementName);
    pElementName = 0;
  }
  PropVariantClear(pvar);
  PropVariantClear(v63);
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v32 )
    operator delete[](v32);
  if ( pv )
    CoTaskMemFree(pv);
  return v8;
}

```

## disassembly

```asm
0x180003ae8  mov     [rsp-8+arg_10], rbx
0x180003aed  push    rbp
0x180003aee  push    rsi
0x180003aef  push    rdi
0x180003af0  push    r12
0x180003af2  push    r13
0x180003af4  push    r14
0x180003af6  push    r15
0x180003af8  lea     rbp, [rsp-10h]
0x180003afd  sub     rsp, 110h
0x180003b04  mov     rax, cs:__security_cookie
0x180003b0b  xor     rax, rsp
0x180003b0e  mov     [rbp+40h+var_40], rax
0x180003b12  xor     r12d, r12d
0x180003b15  mov     rdi, rdx
0x180003b18  mov     r13, rcx
0x180003b1b  test    rdx, rdx
0x180003b1e  jnz     short loc_180003B2A
0x180003b20  mov     eax, 80070057h
0x180003b25  jmp     loc_180003EAA
0x180003b2a  xor     eax, eax
0x180003b2c  mov     [rsp+140h+pv], r12
0x180003b31  mov     [rbp+40h+var_A8], rax
0x180003b35  xorps   xmm0, xmm0
0x180003b38  mov     [rbp+40h+var_90], rax
0x180003b3c  xorps   xmm1, xmm1
0x180003b3f  mov     rax, [rdx]
0x180003b42  mov     rcx, rdi
0x180003b45  lea     rdx, [rsp+140h+pv]
0x180003b4a  mov     [rsp+140h+var_E0], r12
0x180003b4f  mov     [rsp+140h+var_D8], r12
0x180003b54  movups  xmmword ptr [rbp+40h+pvar], xmm0
0x180003b58  mov     rax, [rax+20h]
0x180003b5c  movups  xmmword ptr [rbp+40h+var_A0], xmm1
0x180003b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b65  or      r14, 0FFFFFFFFFFFFFFFFh
0x180003b69  mov     esi, eax
0x180003b6b  mov     ebx, 80070057h
0x180003b70  test    eax, eax
0x180003b72  jnz     loc_180003CBA
0x180003b78  mov     rax, [rdi]
0x180003b7b  lea     r8, [rsp+140h+var_E0]
0x180003b80  xor     edx, edx
0x180003b82  mov     rcx, rdi
0x180003b85  mov     rax, [rax+30h]
0x180003b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8e  mov     esi, eax
0x180003b90  test    eax, eax
0x180003b92  jnz     loc_180003CBA
0x180003b98  mov     rcx, [rsp+140h+var_E0]
0x180003b9d  lea     r8, [rbp+40h+pvar]
0x180003ba1  lea     rdx, PKEY_PUBSVCS_METADATA
0x180003ba8  mov     rax, [rcx]
0x180003bab  mov     rax, [rax+28h]
0x180003baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb4  mov     esi, eax
0x180003bb6  test    eax, eax
0x180003bb8  jz      short loc_180003BC9
0x180003bba  mov     r9d, 456h
0x180003bc0  lea     r8, aIpropertystore_0; "IPropertyStore::GetValue( PKEY_PUBSVCS_"...
0x180003bc7  jmp     short loc_180003BF8
0x180003bc9  mov     rcx, [rsp+140h+var_E0]
0x180003bce  lea     r8, [rbp+40h+var_A0]
0x180003bd2  lea     rdx, PKEY_PUBSVCS_TYPE
0x180003bd9  mov     rax, [rcx]
0x180003bdc  mov     rax, [rax+28h]
0x180003be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be5  mov     esi, eax
0x180003be7  test    eax, eax
0x180003be9  jz      short loc_180003C07
0x180003beb  mov     r9d, 45Eh; unsigned int
0x180003bf1  lea     r8, aIpropertystore; "IPropertyStore::GetValue( PKEY_PUBSVCS_"...
0x180003bf8  mov     edx, eax; int
0x180003bfa  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x180003bff  mov     r15, r12
0x180003c02  jmp     loc_180003DAF
0x180003c07  cmp     word ptr [rbp+40h+pvar], 1Fh
0x180003c0c  jnz     loc_180003D1C
0x180003c12  mov     rax, [rbp+40h+pvar+8]
0x180003c16  test    rax, rax
0x180003c19  jz      loc_180003D1C
0x180003c1f  cmp     word ptr [rbp+40h+var_A0], 1Fh
0x180003c24  jnz     loc_180003D1C
0x180003c2a  cmp     [rbp+40h+var_A0+8], r12
0x180003c2e  jz      loc_180003D1C
0x180003c34  test    rax, rax
0x180003c37  jz      loc_180003D13
0x180003c3d  mov     r8d, [r13+58h]
0x180003c41  mov     ecx, r8d
0x180003c44  shr     rcx, 1
0x180003c47  mov     rdx, rcx
0x180003c4a  jz      short loc_180003C5C
0x180003c4c  cmp     [rax], r12w
0x180003c50  jz      short loc_180003C5C
0x180003c52  add     rax, 2
0x180003c56  sub     rcx, 1
0x180003c5a  jnz     short loc_180003C4C
0x180003c5c  mov     rax, rcx
0x180003c5f  neg     rax
0x180003c62  sbb     esi, esi
0x180003c64  not     esi
0x180003c66  and     esi, ebx
0x180003c68  test    rcx, rcx
0x180003c6b  jz      short loc_180003C72
0x180003c6d  sub     rdx, rcx
0x180003c70  jmp     short loc_180003C75
0x180003c72  mov     rdx, r12
0x180003c75  test    rcx, rcx
0x180003c78  jz      loc_180003D15
0x180003c7e  mov     eax, [r13+5Ch]
0x180003c82  lea     r12, [rdx+rdx]
0x180003c86  add     rax, r12
0x180003c89  mov     [rsp+140h+var_D8], r12
0x180003c8e  cmp     rax, r8
0x180003c91  jbe     short loc_180003CA0
0x180003c93  mov     esi, 80004005h
0x180003c98  xor     r12d, r12d
0x180003c9b  jmp     loc_180003BFF
0x180003ca0  mov     rdx, [rsp+140h+pv]; unsigned __int16 *
0x180003ca5  mov     r8d, r12d; unsigned int
0x180003ca8  mov     rcx, r13; this
0x180003cab  call    ?AddInstanceInfo@CWSDPublisher@@IEAAJPEBGK@Z; CWSDPublisher::AddInstanceInfo(ushort const *,ulong)
0x180003cb0  mov     [rsp+140h+var_D8], r12
0x180003cb5  mov     esi, eax
0x180003cb7  xor     r12d, r12d
0x180003cba  mov     r15, r12
0x180003cbd  test    esi, esi
0x180003cbf  jnz     loc_180003DAF
0x180003cc5  mov     rcx, [rsp+140h+pv]
0x180003cca  mov     rax, r14
0x180003ccd  inc     rax
0x180003cd0  cmp     [rcx+rax*2], r12w
0x180003cd5  jnz     short loc_180003CCD
0x180003cd7  lea     edi, [rax+6]
0x180003cda  mov     eax, 2
0x180003cdf  mul     rdi
0x180003ce2  cmovb   rax, r14
0x180003ce6  mov     rcx, rax; unsigned __int64
0x180003ce9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003cee  mov     r15, rax
0x180003cf1  test    rax, rax
0x180003cf4  jz      loc_180003DAA
0x180003cfa  test    rdi, rdi
0x180003cfd  jz      loc_180003D9D
0x180003d03  cmp     rdi, 7FFFFFFFh
0x180003d0a  jbe     short loc_180003D32
0x180003d0c  mov     esi, ebx
0x180003d0e  jmp     loc_180003DA4
0x180003d13  mov     esi, ebx
0x180003d15  mov     [rsp+140h+var_D8], r12
0x180003d1a  jmp     short loc_180003CBA
0x180003d1c  mov     esi, ebx
0x180003d1e  lea     r8, aPropvariantTyp; "PROPVARIANT type"
0x180003d25  mov     r9d, 46Bh
0x180003d2b  mov     edx, ebx
0x180003d2d  jmp     loc_180003BFA
0x180003d32  mov     eax, 7FFFFFFEh
0x180003d37  lea     rcx, aFdid; "fdid:"
0x180003d3e  mov     r8, rdi
0x180003d41  mov     rdx, r15
0x180003d44  test    rax, rax
0x180003d47  jz      short loc_180003D68
0x180003d49  movzx   r9d, word ptr [rcx]
0x180003d4d  test    r9w, r9w
0x180003d51  jz      short loc_180003D68
0x180003d53  mov     [rdx], r9w
0x180003d57  add     rcx, 2
0x180003d5b  add     rdx, 2
0x180003d5f  dec     rax
0x180003d62  sub     r8, 1
0x180003d66  jnz     short loc_180003D44
0x180003d68  mov     rax, r8
0x180003d6b  lea     rcx, [rdx-2]
0x180003d6f  neg     rax
0x180003d72  sbb     esi, esi
0x180003d74  not     esi
0x180003d76  and     esi, 8007007Ah
0x180003d7c  test    r8, r8
0x180003d7f  cmovnz  rcx, rdx
0x180003d83  mov     [rcx], r12w
0x180003d87  jz      short loc_180003DAF
0x180003d89  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x180003d8e  mov     rdx, rdi; unsigned __int64
0x180003d91  mov     rcx, r15; unsigned __int16 *
0x180003d94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003d99  mov     esi, eax
0x180003d9b  jmp     short loc_180003DAF
0x180003d9d  mov     esi, ebx
0x180003d9f  test    rdi, rdi
0x180003da2  jz      short loc_180003DAF
0x180003da4  mov     [rax], r12w
0x180003da8  jmp     short loc_180003DAF
0x180003daa  mov     esi, 8007000Eh
0x180003daf  mov     [rsp+140h+pVoid], r12
0x180003db4  mov     [rsp+140h+pElementName], r12
0x180003db9  test    esi, esi
0x180003dbb  jnz     short loc_180003DFB
0x180003dbd  mov     rcx, [r13+8]
0x180003dc1  lea     r9, [rsp+140h+pVoid]
0x180003dc6  mov     r8, [rbp+40h+var_A0+8]
0x180003dca  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/pu"...
0x180003dd1  mov     rax, [rcx]
0x180003dd4  mov     rax, [rax+20h]
0x180003dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ddd  mov     esi, eax
0x180003ddf  test    eax, eax
0x180003de1  jz      loc_180003ED1
0x180003de7  mov     r9d, 496h; unsigned int
0x180003ded  lea     r8, aIwsdxmlcontext_0; "IWSDXMLContext::AddNameToNamespace -- t"...
0x180003df4  mov     edx, eax; int
0x180003df6  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x180003dfb  mov     r14, r12
0x180003dfe  mov     rdx, [rsp+140h+pv]; unsigned __int16 *
0x180003e03  mov     rcx, r13; this
0x180003e06  call    ?FreeInstanceInfo@CWSDPublisher@@IEAAJPEBG@Z; CWSDPublisher::FreeInstanceInfo(ushort const *)
0x180003e0b  test    r15, r15
0x180003e0e  jz      short loc_180003E18
0x180003e10  mov     rcx, r15; Block
0x180003e13  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003e18  mov     rcx, [rsp+140h+pVoid]; pVoid
0x180003e1d  test    rcx, rcx
0x180003e20  jz      short loc_180003E31
0x180003e22  call    cs:__imp_WSDFreeLinkedMemory
0x180003e28  mov     [rsp+140h+pVoid], 0
0x180003e31  test    r12, r12
0x180003e34  jz      short loc_180003E3F
0x180003e36  mov     rcx, r12; pAny
0x180003e39  call    cs:__imp_WSDXMLCleanupElement
0x180003e3f  mov     rcx, [rsp+140h+pElementName]; pVoid
0x180003e44  test    rcx, rcx
0x180003e47  jz      short loc_180003E58
0x180003e49  call    cs:__imp_WSDFreeLinkedMemory
0x180003e4f  mov     [rsp+140h+pElementName], 0
0x180003e58  lea     rcx, [rbp+40h+pvar]; pvar
0x180003e5c  call    cs:__imp_PropVariantClear
0x180003e62  lea     rcx, [rbp+40h+var_A0]; pvar
0x180003e66  call    cs:__imp_PropVariantClear
0x180003e6c  mov     rcx, [rsp+140h+var_E0]
0x180003e71  test    rcx, rcx
0x180003e74  jz      short loc_180003E8B
0x180003e76  mov     rax, [rcx]
0x180003e79  mov     rax, [rax+10h]
0x180003e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e82  mov     [rsp+140h+var_E0], 0
0x180003e8b  test    r14, r14
0x180003e8e  jz      short loc_180003E98
0x180003e90  mov     rcx, r14; Block
0x180003e93  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003e98  mov     rcx, [rsp+140h+pv]; pv
0x180003e9d  test    rcx, rcx
0x180003ea0  jz      short loc_180003EA8
0x180003ea2  call    cs:__imp_CoTaskMemFree
0x180003ea8  mov     eax, esi
0x180003eaa  mov     rcx, [rbp+40h+var_40]
0x180003eae  xor     rcx, rsp; StackCookie
0x180003eb1  call    __security_check_cookie
0x180003eb6  mov     rbx, [rsp+140h+arg_10]
0x180003ebe  add     rsp, 110h
0x180003ec5  pop     r15
0x180003ec7  pop     r14
0x180003ec9  pop     r13
0x180003ecb  pop     r12
0x180003ecd  pop     rdi
0x180003ece  pop     rsi
0x180003ecf  pop     rbp
0x180003ed0  retn
0x180003ed1  mov     rcx, [rbp+40h+pvar+8]
0x180003ed5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003ed9  mov     rax, rdi
0x180003edc  inc     rax
0x180003edf  cmp     [rcx+rax*2], r12w
0x180003ee4  jnz     short loc_180003EDC
0x180003ee6  lea     ebx, ds:1[rax*2]
0x180003eed  mov     eax, 2
0x180003ef2  mov     ecx, ebx
0x180003ef4  mul     rcx
0x180003ef7  cmovb   rax, rdi
0x180003efb  mov     rcx, rax; unsigned __int64
0x180003efe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003f03  mov     r14, rax
0x180003f06  test    rax, rax
0x180003f09  jnz     short loc_180003F15
0x180003f0b  mov     esi, 8007000Eh
0x180003f10  jmp     loc_180003DFE
0x180003f15  mov     rcx, [rbp+40h+pvar+8]; unsigned __int16 *
0x180003f19  mov     r8d, ebx; unsigned int
0x180003f1c  mov     rdx, r14; unsigned __int16 *
0x180003f1f  call    ?EscapeString@@YAJPEBGPEAGK@Z; EscapeString(ushort const *,ushort *,ulong)
0x180003f24  xor     r11d, r11d
0x180003f27  mov     esi, eax
0x180003f29  test    eax, eax
0x180003f2b  jnz     loc_180003DFE
0x180003f31  inc     rdi
0x180003f34  cmp     [r14+rdi*2], r11w
0x180003f39  jnz     short loc_180003F31
0x180003f3b  lea     ebx, [rdi+1]
0x180003f3e  mov     [rbp+40h+pszText], r14
0x180003f42  mov     [rsp+140h+var_F8], ebx
0x180003f46  mov     rdi, r14
0x180003f49  mov     eax, r11d
  ... truncated ...
```
