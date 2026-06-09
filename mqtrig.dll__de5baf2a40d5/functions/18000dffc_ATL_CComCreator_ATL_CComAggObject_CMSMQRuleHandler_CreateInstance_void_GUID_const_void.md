# ATL::CComCreator<ATL::CComAggObject<CMSMQRuleHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000dffc`
- end: `0x18000e0dc`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQRuleHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000de90`

## callees

- `0x1800051e0`
- `0x18000dbcc`
- `0x18000dffc`
- `0x18000e80c`
- `0x18000ed1c`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQRuleHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MmAllocate(0xC8u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQRuleHandler>::`vftable';
    CMSMQRuleHandler::CMSMQRuleHandler((CMSMQRuleHandler *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQRuleHandler>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQRuleHandler>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    v9[5] = a1;
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v10 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v9 + 6));
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 < 0
      || (v7 = CMSMQRuleHandler::FinalConstruct((CMSMQRuleHandler *)(v9 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQRuleHandler>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000dffc  push    rbx
0x18000dffe  push    rbp
0x18000dfff  push    rsi
0x18000e000  push    rdi
0x18000e001  push    r14
0x18000e003  push    r15
0x18000e005  sub     rsp, 28h
0x18000e009  mov     r14, r8
0x18000e00c  mov     r15, rdx
0x18000e00f  mov     rbp, rcx
0x18000e012  test    r8, r8
0x18000e015  jnz     short loc_18000E021
0x18000e017  mov     eax, 80004003h
0x18000e01c  jmp     loc_18000E0CF
0x18000e021  mov     qword ptr [r8], 0
0x18000e028  mov     esi, 8007000Eh
0x18000e02d  mov     ecx, 0C8h; unsigned __int64
0x18000e032  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e037  mov     rdi, rax
0x18000e03a  mov     [rsp+58h+arg_10], rax
0x18000e03f  test    rax, rax
0x18000e042  jz      short loc_18000E081
0x18000e044  mov     dword ptr [rax+8], 0
0x18000e04b  lea     rax, ??_7?$CComAggObject@VCMSMQRuleHandler@@@ATL@@6B@; const ATL::CComAggObject<CMSMQRuleHandler>::`vftable'
0x18000e052  mov     [rdi], rax
0x18000e055  lea     rcx, [rdi+18h]; this
0x18000e059  call    ??0CMSMQRuleHandler@@QEAA@XZ; CMSMQRuleHandler::CMSMQRuleHandler(void)
0x18000e05e  lea     rax, ??_7?$CComContainedObject@VCMSMQRuleHandler@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQRuleHandler>::`vftable'{for `ISupportErrorInfo'}
0x18000e065  mov     [rdi+18h], rax
0x18000e069  lea     rax, ??_7?$CComContainedObject@VCMSMQRuleHandler@@@ATL@@6B?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQRuleHandler>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e070  mov     [rdi+20h], rax
0x18000e074  mov     [rdi+28h], rbp
0x18000e078  lock inc cs:dword_18002CFF8
0x18000e07f  jmp     short loc_18000E083
0x18000e081  xor     edi, edi
0x18000e083  test    rdi, rdi
0x18000e086  jz      short loc_18000E0CD
0x18000e088  lea     rcx, [rdi+30h]; this
0x18000e08c  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e091  xor     esi, esi
0x18000e093  test    eax, eax
0x18000e095  cmovs   esi, eax
0x18000e098  test    esi, esi
0x18000e09a  js      short loc_18000E0C5
0x18000e09c  lea     rcx, [rdi+18h]; this
0x18000e0a0  call    ?FinalConstruct@CMSMQRuleHandler@@QEAAJXZ; CMSMQRuleHandler::FinalConstruct(void)
0x18000e0a5  mov     esi, eax
0x18000e0a7  test    eax, eax
0x18000e0a9  jnz     short loc_18000E0C5
0x18000e0ab  mov     rax, [rdi]
0x18000e0ae  mov     r8, r14
0x18000e0b1  mov     rdx, r15
0x18000e0b4  mov     rcx, rdi
0x18000e0b7  mov     rax, [rax]
0x18000e0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bf  mov     esi, eax
0x18000e0c1  test    eax, eax
0x18000e0c3  jz      short loc_18000E0CD
0x18000e0c5  mov     rcx, rdi; Block
0x18000e0c8  call    ??_G?$CComAggObject@VCMSMQRuleHandler@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQRuleHandler>::`scalar deleting destructor'(uint)
0x18000e0cd  mov     eax, esi
0x18000e0cf  add     rsp, 28h
0x18000e0d3  pop     r15
0x18000e0d5  pop     r14
0x18000e0d7  pop     rdi
0x18000e0d8  pop     rsi
0x18000e0d9  pop     rbp
0x18000e0da  pop     rbx
0x18000e0db  retn
```
