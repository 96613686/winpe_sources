# COfflineFilesMachineConfiguration::ParseSlowLinkParamsString(ushort const *,ATL::CComVariant &)

- ea: `0x18001dc18`
- end: `0x18001dd9b`
- name: `?ParseSlowLinkParamsString@COfflineFilesMachineConfiguration@@CAJPEBGAEAVCComVariant@ATL@@@Z`
- size: `387`
- prototype: `static int(const unsigned __int16 *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e9b8`

## callees

- `0x1800186c0`
- `0x18001c8c8`
- `0x18001c938`
- `0x18001cb6c`
- `0x18001cbf0`
- `0x18001d74c`
- `0x18001dc18`
- `0x18001de98`
- `0x18001dec8`
- `0x18001e048`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001dcf1`
- `OLEAUT32!__imp_VariantClear` at `0x18001dd25`
- `OLEAUT32!__imp_VariantClear` at `0x18001dcf1`
- `OLEAUT32!__imp_VariantClear` at `0x18001dd25`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::ParseSlowLinkParamsString(
        const unsigned __int16 *a1,
        VARIANTARG *a2)
{
  __int64 v4; // r8
  __int64 v5; // r8
  _WORD *v6; // rbx
  _WORD *v8; // rdi
  HRESULT v9; // esi
  struct tagSAFEARRAY *v10; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h] BYREF
  _WORD *v12; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  int v14; // [rsp+80h] [rbp+30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF

  ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v11);
  v11 = 2;
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v10, &v11);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v15,
    a1);
  v14 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    &v15,
    &v12,
    v4,
    &v14);
  v6 = v12;
  if ( !*v12 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&v10);
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    &v15,
    &v12,
    v5,
    &v14);
  v8 = v12;
  if ( *v12 )
  {
    pvarg.vt = 0;
    ATL::CComVariant::operator=(&pvarg, v6);
    v9 = ATL::CComSafeArray<tagVARIANT,12>::SetAt((__int64)&v10, 0, &pvarg);
    VariantClear(&pvarg);
    if ( v9 >= 0 )
    {
      pvarg.vt = 0;
      ATL::CComVariant::operator=(&pvarg, v8);
      v9 = ATL::CComSafeArray<tagVARIANT,12>::SetAt((__int64)&v10, 1, &pvarg);
      VariantClear(&pvarg);
      if ( v9 >= 0 )
      {
        ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
        ATL::CComVariant::operator=(a2, v10);
        v9 = 0;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
LABEL_9:
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001dc18  mov     [rsp-18h+arg_0], rbx
0x18001dc1d  mov     [rsp-18h+arg_8], rsi
0x18001dc22  push    rbp
0x18001dc23  push    rdi
0x18001dc24  push    r14
0x18001dc26  mov     rbp, rsp
0x18001dc29  sub     rsp, 50h
0x18001dc2d  mov     rbx, rcx
0x18001dc30  mov     r14, rdx
0x18001dc33  lea     rcx, [rbp+var_28]; this
0x18001dc37  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001dc3c  lea     rdx, [rbp+var_28]
0x18001dc40  mov     [rbp+var_28], 2
0x18001dc48  lea     rcx, [rbp+var_30]
0x18001dc4c  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18001dc51  mov     rdx, rbx
0x18001dc54  lea     rcx, [rbp+arg_18]
0x18001dc58  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001dc5d  lea     r9, [rbp+arg_10]
0x18001dc61  mov     [rbp+arg_10], 0
0x18001dc68  lea     rdx, [rbp+var_20]
0x18001dc6c  lea     rcx, [rbp+arg_18]
0x18001dc70  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001dc75  mov     rbx, [rbp+var_20]
0x18001dc79  xor     eax, eax
0x18001dc7b  cmp     [rbx], ax
0x18001dc7e  jnz     short loc_18001DCA9
0x18001dc80  lea     rcx, [rbx-18h]; this
0x18001dc84  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dc89  mov     rcx, [rbp+arg_18]
0x18001dc8d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001dc91  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dc96  lea     rcx, [rbp+var_30]
0x18001dc9a  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001dc9f  mov     eax, 80070057h
0x18001dca4  jmp     loc_18001DD88
0x18001dca9  lea     r9, [rbp+arg_10]
0x18001dcad  lea     rdx, [rbp+var_20]
0x18001dcb1  lea     rcx, [rbp+arg_18]
0x18001dcb5  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001dcba  mov     rdi, [rbp+var_20]
0x18001dcbe  xor     eax, eax
0x18001dcc0  cmp     [rdi], ax
0x18001dcc3  jnz     short loc_18001DCCC
0x18001dcc5  mov     esi, 80070057h
0x18001dcca  jmp     short loc_18001DD2F
0x18001dccc  mov     rdx, rbx
0x18001dccf  mov     word ptr [rbp+pvarg], ax
0x18001dcd3  lea     rcx, [rbp+pvarg]
0x18001dcd7  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001dcdc  lea     r8, [rbp+pvarg]
0x18001dce0  xor     edx, edx
0x18001dce2  lea     rcx, [rbp+var_30]
0x18001dce6  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18001dceb  lea     rcx, [rbp+pvarg]; pvarg
0x18001dcef  mov     esi, eax
0x18001dcf1  call    cs:__imp_VariantClear
0x18001dcf7  test    esi, esi
0x18001dcf9  js      short loc_18001DD2F
0x18001dcfb  xor     eax, eax
0x18001dcfd  lea     rcx, [rbp+pvarg]
0x18001dd01  mov     rdx, rdi
0x18001dd04  mov     word ptr [rbp+pvarg], ax
0x18001dd08  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001dd0d  lea     r8, [rbp+pvarg]
0x18001dd11  mov     edx, 1
0x18001dd16  lea     rcx, [rbp+var_30]
0x18001dd1a  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18001dd1f  lea     rcx, [rbp+pvarg]; pvarg
0x18001dd23  mov     esi, eax
0x18001dd25  call    cs:__imp_VariantClear
0x18001dd2b  test    esi, esi
0x18001dd2d  jns     short loc_18001DD50
0x18001dd2f  lea     rcx, [rdi-18h]; this
0x18001dd33  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dd38  lea     rcx, [rbx-18h]; this
0x18001dd3c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dd41  mov     rcx, [rbp+arg_18]
0x18001dd45  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001dd49  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dd4e  jmp     short loc_18001DD7D
0x18001dd50  lea     rcx, [rdi-18h]; this
0x18001dd54  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dd59  lea     rcx, [rbx-18h]; this
0x18001dd5d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dd62  mov     rcx, [rbp+arg_18]
0x18001dd66  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001dd6a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dd6f  mov     rdx, [rbp+var_30]; struct tagSAFEARRAY *
0x18001dd73  mov     rcx, r14; unsigned __int16 *
0x18001dd76  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::operator=(tagSAFEARRAY const *)
0x18001dd7b  xor     esi, esi
0x18001dd7d  lea     rcx, [rbp+var_30]
0x18001dd81  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001dd86  mov     eax, esi
0x18001dd88  mov     rbx, [rsp+50h+arg_0]
0x18001dd8d  mov     rsi, [rsp+50h+arg_8]
0x18001dd92  add     rsp, 50h
0x18001dd96  pop     r14
0x18001dd98  pop     rdi
0x18001dd99  pop     rbp
0x18001dd9a  retn
```
