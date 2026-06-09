# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x1800180c0`
- end: `0x1800180f4`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800025a0`
- `0x180016fb0`
- `0x1800180c0`

## pseudocode

```c
void *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800180c0  mov     [rsp+arg_0], rbx
0x1800180c5  push    rdi
0x1800180c6  sub     rsp, 20h
0x1800180ca  mov     ebx, edx
0x1800180cc  mov     rdi, rcx
0x1800180cf  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)
0x1800180d4  test    bl, 1
0x1800180d7  jz      short loc_1800180E6
0x1800180d9  mov     edx, 50h ; 'P'; unsigned __int64
0x1800180de  mov     rcx, rdi; void *
0x1800180e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800180e6  mov     rbx, [rsp+28h+arg_0]
0x1800180eb  mov     rax, rdi
0x1800180ee  add     rsp, 20h
0x1800180f2  pop     rdi
0x1800180f3  retn
```
