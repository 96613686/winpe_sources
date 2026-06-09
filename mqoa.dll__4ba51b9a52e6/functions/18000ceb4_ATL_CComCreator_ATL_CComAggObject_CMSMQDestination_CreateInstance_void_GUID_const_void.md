# ATL::CComCreator<ATL::CComAggObject<CMSMQDestination>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000ceb4`
- end: `0x18000cf9f`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQDestination@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cbb0`

## callees

- `0x18000173c`
- `0x18000b268`
- `0x18000ceb4`
- `0x18000e778`
- `0x18000f34c`
- `0x180021d68`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQDestination>>::CreateInstance(
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
  v8 = operator new(0xB8u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQDestination>::`vftable';
    CMSMQDestination::CMSMQDestination((CMSMQDestination *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQDestination>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQDestination>::`vftable'{for `ATL::IDispatchImpl<IMSMQDestination,&_GUID const IID_IMSMQDestination,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[5] = &ATL::CComContainedObject<CMSMQDestination>::`vftable'{for `ATL::IDispatchImpl<IMSMQPrivateDestination,&_GUID const IID_IMSMQPrivateDestination,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[6] = a1;
    _InterlockedIncrement(&dword_180038608);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v10 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v9 + 7));
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 < 0
      || (v7 = CMSMQDestination::FinalConstruct((CMSMQDestination *)(v9 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQDestination>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ceb4  push    rbx
0x18000ceb6  push    rbp
0x18000ceb7  push    rsi
0x18000ceb8  push    rdi
0x18000ceb9  push    r14
0x18000cebb  push    r15
0x18000cebd  sub     rsp, 28h
0x18000cec1  mov     r14, r8
0x18000cec4  mov     r15, rdx
0x18000cec7  mov     rbp, rcx
0x18000ceca  test    r8, r8
0x18000cecd  jnz     short loc_18000CED9
0x18000cecf  mov     eax, 80004003h
0x18000ced4  jmp     loc_18000CF92
0x18000ced9  mov     qword ptr [r8], 0
0x18000cee0  mov     esi, 8007000Eh
0x18000cee5  mov     ecx, 0B8h; Size
0x18000ceea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ceef  mov     rdi, rax
0x18000cef2  mov     [rsp+58h+arg_10], rax
0x18000cef7  test    rax, rax
0x18000cefa  jz      short loc_18000CF44
0x18000cefc  mov     dword ptr [rax+8], 0
0x18000cf03  lea     rax, ??_7?$CComAggObject@VCMSMQDestination@@@ATL@@6B@; const ATL::CComAggObject<CMSMQDestination>::`vftable'
0x18000cf0a  mov     [rdi], rax
0x18000cf0d  lea     rcx, [rdi+18h]; this
0x18000cf11  call    ??0CMSMQDestination@@QEAA@XZ; CMSMQDestination::CMSMQDestination(void)
0x18000cf16  lea     rax, ??_7?$CComContainedObject@VCMSMQDestination@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQDestination>::`vftable'{for `ISupportErrorInfo'}
0x18000cf1d  mov     [rdi+18h], rax
0x18000cf21  lea     rax, ??_7?$CComContainedObject@VCMSMQDestination@@@ATL@@6B?$IDispatchImpl@UIMSMQDestination@@$1?IID_IMSMQDestination@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQDestination>::`vftable'{for `ATL::IDispatchImpl<IMSMQDestination,&_GUID const IID_IMSMQDestination,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000cf28  mov     [rdi+20h], rax
0x18000cf2c  lea     rax, ??_7?$CComContainedObject@VCMSMQDestination@@@ATL@@6B?$IDispatchImpl@UIMSMQPrivateDestination@@$1?IID_IMSMQPrivateDestination@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQDestination>::`vftable'{for `ATL::IDispatchImpl<IMSMQPrivateDestination,&_GUID const IID_IMSMQPrivateDestination,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000cf33  mov     [rdi+28h], rax
0x18000cf37  mov     [rdi+30h], rbp
0x18000cf3b  lock inc cs:dword_180038608
0x18000cf42  jmp     short loc_18000CF46
0x18000cf44  xor     edi, edi
0x18000cf46  test    rdi, rdi
0x18000cf49  jz      short loc_18000CF90
0x18000cf4b  lea     rcx, [rdi+38h]; this
0x18000cf4f  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000cf54  xor     esi, esi
0x18000cf56  test    eax, eax
0x18000cf58  cmovs   esi, eax
0x18000cf5b  test    esi, esi
0x18000cf5d  js      short loc_18000CF88
0x18000cf5f  lea     rcx, [rdi+18h]; this
0x18000cf63  call    ?FinalConstruct@CMSMQDestination@@QEAAJXZ; CMSMQDestination::FinalConstruct(void)
0x18000cf68  mov     esi, eax
0x18000cf6a  test    eax, eax
0x18000cf6c  jnz     short loc_18000CF88
0x18000cf6e  mov     rax, [rdi]
0x18000cf71  mov     r8, r14
0x18000cf74  mov     rdx, r15
0x18000cf77  mov     rcx, rdi
0x18000cf7a  mov     rax, [rax]
0x18000cf7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf82  mov     esi, eax
0x18000cf84  test    eax, eax
0x18000cf86  jz      short loc_18000CF90
0x18000cf88  mov     rcx, rdi; Block
0x18000cf8b  call    ??_G?$CComAggObject@VCMSMQDestination@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQDestination>::`scalar deleting destructor'(uint)
0x18000cf90  mov     eax, esi
0x18000cf92  add     rsp, 28h
0x18000cf96  pop     r15
0x18000cf98  pop     r14
0x18000cf9a  pop     rdi
0x18000cf9b  pop     rsi
0x18000cf9c  pop     rbp
0x18000cf9d  pop     rbx
0x18000cf9e  retn
```
