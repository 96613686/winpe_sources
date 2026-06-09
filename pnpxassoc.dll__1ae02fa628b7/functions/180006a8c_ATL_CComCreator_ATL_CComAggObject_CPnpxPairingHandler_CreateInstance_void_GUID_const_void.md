# ATL::CComCreator<ATL::CComAggObject<CPnpxPairingHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006a8c`
- end: `0x180006b8a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPnpxPairingHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006890`

## callees

- `0x1800019d4`
- `0x180006a8c`
- `0x180006f6c`
- `0x18000d500`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPnpxPairingHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  struct ATL::CAtlModule *v10; // rcx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x98u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CPnpxPairingHandler>::`vftable';
    CPnpxPairingHandler::CPnpxPairingHandler((CPnpxPairingHandler *)(v8 + 6));
    v10 = ATL::_pAtlModule;
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryServiceProvider'};
    *((_QWORD *)v9 + 4) = &ATL::CComContainedObject<CPnpxPairingHandler>::`vftable'{for `IPairingHandler'};
    *((_QWORD *)v9 + 5) = &ATL::CComContainedObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryNotification'};
    *((_QWORD *)v9 + 6) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v9 + 14));
    if ( v11 >= 0 )
      *((_BYTE *)v9 + 96) = 1;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v7 = 0;
    if ( v13 < 0 )
      v7 = v13;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180006a8c  push    rbx
0x180006a8e  push    rbp
0x180006a8f  push    rsi
0x180006a90  push    rdi
0x180006a91  push    r14
0x180006a93  sub     rsp, 20h
0x180006a97  mov     rsi, r8
0x180006a9a  mov     rbp, rdx
0x180006a9d  mov     r14, rcx
0x180006aa0  test    r8, r8
0x180006aa3  jnz     short loc_180006AAF
0x180006aa5  mov     eax, 80004003h
0x180006aaa  jmp     loc_180006B7F
0x180006aaf  mov     ecx, 98h; Size
0x180006ab4  mov     qword ptr [r8], 0
0x180006abb  mov     ebx, 8007000Eh
0x180006ac0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ac5  mov     rdi, rax
0x180006ac8  test    rax, rax
0x180006acb  jz      loc_180006B7D
0x180006ad1  mov     dword ptr [rax+8], 0
0x180006ad8  lea     rcx, [rdi+18h]; this
0x180006adc  lea     rax, ??_7?$CComAggObject@VCPnpxPairingHandler@@@ATL@@6B@; const ATL::CComAggObject<CPnpxPairingHandler>::`vftable'
0x180006ae3  mov     [rdi], rax
0x180006ae6  call    ??0CPnpxPairingHandler@@QEAA@XZ; CPnpxPairingHandler::CPnpxPairingHandler(void)
0x180006aeb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006af2  lea     rax, ??_7?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@6BIFunctionDiscoveryServiceProvider@@@; const ATL::CComContainedObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryServiceProvider'}
0x180006af9  mov     [rdi+18h], rax
0x180006afd  lea     rax, ??_7?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@6BIPairingHandler@@@; const ATL::CComContainedObject<CPnpxPairingHandler>::`vftable'{for `IPairingHandler'}
0x180006b04  mov     [rdi+20h], rax
0x180006b08  lea     rax, ??_7?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@6BIFunctionDiscoveryNotification@@@; const ATL::CComContainedObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryNotification'}
0x180006b0f  mov     [rdi+28h], rax
0x180006b13  mov     [rdi+30h], r14
0x180006b17  mov     rax, [rcx]
0x180006b1a  mov     rax, [rax+8]
0x180006b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b23  lea     rcx, [rdi+38h]; this
0x180006b27  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006b2c  mov     ecx, eax
0x180006b2e  test    eax, eax
0x180006b30  js      short loc_180006B36
0x180006b32  mov     byte ptr [rdi+60h], 1
0x180006b36  xor     eax, eax
0x180006b38  test    ecx, ecx
0x180006b3a  cmovs   eax, ecx
0x180006b3d  xor     ecx, ecx
0x180006b3f  test    eax, eax
0x180006b41  cmovs   ecx, eax
0x180006b44  xor     ebx, ebx
0x180006b46  test    ecx, ecx
0x180006b48  cmovs   ebx, ecx
0x180006b4b  test    ebx, ebx
0x180006b4d  jnz     short loc_180006B69
0x180006b4f  mov     rax, [rdi]
0x180006b52  mov     r8, rsi
0x180006b55  mov     rdx, rbp
0x180006b58  mov     rcx, rdi
0x180006b5b  mov     rax, [rax]
0x180006b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b63  mov     ebx, eax
0x180006b65  test    eax, eax
0x180006b67  jz      short loc_180006B7D
0x180006b69  mov     rcx, [rdi]
0x180006b6c  mov     edx, 1
0x180006b71  mov     rax, [rcx+18h]
0x180006b75  mov     rcx, rdi
0x180006b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7d  mov     eax, ebx
0x180006b7f  add     rsp, 20h
0x180006b83  pop     r14
0x180006b85  pop     rdi
0x180006b86  pop     rsi
0x180006b87  pop     rbp
0x180006b88  pop     rbx
0x180006b89  retn
```
