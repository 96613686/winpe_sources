# KerbReferenceContext

- ea: `0x140025df0`
- end: `0x140025e20`
- name: `KerbReferenceContext`
- size: `48`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140020920`
- `0x140020ce0`
- `0x140025cf0`
- `0x1400263c0`
- `0x140026a00`
- `0x140026ad0`
- `0x140026ba0`
- `0x140026c70`
- `0x140030100`

## callees

- `0x140010240`

## pseudocode

```c
__int64 __fastcall KerbReferenceContext(__int64 a1, unsigned __int8 a2)
{
  __int64 v2; // rbx

  v2 = a1;
  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD))xmmword_140018CB0)(a1, 1112687947, a2) < 0 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x140025df0  push    rbx
0x140025df2  sub     rsp, 20h
0x140025df6  mov     rax, qword ptr cs:xmmword_140018CB0
0x140025dfd  movzx   r8d, dl
0x140025e01  mov     edx, 4252454Bh
0x140025e06  mov     rbx, rcx
0x140025e09  call    _guard_dispatch_icall
0x140025e0e  xor     ecx, ecx
0x140025e10  test    eax, eax
0x140025e12  cmovs   rbx, rcx
0x140025e16  mov     rax, rbx
0x140025e19  add     rsp, 20h
0x140025e1d  pop     rbx
0x140025e1e  retn
```
