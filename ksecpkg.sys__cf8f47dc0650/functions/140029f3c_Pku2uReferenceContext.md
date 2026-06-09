# Pku2uReferenceContext

- ea: `0x140029f3c`
- end: `0x140029f6b`
- name: `Pku2uReferenceContext`
- size: `47`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000db50`
- `0x140021d20`
- `0x140022150`
- `0x140028fb0`
- `0x1400290b0`
- `0x1400291a0`
- `0x140029690`
- `0x140029780`
- `0x140029870`

## callees

- `0x140010240`

## pseudocode

```c
__int64 __fastcall Pku2uReferenceContext(__int64 a1, char a2, __int64 a3)
{
  __int64 v3; // rbx

  LOBYTE(a3) = a2;
  v3 = a1;
  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64))xmmword_140019070)(a1, 1112687947, a3) < 0 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x140029f3c  push    rbx
0x140029f3e  sub     rsp, 20h
0x140029f42  mov     rax, qword ptr cs:xmmword_140019070
0x140029f49  mov     r8b, dl
0x140029f4c  mov     edx, 4252454Bh
0x140029f51  mov     rbx, rcx
0x140029f54  call    _guard_dispatch_icall
0x140029f59  xor     edx, edx
0x140029f5b  test    eax, eax
0x140029f5d  cmovs   rbx, rdx
0x140029f61  mov     rax, rbx
0x140029f64  add     rsp, 20h
0x140029f68  pop     rbx
0x140029f69  retn
```
