# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_ClearList(void)

- ea: `0x180043114`
- end: `0x180043167`
- name: `?_ClearList@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180043194`
- `0x18004bcd4`

## callees

- `0x1800245f0`
- `0x180043114`
- `0x1800431f4`

## pseudocode

```c
void __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_ClearList(
        __int64 a1)
{
  __int64 *v2; // rdi
  __int64 *v3; // rdx
  __int64 v4; // rax

  while ( 1 )
  {
    v2 = *(__int64 **)a1;
    if ( *(_QWORD *)a1 == a1 )
      break;
    v3 = (__int64 *)v2[1];
    v4 = *v2;
    *v3 = *v2;
    *(_QWORD *)(v4 + 8) = v3;
    utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::clear(v2 + 90);
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  }
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x180043114  mov     [rsp+arg_0], rbx
0x180043119  push    rdi
0x18004311a  sub     rsp, 20h
0x18004311e  mov     rbx, rcx
0x180043121  mov     rdi, [rbx]
0x180043124  cmp     rdi, rbx
0x180043127  jz      short loc_180043154
0x180043129  mov     rdx, [rdi+8]
0x18004312d  lea     rcx, [rdi+2D0h]
0x180043134  mov     rax, [rdi]
0x180043137  mov     [rdx], rax
0x18004313a  mov     [rax+8], rdx
0x18004313e  call    ?clear@?$_Tree@W4DXGI_FORMAT@@W41@U?$less@W4DXGI_FORMAT@@@utl@@V?$allocator@W4DXGI_FORMAT@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<DXGI_FORMAT,DXGI_FORMAT,utl::less<DXGI_FORMAT>,utl::allocator<DXGI_FORMAT>,0>::clear(void)
0x180043143  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004314a  mov     rcx, rdi; void *
0x18004314d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180043152  jmp     short loc_180043121
0x180043154  mov     qword ptr [rbx+18h], 0
0x18004315c  mov     rbx, [rsp+28h+arg_0]
0x180043161  add     rsp, 20h
0x180043165  pop     rdi
0x180043166  retn
```
