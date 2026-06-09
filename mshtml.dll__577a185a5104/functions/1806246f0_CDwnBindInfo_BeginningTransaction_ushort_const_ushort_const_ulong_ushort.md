# CDwnBindInfo::BeginningTransaction(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x1806246f0`
- end: `0x18062512f`
- name: `?BeginningTransaction@CDwnBindInfo@@UEAAJPEBG0KPEAPEAG@Z`
- size: `2623`
- prototype: `__int64 __fastcall(CDwnBindInfo *this, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005ce98`
- `0x18005e648`
- `0x18005e684`
- `0x1800ea428`
- `0x1806246f0`
- `0x180625138`
- `0x1806251bc`
- `0x180626404`
- `0x180680cc8`
- `0x180730a68`
- `0x180778414`
- `0x181091074`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180624c70`
- `msvcrt!memcpy_s` at `0x180624c70`
- `KERNEL32!LeaveCriticalSection` at `0x1806247dc`
- `KERNEL32!LeaveCriticalSection` at `0x1806247dc`
- `KERNEL32!EnterCriticalSection` at `0x1806247a4`
- `KERNEL32!EnterCriticalSection` at `0x1806247a4`
- `iertutil!CreateIUriBuilder` at `0x180624ce3`
- `iertutil!CreateIUriBuilder` at `0x180624ce3`
- `iertutil!CreateUri` at `0x1806249ae`
- `iertutil!CreateUri` at `0x180624bbc`
- `iertutil!CreateUri` at `0x1806249ae`
- `iertutil!CreateUri` at `0x180624bbc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180624b14`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180624eec`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180624b14`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180624eec`
- `OLEAUT32!__imp_SysFreeString` at `0x1806248b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1806248c9`
- `OLEAUT32!__imp_SysFreeString` at `0x180624da2`
- `OLEAUT32!__imp_SysFreeString` at `0x1806248b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1806248c9`
- `OLEAUT32!__imp_SysFreeString` at `0x180624da2`
- `OLEAUT32!__imp_SysStringLen` at `0x180624c06`
- `OLEAUT32!__imp_SysStringLen` at `0x1806250e7`
- `OLEAUT32!__imp_SysStringLen` at `0x180624c06`
- `OLEAUT32!__imp_SysStringLen` at `0x1806250e7`

## string_xrefs

- `0x180624a34`: `User-Agent: `

## pseudocode

