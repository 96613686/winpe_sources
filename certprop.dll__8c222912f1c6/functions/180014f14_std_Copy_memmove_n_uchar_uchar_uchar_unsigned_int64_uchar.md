# std::_Copy_memmove_n<uchar *,uchar *>(uchar *,unsigned __int64,uchar *)

- ea: `0x180014f14`
- end: `0x180014f41`
- name: `??$_Copy_memmove_n@PEAEPEAE@std@@YAPEAEPEAE_K0@Z`
- size: `45`
- prototype: `__int64 __fastcall(void *Src, size_t Size, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014e88`

## callees

- `0x180024404`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_n<unsigned char *,unsigned char *>(void *Src, size_t Size, void *a3)
{
  memmove_0(a3, Src, Size);
  return (__int64)a3 + Size;
}

```

## disassembly

```asm
0x180014f14  mov     [rsp+arg_0], rbx
0x180014f19  push    rdi
0x180014f1a  sub     rsp, 20h
0x180014f1e  mov     rdi, r8
0x180014f21  mov     rbx, rdx
0x180014f24  mov     r8, rdx; Size
0x180014f27  mov     rdx, rcx; Src
0x180014f2a  mov     rcx, rdi; void *
0x180014f2d  call    memmove_0
0x180014f32  lea     rax, [rbx+rdi]
0x180014f36  mov     rbx, [rsp+28h+arg_0]
0x180014f3b  add     rsp, 20h
0x180014f3f  pop     rdi
0x180014f40  retn
```
