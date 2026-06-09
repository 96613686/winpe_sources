# CHashValueStringList::~CHashValueStringList(void)

- ea: `0x18000ea90`
- end: `0x18000eabf`
- name: `??1CHashValueStringList@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CHashValueStringList *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f35c`
- `0x1800219a0`
- `0x1800269cc`

## callees

- `0x18000ea90`
- `0x18000eac8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eab3`

## pseudocode

```c
void __fastcall CHashValueStringList::~CHashValueStringList(CHashValueStringList *this)
{
  void *v2; // rcx

  CTPLiteSListContainer<CStringListLink>::~CTPLiteSListContainer<CStringListLink>((_QWORD *)this + 6);
  v2 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18000ea90  push    rbx
0x18000ea92  sub     rsp, 20h
0x18000ea96  mov     rbx, rcx
0x18000ea99  add     rcx, 30h ; '0'
0x18000ea9d  call    ??1?$CTPLiteSListContainer@VCStringListLink@@@@QEAA@XZ; CTPLiteSListContainer<CStringListLink>::~CTPLiteSListContainer<CStringListLink>(void)
0x18000eaa2  mov     rcx, [rbx+28h]; pv
0x18000eaa6  mov     qword ptr [rbx+28h], 0
0x18000eaae  test    rcx, rcx
0x18000eab1  jz      short loc_18000EAB9
0x18000eab3  call    cs:__imp_CoTaskMemFree
0x18000eab9  add     rsp, 20h
0x18000eabd  pop     rbx
0x18000eabe  retn
```
