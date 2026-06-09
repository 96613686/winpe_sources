# std::_Ref_count_obj2<Rpc::RpcClient>::_Delete_this(void)

- ea: `0x18000ba90`
- end: `0x18000baaf`
- name: `?_Delete_this@?$_Ref_count_obj2@VRpcClient@Rpc@@@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ba90`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<Rpc::RpcClient>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000ba90  sub     rsp, 28h
0x18000ba94  test    rcx, rcx
0x18000ba97  jz      short loc_18000BAAA
0x18000ba99  mov     rax, [rcx]
0x18000ba9c  mov     edx, 1
0x18000baa1  mov     rax, [rax+10h]
0x18000baa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baaa  add     rsp, 28h
0x18000baae  retn
```
