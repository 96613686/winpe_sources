# ATL::CComPtrBase<BackgroundCopyJobNotify>::~CComPtrBase<BackgroundCopyJobNotify>(void)

- ea: `0x18000aff4`
- end: `0x18000b00a`
- name: `??1?$CComPtrBase@VBackgroundCopyJobNotify@@@ATL@@QEAA@XZ`
- size: `22`
- prototype: `unsigned int __fastcall(BackgroundCopyJobNotify **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000afe8`
- `0x18000b544`

## callees

- `0x18000aff4`
- `0x180012ca0`

## pseudocode

```c
unsigned int __fastcall ATL::CComPtrBase<BackgroundCopyJobNotify>::~CComPtrBase<BackgroundCopyJobNotify>(
        BackgroundCopyJobNotify **a1)
{
  BackgroundCopyJobNotify *v1; // rcx
  unsigned int result; // eax

  v1 = *a1;
  if ( v1 )
    return BackgroundCopyJobNotify::Release(v1);
  return result;
}

```

## disassembly

```asm
0x18000aff4  sub     rsp, 28h
0x18000aff8  mov     rcx, [rcx]; this
0x18000affb  test    rcx, rcx
0x18000affe  jz      short loc_18000B005
0x18000b000  call    ?Release@BackgroundCopyJobNotify@@UEAAKXZ; BackgroundCopyJobNotify::Release(void)
0x18000b005  add     rsp, 28h
0x18000b009  retn
```
