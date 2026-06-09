# ATL::CComCreator<ATL::CComAggObject<CMSMQMessage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d1bc`
- end: `0x18000d29c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQMessage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc10`

## callees

- `0x18000173c`
- `0x18000b2e0`
- `0x18000d1bc`
- `0x18000e748`
- `0x18000f34c`
- `0x1800130f8`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQMessage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v7; // esi
  _QWORD *v8; // rax
  unsigned int v9; // edx
  _QWORD *v10; // rdi
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x61A8u);
  v10 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQMessage>::`vftable';
    CMSMQMessage::CMSMQMessage((CMSMQMessage *)(v8 + 3), v9);
    v10[3] = &ATL::CComContainedObject<CMSMQMessage>::`vftable'{for `ISupportErrorInfo'};
    v10[4] = &ATL::CComContainedObject<CMSMQMessage>::`vftable'{for `ATL::IDispatchImpl<IMSMQMessage4,&_GUID const IID_IMSMQMessage4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v10[5] = a1;
    _InterlockedIncrement(&dword_180038608);
  }
  else
  {
    v10 = 0;
  }
  if ( v10 )
  {
    v11 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v10 + 6));
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 < 0
      || (v7 = CMSMQQuery::FinalConstruct((CMSMQQuery *)(v10 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v10)(v10, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQMessage>::`scalar deleting destructor'(v10);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d1bc  push    rbx
0x18000d1be  push    rbp
0x18000d1bf  push    rsi
0x18000d1c0  push    rdi
0x18000d1c1  push    r14
0x18000d1c3  push    r15
0x18000d1c5  sub     rsp, 28h
0x18000d1c9  mov     r14, r8
0x18000d1cc  mov     r15, rdx
0x18000d1cf  mov     rbp, rcx
0x18000d1d2  test    r8, r8
0x18000d1d5  jnz     short loc_18000D1E1
0x18000d1d7  mov     eax, 80004003h
0x18000d1dc  jmp     loc_18000D28F
0x18000d1e1  mov     qword ptr [r8], 0
0x18000d1e8  mov     esi, 8007000Eh
0x18000d1ed  mov     ecx, 61A8h; Size
0x18000d1f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d1f7  mov     rdi, rax
0x18000d1fa  mov     [rsp+58h+arg_10], rax
0x18000d1ff  test    rax, rax
0x18000d202  jz      short loc_18000D241
0x18000d204  mov     dword ptr [rax+8], 0
0x18000d20b  lea     rax, ??_7?$CComAggObject@VCMSMQMessage@@@ATL@@6B@; const ATL::CComAggObject<CMSMQMessage>::`vftable'
0x18000d212  mov     [rdi], rax
0x18000d215  lea     rcx, [rdi+18h]; this
0x18000d219  call    ??0CMSMQMessage@@QEAA@XZ; CMSMQMessage::CMSMQMessage(void)
0x18000d21e  lea     rax, ??_7?$CComContainedObject@VCMSMQMessage@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQMessage>::`vftable'{for `ISupportErrorInfo'}
0x18000d225  mov     [rdi+18h], rax
0x18000d229  lea     rax, ??_7?$CComContainedObject@VCMSMQMessage@@@ATL@@6B?$IDispatchImpl@UIMSMQMessage4@@$1?IID_IMSMQMessage4@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQMessage>::`vftable'{for `ATL::IDispatchImpl<IMSMQMessage4,&_GUID const IID_IMSMQMessage4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d230  mov     [rdi+20h], rax
0x18000d234  mov     [rdi+28h], rbp
0x18000d238  lock inc cs:dword_180038608
0x18000d23f  jmp     short loc_18000D243
0x18000d241  xor     edi, edi
0x18000d243  test    rdi, rdi
0x18000d246  jz      short loc_18000D28D
0x18000d248  lea     rcx, [rdi+30h]; this
0x18000d24c  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d251  xor     esi, esi
0x18000d253  test    eax, eax
0x18000d255  cmovs   esi, eax
0x18000d258  test    esi, esi
0x18000d25a  js      short loc_18000D285
0x18000d25c  lea     rcx, [rdi+18h]; this
0x18000d260  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d265  mov     esi, eax
0x18000d267  test    eax, eax
0x18000d269  jnz     short loc_18000D285
0x18000d26b  mov     rax, [rdi]
0x18000d26e  mov     r8, r14
0x18000d271  mov     rdx, r15
0x18000d274  mov     rcx, rdi
0x18000d277  mov     rax, [rax]
0x18000d27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d27f  mov     esi, eax
0x18000d281  test    eax, eax
0x18000d283  jz      short loc_18000D28D
0x18000d285  mov     rcx, rdi; Block
0x18000d288  call    ??_G?$CComAggObject@VCMSMQMessage@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQMessage>::`scalar deleting destructor'(uint)
0x18000d28d  mov     eax, esi
0x18000d28f  add     rsp, 28h
0x18000d293  pop     r15
0x18000d295  pop     r14
0x18000d297  pop     rdi
0x18000d298  pop     rsi
0x18000d299  pop     rbp
0x18000d29a  pop     rbx
0x18000d29b  retn
```
