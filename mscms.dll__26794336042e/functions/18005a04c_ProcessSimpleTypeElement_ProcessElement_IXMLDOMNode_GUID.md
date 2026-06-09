# ProcessSimpleTypeElement::ProcessElement(IXMLDOMNode *,_GUID *)

- ea: `0x18005a04c`
- end: `0x18005a0be`
- name: `?ProcessElement@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@PEAU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(ProcessSimpleTypeElement *__hidden this, LPCLSID pclsid, struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800599a4`
- `0x18005b17c`

## callees

- `0x180059e04`
- `0x18005a04c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18005a070`
- `OLEAUT32!__imp_VariantInit` at `0x18005a070`
- `OLEAUT32!__imp_VariantClear` at `0x18005a0ab`
- `OLEAUT32!__imp_VariantClear` at `0x18005a0ab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005a09e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005a09e`

## pseudocode

```c
__int64 __fastcall ProcessSimpleTypeElement::ProcessElement(
        ProcessSimpleTypeElement *this,
        LPCLSID pclsid,
        struct _GUID *a3)
{
  HRESULT RequiredAttributeValue; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  RequiredAttributeValue = ProcessSimpleTypeElement::GetRequiredAttributeValue(
                             this,
                             (struct IXMLDOMNode *)&stru_18008E4B8,
                             (const unsigned __int16 *)8,
                             (unsigned __int16)&pvarg,
                             *(struct tagVARIANT **)&pvarg.vt);
  if ( RequiredAttributeValue >= 0 )
  {
    RequiredAttributeValue = CLSIDFromString(pvarg.bstrVal, pclsid);
    VariantClear(&pvarg);
  }
  return (unsigned int)RequiredAttributeValue;
}

```

## disassembly

```asm
0x18005a04c  mov     [rsp+arg_0], rbx
0x18005a051  push    rdi
0x18005a052  sub     rsp, 40h
0x18005a056  mov     rbx, rcx
0x18005a059  xorps   xmm0, xmm0
0x18005a05c  xor     eax, eax
0x18005a05e  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18005a063  movups  xmmword ptr [rsp+48h+pvarg], xmm0; struct tagVARIANT *
0x18005a068  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18005a06d  mov     rdi, rdx
0x18005a070  call    cs:__imp_VariantInit
0x18005a076  mov     r8d, 8; unsigned __int16 *
0x18005a07c  lea     r9, [rsp+48h+pvarg]; unsigned __int16
0x18005a081  lea     rdx, stru_18008E4B8; struct IXMLDOMNode *
0x18005a088  mov     rcx, rbx; this
0x18005a08b  call    ?GetRequiredAttributeValue@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@PEBGGPEAUtagVARIANT@@@Z; ProcessSimpleTypeElement::GetRequiredAttributeValue(IXMLDOMNode *,ushort const *,ushort,tagVARIANT *)
0x18005a090  mov     ebx, eax
0x18005a092  test    eax, eax
0x18005a094  js      short loc_18005A0B1
0x18005a096  mov     rcx, qword ptr [rsp+48h+pvarg+8]; lpsz
0x18005a09b  mov     rdx, rdi; pclsid
0x18005a09e  call    cs:__imp_CLSIDFromString
0x18005a0a4  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18005a0a9  mov     ebx, eax
0x18005a0ab  call    cs:__imp_VariantClear
0x18005a0b1  mov     eax, ebx
0x18005a0b3  mov     rbx, [rsp+48h+arg_0]
0x18005a0b8  add     rsp, 40h
0x18005a0bc  pop     rdi
0x18005a0bd  retn
```
