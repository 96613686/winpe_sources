# _CWiGigDAFProviderAssociation::StartWriteCeremonyData_::_1_::dtor$1

- ea: `0x18001cf7e`
- end: `0x18001cfa0`
- name: `_CWiGigDAFProviderAssociation::StartWriteCeremonyData_::_1_::dtor$1`
- size: `34`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001f1c`

## pseudocode

```c
void __fastcall CWiGigDAFProviderAssociation::StartWriteCeremonyData_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 144));
}

```

## disassembly

```asm
0x18001cf7e  push    rbp
0x18001cf80  sub     rsp, 20h
0x18001cf84  mov     rbp, rdx
0x18001cf87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001cf8e  mov     rcx, [rbp+90h]; Block
0x18001cf95  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cf9a  add     rsp, 20h
0x18001cf9e  pop     rbp
0x18001cf9f  retn
```
