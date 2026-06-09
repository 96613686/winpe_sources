# IASGetDictionary

- ea: `0x1800027a0`
- end: `0x1800028eb`
- name: `IASGetDictionary`
- size: `331`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, struct _IASTable *, VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002ba0`

## callees

- `0x180002428`
- `0x180002540`
- `0x180002664`
- `0x1800027a0`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800027b8`
- `OLEAUT32!__imp_VariantInit` at `0x1800027b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800028c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800028c1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000283d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000283d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800027e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800027e5`

## pseudocode

```c
__int64 __fastcall IASGetDictionary(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        struct _IASTable *a4,
        VARIANTARG *pvarg)
{
  HRESULT Instance; // ebx
  IUnknown *v8; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  _QWORD *v10; // rdx
  IUnknown *pProxy; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v13[48]; // [rsp+48h] [rbp-30h] BYREF

  VariantInit(pvarg);
  pProxy = 0;
  Instance = CoCreateInstance(
               &GUID_6bc09692_0ce6_11d1_baae_00c04fc2e20d,
               0,
               0x15u,
               &GUID_f42cfa19_ea06_4eb6_9891_d583f0ce46fc,
               (LPVOID *)&pProxy);
  if ( Instance >= 0 )
  {
    CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x800u);
    v8 = pProxy;
    QueryInterface = pProxy->lpVtbl[1].QueryInterface;
    v10 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v13, a1);
    if ( v10 )
      v10 = (_QWORD *)*v10;
    Instance = ((__int64 (__fastcall *)(IUnknown *, _QWORD *, VARIANTARG *))QueryInterface)(v8, v10, pvarg);
    _bstr_t::~_bstr_t((_bstr_t *)v13);
    if ( Instance >= 0 )
    {
      Instance = ExtractTableFromVariant(pvarg, a4);
      if ( Instance < 0 )
        VariantClear(pvarg);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    }
    else if ( pProxy )
    {
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    }
  }
  else if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800027a0  push    rbx
0x1800027a2  push    rbp
0x1800027a3  push    rsi
0x1800027a4  push    r14
0x1800027a6  sub     rsp, 58h
0x1800027aa  mov     rsi, r9
0x1800027ad  mov     rbp, rcx
0x1800027b0  mov     rcx, [rsp+78h+pvarg]; pvarg
0x1800027b8  call    cs:__imp_VariantInit
0x1800027be  mov     [rsp+78h+pProxy], 0
0x1800027c7  lea     rax, [rsp+78h+pProxy]
0x1800027cc  mov     [rsp+78h+ppv], rax; ppv
0x1800027d1  lea     r9, _GUID_f42cfa19_ea06_4eb6_9891_d583f0ce46fc; riid
0x1800027d8  xor     edx, edx; pUnkOuter
0x1800027da  lea     r8d, [rdx+15h]; dwClsContext
0x1800027de  lea     rcx, _GUID_6bc09692_0ce6_11d1_baae_00c04fc2e20d; rclsid
0x1800027e5  call    cs:__imp_CoCreateInstance
0x1800027eb  mov     ebx, eax
0x1800027ed  test    eax, eax
0x1800027ef  jns     short loc_18000280D
0x1800027f1  mov     rcx, [rsp+78h+pProxy]
0x1800027f6  test    rcx, rcx
0x1800027f9  jz      short loc_180002808
0x1800027fb  mov     rdx, [rcx]
0x1800027fe  mov     rax, [rdx+10h]
0x180002802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002807  nop
0x180002808  jmp     loc_1800028DF
0x18000280d  mov     [rsp+78h+dwCapabilities], 800h; dwCapabilities
0x180002815  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x18000281e  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x180002826  mov     dword ptr [rsp+78h+ppv], 0; dwAuthnLevel
0x18000282e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180002832  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180002835  mov     r8d, edx; dwAuthzSvc
0x180002838  mov     rcx, [rsp+78h+pProxy]; pProxy
0x18000283d  call    cs:__imp_CoSetProxyBlanket
0x180002843  mov     rbx, [rsp+78h+pProxy]
0x180002848  mov     rax, [rbx]
0x18000284b  mov     r14, [rax+18h]
0x18000284f  mov     rdx, rbp; unsigned __int16 *
0x180002852  lea     rcx, [rsp+78h+var_30]; this
0x180002857  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000285c  mov     rdx, [rax]
0x18000285f  test    rdx, rdx
0x180002862  jz      short loc_180002867
0x180002864  mov     rdx, [rdx]
0x180002867  mov     r8, [rsp+78h+pvarg]
0x18000286f  mov     rcx, rbx
0x180002872  mov     rax, r14
0x180002875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000287a  mov     ebx, eax
0x18000287c  lea     rcx, [rsp+78h+var_30]; this
0x180002881  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180002886  test    ebx, ebx
0x180002888  jns     short loc_1800028A3
0x18000288a  mov     rcx, [rsp+78h+pProxy]
0x18000288f  test    rcx, rcx
0x180002892  jz      short loc_1800028A1
0x180002894  mov     rdx, [rcx]
0x180002897  mov     rax, [rdx+10h]
0x18000289b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a0  nop
0x1800028a1  jmp     short loc_1800028DF
0x1800028a3  mov     rdx, rsi; struct _IASTable *
0x1800028a6  mov     rcx, [rsp+78h+pvarg]; struct tagVARIANT *
0x1800028ae  call    ?ExtractTableFromVariant@@YAJPEAUtagVARIANT@@PEAU_IASTable@@@Z; ExtractTableFromVariant(tagVARIANT *,_IASTable *)
0x1800028b3  mov     ebx, eax
0x1800028b5  test    eax, eax
0x1800028b7  jns     short loc_1800028C8
0x1800028b9  mov     rcx, [rsp+78h+pvarg]; pvarg
0x1800028c1  call    cs:__imp_VariantClear
0x1800028c7  nop
0x1800028c8  mov     rcx, [rsp+78h+pProxy]
0x1800028cd  test    rcx, rcx
0x1800028d0  jz      short loc_1800028DF
0x1800028d2  mov     rdx, [rcx]
0x1800028d5  mov     rax, [rdx+10h]
0x1800028d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028de  nop
0x1800028df  mov     eax, ebx
0x1800028e1  add     rsp, 58h
0x1800028e5  pop     r14
0x1800028e7  pop     rsi
0x1800028e8  pop     rbp
0x1800028e9  pop     rbx
0x1800028ea  retn
```
