# LoadCloneXML(ushort *,ushort *,ushort *,CloneXMLParser *)

- ea: `0x180026ce8`
- end: `0x18002702b`
- name: `?LoadCloneXML@@YAJPEAG00PEAVCloneXMLParser@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, OLECHAR *, struct CloneXMLParser *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800249ec`
- `0x180026428`
- `0x180026518`

## callees

- `0x180026ce8`
- `0x180027034`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026dea`
- `OLEAUT32!__imp_SysAllocString` at `0x180026e17`
- `OLEAUT32!__imp_SysAllocString` at `0x180026ee4`
- `OLEAUT32!__imp_SysAllocString` at `0x180026dea`
- `OLEAUT32!__imp_SysAllocString` at `0x180026e17`
- `OLEAUT32!__imp_SysAllocString` at `0x180026ee4`
- `OLEAUT32!__imp_SysFreeString` at `0x180026ffa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c89a`
- `OLEAUT32!__imp_SysFreeString` at `0x180026ffa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c89a`
- `OLEAUT32!__imp_VariantInit` at `0x180026d53`
- `OLEAUT32!__imp_VariantInit` at `0x180026d5e`
- `OLEAUT32!__imp_VariantInit` at `0x180026d6c`
- `OLEAUT32!__imp_VariantInit` at `0x180026d53`
- `OLEAUT32!__imp_VariantInit` at `0x180026d5e`
- `OLEAUT32!__imp_VariantInit` at `0x180026d6c`
- `OLEAUT32!__imp_VariantClear` at `0x180026fa2`
- `OLEAUT32!__imp_VariantClear` at `0x180026fe3`
- `OLEAUT32!__imp_VariantClear` at `0x180026ff1`
- `OLEAUT32!__imp_VariantClear` at `0x18002c83f`
- `OLEAUT32!__imp_VariantClear` at `0x18002c883`
- `OLEAUT32!__imp_VariantClear` at `0x18002c890`
- `OLEAUT32!__imp_VariantClear` at `0x180026fa2`
- `OLEAUT32!__imp_VariantClear` at `0x180026fe3`
- `OLEAUT32!__imp_VariantClear` at `0x180026ff1`
- `OLEAUT32!__imp_VariantClear` at `0x18002c83f`
- `OLEAUT32!__imp_VariantClear` at `0x18002c883`
- `OLEAUT32!__imp_VariantClear` at `0x18002c890`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026d92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026dd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026d92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026dd5`

## pseudocode

