# RefCount::Release(void)

- ea: `0x140001660`
- end: `0x140001691`
- name: `?Release@RefCount@@QEAAXXZ`
- size: `49`
- prototype: `void __fastcall(RefCount *__hidden this)`
- caller_count: `56`
- callee_count: `2`
- tags: ``

## callers

- `0x140001008`
- `0x140001050`
- `0x1400010fc`
- `0x140001310`
- `0x140001350`
- `0x140001f10`
- `0x1400027b0`
- `0x140002a40`
- `0x140002d44`
- `0x1400049fc`
- `0x140004c80`
- `0x140011010`
- `0x1400112e0`
- `0x1400113d0`
- `0x140017880`
- `0x140017cac`
- `0x14001b080`
- `0x14001b144`
- `0x14001d938`
- `0x14001dafc`
- `0x14001dcb4`
- `0x140020ab0`
- `0x1400227a0`
- `0x140023030`
- `0x140023500`
- `0x140023cf0`
- `0x140024020`
- `0x1400242b0`
- `0x140024830`
- `0x140024a50`
- `0x140024cf0`
- `0x140025480`
- `0x1400254c0`
- `0x140025c40`
- `0x140026380`
- `0x1400268e0`
- `0x140026c18`
- `0x140027190`
- `0x140027d50`
- `0x140027f30`
- `0x140027fe0`
- `0x140028e50`
- `0x140028ec0`
- `0x140028f80`
- `0x1400290c0`
- `0x140029c90`
- `0x140029f80`
- `0x14002ab90`
- `0x14002b120`
- `0x14002b530`

## callees

- `0x140001660`
- `0x140006560`

## pseudocode

```c
void __fastcall RefCount::Release(RefCount *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(RefCount *, __int64))(*(_QWORD *)this + 16LL))(this, 1);
  }
}

```

## disassembly

```asm
0x140001660  sub     rsp, 28h
0x140001664  mov     eax, 0FFFFFFFFh
0x140001669  lock xadd [rcx+10h], eax
0x14000166e  cmp     eax, 1
0x140001671  jz      short loc_140001679
0x140001673  add     rsp, 28h
0x140001677  retn
0x140001679  test    rcx, rcx
0x14000167c  jz      short loc_140001673
0x14000167e  mov     rax, [rcx]
0x140001681  mov     edx, 1
0x140001686  mov     rax, [rax+10h]
0x14000168a  call    _guard_dispatch_icall
0x14000168f  jmp     short loc_140001673
```
