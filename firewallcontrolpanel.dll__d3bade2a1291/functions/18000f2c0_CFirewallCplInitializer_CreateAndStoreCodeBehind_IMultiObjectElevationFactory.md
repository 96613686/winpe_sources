# CFirewallCplInitializer::_CreateAndStoreCodeBehind(IMultiObjectElevationFactory *)

- ea: `0x18000f2c0`
- end: `0x18000f432`
- name: `?_CreateAndStoreCodeBehind@CFirewallCplInitializer@@IEAAJPEAUIMultiObjectElevationFactory@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(IUnknown **this, IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f130`

## callees

- `0x180008b30`
- `0x18000906c`
- `0x180009b30`
- `0x18000f2c0`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18000f2f1`
- `SHCORE!IUnknown_QueryService` at `0x18000f2f1`
- `OLEAUT32!__imp_VariantClear` at `0x18000f3fa`
- `OLEAUT32!__imp_VariantClear` at `0x18000f3fa`

## pseudocode

```c
__int64 __fastcall CFirewallCplInitializer::_CreateAndStoreCodeBehind(IUnknown **this, IUnknown *a2)
{
  unsigned __int64 v3; // rdx
  int v4; // edi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  void *v9; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v10; // [rsp+60h] [rbp+18h]

  v9 = 0;
  v4 = IUnknown_QueryService(
         this[2],
         (const GUID *const)&SID_PerNamespaceIDPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &v9);
  if ( v4 >= 0 )
  {
    v5 = DirectUI::HAllocAndZero((DirectUI *)0x60, v3);
    v6 = v5;
    v10 = v5;
    if ( v5 )
    {
      *v5 = &CFirewallCplCore::`vftable'{for `IUnknown'};
      v5[1] = &CFirewallCplCore::`vftable'{for `IFwChangeListener'};
      v5[2] = 0;
      v5[3] = 0;
      v5[4] = 0;
      v5[5] = 0;
      *((_BYTE *)v5 + 48) = 0;
      v5[7] = 0;
      *((_DWORD *)v5 + 16) = 1;
      v5[9] = 0;
      v5[10] = 0;
      v5[11] = 0;
      _InterlockedIncrement(&g_cLocks);
      v4 = CFirewallCplCore::Initialize((CFirewallCplCore *)v5, a2);
      if ( v4 >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 13;
        v4 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, CY *))*v6)(
               v6,
               &GUID_00000000_0000_0000_c000_000000000046,
               &pvarg.cyVal);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(void *, const WCHAR *, VARIANTARG *))(*(_QWORD *)v9 + 32LL))(
                 v9,
                 L"FirewallCplCore",
                 &pvarg);
          VariantClear(&pvarg);
        }
      }
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
    else
    {
      v4 = -2147024882;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f2c0  mov     rax, rsp
0x18000f2c3  mov     [rax+10h], rbx
0x18000f2c7  mov     [rax+20h], rsi
0x18000f2cb  push    rdi
0x18000f2cc  sub     rsp, 40h
0x18000f2d0  mov     rsi, rdx
0x18000f2d3  mov     qword ptr [rax+8], 0
0x18000f2db  lea     r9, [rax+8]; ppvOut
0x18000f2df  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000f2e6  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18000f2ed  mov     rcx, [rcx+10h]; punk
0x18000f2f1  call    cs:__imp_IUnknown_QueryService
0x18000f2f7  mov     edi, eax
0x18000f2f9  test    eax, eax
0x18000f2fb  js      loc_18000F416
0x18000f301  mov     ecx, 60h ; '`'; this
0x18000f306  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000f30b  mov     rbx, rax
0x18000f30e  mov     [rsp+48h+arg_10], rax
0x18000f313  test    rax, rax
0x18000f316  jz      loc_18000F411
0x18000f31c  lea     rax, ??_7CFirewallCplCore@@6BIUnknown@@@; const CFirewallCplCore::`vftable'{for `IUnknown'}
0x18000f323  mov     [rbx], rax
0x18000f326  lea     rax, ??_7CFirewallCplCore@@6BIFwChangeListener@@@; const CFirewallCplCore::`vftable'{for `IFwChangeListener'}
0x18000f32d  mov     [rbx+8], rax
0x18000f331  mov     qword ptr [rbx+10h], 0
0x18000f339  mov     qword ptr [rbx+18h], 0
0x18000f341  mov     qword ptr [rbx+20h], 0
0x18000f349  mov     qword ptr [rbx+28h], 0
0x18000f351  mov     byte ptr [rbx+30h], 0
0x18000f355  mov     qword ptr [rbx+38h], 0
0x18000f35d  mov     dword ptr [rbx+40h], 1
0x18000f364  mov     qword ptr [rbx+48h], 0
0x18000f36c  mov     qword ptr [rbx+50h], 0
0x18000f374  mov     qword ptr [rbx+58h], 0
0x18000f37c  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x18000f383  test    rbx, rbx
0x18000f386  jz      loc_18000F411
0x18000f38c  mov     rdx, rsi; struct IMultiObjectElevationFactory *
0x18000f38f  mov     rcx, rbx; this
0x18000f392  call    ?Initialize@CFirewallCplCore@@QEAAJPEAUIMultiObjectElevationFactory@@@Z; CFirewallCplCore::Initialize(IMultiObjectElevationFactory *)
0x18000f397  mov     edi, eax
0x18000f399  test    eax, eax
0x18000f39b  js      short loc_18000F400
0x18000f39d  xorps   xmm0, xmm0
0x18000f3a0  xor     eax, eax
0x18000f3a2  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x18000f3a7  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18000f3ac  mov     eax, 0Dh
0x18000f3b1  mov     word ptr [rsp+48h+pvarg], ax
0x18000f3b6  mov     rax, [rbx]
0x18000f3b9  lea     r8, [rsp+48h+pvarg+8]
0x18000f3be  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000f3c5  mov     rcx, rbx
0x18000f3c8  mov     rax, [rax]
0x18000f3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d0  mov     edi, eax
0x18000f3d2  test    eax, eax
0x18000f3d4  js      short loc_18000F400
0x18000f3d6  mov     rcx, [rsp+48h+arg_0]
0x18000f3db  mov     rax, [rcx]
0x18000f3de  lea     r8, [rsp+48h+pvarg]
0x18000f3e3  lea     rdx, aFirewallcplcor; "FirewallCplCore"
0x18000f3ea  mov     rax, [rax+20h]
0x18000f3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3f3  mov     edi, eax
0x18000f3f5  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18000f3fa  call    cs:__imp_VariantClear
0x18000f400  mov     rax, [rbx]
0x18000f403  mov     rcx, rbx
0x18000f406  mov     rax, [rax+10h]
0x18000f40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f40f  jmp     short loc_18000F416
0x18000f411  mov     edi, 8007000Eh
0x18000f416  lea     rcx, [rsp+48h+arg_0]
0x18000f41b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f420  mov     eax, edi
0x18000f422  mov     rbx, [rsp+48h+arg_8]
0x18000f427  mov     rsi, [rsp+48h+arg_18]
0x18000f42c  add     rsp, 40h
0x18000f430  pop     rdi
0x18000f431  retn
```