```c
__int64 __fastcall LoadCloneXML(OLECHAR *psz, OLECHAR *a2, OLECHAR *a3, struct CloneXMLParser *a4)
{
  OLECHAR *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int16 *v12; // rdx
  struct IXMLDOMParseError *v13; // r8
  int v15; // [rsp+30h] [rbp-108h] BYREF
  __int16 v16; // [rsp+34h] [rbp-104h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-100h] BYREF
  struct IXMLDOMParseError *v18; // [rsp+40h] [rbp-F8h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-F0h] BYREF
  OLECHAR *v20; // [rsp+50h] [rbp-E8h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-E0h] BYREF
  VARIANTARG v22; // [rsp+70h] [rbp-C8h] BYREF
  VARIANTARG v23; // [rsp+88h] [rbp-B0h] BYREF
  VARIANTARG v24; // [rsp+A0h] [rbp-98h] BYREF
  VARIANTARG v25; // [rsp+C0h] [rbp-78h] BYREF
  VARIANTARG v26; // [rsp+E0h] [rbp-58h] BYREF

  v8 = 0;
  v20 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v22, 0, sizeof(v22));
  memset(&v23, 0, sizeof(v23));
  ppv = 0;
  v18 = 0;
  v19 = 0;
  VariantInit(&pvarg);
  VariantInit(&v22);
  VariantInit(&v23);
  v15 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, &ppv);
  if ( v15 )
    goto LABEL_18;
  if ( a2 && a3 )
  {
    v15 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 0x15u, &IID_IXMLDOMSchemaCollection, &v19);
    if ( v15 )
      goto LABEL_18;
    v8 = SysAllocString(a3);
    v20 = v8;
    if ( !v8 )
      goto LABEL_6;
    v22.vt = 8;
    v22.llVal = (LONGLONG)SysAllocString(a2);
    if ( !v22.llVal )
      goto LABEL_6;
    v9 = *(_QWORD *)v19;
    v24 = v22;
    v15 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v9 + 56))(v19, v8, &v24);
    if ( v15 < 0 )
      goto LABEL_18;
    v23.vt = 13;
    v23.llVal = (LONGLONG)v19;
    v19 = 0;
    v10 = *(_QWORD *)ppv;
    v25 = v23;
    v15 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(v10 + 624))(ppv, &v25);
    if ( v15 < 0 )
      goto LABEL_18;
  }
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
LABEL_6:
    v15 = -2147024882;
    goto LABEL_18;
  }
  v16 = 0;
  v11 = *(_QWORD *)ppv;
  v26 = pvarg;
  v15 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v11 + 464))(ppv, &v26, &v16);
  if ( v15 >= 0 && v16 )
  {
    v15 = (**(__int64 (__fastcall ***)(struct CloneXMLParser *, LPVOID))a4)(a4, ppv);
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMParseError **))(*(_QWORD *)ppv + 480LL))(ppv, &v18);
    if ( v15 < 0 )
      v13 = 0;
    else
      v13 = v18;
    ReportXmlError(psz, v12, v13, &v15);
  }
LABEL_18:
  VariantClear(&pvarg);
  if ( v18 )
  {
    ((void (__fastcall *)(struct IXMLDOMParseError *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  VariantClear(&v22);
  VariantClear(&v23);
  SysFreeString(v8);
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180026ce8  push    rbx
0x180026cea  push    rsi
0x180026ceb  push    rdi
0x180026cec  push    r12
0x180026cee  push    r14
0x180026cf0  push    r15
0x180026cf2  sub     rsp, 108h
0x180026cf9  mov     r15, r9
0x180026cfc  mov     rdi, r8
0x180026cff  mov     r14, rdx
0x180026d02  mov     rsi, rcx
0x180026d05  xor     r12d, r12d
0x180026d08  mov     ebx, r12d
0x180026d0b  mov     [rsp+138h+var_E8], rbx
0x180026d10  xorps   xmm0, xmm0
0x180026d13  xor     eax, eax
0x180026d15  movups  xmmword ptr [rsp+138h+pvarg], xmm0
0x180026d1a  mov     qword ptr [rsp+138h+pvarg+10h], rax
0x180026d1f  xorps   xmm1, xmm1
0x180026d22  movups  xmmword ptr [rsp+138h+var_C8], xmm1
0x180026d27  mov     qword ptr [rsp+138h+var_C8+10h], rax
0x180026d2f  movups  xmmword ptr [rsp+138h+var_B0], xmm0
0x180026d37  mov     qword ptr [rsp+138h+var_B0+10h], rax
0x180026d3f  mov     [rsp+138h+var_100], r12
0x180026d44  mov     [rsp+138h+var_F8], r12
0x180026d49  mov     [rsp+138h+var_F0], r12
0x180026d4e  lea     rcx, [rsp+138h+pvarg]; pvarg
0x180026d53  call    cs:__imp_VariantInit
0x180026d59  lea     rcx, [rsp+138h+var_C8]; pvarg
0x180026d5e  call    cs:__imp_VariantInit
0x180026d64  lea     rcx, [rsp+138h+var_B0]; pvarg
0x180026d6c  call    cs:__imp_VariantInit
0x180026d72  nop
0x180026d73  lea     rax, [rsp+138h+var_100]
0x180026d78  mov     [rsp+138h+ppv], rax; ppv
0x180026d7d  lea     r9, IID_IXMLDOMDocument3; riid
0x180026d84  xor     edx, edx; pUnkOuter
0x180026d86  lea     r8d, [r12+1]; dwClsContext
0x180026d8b  lea     rcx, CLSID_DOMDocument60; rclsid
0x180026d92  call    cs:__imp_CoCreateInstance
0x180026d98  mov     [rsp+138h+var_108], eax
0x180026d9c  test    eax, eax
0x180026d9e  jnz     loc_180026F9D
0x180026da4  test    r14, r14
0x180026da7  jz      loc_180026ED7
0x180026dad  test    rdi, rdi
0x180026db0  jz      loc_180026ED7
0x180026db6  lea     rax, [rsp+138h+var_F0]
0x180026dbb  mov     [rsp+138h+ppv], rax; ppv
0x180026dc0  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x180026dc7  xor     edx, edx; pUnkOuter
0x180026dc9  lea     r8d, [r12+15h]; dwClsContext
0x180026dce  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x180026dd5  call    cs:__imp_CoCreateInstance
0x180026ddb  mov     [rsp+138h+var_108], eax
0x180026ddf  test    eax, eax
0x180026de1  jnz     loc_180026F9D
0x180026de7  mov     rcx, rdi; psz
0x180026dea  call    cs:__imp_SysAllocString
0x180026df0  mov     rbx, rax
0x180026df3  mov     [rsp+138h+var_E8], rax
0x180026df8  test    rax, rax
0x180026dfb  jnz     short loc_180026E0A
0x180026dfd  mov     [rsp+138h+var_108], 8007000Eh
0x180026e05  jmp     loc_180026F9D
0x180026e0a  mov     edi, 8
0x180026e0f  mov     word ptr [rsp+138h+var_C8], di
0x180026e14  mov     rcx, r14; psz
0x180026e17  call    cs:__imp_SysAllocString
0x180026e1d  mov     qword ptr [rsp+138h+var_C8+8], rax
0x180026e22  test    rax, rax
0x180026e25  jz      short loc_180026DFD
0x180026e27  mov     rcx, [rsp+138h+var_F0]
0x180026e2c  mov     rax, [rcx]
0x180026e2f  movups  xmm0, xmmword ptr [rsp+138h+var_C8]
0x180026e34  movaps  [rsp+138h+var_98], xmm0
0x180026e3c  movsd   xmm1, qword ptr [rsp+138h+var_C8+10h]
0x180026e45  movsd   [rsp+138h+var_88], xmm1
0x180026e4e  lea     r8, [rsp+138h+var_98]
0x180026e56  mov     rdx, rbx
0x180026e59  mov     rax, [rax+38h]
0x180026e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e62  mov     [rsp+138h+var_108], eax
0x180026e66  test    eax, eax
0x180026e68  js      loc_180026F9D
0x180026e6e  lea     eax, [rdi+5]
0x180026e71  mov     word ptr [rsp+138h+var_B0], ax
0x180026e79  mov     rax, [rsp+138h+var_F0]
0x180026e7e  mov     qword ptr [rsp+138h+var_B0+8], rax
0x180026e86  mov     [rsp+138h+var_F0], r12
0x180026e8b  mov     rcx, [rsp+138h+var_100]
0x180026e90  mov     rax, [rcx]
0x180026e93  movups  xmm0, xmmword ptr [rsp+138h+var_B0]
0x180026e9b  movaps  [rsp+138h+var_78], xmm0
0x180026ea3  movsd   xmm1, qword ptr [rsp+138h+var_B0+10h]
0x180026eac  movsd   [rsp+138h+var_68], xmm1
0x180026eb5  lea     rdx, [rsp+138h+var_78]
0x180026ebd  mov     rax, [rax+270h]
0x180026ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ec9  mov     [rsp+138h+var_108], eax
0x180026ecd  test    eax, eax
0x180026ecf  js      loc_180026F9D
0x180026ed5  jmp     short loc_180026EDC
0x180026ed7  mov     edi, 8
0x180026edc  mov     word ptr [rsp+138h+pvarg], di
0x180026ee1  mov     rcx, rsi; psz
0x180026ee4  call    cs:__imp_SysAllocString
0x180026eea  mov     qword ptr [rsp+138h+pvarg+8], rax
0x180026eef  test    rax, rax
0x180026ef2  jz      loc_180026DFD
0x180026ef8  mov     [rsp+138h+var_104], r12w
0x180026efe  mov     rcx, [rsp+138h+var_100]
0x180026f03  mov     rax, [rcx]
0x180026f06  movups  xmm0, xmmword ptr [rsp+138h+pvarg]
0x180026f0b  movaps  [rsp+138h+var_58], xmm0
0x180026f13  movsd   xmm1, qword ptr [rsp+138h+pvarg+10h]
0x180026f19  movsd   [rsp+138h+var_48], xmm1
0x180026f22  lea     r8, [rsp+138h+var_104]
0x180026f27  lea     rdx, [rsp+138h+var_58]
0x180026f2f  mov     rax, [rax+1D0h]
0x180026f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f3b  mov     [rsp+138h+var_108], eax
0x180026f3f  test    eax, eax
0x180026f41  js      short loc_180026F64
0x180026f43  cmp     [rsp+138h+var_104], r12w
0x180026f49  jz      short loc_180026F64
0x180026f4b  mov     rax, [r15]
0x180026f4e  mov     rdx, [rsp+138h+var_100]
0x180026f53  mov     rcx, r15
0x180026f56  mov     rax, [rax]
0x180026f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f5e  mov     [rsp+138h+var_108], eax
0x180026f62  jmp     short loc_180026F9D
0x180026f64  mov     rcx, [rsp+138h+var_100]
0x180026f69  mov     rax, [rcx]
0x180026f6c  lea     rdx, [rsp+138h+var_F8]
0x180026f71  mov     rax, [rax+1E0h]
0x180026f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f7d  mov     [rsp+138h+var_108], eax
0x180026f81  lea     r9, [rsp+138h+var_108]; int *
0x180026f86  mov     rcx, rsi; psz
0x180026f89  test    eax, eax
0x180026f8b  js      short loc_180026F94
0x180026f8d  mov     r8, [rsp+138h+var_F8]
0x180026f92  jmp     short loc_180026F97
0x180026f94  xor     r8d, r8d; struct IXMLDOMParseError *
0x180026f97  call    ?ReportXmlError@@YAXPEAG0PEAUIXMLDOMParseError@@PEAJ@Z; ReportXmlError(ushort *,ushort *,IXMLDOMParseError *,long *)
0x180026f9c  nop
0x180026f9d  lea     rcx, [rsp+138h+pvarg]; pvarg
0x180026fa2  call    cs:__imp_VariantClear
0x180026fa8  mov     rcx, [rsp+138h+var_F8]
0x180026fad  test    rcx, rcx
0x180026fb0  jz      short loc_180026FC3
0x180026fb2  mov     rax, [rcx]
0x180026fb5  mov     rax, [rax+10h]
0x180026fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fbe  mov     [rsp+138h+var_F8], r12
0x180026fc3  mov     rcx, [rsp+138h+var_100]
0x180026fc8  test    rcx, rcx
0x180026fcb  jz      short loc_180026FDE
0x180026fcd  mov     rax, [rcx]
0x180026fd0  mov     rax, [rax+10h]
0x180026fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fd9  mov     [rsp+138h+var_100], r12
0x180026fde  lea     rcx, [rsp+138h+var_C8]; pvarg
0x180026fe3  call    cs:__imp_VariantClear
0x180026fe9  lea     rcx, [rsp+138h+var_B0]; pvarg
0x180026ff1  call    cs:__imp_VariantClear
0x180026ff7  mov     rcx, rbx; bstrString
0x180026ffa  call    cs:__imp_SysFreeString
0x180027000  mov     rcx, [rsp+138h+var_F0]
0x180027005  test    rcx, rcx
0x180027008  jz      short loc_180027016
0x18002700a  mov     rax, [rcx]
0x18002700d  mov     rax, [rax+10h]
0x180027011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027016  mov     eax, [rsp+138h+var_108]
0x18002701a  add     rsp, 108h
0x180027021  pop     r15
0x180027023  pop     r14
0x180027025  pop     r12
0x180027027  pop     rdi
0x180027028  pop     rsi
0x180027029  pop     rbx
0x18002702a  retn
0x18002c832  push    rbp
0x18002c834  sub     rsp, 30h
0x18002c838  mov     rbp, rdx
0x18002c83b  lea     rcx, [rbp+58h]; pvarg
0x18002c83f  call    cs:__imp_VariantClear
0x18002c845  mov     rcx, [rbp+40h]
0x18002c849  test    rcx, rcx
0x18002c84c  jz      short loc_18002C862
0x18002c84e  mov     rax, [rcx]
0x18002c851  mov     rax, [rax+10h]
0x18002c855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c85a  mov     qword ptr [rbp+40h], 0
0x18002c862  mov     rcx, [rbp+38h]
0x18002c866  test    rcx, rcx
0x18002c869  jz      short loc_18002C87F
0x18002c86b  mov     rax, [rcx]
0x18002c86e  mov     rax, [rax+10h]
0x18002c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c877  mov     qword ptr [rbp+38h], 0
0x18002c87f  lea     rcx, [rbp+70h]; pvarg
0x18002c883  call    cs:__imp_VariantClear
0x18002c889  lea     rcx, [rbp+88h]; pvarg
0x18002c890  call    cs:__imp_VariantClear
0x18002c896  mov     rcx, [rbp+50h]; bstrString
0x18002c89a  call    cs:__imp_SysFreeString
0x18002c8a0  mov     rcx, [rbp+48h]
0x18002c8a4  test    rcx, rcx
0x18002c8a7  jz      short loc_18002C8B6
0x18002c8a9  mov     rax, [rcx]
0x18002c8ac  mov     rax, [rax+10h]
0x18002c8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8b5  nop
0x18002c8b6  add     rsp, 30h
0x18002c8ba  pop     rbp
0x18002c8bb  retn
```
