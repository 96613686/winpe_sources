# GetShareEngineForMode(SHARE_MODE,int,IShellItemArray *,IShareEngine *,IShellItemArray *,IMultiObjectElevationFactory *,IShareEngine * *,IShareProgressSink *)

- ea: `0x180067e90`
- end: `0x18006810e`
- name: `?GetShareEngineForMode@@YAJW4SHARE_MODE@@HPEAUIShellItemArray@@PEAUIShareEngine@@1PEAUIMultiObjectElevationFactory@@PEAPEAU3@PEAUIShareProgressSink@@@Z`
- size: `638`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180068b38`
- `0x18006e6f4`
- `0x18006ebf0`
- `0x1800719c4`

## callees

- `0x18001a1a4`
- `0x1800254e0`
- `0x180067e90`
- `0x180068878`
- `0x180072f1c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067f43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067f43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800680c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800680c3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180067fa4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180067fa4`

## pseudocode

```c
__int64 __fastcall GetShareEngineForMode(
        int a1,
        int a2,
        void *a3,
        IUnknown *a4,
        struct IShellItemArray *a5,
        struct IMultiObjectElevationFactory *a6,
        IUnknown **ppv,
        __int64 a8)
{
  GUID v11; // xmm0
  int UnaliasedArray; // ebx
  HRESULT v13; // eax
  IUnknown *v14; // rcx
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  struct IShellItemArray *v17; // [rsp+48h] [rbp-38h] BYREF
  __int64 v18; // [rsp+50h] [rbp-30h] BYREF
  struct IShellItemArray *v19; // [rsp+58h] [rbp-28h] BYREF
  IID rclsid; // [rsp+60h] [rbp-20h] BYREF

  pv = a3;
  v11 = CLSID_SmbShareEngine;
  rclsid = CLSID_SmbShareEngine;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v11 = CLSID_InplaceShareEngine;
    }
    else
    {
      if ( a1 != 2 )
        goto LABEL_7;
      v11 = CLSID_LibraryShareEngine;
    }
  }
  rclsid = v11;
