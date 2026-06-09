# BDATuningModel::IPersistTuneXmlCollectionImpl<CComponentTypes,IComponentType,256>::IPersistTuneXmlCollection_Load(tagVARIANT)

- ea: `0x18002d040`
- end: `0x18002d375`
- name: `?IPersistTuneXmlCollection_Load@?$IPersistTuneXmlCollectionImpl@VCComponentTypes@@UIComponentType@@$0BAA@@BDATuningModel@@IEAAJUtagVARIANT@@@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e800`

## callees

- `0x180006b38`
- `0x18001424c`
- `0x18002a428`
- `0x18002d040`
- `0x180054410`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002d132`
- `ole32!CoCreateInstance` at `0x18002d132`
- `OLEAUT32!__imp_VariantClear` at `0x18002d232`
- `OLEAUT32!__imp_VariantClear` at `0x18002d25d`
- `OLEAUT32!__imp_VariantClear` at `0x18002d282`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2ad`
- `OLEAUT32!__imp_VariantClear` at `0x18002d310`
- `OLEAUT32!__imp_VariantClear` at `0x18002d355`
- `OLEAUT32!__imp_VariantClear` at `0x18002d232`
- `OLEAUT32!__imp_VariantClear` at `0x18002d25d`
- `OLEAUT32!__imp_VariantClear` at `0x18002d282`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2ad`
- `OLEAUT32!__imp_VariantClear` at `0x18002d310`
- `OLEAUT32!__imp_VariantClear` at `0x18002d355`

## pseudocode

```c
__int64 __fastcall BDATuningModel::IPersistTuneXmlCollectionImpl<CComponentTypes,IComponentType,256>::IPersistTuneXmlCollection_Load(
        __int64 a1,
        VARIANTARG *a2)
{
  HRESULT TuneXmlNodeFromVariant; // ebx
  __int64 v4; // rcx
  __int64 v6; // [rsp+30h] [rbp-39h] BYREF
  struct IXMLDOMNode *v7; // [rsp+38h] [rbp-31h] BYREF
  VARIANTARG v8; // [rsp+40h] [rbp-29h] BYREF
  __int64 v9; // [rsp+58h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG v11; // [rsp+80h] [rbp+17h] BYREF
  int v12; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v13; // [rsp+D8h] [rbp+6Fh] BYREF
  struct IDispatch *v14; // [rsp+E0h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+E8h] [rbp+7Fh] BYREF

  v7 = 0;
  pvarg = *a2;
  TuneXmlNodeFromVariant = GetTuneXmlNodeFromVariant(&pvarg, &v7);
  if ( TuneXmlNodeFromVariant >= 0 )
  {
    if ( !v7 )
    {
LABEL_3:
      TuneXmlNodeFromVariant = -2147418113;
      goto LABEL_33;
    }
    v13 = 0;
    TuneXmlNodeFromVariant = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v7->lpVtbl->get_childNodes)(
                               v7,
                               &v13);
    if ( TuneXmlNodeFromVariant >= 0 )
    {
      if ( !v13 )
      {
LABEL_6:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v13);
        goto LABEL_3;
      }
      v12 = 0;
      TuneXmlNodeFromVariant = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 64LL))(v13, &v12);
      if ( TuneXmlNodeFromVariant >= 0 )
      {
        if ( v12 > 256 )
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v13);
          TuneXmlNodeFromVariant = -2147024883;
          goto LABEL_33;
        }
        ppv = 0;
        TuneXmlNodeFromVariant = CoCreateInstance(
                                   &GUID_e77026b0_b97f_4cbb_b7fb_f4f03ad69f11,
                                   0,
                                   0x17u,
                                   &GUID_990237ae_ac11_4614_be8f_dd217a4cb4cb,
                                   &ppv);
        if ( TuneXmlNodeFromVariant >= 0 )
        {
          while ( 1 )
          {
            v14 = 0;
            TuneXmlNodeFromVariant = (*(__int64 (__fastcall **)(__int64, struct IDispatch **))(*(_QWORD *)v13 + 72LL))(
                                       v13,
                                       &v14);
            if ( TuneXmlNodeFromVariant < 0 || !v14 )
              goto LABEL_30;
            ATL::CComVariant::CComVariant((ATL::CComVariant *)&v8, v14);
            v6 = 0;
            v11 = v8;
            TuneXmlNodeFromVariant = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                                       ppv,
                                       &v11,
                                       &v6);
            if ( TuneXmlNodeFromVariant < 0 )
              goto LABEL_27;
            if ( !v6 )
              break;
            ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>(
              &v9,
              v6);
            if ( !v9 )
            {
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v9);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v6);
              if ( v8.vt == 4095 )
                v8.vt = 8;
              VariantClear(&v8);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v14);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v13);
              TuneXmlNodeFromVariant = -2147467262;
              goto LABEL_33;
            }
            memset(&pvarg, 0, sizeof(pvarg));
            pvarg.vt = 0;
            v4 = a1 - 32;
            if ( !a1 )
              v4 = 48;
            TuneXmlNodeFromVariant = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v4 + 96LL))(
                                       v4,
                                       v9,
                                       &pvarg);
            if ( TuneXmlNodeFromVariant < 0 )
            {
              if ( pvarg.vt == 4095 )
                pvarg.vt = 8;
              VariantClear(&pvarg);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v9);
