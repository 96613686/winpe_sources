# BackgroundCopyJobNotify::WorkerThreadParam::~WorkerThreadParam(void)

- ea: `0x18001224c`
- end: `0x18001227a`
- name: `??1WorkerThreadParam@BackgroundCopyJobNotify@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(BackgroundCopyJobNotify::WorkerThreadParam *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012280`

## callees

- `0x1800033d4`
- `0x180005b9c`
- `0x18001224c`

## pseudocode

```c
void __fastcall BackgroundCopyJobNotify::WorkerThreadParam::~WorkerThreadParam(
        BackgroundCopyJobNotify::WorkerThreadParam *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 1);
}

```

## disassembly

```asm
0x18001224c  push    rbx
0x18001224e  sub     rsp, 20h
0x180012252  mov     rbx, rcx
0x180012255  mov     rcx, [rcx+20h]; this
0x180012259  test    rcx, rcx
0x18001225c  jz      short loc_180012263
0x18001225e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180012263  lea     rcx, [rbx+10h]
0x180012267  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001226c  lea     rcx, [rbx+8]
0x180012270  add     rsp, 20h
0x180012274  pop     rbx
0x180012275  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
