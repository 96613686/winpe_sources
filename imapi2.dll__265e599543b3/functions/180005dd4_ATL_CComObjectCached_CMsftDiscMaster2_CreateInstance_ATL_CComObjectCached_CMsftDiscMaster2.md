# ATL::CComObjectCached<CMsftDiscMaster2>::CreateInstance(ATL::CComObjectCached<CMsftDiscMaster2> * *)

- ea: `0x180005dd4`
- end: `0x180005e9b`
- name: `?CreateInstance@?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@SAJPEAPEAV12@@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x180005dd4`
- `0x180005fa4`
- `0x1800062dc`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000ef44`
- `0x18000eff4`
- `0x18000fdd4`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CMsftDiscMaster2>::CreateInstance(CMsftDiscMaster2 **a1)
{
  CMsftDiscMaster2 *v3; // rax
  CMsftDiscMaster2 *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (CMsftDiscMaster2 *)operator new(0xB0u);
  v4 = v3;
  if ( !v3 )
  {
    v6 = -2147024882;
    goto LABEL_12;
  }
  CMsftDiscMaster2::CMsftDiscMaster2(v3);
  *((_QWORD *)v4 + 1) = &ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscMaster2>'};
  *(_QWORD *)v4 = &ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ATL::IDispatchImpl<IDiscMaster2,&_GUID const IID_IDiscMaster2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)v4 + 2) = &ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)v4 + 3) = &ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `CProxy_DDiscMaster2Events<CMsftDiscMaster2>'};
  *((_QWORD *)v4 + 6) = &ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ISupportErrorInfo'};
  ATL::SafeIncrementReferenceMultiThread((volatile int *)v4 + 14);
  v5 = ATL::CComSafeDeleteCriticalSection::Init((CMsftDiscMaster2 *)((char *)v4 + 64));
  if ( v5 >= 0 )
    v5 = CMsftDiscMaster2::FinalConstruct(v4);
  v6 = 0;
  if ( v5 < 0 )
    v6 = v5;
  ATL::SafeDecrementReferenceMultiThread((volatile int *)v4 + 14);
  if ( v6 )
  {
    ATL::CComObjectCached<CMsftDiscMaster2>::`scalar deleting destructor'(v4);
LABEL_12:
    v4 = 0;
    goto LABEL_13;
  }
  v6 = 0;
LABEL_13:
  *a1 = v4;
  return v6;
}

```

## disassembly

```asm
0x180005dd4  push    rbx
0x180005dd6  push    rbp
0x180005dd7  push    rsi
0x180005dd8  push    rdi
0x180005dd9  sub     rsp, 28h
0x180005ddd  mov     rsi, rcx
0x180005de0  test    rcx, rcx
0x180005de3  jnz     short loc_180005DEF
0x180005de5  mov     eax, 80004003h
0x180005dea  jmp     loc_180005E92
0x180005def  mov     qword ptr [rcx], 0
0x180005df6  mov     ecx, 0B0h; Size
0x180005dfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e00  mov     rbx, rax
0x180005e03  test    rax, rax
0x180005e06  jz      short loc_180005E86
0x180005e08  mov     rcx, rax; this
0x180005e0b  call    ??0CMsftDiscMaster2@@QEAA@XZ; CMsftDiscMaster2::CMsftDiscMaster2(void)
0x180005e10  lea     rax, ??_7?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@6B?$IConnectionPointContainerImpl@VCMsftDiscMaster2@@@1@@; const ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMsftDiscMaster2>'}
0x180005e17  mov     [rbx+8], rax
0x180005e1b  lea     rcx, ??_7?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@6B?$IDispatchImpl@UIDiscMaster2@@$1?IID_IDiscMaster2@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ATL::IDispatchImpl<IDiscMaster2,&_GUID const IID_IDiscMaster2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180005e22  lea     rax, ??_7?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MsftDiscMaster2@@3U_GUID@@B$1?IID_DDiscMaster2Events@@3U2@B$1?LIBID_IMAPI2@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180005e29  mov     [rbx], rcx
0x180005e2c  mov     [rbx+10h], rax
0x180005e30  lea     rcx, [rbx+38h]; volatile int *
0x180005e34  lea     rax, ??_7?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@6B?$CProxy_DDiscMaster2Events@VCMsftDiscMaster2@@@@@; const ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `CProxy_DDiscMaster2Events<CMsftDiscMaster2>'}
0x180005e3b  mov     [rbx+18h], rax
0x180005e3f  lea     rax, ??_7?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObjectCached<CMsftDiscMaster2>::`vftable'{for `ISupportErrorInfo'}
0x180005e46  mov     [rbx+30h], rax
0x180005e4a  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180005e4f  lea     rcx, [rbx+40h]; this
0x180005e53  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005e58  test    eax, eax
0x180005e5a  js      short loc_180005E64
0x180005e5c  mov     rcx, rbx; this
0x180005e5f  call    ?FinalConstruct@CMsftDiscMaster2@@QEAAJXZ; CMsftDiscMaster2::FinalConstruct(void)
0x180005e64  xor     edi, edi
0x180005e66  lea     rcx, [rbx+38h]; volatile int *
0x180005e6a  test    eax, eax
0x180005e6c  cmovs   edi, eax
0x180005e6f  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005e74  test    edi, edi
0x180005e76  jz      short loc_180005E82
0x180005e78  mov     rcx, rbx; Block
0x180005e7b  call    ??_G?$CComObjectCached@VCMsftDiscMaster2@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<CMsftDiscMaster2>::`scalar deleting destructor'(uint)
0x180005e80  jmp     short loc_180005E8B
0x180005e82  xor     edi, edi
0x180005e84  jmp     short loc_180005E8D
0x180005e86  mov     edi, 8007000Eh
0x180005e8b  xor     ebx, ebx
0x180005e8d  mov     [rsi], rbx
0x180005e90  mov     eax, edi
0x180005e92  add     rsp, 28h
0x180005e96  pop     rdi
0x180005e97  pop     rsi
0x180005e98  pop     rbp
0x180005e99  pop     rbx
0x180005e9a  retn
```
