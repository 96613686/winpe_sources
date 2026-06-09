# CRegBagBase::Read(ushort const *,tagVARIANT *,IErrorLog *)

- ea: `0x180011f00`
- end: `0x180012210`
- name: `?Read@CRegBagBase@@UEAAJPEBGPEAUtagVARIANT@@PEAUIErrorLog@@@Z`
- size: `784`
- prototype: `int(CRegBagBase *__hidden this, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004640`
- `0x180004740`
- `0x180004b48`
- `0x180006b38`
- `0x18000dba4`
- `0x18000dbe4`
- `0x18001009c`
- `0x18001020c`
- `0x180010e9c`
- `0x180011c40`
- `0x180011f00`
- `0x180012334`
- `0x1800f8010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1800120b9`
- `ole32!CLSIDFromString` at `0x1800120b9`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800120ef`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012108`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800120ef`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012108`
- `ADVAPI32!RegQueryValueW` at `0x180012090`
- `ADVAPI32!RegQueryValueW` at `0x180012090`
- `ADVAPI32!RegQueryValueExW` at `0x180011f76`
- `ADVAPI32!RegQueryValueExW` at `0x180011fd8`
- `ADVAPI32!RegQueryValueExW` at `0x180011f76`
- `ADVAPI32!RegQueryValueExW` at `0x180011fd8`

## pseudocode

