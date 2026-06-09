# std::list<HardwareAddress,std::allocator<HardwareAddress>>::~list<HardwareAddress,std::allocator<HardwareAddress>>(void)

- ea: `0x18001837c`
- end: `0x1800183ce`
- name: `??1?$list@VHardwareAddress@@V?$allocator@VHardwareAddress@@@std@@@std@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001ddf2`

## callees

- `0x1800014d0`
- `0x18001837c`

## pseudocode

```c
void __fastcall std::list<HardwareAddress>::~list<HardwareAddress>(__int64 a1)
{
  _QWORD *v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      operator delete(v2);
      v3 = *(_QWORD **)a1;
      v2 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x18001837c  mov     [rsp+arg_0], rbx
0x180018381  push    rdi
0x180018382  sub     rsp, 20h
0x180018386  mov     rax, [rcx]
0x180018389  mov     rdi, rcx
0x18001838c  mov     rdx, [rax]
0x18001838f  mov     [rax], rax
0x180018392  mov     rax, [rcx]
0x180018395  mov     [rax+8], rax
0x180018399  mov     qword ptr [rcx+8], 0
0x1800183a1  mov     rcx, [rcx]
0x1800183a4  cmp     rdx, rcx
0x1800183a7  jz      short loc_1800183BF
0x1800183a9  mov     rbx, [rdx]
0x1800183ac  mov     rcx, rdx; Block
0x1800183af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800183b4  mov     rcx, [rdi]; Block
0x1800183b7  mov     rdx, rbx
0x1800183ba  cmp     rbx, rcx
0x1800183bd  jnz     short loc_1800183A9
0x1800183bf  mov     rbx, [rsp+28h+arg_0]
0x1800183c4  add     rsp, 20h
0x1800183c8  pop     rdi
0x1800183c9  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
