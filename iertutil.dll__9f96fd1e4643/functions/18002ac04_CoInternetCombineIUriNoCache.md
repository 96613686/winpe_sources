# CoInternetCombineIUriNoCache

- ea: `0x18002ac04`
- end: `0x18002b5a0`
- name: `CoInternetCombineIUriNoCache`
- size: `2460`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18002bc70`

## callees

- `0x180002b5c`
- `0x180015f88`
- `0x1800173a0`
- `0x180026834`
- `0x18002a420`
- `0x18002aab4`
- `0x18002ac04`
- `0x18002b5b0`
- `0x18002b680`
- `0x18004afcc`
- `0x18004bb5c`
- `0x18004d090`
- `0x180052d28`
- `0x1800540d0`
- `0x180057afc`
- `0x180057b6c`
- `0x180083c10`
- `0x180083cd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002b1c8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002b4c8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002b1c8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002b4c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b4fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b4fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b27f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aeb6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aec0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b133`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aeb6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aec0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b133`
- `OLEAUT32!__imp_SysStringLen` at `0x18002afa8`
- `OLEAUT32!__imp_SysStringLen` at `0x18002afe0`
- `OLEAUT32!__imp_SysStringLen` at `0x18002afa8`
- `OLEAUT32!__imp_SysStringLen` at `0x18002afe0`

## pseudocode

