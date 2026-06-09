# DereferenceAdapter

- ea: `0x140001870`
- end: `0x140001890`
- name: `DereferenceAdapter`
- size: `32`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1400013f0`
- `0x140001d60`
- `0x1400024e0`
- `0x140002e80`
- `0x140003c60`
- `0x140019940`
- `0x14001ac30`
- `0x14001af80`
- `0x14001d500`

## callees

- `0x140001870`
- `0x14001d39c`

## pseudocode

```c
void __fastcall DereferenceAdapter(__int64 a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
    FreeAdapter(a1);
}

```

## disassembly

```asm
0x140001870  sub     rsp, 28h
0x140001874  mov     eax, 0FFFFFFFFh
0x140001879  lock xadd [rcx+4], eax
0x14000187e  cmp     eax, 1
0x140001881  jz      short loc_140001889
0x140001883  add     rsp, 28h
0x140001887  retn
0x140001889  call    FreeAdapter
0x14000188e  jmp     short loc_140001883
```
