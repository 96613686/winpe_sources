# ATL::CComCreator<ATL::CComAggObject<CMSMQQueue>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d38c`
- end: `0x18000d46c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQQueue@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc50`

## callees

- `0x18000173c`
- `0x18000b330`
- `0x18000d38c`
- `0x18000e748`
- `0x18000f34c`
- `0x18001a638`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQQueue>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
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
  v8 = operator new(0x108u);
  v10 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQQueue>::`vftable';
    CMSMQQueue::CMSMQQueue((CMSMQQueue *)(v8 + 3), v9);
    v10[3] = &ATL::CComContainedObject<CMSMQQueue>::`vftable'{for `ISupportErrorInfo'};
    v10[4] = &ATL::CComContainedObject<CMSMQQueue>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueue4,&_GUID const IID_IMSMQQueue4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
      ATL::CComAggObject<CMSMQQueue>::`scalar deleting destructor'(v10);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d38c  push    rbx
0x18000d38e  push    rbp
0x18000d38f  push    rsi
0x18000d390  push    rdi
0x18000d391  push    r14
0x18000d393  push    r15
0x18000d395  sub     rsp, 28h
0x18000d399  mov     r14, r8
0x18000d39c  mov     r15, rdx
0x18000d39f  mov     rbp, rcx
0x18000d3a2  test    r8, r8
0x18000d3a5  jnz     short loc_18000D3B1
0x18000d3a7  mov     eax, 80004003h
0x18000d3ac  jmp     loc_18000D45F
0x18000d3b1  mov     qword ptr [r8], 0
0x18000d3b8  mov     esi, 8007000Eh
0x18000d3bd  mov     ecx, 108h; Size
0x18000d3c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d3c7  mov     rdi, rax
0x18000d3ca  mov     [rsp+58h+arg_10], rax
0x18000d3cf  test    rax, rax
0x18000d3d2  jz      short loc_18000D411
0x18000d3d4  mov     dword ptr [rax+8], 0
0x18000d3db  lea     rax, ??_7?$CComAggObject@VCMSMQQueue@@@ATL@@6B@; const ATL::CComAggObject<CMSMQQueue>::`vftable'
0x18000d3e2  mov     [rdi], rax
0x18000d3e5  lea     rcx, [rdi+18h]; this
0x18000d3e9  call    ??0CMSMQQueue@@QEAA@XZ; CMSMQQueue::CMSMQQueue(void)
0x18000d3ee  lea     rax, ??_7?$CComContainedObject@VCMSMQQueue@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQQueue>::`vftable'{for `ISupportErrorInfo'}
0x18000d3f5  mov     [rdi+18h], rax
0x18000d3f9  lea     rax, ??_7?$CComContainedObject@VCMSMQQueue@@@ATL@@6B?$IDispatchImpl@UIMSMQQueue4@@$1?IID_IMSMQQueue4@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQQueue>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueue4,&_GUID const IID_IMSMQQueue4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d400  mov     [rdi+20h], rax
0x18000d404  mov     [rdi+28h], rbp
0x18000d408  lock inc cs:dword_180038608
0x18000d40f  jmp     short loc_18000D413
0x18000d411  xor     edi, edi
0x18000d413  test    rdi, rdi
0x18000d416  jz      short loc_18000D45D
0x18000d418  lea     rcx, [rdi+30h]; this
0x18000d41c  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d421  xor     esi, esi
0x18000d423  test    eax, eax
0x18000d425  cmovs   esi, eax
0x18000d428  test    esi, esi
0x18000d42a  js      short loc_18000D455
0x18000d42c  lea     rcx, [rdi+18h]; this
0x18000d430  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d435  mov     esi, eax
0x18000d437  test    eax, eax
0x18000d439  jnz     short loc_18000D455
0x18000d43b  mov     rax, [rdi]
0x18000d43e  mov     r8, r14
0x18000d441  mov     rdx, r15
0x18000d444  mov     rcx, rdi
0x18000d447  mov     rax, [rax]
0x18000d44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d44f  mov     esi, eax
0x18000d451  test    eax, eax
0x18000d453  jz      short loc_18000D45D
0x18000d455  mov     rcx, rdi; Block
0x18000d458  call    ??_G?$CComAggObject@VCMSMQQueue@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQQueue>::`scalar deleting destructor'(uint)
0x18000d45d  mov     eax, esi
0x18000d45f  add     rsp, 28h
0x18000d463  pop     r15
0x18000d465  pop     r14
0x18000d467  pop     rdi
0x18000d468  pop     rsi
0x18000d469  pop     rbp
0x18000d46a  pop     rbx
0x18000d46b  retn
```
