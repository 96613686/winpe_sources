# std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam,std::default_delete<BackgroundCopyJobNotify::WorkerThreadParam>>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam,std::default_delete<BackgroundCopyJobNotify::WorkerThreadParam>>(void)

- ea: `0x180012230`
- end: `0x180012246`
- name: `??1?$unique_ptr@UWorkerThreadParam@BackgroundCopyJobNotify@@U?$default_delete@UWorkerThreadParam@BackgroundCopyJobNotify@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800122d0`
- `0x1800128a0`
- `0x180012a70`
- `0x180014857`

## callees

- `0x180012230`
- `0x180012280`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<BackgroundCopyJobNotify::WorkerThreadParam>::operator()();
  return result;
}

```

## disassembly

```asm
0x180012230  sub     rsp, 28h
0x180012234  mov     rdx, [rcx]
0x180012237  test    rdx, rdx
0x18001223a  jz      short loc_180012241
0x18001223c  call    ??R?$default_delete@UWorkerThreadParam@BackgroundCopyJobNotify@@@std@@QEBAXPEAUWorkerThreadParam@BackgroundCopyJobNotify@@@Z; std::default_delete<BackgroundCopyJobNotify::WorkerThreadParam>::operator()(BackgroundCopyJobNotify::WorkerThreadParam *)
0x180012241  add     rsp, 28h
0x180012245  retn
```
