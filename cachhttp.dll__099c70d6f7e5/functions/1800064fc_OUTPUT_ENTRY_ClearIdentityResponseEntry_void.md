# OUTPUT_ENTRY::ClearIdentityResponseEntry(void)

- ea: `0x1800064fc`
- end: `0x180006533`
- name: `?ClearIdentityResponseEntry@OUTPUT_ENTRY@@QEAAXXZ`
- size: `55`
- prototype: `void __fastcall(OUTPUT_ENTRY *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f20`
- `0x180006338`
- `0x1800081f0`

## callees

- `0x1800064fc`
- `0x1800065c8`
- `0x1800071bc`

## pseudocode

```c
void __fastcall OUTPUT_ENTRY::ClearIdentityResponseEntry(OUTPUT_ENTRY *this)
{
  RESPONSE_ENTRY *v2; // rcx

  v2 = (RESPONSE_ENTRY *)*((_QWORD *)this + 103);
  if ( v2 )
  {
    RESPONSE_ENTRY::SetFlushed(v2);
    RESPONSE_ENTRY::DereferenceResponseEntry(*((RESPONSE_ENTRY **)this + 103));
    *((_QWORD *)this + 103) = 0;
  }
}

```

## disassembly

```asm
0x1800064fc  push    rbx
0x1800064fe  sub     rsp, 20h
0x180006502  mov     rbx, rcx
0x180006505  mov     rcx, [rcx+338h]; this
0x18000650c  test    rcx, rcx
0x18000650f  jz      short loc_18000652D
0x180006511  call    ?SetFlushed@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::SetFlushed(void)
0x180006516  mov     rcx, [rbx+338h]; this
0x18000651d  call    ?DereferenceResponseEntry@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::DereferenceResponseEntry(void)
0x180006522  mov     qword ptr [rbx+338h], 0
0x18000652d  add     rsp, 20h
0x180006531  pop     rbx
0x180006532  retn
```
