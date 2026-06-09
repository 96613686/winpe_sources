# BDATuningModel::IPersistTuneXmlCollectionImpl<CComponents,IComponent,256>::IPersistTuneXmlCollection_Load(tagVARIANT)

- ea: `0x180017380`
- end: `0x1800176b5`
- name: `?IPersistTuneXmlCollection_Load@?$IPersistTuneXmlCollectionImpl@VCComponents@@UIComponent@@$0BAA@@BDATuningModel@@IEAAJUtagVARIANT@@@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180018170`

## callees

- `0x180006b38`
- `0x180013ff8`
- `0x18001424c`
- `0x180017380`
- `0x180054410`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180017472`
- `ole32!CoCreateInstance` at `0x180017472`
- `OLEAUT32!__imp_VariantClear` at `0x180017572`
- `OLEAUT32!__imp_VariantClear` at `0x18001759d`
- `OLEAUT32!__imp_VariantClear` at `0x1800175c2`
- `OLEAUT32!__imp_VariantClear` at `0x1800175ed`
- `OLEAUT32!__imp_VariantClear` at `0x180017650`
- `OLEAUT32!__imp_VariantClear` at `0x180017695`
- `OLEAUT32!__imp_VariantClear` at `0x180017572`
- `OLEAUT32!__imp_VariantClear` at `0x18001759d`
- `OLEAUT32!__imp_VariantClear` at `0x1800175c2`
- `OLEAUT32!__imp_VariantClear` at `0x1800175ed`
- `OLEAUT32!__imp_VariantClear` at `0x180017650`
- `OLEAUT32!__imp_VariantClear` at `0x180017695`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall BDATuningModel::IPersistTuneXmlCollectionImpl<CComponents,IComponent,256>::IPersistTuneXmlCollection_Load(
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
            ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>(
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
            v4 = a1 + 8;
            if ( !a1 )
              v4 = 88;
            TuneXmlNodeFromVariant = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v4 + 88LL))(
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
0x180017380  push    rbp
0x180017382  push    rbx
0x180017383  push    rdi
0x180017384  push    r14
0x180017386  push    r15
0x180017388  lea     rbp, [rsp-37h]
0x18001738d  sub     rsp, 0A0h
0x180017394  mov     rdi, rcx
0x180017397  mov     [rbp+57h+var_88], 0
0x18001739f  movaps  xmm0, xmmword ptr [rdx]
0x1800173a2  movaps  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800173a6  movsd   xmm1, qword ptr [rdx+10h]
0x1800173ab  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x1800173b0  lea     rdx, [rbp+57h+var_88]; struct IXMLDOMNode **
0x1800173b4  lea     rcx, [rbp+57h+pvarg]; struct tagVARIANT
0x1800173b8  call    ?GetTuneXmlNodeFromVariant@@YAJUtagVARIANT@@PEAPEAUIXMLDOMNode@@@Z; GetTuneXmlNodeFromVariant(tagVARIANT,IXMLDOMNode * *)
0x1800173bd  mov     ebx, eax
0x1800173bf  test    eax, eax
0x1800173c1  js      loc_180017612
0x1800173c7  mov     rcx, [rbp+57h+var_88]
0x1800173cb  test    rcx, rcx
0x1800173ce  jnz     short loc_1800173DA
0x1800173d0  mov     ebx, 8000FFFFh
0x1800173d5  jmp     loc_180017612
0x1800173da  mov     [rbp+57h+arg_8], 0
0x1800173e2  mov     rax, [rcx]
0x1800173e5  lea     rdx, [rbp+57h+arg_8]
0x1800173e9  mov     rax, [rax+60h]
0x1800173ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173f2  mov     ebx, eax
0x1800173f4  test    eax, eax
0x1800173f6  js      loc_180017608
0x1800173fc  mov     rcx, [rbp+57h+arg_8]
0x180017400  test    rcx, rcx
0x180017403  jnz     short loc_180017410
0x180017405  lea     rcx, [rbp+57h+arg_8]
0x180017409  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001740e  jmp     short loc_1800173D0
0x180017410  mov     [rbp+57h+arg_0], 0
0x180017417  mov     rax, [rcx]
0x18001741a  lea     rdx, [rbp+57h+arg_0]
0x18001741e  mov     rax, [rax+40h]
0x180017422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017427  mov     ebx, eax
0x180017429  test    eax, eax
0x18001742b  js      loc_180017608
0x180017431  cmp     [rbp+57h+arg_0], 100h
0x180017438  jle     short loc_18001744D
0x18001743a  lea     rcx, [rbp+57h+arg_8]
0x18001743e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017443  mov     ebx, 8007000Dh
0x180017448  jmp     loc_180017612
0x18001744d  mov     [rbp+57h+arg_18], 0
0x180017455  lea     rax, [rbp+57h+arg_18]
0x180017459  mov     [rsp+0C0h+ppv], rax; ppv
0x18001745e  lea     r9, _GUID_990237ae_ac11_4614_be8f_dd217a4cb4cb; riid
0x180017465  xor     edx, edx; pUnkOuter
0x180017467  lea     r8d, [rdx+17h]; dwClsContext
0x18001746b  lea     rcx, _GUID_e77026b0_b97f_4cbb_b7fb_f4f03ad69f11; rclsid
0x180017472  call    cs:__imp_CoCreateInstance
0x180017478  mov     ebx, eax
0x18001747a  test    eax, eax
0x18001747c  js      loc_1800175FE
0x180017482  mov     r15d, 0FFFh
0x180017488  mov     r14d, 8
0x18001748e  mov     [rbp+57h+arg_10], 0
0x180017496  mov     rcx, [rbp+57h+arg_8]
0x18001749a  mov     rax, [rcx]
0x18001749d  lea     rdx, [rbp+57h+arg_10]
0x1800174a1  mov     rax, [rax+48h]
0x1800174a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174aa  mov     ebx, eax
0x1800174ac  test    eax, eax
0x1800174ae  js      loc_1800175F4
0x1800174b4  mov     rdx, [rbp+57h+arg_10]; struct IDispatch *
0x1800174b8  test    rdx, rdx
0x1800174bb  jz      loc_1800175F4
0x1800174c1  lea     rcx, [rbp+57h+var_80]; this
0x1800174c5  call    ??0CComVariant@ATL@@QEAA@PEAUIDispatch@@@Z; ATL::CComVariant::CComVariant(IDispatch *)
0x1800174ca  nop
0x1800174cb  mov     [rbp+57h+var_90], 0
0x1800174d3  mov     rcx, [rbp+57h+arg_18]
0x1800174d7  movups  xmm0, xmmword ptr [rbp+57h+var_80]
0x1800174db  movaps  [rbp+57h+var_40], xmm0
0x1800174df  movsd   xmm1, qword ptr [rbp+57h+var_80+10h]
0x1800174e4  movsd   [rbp+57h+var_30], xmm1
0x1800174e9  mov     rax, [rcx]
0x1800174ec  lea     r8, [rbp+57h+var_90]
0x1800174f0  lea     rdx, [rbp+57h+var_40]
0x1800174f4  mov     rax, [rax+18h]
0x1800174f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174fd  mov     ebx, eax
0x1800174ff  test    eax, eax
0x180017501  js      loc_1800175D3
0x180017507  mov     rdx, [rbp+57h+var_90]
0x18001750b  test    rdx, rdx
0x18001750e  jz      loc_18001767B
0x180017514  lea     rcx, [rbp+57h+var_68]
0x180017518  call    ??0?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>(IUnknown *)
0x18001751d  nop
0x18001751e  mov     rdx, [rbp+57h+var_68]
0x180017522  test    rdx, rdx
0x180017525  jz      loc_18001762C
0x18001752b  xorps   xmm0, xmm0
0x18001752e  xor     eax, eax
0x180017530  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180017534  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180017538  mov     word ptr [rbp+57h+pvarg], ax
0x18001753c  lea     rcx, [rdi+8]
0x180017540  mov     eax, 58h ; 'X'
0x180017545  test    rdi, rdi
0x180017548  cmovz   rcx, rax
0x18001754c  mov     rax, [rcx]
0x18001754f  lea     r8, [rbp+57h+pvarg]
0x180017553  mov     rax, [rax+58h]
0x180017557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001755c  mov     ebx, eax
0x18001755e  test    eax, eax
0x180017560  js      short loc_1800175B2
0x180017562  cmp     word ptr [rbp+57h+pvarg], r15w
0x180017567  jnz     short loc_18001756E
0x180017569  mov     word ptr [rbp+57h+pvarg], r14w
0x18001756e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180017572  call    cs:__imp_VariantClear
0x180017578  nop
0x180017579  lea     rcx, [rbp+57h+var_68]
0x18001757d  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017582  nop
0x180017583  lea     rcx, [rbp+57h+var_90]
0x180017587  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001758c  nop
0x18001758d  cmp     word ptr [rbp+57h+var_80], r15w
0x180017592  jnz     short loc_180017599
0x180017594  mov     word ptr [rbp+57h+var_80], r14w
0x180017599  lea     rcx, [rbp+57h+var_80]; pvarg
0x18001759d  call    cs:__imp_VariantClear
0x1800175a3  nop
0x1800175a4  lea     rcx, [rbp+57h+arg_10]
0x1800175a8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800175ad  jmp     loc_18001748E
0x1800175b2  cmp     word ptr [rbp+57h+pvarg], r15w
0x1800175b7  jnz     short loc_1800175BE
0x1800175b9  mov     word ptr [rbp+57h+pvarg], r14w
0x1800175be  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800175c2  call    cs:__imp_VariantClear
0x1800175c8  nop
0x1800175c9  lea     rcx, [rbp+57h+var_68]
0x1800175cd  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800175d2  nop
0x1800175d3  lea     rcx, [rbp+57h+var_90]
0x1800175d7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800175dc  nop
0x1800175dd  cmp     word ptr [rbp+57h+var_80], r15w
0x1800175e2  jnz     short loc_1800175E9
0x1800175e4  mov     word ptr [rbp+57h+var_80], r14w
0x1800175e9  lea     rcx, [rbp+57h+var_80]; pvarg
0x1800175ed  call    cs:__imp_VariantClear
0x1800175f3  nop
0x1800175f4  lea     rcx, [rbp+57h+arg_10]
0x1800175f8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800175fd  nop
0x1800175fe  lea     rcx, [rbp+57h+arg_18]
0x180017602  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017607  nop
0x180017608  lea     rcx, [rbp+57h+arg_8]
0x18001760c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017611  nop
0x180017612  lea     rcx, [rbp+57h+var_88]
0x180017616  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001761b  mov     eax, ebx
0x18001761d  add     rsp, 0A0h
0x180017624  pop     r15
0x180017626  pop     r14
0x180017628  pop     rdi
0x180017629  pop     rbx
0x18001762a  pop     rbp
0x18001762b  retn
0x18001762c  lea     rcx, [rbp+57h+var_68]
0x180017630  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017635  nop
0x180017636  lea     rcx, [rbp+57h+var_90]
0x18001763a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001763f  nop
0x180017640  cmp     word ptr [rbp+57h+var_80], r15w
0x180017645  jnz     short loc_18001764C
0x180017647  mov     word ptr [rbp+57h+var_80], r14w
0x18001764c  lea     rcx, [rbp+57h+var_80]; pvarg
0x180017650  call    cs:__imp_VariantClear
0x180017656  nop
0x180017657  lea     rcx, [rbp+57h+arg_10]
0x18001765b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017660  nop
0x180017661  lea     rcx, [rbp+57h+arg_18]
0x180017665  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001766a  nop
0x18001766b  lea     rcx, [rbp+57h+arg_8]
0x18001766f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017674  mov     ebx, 80004002h
0x180017679  jmp     short loc_180017612
0x18001767b  lea     rcx, [rbp+57h+var_90]
0x18001767f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180017684  nop
0x180017685  cmp     word ptr [rbp+57h+var_80], r15w
0x18001768a  jnz     short loc_180017691
0x18001768c  mov     word ptr [rbp+57h+var_80], r14w
0x180017691  lea     rcx, [rbp+57h+var_80]; pvarg
0x180017695  call    cs:__imp_VariantClear
0x18001769b  nop
0x18001769c  lea     rcx, [rbp+57h+arg_10]
0x1800176a0  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800176a5  nop
0x1800176a6  lea     rcx, [rbp+57h+arg_18]
0x1800176aa  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800176af  jmp     loc_180017405
```
