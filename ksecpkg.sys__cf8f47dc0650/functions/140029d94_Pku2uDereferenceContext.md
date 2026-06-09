# Pku2uDereferenceContext

- ea: `0x140029d94`
- end: `0x140029dc9`
- name: `Pku2uDereferenceContext`
- size: `53`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x14000db50`
- `0x140021d20`
- `0x140021db0`
- `0x140022010`
- `0x140022150`
- `0x140028fb0`
- `0x1400290b0`
- `0x1400291a0`
- `0x140029690`
- `0x140029780`
- `0x140029870`

## callees

- `0x14000dca8`
- `0x140010240`
- `0x140029d94`

## pseudocode

```c
__int64 __fastcall Pku2uDereferenceContext(PVOID P)
{
  __int64 result; // rax
  char v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  result = (*((__int64 (__fastcall **)(PVOID, char *))&xmmword_140019070 + 1))(P, &v3);
  if ( v3 )
    return Pku2uFreeContext(P);
  return result;
}

```

## disassembly

```asm
0x140029d94  push    rbx
0x140029d96  sub     rsp, 20h
0x140029d9a  mov     rax, qword ptr cs:xmmword_140019070+8
0x140029da1  lea     rdx, [rsp+28h+arg_8]
0x140029da6  mov     rbx, rcx
0x140029da9  mov     [rsp+28h+arg_8], 0
0x140029dae  call    _guard_dispatch_icall
0x140029db3  cmp     [rsp+28h+arg_8], 0
0x140029db8  jz      short loc_140029DC2
0x140029dba  mov     rcx, rbx; P
0x140029dbd  call    Pku2uFreeContext
0x140029dc2  add     rsp, 20h
0x140029dc6  pop     rbx
0x140029dc7  retn
```
