# IASTL::IASAttributeVector::~IASAttributeVector(void)

- ea: `0x18000b2dc`
- end: `0x18000b304`
- name: `??1IASAttributeVector@IASTL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(IASTL::IASAttributeVector *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b2a0`
- `0x18000b960`
- `0x180014f94`
- `0x180018620`
- `0x180018fb0`
- `0x18001a738`
- `0x18001b5e8`
- `0x18001b7bc`
- `0x18002bbdc`
- `0x18002c53b`
- `0x18002cc1d`
- `0x18002cc77`

## callees

- `0x18000b2dc`
- `0x18000b648`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2f8`

## pseudocode

```c
void __fastcall IASTL::IASAttributeVector::~IASAttributeVector(IASTL::IASAttributeVector *this)
{
  IASTL::IASAttributeVector::clear(this);
  if ( *((_BYTE *)this + 20) )
  {
    if ( *(_QWORD *)this )
      CoTaskMemFree(*(LPVOID *)this);
  }
}

```

## disassembly

```asm
0x18000b2dc  push    rbx
0x18000b2de  sub     rsp, 20h
0x18000b2e2  mov     rbx, rcx
0x18000b2e5  call    ?clear@IASAttributeVector@IASTL@@QEAAXXZ; IASTL::IASAttributeVector::clear(void)
0x18000b2ea  cmp     byte ptr [rbx+14h], 0
0x18000b2ee  jz      short loc_18000B2FE
0x18000b2f0  mov     rcx, [rbx]; pv
0x18000b2f3  test    rcx, rcx
0x18000b2f6  jz      short loc_18000B2FE
0x18000b2f8  call    cs:__imp_CoTaskMemFree
0x18000b2fe  add     rsp, 20h
0x18000b302  pop     rbx
0x18000b303  retn
```
