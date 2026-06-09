# std::default_delete<BackgroundCopyJobNotify::WorkerThreadParam>::operator()(BackgroundCopyJobNotify::WorkerThreadParam *)

- ea: `0x180012280`
- end: `0x1800122a3`
- name: `??R?$default_delete@UWorkerThreadParam@BackgroundCopyJobNotify@@@std@@QEBAXPEAUWorkerThreadParam@BackgroundCopyJobNotify@@@Z`
- size: `35`
- prototype: `void __fastcall(__int64, BackgroundCopyJobNotify::WorkerThreadParam *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180012230`

## callees

- `0x180001e54`
- `0x18001224c`
- `0x180012280`

## pseudocode

```c
void __fastcall std::default_delete<BackgroundCopyJobNotify::WorkerThreadParam>::operator()(
        __int64 a1,
        BackgroundCopyJobNotify::WorkerThreadParam *a2)
{
  if ( a2 )
  {
    BackgroundCopyJobNotify::WorkerThreadParam::~WorkerThreadParam(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180012280  test    rdx, rdx
0x180012283  jz      short locret_1800122A2
0x180012285  push    rbx
0x180012286  sub     rsp, 20h
0x18001228a  mov     rcx, rdx; this
0x18001228d  mov     rbx, rdx
0x180012290  call    ??1WorkerThreadParam@BackgroundCopyJobNotify@@QEAA@XZ; BackgroundCopyJobNotify::WorkerThreadParam::~WorkerThreadParam(void)
0x180012295  mov     rcx, rbx; Block
0x180012298  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001229d  add     rsp, 20h
0x1800122a1  pop     rbx
0x1800122a2  retn
```
