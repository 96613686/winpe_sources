# CSubscription::CreateFromTier2CheckConfig(IEventSystemTier2 *,IUnknown *,ushort const * *,int,IDispatch * *)

- ea: `0x1800291b0`
- end: `0x18002987e`
- name: `?CreateFromTier2CheckConfig@CSubscription@@SAJPEAUIEventSystemTier2@@PEAUIUnknown@@PEAPEBGHPEAPEAUIDispatch@@@Z`
- size: `1742`
- prototype: `__int64 __fastcall(struct IEventSystemTier2 *, struct IUnknown *, const unsigned __int16 **, int, struct IDispatch **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008938`
- `0x180012654`
- `0x180015850`
- `0x180015efc`
- `0x180022778`
- `0x1800291b0`
- `0x18003f080`
- `0x1800434ae`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180029548`
- `OLEAUT32!__imp_VariantInit` at `0x18002963b`
- `OLEAUT32!__imp_VariantInit` at `0x180029548`
- `OLEAUT32!__imp_VariantInit` at `0x18002963b`
- `OLEAUT32!__imp_VariantClear` at `0x180029598`
- `OLEAUT32!__imp_VariantClear` at `0x1800295ae`
- `OLEAUT32!__imp_VariantClear` at `0x18002968b`
- `OLEAUT32!__imp_VariantClear` at `0x1800296a1`
- `OLEAUT32!__imp_VariantClear` at `0x180029598`
- `OLEAUT32!__imp_VariantClear` at `0x1800295ae`
- `OLEAUT32!__imp_VariantClear` at `0x18002968b`
- `OLEAUT32!__imp_VariantClear` at `0x1800296a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296af`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296af`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800296d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029203`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800293a6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800293a6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800292ad`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800292ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002978f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002978f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800297c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800297c5`
- `PROPSYS!PropVariantToVariant` at `0x180029566`
- `PROPSYS!PropVariantToVariant` at `0x180029659`
- `PROPSYS!PropVariantToVariant` at `0x180029566`
- `PROPSYS!PropVariantToVariant` at `0x180029659`

## string_xrefs

- `0x1800293c0`: `com\complus\src\events\tier1\subscription.cpp`
- `0x1800294fd`: `com\complus\src\events\tier1\subscription.cpp`
- `0x1800295f2`: `com\complus\src\events\tier1\subscription.cpp`
- `0x1800297dd`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180029823`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
__int64 __fastcall CSubscription::CreateFromTier2CheckConfig(
        struct IEventSystemTier2 *a1,
        struct IUnknown *a2,
        const unsigned __int16 **a3,
        int a4,
        struct IDispatch **a5)
{
  const unsigned __int16 **v6; // r13
  CSubscription *v8; // rax
  CSubscription *v9; // rsi
  HRESULT v11; // ebx
  __int64 v12; // r9
  HRESULT v13; // eax
  int v14; // r14d
  int v15; // eax
  unsigned int i; // r15d
  __int64 v17; // r13
  unsigned int j; // r14d
  __int64 v19; // r15
  int v20; // eax
  HRESULT Instance; // eax
  int v22; // eax
  struct IUnknown *v23; // [rsp+50h] [rbp-158h] BYREF
  int v24; // [rsp+58h] [rbp-150h]
  IUnknown *pProxy; // [rsp+60h] [rbp-148h] BYREF
  struct IDispatch *v26; // [rsp+68h] [rbp-140h] BYREF
  CSubscription *v27; // [rsp+70h] [rbp-138h]
  struct tagBLOB v28; // [rsp+78h] [rbp-130h] BYREF
  const unsigned __int16 **v29; // [rsp+88h] [rbp-120h]
  struct IEventSystemTier2 *v30; // [rsp+90h] [rbp-118h]
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-110h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-100h]
  PROPVARIANT v33[2]; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-E8h]
  struct IDispatch **v35; // [rsp+C8h] [rbp-E0h]
  PROPVARIANT v36[2]; // [rsp+D0h] [rbp-D8h] BYREF
  __int64 v37; // [rsp+E0h] [rbp-C8h]
  PROPVARIANT v38[2]; // [rsp+E8h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+F8h] [rbp-B0h]
  struct tagPROPVARIANT v40; // [rsp+100h] [rbp-A8h] BYREF
  struct tagPROPVARIANT v41; // [rsp+120h] [rbp-88h] BYREF
  struct tagPROPVARIANT pclsid; // [rsp+140h] [rbp-68h] BYREF

  v6 = a3;
  v29 = a3;
  v30 = a1;
  v35 = a5;
  v8 = (CSubscription *)CoTaskMemAlloc(0x388u);
  if ( v8 )
    v9 = CSubscription::CSubscription(v8);
  else
    v9 = 0;
  v27 = v9;
  if ( !v9 )
    return 2147942414LL;
  v26 = 0;
  v11 = (**(__int64 (__fastcall ***)(CSubscription *, GUID *, struct IDispatch **))v9)(
          v9,
          &IID_IEventSubscription2,
          &v26);
  if ( v11 >= 0 )
  {
    pProxy = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IEventSubscriptionTier2,
            &pProxy);
    if ( v11 >= 0 )
    {
      CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
      *(_OWORD *)pvar = 0;
      v32 = 0;
      *(_OWORD *)v36 = 0;
      v37 = 0;
      *(_OWORD *)v33 = 0;
      v34 = 0;
      *(_OWORD *)v38 = 0;
      v39 = 0;
      v23 = 0;
      *(_QWORD *)&v28.cbSize = 0;
      v28.pBlobData = 0;
      v11 = ((__int64 (__fastcall *)(IUnknown *, struct IEventSystemTier2 *, char *, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *, struct tagBLOB *))pProxy->lpVtbl[1].AddRef)(
              pProxy,
              v30,
              (char *)v9 + 40,
              pvar,
              v36,
              v33,
              v38,
              &v28);
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      if ( v11 >= 0 )
      {
        *(GUID *)&pclsid.vt = GUID_NULL;
        if ( *((_WORD *)v9 + 212) )
        {
          v13 = CLSIDFromString(*((LPCOLESTR *)v9 + 54), (LPCLSID)&pclsid);
          v11 = v13;
          if ( v13 < 0 )
            InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x178u, 0x10u, v13);
        }
        else
        {
          *(GUID *)&pclsid.vt = GUID_NULL;
        }
        v14 = v11;
        if ( a4 )
        {
          if ( !memcmp_0(&GUID_NULL, &pclsid, 0x10u) )
          {
            v11 = -2147220979;
            v14 = -2147220979;
          }
LABEL_20:
          if ( v14 >= 0 )
          {
            pclsid = *(struct tagPROPVARIANT *)((char *)v9 + 448);
            v40 = *(struct tagPROPVARIANT *)((char *)v9 + 424);
            v41 = *(struct tagPROPVARIANT *)((char *)v9 + 40);
            v15 = ConcatenateECID_PARTID_APPID(&v41, &v40, &pclsid, v12, (unsigned __int16 *)v9 + 334);
            v11 = v15;
            if ( v15 >= 0 )
            {
              if ( LOWORD(pvar[0]) == 4127 )
              {
                if ( LOWORD(v36[0]) != 4108 )
                  InternalAssert(
                    L"com\\complus\\src\\events\\tier1\\subscription.cpp",
                    0x199u,
                    0x10u,
                    L"pubProps.vt == (VT_VECTOR | VT_VARIANT)");
                for ( i = 0; ; ++i )
                {
                  v15 = v11;
                  if ( i >= LODWORD(pvar[1]) )
                    break;
                  v17 = *(_QWORD *)(v32 + 8LL * i);
                  memset(&pclsid, 0, sizeof(pclsid));
                  VariantInit((VARIANTARG *)&pclsid);
                  v11 = PropVariantToVariant((const PROPVARIANT *)(v37 + 24LL * i), (VARIANT *)&pclsid);
                  if ( v11 < 0 )
                  {
                    VariantClear((VARIANTARG *)&pclsid);
                    v15 = v11;
                    break;
                  }
                  (*(void (__fastcall **)(__int64, struct tagPROPVARIANT *, __int64))(*((_QWORD *)v9 + 61) + 88LL))(
                    (__int64)v9 + 488,
                    &pclsid,
                    v17);
                  VariantClear((VARIANTARG *)&pclsid);
                }
                v6 = v29;
              }
              if ( v15 >= 0 && LOWORD(v33[0]) == 4127 )
              {
                if ( LOWORD(v38[0]) != 4108 )
                  InternalAssert(
                    L"com\\complus\\src\\events\\tier1\\subscription.cpp",
                    0x1AEu,
                    0x10u,
                    L"subProps.vt == (VT_VECTOR | VT_VARIANT)");
                for ( j = 0; j < LODWORD(v33[1]); ++j )
                {
                  v19 = *(_QWORD *)(v34 + 8LL * j);
                  memset(&pclsid, 0, sizeof(pclsid));
                  VariantInit((VARIANTARG *)&pclsid);
                  v11 = PropVariantToVariant((const PROPVARIANT *)(v39 + 24LL * j), (VARIANT *)&pclsid);
                  if ( v11 < 0 )
                  {
                    VariantClear((VARIANTARG *)&pclsid);
                    break;
                  }
                  (*(void (__fastcall **)(__int64, struct tagPROPVARIANT *, __int64))(*((_QWORD *)v9 + 72) + 88LL))(
                    (__int64)v9 + 576,
                    &pclsid,
                    v19);
                  VariantClear((VARIANTARG *)&pclsid);
                }
              }
            }
            PropVariantClear(pvar);
            PropVariantClear(v36);
            PropVariantClear(v33);
            PropVariantClear(v38);
          }
          if ( v11 < 0 )
          {
            ((void (__fastcall *)(struct IDispatch *))v26->lpVtbl->Release)(v26);
            v26 = 0;
            v9 = 0;
            v27 = 0;
          }
          else
          {
            *v35 = v26;
            if ( v6 )
              *v6 = (const unsigned __int16 *)((char *)v9 + 668);
          }
          if ( v11 < 0 || !v28.pBlobData )
            goto LABEL_54;
          v20 = UnmarshalIUnknownFromBlob(&v28, &v23);
          v11 = v20;
          if ( v20 == -2147023174 || v20 == -2147417848 || (unsigned int)(v20 + 2147023170) <= 1 )
          {
            (*(void (__fastcall **)(struct IEventSystemTier2 *, const wchar_t *))(*(_QWORD *)v30 + 96LL))(v30, L"ALL");
            v11 = 0;
          }
          else if ( v20 >= 0 )
          {
            goto LABEL_54;
          }
          v23 = 0;
LABEL_54:
          if ( v28.pBlobData )
            CoTaskMemFree(v28.pBlobData);
          if ( v23 )
          {
            if ( !*((_QWORD *)v9 + 59) )
            {
              Instance = CoCreateInstance(
                           &CLSID_StdGlobalInterfaceTable,
                           0,
                           0x17u,
                           &IID_IGlobalInterfaceTable,
                           (LPVOID *)v9 + 59);
              if ( Instance < 0 )
                InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x200u, 0x11u, Instance);
            }
            v22 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, GUID *, __int64))(**((_QWORD **)v9 + 59) + 24LL))(
                    *((_QWORD *)v9 + 59),
                    v23,
                    &IID_IUnknown,
                    (__int64)v9 + 480);
            v11 = v22;
            v24 = v22;
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x208u, 0x11u, v22);
            ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
          }
          goto LABEL_63;
        }
        if ( !memcmp_0(&GUID_NULL, &pclsid, 0x10u) )
          goto LABEL_20;
        v11 = -2147220978;
      }
      v14 = v11;
      goto LABEL_20;
    }
  }
