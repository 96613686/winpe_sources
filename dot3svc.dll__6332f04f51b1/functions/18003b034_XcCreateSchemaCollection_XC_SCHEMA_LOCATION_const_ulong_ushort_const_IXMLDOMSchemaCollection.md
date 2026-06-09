# XcCreateSchemaCollection(_XC_SCHEMA_LOCATION const *,ulong,ushort const *,IXMLDOMSchemaCollection * *)

- ea: `0x18003b034`
- end: `0x18003b24c`
- name: `?XcCreateSchemaCollection@@YAKPEBU_XC_SCHEMA_LOCATION@@KPEBGPEAPEAUIXMLDOMSchemaCollection@@@Z`
- size: `536`
- prototype: `unsigned int(const struct _XC_SCHEMA_LOCATION *, unsigned int, const unsigned __int16 *, struct IXMLDOMSchemaCollection **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032778`

## callees

- `0x1800025f0`
- `0x180008c38`
- `0x1800326fc`
- `0x18003a8b0`
- `0x18003a8f4`
- `0x18003b034`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b0eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b0eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b205`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b205`
- `OLEAUT32!__imp_VariantInit` at `0x18003b077`
- `OLEAUT32!__imp_VariantInit` at `0x18003b077`
- `OLEAUT32!__imp_VariantClear` at `0x18003b210`
- `OLEAUT32!__imp_VariantClear` at `0x18003b210`

## pseudocode

