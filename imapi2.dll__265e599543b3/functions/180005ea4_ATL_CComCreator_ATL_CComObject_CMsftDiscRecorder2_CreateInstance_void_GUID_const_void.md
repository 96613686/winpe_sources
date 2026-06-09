# ATL::CComCreator<ATL::CComObject<CMsftDiscRecorder2>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005ea4`
- end: `0x180005f9c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftDiscRecorder2@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005cc0`

## callees

- `0x180005ea4`
- `0x180005fa4`
- `0x18000c954`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000f680`
- `0x18000fdd4`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftDiscRecorder2>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // edi
  CMsftDiscRecorder2 *v6; // rax
  CMsftDiscRecorder2 *v7; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (CMsftDiscRecorder2 *)operator new(0xF8u);
  v7 = v6;
  if ( v6 )
  {
    CMsftDiscRecorder2::CMsftDiscRecorder2(v6);
    *(_QWORD *)v7 = &ATL::CComObject<CMsftDiscRecorder2>::`vftable'{for `ATL::IDispatchImpl<IDiscRecorder2,&_GUID const IID_IDiscRecorder2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    v9 = ATL::_pAtlModule;
    *((_QWORD *)v7 + 1) = &ATL::CComObject<CMsftDiscRecorder2>::`vftable'{for `IDiscRecorder2Ex'};
    *((_QWORD *)v7 + 2) = &ATL::CComObject<CMsftDiscRecorder2>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v7 + 6);
    v10 = ATL::CComSafeDeleteCriticalSection::Init((CMsftDiscRecorder2 *)((char *)v7 + 32));
    if ( v10 >= 0 )
      v10 = CMsftDiscRecorder2::FinalConstruct(v7);
    v5 = 0;
    if ( v10 < 0 )
      v5 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v7 + 6);
    if ( v5 || (v5 = (**(__int64 (__fastcall ***)(CMsftDiscRecorder2 *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMsftDiscRecorder2 *, __int64))(*(_QWORD *)v7 + 224LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180005ea4  push    rbx
0x180005ea6  push    rbp
0x180005ea7  push    rsi
0x180005ea8  push    rdi
0x180005ea9  push    r14
0x180005eab  sub     rsp, 20h
0x180005eaf  mov     rsi, r8
0x180005eb2  mov     r14, rdx
0x180005eb5  test    r8, r8
0x180005eb8  jz      loc_180005F88
0x180005ebe  mov     ecx, 0F8h; Size
0x180005ec3  mov     qword ptr [r8], 0
0x180005eca  mov     edi, 8007000Eh
0x180005ecf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ed4  mov     rbx, rax
0x180005ed7  test    rax, rax
0x180005eda  jnz     short loc_180005EE9
0x180005edc  mov     eax, edi
0x180005ede  add     rsp, 20h
0x180005ee2  pop     r14
0x180005ee4  pop     rdi
0x180005ee5  pop     rsi
0x180005ee6  pop     rbp
0x180005ee7  pop     rbx
0x180005ee8  retn
0x180005ee9  mov     rcx, rbx; this
0x180005eec  call    ??0CMsftDiscRecorder2@@QEAA@XZ; CMsftDiscRecorder2::CMsftDiscRecorder2(void)
0x180005ef1  lea     rcx, ??_7?$CComObject@VCMsftDiscRecorder2@@@ATL@@6B?$IDispatchImpl@UIDiscRecorder2@@$1?IID_IDiscRecorder2@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscRecorder2>::`vftable'{for `ATL::IDispatchImpl<IDiscRecorder2,&_GUID const IID_IDiscRecorder2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180005ef8  mov     [rbx], rcx
0x180005efb  lea     rax, ??_7?$CComObject@VCMsftDiscRecorder2@@@ATL@@6BIDiscRecorder2Ex@@@; const ATL::CComObject<CMsftDiscRecorder2>::`vftable'{for `IDiscRecorder2Ex'}
0x180005f02  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005f09  mov     [rbx+8], rax
0x180005f0d  lea     rax, ??_7?$CComObject@VCMsftDiscRecorder2@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftDiscRecorder2>::`vftable'{for `ISupportErrorInfo'}
0x180005f14  mov     [rbx+10h], rax
0x180005f18  mov     rax, [rcx]
0x180005f1b  mov     rax, [rax+8]
0x180005f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f24  lea     rcx, [rbx+18h]; volatile int *
0x180005f28  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180005f2d  lea     rcx, [rbx+20h]; this
0x180005f31  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005f36  test    eax, eax
0x180005f38  jns     short loc_180005F92
0x180005f3a  xor     edi, edi
0x180005f3c  lea     rcx, [rbx+18h]; volatile int *
0x180005f40  test    eax, eax
0x180005f42  cmovs   edi, eax
0x180005f45  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005f4a  test    edi, edi
0x180005f4c  jnz     short loc_180005F6C
0x180005f4e  mov     rax, [rbx]
0x180005f51  mov     r8, rsi
0x180005f54  mov     rdx, r14
0x180005f57  mov     rcx, rbx
0x180005f5a  mov     rax, [rax]
0x180005f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f62  mov     edi, eax
0x180005f64  test    eax, eax
0x180005f66  jz      loc_180005EDC
0x180005f6c  mov     rcx, [rbx]
0x180005f6f  mov     edx, 1
0x180005f74  mov     rax, [rcx+0E0h]
0x180005f7b  mov     rcx, rbx
0x180005f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f83  jmp     loc_180005EDC
0x180005f88  mov     eax, 80004003h
0x180005f8d  jmp     loc_180005EDE
0x180005f92  mov     rcx, rbx; this
0x180005f95  call    ?FinalConstruct@CMsftDiscRecorder2@@QEAAJXZ; CMsftDiscRecorder2::FinalConstruct(void)
0x180005f9a  jmp     short loc_180005F3A
```
