# std::default_delete<FveEasUtil>::operator()(FveEasUtil *)

- ea: `0x180023efc`
- end: `0x180023f24`
- name: `??R?$default_delete@VFveEasUtil@@@std@@QEBAXPEAVFveEasUtil@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, FveEasUtil *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800239c8`
- `0x180023a40`
- `0x180023dc0`

## callees

- `0x180001bd4`
- `0x180023ddc`
- `0x180023efc`

## pseudocode

```c
void __fastcall std::default_delete<FveEasUtil>::operator()(__int64 a1, FveEasUtil *a2)
{
  if ( a2 )
  {
    FveEasUtil::~FveEasUtil(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180023efc  test    rdx, rdx
0x180023eff  jz      short locret_180023F23
0x180023f01  push    rbx
0x180023f02  sub     rsp, 20h
0x180023f06  mov     rcx, rdx; this
0x180023f09  mov     rbx, rdx
0x180023f0c  call    ??1FveEasUtil@@QEAA@XZ; FveEasUtil::~FveEasUtil(void)
0x180023f11  mov     edx, 38h ; '8'; unsigned __int64
0x180023f16  mov     rcx, rbx; void *
0x180023f19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023f1e  add     rsp, 20h
0x180023f22  pop     rbx
0x180023f23  retn
```
