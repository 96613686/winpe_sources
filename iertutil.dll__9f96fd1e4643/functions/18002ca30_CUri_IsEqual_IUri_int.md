# CUri::IsEqual(IUri *,int *)

- ea: `0x18002ca30`
- end: `0x18002d62e`
- name: `?IsEqual@CUri@@UEAAJPEAUIUri@@PEAH@Z`
- size: `3070`
- prototype: `__int64 __fastcall(struct IUri *this, struct IUri *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18002a420`
- `0x18002b680`
- `0x18002ca30`
- `0x18002d634`
- `0x18002dcb0`
- `0x18007c5c0`
- `0x18007fb4c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d332`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d4fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d56a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d5d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d332`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d4fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d56a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d5d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d31e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d31e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ced7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ced7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d402`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d472`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d402`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d472`

## pseudocode

```c
__int64 __fastcall CUri::IsEqual(struct IUri *this, struct IUri *a2, int *a3)
{
  __int64 result; // rax
  struct IUri *v7; // r15
  struct IUri v8; // rax
  int v9; // r14d
  int v10; // eax
  struct IUriVtbl *lpVtbl; // rax
  int v12; // ebx
  CUriPrivWrapper *v13; // rcx
  int v14; // esi
  struct IUriVtbl *v15; // rax
  __int64 v16; // rbx
  bool v17; // di
  struct IUriVtbl *v18; // rax
  struct IUri *v19; // rbx
  bool v20; // di
  unsigned int v21; // esi
  _DWORD *v22; // rdi
  int v23; // ebx
  int v24; // eax
  LPCWCH v25; // rcx
  int v26; // eax
  int v27; // edx
  struct IUriVtbl *v28; // rax
  int v29; // ebx
  CUriPrivWrapper *v30; // rcx
  int UriPriv; // eax
  __int64 v32; // rcx
  BOOL v33; // ebx
  int v34; // eax
  __int64 v35; // rcx
  BOOL v36; // ebx
  struct IUri v37; // rax
  struct IUriVtbl *v38; // rax
  int v39; // ebx
  int v40; // eax
  HANDLE ProcessHeap; // rax
  CUriPrivWrapper *v42; // rax
  CUriPrivWrapper *v43; // rax
  int v44; // ebx
  int v45; // eax
  HANDLE v46; // rax
  CUriPrivWrapper *v47; // rax
  CUriPrivWrapper *v48; // rax
  HANDLE v49; // rax
  CUriPrivWrapper *v50; // rax
  CUriPrivWrapper *v51; // rax
  HANDLE v52; // rax
  CUriPrivWrapper *v53; // rax
  CUriPrivWrapper *v54; // rax
  int cchCount2; // [rsp+48h] [rbp-69h] BYREF
  int v56[2]; // [rsp+50h] [rbp-61h] BYREF
  int cchCount1; // [rsp+58h] [rbp-59h] BYREF
  __int64 v58; // [rsp+60h] [rbp-51h] BYREF
  CUriPrivWrapper *v59; // [rsp+68h] [rbp-49h] BYREF
  CUriPrivWrapper *v60; // [rsp+70h] [rbp-41h] BYREF
  struct IUri *v61; // [rsp+78h] [rbp-39h]
  void **v62; // [rsp+80h] [rbp-31h] BYREF
  __int64 v63; // [rsp+88h] [rbp-29h]
  int v64; // [rsp+90h] [rbp-21h]
  BSTR bstrString[2]; // [rsp+98h] [rbp-19h]
  int v66; // [rsp+A8h] [rbp-9h]
  int v67; // [rsp+B0h] [rbp-1h] BYREF
  int v68; // [rsp+B4h] [rbp+3h] BYREF
  int v69; // [rsp+B8h] [rbp+7h] BYREF
  LPCWCH lpString1; // [rsp+C0h] [rbp+Fh] BYREF
  LPCWCH lpString2; // [rsp+C8h] [rbp+17h] BYREF
  int v73; // [rsp+130h] [rbp+7Fh] BYREF

  v73 = 0;
  v67 = 0;
  v69 = 0;
  v68 = 0;
  v59 = 0;
  v60 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  result = 0;
  if ( a2 )
  {
    if ( SLODWORD(this[4].lpVtbl) >= 0 )
    {
      return 2147549183LL;
    }
    else
    {
      if ( this == (struct IUri *)16 )
      {
        v7 = 0;
      }
      else
      {
        if ( this == a2 )
        {
          *a3 = 1;
          return result;
        }
        v7 = this;
      }
      v8.lpVtbl = v7->lpVtbl;
      v61 = a2;
      v9 = ((__int64 (__fastcall *)(struct IUri *, int *))v8.lpVtbl->GetScheme)(v7, &v73);
      if ( v9 < 0 )
        goto LABEL_68;
      v9 = ((__int64 (__fastcall *)(struct IUri *, int *))a2->lpVtbl->GetScheme)(a2, &v67);
      if ( v9 < 0 )
        goto LABEL_68;
      v10 = v73;
      if ( v73 != v67 )
      {
        *a3 = 0;
        goto LABEL_68;
      }
      if ( v73 != 9 )
      {
        if ( LOBYTE(this[41].lpVtbl) )
        {
          lpVtbl = a2->lpVtbl;
          *(_QWORD *)v56 = 0;
          cchCount1 = ((__int64 (__fastcall *)(struct IUri *, GUID *, int *))lpVtbl->QueryInterface)(
                        a2,
                        &IID_IUriPriv2,
                        v56);
          v12 = cchCount1;
          if ( cchCount1 < 0 )
          {
            ProcessHeap = GetProcessHeap();
            v42 = (CUriPrivWrapper *)HeapAlloc(ProcessHeap, 8u, 0x98u);
            if ( v42 )
            {
              v43 = CUriPrivWrapper::CUriPrivWrapper(v42, a2, &cchCount1);
              v12 = cchCount1;
              v13 = v43;
            }
            else
            {
              v13 = 0;
            }
            *(_QWORD *)v56 = v13;
            if ( v12 >= 0 )
            {
              v12 = 0;
              if ( !v13 )
                v12 = -2147024882;
            }
            else
            {
              if ( v13 )
                CUriPrivWrapper::`scalar deleting destructor'(v13, 1u);
              v13 = 0;
              *(_QWORD *)v56 = 0;
            }
          }
          else
          {
            v13 = *(CUriPrivWrapper **)v56;
          }
          if ( v12 >= 0 )
          {
            cchCount1 = 0;
            if ( (*(int (__fastcall **)(CUriPrivWrapper *, int *))(*(_QWORD *)v13 + 416LL))(v13, &cchCount1) >= 0
              && HIDWORD(this[40].lpVtbl) != cchCount1 )
            {
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
              *a3 = 0;
              goto LABEL_68;
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
          }
        }
        v10 = v73;
      }
      v14 = 16;
      if ( v10 == 9 )
      {
        v38 = v7->lpVtbl;
        cchCount1 = 0;
        cchCount2 = 0;
        v39 = ((__int64 (__fastcall *)(struct IUri *, GUID *, CUriPrivWrapper **))v38->QueryInterface)(
                v7,
                &IID_IUriPriv,
                &v59);
        v40 = ((__int64 (__fastcall *)(struct IUri *, GUID *, CUriPrivWrapper **))a2->lpVtbl->QueryInterface)(
                a2,
                &IID_IUriPriv,
                &v60);
        if ( v39 >= 0 && v40 >= 0 )
        {
          v44 = (*(__int64 (__fastcall **)(CUriPrivWrapper *, int *))(*(_QWORD *)v59 + 376LL))(v59, &cchCount1);
          v45 = (*(__int64 (__fastcall **)(CUriPrivWrapper *, int *))(*(_QWORD *)v60 + 376LL))(v60, &cchCount2);
          if ( !v44 && !v45 && (((unsigned __int8)cchCount2 ^ (unsigned __int8)cchCount1) & 0x20) != 0 )
            v14 = 48;
        }
        if ( v59 )
        {
          (*(void (__fastcall **)(CUriPrivWrapper *))(*(_QWORD *)v59 + 16LL))(v59);
          v59 = 0;
        }
        if ( v60 )
        {
          (*(void (__fastcall **)(CUriPrivWrapper *))(*(_QWORD *)v60 + 16LL))(v60);
          v60 = 0;
        }
      }
      v15 = v7->lpVtbl;
      v16 = 0;
      *(_QWORD *)v56 = 0;
      cchCount2 = 0;
      v58 = 0;
      if ( ((int (__fastcall *)(struct IUri *, GUID *, int *))v15->QueryInterface)(
             v7,
             &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
             v56) < 0 )
      {
        cchCount2 = HelperAddUriDefaultFlags(0x3002B80u, 5u);
      }
      else
      {
        v17 = 1;
        if ( !(*(unsigned int (__fastcall **)(_QWORD, int *))(**(_QWORD **)v56 + 376LL))(*(_QWORD *)v56, &cchCount2) )
          v17 = (v14 & cchCount2) != 0;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
        *(_QWORD *)v56 = 0;
        if ( !v17 )
          goto LABEL_24;
      }
      v62 = &CUString::`vftable';
      v63 = 0;
      v64 = 11;
      v66 = 0;
      *(_OWORD *)bstrString = 0;
      v9 = CUString::Set((CUString *)&v62, v7, Uri_PROPERTY_RAW_URI);
      if ( !v9 )
      {
        UriPriv = CreateUriPriv(bstrString[1], 0, cchCount2 & (unsigned int)~v14, 0, 0, 0, 0, (struct IUri **)&v58);
        v62 = &CUString::`vftable';
        v9 = UriPriv;
        if ( UriPriv < 0 )
        {
          v32 = v63;
          v33 = v63 != 0;
          if ( v63 || v64 != 11 )
          {
            if ( bstrString[0] )
            {
              SysFreeString(bstrString[0]);
              v32 = v63;
              bstrString[0] = 0;
            }
            bstrString[1] = 0;
            v66 = 0;
            if ( v33 && v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          v64 = 11;
          goto LABEL_68;
        }
        CUString::Set((CUString *)&v62, 0, Uri_PROPERTY_RAW_URI);
        v16 = v58;
LABEL_136:
        if ( v16 )
        {
LABEL_25:
          if ( (struct IUri *)v16 != v7 )
            v7 = (struct IUri *)v16;
          v18 = a2->lpVtbl;
          v19 = 0;
          *(_QWORD *)v56 = 0;
          cchCount2 = 0;
          v58 = 0;
          if ( ((int (__fastcall *)(struct IUri *, GUID *, int *))v18->QueryInterface)(
                 a2,
                 &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
                 v56) < 0 )
          {
            cchCount2 = HelperAddUriDefaultFlags(0x3002B80u, 5u);
          }
          else
          {
            v20 = 1;
            if ( !(*(unsigned int (__fastcall **)(_QWORD, int *))(**(_QWORD **)v56 + 376LL))(*(_QWORD *)v56, &cchCount2) )
              v20 = (v14 & cchCount2) != 0;
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
            *(_QWORD *)v56 = 0;
            if ( !v20 )
              goto LABEL_31;
          }
          v62 = &CUString::`vftable';
          v63 = 0;
          v64 = 11;
          v66 = 0;
          *(_OWORD *)bstrString = 0;
          v9 = CUString::Set((CUString *)&v62, a2, Uri_PROPERTY_RAW_URI);
          if ( !v9 )
          {
            v34 = CreateUriPriv(bstrString[1], 0, cchCount2 & (unsigned int)~v14, 0, 0, 0, 0, (struct IUri **)&v58);
            v62 = &CUString::`vftable';
            v9 = v34;
            if ( v34 < 0 )
            {
              v35 = v63;
              v36 = v63 != 0;
              if ( v63 || v64 != 11 )
              {
                if ( bstrString[0] )
                {
                  SysFreeString(bstrString[0]);
                  v35 = v63;
                  bstrString[0] = 0;
                }
                bstrString[1] = 0;
                v66 = 0;
                if ( v36 && v35 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              }
              v37.lpVtbl = v7->lpVtbl;
              v64 = 11;
              ((void (__fastcall *)(struct IUri *))v37.lpVtbl->Release)(v7);
              goto LABEL_68;
            }
            CUString::Set((CUString *)&v62, 0, Uri_PROPERTY_RAW_URI);
            v19 = (struct IUri *)v58;
LABEL_142:
            if ( v19 )
            {
LABEL_32:
              if ( v19 == a2 )
                v19 = a2;
              else
                v61 = v19;
              v9 = ((__int64 (__fastcall *)(struct IUri *, int *))v7->lpVtbl->GetPort)(v7, &v69);
              if ( v9 < 0 )
                goto LABEL_65;
              v9 = ((__int64 (__fastcall *)(struct IUri *, int *))v19->lpVtbl->GetPort)(v19, &v68);
              if ( v9 < 0 )
                goto LABEL_65;
              v21 = 0;
              if ( v69 != v68 )
              {
                *a3 = 0;
                ((void (__fastcall *)(struct IUri *))v7->lpVtbl->Release)(v7);
                goto LABEL_67;
              }
              v59 = 0;
              v56[0] = ((__int64 (__fastcall *)(struct IUri *, GUID *, CUriPrivWrapper **))v7->lpVtbl->QueryInterface)(
                         v7,
                         &IID_IUriPriv,
                         &v59);
              v9 = v56[0];
              if ( v56[0] < 0 )
              {
                v46 = GetProcessHeap();
                v47 = (CUriPrivWrapper *)HeapAlloc(v46, 8u, 0x98u);
                if ( v47 )
                {
                  v48 = CUriPrivWrapper::CUriPrivWrapper(v47, v7, v56);
                  v9 = v56[0];
                }
                else
                {
                  v48 = 0;
                }
                v59 = v48;
                if ( v9 >= 0 )
                {
                  v9 = 0;
                  if ( !v48 )
                    v9 = -2147024882;
                }
                else
                {
                  if ( v48 )
                    CUriPrivWrapper::`scalar deleting destructor'(v48, 1u);
                  v59 = 0;
                }
              }
              if ( v9 < 0 )
              {
                ((void (__fastcall *)(struct IUri *))v7->lpVtbl->Release)(v7);
                goto LABEL_67;
              }
              v60 = 0;
              v56[0] = ((__int64 (__fastcall *)(struct IUri *, GUID *, CUriPrivWrapper **))v19->lpVtbl->QueryInterface)(
                         v19,
                         &IID_IUriPriv,
                         &v60);
              v9 = v56[0];
              if ( v56[0] < 0 )
              {
                v49 = GetProcessHeap();
                v50 = (CUriPrivWrapper *)HeapAlloc(v49, 8u, 0x98u);
                if ( v50 )
                {
                  v51 = CUriPrivWrapper::CUriPrivWrapper(v50, v19, v56);
                  v9 = v56[0];
                }
                else
                {
                  v51 = 0;
                }
                v60 = v51;
                if ( v9 >= 0 )
                {
                  v9 = 0;
                  if ( !v51 )
                    v9 = -2147024882;
                }
                else
                {
                  if ( v51 )
                    CUriPrivWrapper::`scalar deleting destructor'(v51, 1u);
                  v60 = 0;
                }
              }
              if ( v9 < 0 )
              {
LABEL_65:
                ((void (__fastcall *)(struct IUri *))v7->lpVtbl->Release)(v7);
                goto LABEL_66;
              }
              lpString1 = 0;
              cchCount1 = 0;
              lpString2 = 0;
              cchCount2 = 0;
              while ( 1 )
              {
                if ( v21 >= 7 )
                {
                  *a3 = 1;
                  ((void (__fastcall *)(struct IUri *))v7->lpVtbl->Release)(v7);
LABEL_66:
                  v19 = v61;
LABEL_67:
                  ((void (__fastcall *)(struct IUri *))v19->lpVtbl->Release)(v19);
                  goto LABEL_68;
                }
                v22 = (_DWORD *)qword_180175910 + v21;
                v23 = (*(__int64 (__fastcall **)(CUriPrivWrapper *, _QWORD, LPCWCH *, int *))(*(_QWORD *)v59 + 224LL))(
                        v59,
                        (unsigned int)*v22,
                        &lpString1,
                        &cchCount1);
                v9 = v23;
                if ( v23 < 0 )
                  goto LABEL_65;
                v24 = (*(__int64 (__fastcall **)(CUriPrivWrapper *, _QWORD, LPCWCH *, int *))(*(_QWORD *)v60 + 224LL))(
                        v60,
                        (unsigned int)*v22,
                        &lpString2,
                        &cchCount2);
                v9 = v24;
                if ( v24 < 0 )
                  goto LABEL_65;
                v9 = 0;
                if ( v23 != v24 )
                {
LABEL_64:
                  *a3 = 0;
                  goto LABEL_65;
                }
                if ( !v23 )
                {
                  if ( v73 == 9 )
                  {
                    if ( *v22 == 8 )
                    {
                      if ( cchCount1 != cchCount2
                        || lpString1 != lpString2
                        && CompareStringOrdinal(lpString1, cchCount1, lpString2, cchCount2, 1) != 2 )
                      {
                        goto LABEL_64;
                      }
                      goto LABEL_54;
                    }
                  }
                  else if ( *v22 == 8 )
                  {
                    if ( !LOBYTE(this[41].lpVtbl) )
                    {
                      HIDWORD(this[40].lpVtbl) = CreateStringHashN(
                                                   (const unsigned __int8 *)lpString1,
                                                   2LL * (unsigned int)cchCount1);
                      LOBYTE(this[41].lpVtbl) = 1;
                    }
                    v28 = a2->lpVtbl;
                    v58 = 0;
                    v56[0] = ((__int64 (__fastcall *)(struct IUri *, GUID *, __int64 *))v28->QueryInterface)(
                               a2,
                               &IID_IUriPriv2,
                               &v58);
                    v29 = v56[0];
                    if ( v56[0] < 0 )
                    {
                      v52 = GetProcessHeap();
                      v53 = (CUriPrivWrapper *)HeapAlloc(v52, 8u, 0x98u);
                      if ( v53 )
                      {
                        v54 = CUriPrivWrapper::CUriPrivWrapper(v53, a2, v56);
                        v29 = v56[0];
                        v30 = v54;
                      }
                      else
                      {
                        v30 = 0;
                      }
                      v58 = (__int64)v30;
                      if ( v29 >= 0 )
                      {
                        v29 = 0;
                        if ( !v30 )
                          v29 = -2147024882;
                      }
                      else
                      {
                        if ( v30 )
                          CUriPrivWrapper::`scalar deleting destructor'(v30, 1u);
                        v30 = 0;
                        v58 = 0;
                      }
                    }
                    else
                    {
                      v30 = (CUriPrivWrapper *)v58;
                    }
                    if ( v29 >= 0 )
                    {
                      v56[0] = 0;
                      if ( (*(int (__fastcall **)(CUriPrivWrapper *, int *))(*(_QWORD *)v30 + 416LL))(v30, v56) < 0 )
                      {
                        v56[0] = CreateStringHashN((const unsigned __int8 *)lpString2, 2LL * (unsigned int)cchCount2);
                        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 424LL))(v58, (unsigned int)v56[0]);
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                    }
                  }
                  if ( cchCount1 != cchCount2 )
                    goto LABEL_64;
                  v25 = lpString1;
                  if ( lpString1 != lpString2 )
                  {
                    do
                    {
                      v26 = *(LPCWCH)((char *)v25 + (char *)lpString2 - (char *)lpString1);
                      v27 = *v25 - v26;
                      if ( v27 )
                        break;
                      ++v25;
                    }
                    while ( v26 );
                    if ( v27 )
                      goto LABEL_64;
                  }
                }
LABEL_54:
                ++v21;
              }
            }
LABEL_31:
            ((void (__fastcall *)(struct IUri *))a2->lpVtbl->AddRef)(a2);
            v19 = a2;
            goto LABEL_32;
          }
          v62 = &CUString::`vftable';
          if ( v9 == 1 )
          {
            v9 = -2147418113;
            CUString::Set((CUString *)&v62, 0, Uri_PROPERTY_RAW_URI);
          }
          else
          {
            CUString::Set((CUString *)&v62, 0, Uri_PROPERTY_RAW_URI);
            if ( v9 >= 0 )
              goto LABEL_142;
          }
          ((void (__fastcall *)(struct IUri *))v7->lpVtbl->Release)(v7);
          goto LABEL_68;
        }
LABEL_24:
        ((void (__fastcall *)(struct IUri *))v7->lpVtbl->AddRef)(v7);
        v16 = (__int64)v7;
        goto LABEL_25;
      }
      v62 = &CUString::`vftable';
      if ( v9 == 1 )
      {
        v9 = -2147418113;
        CUString::Set((CUString *)&v62, 0, Uri_PROPERTY_RAW_URI);
        goto LABEL_68;
      }
      CUString::Set((CUString *)&v62, 0, Uri_PROPERTY_RAW_URI);
      if ( v9 >= 0 )
        goto LABEL_136;
LABEL_68:
      if ( v59 )
      {
        (*(void (__fastcall **)(CUriPrivWrapper *))(*(_QWORD *)v59 + 16LL))(v59);
        v59 = 0;
      }
      if ( v60 )
        (*(void (__fastcall **)(CUriPrivWrapper *))(*(_QWORD *)v60 + 16LL))(v60);
      return (unsigned int)v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ca30  mov     r11, rsp
0x18002ca33  mov     [r11+18h], r8
0x18002ca37  push    rbp
0x18002ca38  push    rsi
0x18002ca39  push    rdi
0x18002ca3a  push    r12
0x18002ca3c  push    r13
0x18002ca3e  lea     rbp, [r11-5Fh]
0x18002ca42  sub     rsp, 0E0h
0x18002ca49  xor     esi, esi
0x18002ca4b  mov     rdi, r8
0x18002ca4e  mov     [rbp+57h+arg_18], esi
0x18002ca51  mov     r12, rdx
0x18002ca54  mov     [rbp+57h+var_58], esi
0x18002ca57  mov     r13, rcx
0x18002ca5a  mov     [rbp+57h+var_50], esi
0x18002ca5d  mov     [rbp+57h+var_54], esi
0x18002ca60  mov     [rbp+57h+var_A0], rsi
0x18002ca64  mov     [rbp+57h+var_98], rsi
0x18002ca68  test    r8, r8
0x18002ca6b  jz      loc_18002D303
0x18002ca71  mov     [r8], esi
0x18002ca74  mov     eax, esi
0x18002ca76  test    rdx, rdx
0x18002ca79  jz      loc_18002CF59
0x18002ca7f  mov     [r11-30h], r14
0x18002ca83  cmp     [rcx+20h], eax
0x18002ca86  jge     loc_18002D30D
0x18002ca8c  mov     [r11-38h], r15
0x18002ca90  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18002ca94  jz      loc_18002D1A7
0x18002ca9a  cmp     r13, rdx
0x18002ca9d  jz      loc_18002D1DE
0x18002caa3  mov     r15, r13
0x18002caa6  mov     rax, [r15]
0x18002caa9  lea     rdx, [rbp+57h+arg_18]
0x18002caad  mov     rcx, r15
0x18002cab0  mov     [rbp+57h+var_90], r12
0x18002cab4  mov     rax, [rax+0C0h]
0x18002cabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cac0  mov     r14d, eax
0x18002cac3  test    eax, eax
0x18002cac5  js      loc_18002CF18
0x18002cacb  mov     rax, [r12]
0x18002cacf  lea     rdx, [rbp+57h+var_58]
0x18002cad3  mov     rcx, r12
0x18002cad6  mov     rax, [rax+0C0h]
0x18002cadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cae2  mov     r14d, eax
0x18002cae5  test    eax, eax
0x18002cae7  js      loc_18002CF18
0x18002caed  mov     eax, [rbp+57h+arg_18]
0x18002caf0  cmp     eax, [rbp+57h+var_58]
0x18002caf3  jnz     loc_18002D317
0x18002caf9  mov     [rsp+100h+arg_0], rbx
0x18002cb01  cmp     eax, 9
0x18002cb04  jz      short loc_18002CB82
0x18002cb06  movzx   eax, byte ptr [r13+148h]
0x18002cb0e  test    al, al
0x18002cb10  jz      short loc_18002CB7F
0x18002cb12  mov     rax, [r12]
0x18002cb16  lea     r8, [rbp+57h+var_B8]
0x18002cb1a  lea     rdx, IID_IUriPriv2
0x18002cb21  mov     qword ptr [rbp+57h+var_B8], rsi
0x18002cb25  mov     rcx, r12
0x18002cb28  mov     rax, [rax]
0x18002cb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb30  mov     [rbp+57h+cchCount1], eax
0x18002cb33  mov     ebx, eax
0x18002cb35  test    eax, eax
0x18002cb37  js      loc_18002D31E
0x18002cb3d  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18002cb41  test    ebx, ebx
0x18002cb43  js      short loc_18002CB7F
0x18002cb45  mov     [rbp+57h+cchCount1], esi
0x18002cb48  lea     rdx, [rbp+57h+cchCount1]
0x18002cb4c  mov     rax, [rcx]
0x18002cb4f  mov     rax, [rax+1A0h]
0x18002cb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb5b  test    eax, eax
0x18002cb5d  js      short loc_18002CB6F
0x18002cb5f  mov     eax, [rbp+57h+cchCount1]
0x18002cb62  cmp     [r13+144h], eax
0x18002cb69  jnz     loc_18002CFF6
0x18002cb6f  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18002cb73  mov     rax, [rcx]
0x18002cb76  mov     rax, [rax+10h]
0x18002cb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb7f  mov     eax, [rbp+57h+arg_18]
0x18002cb82  xor     r14d, r14d
0x18002cb85  mov     esi, 10h
0x18002cb8a  cmp     eax, 9
0x18002cb8d  jz      loc_18002D1EA
0x18002cb93  mov     rax, [r15]
0x18002cb96  lea     r8, [rbp+57h+var_B8]
0x18002cb9a  mov     rbx, r14
0x18002cb9d  mov     qword ptr [rbp+57h+var_B8], r14
0x18002cba1  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18002cba8  mov     [rbp+57h+cchCount2], r14d
0x18002cbac  mov     rcx, r15
0x18002cbaf  mov     [rbp+57h+var_A8], rbx
0x18002cbb3  mov     rax, [rax]
0x18002cbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbbb  lea     rdi, ??_7CUString@@6B@; const CUString::`vftable'
0x18002cbc2  test    eax, eax
0x18002cbc4  js      loc_18002D01E
0x18002cbca  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18002cbce  lea     rdx, [rbp+57h+cchCount2]
0x18002cbd2  mov     dil, 1
0x18002cbd5  mov     rax, [rcx]
0x18002cbd8  mov     rax, [rax+178h]
0x18002cbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbe4  test    eax, eax
0x18002cbe6  jnz     short loc_18002CBEF
0x18002cbe8  test    [rbp+57h+cchCount2], esi
0x18002cbeb  setnz   dil
0x18002cbef  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18002cbf3  mov     rax, [rcx]
0x18002cbf6  mov     rax, [rax+10h]
0x18002cbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbff  test    dil, dil
0x18002cc02  mov     qword ptr [rbp+57h+var_B8], r14
0x18002cc06  lea     rdi, ??_7CUString@@6B@; const CUString::`vftable'
0x18002cc0d  jnz     loc_18002D030
0x18002cc13  mov     rax, [r15]
0x18002cc16  mov     rcx, r15
0x18002cc19  mov     rax, [rax+8]
0x18002cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc22  mov     rbx, r15
0x18002cc25  cmp     rbx, r15
0x18002cc28  jnz     loc_18002D00D
0x18002cc2e  mov     rax, [r12]
0x18002cc32  lea     r8, [rbp+57h+var_B8]
0x18002cc36  mov     rbx, r14
0x18002cc39  mov     qword ptr [rbp+57h+var_B8], r14
0x18002cc3d  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18002cc44  mov     [rbp+57h+cchCount2], r14d
0x18002cc48  mov     rcx, r12
0x18002cc4b  mov     [rbp+57h+var_A8], rbx
0x18002cc4f  mov     rax, [rax]
0x18002cc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc57  test    eax, eax
0x18002cc59  js      loc_18002D0DC
0x18002cc5f  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18002cc63  lea     rdx, [rbp+57h+cchCount2]
0x18002cc67  mov     dil, 1
0x18002cc6a  mov     rax, [rcx]
0x18002cc6d  mov     rax, [rax+178h]
0x18002cc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc79  test    eax, eax
0x18002cc7b  jnz     short loc_18002CC84
0x18002cc7d  test    [rbp+57h+cchCount2], esi
0x18002cc80  setnz   dil
0x18002cc84  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18002cc88  mov     rax, [rcx]
0x18002cc8b  mov     rax, [rax+10h]
0x18002cc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc94  mov     qword ptr [rbp+57h+var_B8], r14
0x18002cc98  test    dil, dil
0x18002cc9b  jnz     loc_18002D463
0x18002cca1  mov     rax, [r12]
0x18002cca5  mov     rcx, r12
0x18002cca8  mov     rax, [rax+8]
0x18002ccac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccb1  mov     rbx, r12
0x18002ccb4  cmp     rbx, r12
0x18002ccb7  jnz     loc_18002D015
0x18002ccbd  mov     rbx, r12
0x18002ccc0  mov     rax, [r15]
0x18002ccc3  lea     rdx, [rbp+57h+var_50]
0x18002ccc7  mov     rcx, r15
0x18002ccca  mov     rax, [rax+0B8h]
0x18002ccd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccd6  mov     r14d, eax
0x18002ccd9  test    eax, eax
0x18002ccdb  js      loc_18002CF98
0x18002cce1  mov     rax, [rbx]
0x18002cce4  lea     rdx, [rbp+57h+var_54]
0x18002cce8  mov     rcx, rbx
0x18002cceb  mov     rax, [rax+0B8h]
0x18002ccf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccf7  mov     r14d, eax
0x18002ccfa  test    eax, eax
0x18002ccfc  js      loc_18002CF98
0x18002cd02  mov     eax, [rbp+57h+var_54]
0x18002cd05  xor     esi, esi
0x18002cd07  mov     rcx, r15
0x18002cd0a  cmp     [rbp+57h+var_50], eax
0x18002cd0d  jnz     loc_18002D4D0
0x18002cd13  mov     [rbp+57h+var_A0], rsi
0x18002cd17  lea     r8, [rbp+57h+var_A0]
0x18002cd1b  mov     rax, [r15]
0x18002cd1e  lea     rdx, IID_IUriPriv
0x18002cd25  mov     rax, [rax]
0x18002cd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd2d  mov     [rbp+57h+var_B8], eax
0x18002cd30  mov     r14d, eax
0x18002cd33  test    eax, eax
0x18002cd35  js      loc_18002D4E7
0x18002cd3b  mov     edi, 8007000Eh
0x18002cd40  test    r14d, r14d
0x18002cd43  js      loc_18002CF9F
0x18002cd49  mov     [rbp+57h+var_98], rsi
0x18002cd4d  lea     r8, [rbp+57h+var_98]
0x18002cd51  mov     rax, [rbx]
0x18002cd54  lea     rdx, IID_IUriPriv
0x18002cd5b  mov     rcx, rbx
0x18002cd5e  mov     rax, [rax]
0x18002cd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd66  mov     [rbp+57h+var_B8], eax
0x18002cd69  mov     r14d, eax
0x18002cd6c  test    eax, eax
0x18002cd6e  js      loc_18002D556
0x18002cd74  test    r14d, r14d
0x18002cd77  js      loc_18002CEEE
0x18002cd7d  mov     [rbp+57h+lpString1], rsi
0x18002cd81  mov     [rbp+57h+cchCount1], esi
0x18002cd84  mov     [rbp+57h+lpString2], rsi
0x18002cd88  mov     [rbp+57h+cchCount2], esi
0x18002cd8b  lea     rcx, qword_180175910
0x18002cd92  cmp     esi, 7
0x18002cd95  jnb     loc_18002CFB3
0x18002cd9b  mov     eax, esi
0x18002cd9d  lea     r9, [rbp+57h+cchCount1]
0x18002cda1  mov     edx, [rcx+rax*4]
0x18002cda4  lea     rdi, [rcx+rax*4]
0x18002cda8  mov     rcx, [rbp+57h+var_A0]
0x18002cdac  lea     r8, [rbp+57h+lpString1]
0x18002cdb0  mov     rax, [rcx]
0x18002cdb3  mov     rax, [rax+0E0h]
0x18002cdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdbf  mov     ebx, eax
0x18002cdc1  mov     r14d, eax
0x18002cdc4  test    eax, eax
0x18002cdc6  js      loc_18002CF98
0x18002cdcc  mov     rcx, [rbp+57h+var_98]
0x18002cdd0  lea     r9, [rbp+57h+cchCount2]
0x18002cdd4  lea     r8, [rbp+57h+lpString2]
0x18002cdd8  mov     rdx, [rcx]
0x18002cddb  mov     rax, [rdx+0E0h]
0x18002cde2  mov     edx, [rdi]
0x18002cde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cde9  mov     r14d, eax
0x18002cdec  test    eax, eax
0x18002cdee  js      loc_18002CF98
0x18002cdf4  xor     r14d, r14d
0x18002cdf7  cmp     ebx, eax
0x18002cdf9  jnz     loc_18002CEE6
0x18002cdff  test    ebx, ebx
0x18002ce01  jnz     short loc_18002CE4C
0x18002ce03  cmp     [rbp+57h+arg_18], 9
0x18002ce07  jz      loc_18002D1AF
0x18002ce0d  cmp     dword ptr [rdi], 8
0x18002ce10  jz      short loc_18002CE53
0x18002ce12  mov     eax, [rbp+57h+cchCount2]
0x18002ce15  cmp     [rbp+57h+cchCount1], eax
0x18002ce18  jnz     loc_18002CEE6
0x18002ce1e  mov     rcx, [rbp+57h+lpString1]
0x18002ce22  mov     r8, [rbp+57h+lpString2]
0x18002ce26  cmp     rcx, r8
0x18002ce29  jz      short loc_18002CE4C
0x18002ce2b  sub     r8, rcx
0x18002ce2e  xchg    ax, ax
0x18002ce30  movzx   edx, word ptr [rcx]
0x18002ce33  movzx   eax, word ptr [rcx+r8]
0x18002ce38  sub     edx, eax
0x18002ce3a  jnz     short loc_18002CE44
0x18002ce3c  add     rcx, 2
0x18002ce40  test    eax, eax
0x18002ce42  jnz     short loc_18002CE30
0x18002ce44  test    edx, edx
0x18002ce46  jnz     loc_18002CEE6
0x18002ce4c  inc     esi
0x18002ce4e  jmp     loc_18002CD8B
0x18002ce53  movzx   eax, byte ptr [r13+148h]
0x18002ce5b  test    al, al
0x18002ce5d  jz      loc_18002CFD3
0x18002ce63  mov     rax, [r12]
0x18002ce67  lea     r8, [rbp+57h+var_A8]
0x18002ce6b  xor     edi, edi
0x18002ce6d  lea     rdx, IID_IUriPriv2
0x18002ce74  mov     rcx, r12
0x18002ce77  mov     [rbp+57h+var_A8], rdi
0x18002ce7b  mov     rax, [rax]
0x18002ce7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce83  mov     [rbp+57h+var_B8], eax
0x18002ce86  mov     ebx, eax
0x18002ce88  test    eax, eax
0x18002ce8a  js      loc_18002D5C0
0x18002ce90  mov     rcx, [rbp+57h+var_A8]
0x18002ce94  test    ebx, ebx
0x18002ce96  js      loc_18002CE12
0x18002ce9c  mov     [rbp+57h+var_B8], edi
0x18002ce9f  lea     rdx, [rbp+57h+var_B8]
0x18002cea3  mov     rax, [rcx]
0x18002cea6  mov     rax, [rax+1A0h]
0x18002cead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ceb2  test    eax, eax
0x18002ceb4  js      loc_18002CF68
0x18002ceba  mov     rcx, [rbp+57h+var_A8]
  ... truncated ...
```
