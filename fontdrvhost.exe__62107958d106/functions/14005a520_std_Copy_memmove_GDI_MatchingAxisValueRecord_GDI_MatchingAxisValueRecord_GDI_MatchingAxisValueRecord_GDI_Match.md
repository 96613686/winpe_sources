# std::_Copy_memmove<GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *>(GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *)

- ea: `0x14005a520`
- end: `0x14005a550`
- name: `??$_Copy_memmove@PEAUMatchingAxisValueRecord@GDI@@PEAU12@@std@@YAPEAUMatchingAxisValueRecord@GDI@@PEAU12@00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14005a4e0`
- `0x140093cb0`
- `0x140093d80`
- `0x140093e00`
- `0x140093ea8`
- `0x140093f90`
- `0x140094054`
- `0x14009414c`
- `0x140094378`
- `0x14009458c`
- `0x14009466c`

## callees

- `0x140076ef6`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *>(
        void *Src,
        __int64 a2,
        void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x14005a520  mov     [rsp+arg_0], rbx
0x14005a525  push    rdi
0x14005a526  sub     rsp, 20h
0x14005a52a  mov     rbx, rdx
0x14005a52d  mov     rdi, r8
0x14005a530  sub     rbx, rcx
0x14005a533  mov     rdx, rcx; Src
0x14005a536  mov     r8, rbx; Size
0x14005a539  mov     rcx, rdi; void *
0x14005a53c  call    memmove_0
0x14005a541  lea     rax, [rbx+rdi]
0x14005a545  mov     rbx, [rsp+28h+arg_0]
0x14005a54a  add     rsp, 20h
0x14005a54e  pop     rdi
0x14005a54f  retn
```
