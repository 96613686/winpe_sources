# ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2RawCD>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002de28`
- end: `0x18002df3a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002de00`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x18002d5c8`
- `0x18002de28`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftDiscFormat2RawCD>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CMsftDiscFormat2RawCD *v7; // rax
  CMsftDiscFormat2RawCD *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMsftDiscFormat2RawCD *)operator new(0x128u);
  v8 = v7;
  if ( v7 )
  {
    CMsftDiscFormat2RawCD::CMsftDiscFormat2RawCD(v7);
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscFormat2RawCD>'};
    *(_QWORD *)v8 = &ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IDispatchImpl<IDiscFormat2RawCD,&_GUID const IID_IDiscFormat2RawCD,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    v9 = ATL::_pAtlModule;
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscFormat2RawCD,&_GUID const IID_DDiscFormat2RawCDEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `CProxy_DDiscFormat2RawCDEvents<CMsftDiscFormat2RawCD>'};
    *((_QWORD *)v8 + 6) = &ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IDispEventSimpleImpl<0,CMsftDiscFormat2RawCD,&_GUID const IID_DWriteEngine2Events>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 26);
    v10 = ATL::CComSafeDeleteCriticalSection::Init((CMsftDiscFormat2RawCD *)((char *)v8 + 112));
    if ( v10 >= 0 )
    {
      *((_DWORD *)v8 + 73) = 0;
      v10 = 0;
    }
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 26);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMsftDiscFormat2RawCD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMsftDiscFormat2RawCD *, __int64))(*(_QWORD *)v8 + 296LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18002de28  push    rbx
0x18002de2a  push    rbp
0x18002de2b  push    rsi
0x18002de2c  push    rdi
0x18002de2d  push    r14
0x18002de2f  sub     rsp, 20h
0x18002de33  mov     rsi, r8
0x18002de36  mov     r14, rdx
0x18002de39  test    r8, r8
0x18002de3c  jnz     short loc_18002DE48
0x18002de3e  mov     eax, 80004003h
0x18002de43  jmp     loc_18002DF2F
0x18002de48  mov     ecx, 128h; Size
0x18002de4d  mov     qword ptr [r8], 0
0x18002de54  mov     edi, 8007000Eh
0x18002de59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002de5e  mov     rbx, rax
0x18002de61  test    rax, rax
0x18002de64  jz      loc_18002DF2D
0x18002de6a  mov     rcx, rax; this
0x18002de6d  call    ??0CMsftDiscFormat2RawCD@@QEAA@XZ; CMsftDiscFormat2RawCD::CMsftDiscFormat2RawCD(void)
0x18002de72  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@6B?$IConnectionPointContainerImpl@VCMsftDiscFormat2RawCD@@@1@@; const ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscFormat2RawCD>'}
0x18002de79  mov     [rbx+8], rax
0x18002de7d  lea     rcx, ??_7?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@6B?$IDispatchImpl@UIDiscFormat2RawCD@@$1?IID_IDiscFormat2RawCD@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IDispatchImpl<IDiscFormat2RawCD,&_GUID const IID_IDiscFormat2RawCD,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18002de84  mov     [rbx], rcx
0x18002de87  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MsftDiscFormat2RawCD@@3U_GUID@@B$1?IID_DDiscFormat2RawCDEvents@@3U2@B$1?LIBID_IMAPI2@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscFormat2RawCD,&_GUID const IID_DDiscFormat2RawCDEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18002de8e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002de95  mov     [rbx+10h], rax
0x18002de99  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@6B?$CProxy_DDiscFormat2RawCDEvents@VCMsftDiscFormat2RawCD@@@@@; const ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `CProxy_DDiscFormat2RawCDEvents<CMsftDiscFormat2RawCD>'}
0x18002dea0  mov     [rbx+18h], rax
0x18002dea4  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@6B?$IDispEventSimpleImpl@$0A@VCMsftDiscFormat2RawCD@@$1?IID_DWriteEngine2Events@@3U_GUID@@B@1@@; const ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ATL::IDispEventSimpleImpl<0,CMsftDiscFormat2RawCD,&_GUID const IID_DWriteEngine2Events>'}
0x18002deab  mov     [rbx+30h], rax
0x18002deaf  lea     rax, ??_7?$CComObject@VCMsftDiscFormat2RawCD@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftDiscFormat2RawCD>::`vftable'{for `ISupportErrorInfo'}
0x18002deb6  mov     [rbx+60h], rax
0x18002deba  mov     rax, [rcx]
0x18002debd  mov     rax, [rax+8]
0x18002dec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dec6  lea     rcx, [rbx+68h]; volatile int *
0x18002deca  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18002decf  lea     rcx, [rbx+70h]; this
0x18002ded3  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18002ded8  test    eax, eax
0x18002deda  js      short loc_18002DEE8
0x18002dedc  mov     dword ptr [rbx+124h], 0
0x18002dee6  xor     eax, eax
0x18002dee8  xor     edi, edi
0x18002deea  lea     rcx, [rbx+68h]; volatile int *
0x18002deee  test    eax, eax
0x18002def0  cmovs   edi, eax
0x18002def3  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18002def8  test    edi, edi
0x18002defa  jnz     short loc_18002DF16
0x18002defc  mov     rax, [rbx]
0x18002deff  mov     r8, rsi
0x18002df02  mov     rdx, r14
0x18002df05  mov     rcx, rbx
0x18002df08  mov     rax, [rax]
0x18002df0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df10  mov     edi, eax
0x18002df12  test    eax, eax
0x18002df14  jz      short loc_18002DF2D
0x18002df16  mov     rcx, [rbx]
0x18002df19  mov     edx, 1
0x18002df1e  mov     rax, [rcx+128h]
0x18002df25  mov     rcx, rbx
0x18002df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df2d  mov     eax, edi
0x18002df2f  add     rsp, 20h
0x18002df33  pop     r14
0x18002df35  pop     rdi
0x18002df36  pop     rsi
0x18002df37  pop     rbp
0x18002df38  pop     rbx
0x18002df39  retn
```
