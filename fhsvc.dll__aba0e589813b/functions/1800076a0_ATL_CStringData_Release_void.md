# ATL::CStringData::Release(void)

- ea: `0x1800076a0`
- end: `0x1800076c5`
- name: `?Release@CStringData@ATL@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(ATL::CStringData *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dd0`
- `0x180007644`
- `0x18000a360`
- `0x18000aa08`
- `0x18000dd60`

## callees

- `0x1800076a0`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CStringData::Release(ATL::CStringData *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, ATL::CStringData *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, this);
}

```

## disassembly

```asm
0x1800076a0  mov     eax, 0FFFFFFFFh
0x1800076a5  lock xadd [rcx+10h], eax
0x1800076aa  sub     eax, 1
0x1800076ad  jg      short locret_1800076C4
0x1800076af  mov     r8, [rcx]
0x1800076b2  mov     rdx, rcx
0x1800076b5  mov     rcx, r8
0x1800076b8  mov     rax, [r8]
0x1800076bb  mov     rax, [rax+8]
0x1800076bf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800076c4  retn
```
