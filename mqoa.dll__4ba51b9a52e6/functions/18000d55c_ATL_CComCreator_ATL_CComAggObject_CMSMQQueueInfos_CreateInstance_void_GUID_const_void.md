# ATL::CComCreator<ATL::CComAggObject<CMSMQQueueInfos>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d55c`
- end: `0x18000d63c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQQueueInfos@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc90`

## callees

- `0x18000173c`
- `0x18000b380`
- `0x18000d55c`
- `0x18000e748`
- `0x18000f34c`
- `0x18001f010`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQQueueInfos>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0xC0u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQQueueInfos>::`vftable';
    CMSMQQueueInfos::CMSMQQueueInfos((CMSMQQueueInfos *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQQueueInfos>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQQueueInfos>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueInfos4,&_GUID const IID_IMSMQQueueInfos4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[5] = a1;
    _InterlockedIncrement(&dword_180038608);
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
      || (v7 = CMSMQQuery::FinalConstruct((CMSMQQuery *)(v9 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQQueueInfos>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d55c  push    rbx
0x18000d55e  push    rbp
0x18000d55f  push    rsi
0x18000d560  push    rdi
0x18000d561  push    r14
0x18000d563  push    r15
0x18000d565  sub     rsp, 28h
0x18000d569  mov     r14, r8
0x18000d56c  mov     r15, rdx
0x18000d56f  mov     rbp, rcx
0x18000d572  test    r8, r8
0x18000d575  jnz     short loc_18000D581
0x18000d577  mov     eax, 80004003h
0x18000d57c  jmp     loc_18000D62F
0x18000d581  mov     qword ptr [r8], 0
0x18000d588  mov     esi, 8007000Eh
0x18000d58d  mov     ecx, 0C0h; Size
0x18000d592  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d597  mov     rdi, rax
0x18000d59a  mov     [rsp+58h+arg_10], rax
0x18000d59f  test    rax, rax
0x18000d5a2  jz      short loc_18000D5E1
0x18000d5a4  mov     dword ptr [rax+8], 0
0x18000d5ab  lea     rax, ??_7?$CComAggObject@VCMSMQQueueInfos@@@ATL@@6B@; const ATL::CComAggObject<CMSMQQueueInfos>::`vftable'
0x18000d5b2  mov     [rdi], rax
0x18000d5b5  lea     rcx, [rdi+18h]; this
0x18000d5b9  call    ??0CMSMQQueueInfos@@QEAA@XZ; CMSMQQueueInfos::CMSMQQueueInfos(void)
0x18000d5be  lea     rax, ??_7?$CComContainedObject@VCMSMQQueueInfos@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQQueueInfos>::`vftable'{for `ISupportErrorInfo'}
0x18000d5c5  mov     [rdi+18h], rax
0x18000d5c9  lea     rax, ??_7?$CComContainedObject@VCMSMQQueueInfos@@@ATL@@6B?$IDispatchImpl@UIMSMQQueueInfos4@@$1?IID_IMSMQQueueInfos4@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQQueueInfos>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueInfos4,&_GUID const IID_IMSMQQueueInfos4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d5d0  mov     [rdi+20h], rax
0x18000d5d4  mov     [rdi+28h], rbp
0x18000d5d8  lock inc cs:dword_180038608
0x18000d5df  jmp     short loc_18000D5E3
0x18000d5e1  xor     edi, edi
0x18000d5e3  test    rdi, rdi
0x18000d5e6  jz      short loc_18000D62D
0x18000d5e8  lea     rcx, [rdi+30h]; this
0x18000d5ec  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d5f1  xor     esi, esi
0x18000d5f3  test    eax, eax
0x18000d5f5  cmovs   esi, eax
0x18000d5f8  test    esi, esi
0x18000d5fa  js      short loc_18000D625
0x18000d5fc  lea     rcx, [rdi+18h]; this
0x18000d600  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d605  mov     esi, eax
0x18000d607  test    eax, eax
0x18000d609  jnz     short loc_18000D625
0x18000d60b  mov     rax, [rdi]
0x18000d60e  mov     r8, r14
0x18000d611  mov     rdx, r15
0x18000d614  mov     rcx, rdi
0x18000d617  mov     rax, [rax]
0x18000d61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61f  mov     esi, eax
0x18000d621  test    eax, eax
0x18000d623  jz      short loc_18000D62D
0x18000d625  mov     rcx, rdi; Block
0x18000d628  call    ??_G?$CComAggObject@VCMSMQQueueInfos@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQQueueInfos>::`scalar deleting destructor'(uint)
0x18000d62d  mov     eax, esi
0x18000d62f  add     rsp, 28h
0x18000d633  pop     r15
0x18000d635  pop     r14
0x18000d637  pop     rdi
0x18000d638  pop     rsi
0x18000d639  pop     rbp
0x18000d63a  pop     rbx
0x18000d63b  retn
```
