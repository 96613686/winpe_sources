# OUTPUT_ENTRY::ClearAlternateResponseEntry(void)

- ea: `0x1800064bc`
- end: `0x1800064f3`
- name: `?ClearAlternateResponseEntry@OUTPUT_ENTRY@@QEAAXXZ`
- size: `55`
- prototype: `void __fastcall(OUTPUT_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006338`
- `0x1800081f0`

## callees

- `0x1800064bc`
- `0x1800065c8`
- `0x1800071bc`

## pseudocode

```c
void __fastcall OUTPUT_ENTRY::ClearAlternateResponseEntry(OUTPUT_ENTRY *this)
{
  RESPONSE_ENTRY *v2; // rcx

  v2 = (RESPONSE_ENTRY *)*((_QWORD *)this + 104);
  if ( v2 )
  {
    RESPONSE_ENTRY::SetFlushed(v2);
    RESPONSE_ENTRY::DereferenceResponseEntry(*((RESPONSE_ENTRY **)this + 104));
    *((_QWORD *)this + 104) = 0;
  }
}

```

## disassembly

```asm
0x1800064bc  push    rbx
0x1800064be  sub     rsp, 20h
0x1800064c2  mov     rbx, rcx
0x1800064c5  mov     rcx, [rcx+340h]; this
0x1800064cc  test    rcx, rcx
0x1800064cf  jz      short loc_1800064ED
0x1800064d1  call    ?SetFlushed@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::SetFlushed(void)
0x1800064d6  mov     rcx, [rbx+340h]; this
0x1800064dd  call    ?DereferenceResponseEntry@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::DereferenceResponseEntry(void)
0x1800064e2  mov     qword ptr [rbx+340h], 0
0x1800064ed  add     rsp, 20h
0x1800064f1  pop     rbx
0x1800064f2  retn
```
