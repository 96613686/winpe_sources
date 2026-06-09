# ATL::CComCreator<ATL::CComObject<CServicingSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004ac0`
- end: `0x180004bdc`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCServicingSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800044d0`

## callees

- `0x180001a5c`
- `0x180002e04`
- `0x180004ac0`
- `0x180004f34`
- `0x180006498`
- `0x1800064c0`
- `0x180023210`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CServicingSession>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CServicingSession *v7; // rax
  CServicingSession *v8; // rbx
  int v9; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CServicingSession *)operator new(0x1A8u);
  v8 = v7;
  if ( v7 )
  {
    CServicingSession::CServicingSession(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CServicingSession>::`vftable'{for `IFhEngineServicing'};
    *((_QWORD *)v8 + 1) = &ATL::CComContainedObject<CServicingSession>::`vftable'{for `CSessionBaseRW'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 72);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CServicingSession *)((char *)v8 + 296));
    if ( v9 >= 0 )
      v9 = CServicingSession::FinalConstruct(v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 72);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CServicingSession *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CServicingSession *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004ac0  mov     [rsp+arg_10], r8
0x180004ac5  mov     [rsp+arg_8], rdx
0x180004aca  mov     [rsp+arg_0], rcx
0x180004acf  push    rbx
0x180004ad0  push    rsi
0x180004ad1  push    rdi
0x180004ad2  push    r14
0x180004ad4  push    r15
0x180004ad6  sub     rsp, 20h
0x180004ada  mov     rsi, r8
0x180004add  mov     r15, rdx
0x180004ae0  test    r8, r8
0x180004ae3  jnz     short loc_180004AEF
0x180004ae5  mov     eax, 80004003h
0x180004aea  jmp     loc_180004BD0
0x180004aef  mov     qword ptr [r8], 0
0x180004af6  mov     edi, 8007000Eh
0x180004afb  mov     dword ptr [rsp+48h+arg_0], edi
0x180004aff  mov     [rsp+48h+arg_18], 0
0x180004b08  mov     ecx, 1A8h; Size
0x180004b0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b12  mov     rbx, rax
0x180004b15  test    rbx, rbx
0x180004b18  jz      short loc_180004B4A
0x180004b1a  mov     rcx, rax; this
0x180004b1d  call    ??0CServicingSession@@QEAA@XZ; CServicingSession::CServicingSession(void)
0x180004b22  lea     rax, ??_7?$CComObject@VCServicingSession@@@ATL@@6BIFhEngineServicing@@@; const ATL::CComObject<CServicingSession>::`vftable'{for `IFhEngineServicing'}
0x180004b29  mov     [rbx], rax
0x180004b2c  lea     rax, ??_7?$CComContainedObject@VCServicingSession@@@ATL@@6BCSessionBaseRW@@@; const ATL::CComContainedObject<CServicingSession>::`vftable'{for `CSessionBaseRW'}
0x180004b33  mov     [rbx+8], rax
0x180004b37  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004b3e  mov     rax, [rcx]
0x180004b41  mov     rax, [rax+8]
0x180004b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b4a  mov     [rsp+48h+arg_18], rbx
0x180004b4f  jmp     short loc_180004B64
0x180004b51  mov     rsi, [rsp+48h+arg_10]
0x180004b56  mov     r15, [rsp+48h+arg_8]
0x180004b5b  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004b5f  mov     rbx, [rsp+48h+arg_18]
0x180004b64  test    rbx, rbx
0x180004b67  jz      short loc_180004BCE
0x180004b69  lea     r14, [rbx+120h]
0x180004b70  mov     rcx, r14; volatile int *
0x180004b73  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180004b78  lea     rcx, [r14+8]; this
0x180004b7c  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004b81  test    eax, eax
0x180004b83  js      short loc_180004B8D
0x180004b85  mov     rcx, rbx; this
0x180004b88  call    ?FinalConstruct@CServicingSession@@QEAAJXZ; CServicingSession::FinalConstruct(void)
0x180004b8d  xor     edi, edi
0x180004b8f  test    eax, eax
0x180004b91  cmovs   edi, eax
0x180004b94  mov     rcx, r14; volatile int *
0x180004b97  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180004b9c  test    edi, edi
0x180004b9e  jnz     short loc_180004BBA
0x180004ba0  mov     rax, [rbx]
0x180004ba3  mov     r8, rsi
0x180004ba6  mov     rdx, r15
0x180004ba9  mov     rcx, rbx
0x180004bac  mov     rax, [rax]
0x180004baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb4  mov     edi, eax
0x180004bb6  test    eax, eax
0x180004bb8  jz      short loc_180004BCE
0x180004bba  mov     rdx, [rbx]
0x180004bbd  mov     rax, [rdx+48h]
0x180004bc1  mov     edx, 1
0x180004bc6  mov     rcx, rbx
0x180004bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bce  mov     eax, edi
0x180004bd0  add     rsp, 20h
0x180004bd4  pop     r15
0x180004bd6  pop     r14
0x180004bd8  pop     rdi
0x180004bd9  pop     rsi
0x180004bda  pop     rbx
0x180004bdb  retn
```
