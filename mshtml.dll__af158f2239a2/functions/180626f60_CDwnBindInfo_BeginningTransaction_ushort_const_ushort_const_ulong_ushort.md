# CDwnBindInfo::BeginningTransaction(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180626f60`
- end: `0x180627950`
- name: `?BeginningTransaction@CDwnBindInfo@@UEAAJPEBG0KPEAPEAG@Z`
- size: `2544`
- prototype: `__int64 __fastcall(CDwnBindInfo *this, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x1801bf344`
- `0x1801c0acc`
- `0x1801c0b08`
- `0x18043c328`
- `0x180626f60`
- `0x180627958`
- `0x1806279dc`
- `0x180628bc4`
- `0x1806809d4`
- `0x180729168`
- `0x180771070`
- `0x181060d14`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1806274af`
- `msvcrt!memcpy_s` at `0x1806274af`
- `KERNEL32!LeaveCriticalSection` at `0x180627046`
- `KERNEL32!LeaveCriticalSection` at `0x180627046`
- `KERNEL32!EnterCriticalSection` at `0x180627014`
- `KERNEL32!EnterCriticalSection` at `0x180627014`
- `iertutil!CreateIUriBuilder` at `0x18062751c`
- `iertutil!CreateIUriBuilder` at `0x18062751c`
- `iertutil!CreateUri` at `0x180627205`
- `iertutil!CreateUri` at `0x180627407`
- `iertutil!CreateUri` at `0x180627205`
- `iertutil!CreateUri` at `0x180627407`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180627365`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180627719`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180627365`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180627719`
- `OLEAUT32!__imp_SysFreeString` at `0x18062711c`
- `OLEAUT32!__imp_SysFreeString` at `0x180627127`
- `OLEAUT32!__imp_SysFreeString` at `0x1806275d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18062711c`
- `OLEAUT32!__imp_SysFreeString` at `0x180627127`
- `OLEAUT32!__imp_SysFreeString` at `0x1806275d5`
- `OLEAUT32!__imp_SysStringLen` at `0x18062744b`
- `OLEAUT32!__imp_SysStringLen` at `0x18062790e`
- `OLEAUT32!__imp_SysStringLen` at `0x18062744b`
- `OLEAUT32!__imp_SysStringLen` at `0x18062790e`

## string_xrefs

- `0x180627285`: `User-Agent: `

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
    (CStr *)&pwzURI,
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
0x180626f60  mov     [rsp-8+arg_10], rbx
0x180626f65  push    rbp
0x180626f66  push    rsi
0x180626f67  push    rdi
0x180626f68  push    r12
0x180626f6a  push    r13
0x180626f6c  push    r14
0x180626f6e  push    r15
0x180626f70  lea     rbp, [rsp-90h]
0x180626f78  sub     rsp, 190h
0x180626f7f  mov     rax, cs:__security_cookie
0x180626f86  xor     rax, rsp
0x180626f89  mov     [rbp+0C0h+var_40], rax
0x180626f90  mov     r15, [rbp+0C0h+arg_20]
0x180626f97  mov     rbx, rdx
0x180626f9a  mov     r13, rcx
0x180626f9d  mov     [rsp+1C0h+var_158], r15
0x180626fa2  xor     edx, edx; Val
0x180626fa4  lea     rcx, [rbp+0C0h+var_F0]; void *
0x180626fa8  mov     r8d, 0B0h; Size
0x180626fae  call    memset_0
0x180626fb3  xor     r9d, r9d
0x180626fb6  mov     [rsp+1C0h+ppURI], r9
0x180626fbb  mov     esi, r9d
0x180626fbe  mov     [rsp+1C0h+bstrString], r9
0x180626fc3  mov     [rsp+1C0h+pbstr], r9
0x180626fc8  test    rbx, rbx
0x180626fcb  jnz     loc_1806271EB
0x180626fd1  lea     rdx, [r13-30h]
0x180626fd5  test    byte ptr [rdx+0B4h], 1
0x180626fdc  jnz     loc_1806276F5
0x180626fe2  mov     [r15], r9
0x180626fe5  lea     rdi, [rbp+0C0h+var_F0]
0x180626fe9  or      r12, 0FFFFFFFFFFFFFFFFh
0x180626fed  lea     r14, [rsp+1C0h+var_150]
0x180626ff2  lea     r15, asc_1814088E4; "\r\n"
0x180626ff9  mov     ebx, 80004005h
0x180626ffe  cmp     [r13+20h], r9
0x180627002  jz      loc_180627318
0x180627008  lea     rcx, ?g_csDwnDoc@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18062700f  mov     [rsp+1C0h+pwzURI], r9
0x180627014  call    cs:__imp_EnterCriticalSection
0x18062701a  mov     eax, [r13+84h]
0x180627021  lea     rcx, [rsp+1C0h+pwzURI]; this
0x180627026  mov     rdx, [r13+20h]
0x18062702a  not     eax
0x18062702c  and     eax, 1
0x18062702f  or      rax, 28h
0x180627033  add     rax, rax
0x180627036  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x18062703a  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x18062703f  lea     rcx, ?g_csDwnDoc@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x180627046  call    cs:__imp_LeaveCriticalSection
0x18062704c  mov     rbx, [rsp+1C0h+pwzURI]
0x180627051  xor     r9d, r9d
0x180627054  mov     r15, rbx
0x180627057  test    rbx, rbx
0x18062705a  jnz     loc_180627388
0x180627060  lea     r15, asc_1814088E4; "\r\n"
0x180627067  mov     rdx, [r13+20h]
0x18062706b  mov     rcx, [rdx+2B8h]
0x180627072  test    rcx, rcx
0x180627075  jnz     loc_180627159
0x18062707b  mov     rcx, [r13+78h]
0x18062707f  test    rcx, rcx
0x180627082  jnz     loc_180627828
0x180627088  mov     rcx, [rdx+68h]
0x18062708c  test    rcx, rcx
0x18062708f  jnz     loc_1806274D0
0x180627095  mov     rdx, [r13+20h]; unsigned __int16 *
0x180627099  mov     rcx, [rdx+2F0h]; pszFirst
0x1806270a0  test    rcx, rcx
0x1806270a3  jz      loc_180627256
0x1806270a9  lea     r8, [rbp+0C0h+var_F0]
0x1806270ad  mov     rax, rdi
0x1806270b0  sub     rax, r8
0x1806270b3  sar     rax, 3
0x1806270b7  inc     rax
0x1806270ba  cmp     rax, 16h
0x1806270be  jge     loc_180627814
0x1806270c4  mov     [rdi], rcx
0x1806270c7  mov     rax, r12
0x1806270ca  inc     rax
0x1806270cd  cmp     [rcx+rax*2], r9w
0x1806270d2  jnz     short loc_1806270CA
0x1806270d4  mov     [r14], eax
0x1806270d7  lea     r8, [rbp+0C0h+var_F0]; void *
0x1806270db  lea     rax, [rdi+8]
0x1806270df  sub     rax, r8
0x1806270e2  sar     rax, 3
0x1806270e6  inc     rax
0x1806270e9  cmp     rax, 16h
0x1806270ed  jl      loc_180627235
0x1806270f3  mov     esi, 80004005h
0x1806270f8  test    rbx, rbx
0x1806270fb  jz      short loc_18062710D
0x1806270fd  mov     rcx, cs:g_hProcessHeap; this
0x180627104  lea     rdx, [rbx-4]; void *
0x180627108  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18062710d  mov     rcx, [rsp+1C0h+ppURI]; struct IUnknown *
0x180627112  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180627117  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x18062711c  call    cs:__imp_SysFreeString
0x180627122  mov     rcx, [rsp+1C0h+pbstr]; bstrString
0x180627127  call    cs:__imp_SysFreeString
0x18062712d  mov     eax, esi
0x18062712f  mov     rcx, [rbp+0C0h+var_40]
0x180627136  xor     rcx, rsp; StackCookie
0x180627139  call    __security_check_cookie
0x18062713e  mov     rbx, [rsp+1C0h+arg_10]
0x180627146  add     rsp, 190h
0x18062714d  pop     r15
0x18062714f  pop     r14
0x180627151  pop     r13
0x180627153  pop     r12
0x180627155  pop     rdi
0x180627156  pop     rsi
0x180627157  pop     rbp
0x180627158  retn
0x180627159  lea     r8, [rbp+0C0h+var_F0]
0x18062715d  mov     rax, rdi
0x180627160  sub     rax, r8
0x180627163  sar     rax, 3
0x180627167  inc     rax
0x18062716a  cmp     rax, 16h
0x18062716e  jge     loc_180627814
0x180627174  lea     rax, aAcceptLanguage_0; "Accept-Language: "
0x18062717b  mov     dword ptr [r14], 11h
0x180627182  mov     [rdi], rax
0x180627185  lea     r8, [rbp+0C0h+var_F0]
0x180627189  lea     rax, [rdi+8]
0x18062718d  sub     rax, r8
0x180627190  sar     rax, 3
0x180627194  inc     rax
0x180627197  cmp     rax, 16h
0x18062719b  jge     loc_180627814
0x1806271a1  mov     [rdi+8], rcx
0x1806271a5  mov     rax, r12
0x1806271a8  inc     rax
0x1806271ab  cmp     [rcx+rax*2], r9w
0x1806271b0  jnz     short loc_1806271A8
0x1806271b2  mov     [r14+4], eax
0x1806271b6  lea     rcx, [rbp+0C0h+var_F0]
0x1806271ba  lea     rax, [rdi+10h]
0x1806271be  sub     rax, rcx
0x1806271c1  sar     rax, 3
0x1806271c5  inc     rax
0x1806271c8  cmp     rax, 16h
0x1806271cc  jge     loc_180627814
0x1806271d2  mov     [rdi+10h], r15
0x1806271d6  add     rdi, 18h
0x1806271da  mov     dword ptr [r14+8], 2
0x1806271e2  add     r14, 0Ch
0x1806271e6  jmp     loc_18062707B
0x1806271eb  cmp     r9w, [rbx]
0x1806271ef  jz      loc_180626FD1
0x1806271f5  lea     r9, [rsp+1C0h+ppURI]; ppURI
0x1806271fa  xor     r8d, r8d; dwReserved
0x1806271fd  mov     edx, 3002B84h; dwFlags
0x180627202  mov     rcx, rbx; pwzURI
0x180627205  call    cs:__imp_CreateUri
0x18062720b  mov     esi, eax
0x18062720d  test    eax, eax
0x18062720f  jnz     loc_18062710D
0x180627215  mov     rdx, [rsp+1C0h+ppURI]; struct IUri *
0x18062721a  lea     rcx, [r13-30h]; this
0x18062721e  call    ?SetUri@CDwnBindInfo@@QEAAJPEAUIUri@@@Z; CDwnBindInfo::SetUri(IUri *)
0x180627223  xor     r9d, r9d
0x180627226  mov     esi, eax
0x180627228  test    eax, eax
0x18062722a  jz      loc_180626FD1
0x180627230  jmp     loc_18062710D
0x180627235  mov     [rdi+8], r15
0x180627239  add     rdi, 10h
0x18062723d  mov     dword ptr [r14+4], 2
0x180627245  add     r14, 8
0x180627249  cmp     [rdx+2C0h], r9
0x180627250  jnz     loc_180627883
0x180627256  mov     rax, [r13+20h]
0x18062725a  mov     rcx, [rax+2C0h]
0x180627261  test    rcx, rcx
0x180627264  jz      loc_1806272F7
0x18062726a  lea     rdx, [rbp+0C0h+var_F0]
0x18062726e  mov     rax, rdi
0x180627271  sub     rax, rdx
0x180627274  sar     rax, 3
0x180627278  inc     rax
0x18062727b  cmp     rax, 16h
0x18062727f  jge     loc_180627814
0x180627285  lea     rax, aUserAgent_0; "User-Agent: "
0x18062728c  mov     dword ptr [r14], 0Ch
0x180627293  mov     [rdi], rax
0x180627296  lea     rdx, [rbp+0C0h+var_F0]
0x18062729a  lea     rax, [rdi+8]
0x18062729e  sub     rax, rdx
0x1806272a1  sar     rax, 3
0x1806272a5  inc     rax
0x1806272a8  cmp     rax, 16h
0x1806272ac  jge     loc_180627814
0x1806272b2  mov     [rdi+8], rcx
0x1806272b6  mov     rax, r12
0x1806272b9  inc     rax
0x1806272bc  cmp     [rcx+rax*2], r9w
0x1806272c1  jnz     short loc_1806272B9
0x1806272c3  mov     [r14+4], eax
0x1806272c7  lea     rcx, [rbp+0C0h+var_F0]
0x1806272cb  lea     rax, [rdi+10h]
0x1806272cf  sub     rax, rcx
0x1806272d2  sar     rax, 3
0x1806272d6  inc     rax
0x1806272d9  cmp     rax, 16h
0x1806272dd  jge     loc_1806270F3
0x1806272e3  mov     [rdi+10h], r15
0x1806272e7  add     rdi, 18h
0x1806272eb  mov     dword ptr [r14+8], 2
0x1806272f3  add     r14, 0Ch
0x1806272f7  test    rbx, rbx
0x1806272fa  jz      short loc_18062730F
0x1806272fc  mov     rcx, cs:g_hProcessHeap; this
0x180627303  lea     rdx, [rbx-4]; void *
0x180627307  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18062730c  xor     r9d, r9d
0x18062730f  mov     ebx, 80004005h
0x180627314  lea     rdx, [r13-30h]
0x180627318  mov     rcx, [r13+28h]
0x18062731c  test    rcx, rcx
0x18062731f  jnz     loc_1806275F0
0x180627325  mov     rcx, rdx; this
0x180627328  call    ?IsOriginCheckRequired@CDwnBindInfo@@QEAA_NXZ; CDwnBindInfo::IsOriginCheckRequired(void)
0x18062732d  test    al, al
0x18062732f  jnz     loc_18062789F
0x180627335  lea     rax, [rbp+0C0h+var_F0]
0x180627339  cmp     rdi, rax
0x18062733c  jbe     loc_18062710D
0x180627342  mov     r12, rdi
0x180627345  mov     eax, r9d
0x180627348  sub     r14, 4
0x18062734c  lea     rcx, [rbp+0C0h+var_F0]
0x180627350  sub     rdi, 8
0x180627354  add     eax, [r14]
0x180627357  cmp     rdi, rcx
0x18062735a  ja      short loc_180627348
0x18062735c  inc     eax
0x18062735e  lea     rbx, [rax+rax]
0x180627362  mov     rcx, rbx; cb
0x180627365  call    cs:__imp_CoTaskMemAlloc
0x18062736b  mov     r15, rax
0x18062736e  test    rax, rax
0x180627371  jz      loc_1806276C4
0x180627377  lea     r13, [rbx+rax]
0x18062737b  mov     rax, [rsp+1C0h+var_158]
0x180627380  mov     [rax], r15
0x180627383  jmp     loc_1806274C0
0x180627388  mov     eax, [r13+84h]
0x18062738f  and     al, 1
0x180627391  neg     al
0x180627393  mov     rax, [r13+20h]
0x180627397  sbb     rcx, rcx
0x18062739a  and     rcx, 0FFFFFFFFFFFFFFD8h
0x18062739e  mov     eax, [rcx+rax+2B0h]
0x1806273a5  lea     rcx, [r13-30h]
0x1806273a9  mov     dword ptr [rsp+1C0h+pIUri], eax
0x1806273ad  mov     rax, [rcx]
0x1806273b0  mov     rax, [rax+10h]
0x1806273b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806273b9  xor     r9d, r9d
0x1806273bc  mov     r12d, eax
0x1806273bf  test    eax, eax
0x1806273c1  jz      loc_180627749
0x1806273c7  test    byte ptr [r13+84h], 1
0x1806273cf  jz      loc_1806276CE
0x1806273d5  lea     rax, aReferer; "Referer: "
0x1806273dc  mov     [rsp+1C0h+pIUri], r9
0x1806273e1  mov     [rsp+1C0h+ppIUriBuilder], r9
0x1806273e6  xor     r8d, r8d; dwReserved
0x1806273e9  mov     [rsp+1C0h+bstrString], r9
0x1806273ee  mov     edx, 3022B05h; dwFlags
0x1806273f3  lea     r9, [rsp+1C0h+pIUri]; ppURI
0x1806273f8  mov     [rbp+0C0h+var_F0], rax
0x1806273fc  mov     rcx, rbx; pwzURI
0x1806273ff  mov     [rsp+1C0h+var_150], 9
0x180627407  call    cs:__imp_CreateUri
0x18062740d  xor     r9d, r9d
0x180627410  mov     edi, eax
0x180627412  test    eax, eax
0x180627414  jns     loc_18062750D
0x18062741a  mov     rcx, [rsp+1C0h+bstrString]; pbstr
0x18062741f  mov     rdx, [rsp+1C0h+pIUri]
0x180627424  test    rdx, rdx
0x180627427  jnz     loc_18062768C
0x18062742d  mov     rdx, [rsp+1C0h+ppIUriBuilder]
0x180627432  test    rdx, rdx
0x180627435  jnz     loc_1806276A8
0x18062743b  test    edi, edi
0x18062743d  js      loc_180627782
0x180627443  mov     [rbp+0C0h+var_E8], rcx
0x180627447  lea     rdi, [rbp+0C0h+var_E0]
0x18062744b  call    cs:__imp_SysStringLen
0x180627451  or      r12, 0FFFFFFFFFFFFFFFFh
0x180627455  mov     [rsp+1C0h+var_14C], eax
  ... truncated ...
```