```c
__int64 __fastcall CRegBagBase::Read(CRegBagBase *this, WCHAR *a2, struct tagVARIANT *a3, struct IErrorLog *a4)
{
  HKEY v8; // rcx
  LSTATUS v9; // eax
  CRegBagBase *v10; // rcx
  BYTE *v12; // rsi
  unsigned __int64 v13; // rdx
  int v14; // ebx
  unsigned __int64 v15; // rdx
  HKEY v16; // rdx
  int v17; // eax
  int v18; // eax
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID v23; // [rsp+38h] [rbp-C8h] BYREF
  LONG v24; // [rsp+40h] [rbp-C0h] BYREF
  void *v25; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  CLSID pclsid; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR Data[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR sz[160]; // [rsp+C0h] [rbp-40h] BYREF

  if ( a2 && a3 )
  {
    v8 = (HKEY)*((_QWORD *)this + 11);
    Type = 0;
    cbData = 64;
    v9 = RegQueryValueExW(v8, a2, 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v9 )
    {
      LODWORD(lpData) = cbData;
      return CRegBagBase::RegConvertToVARIANT(v10, a3, Type, Data, (size_t)lpData);
    }
    if ( v9 == 234 )
    {
      cbData += 2;
      v12 = (BYTE *)operator new[](cbData);
      v14 = RegQueryValueExW(*((HKEY *)this + 11), a2, 0, &Type, v12, &cbData);
      if ( v14 )
      {
        operator delete(v12, v13);
        if ( v14 > 0 )
          return (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        LODWORD(lpDataa) = cbData;
        v14 = CRegBagBase::RegConvertToVARIANT((CRegBagBase *)cbData, a3, Type, (const OLECHAR *)v12, (size_t)lpDataa);
        operator delete(v12, v15);
      }
      return (unsigned int)v14;
    }
    v16 = (HKEY)*((_QWORD *)this + 11);
    memset(hKey, 0, sizeof(hKey));
    v17 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, v16, a2, 0x20019u, 0);
    v14 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v14 = (unsigned __int16)v17 | 0x80070000;
      goto LABEL_27;
    }
    v24 = 320;
    v18 = RegQueryValueW(hKey[0], 0, sz, &v24);
    if ( v18 )
    {
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v14 = v18;
      goto LABEL_27;
    }
    pclsid = 0;
    if ( CLSIDFromString(sz, &pclsid) < 0 )
    {
      v14 = -2147467259;
LABEL_27:
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      return (unsigned int)v14;
    }
    if ( !a3->vt || a3->vt == 1 )
    {
      a3->vt = 9;
      a3->llVal = 0;
    }
    else if ( a3->vt != 9
           && a3->vt != 13
           && VariantChangeType(a3, a3, 0, 9u) < 0
           && VariantChangeType(a3, a3, 0, 0xDu) < 0 )
    {
      v14 = -2147024809;
      goto LABEL_27;
    }
    ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>(
      &v25,
      a3->llVal);
    v23 = v25;
    if ( v25 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
    v14 = LoadPersistedObject<ATL::CComQIPtr<IPropertyBag,&__s_GUID const _GUID_55272a00_42cb_11ce_8135_00aa004bb851>,ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>>(
            &v23,
            &pclsid,
            a2,
            (__int64)a4);
    if ( v14 < 0 )
    {
      ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>(&v23);
      ppv = v23;
      if ( v23 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 8LL))(v23);
      v14 = LoadPersistedObject<ATL::CComQIPtr<IPropertyBag2,&__s_GUID const _GUID_22f55882_280b_11d0_a8a9_00a0c90c2004>,ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>>(
              &ppv,
              &pclsid,
              a2,
              (__int64)a4);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v25);
    goto LABEL_27;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180011f00  push    rbp
0x180011f02  push    rbx
0x180011f03  push    rsi
0x180011f04  push    rdi
0x180011f05  push    r14
0x180011f07  push    r15
0x180011f09  lea     rbp, [rsp-118h]
0x180011f11  sub     rsp, 218h
0x180011f18  mov     rax, cs:__security_cookie
0x180011f1f  xor     rax, rsp
0x180011f22  mov     [rbp+140h+var_40], rax
0x180011f29  mov     rsi, r9
0x180011f2c  mov     rdi, r8
0x180011f2f  mov     r15, rdx
0x180011f32  mov     r14, rcx
0x180011f35  test    rdx, rdx
0x180011f38  jz      loc_1800121EC
0x180011f3e  test    r8, r8
0x180011f41  jz      loc_1800121EC
0x180011f47  mov     rcx, [rcx+58h]; hKey
0x180011f4b  lea     rax, [rsp+240h+cbData]
0x180011f50  mov     [rsp+240h+lpcbData], rax; lpcbData
0x180011f55  lea     r9, [rsp+240h+Type]; lpType
0x180011f5a  lea     rax, [rbp+140h+Data]
0x180011f5e  mov     [rsp+240h+Type], 0
0x180011f66  xor     r8d, r8d; lpReserved
0x180011f69  mov     [rsp+240h+lpData], rax; lpData
0x180011f6e  mov     [rsp+240h+cbData], 40h ; '@'
0x180011f76  call    cs:__imp_RegQueryValueExW
0x180011f7c  test    eax, eax
0x180011f7e  jnz     short loc_180011F9E
0x180011f80  mov     eax, [rsp+240h+cbData]
0x180011f84  lea     r9, [rbp+140h+Data]; unsigned __int8 *
0x180011f88  mov     r8d, [rsp+240h+Type]; unsigned int
0x180011f8d  mov     rdx, rdi; struct tagVARIANT *
0x180011f90  mov     dword ptr [rsp+240h+lpData], eax; unsigned int
0x180011f94  call    ?RegConvertToVARIANT@CRegBagBase@@IEAAJPEAUtagVARIANT@@KPEAEK@Z; CRegBagBase::RegConvertToVARIANT(tagVARIANT *,ulong,uchar *,ulong)
0x180011f99  jmp     loc_1800121F1
0x180011f9e  cmp     eax, 0EAh
0x180011fa3  jnz     short loc_180012024
0x180011fa5  mov     eax, [rsp+240h+cbData]
0x180011fa9  add     eax, 2
0x180011fac  mov     ecx, eax; unsigned __int64
0x180011fae  mov     [rsp+240h+cbData], eax
0x180011fb2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011fb7  mov     rcx, [r14+58h]; hKey
0x180011fbb  lea     r9, [rsp+240h+Type]; lpType
0x180011fc0  mov     rsi, rax
0x180011fc3  xor     r8d, r8d; lpReserved
0x180011fc6  lea     rax, [rsp+240h+cbData]
0x180011fcb  mov     rdx, r15; lpValueName
0x180011fce  mov     [rsp+240h+lpcbData], rax; lpcbData
0x180011fd3  mov     [rsp+240h+lpData], rsi; lpData
0x180011fd8  call    cs:__imp_RegQueryValueExW
0x180011fde  mov     ebx, eax
0x180011fe0  test    eax, eax
0x180011fe2  jnz     short loc_18001200D
0x180011fe4  mov     ecx, [rsp+240h+cbData]; this
0x180011fe8  mov     r9, rsi; unsigned __int8 *
0x180011feb  mov     r8d, [rsp+240h+Type]; unsigned int
0x180011ff0  mov     rdx, rdi; struct tagVARIANT *
0x180011ff3  mov     dword ptr [rsp+240h+lpData], ecx; unsigned int
0x180011ff7  call    ?RegConvertToVARIANT@CRegBagBase@@IEAAJPEAUtagVARIANT@@KPEAEK@Z; CRegBagBase::RegConvertToVARIANT(tagVARIANT *,ulong,uchar *,ulong)
0x180011ffc  mov     rcx, rsi; void *
0x180011fff  mov     ebx, eax
0x180012001  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012006  mov     eax, ebx
0x180012008  jmp     loc_1800121F1
0x18001200d  mov     rcx, rsi; void *
0x180012010  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012015  test    ebx, ebx
0x180012017  jle     short loc_180012006
0x180012019  movzx   ebx, bx
0x18001201c  or      ebx, 80070000h
0x180012022  jmp     short loc_180012006
0x180012024  mov     rdx, [r14+58h]; hKey
0x180012028  lea     rcx, [rsp+240h+hKey]; this
0x18001202d  mov     r9d, 20019h; unsigned int
0x180012033  mov     [rsp+240h+hKey], 0
0x18001203c  mov     r8, r15; lpSubKey
0x18001203f  mov     [rsp+240h+var_1E8], 0
0x180012048  mov     [rsp+240h+var_1E0], 0
0x180012051  mov     dword ptr [rsp+240h+lpData], 0; unsigned int
0x180012059  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18001205e  mov     ebx, eax
0x180012060  test    eax, eax
0x180012062  jz      short loc_180012078
0x180012064  jle     loc_180012117
0x18001206a  movzx   ebx, ax
0x18001206d  or      ebx, 80070000h
0x180012073  jmp     loc_180012117
0x180012078  mov     rcx, [rsp+240h+hKey]; hKey
0x18001207d  lea     r9, [rsp+240h+var_200]; lpcbData
0x180012082  lea     r8, [rbp+140h+sz]; lpData
0x180012086  mov     [rsp+240h+var_200], 140h
0x18001208e  xor     edx, edx; lpSubKey
0x180012090  call    cs:__imp_RegQueryValueW
0x180012096  test    eax, eax
0x180012098  jz      short loc_1800120A8
0x18001209a  jle     short loc_1800120A4
0x18001209c  movzx   eax, ax
0x18001209f  or      eax, 80070000h
0x1800120a4  mov     ebx, eax
0x1800120a6  jmp     short loc_180012117
0x1800120a8  xorps   xmm0, xmm0
0x1800120ab  lea     rdx, [rsp+240h+pclsid]; pclsid
0x1800120b0  lea     rcx, [rbp+140h+sz]; lpsz
0x1800120b4  movups  xmmword ptr [rsp+240h+pclsid.Data1], xmm0
0x1800120b9  call    cs:__imp_CLSIDFromString
0x1800120bf  test    eax, eax
0x1800120c1  jns     short loc_1800120CA
0x1800120c3  mov     ebx, 80004005h
0x1800120c8  jmp     short loc_180012117
0x1800120ca  movzx   ecx, word ptr [rdi]
0x1800120cd  test    ecx, ecx
0x1800120cf  jz      short loc_180012126
0x1800120d1  sub     ecx, 1
0x1800120d4  jz      short loc_180012126
0x1800120d6  sub     ecx, 8
0x1800120d9  jz      short loc_180012133
0x1800120db  cmp     ecx, 4
0x1800120de  jz      short loc_180012133
0x1800120e0  mov     r9d, 9; vt
0x1800120e6  xor     r8d, r8d; wFlags
0x1800120e9  mov     rdx, rdi; pvarSrc
0x1800120ec  mov     rcx, rdi; pvargDest
0x1800120ef  call    cs:__imp_VariantChangeType
0x1800120f5  test    eax, eax
0x1800120f7  jns     short loc_180012133
0x1800120f9  mov     r9d, 0Dh; vt
0x1800120ff  xor     r8d, r8d; wFlags
0x180012102  mov     rdx, rdi; pvarSrc
0x180012105  mov     rcx, rdi; pvargDest
0x180012108  call    cs:__imp_VariantChangeType
0x18001210e  test    eax, eax
0x180012110  jns     short loc_180012133
0x180012112  mov     ebx, 80070057h
0x180012117  lea     rcx, [rsp+240h+hKey]; this
0x18001211c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180012121  jmp     loc_180012006
0x180012126  mov     word ptr [rdi], 9
0x18001212b  mov     qword ptr [rdi+8], 0
0x180012133  mov     rdx, [rdi+8]
0x180012137  lea     rcx, [rsp+240h+var_1F8]
0x18001213c  call    ??0?$CComQIPtr@UIPersistPropertyBag@@$1?_GUID_37d84f60_42cb_11ce_8135_00aa004bb851@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>(IUnknown *)
0x180012141  mov     rcx, [rsp+240h+var_1F8]
0x180012146  mov     rbx, [r14+58h]
0x18001214a  mov     [rsp+240h+var_208], rcx
0x18001214f  test    rcx, rcx
0x180012152  jz      short loc_180012160
0x180012154  mov     rax, [rcx]
0x180012157  mov     rax, [rax+8]
0x18001215b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012160  mov     [rsp+240h+lpcbData], rsi; __int64
0x180012165  lea     rdx, [rsp+240h+pclsid]; rclsid
0x18001216a  mov     r9, rbx
0x18001216d  mov     [rsp+240h+lpData], r15; unsigned __int16 *
0x180012172  mov     r8, rdi
0x180012175  lea     rcx, [rsp+240h+var_208]; ppv
0x18001217a  call    ??$LoadPersistedObject@V?$CComQIPtr@UIPropertyBag@@$1?_GUID_55272a00_42cb_11ce_8135_00aa004bb851@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIPersistPropertyBag@@$1?_GUID_37d84f60_42cb_11ce_8135_00aa004bb851@@3U__s_GUID@@B@2@@@YAJV?$CComQIPtr@UIPersistPropertyBag@@$1?_GUID_37d84f60_42cb_11ce_8135_00aa004bb851@@3U__s_GUID@@B@ATL@@AEAU_GUID@@PEAUtagVARIANT@@PEAUHKEY__@@PEBGPEAUIErrorLog@@@Z; LoadPersistedObject<ATL::CComQIPtr<IPropertyBag,&__s_GUID const _GUID_55272a00_42cb_11ce_8135_00aa004bb851>,ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>>(ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>,_GUID &,tagVARIANT *,HKEY__ *,ushort const *,IErrorLog *)
0x18001217f  mov     ebx, eax
0x180012181  test    eax, eax
0x180012183  jns     short loc_1800121DD
0x180012185  mov     rdx, [rdi+8]
0x180012189  lea     rcx, [rsp+240h+var_208]
0x18001218e  call    ??0?$CComQIPtr@UIPersistPropertyBag2@@$1?_GUID_22f55881_280b_11d0_a8a9_00a0c90c2004@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>(IUnknown *)
0x180012193  mov     rcx, [rsp+240h+var_208]
0x180012198  mov     rbx, [r14+58h]
0x18001219c  mov     [rsp+240h+ppv], rcx
0x1800121a1  test    rcx, rcx
0x1800121a4  jz      short loc_1800121B2
0x1800121a6  mov     rax, [rcx]
0x1800121a9  mov     rax, [rax+8]
0x1800121ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b2  mov     [rsp+240h+lpcbData], rsi; __int64
0x1800121b7  lea     rdx, [rsp+240h+pclsid]; rclsid
0x1800121bc  mov     r9, rbx
0x1800121bf  mov     [rsp+240h+lpData], r15; unsigned __int16 *
0x1800121c4  mov     r8, rdi
0x1800121c7  lea     rcx, [rsp+240h+ppv]; ppv
0x1800121cc  call    ??$LoadPersistedObject@V?$CComQIPtr@UIPropertyBag2@@$1?_GUID_22f55882_280b_11d0_a8a9_00a0c90c2004@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIPersistPropertyBag2@@$1?_GUID_22f55881_280b_11d0_a8a9_00a0c90c2004@@3U__s_GUID@@B@2@@@YAJV?$CComQIPtr@UIPersistPropertyBag2@@$1?_GUID_22f55881_280b_11d0_a8a9_00a0c90c2004@@3U__s_GUID@@B@ATL@@AEAU_GUID@@PEAUtagVARIANT@@PEAUHKEY__@@PEBGPEAUIErrorLog@@@Z; LoadPersistedObject<ATL::CComQIPtr<IPropertyBag2,&__s_GUID const _GUID_22f55882_280b_11d0_a8a9_00a0c90c2004>,ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>>(ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>,_GUID &,tagVARIANT *,HKEY__ *,ushort const *,IErrorLog *)
0x1800121d1  lea     rcx, [rsp+240h+var_208]
0x1800121d6  mov     ebx, eax
0x1800121d8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800121dd  lea     rcx, [rsp+240h+var_1F8]
0x1800121e2  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800121e7  jmp     loc_180012117
0x1800121ec  mov     eax, 80004003h
0x1800121f1  mov     rcx, [rbp+140h+var_40]
0x1800121f8  xor     rcx, rsp; StackCookie
0x1800121fb  call    __security_check_cookie
0x180012200  add     rsp, 218h
0x180012207  pop     r15
0x180012209  pop     r14
0x18001220b  pop     rdi
0x18001220c  pop     rsi
0x18001220d  pop     rbx
0x18001220e  pop     rbp
0x18001220f  retn
```
