# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::_PairMapTag,_GUID const &,DXVAConfiguration>(utl::_PairMapTag &&,_GUID const &,DXVAConfiguration &&)

- ea: `0x18004aed8`
- end: `0x18004af42`
- name: `??$_NewNodeConstruct@U_PairMapTag@utl@@AEBU_GUID@@UDXVAConfiguration@@@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@$$QEAU_PairMapTag@1@AEBU_GUID@@$$QEAUDXVAConfiguration@@@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bd00`
- `0x18004c424`

## callees

- `0x18004ae14`
- `0x18004ae48`
- `0x18004aed8`
- `0x18004b084`
- `0x18004b1b0`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::_PairMapTag,_GUID const &,DXVAConfiguration>(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4)
{
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = a2;
  utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNode<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(
    a1,
    &v10);
  v7 = v10;
  if ( v10 )
  {
    *(_OWORD *)(v10 + 24) = *a3;
    DXVAConfiguration::DXVAConfiguration(v7 + 40, a4);
    LOBYTE(v6) = 1;
  }
  else
  {
    LOBYTE(v6) = 0;
  }
  v8 = utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNodeCommit<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(
         v7,
         &v10,
         v6);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<enum DXGI_FORMAT>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<enum DXGI_FORMAT>>>(&v10);
  return v8;
}

```

## disassembly

```asm
0x18004aed8  mov     [rsp+arg_0], rbx
0x18004aedd  mov     [rsp+arg_8], rdx
0x18004aee2  push    rdi
0x18004aee3  sub     rsp, 20h
0x18004aee7  lea     rdx, [rsp+28h+arg_8]
0x18004aeec  mov     rbx, r9
0x18004aeef  mov     rdi, r8
0x18004aef2  call    ??$_NewNode@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@@utl@@IEAA?AU?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@utl@@@1@XZ; utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNode<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(void)
0x18004aef7  mov     rcx, [rsp+28h+arg_8]
0x18004aefc  test    rcx, rcx
0x18004aeff  jz      short loc_18004AF1A
0x18004af01  movups  xmm0, xmmword ptr [rdi]
0x18004af04  mov     rdx, rbx
0x18004af07  movdqu  xmmword ptr [rcx+18h], xmm0
0x18004af0c  add     rcx, 28h ; '('
0x18004af10  call    ??0DXVAConfiguration@@QEAA@$$QEAU0@@Z; DXVAConfiguration::DXVAConfiguration(DXVAConfiguration &&)
0x18004af15  mov     r8b, 1
0x18004af18  jmp     short loc_18004AF1D
0x18004af1a  xor     r8b, r8b
0x18004af1d  lea     rdx, [rsp+28h+arg_8]
0x18004af22  call    ??$_NewNodeCommit@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@@utl@@IEAAPEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@AEAU?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@utl@@@1@_N@Z; utl::_ContainerBase<utl::pair<_GUID const,DXVAConfiguration>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::_NewNodeCommit<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>(utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>>>> &,bool)
0x18004af27  lea     rcx, [rsp+28h+arg_8]
0x18004af2c  mov     rbx, rax
0x18004af2f  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@W4DXGI_FORMAT@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<DXGI_FORMAT>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<DXGI_FORMAT>>>(void)
0x18004af34  mov     rax, rbx
0x18004af37  mov     rbx, [rsp+28h+arg_0]
0x18004af3c  add     rsp, 20h
0x18004af40  pop     rdi
0x18004af41  retn
```
