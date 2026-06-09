# DiscpInsertTargetList

- ea: `0x1800078ac`
- end: `0x1800078f8`
- name: `DiscpInsertTargetList`
- size: `76`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cbc`
- `0x180005098`
- `0x180009358`
- `0x180013a1c`

## callees

- `0x1800076dc`
- `0x1800078ac`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x1800078dd`
- `ISCSIUM!DiscpFreeMemory` at `0x1800078dd`

## pseudocode

```c
void __fastcall DiscpInsertTargetList(_QWORD **a1)
{
  _QWORD *v1; // rbx
  __int64 v3; // rsi

  v1 = *a1;
  while ( v1 != a1 )
  {
    v3 = (__int64)v1;
    v1 = (_QWORD *)*v1;
    if ( (unsigned int)DiscpInsertTarget(v3, 1) )
      DiscpFreeMemory(v3);
  }
}

```

## disassembly

```asm
0x1800078ac  mov     [rsp+arg_0], rbx
0x1800078b1  mov     [rsp+arg_8], rsi
0x1800078b6  push    rdi
0x1800078b7  sub     rsp, 20h
0x1800078bb  mov     rbx, [rcx]
0x1800078be  mov     rdi, rcx
0x1800078c1  cmp     rbx, rcx
0x1800078c4  jz      short loc_1800078E8
0x1800078c6  mov     rsi, rbx
0x1800078c9  mov     dl, 1
0x1800078cb  mov     rbx, [rbx]
0x1800078ce  mov     rcx, rsi
0x1800078d1  call    DiscpInsertTarget
0x1800078d6  test    eax, eax
0x1800078d8  jz      short loc_1800078E3
0x1800078da  mov     rcx, rsi
0x1800078dd  call    cs:__imp_DiscpFreeMemory
0x1800078e3  cmp     rbx, rdi
0x1800078e6  jnz     short loc_1800078C6
0x1800078e8  mov     rbx, [rsp+28h+arg_0]
0x1800078ed  mov     rsi, [rsp+28h+arg_8]
0x1800078f2  add     rsp, 20h
0x1800078f6  pop     rdi
0x1800078f7  retn
```
