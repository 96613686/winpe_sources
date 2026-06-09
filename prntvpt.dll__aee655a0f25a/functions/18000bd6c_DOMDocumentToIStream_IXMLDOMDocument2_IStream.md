# DOMDocumentToIStream(IXMLDOMDocument2 *,IStream *)

- ea: `0x18000bd6c`
- end: `0x18000be0c`
- name: `?DOMDocumentToIStream@@YAJPEAUIXMLDOMDocument2@@PEAUIStream@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IStream *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008190`
- `0x1800087e0`
- `0x180013380`
- `0x180013420`
- `0x1800141b0`

## callees

- `0x18000bd6c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000bd9a`
- `OLEAUT32!__imp_VariantInit` at `0x18000bd9a`
- `OLEAUT32!__imp_VariantClear` at `0x18000bdf2`
- `OLEAUT32!__imp_VariantClear` at `0x18000bdf2`

## pseudocode

```c
__int64 __fastcall DOMDocumentToIStream(struct IXMLDOMDocument2 *a1, struct IStream *a2)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *save)(IXMLDOMDocument2 *, VARIANT); // rax
  unsigned int v6; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG v9; // [rsp+40h] [rbp-28h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 13;
  ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  lpVtbl = a1->lpVtbl;
  pvarg.llVal = (LONGLONG)a2;
  save = lpVtbl->save;
  v9 = pvarg;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))save)(a1, &v9);
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x18000bd6c  mov     [rsp+arg_0], rbx
0x18000bd71  push    rdi
0x18000bd72  sub     rsp, 60h
0x18000bd76  mov     rbx, rdx
0x18000bd79  mov     rdi, rcx
0x18000bd7c  test    rcx, rcx
0x18000bd7f  jz      short loc_18000BDFC
0x18000bd81  test    rdx, rdx
0x18000bd84  jz      short loc_18000BDFC
0x18000bd86  xorps   xmm0, xmm0
0x18000bd89  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000bd8e  xor     eax, eax
0x18000bd90  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18000bd95  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x18000bd9a  call    cs:__imp_VariantInit
0x18000bda0  mov     eax, 0Dh
0x18000bda5  mov     rcx, rbx
0x18000bda8  mov     word ptr [rsp+68h+pvarg], ax
0x18000bdad  mov     rax, [rbx]
0x18000bdb0  mov     rax, [rax+8]
0x18000bdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb9  mov     rax, [rdi]
0x18000bdbc  lea     rdx, [rsp+68h+var_28]
0x18000bdc1  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x18000bdc7  mov     rcx, rdi
0x18000bdca  mov     qword ptr [rsp+68h+pvarg+8], rbx
0x18000bdcf  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x18000bdd4  mov     rax, [rax+210h]
0x18000bddb  movsd   [rsp+68h+var_18], xmm1
0x18000bde1  movaps  [rsp+68h+var_28], xmm0
0x18000bde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdeb  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000bdf0  mov     ebx, eax
0x18000bdf2  call    cs:__imp_VariantClear
0x18000bdf8  mov     eax, ebx
0x18000bdfa  jmp     short loc_18000BE01
0x18000bdfc  mov     eax, 80070057h
0x18000be01  mov     rbx, [rsp+68h+arg_0]
0x18000be06  add     rsp, 60h
0x18000be0a  pop     rdi
0x18000be0b  retn
```
