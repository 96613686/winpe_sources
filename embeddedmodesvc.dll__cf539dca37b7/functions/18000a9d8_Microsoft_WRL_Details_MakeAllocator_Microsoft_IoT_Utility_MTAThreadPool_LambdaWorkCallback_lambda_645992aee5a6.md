# Microsoft::WRL::Details::MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____

- ea: `0x18000a9d8`
- end: `0x18000a9ee`
- name: `Microsoft::WRL::Details::MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009a90`
- `0x18000c888`
- `0x18000f304`
- `0x18000f3a8`

## callees

- `0x180002f84`
- `0x18000a9d8`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000a9d8  sub     rsp, 28h
0x18000a9dc  mov     rcx, [rcx]; Block
0x18000a9df  test    rcx, rcx
0x18000a9e2  jz      short loc_18000A9E9
0x18000a9e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a9e9  add     rsp, 28h
0x18000a9ed  retn
```