LABEL_63:
  if ( v9 )
    *((_DWORD *)v9 + 166) = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800291b0  push    rbx
0x1800291b2  push    rsi
0x1800291b3  push    rdi
0x1800291b4  push    r12
0x1800291b6  push    r13
0x1800291b8  push    r14
0x1800291ba  push    r15
0x1800291bc  sub     rsp, 170h
0x1800291c3  mov     rax, cs:__security_cookie
0x1800291ca  xor     rax, rsp
0x1800291cd  mov     [rsp+1A8h+var_48], rax
0x1800291d5  mov     r15d, r9d
0x1800291d8  mov     r13, r8
0x1800291db  mov     [rsp+1A8h+var_120], r8
0x1800291e3  mov     r14, rdx
0x1800291e6  mov     [rsp+1A8h+var_118], rcx
0x1800291ee  mov     rax, [rsp+1A8h+arg_20]
0x1800291f6  mov     [rsp+1A8h+var_E0], rax
0x1800291fe  mov     ecx, 388h; cb
0x180029203  call    cs:__imp_CoTaskMemAlloc
0x180029209  xor     edi, edi
0x18002920b  test    rax, rax
0x18002920e  jz      short loc_18002921D
0x180029210  mov     rcx, rax; this
0x180029213  call    ??0CSubscription@@AEAA@XZ; CSubscription::CSubscription(void)
0x180029218  mov     rsi, rax
0x18002921b  jmp     short loc_180029220
0x18002921d  mov     rsi, rdi
0x180029220  mov     [rsp+1A8h+var_138], rsi
0x180029225  test    rsi, rsi
0x180029228  jnz     short loc_180029234
0x18002922a  mov     eax, 8007000Eh
0x18002922f  jmp     loc_18002985B
0x180029234  mov     [rsp+1A8h+var_140], rdi
0x180029239  mov     rax, [rsi]
0x18002923c  lea     r8, [rsp+1A8h+var_140]
0x180029241  lea     rdx, IID_IEventSubscription2
0x180029248  mov     rcx, rsi
0x18002924b  mov     rax, [rax]
0x18002924e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029253  mov     ebx, eax
0x180029255  test    eax, eax
0x180029257  js      loc_18002984E
0x18002925d  mov     [rsp+1A8h+pProxy], rdi
0x180029262  mov     rax, [r14]
0x180029265  lea     r8, [rsp+1A8h+pProxy]
0x18002926a  lea     rdx, IID_IEventSubscriptionTier2
0x180029271  mov     rcx, r14
0x180029274  mov     rax, [rax]
0x180029277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002927c  mov     ebx, eax
0x18002927e  test    eax, eax
0x180029280  js      loc_18002984E
0x180029286  mov     [rsp+1A8h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002928e  mov     [rsp+1A8h+pAuthInfo], rdi; pAuthInfo
0x180029293  mov     [rsp+1A8h+dwImpLevel], 3; dwImpLevel
0x18002929b  mov     [rsp+1A8h+dwAuthnLevel], edi; dwAuthnLevel
0x18002929f  xor     r9d, r9d; pServerPrincName
0x1800292a2  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800292a5  mov     r8d, edx; dwAuthzSvc
0x1800292a8  mov     rcx, [rsp+1A8h+pProxy]; pProxy
0x1800292ad  call    cs:__imp_CoSetProxyBlanket
0x1800292b3  xorps   xmm0, xmm0
0x1800292b6  xor     eax, eax
0x1800292b8  movups  xmmword ptr [rsp+1A8h+pvar], xmm0
0x1800292c0  mov     [rsp+1A8h+var_100], rax
0x1800292c8  xorps   xmm1, xmm1
0x1800292cb  movups  xmmword ptr [rsp+1A8h+var_D8], xmm1
0x1800292d3  mov     [rsp+1A8h+var_C8], rax
0x1800292db  movups  xmmword ptr [rsp+1A8h+var_F8], xmm0
0x1800292e3  mov     [rsp+1A8h+var_E8], rax
0x1800292eb  movups  xmmword ptr [rsp+1A8h+var_C0], xmm1
0x1800292f3  mov     [rsp+1A8h+var_B0], rax
0x1800292fb  mov     [rsp+1A8h+var_158], rdi
0x180029300  mov     qword ptr [rsp+1A8h+var_130.cbSize], rdi
0x180029305  mov     [rsp+1A8h+var_130.pBlobData], rdi
0x18002930d  mov     rcx, [rsp+1A8h+pProxy]
0x180029312  mov     rax, [rcx]
0x180029315  lea     rdx, [rsp+1A8h+var_130]
0x18002931a  mov     qword ptr [rsp+1A8h+dwCapabilities], rdx
0x18002931f  lea     rdx, [rsp+1A8h+var_C0]
0x180029327  mov     [rsp+1A8h+pAuthInfo], rdx
0x18002932c  lea     rdx, [rsp+1A8h+var_F8]
0x180029334  mov     qword ptr [rsp+1A8h+dwImpLevel], rdx
0x180029339  lea     rdx, [rsp+1A8h+var_D8]
0x180029341  mov     qword ptr [rsp+1A8h+dwAuthnLevel], rdx
0x180029346  lea     r9, [rsp+1A8h+pvar]
0x18002934e  lea     r8, [rsi+28h]
0x180029352  mov     rdx, [rsp+1A8h+var_118]
0x18002935a  mov     rax, [rax+20h]
0x18002935e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029363  mov     ebx, eax
0x180029365  mov     rcx, [rsp+1A8h+pProxy]
0x18002936a  mov     rax, [rcx]
0x18002936d  mov     rax, [rax+10h]
0x180029371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029376  test    ebx, ebx
0x180029378  js      loc_18002942D
0x18002937e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180029385  movdqu  xmmword ptr [rsp+1A8h+pclsid.Data1], xmm0
0x18002938e  cmp     [rsi+1A8h], di
0x180029395  jz      short loc_1800293CE
0x180029397  lea     rdx, [rsp+1A8h+pclsid]; pclsid
0x18002939f  mov     rcx, [rsi+1B0h]; lpsz
0x1800293a6  call    cs:__imp_CLSIDFromString
0x1800293ac  mov     ebx, eax
0x1800293ae  test    eax, eax
0x1800293b0  jns     short loc_1800293D7
0x1800293b2  mov     r8d, 10h; unsigned __int16
0x1800293b8  mov     r9d, eax; int
0x1800293bb  mov     edx, 178h; unsigned int
0x1800293c0  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x1800293c7  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800293cc  jmp     short loc_1800293D7
0x1800293ce  movdqu  xmmword ptr [rsp+1A8h+pclsid.Data1], xmm0
0x1800293d7  mov     r14d, ebx
0x1800293da  test    r15d, r15d
0x1800293dd  jz      short loc_18002940A
0x1800293df  mov     r8d, 10h; Size
0x1800293e5  lea     rdx, [rsp+1A8h+pclsid]; Buf2
0x1800293ed  lea     rcx, GUID_NULL; Buf1
0x1800293f4  call    memcmp_0
0x1800293f9  test    eax, eax
0x1800293fb  jnz     short loc_180029405
0x1800293fd  mov     ebx, 8004020Dh
0x180029402  mov     r14d, ebx
0x180029405  test    r15d, r15d
0x180029408  jnz     short loc_180029430
0x18002940a  mov     r8d, 10h; Size
0x180029410  lea     rdx, [rsp+1A8h+pclsid]; Buf2
0x180029418  lea     rcx, GUID_NULL; Buf1
0x18002941f  call    memcmp_0
0x180029424  test    eax, eax
0x180029426  jz      short loc_180029430
0x180029428  mov     ebx, 8004020Eh
0x18002942d  mov     r14d, ebx
0x180029430  test    r14d, r14d
0x180029433  js      loc_1800296DF
0x180029439  movups  xmm0, xmmword ptr [rsi+1C0h]
0x180029440  movaps  xmmword ptr [rsp+1A8h+pclsid.Data1], xmm0
0x180029448  movsd   xmm1, qword ptr [rsi+1D0h]
0x180029450  movsd   [rsp+1A8h+var_58], xmm1
0x180029459  movups  xmm0, xmmword ptr [rsi+1A8h]
0x180029460  movaps  xmmword ptr [rsp+1A8h+var_A8], xmm0
0x180029468  movsd   xmm1, qword ptr [rsi+1B8h]
0x180029470  movsd   qword ptr [rsp+1A8h+var_A8+10h], xmm1
0x180029479  movups  xmm0, xmmword ptr [rsi+28h]
0x18002947d  movaps  xmmword ptr [rsp+1A8h+var_88], xmm0
0x180029485  movsd   xmm1, qword ptr [rsi+38h]
0x18002948a  movsd   qword ptr [rsp+1A8h+var_88+10h], xmm1
0x180029493  lea     rax, [rsi+29Ch]
0x18002949a  mov     qword ptr [rsp+1A8h+dwAuthnLevel], rax; unsigned __int16 *
0x18002949f  lea     r8, [rsp+1A8h+pclsid]; struct tagPROPVARIANT *
0x1800294a7  lea     rdx, [rsp+1A8h+var_A8]; struct tagPROPVARIANT *
0x1800294af  lea     rcx, [rsp+1A8h+var_88]; struct tagPROPVARIANT *
0x1800294b7  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x1800294bc  mov     ebx, eax
0x1800294be  mov     r12d, 101Fh
0x1800294c4  lea     r14d, [r12-13h]
0x1800294c9  test    eax, eax
0x1800294cb  js      loc_1800296A7
0x1800294d1  cmp     word ptr [rsp+1A8h+pvar], r12w
0x1800294da  jnz     loc_1800295BE
0x1800294e0  cmp     word ptr [rsp+1A8h+var_D8], r14w
0x1800294e9  jz      short loc_180029509
0x1800294eb  mov     r8d, 10h; unsigned __int16
0x1800294f1  lea     r9, aPubpropsVtVtVe; "pubProps.vt == (VT_VECTOR | VT_VARIANT)"
0x1800294f8  mov     edx, 199h; unsigned int
0x1800294fd  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180029504  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180029509  mov     r15d, edi
0x18002950c  mov     eax, ebx
0x18002950e  cmp     r15d, dword ptr [rsp+1A8h+pvar+8]
0x180029516  jnb     loc_1800295B6
0x18002951c  mov     ebx, r15d
0x18002951f  mov     rax, [rsp+1A8h+var_100]
0x180029527  mov     r13, [rax+rbx*8]
0x18002952b  xorps   xmm0, xmm0
0x18002952e  xor     eax, eax
0x180029530  movups  xmmword ptr [rsp+1A8h+pclsid.Data1], xmm0
0x180029538  mov     [rsp+1A8h+var_58], rax
0x180029540  lea     rcx, [rsp+1A8h+pclsid]; pvarg
0x180029548  call    cs:__imp_VariantInit
0x18002954e  lea     rcx, [rbx+rbx*2]
0x180029552  mov     rax, [rsp+1A8h+var_C8]
0x18002955a  lea     rcx, [rax+rcx*8]; pPropVar
0x18002955e  lea     rdx, [rsp+1A8h+pclsid]; pVar
0x180029566  call    cs:__imp_PropVariantToVariant
0x18002956c  mov     ebx, eax
0x18002956e  test    eax, eax
0x180029570  js      short loc_1800295A6
0x180029572  lea     rcx, [rsi+1E8h]
0x180029579  mov     rax, [rcx]
0x18002957c  mov     r8, r13
0x18002957f  lea     rdx, [rsp+1A8h+pclsid]
0x180029587  mov     rax, [rax+58h]
0x18002958b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029590  lea     rcx, [rsp+1A8h+pclsid]; pvarg
0x180029598  call    cs:__imp_VariantClear
0x18002959e  inc     r15d
0x1800295a1  jmp     loc_18002950C
0x1800295a6  lea     rcx, [rsp+1A8h+pclsid]; pvarg
0x1800295ae  call    cs:__imp_VariantClear
0x1800295b4  mov     eax, ebx
0x1800295b6  mov     r13, [rsp+1A8h+var_120]
0x1800295be  test    eax, eax
0x1800295c0  js      loc_1800296A7
0x1800295c6  cmp     word ptr [rsp+1A8h+var_F8], r12w
0x1800295cf  jnz     loc_1800296A7
0x1800295d5  cmp     word ptr [rsp+1A8h+var_C0], r14w
0x1800295de  jz      short loc_1800295FE
0x1800295e0  mov     r8d, 10h; unsigned __int16
0x1800295e6  lea     r9, aSubpropsVtVtVe; "subProps.vt == (VT_VECTOR | VT_VARIANT)"
0x1800295ed  mov     edx, 1AEh; unsigned int
0x1800295f2  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x1800295f9  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800295fe  mov     r14d, edi
0x180029601  cmp     r14d, dword ptr [rsp+1A8h+var_F8+8]
0x180029609  jnb     loc_1800296A7
0x18002960f  mov     ebx, r14d
0x180029612  mov     rax, [rsp+1A8h+var_E8]
0x18002961a  mov     r15, [rax+rbx*8]
0x18002961e  xorps   xmm0, xmm0
0x180029621  xor     eax, eax
0x180029623  movups  xmmword ptr [rsp+1A8h+pclsid.Data1], xmm0
0x18002962b  mov     [rsp+1A8h+var_58], rax
0x180029633  lea     rcx, [rsp+1A8h+pclsid]; pvarg
0x18002963b  call    cs:__imp_VariantInit
0x180029641  lea     rcx, [rbx+rbx*2]
0x180029645  mov     rax, [rsp+1A8h+var_B0]
0x18002964d  lea     rcx, [rax+rcx*8]; pPropVar
0x180029651  lea     rdx, [rsp+1A8h+pclsid]; pVar
0x180029659  call    cs:__imp_PropVariantToVariant
0x18002965f  mov     ebx, eax
0x180029661  test    eax, eax
0x180029663  js      short loc_180029699
0x180029665  lea     rcx, [rsi+240h]
0x18002966c  mov     rax, [rcx]
0x18002966f  mov     r8, r15
0x180029672  lea     rdx, [rsp+1A8h+pclsid]
0x18002967a  mov     rax, [rax+58h]
0x18002967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029683  lea     rcx, [rsp+1A8h+pclsid]; pvarg
0x18002968b  call    cs:__imp_VariantClear
0x180029691  inc     r14d
0x180029694  jmp     loc_180029601
0x180029699  lea     rcx, [rsp+1A8h+pclsid]; pvarg
0x1800296a1  call    cs:__imp_VariantClear
0x1800296a7  lea     rcx, [rsp+1A8h+pvar]; pvar
0x1800296af  call    cs:__imp_PropVariantClear
0x1800296b5  lea     rcx, [rsp+1A8h+var_D8]; pvar
0x1800296bd  call    cs:__imp_PropVariantClear
0x1800296c3  lea     rcx, [rsp+1A8h+var_F8]; pvar
0x1800296cb  call    cs:__imp_PropVariantClear
0x1800296d1  lea     rcx, [rsp+1A8h+var_C0]; pvar
0x1800296d9  call    cs:__imp_PropVariantClear
0x1800296df  test    ebx, ebx
0x1800296e1  js      short loc_180029705
0x1800296e3  mov     rax, [rsp+1A8h+var_140]
0x1800296e8  mov     rcx, [rsp+1A8h+var_E0]
0x1800296f0  mov     [rcx], rax
0x1800296f3  test    r13, r13
0x1800296f6  jz      short loc_180029723
0x1800296f8  lea     rax, [rsi+29Ch]
0x1800296ff  mov     [r13+0], rax
0x180029703  jmp     short loc_180029723
0x180029705  mov     rcx, [rsp+1A8h+var_140]
0x18002970a  mov     rax, [rcx]
0x18002970d  mov     rax, [rax+10h]
0x180029711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029716  mov     [rsp+1A8h+var_140], rdi
0x18002971b  mov     rsi, rdi
0x18002971e  mov     [rsp+1A8h+var_138], rdi
0x180029723  test    ebx, ebx
0x180029725  js      short loc_180029782
0x180029727  cmp     [rsp+1A8h+var_130.pBlobData], rdi
0x18002972f  jz      short loc_180029782
0x180029731  lea     rdx, [rsp+1A8h+var_158]; struct IUnknown **
0x180029736  lea     rcx, [rsp+1A8h+var_130]; struct tagBLOB *
0x18002973b  call    ?UnmarshalIUnknownFromBlob@@YAJAEBUtagBLOB@@AEAPEAUIUnknown@@@Z; UnmarshalIUnknownFromBlob(tagBLOB const &,IUnknown * &)
0x180029740  mov     ebx, eax
0x180029742  cmp     eax, 800706BAh
0x180029747  jz      short loc_180029760
0x180029749  cmp     eax, 80010108h
0x18002974e  jz      short loc_180029760
0x180029750  add     eax, 7FF8F942h
0x180029755  cmp     eax, 1
0x180029758  jbe     short loc_180029760
0x18002975a  test    ebx, ebx
0x18002975c  js      short loc_18002977D
0x18002975e  jmp     short loc_180029782
0x180029760  mov     rcx, [rsp+1A8h+var_118]
0x180029768  mov     rax, [rcx]
0x18002976b  lea     rdx, aAll; "ALL"
0x180029772  mov     rax, [rax+60h]
0x180029776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002977b  mov     ebx, edi
0x18002977d  mov     [rsp+1A8h+var_158], rdi
0x180029782  mov     rcx, [rsp+1A8h+var_130.pBlobData]; pv
0x18002978a  test    rcx, rcx
  ... truncated ...
```
