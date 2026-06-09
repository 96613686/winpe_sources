# std::_Copy_memmove<uchar *,uchar *>(uchar *,uchar *,uchar *)

- ea: `0x18000e708`
- end: `0x18000e738`
- name: `??$_Copy_memmove@PEAEPEAE@std@@YAPEAEPEAE00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e6cc`
- `0x18001df78`

## callees

- `0x180024404`

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
0x18000e708  mov     [rsp+arg_0], rbx
0x18000e70d  push    rdi
0x18000e70e  sub     rsp, 20h
0x18000e712  mov     rbx, rdx
0x18000e715  mov     rdi, r8
0x18000e718  sub     rbx, rcx
0x18000e71b  mov     rdx, rcx; Src
0x18000e71e  mov     r8, rbx; Size
0x18000e721  mov     rcx, rdi; void *
0x18000e724  call    memmove_0
0x18000e729  lea     rax, [rbx+rdi]
0x18000e72d  mov     rbx, [rsp+28h+arg_0]
0x18000e732  add     rsp, 20h
0x18000e736  pop     rdi
0x18000e737  retn
```
