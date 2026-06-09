# ATL::CComCreator<ATL::CComObject<CMSMQTriggerSet>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e488`
- end: `0x18000e56a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQTriggerSet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dee0`

## callees

- `0x18000dc94`
- `0x18000e488`
- `0x18000e83c`
- `0x18000ed1c`
- `0x18000fae4`
- `0x18000fb0c`
- `0x180010390`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQTriggerSet>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // edi
  CMSMQTriggerSet *v7; // rax
  CMSMQTriggerSet *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSMQTriggerSet *)MmAllocate(0x4C0u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQTriggerSet::CMSMQTriggerSet(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 4);
    v6 = ATL::CComAutoDeleteCriticalSection::Init((CMSMQTriggerSet *)((char *)v8 + 24));
    if ( v6 >= 0 )
      v6 = CMSMQTriggerSet::FinalConstruct(v8);
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMSMQTriggerSet *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      ATL::CComObject<CMSMQTriggerSet>::`scalar deleting destructor'(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e488  mov     [rsp+arg_8], rbx
0x18000e48d  mov     [rsp+arg_10], rbp
0x18000e492  mov     [rsp+arg_0], rcx
0x18000e497  push    rsi
0x18000e498  push    rdi
0x18000e499  push    r14
0x18000e49b  sub     rsp, 20h
0x18000e49f  mov     r14, r8
0x18000e4a2  mov     rbp, rdx
0x18000e4a5  test    r8, r8
0x18000e4a8  jnz     short loc_18000E4B4
0x18000e4aa  mov     eax, 80004003h
0x18000e4af  jmp     loc_18000E557
0x18000e4b4  mov     qword ptr [r8], 0
0x18000e4bb  mov     edi, 8007000Eh
0x18000e4c0  mov     ecx, 4C0h; unsigned __int64
0x18000e4c5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e4ca  mov     rbx, rax
0x18000e4cd  mov     [rsp+38h+arg_0], rax
0x18000e4d2  test    rax, rax
0x18000e4d5  jz      short loc_18000E4FD
0x18000e4d7  mov     rcx, rax; this
0x18000e4da  call    ??0CMSMQTriggerSet@@QEAA@XZ; CMSMQTriggerSet::CMSMQTriggerSet(void)
0x18000e4df  lea     rax, ??_7?$CComObject@VCMSMQTriggerSet@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ISupportErrorInfo'}
0x18000e4e6  mov     [rbx], rax
0x18000e4e9  lea     rax, ??_7?$CComObject@VCMSMQTriggerSet@@@ATL@@6B?$IDispatchImpl@UIMSMQTriggerSet@@$1?IID_IMSMQTriggerSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e4f0  mov     [rbx+8], rax
0x18000e4f4  lock inc cs:dword_18002CFF8
0x18000e4fb  jmp     short loc_18000E4FF
0x18000e4fd  xor     ebx, ebx
0x18000e4ff  test    rbx, rbx
0x18000e502  jz      short loc_18000E555
0x18000e504  lea     rcx, [rbx+10h]; volatile int *
0x18000e508  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000e50d  lea     rcx, [rbx+18h]; this
0x18000e511  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e516  mov     edi, eax
0x18000e518  test    eax, eax
0x18000e51a  js      short loc_18000E526
0x18000e51c  mov     rcx, rbx; this
0x18000e51f  call    ?FinalConstruct@CMSMQTriggerSet@@QEAAJXZ; CMSMQTriggerSet::FinalConstruct(void)
0x18000e524  mov     edi, eax
0x18000e526  lea     rcx, [rbx+10h]; volatile int *
0x18000e52a  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000e52f  test    edi, edi
0x18000e531  jnz     short loc_18000E54D
0x18000e533  mov     rax, [rbx]
0x18000e536  mov     r8, r14
0x18000e539  mov     rdx, rbp
0x18000e53c  mov     rcx, rbx
0x18000e53f  mov     rax, [rax]
0x18000e542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e547  mov     edi, eax
0x18000e549  test    eax, eax
0x18000e54b  jz      short loc_18000E555
0x18000e54d  mov     rcx, rbx; Block
0x18000e550  call    ??_G?$CComObject@VCMSMQTriggerSet@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQTriggerSet>::`scalar deleting destructor'(uint)
0x18000e555  mov     eax, edi
0x18000e557  mov     rbx, [rsp+38h+arg_8]
0x18000e55c  mov     rbp, [rsp+38h+arg_10]
0x18000e561  add     rsp, 20h
0x18000e565  pop     r14
0x18000e567  pop     rdi
0x18000e568  pop     rsi
0x18000e569  retn
```
