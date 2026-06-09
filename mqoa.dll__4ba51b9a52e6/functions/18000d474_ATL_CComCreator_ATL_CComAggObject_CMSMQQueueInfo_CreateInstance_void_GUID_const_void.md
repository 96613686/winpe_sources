# ATL::CComCreator<ATL::CComAggObject<CMSMQQueueInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d474`
- end: `0x18000d554`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQQueueInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc70`

## callees

- `0x18000173c`
- `0x18000b358`
- `0x18000d474`
- `0x18000e748`
- `0x18000f34c`
- `0x18001c928`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQQueueInfo>>::CreateInstance(
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
  v8 = operator new(0x110u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQQueueInfo>::`vftable';
    CMSMQQueueInfo::CMSMQQueueInfo((CMSMQQueueInfo *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQQueueInfo>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQQueueInfo>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueInfo4,&_GUID const IID_IMSMQQueueInfo4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
      ATL::CComAggObject<CMSMQQueueInfo>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d474  push    rbx
0x18000d476  push    rbp
0x18000d477  push    rsi
0x18000d478  push    rdi
0x18000d479  push    r14
0x18000d47b  push    r15
0x18000d47d  sub     rsp, 28h
0x18000d481  mov     r14, r8
0x18000d484  mov     r15, rdx
0x18000d487  mov     rbp, rcx
0x18000d48a  test    r8, r8
0x18000d48d  jnz     short loc_18000D499
0x18000d48f  mov     eax, 80004003h
0x18000d494  jmp     loc_18000D547
0x18000d499  mov     qword ptr [r8], 0
0x18000d4a0  mov     esi, 8007000Eh
0x18000d4a5  mov     ecx, 110h; Size
0x18000d4aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d4af  mov     rdi, rax
0x18000d4b2  mov     [rsp+58h+arg_10], rax
0x18000d4b7  test    rax, rax
0x18000d4ba  jz      short loc_18000D4F9
0x18000d4bc  mov     dword ptr [rax+8], 0
0x18000d4c3  lea     rax, ??_7?$CComAggObject@VCMSMQQueueInfo@@@ATL@@6B@; const ATL::CComAggObject<CMSMQQueueInfo>::`vftable'
0x18000d4ca  mov     [rdi], rax
0x18000d4cd  lea     rcx, [rdi+18h]; this
0x18000d4d1  call    ??0CMSMQQueueInfo@@QEAA@XZ; CMSMQQueueInfo::CMSMQQueueInfo(void)
0x18000d4d6  lea     rax, ??_7?$CComContainedObject@VCMSMQQueueInfo@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQQueueInfo>::`vftable'{for `ISupportErrorInfo'}
0x18000d4dd  mov     [rdi+18h], rax
0x18000d4e1  lea     rax, ??_7?$CComContainedObject@VCMSMQQueueInfo@@@ATL@@6B?$IDispatchImpl@UIMSMQQueueInfo4@@$1?IID_IMSMQQueueInfo4@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQQueueInfo>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueInfo4,&_GUID const IID_IMSMQQueueInfo4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d4e8  mov     [rdi+20h], rax
0x18000d4ec  mov     [rdi+28h], rbp
0x18000d4f0  lock inc cs:dword_180038608
0x18000d4f7  jmp     short loc_18000D4FB
0x18000d4f9  xor     edi, edi
0x18000d4fb  test    rdi, rdi
0x18000d4fe  jz      short loc_18000D545
0x18000d500  lea     rcx, [rdi+30h]; this
0x18000d504  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d509  xor     esi, esi
0x18000d50b  test    eax, eax
0x18000d50d  cmovs   esi, eax
0x18000d510  test    esi, esi
0x18000d512  js      short loc_18000D53D
0x18000d514  lea     rcx, [rdi+18h]; this
0x18000d518  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d51d  mov     esi, eax
0x18000d51f  test    eax, eax
0x18000d521  jnz     short loc_18000D53D
0x18000d523  mov     rax, [rdi]
0x18000d526  mov     r8, r14
0x18000d529  mov     rdx, r15
0x18000d52c  mov     rcx, rdi
0x18000d52f  mov     rax, [rax]
0x18000d532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d537  mov     esi, eax
0x18000d539  test    eax, eax
0x18000d53b  jz      short loc_18000D545
0x18000d53d  mov     rcx, rdi; Block
0x18000d540  call    ??_G?$CComAggObject@VCMSMQQueueInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQQueueInfo>::`scalar deleting destructor'(uint)
0x18000d545  mov     eax, esi
0x18000d547  add     rsp, 28h
0x18000d54b  pop     r15
0x18000d54d  pop     r14
0x18000d54f  pop     rdi
0x18000d550  pop     rsi
0x18000d551  pop     rbp
0x18000d552  pop     rbx
0x18000d553  retn
```
