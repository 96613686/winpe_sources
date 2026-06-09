# ATL::CComCreator<ATL::CComObject<CMsftDiscMaster2>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180028208`
- end: `0x180028308`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftDiscMaster2@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800281e0`

## callees

- `0x180005fa4`
- `0x1800062dc`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000eff4`
- `0x18000fdd4`
- `0x180028208`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftDiscMaster2>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CMsftDiscMaster2 *v7; // rax
  CMsftDiscMaster2 *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMsftDiscMaster2 *)operator new(0xB0u);
  v8 = v7;
  if ( v7 )
  {
    CMsftDiscMaster2::CMsftDiscMaster2(v7);
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscMaster2>'};
    *(_QWORD *)v8 = &ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ATL::IDispatchImpl<IDiscMaster2,&_GUID const IID_IDiscMaster2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    v9 = ATL::_pAtlModule;
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `CProxy_DDiscMaster2Events<CMsftDiscMaster2>'};
    *((_QWORD *)v8 + 6) = &ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 14);
    v10 = ATL::CComSafeDeleteCriticalSection::Init((CMsftDiscMaster2 *)((char *)v8 + 64));
    if ( v10 >= 0 )
      v10 = CMsftDiscMaster2::FinalConstruct(v8);
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 14);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMsftDiscMaster2 *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMsftDiscMaster2 *, __int64))(*(_QWORD *)v8 + 88LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180028208  push    rbx
0x18002820a  push    rbp
0x18002820b  push    rsi
0x18002820c  push    rdi
0x18002820d  push    r14
0x18002820f  sub     rsp, 20h
0x180028213  mov     rsi, r8
0x180028216  mov     r14, rdx
0x180028219  test    r8, r8
0x18002821c  jnz     short loc_180028228
0x18002821e  mov     eax, 80004003h
0x180028223  jmp     loc_1800282FD
0x180028228  mov     ecx, 0B0h; Size
0x18002822d  mov     qword ptr [r8], 0
0x180028234  mov     edi, 8007000Eh
0x180028239  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002823e  mov     rbx, rax
0x180028241  test    rax, rax
0x180028244  jz      loc_1800282FB
0x18002824a  mov     rcx, rax; this
0x18002824d  call    ??0CMsftDiscMaster2@@QEAA@XZ; CMsftDiscMaster2::CMsftDiscMaster2(void)
0x180028252  lea     rax, ??_7?$CComObject@VCMsftDiscMaster2@@@ATL@@6B?$IConnectionPointContainerImpl@VCMsftDiscMaster2@@@1@@; const ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscMaster2>'}
0x180028259  mov     [rbx+8], rax
0x18002825d  lea     rcx, ??_7?$CComObject@VCMsftDiscMaster2@@@ATL@@6B?$IDispatchImpl@UIDiscMaster2@@$1?IID_IDiscMaster2@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ATL::IDispatchImpl<IDiscMaster2,&_GUID const IID_IDiscMaster2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180028264  mov     [rbx], rcx
0x180028267  lea     rax, ??_7?$CComObject@VCMsftDiscMaster2@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MsftDiscMaster2@@3U_GUID@@B$1?IID_DDiscMaster2Events@@3U2@B$1?LIBID_IMAPI2@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18002826e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180028275  mov     [rbx+10h], rax
0x180028279  lea     rax, ??_7?$CComObject@VCMsftDiscMaster2@@@ATL@@6B?$CProxy_DDiscMaster2Events@VCMsftDiscMaster2@@@@@; const ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `CProxy_DDiscMaster2Events<CMsftDiscMaster2>'}
0x180028280  mov     [rbx+18h], rax
0x180028284  lea     rax, ??_7?$CComObject@VCMsftDiscMaster2@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftDiscMaster2>::`vftable'{for `ISupportErrorInfo'}
0x18002828b  mov     [rbx+30h], rax
0x18002828f  mov     rax, [rcx]
0x180028292  mov     rax, [rax+8]
0x180028296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002829b  lea     rcx, [rbx+38h]; volatile int *
0x18002829f  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800282a4  lea     rcx, [rbx+40h]; this
0x1800282a8  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800282ad  test    eax, eax
0x1800282af  js      short loc_1800282B9
0x1800282b1  mov     rcx, rbx; this
0x1800282b4  call    ?FinalConstruct@CMsftDiscMaster2@@QEAAJXZ; CMsftDiscMaster2::FinalConstruct(void)
0x1800282b9  xor     edi, edi
0x1800282bb  lea     rcx, [rbx+38h]; volatile int *
0x1800282bf  test    eax, eax
0x1800282c1  cmovs   edi, eax
0x1800282c4  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800282c9  test    edi, edi
0x1800282cb  jnz     short loc_1800282E7
0x1800282cd  mov     rax, [rbx]
0x1800282d0  mov     r8, rsi
0x1800282d3  mov     rdx, r14
0x1800282d6  mov     rcx, rbx
0x1800282d9  mov     rax, [rax]
0x1800282dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282e1  mov     edi, eax
0x1800282e3  test    eax, eax
0x1800282e5  jz      short loc_1800282FB
0x1800282e7  mov     rcx, [rbx]
0x1800282ea  mov     edx, 1
0x1800282ef  mov     rax, [rcx+58h]
0x1800282f3  mov     rcx, rbx
0x1800282f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282fb  mov     eax, edi
0x1800282fd  add     rsp, 20h
0x180028301  pop     r14
0x180028303  pop     rdi
0x180028304  pop     rsi
0x180028305  pop     rbp
0x180028306  pop     rbx
0x180028307  retn
```
