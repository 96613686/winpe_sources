# ATL::CComCreator<ATL::CComAggObject<CServiceProvider>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006b90`
- end: `0x180006c99`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCServiceProvider@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006990`

## callees

- `0x1800019d4`
- `0x180006b90`
- `0x180006f6c`
- `0x1800098c8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CServiceProvider>>::CreateInstance(
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
  v8 = operator new(0xC8u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CServiceProvider>::`vftable';
    CServiceProvider::CServiceProvider((CServiceProvider *)(v8 + 6));
    v10 = ATL::_pAtlModule;
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IPNPXDeviceAssociation'};
    *((_QWORD *)v9 + 4) = &ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IPNPXAssociation'};
    *((_QWORD *)v9 + 5) = &ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IPNPXAssociationAsync'};
    *((_QWORD *)v9 + 6) = &ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IFunctionDiscoveryServiceProvider'};
    *((_QWORD *)v9 + 7) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v9 + 16));
    if ( v11 >= 0 )
      *((_BYTE *)v9 + 104) = 1;
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
0x180006b90  push    rbx
0x180006b92  push    rbp
0x180006b93  push    rsi
0x180006b94  push    rdi
0x180006b95  push    r14
0x180006b97  sub     rsp, 20h
0x180006b9b  mov     rsi, r8
0x180006b9e  mov     rbp, rdx
0x180006ba1  mov     r14, rcx
0x180006ba4  test    r8, r8
0x180006ba7  jnz     short loc_180006BB3
0x180006ba9  mov     eax, 80004003h
0x180006bae  jmp     loc_180006C8E
0x180006bb3  mov     ecx, 0C8h; Size
0x180006bb8  mov     qword ptr [r8], 0
0x180006bbf  mov     ebx, 8007000Eh
0x180006bc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006bc9  mov     rdi, rax
0x180006bcc  test    rax, rax
0x180006bcf  jz      loc_180006C8C
0x180006bd5  mov     dword ptr [rax+8], 0
0x180006bdc  lea     rcx, [rdi+18h]; this
0x180006be0  lea     rax, ??_7?$CComAggObject@VCServiceProvider@@@ATL@@6B@; const ATL::CComAggObject<CServiceProvider>::`vftable'
0x180006be7  mov     [rdi], rax
0x180006bea  call    ??0CServiceProvider@@QEAA@XZ; CServiceProvider::CServiceProvider(void)
0x180006bef  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006bf6  lea     rax, ??_7?$CComContainedObject@VCServiceProvider@@@ATL@@6BIPNPXDeviceAssociation@@@; const ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IPNPXDeviceAssociation'}
0x180006bfd  mov     [rdi+18h], rax
0x180006c01  lea     rax, ??_7?$CComContainedObject@VCServiceProvider@@@ATL@@6BIPNPXAssociation@@@; const ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IPNPXAssociation'}
0x180006c08  mov     [rdi+20h], rax
0x180006c0c  lea     rax, ??_7?$CComContainedObject@VCServiceProvider@@@ATL@@6BIPNPXAssociationAsync@@@; const ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IPNPXAssociationAsync'}
0x180006c13  mov     [rdi+28h], rax
0x180006c17  lea     rax, ??_7?$CComContainedObject@VCServiceProvider@@@ATL@@6BIFunctionDiscoveryServiceProvider@@@; const ATL::CComContainedObject<CServiceProvider>::`vftable'{for `IFunctionDiscoveryServiceProvider'}
0x180006c1e  mov     [rdi+30h], rax
0x180006c22  mov     [rdi+38h], r14
0x180006c26  mov     rax, [rcx]
0x180006c29  mov     rax, [rax+8]
0x180006c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c32  lea     rcx, [rdi+40h]; this
0x180006c36  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006c3b  mov     ecx, eax
0x180006c3d  test    eax, eax
0x180006c3f  js      short loc_180006C45
0x180006c41  mov     byte ptr [rdi+68h], 1
0x180006c45  xor     eax, eax
0x180006c47  test    ecx, ecx
0x180006c49  cmovs   eax, ecx
0x180006c4c  xor     ecx, ecx
0x180006c4e  test    eax, eax
0x180006c50  cmovs   ecx, eax
0x180006c53  xor     ebx, ebx
0x180006c55  test    ecx, ecx
0x180006c57  cmovs   ebx, ecx
0x180006c5a  test    ebx, ebx
0x180006c5c  jnz     short loc_180006C78
0x180006c5e  mov     rax, [rdi]
0x180006c61  mov     r8, rsi
0x180006c64  mov     rdx, rbp
0x180006c67  mov     rcx, rdi
0x180006c6a  mov     rax, [rax]
0x180006c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c72  mov     ebx, eax
0x180006c74  test    eax, eax
0x180006c76  jz      short loc_180006C8C
0x180006c78  mov     rcx, [rdi]
0x180006c7b  mov     edx, 1
0x180006c80  mov     rax, [rcx+18h]
0x180006c84  mov     rcx, rdi
0x180006c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8c  mov     eax, ebx
0x180006c8e  add     rsp, 20h
0x180006c92  pop     r14
0x180006c94  pop     rdi
0x180006c95  pop     rsi
0x180006c96  pop     rbp
0x180006c97  pop     rbx
0x180006c98  retn
```
