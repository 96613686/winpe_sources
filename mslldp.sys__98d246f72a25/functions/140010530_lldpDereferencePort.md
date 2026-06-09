# lldpDereferencePort

- ea: `0x140010530`
- end: `0x140010550`
- name: `lldpDereferencePort`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140006310`
- `0x14000ec14`
- `0x14000ec80`
- `0x14000ece8`
- `0x14000efd0`
- `0x14000fca0`
- `0x14000fdd0`

## callees

- `0x140010530`
- `0x140010aec`

## pseudocode

```c
void __fastcall lldpDereferencePort(__int64 a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 48), 0xFFFFFFFF) == 1 )
    lldpDeletePort((char *)a1);
}

```

## disassembly

```asm
0x140010530  sub     rsp, 28h
0x140010534  mov     eax, 0FFFFFFFFh
0x140010539  lock xadd [rcx+30h], eax
0x14001053e  cmp     eax, 1
0x140010541  jz      short loc_140010549
0x140010543  add     rsp, 28h
0x140010547  retn
0x140010549  call    lldpDeletePort
0x14001054e  jmp     short loc_140010543
```
