# XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)

- ea: `0x18003acfc`
- end: `0x18003ada0`
- name: `?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z`
- size: `164`
- prototype: `unsigned int __usercall@<eax>(struct IXMLDOMDocument2 *@<rcx>, struct IXMLDOMNode *@<rdx>, OLECHAR *psz@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct IXMLDOMNode **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bd50`
- `0x18003c52c`

## callees

- `0x18003aa34`
- `0x18003acfc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003ad13`
- `OLEAUT32!__imp_VariantInit` at `0x18003ad13`
- `OLEAUT32!__imp_VariantClear` at `0x18003ad8f`
- `OLEAUT32!__imp_VariantClear` at `0x18003ad8f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003ad41`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003ad41`

## string_xrefs

- `0x18003ad65`: `http://www.microsoft.com/networking/OneX/v1`

## pseudocode

```c
__int64 __fastcall XcAddChildElementDWORD(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        const unsigned __int16 *a4,
        LONG a5)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = a5;
  v8 = VariantChangeType(&pvarg, &pvarg, 0, 8u);
  v9 = v8;
  if ( v8 >= 0 )
    goto LABEL_5;
  if ( (v8 & 0x1FFF0000) == 0x70000 )
    v9 = (unsigned __int16)v8;
  if ( !v9 )
LABEL_5:
    v9 = XcAddChildElement(a1, a2, psz, (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1", pvarg.bstrVal, 0);
  VariantClear(&pvarg);
  return v9;
}

```

## disassembly

```asm
0x18003acfc  push    rbx
0x18003acfe  push    rbp
0x18003acff  push    rsi
0x18003ad00  push    rdi
0x18003ad01  sub     rsp, 58h
0x18003ad05  mov     rbp, rcx
0x18003ad08  mov     rdi, r8
0x18003ad0b  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18003ad10  mov     rsi, rdx
0x18003ad13  call    cs:__imp_VariantInit
0x18003ad19  mov     eax, 13h
0x18003ad1e  lea     rdx, [rsp+78h+pvarg]; pvarSrc
0x18003ad23  mov     word ptr [rsp+78h+pvarg], ax
0x18003ad28  lea     rcx, [rsp+78h+pvarg]; pvargDest
0x18003ad2d  mov     eax, [rsp+78h+arg_20]
0x18003ad34  mov     r9d, 8; vt
0x18003ad3a  xor     r8d, r8d; wFlags
0x18003ad3d  mov     dword ptr [rsp+78h+pvarg+8], eax
0x18003ad41  call    cs:__imp_VariantChangeType
0x18003ad47  mov     ebx, eax
0x18003ad49  test    eax, eax
0x18003ad4b  jns     short loc_18003AD60
0x18003ad4d  and     eax, 1FFF0000h
0x18003ad52  cmp     eax, 70000h
0x18003ad57  jnz     short loc_18003AD5C
0x18003ad59  movzx   ebx, bx
0x18003ad5c  test    ebx, ebx
0x18003ad5e  jnz     short loc_18003AD8A
0x18003ad60  mov     rax, qword ptr [rsp+78h+pvarg+8]
0x18003ad65  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003ad6c  mov     [rsp+78h+var_50], 0; struct IXMLDOMNode **
0x18003ad75  mov     r8, rdi; psz
0x18003ad78  mov     rdx, rsi; struct IXMLDOMNode *
0x18003ad7b  mov     [rsp+78h+var_58], rax; OLECHAR *
0x18003ad80  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003ad83  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18003ad88  mov     ebx, eax
0x18003ad8a  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18003ad8f  call    cs:__imp_VariantClear
0x18003ad95  mov     eax, ebx
0x18003ad97  add     rsp, 58h
0x18003ad9b  pop     rdi
0x18003ad9c  pop     rsi
0x18003ad9d  pop     rbp
0x18003ad9e  pop     rbx
0x18003ad9f  retn
```