```c
__int64 __fastcall CoInternetCombineIUriNoCache(
        struct IUri *a1,
        struct IUri *a2,
        unsigned int a3,
        __int64 a4,
        char a5,
        unsigned __int16 *a6,
        int a7,
        char a8)
{
  unsigned __int16 *v8; // r15
  struct IUri **v9; // r14
  struct IUri *v11; // rsi
  unsigned int v12; // r8d
  int v13; // r9d
  unsigned int v14; // ecx
  int IUriPriv2; // ebx
  char v16; // r12
  int v17; // edi
  char v18; // cl
  struct IUri v20; // rax
  int v21; // eax
  int v22; // edi
  UINT v23; // r13d
  unsigned int v24; // eax
  UINT v25; // esi
  struct IUri v26; // rax
  struct IUri *v27; // rdi
  struct IUri *v28; // rcx
  struct IUriVtbl *lpVtbl; // rax
  int v30; // eax
  BSTR v31; // r14
  BSTR v32; // r15
  unsigned int v33; // r13d
  int v34; // eax
  unsigned __int16 *v35; // rsi
  int v36; // eax
  unsigned __int16 *v37; // rcx
  unsigned __int16 *v38; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  struct IUri *v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+64h] [rbp-9Ch] BYREF
  int v43; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v44; // [rsp+6Ch] [rbp-94h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  BSTR v46; // [rsp+78h] [rbp-88h] BYREF
  int v47; // [rsp+80h] [rbp-80h] BYREF
  BSTR pbstr; // [rsp+88h] [rbp-78h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v50; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v51; // [rsp+A0h] [rbp-60h]
  struct IUri *v52; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-50h]
  struct IUri *v54; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v55[2088]; // [rsp+C0h] [rbp-40h] BYREF

  v8 = a6;
  v9 = (struct IUri **)a4;
  v49 = a4;
  v44 = a3;
  v54 = a1;
  v50 = a6;
  v11 = a1;
  v43 = 0;
  v47 = 0;
  v42 = 0;
  v39 = 0;
  bstrString = 0;
  pbstr = 0;
  v40 = 0;
  v53 = 0;
  if ( !a4 )
  {
    IUriPriv2 = -2147467261;
    goto LABEL_35;
  }
  if ( !a1 || !a2 )
  {
    IUriPriv2 = -2147024809;
    goto LABEL_35;
  }
  v12 = HelperAddUriDefaultFlags(0x3002B80u, 5u);
  if ( (v13 & 0x2000000) != 0 )
    v12 = v12 & 0xFFFFFF3F | 0x80;
  v14 = v12 | 0x20;
  if ( (v13 & 0x10000) == 0 )
    v14 = v12;
  if ( (v13 & 0x8000000) != 0 )
    v14 = v14 & 0xFFFFFEEF | 0x10;
  IUriPriv2 = NormalizeUriCreateFlags(v14, &v39);
  if ( IUriPriv2 < 0 )
    goto LABEL_30;
  if ( (a5 & 2) != 0 )
  {
    v51 = v39 | 0x2000000;
    v8 = v50;
  }
  else
  {
    v51 = v39;
  }
  IUriPriv2 = GetIUriPriv2(a2);
  if ( IUriPriv2 < 0 )
    goto LABEL_30;
  IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, int *))v11->lpVtbl->GetScheme)(v11, &v42);
  if ( IUriPriv2 < 0 )
    goto LABEL_30;
  if ( v42 == 2 || v42 == 11 )
  {
    v41 = 0;
    IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, int *))v40->lpVtbl[1].GetQuery)(v40, &v41);
    if ( IUriPriv2 < 0 )
      goto LABEL_30;
    if ( (v41 & 0x20) != 0 )
    {
      v39 = 0;
      IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, unsigned int *))v40->lpVtbl[1].GetHostType)(v40, &v39);
      if ( IUriPriv2 < 0 )
        goto LABEL_30;
      if ( (v39 & 0x2000000) != 0 )
      {
        ((void (__fastcall *)(struct IUri *))v40->lpVtbl->Release)(v40);
        v26.lpVtbl = a2->lpVtbl;
        v40 = 0;
        v46 = 0;
        IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, BSTR *))v26.lpVtbl->GetRawUri)(a2, &v46);
        if ( IUriPriv2 >= 0 )
        {
          v52 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          IUriPriv2 = CreateUriPriv(v46, 0, 0, 0, (__int64)&v52);
          if ( IUriPriv2 >= 0 )
          {
            v27 = v52;
            IUriPriv2 = GetIUriPriv2(v52);
            if ( IUriPriv2 >= 0 )
            {
              if ( v27 )
                ((void (__fastcall *)(struct IUri *))v27->lpVtbl->Release)(v27);
              if ( v46 )
                SysFreeString(v46);
              goto LABEL_17;
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
        goto LABEL_30;
      }
    }
  }
LABEL_17:
  IUriPriv2 = GetIUriPriv2(v11);
  if ( IUriPriv2 < 0 )
    goto LABEL_30;
  IUriPriv2 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v53 + 408LL))(v53, 6145, &v43);
  if ( IUriPriv2 < 0 )
    goto LABEL_30;
  IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, __int64, int *))v40->lpVtbl[1].GetPort)(v40, 6145, &v47);
  if ( IUriPriv2 < 0 )
    goto LABEL_30;
  v16 = 1;
  if ( (v43 & 0x1000) == 0 || v42 == 1 || v42 == 2 || v42 == 9 )
    goto LABEL_21;
  if ( v42 == 10 )
  {
    if ( (unsigned int)IsStreamEnabled() )
      goto LABEL_21;
  }
  else if ( v42 == 11 || v42 == 14 )
  {
    goto LABEL_21;
  }
  if ( (v47 & 0x801) != 0 && (v43 & 0x801) != 0 )
  {
    if ( dword_18029ACD0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18029ACD0);
      if ( dword_18029ACD0 == -1 )
      {
        byte_18029ACD4 = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_SHIM_MSHELP_COMBINE) == 0;
        Init_thread_footer(&dword_18029ACD0);
      }
    }
    v20.lpVtbl = v11->lpVtbl;
    if ( (v43 & 1) != 0 )
      v21 = ((__int64 (__fastcall *)(struct IUri *, BSTR *))v20.lpVtbl->GetAbsoluteUri)(v11, &bstrString);
    else
      v21 = ((__int64 (__fastcall *)(struct IUri *, BSTR *))v20.lpVtbl->GetRawUri)(v11, &bstrString);
    IUriPriv2 = v21;
    if ( v21 < 0 )
      goto LABEL_30;
    v22 = 0;
    v23 = SysStringLen(bstrString);
    if ( v23 )
    {
      v24 = IsKnownProtocol(bstrString);
      if ( (!v24 || v24 == 7) && (v8 || !a7) )
      {
        v22 = 1;
        lpVtbl = v40->lpVtbl;
        v30 = (v47 & 1) != 0
            ? ((__int64 (__fastcall *)(struct IUri *, BSTR *))lpVtbl->GetAbsoluteUri)(v40, &pbstr)
            : ((unsigned __int64 (__fastcall *)(struct IUri *, BSTR *))lpVtbl->GetRawUri)(v40, &pbstr);
        IUriPriv2 = v30;
        if ( v30 < 0 )
          goto LABEL_30;
      }
    }
    v25 = SysStringLen(pbstr);
    if ( !v22 )
      goto LABEL_55;
    if ( v25 < 3 )
    {
      if ( !byte_18029ACD4 || (unsigned int)StrCmpNIIW(bstrString, L"ms-help:", 8u) )
        goto LABEL_79;
      if ( !v25 || !(unsigned int)StrCmpIIW(L".", pbstr) )
      {
LABEL_131:
        v22 = 0;
        goto LABEL_79;
      }
      v36 = StrCmpIIW(L"./", pbstr);
    }
    else
    {
      if ( (a5 & 1) == 0 )
      {
        if ( !StrCmpNICW(bstrString, L"mk:", 3) )
          v22 = 0;
        goto LABEL_79;
      }
      v41 = 0;
      v39 = 0;
      IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, int *))v40->lpVtbl[1].GetQuery)(v40, &v41);
      if ( IUriPriv2 < 0 )
        goto LABEL_30;
      if ( (v41 & 0x20) != 0
        || ((int (__fastcall *)(struct IUri *, unsigned int *))v40->lpVtbl->GetScheme)(v40, &v39) < 0 )
      {
LABEL_79:
        if ( !v22 )
          goto LABEL_55;
        v31 = (BSTR)&word_1801758E4;
        v39 = 0;
        v32 = (BSTR)&word_1801758E4;
        if ( v23 )
          v32 = bstrString;
        v55[0] = 0;
        if ( v25 )
          v31 = pbstr;
        if ( !v50 )
        {
          IUriPriv2 = -2147024882;
          goto LABEL_30;
        }
        v33 = v44;
        v38 = v55;
        v34 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR, BSTR, _QWORD))(*(_QWORD *)v50 + 32LL))(
                v50,
                v32,
                v31,
                v44);
        v35 = 0;
        IUriPriv2 = v34;
        if ( (a8 & 1) != 0 && v34 == -2147467261 )
        {
          v35 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v39);
          if ( !v35 )
          {
            IUriPriv2 = -2147024882;
            goto LABEL_89;
          }
          v38 = v35;
          IUriPriv2 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR, BSTR, _QWORD))(*(_QWORD *)v50 + 32LL))(
                        v50,
                        v32,
                        v31,
                        v33);
        }
        if ( !IUriPriv2 )
        {
          HelperAddUriDefaultFlags(0x3002B80u, 0x35u);
          v9 = (struct IUri **)v49;
          v37 = v35;
          if ( !v35 )
            v37 = v55;
          IUriPriv2 = CreateUriPriv(v37, 0, 0, 0, v49);
          if ( IUriPriv2 < 0 )
            goto LABEL_30;
          goto LABEL_90;
        }
        if ( IUriPriv2 == -2146697199 )
        {
          v22 = 0;
          IUriPriv2 = 0;
        }
LABEL_89:
        v9 = (struct IUri **)v49;
LABEL_90:
        CoTaskMemFree(v35);
LABEL_55:
        if ( IUriPriv2 < 0 || v22 )
          goto LABEL_30;
        v11 = v54;
        goto LABEL_21;
      }
      if ( v39 != 1 && v39 != 2 && v39 != 9 )
      {
        if ( v39 == 10 )
        {
          if ( !(unsigned int)IsStreamEnabled() )
            goto LABEL_79;
        }
        else if ( v39 != 11 && v39 != 14 )
        {
          goto LABEL_79;
        }
      }
      v36 = StrCmpNICW(bstrString, L"mhtml:", 6);
    }
    if ( v36 )
      goto LABEL_79;
    goto LABEL_131;
  }
LABEL_21:
  v39 = 0;
  v44 = 0;
  IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, unsigned int *))v40->lpVtbl[1].GetQuery)(v40, &v39);
  if ( IUriPriv2 >= 0 )
  {
    IUriPriv2 = ((__int64 (__fastcall *)(struct IUri *, unsigned int *))v40->lpVtbl[1].GetSchemeName)(v40, &v44);
    if ( IUriPriv2 >= 0 )
    {
      v41 = 0;
      v17 = 0;
      v50 = 0;
      LODWORD(v46) = 0;
      if ( ((int (__fastcall *)(struct IUri *, int *))v40->lpVtbl->GetScheme)(v40, &v41) >= 0 && v41 == 9 )
      {
        v18 = v39;
        if ( (v39 & 4) == 0 )
        {
LABEL_26:
          if ( (v18 & 0xC) == 0 || v17 || (v44 & 0x30) == 0 )
            v16 = 0;
          if ( (v18 & 0x20) != 0 || v16 )
          {
            IUriPriv2 = UrlCombineUris(v11, v40, v9, v51, (unsigned __int64)v38);
          }
          else
          {
            v28 = v40;
            *v9 = v40;
            ((void (__fastcall *)(struct IUri *))v28->lpVtbl->AddRef)(v28);
          }
          goto LABEL_30;
        }
        if ( ((int (__fastcall *)(struct IUri *, unsigned __int16 **, BSTR *))v40->lpVtbl[1].GetDisplayUri)(
               v40,
               &v50,
               &v46) >= 0
          && v50 )
        {
          v17 = IsRootedPath(v50);
        }
      }
      v18 = v39;
      goto LABEL_26;
    }
  }
LABEL_30:
  if ( v40 )
    ((void (__fastcall *)(struct IUri *))v40->lpVtbl->Release)(v40);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( IUriPriv2 >= 0 && !*(_QWORD *)v49 )
    IUriPriv2 = -2147467259;
LABEL_35:
  SysFreeString(bstrString);
  SysFreeString(pbstr);
  return (unsigned int)IUriPriv2;
}

```

