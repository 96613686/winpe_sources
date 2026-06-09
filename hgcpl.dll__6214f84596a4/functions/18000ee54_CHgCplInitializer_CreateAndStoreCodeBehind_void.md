# CHgCplInitializer::_CreateAndStoreCodeBehind(void)

- ea: `0x18000ee54`
- end: `0x18000ef6c`
- name: `?_CreateAndStoreCodeBehind@CHgCplInitializer@@IEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CHgCplInitializer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000eca0`

## callees

- `0x18000766c`
- `0x18000b2b0`
- `0x18000eafc`
- `0x18000ee54`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000ee7e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000ee7e`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef39`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef39`

## pseudocode

```c
__int64 __fastcall CHgCplInitializer::_CreateAndStoreCodeBehind(CHgCplInitializer *this)
{
  IUnknown *v1; // rcx
  unsigned __int64 v2; // rdx
  HRESULT v3; // ebx
  CHgCplCore *v4; // rax
  unsigned __int64 v5; // rdx
  CHgCplCore *v6; // rdi
  _QWORD *v7; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+8h] BYREF

  v1 = (IUnknown *)*((_QWORD *)this + 3);
  ppvOut = 0;
  v3 = IUnknown_QueryService(
         v1,
         (const GUID *const)&SID_PerNamespaceIDPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut);
  if ( v3 >= 0 )
  {
    v4 = (CHgCplCore *)DirectUI::HAllocAndZero((DirectUI *)0x58, v2);
    if ( v4 && (v6 = CHgCplCore::CHgCplCore(v4)) != 0 )
    {
      v7 = DirectUI::HAllocAndZero((DirectUI *)0x10, v5);
      if ( v7 )
        v7[1] = 0;
      *((_QWORD *)v6 + 5) = v7;
      if ( v7 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 13;
        v3 = (**(__int64 (__fastcall ***)(CHgCplCore *, GUID *, ULONG *))v6)(
               v6,
               &GUID_00000000_0000_0000_c000_000000000046,
               (ULONG *)&pvarg.cyVal);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(void *, const WCHAR *, VARIANTARG *))(*(_QWORD *)ppvOut + 32LL))(
                 ppvOut,
                 L"HgCplCore",
                 &pvarg);
          VariantClear(&pvarg);
        }
      }
      else
      {
        v3 = -2147024882;
      }
      (*(void (__fastcall **)(CHgCplCore *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ee54  mov     [rsp+arg_8], rbx
0x18000ee59  push    rdi
0x18000ee5a  sub     rsp, 40h
0x18000ee5e  mov     rcx, [rcx+18h]; punk
0x18000ee62  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18000ee67  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000ee6e  mov     [rsp+48h+ppvOut], 0
0x18000ee77  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18000ee7e  call    cs:__imp_IUnknown_QueryService
0x18000ee84  mov     ebx, eax
0x18000ee86  test    eax, eax
0x18000ee88  js      loc_18000EF55
0x18000ee8e  mov     ecx, 58h ; 'X'; this
0x18000ee93  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000ee98  test    rax, rax
0x18000ee9b  jz      loc_18000EF50
0x18000eea1  mov     rcx, rax; this
0x18000eea4  call    ??0CHgCplCore@@QEAA@XZ; CHgCplCore::CHgCplCore(void)
0x18000eea9  mov     rdi, rax
0x18000eeac  test    rax, rax
0x18000eeaf  jz      loc_18000EF50
0x18000eeb5  mov     ecx, 10h; this
0x18000eeba  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000eebf  test    rax, rax
0x18000eec2  jz      short loc_18000EECC
0x18000eec4  mov     qword ptr [rax+8], 0
0x18000eecc  mov     [rdi+28h], rax
0x18000eed0  test    rax, rax
0x18000eed3  jnz     short loc_18000EEDC
0x18000eed5  mov     ebx, 8007000Eh
0x18000eeda  jmp     short loc_18000EF3F
0x18000eedc  xor     eax, eax
0x18000eede  lea     r8, [rsp+48h+pvarg+8]
0x18000eee3  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18000eee8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000eeef  xorps   xmm0, xmm0
0x18000eef2  mov     eax, 0Dh
0x18000eef7  movups  xmmword ptr [rsp+20h], xmm0
0x18000eefc  mov     word ptr [rsp+48h+pvarg], ax
0x18000ef01  mov     rcx, rdi
0x18000ef04  mov     rax, [rdi]
0x18000ef07  mov     rax, [rax]
0x18000ef0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef0f  mov     ebx, eax
0x18000ef11  test    eax, eax
0x18000ef13  js      short loc_18000EF3F
0x18000ef15  mov     rcx, [rsp+48h+ppvOut]
0x18000ef1a  lea     r8, [rsp+48h+pvarg]
0x18000ef1f  lea     rdx, propName; "HgCplCore"
0x18000ef26  mov     rax, [rcx]
0x18000ef29  mov     rax, [rax+20h]
0x18000ef2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef32  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18000ef37  mov     ebx, eax
0x18000ef39  call    cs:__imp_VariantClear
0x18000ef3f  mov     rax, [rdi]
0x18000ef42  mov     rcx, rdi
0x18000ef45  mov     rax, [rax+10h]
0x18000ef49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef4e  jmp     short loc_18000EF55
0x18000ef50  mov     ebx, 8007000Eh
0x18000ef55  lea     rcx, [rsp+48h+ppvOut]
0x18000ef5a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ef5f  mov     eax, ebx
0x18000ef61  mov     rbx, [rsp+48h+arg_8]
0x18000ef66  add     rsp, 40h
0x18000ef6a  pop     rdi
0x18000ef6b  retn
```
