# ATL::CComCreator<ATL::CComObject<CMsftWriteEngine2>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800327e8`
- end: `0x1800328eb`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftWriteEngine2@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800327c0`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x180032598`
- `0x1800327e8`
- `0x180032af0`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftWriteEngine2>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CMsftWriteEngine2 *v7; // rax
  CMsftWriteEngine2 *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMsftWriteEngine2 *)operator new(0x108u);
  v8 = v7;
  if ( v7 )
  {
    CMsftWriteEngine2::CMsftWriteEngine2(v7);
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>'};
    *(_QWORD *)v8 = &ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ATL::IDispatchImpl<IWriteEngine2,&_GUID const IID_IWriteEngine2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    v9 = ATL::_pAtlModule;
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftWriteEngine2,&_GUID const IID_DWriteEngine2Events,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `CProxy_DWriteEngine2Events<CMsftWriteEngine2>'};
    *((_QWORD *)v8 + 6) = &ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 14);
    v10 = ATL::CComSafeDeleteCriticalSection::Init((CMsftWriteEngine2 *)((char *)v8 + 64));
    if ( v10 >= 0 )
      v10 = CMsftWriteEngine2::FinalConstruct((HANDLE *)v8);
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 14);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMsftWriteEngine2 *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMsftWriteEngine2 *, __int64))(*(_QWORD *)v8 + 160LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800327e8  push    rbx
0x1800327ea  push    rbp
0x1800327eb  push    rsi
0x1800327ec  push    rdi
0x1800327ed  push    r14
0x1800327ef  sub     rsp, 20h
0x1800327f3  mov     rsi, r8
0x1800327f6  mov     r14, rdx
0x1800327f9  test    r8, r8
0x1800327fc  jnz     short loc_180032808
0x1800327fe  mov     eax, 80004003h
0x180032803  jmp     loc_1800328E0
0x180032808  mov     ecx, 108h; Size
0x18003280d  mov     qword ptr [r8], 0
0x180032814  mov     edi, 8007000Eh
0x180032819  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003281e  mov     rbx, rax
0x180032821  test    rax, rax
0x180032824  jz      loc_1800328DE
0x18003282a  mov     rcx, rax; this
0x18003282d  call    ??0CMsftWriteEngine2@@QEAA@XZ; CMsftWriteEngine2::CMsftWriteEngine2(void)
0x180032832  lea     rax, ??_7?$CComObject@VCMsftWriteEngine2@@@ATL@@6B?$IConnectionPointContainerImpl@VCMsftWriteEngine2@@@1@@; const ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>'}
0x180032839  mov     [rbx+8], rax
0x18003283d  lea     rcx, ??_7?$CComObject@VCMsftWriteEngine2@@@ATL@@6B?$IDispatchImpl@UIWriteEngine2@@$1?IID_IWriteEngine2@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ATL::IDispatchImpl<IWriteEngine2,&_GUID const IID_IWriteEngine2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180032844  mov     [rbx], rcx
0x180032847  lea     rax, ??_7?$CComObject@VCMsftWriteEngine2@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MsftWriteEngine2@@3U_GUID@@B$1?IID_DWriteEngine2Events@@3U2@B$1?LIBID_IMAPI2@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftWriteEngine2,&_GUID const IID_DWriteEngine2Events,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18003284e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180032855  mov     [rbx+10h], rax
0x180032859  lea     rax, ??_7?$CComObject@VCMsftWriteEngine2@@@ATL@@6B?$CProxy_DWriteEngine2Events@VCMsftWriteEngine2@@@@@; const ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `CProxy_DWriteEngine2Events<CMsftWriteEngine2>'}
0x180032860  mov     [rbx+18h], rax
0x180032864  lea     rax, ??_7?$CComObject@VCMsftWriteEngine2@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftWriteEngine2>::`vftable'{for `ISupportErrorInfo'}
0x18003286b  mov     [rbx+30h], rax
0x18003286f  mov     rax, [rcx]
0x180032872  mov     rax, [rax+8]
0x180032876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003287b  lea     rcx, [rbx+38h]; volatile int *
0x18003287f  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180032884  lea     rcx, [rbx+40h]; this
0x180032888  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18003288d  test    eax, eax
0x18003288f  js      short loc_180032899
0x180032891  mov     rcx, rbx; this
0x180032894  call    ?FinalConstruct@CMsftWriteEngine2@@QEAAJXZ; CMsftWriteEngine2::FinalConstruct(void)
0x180032899  xor     edi, edi
0x18003289b  lea     rcx, [rbx+38h]; volatile int *
0x18003289f  test    eax, eax
0x1800328a1  cmovs   edi, eax
0x1800328a4  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800328a9  test    edi, edi
0x1800328ab  jnz     short loc_1800328C7
0x1800328ad  mov     rax, [rbx]
0x1800328b0  mov     r8, rsi
0x1800328b3  mov     rdx, r14
0x1800328b6  mov     rcx, rbx
0x1800328b9  mov     rax, [rax]
0x1800328bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328c1  mov     edi, eax
0x1800328c3  test    eax, eax
0x1800328c5  jz      short loc_1800328DE
0x1800328c7  mov     rcx, [rbx]
0x1800328ca  mov     edx, 1
0x1800328cf  mov     rax, [rcx+0A0h]
0x1800328d6  mov     rcx, rbx
0x1800328d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328de  mov     eax, edi
0x1800328e0  add     rsp, 20h
0x1800328e4  pop     r14
0x1800328e6  pop     rdi
0x1800328e7  pop     rsi
0x1800328e8  pop     rbp
0x1800328e9  pop     rbx
0x1800328ea  retn
```
