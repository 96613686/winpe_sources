# std::_Copy_memmove<ushort *,ushort *>(ushort *,ushort *,ushort *)

- ea: `0x180009b60`
- end: `0x180009b90`
- name: `??$_Copy_memmove@PEAGPEAG@std@@YAPEAGPEAG00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a310`
- `0x18000a84c`

## callees

- `0x1800139ec`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<unsigned short *,unsigned short *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180009b60  mov     [rsp+arg_0], rbx
0x180009b65  push    rdi
0x180009b66  sub     rsp, 20h
0x180009b6a  mov     rbx, rdx
0x180009b6d  mov     rdi, r8
0x180009b70  sub     rbx, rcx
0x180009b73  mov     rdx, rcx; Src
0x180009b76  mov     r8, rbx; Size
0x180009b79  mov     rcx, rdi; void *
0x180009b7c  call    memmove_0
0x180009b81  lea     rax, [rbx+rdi]
0x180009b85  mov     rbx, [rsp+28h+arg_0]
0x180009b8a  add     rsp, 20h
0x180009b8e  pop     rdi
0x180009b8f  retn
```