LABEL_7:
  if ( a6 )
  {
    UnaliasedArray = (*(__int64 (__fastcall **)(struct IMultiObjectElevationFactory *, IID *, GUID *, IUnknown **))(*(_QWORD *)a6 + 40LL))(
                       a6,
                       &rclsid,
                       &GUID_559b1911_d3af_486e_b8bc_242b24df0114,
                       ppv);
    if ( UnaliasedArray < 0 )
      return (unsigned int)UnaliasedArray;
    if ( a1 != 2 || !a2 )
      goto LABEL_16;
    v13 = CoSetProxyBlanket(*ppv, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  }
  else
  {
    if ( a4 )
    {
      ((void (__fastcall *)(IUnknown *))a4->lpVtbl->AddRef)(a4);
      *ppv = a4;
      return 0;
    }
    v13 = CoCreateInstance(&rclsid, 0, 1u, &GUID_559b1911_d3af_486e_b8bc_242b24df0114, (LPVOID *)ppv);
  }
  UnaliasedArray = v13;
  if ( v13 < 0 )
    return (unsigned int)UnaliasedArray;
LABEL_16:
  v19 = 0;
  UnaliasedArray = _GetUnaliasedArray(a6, (struct IShellItemArray *)pv, &v19);
  if ( UnaliasedArray < 0 )
    goto LABEL_29;
  pv = 0;
  UnaliasedArray = GetCurrentUserStringSid((LPWSTR *)&pv);
  if ( UnaliasedArray >= 0 )
  {
    UnaliasedArray = ((__int64 (__fastcall *)(IUnknown *, LPVOID))(*ppv)->lpVtbl[5].AddRef)(*ppv, pv);
    if ( UnaliasedArray >= 0 )
    {
      if ( !a8
        || (UnaliasedArray = ((__int64 (__fastcall *)(IUnknown *, __int64))(*ppv)->lpVtbl[2].QueryInterface)(*ppv, a8),
            UnaliasedArray >= 0) )
      {
        UnaliasedArray = ((__int64 (__fastcall *)(IUnknown *, struct IShellItemArray *))(*ppv)->lpVtbl[1].AddRef)(
                           *ppv,
                           v19);
        if ( UnaliasedArray >= 0 )
        {
          if ( a5 )
          {
            v14 = *ppv;
            v18 = 0;
            UnaliasedArray = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v14->lpVtbl->QueryInterface)(
                               v14,
                               &GUID_659ad78f_1608_4a89_97d3_c8d741fdd0bc,
                               &v18);
            if ( UnaliasedArray >= 0 )
            {
              v17 = 0;
              UnaliasedArray = _GetUnaliasedArray(a6, a5, &v17);
              if ( UnaliasedArray >= 0 )
              {
                UnaliasedArray = (*(__int64 (__fastcall **)(__int64, struct IShellItemArray *))(*(_QWORD *)v18 + 32LL))(
                                   v18,
                                   v17);
                ((void (__fastcall *)(struct IShellItemArray *))v17->lpVtbl->Release)(v17);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
          }
        }
      }
    }
    CoTaskMemFree(pv);
  }
  ((void (__fastcall *)(struct IShellItemArray *))v19->lpVtbl->Release)(v19);
  if ( UnaliasedArray < 0 )
LABEL_29:
    SafeRelease<IShellItemArray>(ppv);
  return (unsigned int)UnaliasedArray;
}

```

## disassembly

```asm
0x180067e90  mov     [rsp-38h+arg_0], rbx
0x180067e95  push    rbp
0x180067e96  push    rsi
0x180067e97  push    rdi
0x180067e98  push    r12
0x180067e9a  push    r13
0x180067e9c  push    r14
0x180067e9e  push    r15
0x180067ea0  mov     rbp, rsp
0x180067ea3  sub     rsp, 80h
0x180067eaa  mov     rax, cs:__security_cookie
0x180067eb1  xor     rax, rsp
0x180067eb4  mov     [rbp+var_10], rax
0x180067eb8  mov     r15, [rbp+arg_20]
0x180067ebc  mov     r12d, edx
0x180067ebf  mov     rsi, [rbp+arg_28]
0x180067ec3  mov     rbx, r9
0x180067ec6  mov     rdi, [rbp+arg_30]
0x180067eca  mov     r14d, ecx
0x180067ecd  mov     r13, [rbp+arg_38]
0x180067ed1  mov     edx, ecx
0x180067ed3  mov     [rbp+pv], r8
0x180067ed7  movups  xmm0, xmmword ptr cs:CLSID_SmbShareEngine.Data1
0x180067ede  movdqu  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180067ee3  test    ecx, ecx
0x180067ee5  jz      short loc_180067F01
0x180067ee7  sub     edx, 1
0x180067eea  jz      short loc_180067EFA
0x180067eec  cmp     edx, 1
0x180067eef  jnz     short loc_180067F06
0x180067ef1  movups  xmm0, xmmword ptr cs:CLSID_LibraryShareEngine.Data1
0x180067ef8  jmp     short loc_180067F01
0x180067efa  movups  xmm0, xmmword ptr cs:CLSID_InplaceShareEngine.Data1
0x180067f01  movdqu  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180067f06  test    rsi, rsi
0x180067f09  jnz     short loc_180067F4B
0x180067f0b  xor     r14d, r14d
0x180067f0e  test    rbx, rbx
0x180067f11  jz      short loc_180067F2D
0x180067f13  mov     rax, [r9]
0x180067f16  mov     rcx, rbx
0x180067f19  mov     rax, [rax+8]
0x180067f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f22  mov     [rdi], rbx
0x180067f25  mov     ebx, r14d
0x180067f28  jmp     loc_1800680E5
0x180067f2d  xor     edx, edx; pUnkOuter
0x180067f2f  mov     [rsp+80h+ppv], rdi; ppv
0x180067f34  lea     r9, _GUID_559b1911_d3af_486e_b8bc_242b24df0114; riid
0x180067f3b  lea     rcx, [rbp+rclsid]; rclsid
0x180067f3f  lea     r8d, [rdx+1]; dwClsContext
0x180067f43  call    cs:__imp_CoCreateInstance
0x180067f49  jmp     short loc_180067FAA
0x180067f4b  mov     rax, [rsi]
0x180067f4e  lea     r8, _GUID_559b1911_d3af_486e_b8bc_242b24df0114
0x180067f55  mov     r9, rdi
0x180067f58  lea     rdx, [rbp+rclsid]
0x180067f5c  mov     rcx, rsi
0x180067f5f  mov     rax, [rax+28h]
0x180067f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f68  mov     ebx, eax
0x180067f6a  test    eax, eax
0x180067f6c  js      loc_1800680E5
0x180067f72  cmp     r14d, 2
0x180067f76  jnz     short loc_180067FB6
0x180067f78  xor     r14d, r14d
0x180067f7b  test    r12d, r12d
0x180067f7e  jz      short loc_180067FB9
0x180067f80  mov     rcx, [rdi]; pProxy
0x180067f83  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180067f86  mov     [rsp+80h+dwCapabilities], r14d; dwCapabilities
0x180067f8b  mov     r8d, edx; dwAuthzSvc
0x180067f8e  mov     [rsp+80h+pAuthInfo], r14; pAuthInfo
0x180067f93  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180067f97  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x180067f9f  mov     dword ptr [rsp+80h+ppv], r14d; dwAuthnLevel
0x180067fa4  call    cs:__imp_CoSetProxyBlanket
0x180067faa  mov     ebx, eax
0x180067fac  test    eax, eax
0x180067fae  js      loc_1800680E5
0x180067fb4  jmp     short loc_180067FB9
0x180067fb6  xor     r14d, r14d
0x180067fb9  mov     rdx, [rbp+pv]; struct IShellItemArray *
0x180067fbd  lea     r8, [rbp+var_28]; struct IShellItemArray **
0x180067fc1  mov     rcx, rsi; struct IMultiObjectElevationFactory *
0x180067fc4  mov     [rbp+var_28], r14
0x180067fc8  call    ?_GetUnaliasedArray@@YAJPEAUIMultiObjectElevationFactory@@PEAUIShellItemArray@@PEAPEAU2@@Z; _GetUnaliasedArray(IMultiObjectElevationFactory *,IShellItemArray *,IShellItemArray * *)
0x180067fcd  mov     ebx, eax
0x180067fcf  test    eax, eax
0x180067fd1  js      loc_1800680DD
0x180067fd7  lea     rcx, [rbp+pv]; StringSid
0x180067fdb  mov     [rbp+pv], r14
0x180067fdf  call    ?GetCurrentUserStringSid@@YAJPEAPEAG@Z; GetCurrentUserStringSid(ushort * *)
0x180067fe4  mov     ebx, eax
0x180067fe6  test    eax, eax
0x180067fe8  js      loc_1800680C9
0x180067fee  mov     rcx, [rdi]
0x180067ff1  mov     rdx, [rbp+pv]
0x180067ff5  mov     rax, [rcx]
0x180067ff8  mov     rax, [rax+80h]
0x180067fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068004  mov     ebx, eax
0x180068006  test    eax, eax
0x180068008  js      loc_1800680BF
0x18006800e  test    r13, r13
0x180068011  jz      short loc_18006802F
0x180068013  mov     rcx, [rdi]
0x180068016  mov     rdx, r13
0x180068019  mov     rax, [rcx]
0x18006801c  mov     rax, [rax+30h]
0x180068020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068025  mov     ebx, eax
0x180068027  test    eax, eax
0x180068029  js      loc_1800680BF
0x18006802f  mov     rcx, [rdi]
0x180068032  mov     rdx, [rbp+var_28]
0x180068036  mov     rax, [rcx]
0x180068039  mov     rax, [rax+20h]
0x18006803d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068042  mov     ebx, eax
0x180068044  test    eax, eax
0x180068046  js      short loc_1800680BF
0x180068048  test    r15, r15
0x18006804b  jz      short loc_1800680BF
0x18006804d  mov     rcx, [rdi]
0x180068050  lea     r8, [rbp+var_30]
0x180068054  mov     [rbp+var_30], r14
0x180068058  lea     rdx, _GUID_659ad78f_1608_4a89_97d3_c8d741fdd0bc
0x18006805f  mov     rax, [rcx]
0x180068062  mov     rax, [rax]
0x180068065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006806a  mov     ebx, eax
0x18006806c  test    eax, eax
0x18006806e  js      short loc_1800680BF
0x180068070  lea     r8, [rbp+var_38]; struct IShellItemArray **
0x180068074  mov     [rbp+var_38], r14
0x180068078  mov     rdx, r15; struct IShellItemArray *
0x18006807b  mov     rcx, rsi; struct IMultiObjectElevationFactory *
0x18006807e  call    ?_GetUnaliasedArray@@YAJPEAUIMultiObjectElevationFactory@@PEAUIShellItemArray@@PEAPEAU2@@Z; _GetUnaliasedArray(IMultiObjectElevationFactory *,IShellItemArray *,IShellItemArray * *)
0x180068083  mov     ebx, eax
0x180068085  test    eax, eax
0x180068087  js      short loc_1800680AF
0x180068089  mov     rcx, [rbp+var_30]
0x18006808d  mov     rdx, [rbp+var_38]
0x180068091  mov     rax, [rcx]
0x180068094  mov     rax, [rax+20h]
0x180068098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006809d  mov     rcx, [rbp+var_38]
0x1800680a1  mov     ebx, eax
0x1800680a3  mov     rax, [rcx]
0x1800680a6  mov     rax, [rax+10h]
0x1800680aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680af  mov     rcx, [rbp+var_30]
0x1800680b3  mov     rax, [rcx]
0x1800680b6  mov     rax, [rax+10h]
0x1800680ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680bf  mov     rcx, [rbp+pv]; pv
0x1800680c3  call    cs:__imp_CoTaskMemFree
0x1800680c9  mov     rcx, [rbp+var_28]
0x1800680cd  mov     rax, [rcx]
0x1800680d0  mov     rax, [rax+10h]
0x1800680d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680d9  test    ebx, ebx
0x1800680db  jns     short loc_1800680E5
0x1800680dd  mov     rcx, rdi
0x1800680e0  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1800680e5  mov     eax, ebx
0x1800680e7  mov     rcx, [rbp+var_10]
0x1800680eb  xor     rcx, rsp; StackCookie
0x1800680ee  call    __security_check_cookie
0x1800680f3  mov     rbx, [rsp+80h+arg_0]
0x1800680fb  add     rsp, 80h
0x180068102  pop     r15
0x180068104  pop     r14
0x180068106  pop     r13
0x180068108  pop     r12
0x18006810a  pop     rdi
0x18006810b  pop     rsi
0x18006810c  pop     rbp
0x18006810d  retn
```
