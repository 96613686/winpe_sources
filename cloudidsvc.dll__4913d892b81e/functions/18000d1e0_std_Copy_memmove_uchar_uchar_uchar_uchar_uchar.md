# std::_Copy_memmove<uchar *,uchar *>(uchar *,uchar *,uchar *)

- ea: `0x18000d1e0`
- end: `0x18000d210`
- name: `??$_Copy_memmove@PEAEPEAE@std@@YAPEAEPEAE00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d494`
- `0x18000db48`

## callees

- `0x180010780`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<unsigned char *,unsigned char *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x18000d1e0  mov     [rsp+arg_0], rbx
0x18000d1e5  push    rdi
0x18000d1e6  sub     rsp, 20h
0x18000d1ea  mov     rbx, rdx
0x18000d1ed  mov     rdi, r8
0x18000d1f0  sub     rbx, rcx
0x18000d1f3  mov     rdx, rcx; Src
0x18000d1f6  mov     r8, rbx; Size
0x18000d1f9  mov     rcx, rdi; void *
0x18000d1fc  call    memmove_0
0x18000d201  lea     rax, [rbx+rdi]
0x18000d205  mov     rbx, [rsp+28h+arg_0]
0x18000d20a  add     rsp, 20h
0x18000d20e  pop     rdi
0x18000d20f  retn
```
