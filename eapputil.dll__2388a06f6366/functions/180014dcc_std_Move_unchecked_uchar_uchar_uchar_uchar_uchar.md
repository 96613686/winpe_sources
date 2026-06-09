# std::_Move_unchecked<uchar *,uchar *>(uchar *,uchar *,uchar *)

- ea: `0x180014dcc`
- end: `0x180014dfc`
- name: `??$_Move_unchecked@PEAEPEAE@std@@YAPEAEPEAE00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800318b9`
- `0x18003192d`

## callees

- `0x180003942`

## pseudocode

```c
__int64 __fastcall std::_Move_unchecked<unsigned char *,unsigned char *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180014dcc  mov     [rsp+arg_0], rbx
0x180014dd1  push    rdi
0x180014dd2  sub     rsp, 20h
0x180014dd6  mov     rbx, rdx
0x180014dd9  mov     rdi, r8
0x180014ddc  sub     rbx, rcx
0x180014ddf  mov     rdx, rcx; Src
0x180014de2  mov     r8, rbx; Size
0x180014de5  mov     rcx, rdi; void *
0x180014de8  call    memmove_0
0x180014ded  lea     rax, [rbx+rdi]
0x180014df1  mov     rbx, [rsp+28h+arg_0]
0x180014df6  add     rsp, 20h
0x180014dfa  pop     rdi
0x180014dfb  retn
```
