# XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)

- ea: `0x18003aa34`
- end: `0x18003acbe`
- name: `?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z`
- size: `650`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, OLECHAR *, struct IXMLDOMNode **)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033a2c`
- `0x180033ae0`
- `0x18003acfc`
- `0x18003ada8`
- `0x18003bd50`
- `0x18003c2e0`
- `0x18003c52c`

## callees

- `0x1800326fc`
- `0x18003a8b0`
- `0x18003aa34`
- `0x18003ae5c`
- `0x180040010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003ac91`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003aca4`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac91`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003aca4`
- `OLEAUT32!__imp_VariantInit` at `0x18003aa72`
- `OLEAUT32!__imp_VariantInit` at `0x18003aa72`
- `OLEAUT32!__imp_VariantClear` at `0x18003ab4c`
- `OLEAUT32!__imp_VariantClear` at `0x18003ac88`
- `OLEAUT32!__imp_VariantClear` at `0x18003ab4c`
- `OLEAUT32!__imp_VariantClear` at `0x18003ac88`

## pseudocode

```c
__int64 __fastcall XcAddChildElement(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        OLECHAR *psza,
        struct IXMLDOMNode **a6)
{
  OLECHAR *v10; // rdi
  OLECHAR *v11; // rbx
  int v12; // eax
  unsigned int v13; // r14d
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *createNode)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  struct IXMLDOMNode *v20; // [rsp+30h] [rbp-59h] BYREF
  BSTR v21; // [rsp+38h] [rbp-51h] BYREF
  __int64 v22; // [rsp+40h] [rbp-49h] BYREF
  __int64 v23; // [rsp+48h] [rbp-41h] BYREF
  BSTR v24; // [rsp+50h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-29h] BYREF
  VARIANTARG v27; // [rsp+80h] [rbp-9h] BYREF

  v21 = 0;
  v24 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  v23 = 0;
  v20 = 0;
  v22 = 0;
  AtlAssignNoThrow(&v21, psz);
  AtlAssignNoThrow(&v24, a4);
  AtlAssignNoThrow(&bstrString, psza);
  v10 = v24;
  v11 = bstrString;
  if ( !v21 || !v24 || psza && !bstrString )
  {
    v13 = 14;
    goto LABEL_34;
  }
  if ( !bstrString )
    goto LABEL_17;
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int64 *))a1->lpVtbl->createTextNode)(
          a1,
          bstrString,
          &v22);
  v13 = v12;
  if ( v12 >= 0 )
    goto LABEL_17;
  if ( (v12 & 0x1FFF0000) == 0x70000 )
    v13 = (unsigned __int16)v12;
  if ( !v13 )
  {
LABEL_17:
    if ( a2 == (struct IXMLDOMNode *)a1 || (v13 = XcAddWhitespace(a1, a2)) == 0 )
    {
      if ( pvarg.vt != 3 )
      {
        VariantClear(&pvarg);
        pvarg.vt = 3;
      }
      lpVtbl = a1->lpVtbl;
      pvarg.lVal = 1;
      createNode = lpVtbl->createNode;
      v27 = pvarg;
      v16 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, BSTR, OLECHAR *, __int64 *))createNode)(
              a1,
              &v27,
              v21,
              v10,
              &v23);
      v13 = v16;
      if ( v16 >= 0 )
        goto LABEL_18;
      if ( (v16 & 0x1FFF0000) == 0x70000 )
        v13 = (unsigned __int16)v16;
      if ( !v13 )
      {
LABEL_18:
        v17 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))a2->lpVtbl->appendChild)(
                a2,
                v23,
                &v20);
        v13 = v17;
        if ( v17 < 0 )
        {
          if ( (v17 & 0x1FFF0000) == 0x70000 )
            v13 = (unsigned __int16)v17;
          if ( v13 )
            goto LABEL_34;
        }
        else
        {
          v13 = 0;
        }
        if ( !v11 )
        {
LABEL_29:
          if ( a2 == (struct IXMLDOMNode *)a1 || (v13 = XcAddWhitespace(a1, a2)) == 0 )
          {
            if ( a6 )
            {
              *a6 = v20;
              v20 = 0;
            }
          }
          goto LABEL_34;
        }
        v18 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v20->lpVtbl->appendChild)(v20, v22, 0);
        v13 = v18;
        if ( v18 >= 0 )
        {
          v13 = 0;
          goto LABEL_29;
        }
        if ( (v18 & 0x1FFF0000) == 0x70000 )
          v13 = (unsigned __int16)v18;
        if ( !v13 )
          goto LABEL_29;
      }
    }
  }
LABEL_34:
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(&v22);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v20);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(&v23);
  VariantClear(&pvarg);
  SysFreeString(v11);
  SysFreeString(v10);
  SysFreeString(v21);
  return v13;
}

```

