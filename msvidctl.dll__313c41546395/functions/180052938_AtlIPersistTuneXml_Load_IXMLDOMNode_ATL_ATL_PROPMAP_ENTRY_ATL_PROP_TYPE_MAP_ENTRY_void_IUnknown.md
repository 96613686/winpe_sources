# AtlIPersistTuneXml_Load(IXMLDOMNode *,ATL::ATL_PROPMAP_ENTRY *,ATL_PROP_TYPE_MAP_ENTRY *,void *,IUnknown *)

- ea: `0x180052938`
- end: `0x180052e28`
- name: `?AtlIPersistTuneXml_Load@@YAJPEAUIXMLDOMNode@@PEAUATL_PROPMAP_ENTRY@ATL@@PEAUATL_PROP_TYPE_MAP_ENTRY@@PEAXPEAUIUnknown@@@Z`
- size: `1264`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct ATL::ATL_PROPMAP_ENTRY *, struct ATL_PROP_TYPE_MAP_ENTRY *, void *, struct IUnknown *)`
- caller_count: `30`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800181b0`
- `0x18001b090`
- `0x18001c5a0`
- `0x18001e230`
- `0x18001f960`
- `0x180021220`
- `0x180022b80`
- `0x1800242d0`
- `0x180025900`
- `0x180026dd0`
- `0x1800281e0`
- `0x180029500`
- `0x18002e840`
- `0x18002e8f0`
- `0x18002e9a0`
- `0x18002ea50`
- `0x18002eb00`
- `0x180034f20`
- `0x180034fd0`
- `0x180040820`
- `0x1800408d0`
- `0x180040980`
- `0x180040a30`
- `0x180040ae0`
- `0x180040b90`
- `0x180040c40`
- `0x180040cf0`
- `0x180040da0`
- `0x18004f830`
- `0x180052938`

## callees

