# Microsoft::WRL::ComPtr_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_ComPtr_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____

- ea: `0x18000a99c`
- end: `0x18000a9c4`
- name: `Microsoft::WRL::ComPtr_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_ComPtr_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018e2a`
- `0x180019294`
- `0x1800192a6`
- `0x18001956f`

## callees

- `0x18000a99c`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_ComPtr_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000a99c  sub     rsp, 28h
0x18000a9a0  mov     rax, rcx
0x18000a9a3  mov     rcx, [rcx]
0x18000a9a6  test    rcx, rcx
0x18000a9a9  jz      short loc_18000A9BF
0x18000a9ab  mov     qword ptr [rax], 0
0x18000a9b2  mov     rax, [rcx]
0x18000a9b5  mov     rax, [rax+10h]
0x18000a9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9be  nop
0x18000a9bf  add     rsp, 28h
0x18000a9c3  retn
```
