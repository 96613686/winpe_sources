# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)

- ea: `0x180016fb0`
- end: `0x180016fef`
- name: `??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016f34`
- `0x1800180c0`
- `0x18002d9cc`

## callees

- `0x180016fb0`
- `0x18001db20`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 v4; // rcx

  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 < 0 )
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v2);
  v4 = *(_QWORD *)(a1 + 56);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 56) = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return result;
}

```

## disassembly

```asm
0x180016fb0  push    rbx
0x180016fb2  sub     rsp, 20h
0x180016fb6  mov     rbx, rcx
0x180016fb9  mov     rcx, [rcx+48h]
0x180016fbd  test    rcx, rcx
0x180016fc0  jns     short loc_180016FCB
0x180016fc2  add     rcx, rcx
0x180016fc5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180016fca  nop
0x180016fcb  mov     rcx, [rbx+38h]
0x180016fcf  test    rcx, rcx
0x180016fd2  jz      short loc_180016FE9
0x180016fd4  mov     qword ptr [rbx+38h], 0
0x180016fdc  mov     rax, [rcx]
0x180016fdf  mov     rax, [rax+10h]
0x180016fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe8  nop
0x180016fe9  add     rsp, 20h
0x180016fed  pop     rbx
0x180016fee  retn
```
