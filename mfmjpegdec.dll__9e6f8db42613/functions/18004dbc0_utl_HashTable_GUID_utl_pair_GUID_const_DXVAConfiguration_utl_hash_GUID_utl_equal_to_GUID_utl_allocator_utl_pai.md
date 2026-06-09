# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::pair<_GUID const,DXVAConfiguration> const &>(utl::pair<_GUID const,DXVAConfiguration> const &)

- ea: `0x18004dbc0`
- end: `0x18004dc19`
- name: `??$_NewNodeConstruct@AEBU?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@AEBU?$pair@$$CBU_GUID@@UDXVAConfiguration@@@1@@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e054`

## callees

- `0x18004ae14`
- `0x18004ae48`
- `0x18004b1b0`
- `0x18004dbc0`
- `0x18004dc20`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::pair<_GUID const,DXVAConfiguration> const &>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rbx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1;
  utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNode<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(
    a1,
    &v7);
  LOBYTE(v4) = v7
            && (unsigned __int8)utl::allocator_traits<utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::construct<utl::pair<_GUID const,DXVAConfiguration>,utl::pair<_GUID const,DXVAConfiguration> const &>(
                                  v3,
                                  v7 + 24,
                                  a2);
  v5 = utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNodeCommit<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(
         v3,
         &v7,
         v4);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<enum DXGI_FORMAT>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<enum DXGI_FORMAT>>>(&v7);
  return v5;
}

```

## disassembly

```asm
0x18004dbc0  mov     [rsp+arg_0], rcx
0x18004dbc5  push    rbx
0x18004dbc6  sub     rsp, 20h
0x18004dbca  mov     rbx, rdx
0x18004dbcd  lea     rdx, [rsp+28h+arg_0]
0x18004dbd2  call    ??$_NewNode@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@@utl@@IEAA?AU?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@utl@@@1@XZ; utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNode<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(void)
0x18004dbd7  mov     rdx, [rsp+28h+arg_0]
0x18004dbdc  test    rdx, rdx
0x18004dbdf  jz      short loc_18004DBF6
0x18004dbe1  add     rdx, 18h
0x18004dbe5  mov     r8, rbx
0x18004dbe8  call    ??$construct@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@AEBU12@@?$allocator_traits@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@PEAU?$pair@$$CBU_GUID@@UDXVAConfiguration@@@1@AEBU31@@Z; utl::allocator_traits<utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::construct<utl::pair<_GUID const,DXVAConfiguration>,utl::pair<_GUID const,DXVAConfiguration> const &>(utl::allocator<utl::pair<_GUID const,DXVAConfiguration>> &,utl::pair<_GUID const,DXVAConfiguration> *,utl::pair<_GUID const,DXVAConfiguration> const &)
0x18004dbed  test    al, al
0x18004dbef  jz      short loc_18004DBF6
0x18004dbf1  mov     r8b, 1
0x18004dbf4  jmp     short loc_18004DBF9
0x18004dbf6  xor     r8b, r8b
0x18004dbf9  lea     rdx, [rsp+28h+arg_0]
0x18004dbfe  call    ??$_NewNodeCommit@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@@utl@@IEAAPEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@AEAU?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@utl@@@1@_N@Z; utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNodeCommit<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>> &,bool)
0x18004dc03  lea     rcx, [rsp+28h+arg_0]
0x18004dc08  mov     rbx, rax
0x18004dc0b  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@W4DXGI_FORMAT@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<DXGI_FORMAT>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<DXGI_FORMAT>>>(void)
0x18004dc10  mov     rax, rbx
0x18004dc13  add     rsp, 20h
0x18004dc17  pop     rbx
0x18004dc18  retn
```
