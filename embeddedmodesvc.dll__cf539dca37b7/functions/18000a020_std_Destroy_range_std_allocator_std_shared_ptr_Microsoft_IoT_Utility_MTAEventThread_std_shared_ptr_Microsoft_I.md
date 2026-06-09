# std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> *,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>> &)

- ea: `0x18000a020`
- end: `0x18000a057`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@0@@Z`
- size: `55`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000abc4`
- `0x18000adbc`
- `0x18000cee0`
- `0x18000d0ec`
- `0x18000d580`
- `0x18000dd80`

## callees

- `0x18000a020`
- `0x18000c300`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  std::_Ref_count_base *v4; // rcx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(std::_Ref_count_base **)(v3 + 8);
      if ( v4 )
        std::_Ref_count_base::_Decref(v4);
      v3 += 16;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x18000a020  cmp     rcx, rdx
0x18000a023  jz      short locret_18000A056
0x18000a025  mov     [rsp+arg_0], rbx
0x18000a02a  push    rdi
0x18000a02b  sub     rsp, 20h
0x18000a02f  mov     rdi, rdx
0x18000a032  mov     rbx, rcx
0x18000a035  mov     rcx, [rbx+8]; this
0x18000a039  test    rcx, rcx
0x18000a03c  jz      short loc_18000A043
0x18000a03e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a043  add     rbx, 10h
0x18000a047  cmp     rbx, rdi
0x18000a04a  jnz     short loc_18000A035
0x18000a04c  mov     rbx, [rsp+28h+arg_0]
0x18000a051  add     rsp, 20h
0x18000a055  pop     rdi
0x18000a056  retn
```
