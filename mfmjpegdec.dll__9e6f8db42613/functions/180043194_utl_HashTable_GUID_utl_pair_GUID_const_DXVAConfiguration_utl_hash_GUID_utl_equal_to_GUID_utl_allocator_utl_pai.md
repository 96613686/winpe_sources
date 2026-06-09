# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(void)

- ea: `0x180043194`
- end: `0x1800431af`
- name: `?_Uninit@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003f29c`
- `0x18004b21c`
- `0x18004e054`

## callees

- `0x180043114`
- `0x180043170`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(
        __int64 a1)
{
  utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_ClearList(a1);
  return utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FreeBuckets(a1);
}

```

## disassembly

```asm
0x180043194  push    rbx
0x180043196  sub     rsp, 20h
0x18004319a  mov     rbx, rcx
0x18004319d  call    ?_ClearList@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ
0x1800431a2  mov     rcx, rbx
0x1800431a5  add     rsp, 20h
0x1800431a9  pop     rbx
0x1800431aa  jmp     ?_FreeBuckets@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ
```
