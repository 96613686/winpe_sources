# CWebDVDARComp::SetDecoderAudioOutputFormat(ICodecAPI *)

- ea: `0x180073364`
- end: `0x1800738a5`
- name: `?SetDecoderAudioOutputFormat@CWebDVDARComp@@AEAAJPEAUICodecAPI@@@Z`
- size: `1345`
- prototype: `__int64 __fastcall(CWebDVDARComp *__hidden this, struct ICodecAPI *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066c70`

## callees

- `0x180006b38`
- `0x18000eee4`
- `0x180014200`
- `0x180014568`
- `0x18005261c`
- `0x18006f49c`
- `0x180073364`
- `0x1800f8010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180073857`
- `ole32!CoTaskMemFree` at `0x180073857`
- `ole32!CoCreateInstance` at `0x1800733e0`
- `ole32!CoCreateInstance` at `0x1800733e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180073540`
- `OLEAUT32!__imp_SysFreeString` at `0x180073889`
- `OLEAUT32!__imp_SysFreeString` at `0x180073540`
- `OLEAUT32!__imp_SysFreeString` at `0x180073889`
- `OLEAUT32!__imp_VariantClear` at `0x18007358b`
- `OLEAUT32!__imp_VariantClear` at `0x180073609`
- `OLEAUT32!__imp_VariantClear` at `0x180073658`
- `OLEAUT32!__imp_VariantClear` at `0x1800736ae`
- `OLEAUT32!__imp_VariantClear` at `0x1800736f4`
- `OLEAUT32!__imp_VariantClear` at `0x18007373a`
- `OLEAUT32!__imp_VariantClear` at `0x18007377a`
- `OLEAUT32!__imp_VariantClear` at `0x1800737c4`
- `OLEAUT32!__imp_VariantClear` at `0x180073816`
- `OLEAUT32!__imp_VariantClear` at `0x180073848`
- `OLEAUT32!__imp_VariantClear` at `0x18007358b`
- `OLEAUT32!__imp_VariantClear` at `0x180073609`
- `OLEAUT32!__imp_VariantClear` at `0x180073658`
- `OLEAUT32!__imp_VariantClear` at `0x1800736ae`
- `OLEAUT32!__imp_VariantClear` at `0x1800736f4`
- `OLEAUT32!__imp_VariantClear` at `0x18007373a`
- `OLEAUT32!__imp_VariantClear` at `0x18007377a`
- `OLEAUT32!__imp_VariantClear` at `0x1800737c4`
- `OLEAUT32!__imp_VariantClear` at `0x180073816`
- `OLEAUT32!__imp_VariantClear` at `0x180073848`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWebDVDARComp::SetDecoderAudioOutputFormat(CWebDVDARComp *this, struct ICodecAPI *a2)
{
  OLECHAR *v4; // rbx
  HRESULT v5; // edi
  unsigned int v6; // r14d
  CWebDVDARComp *v7; // rcx
  unsigned int v8; // edi
  unsigned int v9; // r15d
  GUID *v10; // rdx
  __int64 v11; // rax
  GUID *v12; // rdx
  VARIANTARG pvarg; // [rsp+40h] [rbp-69h] BYREF
  VARIANTARG v14; // [rsp+58h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-39h] BYREF
  __int64 v16; // [rsp+78h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-29h] BYREF
  __int64 v18; // [rsp+88h] [rbp-21h] BYREF
  __int64 v19; // [rsp+90h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-11h] BYREF
  __int128 v21; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+7h]
  CWebDVDARComp *v23; // [rsp+110h] [rbp+67h] BYREF
  unsigned int v24; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned int v25; // [rsp+120h] [rbp+77h] BYREF
  OLECHAR *v26; // [rsp+128h] [rbp+7Fh] BYREF

  v23 = this;
  if ( !a2 )
    return 2147500034LL;
  v4 = 0;
  v26 = 0;
  ppv = 0;
  v16 = 0;
  v19 = 0;
  v18 = 0;
  pv = 0;
  v21 = 0;
  v22 = 0;
  v5 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         1u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 0, 0, &v16);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 24LL))(
             v16,
             &GUID_1cb9ad4c_dbfa_4c32_b178_c2f568a703b2,
             1,
             0,
             &v19);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v19 + 64LL))(v19, &pv);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 32LL))(v16, 0, &v18);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v18 + 40LL))(
                   v18,
                   &PKEY_AudioEndpoint_FormFactor,
                   &v21);
            if ( v5 >= 0 && (_WORD)v21 == 19 )
            {
              v5 = ((__int64 (__fastcall *)(struct ICodecAPI *, GUID *))a2->lpVtbl->IsSupported)(
                     a2,
                     &GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc);
              if ( v5 >= 0 )
              {
                v6 = *((unsigned __int16 *)pv + 1);
                v7 = (CWebDVDARComp *)DWORD2(v21);
                v8 = (unsigned int)(DWORD2(v21) - 7) <= 2;
                v9 = DWORD2(v21) == 3;
                if ( v6 == 2 )
                {
                  if ( (unsigned int)(DWORD2(v21) - 7) > 2 )
                  {
                    v10 = &GUID_696e1d34_548f_4036_825f_7026c60011bd;
                    if ( DWORD2(v21) != 3 )
                      v10 = &GUID_696e1d30_548f_4036_825f_7026c60011bd;
                  }
                  else
                  {
                    v10 = &GUID_696e1d33_548f_4036_825f_7026c60011bd;
                  }
                  v11 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v10);
                  ATL::CComBSTR::operator=(&v26, v11);
                  SysFreeString(bstrString);
                  pvarg.vt = 0;
                  v4 = v26;
                  ATL::CComVariant::operator=(&pvarg, v26);
                  ((void (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                    a2,
                    &GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc,
                    &pvarg);
                  if ( pvarg.vt == 4095 )
                    pvarg.vt = 8;
                  VariantClear(&pvarg);
                }
                LODWORD(v23) = 0;
                v24 = 0;
                v25 = 0;
                memset(&v14, 0, sizeof(v14));
                v14.vt = 0;
                CWebDVDARComp::GetDecoderParameters(v7, (unsigned int *)&v23, &v24, &v25, v8, v9, v6);
                pvarg.vt = 19;
                pvarg.lVal = (_DWORD)v23 != 0;
                ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                if ( pvarg.vt == 4095 )
                  pvarg.vt = 8;
                VariantClear(&pvarg);
                ((void (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                  a2,
                  &GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27,
                  &v14);
                pvarg.vt = 19;
                pvarg.lVal = v24 != 0;
                ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                if ( pvarg.vt == 4095 )
                  pvarg.vt = 8;
                VariantClear(&pvarg);
                v5 = ((__int64 (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                       a2,
                       &GUID_5612bca1_56da_4582_8da1_ca8090f92768,
                       &v14);
                if ( v25 )
                {
                  if ( v25 != 1 )
                  {
                    if ( v25 != 2 )
                    {
LABEL_43:
                      if ( v14.vt == 4095 )
                        v14.vt = 8;
                      VariantClear(&v14);
                      goto LABEL_46;
                    }
                    pvarg.vt = 19;
                    pvarg.lVal = 2;
                    ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                    if ( pvarg.vt == 4095 )
                      pvarg.vt = 8;
                    VariantClear(&pvarg);
                    v12 = &GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0;
LABEL_42:
                    v5 = ((__int64 (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                           a2,
                           v12,
                           &v14);
                    goto LABEL_43;
                  }
                  pvarg.vt = 19;
                  pvarg.lVal = 1;
                  ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                  if ( pvarg.vt == 4095 )
                    pvarg.vt = 8;
                  VariantClear(&pvarg);
                  ((void (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                    a2,
                    &GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0,
                    &v14);
                  pvarg.vt = 19;
                  pvarg.lVal = 100;
                  ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                  if ( pvarg.vt == 4095 )
                    pvarg.vt = 8;
                  VariantClear(&pvarg);
                  ((void (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                    a2,
                    &GUID_50196c21_1f33_4af5_b296_11426d6c8789,
                    &v14);
                  pvarg.lVal = 100;
                }
                else
                {
                  pvarg.vt = 19;
                  pvarg.lVal = 1;
                  ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                  if ( pvarg.vt == 4095 )
                    pvarg.vt = 8;
                  VariantClear(&pvarg);
                  ((void (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                    a2,
                    &GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0,
                    &v14);
                  pvarg.vt = 19;
                  pvarg.lVal = 0;
                  ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                  if ( pvarg.vt == 4095 )
                    pvarg.vt = 8;
                  VariantClear(&pvarg);
                  ((void (__fastcall *)(struct ICodecAPI *, GUID *, VARIANTARG *))a2->lpVtbl->SetValue)(
                    a2,
                    &GUID_50196c21_1f33_4af5_b296_11426d6c8789,
                    &v14);
                  pvarg.lVal = 0;
                }
                pvarg.vt = 19;
                ATL::CComVariant::InternalCopy((ATL::CComVariant *)&v14, &pvarg);
                if ( pvarg.vt == 4095 )
                  pvarg.vt = 8;
                VariantClear(&pvarg);
                v12 = &GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf;
                goto LABEL_42;
              }
            }
          }
        }
      }
    }
  }
LABEL_46:
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v18);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v19);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v16);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  SysFreeString(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180073364  mov     [rsp-8+arg_0], rcx
0x180073369  push    rbp
0x18007336a  push    rbx
0x18007336b  push    rsi
0x18007336c  push    rdi
0x18007336d  push    r12
0x18007336f  push    r13
0x180073371  push    r14
0x180073373  push    r15
0x180073375  lea     rbp, [rsp-1Fh]
0x18007337a  sub     rsp, 0C8h
0x180073381  mov     rsi, rdx
0x180073384  xor     r12d, r12d
0x180073387  test    rdx, rdx
0x18007338a  jnz     short loc_180073396
0x18007338c  mov     eax, 80004002h
0x180073391  jmp     loc_180073891
0x180073396  mov     rbx, r12
0x180073399  mov     [rbp+57h+arg_18], rbx
0x18007339d  mov     [rbp+57h+var_68], r12
0x1800733a1  mov     [rbp+57h+var_88], r12
0x1800733a5  mov     [rbp+57h+var_70], r12
0x1800733a9  mov     [rbp+57h+var_78], r12
0x1800733ad  mov     [rbp+57h+pv], r12
0x1800733b1  xorps   xmm0, xmm0
0x1800733b4  xor     eax, eax
0x1800733b6  movups  [rbp+57h+var_60], xmm0
0x1800733ba  mov     [rbp+57h+var_50], rax
0x1800733be  lea     rax, [rbp+57h+var_68]
0x1800733c2  mov     [rsp+100h+ppv], rax; ppv
0x1800733c7  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800733ce  mov     r14d, 1
0x1800733d4  mov     r8d, r14d; dwClsContext
0x1800733d7  xor     edx, edx; pUnkOuter
0x1800733d9  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800733e0  call    cs:__imp_CoCreateInstance
0x1800733e6  mov     edi, eax
0x1800733e8  test    eax, eax
0x1800733ea  js      loc_18007384E
0x1800733f0  mov     rcx, [rbp+57h+var_68]
0x1800733f4  mov     rax, [rcx]
0x1800733f7  lea     r9, [rbp+57h+var_88]
0x1800733fb  xor     r8d, r8d
0x1800733fe  xor     edx, edx
0x180073400  mov     rax, [rax+20h]
0x180073404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073409  mov     edi, eax
0x18007340b  test    eax, eax
0x18007340d  js      loc_18007384E
0x180073413  mov     rcx, [rbp+57h+var_88]
0x180073417  mov     rax, [rcx]
0x18007341a  lea     rdx, [rbp+57h+var_70]
0x18007341e  mov     [rsp+100h+ppv], rdx
0x180073423  xor     r9d, r9d
0x180073426  mov     r8d, r14d
0x180073429  lea     rdx, _GUID_1cb9ad4c_dbfa_4c32_b178_c2f568a703b2
0x180073430  mov     rax, [rax+18h]
0x180073434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073439  mov     edi, eax
0x18007343b  test    eax, eax
0x18007343d  js      loc_18007384E
0x180073443  mov     rcx, [rbp+57h+var_70]
0x180073447  mov     rax, [rcx]
0x18007344a  lea     rdx, [rbp+57h+pv]
0x18007344e  mov     rax, [rax+40h]
0x180073452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073457  mov     edi, eax
0x180073459  test    eax, eax
0x18007345b  js      loc_18007384E
0x180073461  mov     rcx, [rbp+57h+var_88]
0x180073465  mov     rax, [rcx]
0x180073468  lea     r8, [rbp+57h+var_78]
0x18007346c  xor     edx, edx
0x18007346e  mov     rax, [rax+20h]
0x180073472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073477  mov     edi, eax
0x180073479  test    eax, eax
0x18007347b  js      loc_18007384E
0x180073481  mov     rcx, [rbp+57h+var_78]
0x180073485  mov     rax, [rcx]
0x180073488  lea     r8, [rbp+57h+var_60]
0x18007348c  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x180073493  mov     rax, [rax+28h]
0x180073497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007349c  mov     edi, eax
0x18007349e  test    eax, eax
0x1800734a0  js      loc_18007384E
0x1800734a6  lea     eax, [r14+12h]
0x1800734aa  cmp     word ptr [rbp+57h+var_60], ax
0x1800734ae  jnz     loc_18007384E
0x1800734b4  mov     rax, [rsi]
0x1800734b7  lea     rdx, _GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc
0x1800734be  mov     rcx, rsi
0x1800734c1  mov     rax, [rax+18h]
0x1800734c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800734ca  mov     edi, eax
0x1800734cc  test    eax, eax
0x1800734ce  js      loc_18007384E
0x1800734d4  mov     rax, [rbp+57h+pv]
0x1800734d8  movzx   r14d, word ptr [rax+2]
0x1800734dd  mov     ecx, dword ptr [rbp+57h+var_60+8]
0x1800734e0  lea     eax, [rcx-7]
0x1800734e3  mov     edi, r12d
0x1800734e6  cmp     eax, 2
0x1800734e9  setbe   dil
0x1800734ed  mov     r15d, r12d
0x1800734f0  cmp     ecx, 3
0x1800734f3  setz    r15b
0x1800734f7  mov     r13d, 8
0x1800734fd  cmp     r14d, 2
0x180073501  jnz     loc_180073591
0x180073507  test    edi, edi
0x180073509  jz      short loc_180073514
0x18007350b  lea     rdx, _GUID_696e1d33_548f_4036_825f_7026c60011bd
0x180073512  jmp     short loc_180073527
0x180073514  cmp     ecx, 3
0x180073517  lea     rdx, _GUID_696e1d34_548f_4036_825f_7026c60011bd
0x18007351e  jz      short loc_180073527
0x180073520  lea     rdx, _GUID_696e1d30_548f_4036_825f_7026c60011bd; struct _GUID *
0x180073527  lea     rcx, [rbp+57h+bstrString]; this
0x18007352b  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180073530  mov     rdx, rax
0x180073533  lea     rcx, [rbp+57h+arg_18]
0x180073537  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18007353c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180073540  call    cs:__imp_SysFreeString
0x180073546  mov     word ptr [rbp+57h+pvarg], r12w
0x18007354b  mov     rbx, [rbp+57h+arg_18]
0x18007354f  mov     rdx, rbx
0x180073552  lea     rcx, [rbp+57h+pvarg]
0x180073556  call    ??4CComVariant@ATL@@QEAAAEAV01@PEAG@Z; ATL::CComVariant::operator=(ushort *)
0x18007355b  nop
0x18007355c  mov     rax, [rsi]
0x18007355f  lea     r8, [rbp+57h+pvarg]
0x180073563  lea     rdx, _GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc
0x18007356a  mov     rcx, rsi
0x18007356d  mov     rax, [rax+48h]
0x180073571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073576  nop
0x180073577  mov     eax, 0FFFh
0x18007357c  cmp     word ptr [rbp+57h+pvarg], ax
0x180073580  jnz     short loc_180073587
0x180073582  mov     word ptr [rbp+57h+pvarg], r13w
0x180073587  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007358b  call    cs:__imp_VariantClear
0x180073591  mov     dword ptr [rbp+57h+arg_0], r12d
0x180073595  mov     [rbp+57h+arg_8], r12d
0x180073599  mov     [rbp+57h+arg_10], r12d
0x18007359d  xorps   xmm0, xmm0
0x1800735a0  xor     eax, eax
0x1800735a2  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800735a6  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x1800735aa  mov     word ptr [rbp+57h+var_A8], r12w
0x1800735af  mov     [rsp+100h+var_D0], r14d; unsigned int
0x1800735b4  mov     [rsp+100h+var_D8], r15d; unsigned int
0x1800735b9  mov     dword ptr [rsp+100h+ppv], edi; unsigned int
0x1800735bd  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x1800735c1  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x1800735c5  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x1800735c9  call    ?GetDecoderParameters@CWebDVDARComp@@AEAAXAEAK00KKK@Z; CWebDVDARComp::GetDecoderParameters(ulong &,ulong &,ulong &,ulong,ulong,ulong)
0x1800735ce  mov     eax, r12d
0x1800735d1  cmp     dword ptr [rbp+57h+arg_0], r12d
0x1800735d5  setnz   al
0x1800735d8  mov     r14d, 13h
0x1800735de  mov     word ptr [rbp+57h+pvarg], r14w
0x1800735e3  mov     dword ptr [rbp+57h+pvarg+8], eax
0x1800735e6  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x1800735ea  lea     rcx, [rbp+57h+var_A8]; this
0x1800735ee  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800735f3  mov     r15d, 0FFFh
0x1800735f9  cmp     word ptr [rbp+57h+pvarg], r15w
0x1800735fe  jnz     short loc_180073605
0x180073600  mov     word ptr [rbp+57h+pvarg], r13w
0x180073605  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073609  call    cs:__imp_VariantClear
0x18007360f  mov     rax, [rsi]
0x180073612  lea     r8, [rbp+57h+var_A8]
0x180073616  lea     rdx, _GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27
0x18007361d  mov     rcx, rsi
0x180073620  mov     rax, [rax+48h]
0x180073624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073629  mov     eax, r12d
0x18007362c  cmp     [rbp+57h+arg_8], r12d
0x180073630  setnz   al
0x180073633  mov     word ptr [rbp+57h+pvarg], r14w
0x180073638  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18007363b  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18007363f  lea     rcx, [rbp+57h+var_A8]; this
0x180073643  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180073648  cmp     word ptr [rbp+57h+pvarg], r15w
0x18007364d  jnz     short loc_180073654
0x18007364f  mov     word ptr [rbp+57h+pvarg], r13w
0x180073654  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073658  call    cs:__imp_VariantClear
0x18007365e  mov     rax, [rsi]
0x180073661  lea     r8, [rbp+57h+var_A8]
0x180073665  lea     rdx, _GUID_5612bca1_56da_4582_8da1_ca8090f92768
0x18007366c  mov     rcx, rsi
0x18007366f  mov     rax, [rax+48h]
0x180073673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073678  mov     edi, eax
0x18007367a  mov     eax, [rbp+57h+arg_10]
0x18007367d  test    eax, eax
0x18007367f  jnz     loc_18007374C
0x180073685  mov     word ptr [rbp+57h+pvarg], r14w
0x18007368a  mov     dword ptr [rbp+57h+pvarg+8], 1
0x180073691  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180073695  lea     rcx, [rbp+57h+var_A8]; this
0x180073699  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18007369e  cmp     word ptr [rbp+57h+pvarg], r15w
0x1800736a3  jnz     short loc_1800736AA
0x1800736a5  mov     word ptr [rbp+57h+pvarg], r13w
0x1800736aa  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800736ae  call    cs:__imp_VariantClear
0x1800736b4  mov     rax, [rsi]
0x1800736b7  lea     r8, [rbp+57h+var_A8]
0x1800736bb  lea     rdx, _GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0
0x1800736c2  mov     rcx, rsi
0x1800736c5  mov     rax, [rax+48h]
0x1800736c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800736ce  mov     word ptr [rbp+57h+pvarg], r14w
0x1800736d3  mov     dword ptr [rbp+57h+pvarg+8], r12d
0x1800736d7  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x1800736db  lea     rcx, [rbp+57h+var_A8]; this
0x1800736df  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800736e4  cmp     word ptr [rbp+57h+pvarg], r15w
0x1800736e9  jnz     short loc_1800736F0
0x1800736eb  mov     word ptr [rbp+57h+pvarg], r13w
0x1800736f0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800736f4  call    cs:__imp_VariantClear
0x1800736fa  mov     rax, [rsi]
0x1800736fd  lea     r8, [rbp+57h+var_A8]
0x180073701  lea     rdx, _GUID_50196c21_1f33_4af5_b296_11426d6c8789
0x180073708  mov     rcx, rsi
0x18007370b  mov     rax, [rax+48h]
0x18007370f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073714  mov     dword ptr [rbp+57h+pvarg+8], r12d
0x180073718  mov     word ptr [rbp+57h+pvarg], r14w
0x18007371d  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180073721  lea     rcx, [rbp+57h+var_A8]; this
0x180073725  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18007372a  cmp     word ptr [rbp+57h+pvarg], r15w
0x18007372f  jnz     short loc_180073736
0x180073731  mov     word ptr [rbp+57h+pvarg], r13w
0x180073736  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007373a  call    cs:__imp_VariantClear
0x180073740  lea     rdx, _GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf
0x180073747  jmp     loc_180073823
0x18007374c  cmp     eax, 1
0x18007374f  jnz     loc_1800737EC
0x180073755  mov     word ptr [rbp+57h+pvarg], r14w
0x18007375a  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18007375d  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180073761  lea     rcx, [rbp+57h+var_A8]; this
0x180073765  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18007376a  cmp     word ptr [rbp+57h+pvarg], r15w
0x18007376f  jnz     short loc_180073776
0x180073771  mov     word ptr [rbp+57h+pvarg], r13w
0x180073776  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007377a  call    cs:__imp_VariantClear
0x180073780  mov     rax, [rsi]
0x180073783  lea     r8, [rbp+57h+var_A8]
0x180073787  lea     rdx, _GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0
0x18007378e  mov     rcx, rsi
0x180073791  mov     rax, [rax+48h]
0x180073795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007379a  mov     word ptr [rbp+57h+pvarg], r14w
0x18007379f  mov     edi, 64h ; 'd'
0x1800737a4  mov     dword ptr [rbp+57h+pvarg+8], edi
0x1800737a7  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x1800737ab  lea     rcx, [rbp+57h+var_A8]; this
0x1800737af  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800737b4  cmp     word ptr [rbp+57h+pvarg], r15w
0x1800737b9  jnz     short loc_1800737C0
0x1800737bb  mov     word ptr [rbp+57h+pvarg], r13w
0x1800737c0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800737c4  call    cs:__imp_VariantClear
0x1800737ca  mov     rax, [rsi]
0x1800737cd  lea     r8, [rbp+57h+var_A8]
0x1800737d1  lea     rdx, _GUID_50196c21_1f33_4af5_b296_11426d6c8789
0x1800737d8  mov     rcx, rsi
0x1800737db  mov     rax, [rax+48h]
0x1800737df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737e4  mov     dword ptr [rbp+57h+pvarg+8], edi
0x1800737e7  jmp     loc_180073718
0x1800737ec  cmp     eax, 2
0x1800737ef  jnz     short loc_180073838
0x1800737f1  mov     word ptr [rbp+57h+pvarg], r14w
0x1800737f6  mov     dword ptr [rbp+57h+pvarg+8], eax
0x1800737f9  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x1800737fd  lea     rcx, [rbp+57h+var_A8]; this
0x180073801  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180073806  cmp     word ptr [rbp+57h+pvarg], r15w
0x18007380b  jnz     short loc_180073812
0x18007380d  mov     word ptr [rbp+57h+pvarg], r13w
0x180073812  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073816  call    cs:__imp_VariantClear
0x18007381c  lea     rdx, _GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0
0x180073823  mov     rax, [rsi]
0x180073826  lea     r8, [rbp+57h+var_A8]
  ... truncated ...
```