```c
__int64 __fastcall CDwnBindInfo::BeginningTransaction(
        CDwnBindInfo *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  IUri *v7; // r9
  unsigned int v8; // esi
  CDwnBindInfo *v9; // rdx
  const unsigned __int16 **v10; // rdi
  __int64 v11; // r12
  int *v12; // r14
  __int64 v13; // rdx
  const unsigned __int16 **v14; // r8
  const WCHAR *v15; // rbx
  LPCWSTR v16; // r15
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rcx
  const unsigned __int16 *v19; // rcx
  unsigned int *v20; // rcx
  __int64 v21; // rdx
  const WCHAR *v22; // rcx
  __int64 v23; // rax
  __int64 v25; // rax
  unsigned int v26; // eax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // r9d
  const unsigned __int16 **v31; // r12
  int v32; // eax
  SIZE_T v33; // rbx
  _WORD *v34; // rax
  _WORD *v35; // r15
  char *v36; // r13
  unsigned int v37; // eax
  unsigned int v38; // r12d
  HRESULT v39; // eax
  int v40; // edi
  OLECHAR *v41; // rcx
  LPCWSTR *v42; // rdi
  int *v43; // r14
  rsize_t v44; // rbx
  char v45; // al
  HRESULT v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  int v49; // eax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rbx
  unsigned __int16 *v54; // rax
  unsigned __int16 *v55; // r10
  unsigned int v56; // eax
  __int64 v57; // rdx
  unsigned int v58; // ecx
  __int64 v59; // rax
  int Header; // eax
  CMarkup *v61; // rcx
  int RefererUrl; // eax
  OLECHAR *v63; // rcx
  LPCWSTR pwzURI; // [rsp+30h] [rbp-D0h] BYREF
  IUri *pIUri; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v67; // [rsp+48h] [rbp-B8h] BYREF
  IUriBuilder *ppIUriBuilder; // [rsp+50h] [rbp-B0h] BYREF
  IUri *ppURI; // [rsp+58h] [rbp-A8h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v71; // [rsp+68h] [rbp-98h]
  int v72; // [rsp+70h] [rbp-90h] BYREF
  UINT v73; // [rsp+74h] [rbp-8Ch]
  int v74; // [rsp+78h] [rbp-88h] BYREF
  char v75; // [rsp+7Ch] [rbp-84h] BYREF
  const unsigned __int16 *v76; // [rsp+D0h] [rbp-30h] BYREF
  void *v77; // [rsp+D8h] [rbp-28h]
  LPCWSTR v78; // [rsp+E0h] [rbp-20h] BYREF
  char v79; // [rsp+E8h] [rbp-18h] BYREF

  v71 = a5;
  memset_0(&v76, 0, 0xB0u);
  LOWORD(v7) = 0;
  ppURI = 0;
  v8 = 0;
  bstrString = 0;
  pbstr = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v8 = CreateUri(a2, 0x3002B84u, 0, &ppURI);
      if ( v8 )
        goto LABEL_15;
      v26 = CDwnBindInfo::SetUri((CDwnBindInfo *)((char *)this - 48), ppURI);
      LOWORD(v7) = 0;
      v8 = v26;
      if ( v26 )
        goto LABEL_15;
    }
  }
  v9 = (CDwnBindInfo *)((char *)this - 48);
  if ( (*((_BYTE *)this + 132) & 1) != 0 )
  {
    v52 = *((_QWORD *)this + 4);
    if ( v52 )
    {
      if ( *(_QWORD *)(v52 + 744) )
      {
        v53 = *(unsigned int *)(v52 + 740);
        v54 = (unsigned __int16 *)CoTaskMemAlloc(2 * v53);
        if ( v54 )
        {
          AnsiToWideTrivial(*(const char **)(*((_QWORD *)this + 4) + 744LL), v54, (unsigned int)v53, v53 - 1);
          *a5 = v55;
          goto LABEL_15;
        }
        goto LABEL_76;
      }
    }
  }
  *a5 = 0;
  v10 = &v76;
  v11 = -1;
  v12 = &v72;
  if ( !*((_QWORD *)this + 4) )
  {
LABEL_37:
    v29 = *((_QWORD *)this + 5);
    if ( v29 )
    {
      v51 = *(const unsigned __int16 **)(v29 + 56);
      if ( v51 )
      {
        if ( v10 - &v76 + 1 >= 22 )
          goto LABEL_111;
        *v12 = 14;
        *v10 = L"Content-Type: ";
        if ( v10 + 1 - &v76 + 1 >= 22 )
          goto LABEL_111;
        v10[1] = v51;
        do
          ++v11;
        while ( v51[v11] != (_WORD)v7 );
        v12[1] = v11;
        if ( v10 + 2 - &v76 + 1 >= 22 )
          goto LABEL_111;
        v10[2] = L"\r\n";
        v10 += 3;
        v12[2] = 2;
        v12 += 3;
      }
    }
    if ( !CDwnBindInfo::IsOriginCheckRequired(v9)
      || (v61 = *(CMarkup **)(*((_QWORD *)this + 4) + 112LL)) == 0
      || (RefererUrl = CMarkup::GetRefererUrl(v61, &pbstr), v30 = 0, RefererUrl < 0) )
    {
LABEL_39:
      if ( v10 <= &v76 )
        goto LABEL_15;
      v31 = v10;
      v32 = v30;
      do
      {
        --v12;
        --v10;
        v32 += *v12;
      }
      while ( v10 > &v76 );
      v33 = (unsigned int)(v32 + 1);
      v34 = CoTaskMemAlloc(v33 * 2);
      v35 = v34;
      if ( v34 )
      {
        v36 = (char *)&v34[v33];
        *v71 = v34;
        while ( v10 < v31 )
        {
          v44 = 2LL * (unsigned int)*v12;
          memcpy_s(v35, v36 - (char *)v35, *v10, v44);
          v35 = (_WORD *)((char *)v35 + v44);
          ++v12;
          ++v10;
        }
        *v35 = 0;
        goto LABEL_15;
      }
LABEL_76:
      v8 = -2147024882;
      goto LABEL_15;
    }
    if ( v10 - &v76 + 1 < 22 )
    {
      *v12 = 8;
      *v10 = L"Origin: ";
      if ( v10 + 1 - &v76 + 1 < 22 )
      {
        v63 = pbstr;
        v10[1] = pbstr;
        v12[1] = SysStringLen(v63);
        if ( v10 + 2 - &v76 + 1 < 22 )
        {
          v10[2] = L"\r\n";
          v10 += 3;
          v12[2] = 2;
          v12 += 3;
          v30 = 0;
          goto LABEL_39;
        }
      }
    }
LABEL_111:
    v8 = -2147467259;
    goto LABEL_15;
  }
  pwzURI = 0;
  EnterCriticalSection(&g_csDwnDoc);
  CStr::Set(
    &pwzURI,
    *(const unsigned __int16 **)(*((_QWORD *)this + 4) + 16 * (((*((_DWORD *)this + 33) & 1) == 0) | 0x28LL)));
  LeaveCriticalSection(&g_csDwnDoc);
  v15 = pwzURI;
  v7 = 0;
  v16 = pwzURI;
  if ( pwzURI )
  {
    LODWORD(pIUri) = *(_DWORD *)((-(__int64)((*((_DWORD *)this + 33) & 1) != 0) & 0xFFFFFFFFFFFFFFD8uLL)
                               + *((_QWORD *)this + 4)
                               + 688);
    v37 = (*(__int64 (__fastcall **)(char *, __int64, const unsigned __int16 **, _QWORD))(*((_QWORD *)this - 6) + 16LL))(
            (char *)this - 48,
            v13,
            v14,
            0);
    v7 = 0;
    v38 = v37;
    if ( !v37 )
    {
      if ( ppURI )
      {
        v67 = 0;
        v56 = ((__int64 (__fastcall *)(IUri *, unsigned int *))ppURI->lpVtbl->GetScheme)(ppURI, &v67);
        v7 = 0;
        v8 = v56;
        if ( !v56 )
          v38 = v67;
      }
    }
    if ( (*((_BYTE *)this + 132) & 1) != 0
      || (unsigned __int8)CDwnDoc::IsSendingReferrerAllowedHelper(
                            *(unsigned int *)(*((_QWORD *)this + 4) + 664LL),
                            (unsigned int)pIUri,
                            v38,
                            0) )
    {
      pIUri = v7;
      ppIUriBuilder = (IUriBuilder *)v7;
      bstrString = (BSTR)v7;
      v76 = L"Referer: ";
      v72 = 9;
      v39 = CreateUri(v15, 0x3022B05u, 0, &pIUri);
      v7 = 0;
      v40 = v39;
      if ( v39 < 0 )
        goto LABEL_47;
      v46 = CreateIUriBuilder(pIUri, 0, 0, &ppIUriBuilder);
      v7 = 0;
      v40 = v46;
      if ( v46 < 0 )
        goto LABEL_47;
      v47 = ((__int64 (__fastcall *)(IUriBuilder *, __int64, const unsigned __int16 **, _QWORD))ppIUriBuilder->lpVtbl->RemoveProperties)(
              ppIUriBuilder,
              8224,
              v14,
              0);
      v7 = 0;
      v40 = v47;
      if ( v47 < 0 )
        goto LABEL_47;
      ((void (__fastcall *)(IUri *, __int64, const unsigned __int16 **, _QWORD))pIUri->lpVtbl->Release)(
        pIUri,
        v48,
        v14,
        0);
      pIUri = 0;
      v49 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, IUri **))ppIUriBuilder->lpVtbl->CreateUriSimple)(
              ppIUriBuilder,
              0,
              0,
              &pIUri);
      v7 = 0;
      v40 = v49;
      if ( v49 < 0
        || (v50 = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, __int64))pIUri->lpVtbl->GetPropertyBSTR)(
                    pIUri,
                    0,
                    &bstrString,
                    2),
            v7 = 0,
            v40 = v50,
            v50 < 0) )
      {
LABEL_47:
        v41 = bstrString;
      }
      else
      {
        v41 = bstrString;
        if ( v50 == 1 || !bstrString )
        {
          SysFreeString(bstrString);
          v7 = 0;
          v40 = -2147467259;
          v41 = 0;
          bstrString = 0;
        }
      }
      if ( pIUri )
      {
        ((void (__fastcall *)(IUri *))pIUri->lpVtbl->Release)(pIUri);
        v41 = bstrString;
        v7 = 0;
      }
      if ( ppIUriBuilder )
      {
        ((void (__fastcall *)(IUriBuilder *))ppIUriBuilder->lpVtbl->Release)(ppIUriBuilder);
        v41 = bstrString;
        v7 = 0;
      }
      if ( v40 < 0 )
      {
        v11 = -1;
        v57 = -1;
        do
          ++v57;
        while ( v15[v57] );
        v58 = 0;
        while ( v58 < (unsigned int)v57 )
        {
          ++v58;
          if ( *v16 == 58 )
          {
            while ( 1 )
            {
              ++v16;
              if ( v58 >= (unsigned int)v57 || *v16 != 47 )
                break;
              ++v58;
            }
            break;
          }
          ++v16;
        }
        v77 = (void *)v15;
        v42 = &v78;
        v73 = v58;
        v43 = &v74;
        if ( v58 < (unsigned int)v57 )
        {
          while ( v58 < (unsigned int)v57 )
          {
            if ( *v16 == 64 )
            {
              v78 = v16 + 1;
              v74 = v57 - v58 - 1;
              v42 = (LPCWSTR *)&v79;
              v43 = (int *)&v75;
              goto LABEL_54;
            }
            if ( *v16 == 47 )
              break;
            ++v58;
            ++v16;
          }
          v73 = v57;
        }
      }
      else
      {
        v77 = v41;
        v42 = &v78;
        v11 = -1;
        v73 = SysStringLen(v41);
        v7 = 0;
        v43 = &v74;
      }
LABEL_54:
      if ( v42 - &v76 + 1 >= 22 )
        goto LABEL_103;
      *v43 = 2;
      *v42 = L"\r\n";
      v10 = v42 + 1;
      v12 = v43 + 1;
    }
    else
    {
      v11 = -1;
    }
  }
  v17 = *((_QWORD *)this + 4);
  v18 = *(const unsigned __int16 **)(v17 + 696);
  if ( v18 )
  {
    if ( v10 - &v76 + 1 >= 22 )
      goto LABEL_103;
    *v12 = 17;
    *v10 = L"Accept-Language: ";
    v14 = &v76;
    if ( v10 + 1 - &v76 + 1 >= 22 )
      goto LABEL_103;
    v10[1] = v18;
    v25 = -1;
    do
      ++v25;
    while ( v18[v25] != (_WORD)v7 );
    v12[1] = v25;
    if ( v10 + 2 - &v76 + 1 >= 22 )
      goto LABEL_103;
    v10[2] = L"\r\n";
    v10 += 3;
    v12[2] = 2;
    v12 += 3;
  }
  v19 = (const unsigned __int16 *)*((_QWORD *)this + 15);
  if ( v19 )
  {
    v14 = &v76;
    if ( v10 - &v76 + 1 >= 22 )
      goto LABEL_103;
    *v10 = v19;
    v59 = -1;
    do
      ++v59;
    while ( v19[v59] != (_WORD)v7 );
    *v12 = v59;
    if ( v10 + 1 - &v76 + 1 >= 22 )
      goto LABEL_103;
    v10[1] = L"\r\n";
    v10 += 2;
    v12[1] = 2;
    v12 += 2;
  }
  v20 = *(unsigned int **)(v17 + 104);
  if ( v20 )
  {
    if ( (*((_BYTE *)this + 132) & 1) == 0 )
    {
      v45 = IsWebPlatformHostBehaviorSupported<38>(v20[1260], v20[1261], v20[1263], v20[1262]);
      v7 = 0;
      if ( v45 )
        goto LABEL_27;
    }
  }
  v21 = *((_QWORD *)this + 4);
  v22 = *(const WCHAR **)(v21 + 752);
  if ( !v22 )
    goto LABEL_27;
  if ( v10 - &v76 + 1 >= 22 )
    goto LABEL_103;
  *v10 = v22;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] != (_WORD)v7 );
  *v12 = v23;
  v14 = &v76;
  if ( v10 + 1 - &v76 + 1 < 22 )
  {
    v10[1] = L"\r\n";
    v10 += 2;
    v12[1] = 2;
    v12 += 2;
    if ( *(IUri **)(v21 + 704) != v7 )
    {
      Header = FindHeader(v22, (const unsigned __int16 *)v21);
      LOWORD(v7) = 0;
      if ( Header )
        goto LABEL_34;
    }
LABEL_27:
    v27 = *(const unsigned __int16 **)(*((_QWORD *)this + 4) + 704LL);
    if ( !v27 )
    {
LABEL_34:
      if ( v15 )
      {
        MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)(v15 - 2), v14);
        LOWORD(v7) = 0;
      }
      v9 = (CDwnBindInfo *)((char *)this - 48);
      goto LABEL_37;
    }
    if ( v10 - &v76 + 1 < 22 )
    {
      *v12 = 12;
      *v10 = L"User-Agent: ";
      if ( v10 + 1 - &v76 + 1 < 22 )
      {
        v10[1] = v27;
        v28 = -1;
        do
          ++v28;
        while ( v27[v28] != (_WORD)v7 );
        v12[1] = v28;
        if ( v10 + 2 - &v76 + 1 >= 22 )
          goto LABEL_13;
        v10[2] = L"\r\n";
        v10 += 3;
        v12[2] = 2;
        v12 += 3;
        goto LABEL_34;
      }
    }
LABEL_103:
    v8 = -2147467259;
    CStr::_Free((CStr *)&pwzURI);
    goto LABEL_15;
  }
LABEL_13:
  v8 = -2147467259;
  if ( v15 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)(v15 - 2), v14);
LABEL_15:
  ReleaseInterface((struct IUnknown *)ppURI);
  SysFreeString(bstrString);
  SysFreeString(pbstr);
  return v8;
}

```

