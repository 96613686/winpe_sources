# ATL::CComCreator<ATL::CComObject<CMSMQRuleHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e2a0`
- end: `0x18000e382`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQRuleHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000de90`

## callees

- `0x1800051e0`
- `0x18000dc44`
- `0x18000e2a0`
- `0x18000e80c`
- `0x18000ed1c`
- `0x18000fae4`
- `0x18000fb0c`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQRuleHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // edi
  CMSMQRuleHandler *v7; // rax
  CMSMQRuleHandler *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSMQRuleHandler *)MmAllocate(0xB0u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQRuleHandler::CMSMQRuleHandler(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 4);
    v6 = ATL::CComAutoDeleteCriticalSection::Init((CMSMQRuleHandler *)((char *)v8 + 24));
    if ( v6 >= 0 )
      v6 = CMSMQRuleHandler::FinalConstruct(v8);
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMSMQRuleHandler *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      ATL::CComObject<CMSMQRuleHandler>::`scalar deleting destructor'(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e2a0  mov     [rsp+arg_8], rbx
0x18000e2a5  mov     [rsp+arg_10], rbp
0x18000e2aa  mov     [rsp+arg_0], rcx
0x18000e2af  push    rsi
0x18000e2b0  push    rdi
0x18000e2b1  push    r14
0x18000e2b3  sub     rsp, 20h
0x18000e2b7  mov     r14, r8
0x18000e2ba  mov     rbp, rdx
0x18000e2bd  test    r8, r8
0x18000e2c0  jnz     short loc_18000E2CC
0x18000e2c2  mov     eax, 80004003h
0x18000e2c7  jmp     loc_18000E36F
0x18000e2cc  mov     qword ptr [r8], 0
0x18000e2d3  mov     edi, 8007000Eh
0x18000e2d8  mov     ecx, 0B0h; unsigned __int64
0x18000e2dd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e2e2  mov     rbx, rax
0x18000e2e5  mov     [rsp+38h+arg_0], rax
0x18000e2ea  test    rax, rax
0x18000e2ed  jz      short loc_18000E315
0x18000e2ef  mov     rcx, rax; this
0x18000e2f2  call    ??0CMSMQRuleHandler@@QEAA@XZ; CMSMQRuleHandler::CMSMQRuleHandler(void)
0x18000e2f7  lea     rax, ??_7?$CComObject@VCMSMQRuleHandler@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ISupportErrorInfo'}
0x18000e2fe  mov     [rbx], rax
0x18000e301  lea     rax, ??_7?$CComObject@VCMSMQRuleHandler@@@ATL@@6B?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e308  mov     [rbx+8], rax
0x18000e30c  lock inc cs:dword_18002CFF8
0x18000e313  jmp     short loc_18000E317
0x18000e315  xor     ebx, ebx
0x18000e317  test    rbx, rbx
0x18000e31a  jz      short loc_18000E36D
0x18000e31c  lea     rcx, [rbx+10h]; volatile int *
0x18000e320  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000e325  lea     rcx, [rbx+18h]; this
0x18000e329  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e32e  mov     edi, eax
0x18000e330  test    eax, eax
0x18000e332  js      short loc_18000E33E
0x18000e334  mov     rcx, rbx; this
0x18000e337  call    ?FinalConstruct@CMSMQRuleHandler@@QEAAJXZ; CMSMQRuleHandler::FinalConstruct(void)
0x18000e33c  mov     edi, eax
0x18000e33e  lea     rcx, [rbx+10h]; volatile int *
0x18000e342  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000e347  test    edi, edi
0x18000e349  jnz     short loc_18000E365
0x18000e34b  mov     rax, [rbx]
0x18000e34e  mov     r8, r14
0x18000e351  mov     rdx, rbp
0x18000e354  mov     rcx, rbx
0x18000e357  mov     rax, [rax]
0x18000e35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e35f  mov     edi, eax
0x18000e361  test    eax, eax
0x18000e363  jz      short loc_18000E36D
0x18000e365  mov     rcx, rbx; Block
0x18000e368  call    ??_G?$CComObject@VCMSMQRuleHandler@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQRuleHandler>::`scalar deleting destructor'(uint)
0x18000e36d  mov     eax, edi
0x18000e36f  mov     rbx, [rsp+38h+arg_8]
0x18000e374  mov     rbp, [rsp+38h+arg_10]
0x18000e379  add     rsp, 20h
0x18000e37d  pop     r14
0x18000e37f  pop     rdi
0x18000e380  pop     rsi
0x18000e381  retn
```
