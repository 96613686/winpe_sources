# ATL::CComObject<CPnpxPairingHandler>::`vector deleting destructor'(uint)

- ea: `0x180005550`
- end: `0x1800055bc`
- name: `??_E?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAPEAXI@Z`
- size: `108`
- prototype: `__int64 __fastcall(CPnpxPairingHandler *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800019b0`
- `0x180005550`
- `0x18000d5b0`
- `0x180014010`

## pseudocode

```c
CPnpxPairingHandler *__fastcall ATL::CComObject<CPnpxPairingHandler>::`vector deleting destructor'(
        CPnpxPairingHandler *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryServiceProvider'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IPairingHandler'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryNotification'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CPnpxPairingHandler::~CPnpxPairingHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005550  mov     [rsp+arg_0], rbx
0x180005555  push    rdi
0x180005556  sub     rsp, 20h
0x18000555a  mov     dword ptr [rcx+18h], 0C0000001h
0x180005561  lea     rax, ??_7?$CComObject@VCPnpxPairingHandler@@@ATL@@6BIFunctionDiscoveryServiceProvider@@@; const ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryServiceProvider'}
0x180005568  mov     [rcx], rax
0x18000556b  mov     rdi, rcx
0x18000556e  lea     rax, ??_7?$CComObject@VCPnpxPairingHandler@@@ATL@@6BIPairingHandler@@@; const ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IPairingHandler'}
0x180005575  mov     ebx, edx
0x180005577  mov     [rcx+8], rax
0x18000557b  lea     rax, ??_7?$CComObject@VCPnpxPairingHandler@@@ATL@@6BIFunctionDiscoveryNotification@@@; const ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryNotification'}
0x180005582  mov     [rcx+10h], rax
0x180005586  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000558d  mov     rax, [rcx]
0x180005590  mov     rax, [rax+10h]
0x180005594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005599  mov     rcx, rdi; this
0x18000559c  call    ??1CPnpxPairingHandler@@UEAA@XZ; CPnpxPairingHandler::~CPnpxPairingHandler(void)
0x1800055a1  test    bl, 1
0x1800055a4  jz      short loc_1800055AE
0x1800055a6  mov     rcx, rdi; Block
0x1800055a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800055ae  mov     rbx, [rsp+28h+arg_0]
0x1800055b3  mov     rax, rdi
0x1800055b6  add     rsp, 20h
0x1800055ba  pop     rdi
0x1800055bb  retn
```