## disassembly

```asm
0x1806246f0  mov     [rsp-8+arg_10], rbx
0x1806246f5  push    rbp
0x1806246f6  push    rsi
0x1806246f7  push    rdi
0x1806246f8  push    r12
0x1806246fa  push    r13
0x1806246fc  push    r14
0x1806246fe  push    r15
0x180624700  lea     rbp, [rsp-90h]
0x180624708  sub     rsp, 190h
0x18062470f  mov     rax, cs:__security_cookie
0x180624716  xor     rax, rsp
0x180624719  mov     [rbp+0C0h+var_40], rax
0x180624720  mov     r15, [rbp+0C0h+arg_20]
0x180624727  mov     rbx, rdx
0x18062472a  mov     r13, rcx
0x18062472d  mov     [rsp+1C0h+var_158], r15
0x180624732  xor     edx, edx; Val
0x180624734  lea     rcx, [rbp+0C0h+var_F0]; void *
0x180624738  mov     r8d, 0B0h; Size
0x18062473e  call    memset_0
0x180624743  xor     r9d, r9d
0x180624746  mov     [rsp+1C0h+ppURI], r9
0x18062474b  mov     esi, r9d
0x18062474e  mov     [rsp+1C0h+bstrString], r9
0x180624753  mov     [rsp+1C0h+pbstr], r9
0x180624758  test    rbx, rbx
0x18062475b  jnz     loc_180624994
0x180624761  lea     rdx, [r13-30h]
0x180624765  test    byte ptr [rdx+0B4h], 1
0x18062476c  jnz     loc_180624EC8
0x180624772  mov     [r15], r9
0x180624775  lea     rdi, [rbp+0C0h+var_F0]
0x180624779  or      r12, 0FFFFFFFFFFFFFFFFh
0x18062477d  lea     r14, [rsp+1C0h+var_150]
0x180624782  lea     r15, asc_18143B398; "\r\n"
0x180624789  mov     ebx, 80004005h
0x18062478e  cmp     [r13+20h], r9
0x180624792  jz      loc_180624AC7
0x180624798  lea     rcx, ?g_csDwnDoc@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18062479f  mov     [rsp+1C0h+pwzURI], r9
0x1806247a4  call    cs:__imp_EnterCriticalSection
0x1806247ab  nop     dword ptr [rax+rax+00h]
0x1806247b0  mov     eax, [r13+84h]
0x1806247b7  lea     rcx, [rsp+1C0h+pwzURI]; this
0x1806247bc  mov     rdx, [r13+20h]
0x1806247c0  not     eax
0x1806247c2  and     eax, 1
0x1806247c5  or      rax, 28h
0x1806247c9  add     rax, rax
0x1806247cc  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x1806247d0  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x1806247d5  lea     rcx, ?g_csDwnDoc@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1806247dc  call    cs:__imp_LeaveCriticalSection
0x1806247e3  nop     dword ptr [rax+rax+00h]
0x1806247e8  mov     rbx, [rsp+1C0h+pwzURI]
0x1806247ed  xor     r9d, r9d
0x1806247f0  mov     r15, rbx
0x1806247f3  test    rbx, rbx
0x1806247f6  jnz     loc_180624B3D
0x1806247fc  lea     r15, asc_18143B398; "\r\n"
0x180624803  mov     rdx, [r13+20h]
0x180624807  mov     rcx, [rdx+2B8h]
0x18062480e  test    rcx, rcx
0x180624811  jnz     loc_180624902
0x180624817  mov     rcx, [r13+78h]
0x18062481b  test    rcx, rcx
0x18062481e  jnz     loc_180625001
0x180624824  mov     rcx, [rdx+68h]
0x180624828  test    rcx, rcx
0x18062482b  jnz     loc_180624C97
0x180624831  mov     rdx, [r13+20h]; unsigned __int16 *
0x180624835  mov     rcx, [rdx+2F0h]; pszFirst
0x18062483c  test    rcx, rcx
0x18062483f  jz      loc_180624A05
0x180624845  lea     r8, [rbp+0C0h+var_F0]
0x180624849  mov     rax, rdi
0x18062484c  sub     rax, r8
0x18062484f  sar     rax, 3
0x180624853  inc     rax
0x180624856  cmp     rax, 16h
0x18062485a  jge     loc_180624FED
0x180624860  mov     [rdi], rcx
0x180624863  mov     rax, r12
0x180624866  inc     rax
0x180624869  cmp     [rcx+rax*2], r9w
0x18062486e  jnz     short loc_180624866
0x180624870  mov     [r14], eax
0x180624873  lea     r8, [rbp+0C0h+var_F0]; void *
0x180624877  lea     rax, [rdi+8]
0x18062487b  sub     rax, r8
0x18062487e  sar     rax, 3
0x180624882  inc     rax
0x180624885  cmp     rax, 16h
0x180624889  jl      loc_1806249E4
0x18062488f  mov     esi, 80004005h
0x180624894  test    rbx, rbx
0x180624897  jz      short loc_1806248A9
0x180624899  mov     rcx, cs:g_hProcessHeap; this
0x1806248a0  lea     rdx, [rbx-4]; void *
0x1806248a4  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1806248a9  mov     rcx, [rsp+1C0h+ppURI]; struct IUnknown *
0x1806248ae  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1806248b3  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x1806248b8  call    cs:__imp_SysFreeString
0x1806248bf  nop     dword ptr [rax+rax+00h]
0x1806248c4  mov     rcx, [rsp+1C0h+pbstr]; bstrString
0x1806248c9  call    cs:__imp_SysFreeString
0x1806248d0  nop     dword ptr [rax+rax+00h]
0x1806248d5  mov     eax, esi
0x1806248d7  mov     rcx, [rbp+0C0h+var_40]
0x1806248de  xor     rcx, rsp; StackCookie
0x1806248e1  call    __security_check_cookie
0x1806248e6  mov     rbx, [rsp+1C0h+arg_10]
0x1806248ee  add     rsp, 190h
0x1806248f5  pop     r15
0x1806248f7  pop     r14
0x1806248f9  pop     r13
0x1806248fb  pop     r12
0x1806248fd  pop     rdi
0x1806248fe  pop     rsi
0x1806248ff  pop     rbp
0x180624900  retn
0x180624902  lea     r8, [rbp+0C0h+var_F0]
0x180624906  mov     rax, rdi
0x180624909  sub     rax, r8
0x18062490c  sar     rax, 3
0x180624910  inc     rax
0x180624913  cmp     rax, 16h
0x180624917  jge     loc_180624FED
0x18062491d  lea     rax, aAcceptLanguage_0; "Accept-Language: "
0x180624924  mov     dword ptr [r14], 11h
0x18062492b  mov     [rdi], rax
0x18062492e  lea     r8, [rbp+0C0h+var_F0]
0x180624932  lea     rax, [rdi+8]
0x180624936  sub     rax, r8
0x180624939  sar     rax, 3
0x18062493d  inc     rax
0x180624940  cmp     rax, 16h
0x180624944  jge     loc_180624FED
0x18062494a  mov     [rdi+8], rcx
0x18062494e  mov     rax, r12
0x180624951  inc     rax
0x180624954  cmp     [rcx+rax*2], r9w
0x180624959  jnz     short loc_180624951
0x18062495b  mov     [r14+4], eax
0x18062495f  lea     rcx, [rbp+0C0h+var_F0]
0x180624963  lea     rax, [rdi+10h]
0x180624967  sub     rax, rcx
0x18062496a  sar     rax, 3
0x18062496e  inc     rax
0x180624971  cmp     rax, 16h
0x180624975  jge     loc_180624FED
0x18062497b  mov     [rdi+10h], r15
0x18062497f  add     rdi, 18h
0x180624983  mov     dword ptr [r14+8], 2
0x18062498b  add     r14, 0Ch
0x18062498f  jmp     loc_180624817
0x180624994  cmp     r9w, [rbx]
0x180624998  jz      loc_180624761
0x18062499e  lea     r9, [rsp+1C0h+ppURI]; ppURI
0x1806249a3  xor     r8d, r8d; dwReserved
0x1806249a6  mov     edx, 3002B84h; dwFlags
0x1806249ab  mov     rcx, rbx; pwzURI
0x1806249ae  call    cs:__imp_CreateUri
0x1806249b5  nop     dword ptr [rax+rax+00h]
0x1806249ba  mov     esi, eax
0x1806249bc  test    eax, eax
0x1806249be  jnz     loc_1806248A9
0x1806249c4  mov     rdx, [rsp+1C0h+ppURI]; struct IUri *
0x1806249c9  lea     rcx, [r13-30h]; this
0x1806249cd  call    ?SetUri@CDwnBindInfo@@QEAAJPEAUIUri@@@Z; CDwnBindInfo::SetUri(IUri *)
0x1806249d2  xor     r9d, r9d
0x1806249d5  mov     esi, eax
0x1806249d7  test    eax, eax
0x1806249d9  jz      loc_180624761
0x1806249df  jmp     loc_1806248A9
0x1806249e4  mov     [rdi+8], r15
0x1806249e8  add     rdi, 10h
0x1806249ec  mov     dword ptr [r14+4], 2
0x1806249f4  add     r14, 8
0x1806249f8  cmp     [rdx+2C0h], r9
0x1806249ff  jnz     loc_18062505C
0x180624a05  mov     rax, [r13+20h]
0x180624a09  mov     rcx, [rax+2C0h]
0x180624a10  test    rcx, rcx
0x180624a13  jz      loc_180624AA6
0x180624a19  lea     rdx, [rbp+0C0h+var_F0]
0x180624a1d  mov     rax, rdi
0x180624a20  sub     rax, rdx
0x180624a23  sar     rax, 3
0x180624a27  inc     rax
0x180624a2a  cmp     rax, 16h
0x180624a2e  jge     loc_180624FED
0x180624a34  lea     rax, aUserAgent_0; "User-Agent: "
0x180624a3b  mov     dword ptr [r14], 0Ch
0x180624a42  mov     [rdi], rax
0x180624a45  lea     rdx, [rbp+0C0h+var_F0]
0x180624a49  lea     rax, [rdi+8]
0x180624a4d  sub     rax, rdx
0x180624a50  sar     rax, 3
0x180624a54  inc     rax
0x180624a57  cmp     rax, 16h
0x180624a5b  jge     loc_180624FED
0x180624a61  mov     [rdi+8], rcx
0x180624a65  mov     rax, r12
0x180624a68  inc     rax
0x180624a6b  cmp     [rcx+rax*2], r9w
0x180624a70  jnz     short loc_180624A68
0x180624a72  mov     [r14+4], eax
0x180624a76  lea     rcx, [rbp+0C0h+var_F0]
0x180624a7a  lea     rax, [rdi+10h]
0x180624a7e  sub     rax, rcx
0x180624a81  sar     rax, 3
0x180624a85  inc     rax
0x180624a88  cmp     rax, 16h
0x180624a8c  jge     loc_18062488F
0x180624a92  mov     [rdi+10h], r15
0x180624a96  add     rdi, 18h
0x180624a9a  mov     dword ptr [r14+8], 2
0x180624aa2  add     r14, 0Ch
0x180624aa6  test    rbx, rbx
0x180624aa9  jz      short loc_180624ABE
0x180624aab  mov     rcx, cs:g_hProcessHeap; this
0x180624ab2  lea     rdx, [rbx-4]; void *
0x180624ab6  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180624abb  xor     r9d, r9d
0x180624abe  mov     ebx, 80004005h
0x180624ac3  lea     rdx, [r13-30h]
0x180624ac7  mov     rcx, [r13+28h]
0x180624acb  test    rcx, rcx
0x180624ace  jnz     loc_180624DC3
0x180624ad4  mov     rcx, rdx; this
0x180624ad7  call    ?IsOriginCheckRequired@CDwnBindInfo@@QEAA_NXZ; CDwnBindInfo::IsOriginCheckRequired(void)
0x180624adc  test    al, al
0x180624ade  jnz     loc_180625078
0x180624ae4  lea     rax, [rbp+0C0h+var_F0]
0x180624ae8  cmp     rdi, rax
0x180624aeb  jbe     loc_1806248A9
0x180624af1  mov     r12, rdi
0x180624af4  mov     eax, r9d
0x180624af7  sub     r14, 4
0x180624afb  lea     rcx, [rbp+0C0h+var_F0]
0x180624aff  sub     rdi, 8
0x180624b03  add     eax, [r14]
0x180624b06  cmp     rdi, rcx
0x180624b09  ja      short loc_180624AF7
0x180624b0b  inc     eax
0x180624b0d  lea     rbx, [rax+rax]
0x180624b11  mov     rcx, rbx; cb
0x180624b14  call    cs:__imp_CoTaskMemAlloc
0x180624b1b  nop     dword ptr [rax+rax+00h]
0x180624b20  mov     r15, rax
0x180624b23  test    rax, rax
0x180624b26  jz      loc_180624E97
0x180624b2c  lea     r13, [rbx+rax]
0x180624b30  mov     rax, [rsp+1C0h+var_158]
0x180624b35  mov     [rax], r15
0x180624b38  jmp     loc_180624C87
0x180624b3d  mov     eax, [r13+84h]
0x180624b44  and     al, 1
0x180624b46  neg     al
0x180624b48  mov     rax, [r13+20h]
0x180624b4c  sbb     rcx, rcx
0x180624b4f  and     rcx, 0FFFFFFFFFFFFFFD8h
0x180624b53  mov     eax, [rcx+rax+2B0h]
0x180624b5a  lea     rcx, [r13-30h]
0x180624b5e  mov     dword ptr [rsp+1C0h+pIUri], eax
0x180624b62  mov     rax, [rcx]
0x180624b65  mov     rax, [rax+10h]
0x180624b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180624b6e  xor     r9d, r9d
0x180624b71  mov     r12d, eax
0x180624b74  test    eax, eax
0x180624b76  jz      loc_180624F22
0x180624b7c  test    byte ptr [r13+84h], 1
0x180624b84  jz      loc_180624EA1
0x180624b8a  lea     rax, aReferer; "Referer: "
0x180624b91  mov     [rsp+1C0h+pIUri], r9
0x180624b96  mov     [rsp+1C0h+ppIUriBuilder], r9
0x180624b9b  xor     r8d, r8d; dwReserved
0x180624b9e  mov     [rsp+1C0h+bstrString], r9
0x180624ba3  mov     edx, 3022B05h; dwFlags
0x180624ba8  lea     r9, [rsp+1C0h+pIUri]; ppURI
0x180624bad  mov     [rbp+0C0h+var_F0], rax
0x180624bb1  mov     rcx, rbx; pwzURI
0x180624bb4  mov     [rsp+1C0h+var_150], 9
0x180624bbc  call    cs:__imp_CreateUri
0x180624bc3  nop     dword ptr [rax+rax+00h]
0x180624bc8  xor     r9d, r9d
0x180624bcb  mov     edi, eax
0x180624bcd  test    eax, eax
0x180624bcf  jns     loc_180624CD4
0x180624bd5  mov     rcx, [rsp+1C0h+bstrString]; pbstr
0x180624bda  mov     rdx, [rsp+1C0h+pIUri]
0x180624bdf  test    rdx, rdx
0x180624be2  jnz     loc_180624E5F
0x180624be8  mov     rdx, [rsp+1C0h+ppIUriBuilder]
0x180624bed  test    rdx, rdx
0x180624bf0  jnz     loc_180624E7B
  ... truncated ...
```
