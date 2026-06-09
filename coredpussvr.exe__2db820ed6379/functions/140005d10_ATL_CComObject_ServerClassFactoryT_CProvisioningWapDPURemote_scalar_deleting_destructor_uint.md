# ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::`scalar deleting destructor'(uint)

- ea: `0x140005d10`
- end: `0x140005d6c`
- name: `??_G?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001794`
- `0x140005b08`
- `0x140005d10`
- `0x14000a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::`scalar deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ServerClassFactoryT<CProvisioningWapDPURemote>::~ServerClassFactoryT<CProvisioningWapDPURemote>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140005d10  mov     [rsp+arg_0], rbx
0x140005d15  push    rdi
0x140005d16  sub     rsp, 20h
0x140005d1a  mov     dword ptr [rcx+8], 0C0000001h
0x140005d21  lea     rax, ??_7?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@6B@; const ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::`vftable'
0x140005d28  mov     [rcx], rax
0x140005d2b  mov     rdi, rcx
0x140005d2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005d35  mov     ebx, edx
0x140005d37  mov     rax, [rcx]
0x140005d3a  mov     rax, [rax+10h]
0x140005d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d43  mov     rcx, rdi
0x140005d46  call    ??1?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@UEAA@XZ; ServerClassFactoryT<CProvisioningWapDPURemote>::~ServerClassFactoryT<CProvisioningWapDPURemote>(void)
0x140005d4b  test    bl, 1
0x140005d4e  jz      short loc_140005D5D
0x140005d50  mov     edx, 40h ; '@'
0x140005d55  mov     rcx, rdi; Block
0x140005d58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005d5d  mov     rbx, [rsp+28h+arg_0]
0x140005d62  mov     rax, rdi
0x140005d65  add     rsp, 20h
0x140005d69  pop     rdi
0x140005d6a  retn
```