```c
__int64 __fastcall XcCreateSchemaCollection(const struct _XC_SCHEMA_LOCATION *a1, __int64 a2, size_t *a3, LPVOID *a4)
{
  OLECHAR *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rsi
  HRESULT v10; // eax
  unsigned int i; // r14d
  int v12; // eax
  __int64 v13; // r11
  __int64 v14; // rax
  int v15; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v18; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v20; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR psz[264]; // [rsp+80h] [rbp-80h] BYREF

  ppv = 0;
  VariantInit(&pvarg);
  v6 = 0;
  v18 = 0;
  v7 = StringCchCopyW(psz, 0x104u, a3);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_5;
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v7;
  if ( !v8 )
  {
LABEL_5:
    v9 = -1;
    do
      ++v9;
    while ( psz[v9] );
    v10 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection, &ppv);
    v8 = v10;
    if ( v10 < 0 )
    {
      if ( (v10 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v10;
      if ( v8 )
        goto LABEL_29;
    }
    else
    {
      v8 = 0;
    }
    for ( i = 0; i < 3; ++i )
    {
      v12 = StringCchCopyW(&psz[v9], 260 - v9, (size_t *)off_180052110[2 * i + 1]);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( (v12 & 0x1FFF0000) == 0x70000 )
          v8 = (unsigned __int16)v12;
        if ( v8 )
          goto LABEL_29;
      }
      AtlAssignNoThrow(&v18, off_180052110[v13]);
      AtlAssignNoThrow((struct ATL::CComVariant *)&pvarg, psz);
      v6 = v18;
      if ( !v18 || pvarg.vt != 8 || !pvarg.llVal )
      {
        v8 = 8;
        goto LABEL_29;
      }
      v14 = *(_QWORD *)ppv;
      v20 = pvarg;
      v15 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *))(v14 + 56))(ppv, v18, &v20);
      v8 = v15;
      if ( v15 < 0 )
      {
        if ( (v15 & 0x1FFF0000) == 0x70000 )
          v8 = (unsigned __int16)v15;
        if ( v8 )
          goto LABEL_29;
      }
      else
      {
        v8 = 0;
      }
    }
    *a4 = ppv;
    ppv = 0;
  }
LABEL_29:
  SysFreeString(v6);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x18003b034  mov     [rsp-8+arg_0], rbx
0x18003b039  push    rbp
0x18003b03a  push    rsi
0x18003b03b  push    rdi
0x18003b03c  push    r12
0x18003b03e  push    r13
0x18003b040  push    r14
0x18003b042  push    r15
0x18003b044  lea     rbp, [rsp-1A0h]
0x18003b04c  sub     rsp, 2A0h
0x18003b053  mov     rax, cs:__security_cookie
0x18003b05a  xor     rax, rsp
0x18003b05d  mov     [rbp+1D0h+var_40], rax
0x18003b064  xor     r12d, r12d
0x18003b067  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18003b06c  mov     [rsp+2D0h+var_2A0], r12
0x18003b071  mov     r15, r9
0x18003b074  mov     rdi, r8
0x18003b077  call    cs:__imp_VariantInit
0x18003b07d  mov     ebx, r12d
0x18003b080  lea     rcx, [rbp+1D0h+psz]; unsigned __int16 *
0x18003b084  mov     r8, rdi; unsigned __int16 *
0x18003b087  mov     [rsp+2D0h+var_298], rbx
0x18003b08c  mov     edx, 104h; unsigned __int64
0x18003b091  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b096  mov     edi, eax
0x18003b098  mov     r13d, 1FFF0000h
0x18003b09e  mov     r14d, 70000h
0x18003b0a4  test    eax, eax
0x18003b0a6  jns     short loc_18003B0BB
0x18003b0a8  and     eax, r13d
0x18003b0ab  cmp     eax, r14d
0x18003b0ae  jnz     short loc_18003B0B3
0x18003b0b0  movzx   edi, di
0x18003b0b3  test    edi, edi
0x18003b0b5  jnz     loc_18003B202
0x18003b0bb  lea     rax, [rbp+1D0h+psz]
0x18003b0bf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003b0c3  inc     rsi
0x18003b0c6  cmp     [rax+rsi*2], r12w
0x18003b0cb  jnz     short loc_18003B0C3
0x18003b0cd  xor     edx, edx; pUnkOuter
0x18003b0cf  lea     rax, [rsp+2D0h+var_2A0]
0x18003b0d4  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x18003b0db  mov     [rsp+2D0h+ppv], rax; ppv
0x18003b0e0  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x18003b0e7  lea     r8d, [rdx+1]; dwClsContext
0x18003b0eb  call    cs:__imp_CoCreateInstance
0x18003b0f1  mov     edi, eax
0x18003b0f3  test    eax, eax
0x18003b0f5  js      short loc_18003B0FC
0x18003b0f7  mov     edi, r12d
0x18003b0fa  jmp     short loc_18003B10F
0x18003b0fc  and     eax, r13d
0x18003b0ff  cmp     eax, r14d
0x18003b102  jnz     short loc_18003B107
0x18003b104  movzx   edi, di
0x18003b107  test    edi, edi
0x18003b109  jnz     loc_18003B202
0x18003b10f  mov     r14d, r12d
0x18003b112  lea     rax, off_180052110; "http://www.microsoft.com/networking/LAN"...
0x18003b119  cmp     r14d, 3
0x18003b11d  jnb     loc_18003B1F5
0x18003b123  mov     r11d, r14d
0x18003b126  lea     rcx, [rbp+1D0h+psz]
0x18003b12a  add     r11, r11
0x18003b12d  lea     rcx, [rcx+rsi*2]; unsigned __int16 *
0x18003b131  mov     edx, 104h
0x18003b136  sub     rdx, rsi; unsigned __int64
0x18003b139  mov     r8, [rax+r11*8+8]; unsigned __int16 *
0x18003b13e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b143  mov     edi, eax
0x18003b145  test    eax, eax
0x18003b147  jns     short loc_18003B15E
0x18003b149  and     eax, r13d
0x18003b14c  cmp     eax, 70000h
0x18003b151  jnz     short loc_18003B156
0x18003b153  movzx   edi, di
0x18003b156  test    edi, edi
0x18003b158  jnz     loc_18003B202
0x18003b15e  lea     rdx, off_180052110; "http://www.microsoft.com/networking/LAN"...
0x18003b165  mov     rdx, [rdx+r11*8]; psz
0x18003b169  lea     rcx, [rsp+2D0h+var_298]; this
0x18003b16e  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18003b173  lea     rdx, [rbp+1D0h+psz]; psz
0x18003b177  lea     rcx, [rsp+2D0h+pvarg]; this
0x18003b17c  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x18003b181  mov     rbx, [rsp+2D0h+var_298]
0x18003b186  mov     eax, 8
0x18003b18b  test    rbx, rbx
0x18003b18e  jz      short loc_18003B1F1
0x18003b190  cmp     word ptr [rsp+2D0h+pvarg], ax
0x18003b195  jnz     short loc_18003B1F1
0x18003b197  cmp     qword ptr [rsp+2D0h+pvarg+8], r12
0x18003b19c  jz      short loc_18003B1F1
0x18003b19e  mov     rcx, [rsp+2D0h+var_2A0]
0x18003b1a3  lea     r8, [rsp+2D0h+var_270]
0x18003b1a8  movups  xmm0, xmmword ptr [rsp+2D0h+pvarg]
0x18003b1ad  mov     rdx, rbx
0x18003b1b0  movsd   xmm1, qword ptr [rsp+2D0h+pvarg+10h]
0x18003b1b6  mov     rax, [rcx]
0x18003b1b9  movaps  [rsp+2D0h+var_270], xmm0
0x18003b1be  movsd   [rsp+2D0h+var_260], xmm1
0x18003b1c4  mov     rax, [rax+38h]
0x18003b1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1cd  mov     edi, eax
0x18003b1cf  test    eax, eax
0x18003b1d1  js      short loc_18003B1D8
0x18003b1d3  mov     edi, r12d
0x18003b1d6  jmp     short loc_18003B1E9
0x18003b1d8  and     eax, r13d
0x18003b1db  cmp     eax, 70000h
0x18003b1e0  jnz     short loc_18003B1E5
0x18003b1e2  movzx   edi, di
0x18003b1e5  test    edi, edi
0x18003b1e7  jnz     short loc_18003B202
0x18003b1e9  inc     r14d
0x18003b1ec  jmp     loc_18003B112
0x18003b1f1  mov     edi, eax
0x18003b1f3  jmp     short loc_18003B202
0x18003b1f5  mov     rdx, [rsp+2D0h+var_2A0]
0x18003b1fa  mov     [r15], rdx
0x18003b1fd  mov     [rsp+2D0h+var_2A0], r12
0x18003b202  mov     rcx, rbx; bstrString
0x18003b205  call    cs:__imp_SysFreeString
0x18003b20b  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18003b210  call    cs:__imp_VariantClear
0x18003b216  lea     rcx, [rsp+2D0h+var_2A0]
0x18003b21b  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003b220  mov     eax, edi
0x18003b222  mov     rcx, [rbp+1D0h+var_40]
0x18003b229  xor     rcx, rsp; StackCookie
0x18003b22c  call    __security_check_cookie
0x18003b231  mov     rbx, [rsp+2D0h+arg_0]
0x18003b239  add     rsp, 2A0h
0x18003b240  pop     r15
0x18003b242  pop     r14
0x18003b244  pop     r13
0x18003b246  pop     r12
0x18003b248  pop     rdi
0x18003b249  pop     rsi
0x18003b24a  pop     rbp
0x18003b24b  retn
```