- `0x180006b38`
- `0x18001584c`
- `0x180016984`
- `0x1800186a4`
- `0x1800191f0`
- `0x180052670`
- `0x180052938`
- `0x180052e30`
- `0x1800f8010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180052c2c`
- `ole32!CLSIDFromString` at `0x180052c2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180052bc6`
- `OLEAUT32!__imp_SysFreeString` at `0x180052bc6`
- `OLEAUT32!__imp_VariantClear` at `0x180052ad3`
- `OLEAUT32!__imp_VariantClear` at `0x180052d46`
- `OLEAUT32!__imp_VariantClear` at `0x180052d85`
- `OLEAUT32!__imp_VariantClear` at `0x180052daa`
- `OLEAUT32!__imp_VariantClear` at `0x180052dcc`
- `OLEAUT32!__imp_VariantClear` at `0x180052df1`
- `OLEAUT32!__imp_VariantClear` at `0x180052ad3`
- `OLEAUT32!__imp_VariantClear` at `0x180052d46`
- `OLEAUT32!__imp_VariantClear` at `0x180052d85`
- `OLEAUT32!__imp_VariantClear` at `0x180052daa`
- `OLEAUT32!__imp_VariantClear` at `0x180052dcc`
- `OLEAUT32!__imp_VariantClear` at `0x180052df1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180052c08`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180052c08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AtlIPersistTuneXml_Load(
        struct IXMLDOMNode *a1,
        struct ATL::ATL_PROPMAP_ENTRY *a2,
        struct ATL_PROP_TYPE_MAP_ENTRY *a3,
        char *a4,
        struct IUnknown *a5)
{
  struct IXMLDOMNode *v8; // r10
  __int64 v9; // r11
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64); // rax
  _QWORD *v16; // r9
  __int64 v17; // r8
  struct ATL::ATL_PROPMAP_ENTRY *v18; // r14
  __int64 (*v19)(void); // rax
  struct ATL_PROP_TYPE_MAP_ENTRY *v20; // rax
  int v21; // ebx
  __int64 v22; // rbx
  __int64 v23; // rcx
  char v24; // al
  const struct type_info *v25; // r8
  __int64 v26; // r14
  int v27; // eax
  unsigned int v28; // eax
  SAFEARRAY **v29; // rbx
  int (__fastcall ***llVal)(_QWORD, GUID *, SAFEARRAY **); // rcx
  GUID *v31; // rdx
  int Property; // r14d
  VARTYPE vt; // r14
  int v34; // eax
  bool v35; // zf
  int v37; // [rsp+30h] [rbp-38h]
  __int64 v38; // [rsp+38h] [rbp-30h]
  struct IDispatch *v39; // [rsp+40h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF

  v8 = a1;
  if ( a1 && a2 && a3 && a4 && a5 )
  {
    v39 = 0;
    v9 = 0;
    v38 = 0;
    v10 = 0;
    v11 = *(_QWORD *)GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4;
    v12 = *(_QWORD *)&GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1;
    while ( 1 )
    {
      v37 = v10;
      v13 = v10;
      v14 = 6LL * v10;
      v15 = (__int64 (__fastcall *)(__int64))*((_QWORD *)a2 + 6 * v10 + 2);
      if ( !v15 )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v39);
        return 0;
      }
      v16 = (_QWORD *)*((_QWORD *)a2 + v14 + 3);
      if ( v16 )
      {
        v17 = *v16 - v12;
        if ( *v16 == v12 )
          v17 = v16[1] - v11;
        if ( !v17 )
        {
          v18 = (struct ATL::ATL_PROPMAP_ENTRY *)v15(v11);
          if ( !v18 )
            goto LABEL_82;
          v19 = (__int64 (*)(void))*((_QWORD *)a3 + 2 * v13 + 1);
          if ( !v19 )
            goto LABEL_85;
          v20 = (struct ATL_PROP_TYPE_MAP_ENTRY *)v19();
          if ( !v20 )
          {
LABEL_82:
            v21 = -2147418113;
            goto LABEL_96;
          }
          v21 = AtlIPersistTuneXml_Load(a1, v18, v20, &a4[*((_QWORD *)a2 + v14 + 4)], a5);
          if ( v21 < 0 )
            goto LABEL_96;
          goto LABEL_79;
        }
      }
      if ( !*((_QWORD *)a2 + v14) )
        goto LABEL_81;
      v22 = 2 * v13;
      v23 = *((_QWORD *)a3 + v22);
      if ( !v23 )
        break;
      v24 = type_info::operator==(v23, &void `RTTI Type Descriptor');
      v8 = a1;
      v9 = v38;
      if ( !v24 )
        break;
LABEL_80:
      v12 = *(_QWORD *)&GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1;
      v11 = *(_QWORD *)GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4;
LABEL_81:
      v10 = v37 + 1;
    }
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    if ( !*((_DWORD *)a2 + 2 * v14 + 10) )
    {
      if ( *((_QWORD *)a2 + v14 + 3) != v9 )
      {
        ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
          &v39,
          v12);
        Property = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IDispatch **))a5->lpVtbl->QueryInterface)(
                     a5,
                     *((_QWORD *)a2 + v14 + 3),
                     &v39);
        if ( Property < 0 )
          goto LABEL_86;
        v38 = *((_QWORD *)a2 + v14 + 3);
      }
      vt = *((_WORD *)a2 + 4 * v14 + 22);
      if ( !vt )
      {
        Property = ATL::CComDispatchDriver::GetProperty(v39, *((_DWORD *)a2 + 2 * v14 + 2), &pvarg);
        if ( Property < 0 )
        {
LABEL_86:
          if ( pvarg.vt == 4095 )
            pvarg.vt = 8;
          VariantClear(&pvarg);
          v21 = Property;
          goto LABEL_96;
        }
        vt = pvarg.vt;
      }
      ATL::CComVariant::ClearToZero((ATL::CComVariant *)&pvarg);
      pvarg.vt = vt;
      v34 = AtlIPersistTuneXml_Read(
              a1,
              *((const unsigned __int16 **)a2 + v14),
              *((const struct type_info **)a3 + v22),
              &pvarg);
      v21 = v34;
      if ( v34 == 1 )
        goto LABEL_23;
      if ( v34 < 0 )
        goto LABEL_93;
      if ( *((_WORD *)a2 + 4 * v14 + 22) != pvarg.vt )
      {
        v35 = pvarg.vt == 4095;
        goto LABEL_90;
      }
      v21 = ATL::CComDispatchDriver::PutProperty(v39, *((_DWORD *)a2 + 2 * v14 + 2), &pvarg);
      if ( v21 < 0 )
      {
LABEL_93:
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
        goto LABEL_96;
      }
      goto LABEL_76;
    }
    v25 = (const struct type_info *)*((_QWORD *)a3 + v22);
    if ( !v25 )
    {
      VariantClear(&pvarg);
LABEL_85:
      v21 = -2147024785;
LABEL_96:
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v39);
      return (unsigned int)v21;
    }
    v26 = *((_QWORD *)a2 + v14 + 4);
    v27 = AtlIPersistTuneXml_Read(v8, *((const unsigned __int16 **)a2 + v14), v25, &pvarg);
    v21 = v27;
    if ( v27 == 1 )
    {
LABEL_23:
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      goto LABEL_78;
    }
    if ( v27 < 0 )
      goto LABEL_93;
    v28 = *((unsigned __int16 *)a2 + 4 * v14 + 22);
    if ( (_WORD)v28 != pvarg.vt )
    {
      v35 = pvarg.vt == 4095;
LABEL_90:
      if ( v35 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
      v21 = -2147024883;
      goto LABEL_96;
    }
    v29 = (SAFEARRAY **)&a4[v26];
    if ( v28 > 0x11 )
    {
      if ( v28 == 18 )
        goto LABEL_64;
      if ( v28 != 19 && v28 != 22 && v28 != 23 )
      {
        if ( v28 == 72 )
        {
          if ( pvarg.vt != 8 || CLSIDFromString(pvarg.bstrVal, (LPCLSID)&a4[v26]) < 0 )
            *(_OWORD *)v29 = 0;
        }
        else if ( v28 == 8209 )
        {
          if ( *v29 )
            SafeArrayDestroy(*v29);
          *v29 = pvarg.parray;
        }
        goto LABEL_76;
      }
    }
    else
    {
      if ( v28 == 17 )
        goto LABEL_37;
      if ( v28 == 2 )
        goto LABEL_64;
      if ( v28 != 3 )
      {
        if ( v28 == 8 )
        {
          if ( *v29 )
            SysFreeString(&(*v29)->cDims);
          *v29 = pvarg.parray;
          pvarg.llVal = 0;
          goto LABEL_76;
        }
        if ( v28 == 9 )
        {
          if ( *v29 )
            (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&(*v29)->cDims + 16LL))(*v29);
          llVal = (int (__fastcall ***)(_QWORD, GUID *, SAFEARRAY **))pvarg.llVal;
          if ( pvarg.llVal )
          {
            v31 = &GUID_00020400_0000_0000_c000_000000000046;
LABEL_42:
            if ( (**llVal)(llVal, v31, v29) >= 0 )
              goto LABEL_76;
          }
LABEL_43:
          *v29 = 0;
          goto LABEL_76;
        }
        if ( v28 != 11 )
        {
          if ( v28 != 13 )
          {
            if ( v28 == 16 )
LABEL_37:
              *(_BYTE *)v29 = pvarg.bVal;
LABEL_76:
            if ( pvarg.vt == 4095 )
              pvarg.vt = 8;
LABEL_78:
            VariantClear(&pvarg);
LABEL_79:
            v8 = a1;
            v9 = v38;
            goto LABEL_80;
          }
          if ( *v29 )
            (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&(*v29)->cDims + 16LL))(*v29);
          llVal = (int (__fastcall ***)(_QWORD, GUID *, SAFEARRAY **))pvarg.llVal;
          if ( pvarg.llVal )
          {
            v31 = (GUID *)*((_QWORD *)a2 + v14 + 3);
            if ( v31 )
              goto LABEL_42;
          }
          goto LABEL_43;
        }
LABEL_64:
        *(_WORD *)v29 = pvarg.iVal;
        goto LABEL_76;
      }
    }
    *(_DWORD *)v29 = pvarg.lVal;
    goto LABEL_76;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180052938  mov     [rsp-40h+arg_0], rcx
0x18005293d  push    rbp
0x18005293e  push    rbx
0x18005293f  push    rsi
0x180052940  push    rdi
0x180052941  push    r12
0x180052943  push    r13
0x180052945  push    r14
0x180052947  push    r15
0x180052949  mov     rbp, rsp
0x18005294c  sub     rsp, 68h
0x180052950  mov     r13, r9
0x180052953  mov     r15, r8
0x180052956  mov     rsi, rdx
0x180052959  mov     r10, rcx
0x18005295c  xor     r14d, r14d
0x18005295f  test    rcx, rcx
0x180052962  jz      loc_180052E12
0x180052968  test    rdx, rdx
0x18005296b  jz      loc_180052E12
0x180052971  test    r8, r8
0x180052974  jz      loc_180052E12
0x18005297a  test    r9, r9
0x18005297d  jz      loc_180052E12
0x180052983  mov     r12, [rbp+arg_20]
0x180052987  test    r12, r12
0x18005298a  jz      loc_180052E12
0x180052990  mov     [rbp+var_28], r14
0x180052994  mov     r11d, r14d
0x180052997  mov     [rbp+var_30], r14
0x18005299b  mov     eax, r14d
0x18005299e  mov     rcx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4
0x1800529a5  mov     rdx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1
0x1800529ac  mov     [rbp+var_38], eax
0x1800529af  movsxd  rbx, eax
0x1800529b2  lea     rdi, [rbx+rbx*2]
0x1800529b6  add     rdi, rdi
0x1800529b9  mov     rax, [rsi+rdi*8+10h]
0x1800529be  test    rax, rax
0x1800529c1  jz      loc_180052E05
0x1800529c7  mov     r9, [rsi+rdi*8+18h]
0x1800529cc  test    r9, r9
0x1800529cf  jz      short loc_180052A43
0x1800529d1  mov     r8, [r9]
0x1800529d4  sub     r8, rdx
0x1800529d7  jnz     short loc_1800529E0
0x1800529d9  mov     r8, [r9+8]
0x1800529dd  sub     r8, rcx
0x1800529e0  test    r8, r8
0x1800529e3  jnz     short loc_180052A43
0x1800529e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529ea  mov     r14, rax
0x1800529ed  test    rax, rax
0x1800529f0  jz      loc_180052D6C
0x1800529f6  add     rbx, rbx
0x1800529f9  mov     rax, [r15+rbx*8+8]
0x1800529fe  test    rax, rax
0x180052a01  jz      loc_180052D8B
0x180052a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a0c  test    rax, rax
0x180052a0f  jz      loc_180052D6C
0x180052a15  mov     r9, [rsi+rdi*8+20h]
0x180052a1a  add     r9, r13; void *
0x180052a1d  mov     [rsp+68h+var_48], r12; struct IUnknown *
0x180052a22  mov     r8, rax; struct ATL_PROP_TYPE_MAP_ENTRY *
0x180052a25  mov     rdx, r14; struct ATL::ATL_PROPMAP_ENTRY *
0x180052a28  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x180052a2c  call    ?AtlIPersistTuneXml_Load@@YAJPEAUIXMLDOMNode@@PEAUATL_PROPMAP_ENTRY@ATL@@PEAUATL_PROP_TYPE_MAP_ENTRY@@PEAXPEAUIUnknown@@@Z; AtlIPersistTuneXml_Load(IXMLDOMNode *,ATL::ATL_PROPMAP_ENTRY *,ATL_PROP_TYPE_MAP_ENTRY *,void *,IUnknown *)
0x180052a31  mov     ebx, eax
0x180052a33  xor     r14d, r14d
0x180052a36  test    eax, eax
0x180052a38  js      loc_180052DF8
0x180052a3e  jmp     loc_180052D4C
0x180052a43  cmp     [rsi+rdi*8], r14
0x180052a47  jz      loc_180052D62
0x180052a4d  add     rbx, rbx
0x180052a50  mov     rcx, [r15+rbx*8]
0x180052a54  test    rcx, rcx
0x180052a57  jz      short loc_180052A75
0x180052a59  lea     rdx, ??_R0X@8; void `RTTI Type Descriptor'
0x180052a60  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x180052a65  mov     r10, [rbp+arg_0]
0x180052a69  mov     r11, [rbp+var_30]
0x180052a6d  test    al, al
0x180052a6f  jnz     loc_180052D54
0x180052a75  xorps   xmm0, xmm0
0x180052a78  xor     eax, eax
0x180052a7a  movups  xmmword ptr [rbp+pvarg], xmm0
0x180052a7e  mov     qword ptr [rbp+pvarg+10h], rax
0x180052a82  mov     word ptr [rbp+pvarg], r14w
0x180052a87  cmp     [rsi+rdi*8+28h], r14d
0x180052a8c  jz      loc_180052C62
0x180052a92  mov     r8, [r15+rbx*8]; struct type_info *
0x180052a96  test    r8, r8
0x180052a99  jz      loc_180052D81
0x180052a9f  mov     r14, [rsi+rdi*8+20h]
0x180052aa4  lea     r9, [rbp+pvarg]; struct tagVARIANT *
0x180052aa8  mov     rdx, [rsi+rdi*8]; unsigned __int16 *
0x180052aac  mov     rcx, r10; struct IXMLDOMNode *
0x180052aaf  call    ?AtlIPersistTuneXml_Read@@YAJPEAUIXMLDOMNode@@PEBGPEBVtype_info@@PEAUtagVARIANT@@@Z; AtlIPersistTuneXml_Read(IXMLDOMNode *,ushort const *,type_info const *,tagVARIANT *)
0x180052ab4  mov     ebx, eax
0x180052ab6  cmp     eax, 1
0x180052ab9  jnz     short loc_180052AE1
0x180052abb  mov     eax, 0FFFh
0x180052ac0  cmp     word ptr [rbp+pvarg], ax
0x180052ac4  jnz     short loc_180052ACF
0x180052ac6  mov     eax, 8
0x180052acb  mov     word ptr [rbp+pvarg], ax
0x180052acf  lea     rcx, [rbp+pvarg]; pvarg
0x180052ad3  call    cs:__imp_VariantClear
0x180052ad9  xor     r14d, r14d
0x180052adc  jmp     loc_180052D4C
0x180052ae1  test    eax, eax
0x180052ae3  js      loc_180052DD9
0x180052ae9  movzx   eax, word ptr [rsi+rdi*8+2Ch]
0x180052aee  cmp     ax, word ptr [rbp+pvarg]
0x180052af2  jnz     loc_180052D76
0x180052af8  lea     rbx, [r14+r13]
0x180052afc  mov     ecx, eax
0x180052afe  cmp     eax, 11h
0x180052b01  ja      loc_180052BDC
0x180052b07  jz      short loc_180052B40
0x180052b09  sub     ecx, 2
0x180052b0c  jz      loc_180052C53
0x180052b12  sub     ecx, 1
0x180052b15  jz      loc_180052C4C
0x180052b1b  sub     ecx, 5
0x180052b1e  jz      loc_180052BBB
0x180052b24  sub     ecx, 1
0x180052b27  jz      short loc_180052B92
0x180052b29  sub     ecx, 2
0x180052b2c  jz      loc_180052C53
0x180052b32  sub     ecx, 2
0x180052b35  jz      short loc_180052B4A
0x180052b37  cmp     ecx, 3
0x180052b3a  jnz     loc_180052C5A
0x180052b40  mov     al, byte ptr [rbp+pvarg+8]
0x180052b43  mov     [rbx], al
0x180052b45  jmp     loc_180052C5A
0x180052b4a  mov     rcx, [rbx]
0x180052b4d  xor     r14d, r14d
0x180052b50  test    rcx, rcx
0x180052b53  jz      short loc_180052B61
0x180052b55  mov     rax, [rcx]
0x180052b58  mov     rax, [rax+10h]
0x180052b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b61  mov     rcx, qword ptr [rbp+pvarg+8]
0x180052b65  test    rcx, rcx
0x180052b68  jz      short loc_180052B8A
0x180052b6a  mov     rdx, [rsi+rdi*8+18h]
0x180052b6f  test    rdx, rdx
0x180052b72  jz      short loc_180052B8A
0x180052b74  mov     rax, [rcx]
0x180052b77  mov     r8, rbx
0x180052b7a  mov     rax, [rax]
0x180052b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b82  test    eax, eax
0x180052b84  jns     loc_180052D2E
0x180052b8a  mov     [rbx], r14
0x180052b8d  jmp     loc_180052D2E
0x180052b92  mov     rcx, [rbx]
0x180052b95  xor     r14d, r14d
0x180052b98  test    rcx, rcx
0x180052b9b  jz      short loc_180052BA9
0x180052b9d  mov     rax, [rcx]
0x180052ba0  mov     rax, [rax+10h]
0x180052ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ba9  mov     rcx, qword ptr [rbp+pvarg+8]
0x180052bad  test    rcx, rcx
0x180052bb0  jz      short loc_180052B8A
0x180052bb2  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180052bb9  jmp     short loc_180052B74
0x180052bbb  mov     rcx, [rbx]; bstrString
0x180052bbe  xor     r14d, r14d
0x180052bc1  test    rcx, rcx
0x180052bc4  jz      short loc_180052BCC
0x180052bc6  call    cs:__imp_SysFreeString
0x180052bcc  mov     rax, qword ptr [rbp+pvarg+8]
0x180052bd0  mov     [rbx], rax
0x180052bd3  mov     qword ptr [rbp+pvarg+8], r14
0x180052bd7  jmp     loc_180052D2E
0x180052bdc  sub     ecx, 12h
0x180052bdf  jz      short loc_180052C53
0x180052be1  sub     ecx, 1
0x180052be4  jz      short loc_180052C4C
0x180052be6  sub     ecx, 3
0x180052be9  jz      short loc_180052C4C
0x180052beb  sub     ecx, 1
0x180052bee  jz      short loc_180052C4C
0x180052bf0  sub     ecx, 31h ; '1'
0x180052bf3  jz      short loc_180052C1A
0x180052bf5  cmp     ecx, 1FC9h
0x180052bfb  jnz     short loc_180052C5A
0x180052bfd  mov     rcx, [rbx]; psa
0x180052c00  xor     r14d, r14d
0x180052c03  test    rcx, rcx
0x180052c06  jz      short loc_180052C0E
0x180052c08  call    cs:__imp_SafeArrayDestroy
0x180052c0e  mov     rax, qword ptr [rbp+pvarg+8]
0x180052c12  mov     [rbx], rax
0x180052c15  jmp     loc_180052D2E
0x180052c1a  mov     eax, 8
0x180052c1f  cmp     word ptr [rbp+pvarg], ax
0x180052c23  jnz     short loc_180052C3E
0x180052c25  mov     rdx, rbx; pclsid
0x180052c28  mov     rcx, qword ptr [rbp+pvarg+8]; lpsz
0x180052c2c  call    cs:__imp_CLSIDFromString
0x180052c32  xor     r14d, r14d
0x180052c35  test    eax, eax
0x180052c37  js      short loc_180052C41
0x180052c39  jmp     loc_180052D2E
0x180052c3e  xor     r14d, r14d
0x180052c41  xorps   xmm0, xmm0
0x180052c44  movups  xmmword ptr [rbx], xmm0
0x180052c47  jmp     loc_180052D2E
0x180052c4c  mov     eax, dword ptr [rbp+pvarg+8]
0x180052c4f  mov     [rbx], eax
0x180052c51  jmp     short loc_180052C5A
0x180052c53  movzx   eax, word ptr [rbp+pvarg+8]
0x180052c57  mov     [rbx], ax
0x180052c5a  xor     r14d, r14d
0x180052c5d  jmp     loc_180052D2E
0x180052c62  cmp     [rsi+rdi*8+18h], r11
0x180052c67  jz      short loc_180052C9E
0x180052c69  lea     rcx, [rbp+var_28]
0x180052c6d  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x180052c72  mov     rax, [r12]
0x180052c76  lea     r8, [rbp+var_28]
0x180052c7a  mov     rdx, [rsi+rdi*8+18h]
0x180052c7f  mov     rcx, r12
0x180052c82  mov     rax, [rax]
0x180052c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c8a  mov     r14d, eax
0x180052c8d  test    eax, eax
0x180052c8f  js      loc_180052D92
0x180052c95  mov     rax, [rsi+rdi*8+18h]
0x180052c9a  mov     [rbp+var_30], rax
0x180052c9e  movzx   r14d, word ptr [rsi+rdi*8+2Ch]
0x180052ca4  test    r14w, r14w
0x180052ca8  jnz     short loc_180052CCB
0x180052caa  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180052cae  mov     edx, [rsi+rdi*8+8]; int
0x180052cb2  mov     rcx, [rbp+var_28]; struct IDispatch *
0x180052cb6  call    ?GetProperty@CComDispatchDriver@ATL@@SAJPEAUIDispatch@@JPEAUtagVARIANT@@@Z; ATL::CComDispatchDriver::GetProperty(IDispatch *,long,tagVARIANT *)
0x180052cbb  mov     r14d, eax
0x180052cbe  test    eax, eax
0x180052cc0  js      loc_180052D92
0x180052cc6  movzx   r14d, word ptr [rbp+pvarg]
0x180052ccb  lea     rcx, [rbp+pvarg]; this
0x180052ccf  call    ?ClearToZero@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::ClearToZero(void)
0x180052cd4  mov     word ptr [rbp+pvarg], r14w
0x180052cd9  lea     r9, [rbp+pvarg]; struct tagVARIANT *
0x180052cdd  mov     r8, [r15+rbx*8]; struct type_info *
0x180052ce1  mov     rdx, [rsi+rdi*8]; unsigned __int16 *
0x180052ce5  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x180052ce9  call    ?AtlIPersistTuneXml_Read@@YAJPEAUIXMLDOMNode@@PEBGPEBVtype_info@@PEAUtagVARIANT@@@Z; AtlIPersistTuneXml_Read(IXMLDOMNode *,ushort const *,type_info const *,tagVARIANT *)
0x180052cee  mov     ebx, eax
0x180052cf0  cmp     eax, 1
0x180052cf3  jz      loc_180052ABB
0x180052cf9  xor     r14d, r14d
0x180052cfc  test    eax, eax
0x180052cfe  js      loc_180052DD9
0x180052d04  movzx   eax, word ptr [rbp+pvarg]
0x180052d08  cmp     [rsi+rdi*8+2Ch], ax
0x180052d0d  jnz     loc_180052DB5
0x180052d13  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180052d17  mov     edx, [rsi+rdi*8+8]; int
0x180052d1b  mov     rcx, [rbp+var_28]; struct IDispatch *
0x180052d1f  call    ?PutProperty@CComDispatchDriver@ATL@@SAJPEAUIDispatch@@JPEAUtagVARIANT@@@Z; ATL::CComDispatchDriver::PutProperty(IDispatch *,long,tagVARIANT *)
0x180052d24  mov     ebx, eax
0x180052d26  test    eax, eax
0x180052d28  js      loc_180052DD9
0x180052d2e  mov     eax, 0FFFh
0x180052d33  cmp     word ptr [rbp+pvarg], ax
0x180052d37  jnz     short loc_180052D42
0x180052d39  mov     eax, 8
0x180052d3e  mov     word ptr [rbp+pvarg], ax
0x180052d42  lea     rcx, [rbp+pvarg]; pvarg
0x180052d46  call    cs:__imp_VariantClear
0x180052d4c  mov     r10, [rbp+arg_0]
0x180052d50  mov     r11, [rbp+var_30]
0x180052d54  mov     rdx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1
0x180052d5b  mov     rcx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4
0x180052d62  mov     eax, [rbp+var_38]
0x180052d65  inc     eax
0x180052d67  jmp     loc_1800529AC
0x180052d6c  mov     ebx, 8000FFFFh
0x180052d71  jmp     loc_180052DF8
0x180052d76  mov     eax, 0FFFh
0x180052d7b  cmp     word ptr [rbp+pvarg], ax
0x180052d7f  jmp     short loc_180052DBD
0x180052d81  lea     rcx, [rbp+pvarg]; pvarg
0x180052d85  call    cs:__imp_VariantClear
0x180052d8b  mov     ebx, 8007006Fh
0x180052d90  jmp     short loc_180052DF8
0x180052d92  mov     eax, 0FFFh
0x180052d97  cmp     word ptr [rbp+pvarg], ax
0x180052d9b  jnz     short loc_180052DA6
0x180052d9d  mov     eax, 8
0x180052da2  mov     word ptr [rbp+pvarg], ax
  ... truncated ...
```
