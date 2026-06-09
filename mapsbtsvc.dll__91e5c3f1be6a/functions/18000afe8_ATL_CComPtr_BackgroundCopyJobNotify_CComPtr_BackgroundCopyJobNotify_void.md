# ATL::CComPtr<BackgroundCopyJobNotify>::~CComPtr<BackgroundCopyJobNotify>(void)

- ea: `0x18000afe8`
- end: `0x18000afed`
- name: `??1?$CComPtr@VBackgroundCopyJobNotify@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800142dd`

## callees

- `0x18000aff4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<BackgroundCopyJobNotify>::~CComPtr<BackgroundCopyJobNotify>(__int64 a1)
{
  return ATL::CComPtrBase<BackgroundCopyJobNotify>::~CComPtrBase<BackgroundCopyJobNotify>(a1);
}

```

## disassembly

```asm
0x18000afe8  jmp     ??1?$CComPtrBase@VBackgroundCopyJobNotify@@@ATL@@QEAA@XZ; ATL::CComPtrBase<BackgroundCopyJobNotify>::~CComPtrBase<BackgroundCopyJobNotify>(void)
```