LABEL_27:
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v6);
              if ( v8.vt == 4095 )
                v8.vt = 8;
              VariantClear(&v8);
LABEL_30:
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v14);
              goto LABEL_31;
            }
            if ( pvarg.vt == 4095 )
              pvarg.vt = 8;
            VariantClear(&pvarg);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v9);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v6);
            if ( v8.vt == 4095 )
              v8.vt = 8;
            VariantClear(&v8);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v14);
          }
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v6);
          if ( v8.vt == 4095 )
            v8.vt = 8;
          VariantClear(&v8);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v14);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
          goto LABEL_6;
        }
LABEL_31:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
      }
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v13);
  }
LABEL_33:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v7);
  return (unsigned int)TuneXmlNodeFromVariant;
}

```

## disassembly

```asm
0x18002d040  push    rbp
0x18002d042  push    rbx
0x18002d043  push    rdi
0x18002d044  push    r14
0x18002d046  push    r15
0x18002d048  lea     rbp, [rsp-37h]
0x18002d04d  sub     rsp, 0A0h
0x18002d054  mov     rdi, rcx
0x18002d057  mov     [rbp+57h+var_88], 0
0x18002d05f  movaps  xmm0, xmmword ptr [rdx]
0x18002d062  movaps  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002d066  movsd   xmm1, qword ptr [rdx+10h]
0x18002d06b  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x18002d070  lea     rdx, [rbp+57h+var_88]; struct IXMLDOMNode **
0x18002d074  lea     rcx, [rbp+57h+pvarg]; struct tagVARIANT
0x18002d078  call    ?GetTuneXmlNodeFromVariant@@YAJUtagVARIANT@@PEAPEAUIXMLDOMNode@@@Z; GetTuneXmlNodeFromVariant(tagVARIANT,IXMLDOMNode * *)
0x18002d07d  mov     ebx, eax
0x18002d07f  test    eax, eax
0x18002d081  js      loc_18002D2D2
0x18002d087  mov     rcx, [rbp+57h+var_88]
0x18002d08b  test    rcx, rcx
0x18002d08e  jnz     short loc_18002D09A
0x18002d090  mov     ebx, 8000FFFFh
0x18002d095  jmp     loc_18002D2D2
0x18002d09a  mov     [rbp+57h+arg_8], 0
0x18002d0a2  mov     rax, [rcx]
0x18002d0a5  lea     rdx, [rbp+57h+arg_8]
0x18002d0a9  mov     rax, [rax+60h]
0x18002d0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b2  mov     ebx, eax
0x18002d0b4  test    eax, eax
0x18002d0b6  js      loc_18002D2C8
0x18002d0bc  mov     rcx, [rbp+57h+arg_8]
0x18002d0c0  test    rcx, rcx
0x18002d0c3  jnz     short loc_18002D0D0
0x18002d0c5  lea     rcx, [rbp+57h+arg_8]
0x18002d0c9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d0ce  jmp     short loc_18002D090
0x18002d0d0  mov     [rbp+57h+arg_0], 0
0x18002d0d7  mov     rax, [rcx]
0x18002d0da  lea     rdx, [rbp+57h+arg_0]
0x18002d0de  mov     rax, [rax+40h]
0x18002d0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0e7  mov     ebx, eax
0x18002d0e9  test    eax, eax
0x18002d0eb  js      loc_18002D2C8
0x18002d0f1  cmp     [rbp+57h+arg_0], 100h
0x18002d0f8  jle     short loc_18002D10D
0x18002d0fa  lea     rcx, [rbp+57h+arg_8]
0x18002d0fe  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d103  mov     ebx, 8007000Dh
0x18002d108  jmp     loc_18002D2D2
0x18002d10d  mov     [rbp+57h+arg_18], 0
0x18002d115  lea     rax, [rbp+57h+arg_18]
0x18002d119  mov     [rsp+0C0h+ppv], rax; ppv
0x18002d11e  lea     r9, _GUID_990237ae_ac11_4614_be8f_dd217a4cb4cb; riid
0x18002d125  xor     edx, edx; pUnkOuter
0x18002d127  lea     r8d, [rdx+17h]; dwClsContext
0x18002d12b  lea     rcx, _GUID_e77026b0_b97f_4cbb_b7fb_f4f03ad69f11; rclsid
0x18002d132  call    cs:__imp_CoCreateInstance
0x18002d138  mov     ebx, eax
0x18002d13a  test    eax, eax
0x18002d13c  js      loc_18002D2BE
0x18002d142  mov     r15d, 0FFFh
0x18002d148  mov     r14d, 8
0x18002d14e  mov     [rbp+57h+arg_10], 0
0x18002d156  mov     rcx, [rbp+57h+arg_8]
0x18002d15a  mov     rax, [rcx]
0x18002d15d  lea     rdx, [rbp+57h+arg_10]
0x18002d161  mov     rax, [rax+48h]
0x18002d165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d16a  mov     ebx, eax
0x18002d16c  test    eax, eax
0x18002d16e  js      loc_18002D2B4
0x18002d174  mov     rdx, [rbp+57h+arg_10]; struct IDispatch *
0x18002d178  test    rdx, rdx
0x18002d17b  jz      loc_18002D2B4
0x18002d181  lea     rcx, [rbp+57h+var_80]; this
0x18002d185  call    ??0CComVariant@ATL@@QEAA@PEAUIDispatch@@@Z; ATL::CComVariant::CComVariant(IDispatch *)
0x18002d18a  nop
0x18002d18b  mov     [rbp+57h+var_90], 0
0x18002d193  mov     rcx, [rbp+57h+arg_18]
0x18002d197  movups  xmm0, xmmword ptr [rbp+57h+var_80]
0x18002d19b  movaps  [rbp+57h+var_40], xmm0
0x18002d19f  movsd   xmm1, qword ptr [rbp+57h+var_80+10h]
0x18002d1a4  movsd   [rbp+57h+var_30], xmm1
0x18002d1a9  mov     rax, [rcx]
0x18002d1ac  lea     r8, [rbp+57h+var_90]
0x18002d1b0  lea     rdx, [rbp+57h+var_40]
0x18002d1b4  mov     rax, [rax+18h]
0x18002d1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1bd  mov     ebx, eax
0x18002d1bf  test    eax, eax
0x18002d1c1  js      loc_18002D293
0x18002d1c7  mov     rdx, [rbp+57h+var_90]
0x18002d1cb  test    rdx, rdx
0x18002d1ce  jz      loc_18002D33B
0x18002d1d4  lea     rcx, [rbp+57h+var_68]
0x18002d1d8  call    ??0?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>(IUnknown *)
0x18002d1dd  nop
0x18002d1de  mov     rdx, [rbp+57h+var_68]
0x18002d1e2  test    rdx, rdx
0x18002d1e5  jz      loc_18002D2EC
0x18002d1eb  xorps   xmm0, xmm0
0x18002d1ee  xor     eax, eax
0x18002d1f0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002d1f4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002d1f8  mov     word ptr [rbp+57h+pvarg], ax
0x18002d1fc  lea     rcx, [rdi-20h]
0x18002d200  mov     eax, 30h ; '0'
0x18002d205  test    rdi, rdi
0x18002d208  cmovz   rcx, rax
0x18002d20c  mov     rax, [rcx]
0x18002d20f  lea     r8, [rbp+57h+pvarg]
0x18002d213  mov     rax, [rax+60h]
0x18002d217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d21c  mov     ebx, eax
0x18002d21e  test    eax, eax
0x18002d220  js      short loc_18002D272
0x18002d222  cmp     word ptr [rbp+57h+pvarg], r15w
0x18002d227  jnz     short loc_18002D22E
0x18002d229  mov     word ptr [rbp+57h+pvarg], r14w
0x18002d22e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002d232  call    cs:__imp_VariantClear
0x18002d238  nop
0x18002d239  lea     rcx, [rbp+57h+var_68]
0x18002d23d  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d242  nop
0x18002d243  lea     rcx, [rbp+57h+var_90]
0x18002d247  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d24c  nop
0x18002d24d  cmp     word ptr [rbp+57h+var_80], r15w
0x18002d252  jnz     short loc_18002D259
0x18002d254  mov     word ptr [rbp+57h+var_80], r14w
0x18002d259  lea     rcx, [rbp+57h+var_80]; pvarg
0x18002d25d  call    cs:__imp_VariantClear
0x18002d263  nop
0x18002d264  lea     rcx, [rbp+57h+arg_10]
0x18002d268  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d26d  jmp     loc_18002D14E
0x18002d272  cmp     word ptr [rbp+57h+pvarg], r15w
0x18002d277  jnz     short loc_18002D27E
0x18002d279  mov     word ptr [rbp+57h+pvarg], r14w
0x18002d27e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002d282  call    cs:__imp_VariantClear
0x18002d288  nop
0x18002d289  lea     rcx, [rbp+57h+var_68]
0x18002d28d  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d292  nop
0x18002d293  lea     rcx, [rbp+57h+var_90]
0x18002d297  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d29c  nop
0x18002d29d  cmp     word ptr [rbp+57h+var_80], r15w
0x18002d2a2  jnz     short loc_18002D2A9
0x18002d2a4  mov     word ptr [rbp+57h+var_80], r14w
0x18002d2a9  lea     rcx, [rbp+57h+var_80]; pvarg
0x18002d2ad  call    cs:__imp_VariantClear
0x18002d2b3  nop
0x18002d2b4  lea     rcx, [rbp+57h+arg_10]
0x18002d2b8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d2bd  nop
0x18002d2be  lea     rcx, [rbp+57h+arg_18]
0x18002d2c2  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d2c7  nop
0x18002d2c8  lea     rcx, [rbp+57h+arg_8]
0x18002d2cc  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d2d1  nop
0x18002d2d2  lea     rcx, [rbp+57h+var_88]
0x18002d2d6  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d2db  mov     eax, ebx
0x18002d2dd  add     rsp, 0A0h
0x18002d2e4  pop     r15
0x18002d2e6  pop     r14
0x18002d2e8  pop     rdi
0x18002d2e9  pop     rbx
0x18002d2ea  pop     rbp
0x18002d2eb  retn
0x18002d2ec  lea     rcx, [rbp+57h+var_68]
0x18002d2f0  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d2f5  nop
0x18002d2f6  lea     rcx, [rbp+57h+var_90]
0x18002d2fa  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d2ff  nop
0x18002d300  cmp     word ptr [rbp+57h+var_80], r15w
0x18002d305  jnz     short loc_18002D30C
0x18002d307  mov     word ptr [rbp+57h+var_80], r14w
0x18002d30c  lea     rcx, [rbp+57h+var_80]; pvarg
0x18002d310  call    cs:__imp_VariantClear
0x18002d316  nop
0x18002d317  lea     rcx, [rbp+57h+arg_10]
0x18002d31b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d320  nop
0x18002d321  lea     rcx, [rbp+57h+arg_18]
0x18002d325  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d32a  nop
0x18002d32b  lea     rcx, [rbp+57h+arg_8]
0x18002d32f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d334  mov     ebx, 80004002h
0x18002d339  jmp     short loc_18002D2D2
0x18002d33b  lea     rcx, [rbp+57h+var_90]
0x18002d33f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d344  nop
0x18002d345  cmp     word ptr [rbp+57h+var_80], r15w
0x18002d34a  jnz     short loc_18002D351
0x18002d34c  mov     word ptr [rbp+57h+var_80], r14w
0x18002d351  lea     rcx, [rbp+57h+var_80]; pvarg
0x18002d355  call    cs:__imp_VariantClear
0x18002d35b  nop
0x18002d35c  lea     rcx, [rbp+57h+arg_10]
0x18002d360  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d365  nop
0x18002d366  lea     rcx, [rbp+57h+arg_18]
0x18002d36a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002d36f  jmp     loc_18002D0C5
```
