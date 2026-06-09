# ATL::CComCreator<ATL::CComAggObject<CServicingSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000474c`
- end: `0x180004882`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCServicingSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800044d0`

## callees

- `0x180001a5c`
- `0x180002e04`
- `0x18000474c`
- `0x180004f34`
- `0x180023210`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CServicingSession>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax
  int v11; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x1C0u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CServicingSession>::`vftable';
    CServicingSession::CServicingSession((CServicingSession *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CServicingSession>::`vftable'{for `IFhEngineServicing'};
    v9[4] = &ATL::CComContainedObject<CServicingSession>::`vftable'{for `CSessionBaseRW'};
    v9[39] = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 40));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CServicingSession::FinalConstruct((CServicingSession *)(v9 + 3));
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000474c  mov     [rsp+arg_0], rbx
0x180004751  mov     [rsp+arg_10], r8
0x180004756  mov     [rsp+arg_8], rdx
0x18000475b  push    rsi
0x18000475c  push    rdi
0x18000475d  push    r12
0x18000475f  push    r14
0x180004761  push    r15
0x180004763  sub     rsp, 30h
0x180004767  mov     r14, r8
0x18000476a  mov     r15, rdx
0x18000476d  mov     r12, rcx
0x180004770  test    r8, r8
0x180004773  jnz     short loc_18000477F
0x180004775  mov     eax, 80004003h
0x18000477a  jmp     loc_180004870
0x18000477f  mov     qword ptr [r8], 0
0x180004786  mov     esi, 8007000Eh
0x18000478b  mov     [rsp+58h+arg_18], esi
0x18000478f  mov     [rsp+58h+var_38], 0
0x180004798  mov     ecx, 1C0h; Size
0x18000479d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047a2  mov     rdi, rax
0x1800047a5  test    rdi, rdi
0x1800047a8  jz      short loc_1800047F4
0x1800047aa  mov     dword ptr [rax+8], 0
0x1800047b1  lea     rax, ??_7?$CComAggObject@VCServicingSession@@@ATL@@6B@; const ATL::CComAggObject<CServicingSession>::`vftable'
0x1800047b8  mov     [rdi], rax
0x1800047bb  lea     rcx, [rdi+18h]; this
0x1800047bf  call    ??0CServicingSession@@QEAA@XZ; CServicingSession::CServicingSession(void)
0x1800047c4  lea     rax, ??_7?$CComContainedObject@VCServicingSession@@@ATL@@6BIFhEngineServicing@@@; const ATL::CComContainedObject<CServicingSession>::`vftable'{for `IFhEngineServicing'}
0x1800047cb  mov     [rdi+18h], rax
0x1800047cf  lea     rax, ??_7?$CComContainedObject@VCServicingSession@@@ATL@@6BCSessionBaseRW@@@; const ATL::CComContainedObject<CServicingSession>::`vftable'{for `CSessionBaseRW'}
0x1800047d6  mov     [rdi+20h], rax
0x1800047da  mov     [rdi+138h], r12
0x1800047e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800047e8  mov     rax, [rcx]
0x1800047eb  mov     rax, [rax+8]
0x1800047ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f4  mov     [rsp+58h+var_38], rdi
0x1800047f9  jmp     short loc_18000480E
0x1800047fb  mov     r14, [rsp+58h+arg_10]
0x180004800  mov     r15, [rsp+58h+arg_8]
0x180004805  mov     esi, [rsp+58h+arg_18]
0x180004809  mov     rdi, [rsp+58h+var_38]
0x18000480e  test    rdi, rdi
0x180004811  jz      short loc_18000486E
0x180004813  lea     rcx, [rdi+140h]; this
0x18000481a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000481f  xor     ecx, ecx
0x180004821  test    eax, eax
0x180004823  cmovs   ecx, eax
0x180004826  test    ecx, ecx
0x180004828  js      short loc_180004835
0x18000482a  lea     rcx, [rdi+18h]; this
0x18000482e  call    ?FinalConstruct@CServicingSession@@QEAAJXZ; CServicingSession::FinalConstruct(void)
0x180004833  mov     ecx, eax
0x180004835  xor     esi, esi
0x180004837  test    ecx, ecx
0x180004839  cmovs   esi, ecx
0x18000483c  test    esi, esi
0x18000483e  jnz     short loc_18000485A
0x180004840  mov     rax, [rdi]
0x180004843  mov     r8, r14
0x180004846  mov     rdx, r15
0x180004849  mov     rcx, rdi
0x18000484c  mov     rax, [rax]
0x18000484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004854  mov     esi, eax
0x180004856  test    eax, eax
0x180004858  jz      short loc_18000486E
0x18000485a  mov     rdx, [rdi]
0x18000485d  mov     rax, [rdx+18h]
0x180004861  mov     edx, 1
0x180004866  mov     rcx, rdi
0x180004869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000486e  mov     eax, esi
0x180004870  mov     rbx, [rsp+58h+arg_0]
0x180004875  add     rsp, 30h
0x180004879  pop     r15
0x18000487b  pop     r14
0x18000487d  pop     r12
0x18000487f  pop     rdi
0x180004880  pop     rsi
0x180004881  retn
```