## disassembly

```asm
0x18003aa34  push    rbp
0x18003aa36  push    rbx
0x18003aa37  push    rdi
0x18003aa38  push    r12
0x18003aa3a  push    r14
0x18003aa3c  push    r15
0x18003aa3e  lea     rbp, [rsp-1Fh]
0x18003aa43  sub     rsp, 0A8h
0x18003aa4a  mov     r15, rcx
0x18003aa4d  mov     [rbp+47h+var_98], 0
0x18003aa55  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18003aa59  mov     [rbp+47h+var_80], 0
0x18003aa61  mov     rdi, r9
0x18003aa64  mov     [rbp+47h+bstrString], 0
0x18003aa6c  mov     rbx, r8
0x18003aa6f  mov     r12, rdx
0x18003aa72  call    cs:__imp_VariantInit
0x18003aa78  mov     rdx, rbx; psz
0x18003aa7b  mov     [rbp+47h+var_88], 0
0x18003aa83  lea     rcx, [rbp+47h+var_98]; this
0x18003aa87  mov     [rbp+47h+var_A0], 0
0x18003aa8f  mov     [rbp+47h+var_90], 0
0x18003aa97  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18003aa9c  mov     rdx, rdi; psz
0x18003aa9f  lea     rcx, [rbp+47h+var_80]; this
0x18003aaa3  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18003aaa8  mov     r14, [rbp+47h+psz]
0x18003aaac  lea     rcx, [rbp+47h+bstrString]; this
0x18003aab0  mov     rdx, r14; psz
0x18003aab3  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18003aab8  cmp     [rbp+47h+var_98], 0
0x18003aabd  mov     rdi, [rbp+47h+var_80]
0x18003aac1  mov     rbx, [rbp+47h+bstrString]
0x18003aac5  jz      loc_18003AC63
0x18003aacb  test    rdi, rdi
0x18003aace  jz      loc_18003AC63
0x18003aad4  test    r14, r14
0x18003aad7  jz      short loc_18003AAE2
0x18003aad9  test    rbx, rbx
0x18003aadc  jz      loc_18003AC63
0x18003aae2  test    rbx, rbx
0x18003aae5  jz      short loc_18003AB20
0x18003aae7  mov     rax, [r15]
0x18003aaea  lea     r8, [rbp+47h+var_90]
0x18003aaee  mov     rdx, rbx
0x18003aaf1  mov     rcx, r15
0x18003aaf4  mov     rax, [rax+188h]
0x18003aafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab00  mov     r14d, eax
0x18003ab03  test    eax, eax
0x18003ab05  jns     short loc_18003AB20
0x18003ab07  and     eax, 1FFF0000h
0x18003ab0c  cmp     eax, 70000h
0x18003ab11  jnz     short loc_18003AB17
0x18003ab13  movzx   r14d, r14w
0x18003ab17  test    r14d, r14d
0x18003ab1a  jnz     loc_18003AC69
0x18003ab20  cmp     r12, r15
0x18003ab23  jz      short loc_18003AB3B
0x18003ab25  mov     rdx, r12; struct IXMLDOMNode *
0x18003ab28  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18003ab2b  call    ?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)
0x18003ab30  mov     r14d, eax
0x18003ab33  test    eax, eax
0x18003ab35  jnz     loc_18003AC69
0x18003ab3b  mov     r14d, 3
0x18003ab41  cmp     word ptr [rbp+47h+pvarg], r14w
0x18003ab46  jz      short loc_18003AB57
0x18003ab48  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18003ab4c  call    cs:__imp_VariantClear
0x18003ab52  mov     word ptr [rbp+47h+pvarg], r14w
0x18003ab57  mov     rax, [r15]
0x18003ab5a  lea     rcx, [rbp+47h+var_88]
0x18003ab5e  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18003ab63  lea     rdx, [rbp+47h+var_50]
0x18003ab67  mov     r8, [rbp+47h+var_98]
0x18003ab6b  mov     r9, rdi
0x18003ab6e  mov     dword ptr [rbp+47h+pvarg+8], 1
0x18003ab75  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18003ab79  mov     rax, [rax+1C0h]
0x18003ab80  mov     [rsp+0D0h+var_B0], rcx
0x18003ab85  mov     rcx, r15
0x18003ab88  movaps  [rbp+47h+var_50], xmm0
0x18003ab8c  movsd   [rbp+47h+var_40], xmm1
0x18003ab91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab96  mov     r14d, eax
0x18003ab99  test    eax, eax
0x18003ab9b  jns     short loc_18003ABB6
0x18003ab9d  and     eax, 1FFF0000h
0x18003aba2  cmp     eax, 70000h
0x18003aba7  jnz     short loc_18003ABAD
0x18003aba9  movzx   r14d, r14w
0x18003abad  test    r14d, r14d
0x18003abb0  jnz     loc_18003AC69
0x18003abb6  mov     rax, [r12]
0x18003abba  lea     r8, [rbp+47h+var_A0]
0x18003abbe  mov     rdx, [rbp+47h+var_88]
0x18003abc2  mov     rcx, r12
0x18003abc5  mov     rax, [rax+0A8h]
0x18003abcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abd1  mov     r14d, eax
0x18003abd4  test    eax, eax
0x18003abd6  js      short loc_18003ABDD
0x18003abd8  xor     r14d, r14d
0x18003abdb  jmp     short loc_18003ABF2
0x18003abdd  and     eax, 1FFF0000h
0x18003abe2  cmp     eax, 70000h
0x18003abe7  jnz     short loc_18003ABED
0x18003abe9  movzx   r14d, r14w
0x18003abed  test    r14d, r14d
0x18003abf0  jnz     short loc_18003AC69
0x18003abf2  test    rbx, rbx
0x18003abf5  jz      short loc_18003AC32
0x18003abf7  mov     rcx, [rbp+47h+var_A0]
0x18003abfb  xor     r8d, r8d
0x18003abfe  mov     rdx, [rbp+47h+var_90]
0x18003ac02  mov     rax, [rcx]
0x18003ac05  mov     rax, [rax+0A8h]
0x18003ac0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac11  mov     r14d, eax
0x18003ac14  test    eax, eax
0x18003ac16  js      short loc_18003AC1D
0x18003ac18  xor     r14d, r14d
0x18003ac1b  jmp     short loc_18003AC32
0x18003ac1d  and     eax, 1FFF0000h
0x18003ac22  cmp     eax, 70000h
0x18003ac27  jnz     short loc_18003AC2D
0x18003ac29  movzx   r14d, r14w
0x18003ac2d  test    r14d, r14d
0x18003ac30  jnz     short loc_18003AC69
0x18003ac32  cmp     r12, r15
0x18003ac35  jz      short loc_18003AC49
0x18003ac37  mov     rdx, r12; struct IXMLDOMNode *
0x18003ac3a  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18003ac3d  call    ?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)
0x18003ac42  mov     r14d, eax
0x18003ac45  test    eax, eax
0x18003ac47  jnz     short loc_18003AC69
0x18003ac49  mov     rcx, [rbp+47h+arg_28]
0x18003ac4d  test    rcx, rcx
0x18003ac50  jz      short loc_18003AC69
0x18003ac52  mov     rax, [rbp+47h+var_A0]
0x18003ac56  mov     [rcx], rax
0x18003ac59  mov     [rbp+47h+var_A0], 0
0x18003ac61  jmp     short loc_18003AC69
0x18003ac63  mov     r14d, 0Eh
0x18003ac69  lea     rcx, [rbp+47h+var_90]
0x18003ac6d  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003ac72  lea     rcx, [rbp+47h+var_A0]
0x18003ac76  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003ac7b  lea     rcx, [rbp+47h+var_88]
0x18003ac7f  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003ac84  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18003ac88  call    cs:__imp_VariantClear
0x18003ac8e  mov     rcx, rbx; bstrString
0x18003ac91  call    cs:__imp_SysFreeString
0x18003ac97  mov     rcx, rdi; bstrString
0x18003ac9a  call    cs:__imp_SysFreeString
0x18003aca0  mov     rcx, [rbp+47h+var_98]; bstrString
0x18003aca4  call    cs:__imp_SysFreeString
0x18003acaa  mov     eax, r14d
0x18003acad  add     rsp, 0A8h
0x18003acb4  pop     r15
0x18003acb6  pop     r14
0x18003acb8  pop     r12
0x18003acba  pop     rdi
0x18003acbb  pop     rbx
0x18003acbc  pop     rbp
0x18003acbd  retn
```