## disassembly

```asm
0x18002ac04  push    rbp
0x18002ac06  push    rbx
0x18002ac07  push    rsi
0x18002ac08  push    rdi
0x18002ac09  push    r12
0x18002ac0b  push    r13
0x18002ac0d  push    r14
0x18002ac0f  push    r15
0x18002ac11  lea     rbp, [rsp-1028h]
0x18002ac19  mov     eax, 1128h
0x18002ac1e  call    _alloca_probe
0x18002ac23  sub     rsp, rax
0x18002ac26  mov     rax, cs:__security_cookie
0x18002ac2d  xor     rax, rsp
0x18002ac30  mov     [rbp+1060h+var_50], rax
0x18002ac37  mov     r15, [rbp+1060h+arg_28]
0x18002ac3e  xor     r13d, r13d
0x18002ac41  mov     r14, r9
0x18002ac44  mov     [rbp+1060h+var_10D0], r9
0x18002ac48  mov     [rsp+1160h+var_10F4], r8d
0x18002ac4d  mov     r9d, r8d
0x18002ac50  mov     [rbp+1060h+var_10A8], rcx
0x18002ac54  mov     rdi, rdx
0x18002ac57  mov     [rbp+1060h+var_10C8], r15
0x18002ac5b  mov     rsi, rcx
0x18002ac5e  mov     [rsp+1160h+var_10F8], r13d
0x18002ac63  mov     [rbp+1060h+var_10E0], r13d
0x18002ac67  mov     [rsp+1160h+var_10FC], r13d
0x18002ac6c  mov     [rsp+1160h+var_1110], r13d
0x18002ac71  mov     [rsp+1160h+bstrString], r13
0x18002ac76  mov     [rbp+1060h+pbstr], r13
0x18002ac7a  mov     [rsp+1160h+var_1108], r13
0x18002ac7f  mov     [rbp+1060h+var_10B0], r13
0x18002ac83  test    r14, r14
0x18002ac86  jz      loc_18002B3C4
0x18002ac8c  test    rcx, rcx
0x18002ac8f  jz      loc_18002B334
0x18002ac95  test    rdx, rdx
0x18002ac98  jz      loc_18002B334
0x18002ac9e  lea     edx, [r13+5]; unsigned int
0x18002aca2  mov     ecx, 3002B80h; unsigned int
0x18002aca7  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18002acac  mov     r12d, 2000000h
0x18002acb2  mov     r8d, eax
0x18002acb5  test    r12d, r9d
0x18002acb8  jz      short loc_18002ACC3
0x18002acba  and     r8d, 0FFFFFFBFh
0x18002acbe  bts     r8d, 7
0x18002acc3  mov     ecx, r8d
0x18002acc6  or      ecx, 20h
0x18002acc9  bt      r9d, 10h
0x18002acce  cmovnb  ecx, r8d; unsigned int
0x18002acd2  bt      r9d, 1Bh
0x18002acd7  jb      loc_18002B160
0x18002acdd  lea     rdx, [rsp+1160h+var_1110]; unsigned int *
0x18002ace2  call    ?NormalizeUriCreateFlags@@YAJKPEAK@Z; NormalizeUriCreateFlags(ulong,ulong *)
0x18002ace7  mov     ebx, eax
0x18002ace9  test    eax, eax
0x18002aceb  js      loc_18002AE82
0x18002acf1  test    [rbp+1060h+arg_20], 2
0x18002acf8  jnz     loc_18002B3CE
0x18002acfe  mov     eax, [rsp+1160h+var_1110]
0x18002ad02  mov     [rbp+1060h+var_10C0], eax
0x18002ad05  lea     rdx, [rsp+1160h+var_1108]
0x18002ad0a  mov     rcx, rdi; struct IUri *
0x18002ad0d  call    GetIUriPriv2
0x18002ad12  mov     ebx, eax
0x18002ad14  test    eax, eax
0x18002ad16  js      loc_18002AE82
0x18002ad1c  mov     rax, [rsi]
0x18002ad1f  lea     rdx, [rsp+1160h+var_10FC]
0x18002ad24  mov     rcx, rsi
0x18002ad27  mov     rax, [rax+0C0h]
0x18002ad2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad33  mov     ebx, eax
0x18002ad35  test    eax, eax
0x18002ad37  js      loc_18002AE82
0x18002ad3d  cmp     [rsp+1160h+var_10FC], 2
0x18002ad42  jz      loc_18002B00C
0x18002ad48  cmp     [rsp+1160h+var_10FC], 0Bh
0x18002ad4d  jz      loc_18002B00C
0x18002ad53  lea     rdx, [rbp+1060h+var_10B0]
0x18002ad57  mov     rcx, rsi; struct IUri *
0x18002ad5a  call    GetIUriPriv2
0x18002ad5f  mov     ebx, eax
0x18002ad61  test    eax, eax
0x18002ad63  js      loc_18002AE82
0x18002ad69  mov     rcx, [rbp+1060h+var_10B0]
0x18002ad6d  lea     r8, [rsp+1160h+var_10F8]
0x18002ad72  mov     edi, 1801h
0x18002ad77  mov     edx, edi
0x18002ad79  mov     rax, [rcx]
0x18002ad7c  mov     rax, [rax+198h]
0x18002ad83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad88  mov     ebx, eax
0x18002ad8a  test    eax, eax
0x18002ad8c  js      loc_18002AE82
0x18002ad92  mov     rcx, [rsp+1160h+var_1108]
0x18002ad97  lea     r8, [rbp+1060h+var_10E0]
0x18002ad9b  mov     edx, edi
0x18002ad9d  mov     rax, [rcx]
0x18002ada0  mov     rax, [rax+198h]
0x18002ada7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adac  mov     ebx, eax
0x18002adae  test    eax, eax
0x18002adb0  js      loc_18002AE82
0x18002adb6  test    [rsp+1160h+var_10F8], 1000h
0x18002adbe  mov     r12d, 1
0x18002adc4  jnz     loc_18002AEFC
0x18002adca  mov     rcx, [rsp+1160h+var_1108]
0x18002adcf  lea     rdx, [rsp+1160h+var_1110]
0x18002add4  mov     [rsp+1160h+var_1110], r13d
0x18002add9  mov     [rsp+1160h+var_10F4], r13d
0x18002adde  mov     rax, [rcx]
0x18002ade1  mov     rax, [rax+168h]
0x18002ade8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aded  mov     ebx, eax
0x18002adef  test    eax, eax
0x18002adf1  js      loc_18002AE82
0x18002adf7  mov     rcx, [rsp+1160h+var_1108]
0x18002adfc  lea     rdx, [rsp+1160h+var_10F4]
0x18002ae01  mov     rax, [rcx]
0x18002ae04  mov     rax, [rax+178h]
0x18002ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae10  mov     ebx, eax
0x18002ae12  test    eax, eax
0x18002ae14  js      short loc_18002AE82
0x18002ae16  mov     rcx, [rsp+1160h+var_1108]
0x18002ae1b  lea     rdx, [rsp+1160h+var_1100]
0x18002ae20  mov     [rsp+1160h+var_1100], r13d
0x18002ae25  mov     edi, r13d
0x18002ae28  mov     [rbp+1060h+var_10C8], r13
0x18002ae2c  mov     dword ptr [rsp+1160h+var_10E8], r13d
0x18002ae31  mov     rax, [rcx]
0x18002ae34  mov     rax, [rax+0C0h]
0x18002ae3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae40  test    eax, eax
0x18002ae42  js      short loc_18002AE4F
0x18002ae44  cmp     [rsp+1160h+var_1100], 9
0x18002ae49  jz      loc_18002B2E9
0x18002ae4f  mov     ecx, [rsp+1160h+var_1110]
0x18002ae53  mov     eax, ecx
0x18002ae55  and     eax, 20h
0x18002ae58  test    cl, 0Ch
0x18002ae5b  jnz     loc_18002B33E
0x18002ae61  mov     r12b, r13b
0x18002ae64  test    eax, eax
0x18002ae66  jz      loc_18002B13E
0x18002ae6c  mov     r9d, [rbp+1060h+var_10C0]; unsigned int
0x18002ae70  mov     r8, r14; struct IUri **
0x18002ae73  mov     rdx, [rsp+1160h+var_1108]; struct IUri *
0x18002ae78  mov     rcx, rsi; struct IUri *
0x18002ae7b  call    ?UrlCombineUris@@YAJPEAUIUri@@0PEAPEAU1@K_K@Z; UrlCombineUris(IUri *,IUri *,IUri * *,ulong,unsigned __int64)
0x18002ae80  mov     ebx, eax
0x18002ae82  mov     rcx, [rsp+1160h+var_1108]
0x18002ae87  test    rcx, rcx
0x18002ae8a  jz      short loc_18002AE98
0x18002ae8c  mov     rax, [rcx]
0x18002ae8f  mov     rax, [rax+10h]
0x18002ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae98  mov     rcx, [rbp+1060h+var_10B0]
0x18002ae9c  test    rcx, rcx
0x18002ae9f  jz      short loc_18002AEAD
0x18002aea1  mov     rax, [rcx]
0x18002aea4  mov     rax, [rax+10h]
0x18002aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aead  test    ebx, ebx
0x18002aeaf  jns     short loc_18002AEEB
0x18002aeb1  mov     rcx, [rsp+1160h+bstrString]; bstrString
0x18002aeb6  call    cs:__imp_SysFreeString
0x18002aebc  mov     rcx, [rbp+1060h+pbstr]; bstrString
0x18002aec0  call    cs:__imp_SysFreeString
0x18002aec6  mov     eax, ebx
0x18002aec8  mov     rcx, [rbp+1060h+var_50]
0x18002aecf  xor     rcx, rsp; StackCookie
0x18002aed2  call    __security_check_cookie
0x18002aed7  add     rsp, 1128h
0x18002aede  pop     r15
0x18002aee0  pop     r14
0x18002aee2  pop     r13
0x18002aee4  pop     r12
0x18002aee6  pop     rdi
0x18002aee7  pop     rsi
0x18002aee8  pop     rbx
0x18002aee9  pop     rbp
0x18002aeea  retn
0x18002aeeb  mov     rax, [rbp+1060h+var_10D0]
0x18002aeef  mov     ecx, 80004005h
0x18002aef4  cmp     [rax], r13
0x18002aef7  cmovz   ebx, ecx
0x18002aefa  jmp     short loc_18002AEB1
0x18002aefc  mov     eax, [rsp+1160h+var_10FC]
0x18002af00  sub     eax, r12d
0x18002af03  jz      loc_18002ADCA
0x18002af09  sub     eax, r12d
0x18002af0c  jz      loc_18002ADCA
0x18002af12  sub     eax, 7
0x18002af15  jz      loc_18002ADCA
0x18002af1b  sub     eax, r12d
0x18002af1e  jz      loc_18002B2D7
0x18002af24  sub     eax, r12d
0x18002af27  jz      loc_18002ADCA
0x18002af2d  cmp     eax, 3
0x18002af30  jz      loc_18002ADCA
0x18002af36  mov     eax, 801h
0x18002af3b  test    [rbp+1060h+var_10E0], eax
0x18002af3e  setnz   cl
0x18002af41  test    [rsp+1160h+var_10F8], eax
0x18002af45  setnz   al
0x18002af48  test    al, cl
0x18002af4a  jz      loc_18002ADCA
0x18002af50  mov     ecx, cs:_tls_index
0x18002af56  mov     rax, gs:58h
0x18002af5f  mov     edx, 4
0x18002af64  mov     rax, [rax+rcx*8]
0x18002af68  mov     ecx, [rdx+rax]
0x18002af6b  cmp     cs:dword_18029ACD0, ecx
0x18002af71  jg      loc_18002B298
0x18002af77  lea     rdx, [rsp+1160h+bstrString]
0x18002af7c  mov     rax, [rsi]
0x18002af7f  mov     rcx, rsi
0x18002af82  test    byte ptr [rsp+1160h+var_10F8], r12b
0x18002af87  jz      loc_18002B3FB
0x18002af8d  mov     rax, [rax+38h]
0x18002af91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af96  mov     ebx, eax
0x18002af98  test    eax, eax
0x18002af9a  js      loc_18002AE82
0x18002afa0  mov     rcx, [rsp+1160h+bstrString]; pbstr
0x18002afa5  mov     edi, r13d
0x18002afa8  call    cs:__imp_SysStringLen
0x18002afae  mov     r13d, eax
0x18002afb1  test    eax, eax
0x18002afb3  jz      short loc_18002AFDC
0x18002afb5  mov     rcx, [rsp+1160h+bstrString]; pszStr1
0x18002afba  call    ?IsKnownProtocol@@YAKPEBG@Z; IsKnownProtocol(ushort const *)
0x18002afbf  test    eax, eax
0x18002afc1  jnz     loc_18002B28A
0x18002afc7  test    r15, r15
0x18002afca  jnz     loc_18002B16C
0x18002afd0  cmp     [rbp+1060h+arg_30], edi
0x18002afd6  jz      loc_18002B16C
0x18002afdc  mov     rcx, [rbp+1060h+pbstr]; pbstr
0x18002afe0  call    cs:__imp_SysStringLen
0x18002afe6  mov     esi, eax
0x18002afe8  test    edi, edi
0x18002afea  jnz     loc_18002B1A0
0x18002aff0  xor     r13d, r13d
0x18002aff3  test    ebx, ebx
0x18002aff5  js      loc_18002AE82
0x18002affb  test    edi, edi
0x18002affd  jnz     loc_18002AE82
0x18002b003  mov     rsi, [rbp+1060h+var_10A8]
0x18002b007  jmp     loc_18002ADCA
0x18002b00c  mov     rcx, [rsp+1160h+var_1108]
0x18002b011  lea     rdx, [rsp+1160h+var_1100]
0x18002b016  mov     [rsp+1160h+var_1100], r13d
0x18002b01b  mov     rax, [rcx]
0x18002b01e  mov     rax, [rax+168h]
0x18002b025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b02a  mov     ebx, eax
0x18002b02c  test    eax, eax
0x18002b02e  js      loc_18002AE82
0x18002b034  test    byte ptr [rsp+1160h+var_1100], 20h
0x18002b039  jz      loc_18002AD53
0x18002b03f  mov     rcx, [rsp+1160h+var_1108]
0x18002b044  lea     rdx, [rsp+1160h+var_1110]
0x18002b049  mov     [rsp+1160h+var_1110], r13d
0x18002b04e  mov     rax, [rcx]
0x18002b051  mov     rax, [rax+190h]
0x18002b058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b05d  mov     ebx, eax
0x18002b05f  test    eax, eax
0x18002b061  js      loc_18002AE82
0x18002b067  test    [rsp+1160h+var_1110], r12d
0x18002b06c  jz      loc_18002AD53
0x18002b072  mov     rcx, [rsp+1160h+var_1108]
0x18002b077  mov     rax, [rcx]
0x18002b07a  mov     rax, [rax+10h]
0x18002b07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b083  mov     rax, [rdi]
0x18002b086  lea     rdx, [rsp+1160h+var_10E8]
0x18002b08b  mov     rcx, rdi
0x18002b08e  mov     [rsp+1160h+var_1108], r13
0x18002b093  mov     [rsp+1160h+var_10E8], r13
0x18002b098  mov     rax, [rax+90h]
0x18002b09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0a4  mov     ebx, eax
0x18002b0a6  test    eax, eax
0x18002b0a8  js      loc_18002B3EC
0x18002b0ae  lea     rcx, [rbp+1060h+var_10B8]
0x18002b0b2  mov     [rbp+1060h+var_10B8], r13
0x18002b0b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b0bb  mov     r8d, [rsp+1160h+var_1110]
0x18002b0c0  lea     rax, [rbp+1060h+var_10B8]
0x18002b0c4  mov     rcx, [rsp+1160h+var_10E8]; unsigned __int16 *
0x18002b0c9  bts     r8d, 1Ah
0x18002b0ce  mov     [rsp+1160h+var_1128], rax; __int64
0x18002b0d3  xor     r9d, r9d
0x18002b0d6  mov     qword ptr [rsp+1160h+var_1130], r13; int
  ... truncated ...
```
