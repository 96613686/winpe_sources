# IASTL::IASAttributeVector::~IASAttributeVector(void)

- ea: `0x18002a2a0`
- end: `0x18002a2c8`
- name: `??1IASAttributeVector@IASTL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(IASTL::IASAttributeVector *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b47c`
- `0x18001c7f0`
- `0x18002f23f`

## callees

- `0x18002a2a0`
- `0x18002a4f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a2bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a2bc`

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
0x18002a2a0  push    rbx
0x18002a2a2  sub     rsp, 20h
0x18002a2a6  mov     rbx, rcx
0x18002a2a9  call    ?clear@IASAttributeVector@IASTL@@QEAAXXZ; IASTL::IASAttributeVector::clear(void)
0x18002a2ae  cmp     byte ptr [rbx+14h], 0
0x18002a2b2  jz      short loc_18002A2C2
0x18002a2b4  mov     rcx, [rbx]; pv
0x18002a2b7  test    rcx, rcx
0x18002a2ba  jz      short loc_18002A2C2
0x18002a2bc  call    cs:__imp_CoTaskMemFree
0x18002a2c2  add     rsp, 20h
0x18002a2c6  pop     rbx
0x18002a2c7  retn
```
