# KerbDereferenceContext

- ea: `0x140025e28`
- end: `0x140025e5d`
- name: `KerbDereferenceContext`
- size: `53`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x140020920`
- `0x1400209a0`
- `0x140020b90`
- `0x140020ce0`
- `0x140025cf0`
- `0x1400263c0`
- `0x140026a00`
- `0x140026ad0`
- `0x140026ba0`
- `0x140026c70`
- `0x140030100`

## callees

- `0x140004c00`
- `0x140010240`
- `0x140025e28`

## pseudocode

```c
void __fastcall KerbDereferenceContext(PVOID P)
{
  char v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  (*((void (__fastcall **)(PVOID, char *))&xmmword_140018CB0 + 1))(P, &v2);
  if ( v2 )
    KerbFreeContext(P);
}

```

## disassembly

```asm
0x140025e28  push    rbx
0x140025e2a  sub     rsp, 20h
0x140025e2e  mov     rax, qword ptr cs:xmmword_140018CB0+8
0x140025e35  lea     rdx, [rsp+28h+arg_8]
0x140025e3a  mov     rbx, rcx
0x140025e3d  mov     [rsp+28h+arg_8], 0
0x140025e42  call    _guard_dispatch_icall
0x140025e47  cmp     [rsp+28h+arg_8], 0
0x140025e4c  jz      short loc_140025E56
0x140025e4e  mov     rcx, rbx; P
0x140025e51  call    ?KerbFreeContext@@YAXPEAU_KERB_KERNEL_CONTEXT@@@Z; KerbFreeContext(_KERB_KERNEL_CONTEXT *)
0x140025e56  add     rsp, 20h
0x140025e5a  pop     rbx
0x140025e5b  retn
```
