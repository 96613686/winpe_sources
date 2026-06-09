# ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2TrackAtOnce>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800378e8`
- end: `0x1800379fc`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800378c0`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x18003670c`
- `0x1800378e8`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2TrackAtOnce>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  CMsftDiscFormat2TrackAtOnce *v7; // rax
  CMsftDiscFormat2TrackAtOnce *v8; // rdi
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax
  int v11; // edx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMsftDiscFormat2TrackAtOnce *)operator new(0x460u);
  v8 = v7;
  if ( v7 )
  {
    CMsftDiscFormat2TrackAtOnce::CMsftDiscFormat2TrackAtOnce(v7);
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IDispatchImpl<IDiscFormat2TrackAtOnce,&_GUID const IID_IDiscFormat2TrackAtOnce,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscFormat2TrackAtOnce>'};
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscFormat2TrackAtOnce,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `CProxy_DDiscFormat2TrackAtOnceEvents<CMsftDiscFormat2TrackAtOnce>'};
    *((_QWORD *)v8 + 6) = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IDispEventSimpleImpl<0,CMsftDiscFormat2TrackAtOnce,&_GUID const IID_DWriteEngine2Events>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 13) = &ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `IBurnVerification'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 28);
    v10 = ATL::CComSafeDeleteCriticalSection::Init((CMsftDiscFormat2TrackAtOnce *)((char *)v8 + 120));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 28);
    if ( v6
      || (v6 = (**(__int64 (__fastcall ***)(CMsftDiscFormat2TrackAtOnce *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      (*(void (__fastcall **)(CMsftDiscFormat2TrackAtOnce *, __int64))(*(_QWORD *)v8 + 304LL))(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800378e8  push    rbx
0x1800378ea  push    rbp
0x1800378eb  push    rsi
0x1800378ec  push    rdi
0x1800378ed  push    r14
0x1800378ef  sub     rsp, 20h
0x1800378f3  mov     r14, r8
0x1800378f6  mov     rbp, rdx
0x1800378f9  test    r8, r8
0x1800378fc  jnz     short loc_180037908
0x1800378fe  mov     eax, 80004003h
0x180037903  jmp     loc_1800379F1
0x180037908  mov     ecx, 460h; Size
0x18003790d  mov     qword ptr [r8], 0
0x180037914  mov     esi, 8007000Eh
0x180037919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003791e  mov     rdi, rax
0x180037921  test    rax, rax
0x180037924  jz      loc_1800379EF
0x18003792a  mov     rcx, rax; this
0x18003792d  call    ??0CMsftDiscFormat2TrackAtOnce@@QEAA@XZ; CMsftDiscFormat2TrackAtOnce::CMsftDiscFormat2TrackAtOnce(void)
0x180037932  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180037939  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6B?$IDispatchImpl@UIDiscFormat2TrackAtOnce@@$1?IID_IDiscFormat2TrackAtOnce@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IDispatchImpl<IDiscFormat2TrackAtOnce,&_GUID const IID_IDiscFormat2TrackAtOnce,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180037940  mov     [rdi], rax
0x180037943  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6B?$IConnectionPointContainerImpl@VCMsftDiscFormat2TrackAtOnce@@@1@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscFormat2TrackAtOnce>'}
0x18003794a  mov     [rdi+8], rax
0x18003794e  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MsftDiscFormat2TrackAtOnce@@3U_GUID@@B$1?IID_DDiscFormat2TrackAtOnceEvents@@3U2@B$1?LIBID_IMAPI2@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscFormat2TrackAtOnce,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180037955  mov     [rdi+10h], rax
0x180037959  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6B?$CProxy_DDiscFormat2TrackAtOnceEvents@VCMsftDiscFormat2TrackAtOnce@@@@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `CProxy_DDiscFormat2TrackAtOnceEvents<CMsftDiscFormat2TrackAtOnce>'}
0x180037960  mov     [rdi+18h], rax
0x180037964  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6B?$IDispEventSimpleImpl@$0A@VCMsftDiscFormat2TrackAtOnce@@$1?IID_DWriteEngine2Events@@3U_GUID@@B@1@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ATL::IDispEventSimpleImpl<0,CMsftDiscFormat2TrackAtOnce,&_GUID const IID_DWriteEngine2Events>'}
0x18003796b  mov     [rdi+30h], rax
0x18003796f  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `ISupportErrorInfo'}
0x180037976  mov     [rdi+60h], rax
0x18003797a  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@6BIBurnVerification@@@; const ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::`vftable'{for `IBurnVerification'}
0x180037981  mov     [rdi+68h], rax
0x180037985  mov     rax, [rcx]
0x180037988  mov     rax, [rax+8]
0x18003798c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037991  lea     rcx, [rdi+70h]; volatile int *
0x180037995  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18003799a  lea     rcx, [rdi+78h]; this
0x18003799e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800379a3  xor     edx, edx
0x1800379a5  lea     rcx, [rdi+70h]; volatile int *
0x1800379a9  test    eax, eax
0x1800379ab  cmovs   edx, eax
0x1800379ae  xor     esi, esi
0x1800379b0  test    edx, edx
0x1800379b2  cmovs   esi, edx
0x1800379b5  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800379ba  test    esi, esi
0x1800379bc  jnz     short loc_1800379D8
0x1800379be  mov     rax, [rdi]
0x1800379c1  mov     r8, r14
0x1800379c4  mov     rdx, rbp
0x1800379c7  mov     rcx, rdi
0x1800379ca  mov     rax, [rax]
0x1800379cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379d2  mov     esi, eax
0x1800379d4  test    eax, eax
0x1800379d6  jz      short loc_1800379EF
0x1800379d8  mov     rcx, [rdi]
0x1800379db  mov     edx, 1
0x1800379e0  mov     rax, [rcx+130h]
0x1800379e7  mov     rcx, rdi
0x1800379ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379ef  mov     eax, esi
0x1800379f1  add     rsp, 20h
0x1800379f5  pop     r14
0x1800379f7  pop     rdi
0x1800379f8  pop     rsi
0x1800379f9  pop     rbp
0x1800379fa  pop     rbx
0x1800379fb  retn
```
