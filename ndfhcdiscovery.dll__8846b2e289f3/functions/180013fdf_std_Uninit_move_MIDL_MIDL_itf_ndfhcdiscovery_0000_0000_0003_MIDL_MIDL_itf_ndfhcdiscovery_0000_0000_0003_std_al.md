# _std::_Uninit_move___MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003_____MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003___std::allocator___MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003____MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003__::_1_::catch$0

- ea: `0x180013fdf`
- end: `0x180013ff6`
- name: `_std::_Uninit_move___MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003_____MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003___std::allocator___MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003____MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003__::_1_::catch$0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001f9c`

## pseudocode

```c
void __noreturn std::_Uninit_move___MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003_____MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003___std::allocator___MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003____MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003__::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x180013fdf  mov     [rsp+arg_8], rdx
0x180013fe4  push    rbp
0x180013fe5  sub     rsp, 20h
0x180013fe9  mov     rbp, rdx
0x180013fec  xor     edx, edx; pThrowInfo
0x180013fee  xor     ecx, ecx; pExceptionObject
0x180013ff0  call    _CxxThrowException_0
```
