# ATL::CComCreator<ATL::CComAggObject<CMSMQApplication>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000cce4`
- end: `0x18000cdc4`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQApplication@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cb70`

## callees

- `0x18000173c`
- `0x18000a8b0`
- `0x18000b218`
- `0x18000cce4`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQApplication>>::CreateInstance(
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
  v8 = operator new(0xA0u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQApplication>::`vftable';
    CMSMQApplication::CMSMQApplication((CMSMQApplication *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQApplication>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQApplication>::`vftable'{for `ATL::IDispatchImpl<IMSMQApplication3,&_GUID const IID_IMSMQApplication3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
      ATL::CComAggObject<CMSMQApplication>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000cce4  push    rbx
0x18000cce6  push    rbp
0x18000cce7  push    rsi
0x18000cce8  push    rdi
0x18000cce9  push    r14
0x18000cceb  push    r15
0x18000cced  sub     rsp, 28h
0x18000ccf1  mov     r14, r8
0x18000ccf4  mov     r15, rdx
0x18000ccf7  mov     rbp, rcx
0x18000ccfa  test    r8, r8
0x18000ccfd  jnz     short loc_18000CD09
0x18000ccff  mov     eax, 80004003h
0x18000cd04  jmp     loc_18000CDB7
0x18000cd09  mov     qword ptr [r8], 0
0x18000cd10  mov     esi, 8007000Eh
0x18000cd15  mov     ecx, 0A0h; Size
0x18000cd1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd1f  mov     rdi, rax
0x18000cd22  mov     [rsp+58h+arg_10], rax
0x18000cd27  test    rax, rax
0x18000cd2a  jz      short loc_18000CD69
0x18000cd2c  mov     dword ptr [rax+8], 0
0x18000cd33  lea     rax, ??_7?$CComAggObject@VCMSMQApplication@@@ATL@@6B@; const ATL::CComAggObject<CMSMQApplication>::`vftable'
0x18000cd3a  mov     [rdi], rax
0x18000cd3d  lea     rcx, [rdi+18h]; this
0x18000cd41  call    ??0CMSMQApplication@@QEAA@XZ; CMSMQApplication::CMSMQApplication(void)
0x18000cd46  lea     rax, ??_7?$CComContainedObject@VCMSMQApplication@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQApplication>::`vftable'{for `ISupportErrorInfo'}
0x18000cd4d  mov     [rdi+18h], rax
0x18000cd51  lea     rax, ??_7?$CComContainedObject@VCMSMQApplication@@@ATL@@6B?$IDispatchImpl@UIMSMQApplication3@@$1?IID_IMSMQApplication3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQApplication>::`vftable'{for `ATL::IDispatchImpl<IMSMQApplication3,&_GUID const IID_IMSMQApplication3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000cd58  mov     [rdi+20h], rax
0x18000cd5c  mov     [rdi+28h], rbp
0x18000cd60  lock inc cs:dword_180038608
0x18000cd67  jmp     short loc_18000CD6B
0x18000cd69  xor     edi, edi
0x18000cd6b  test    rdi, rdi
0x18000cd6e  jz      short loc_18000CDB5
0x18000cd70  lea     rcx, [rdi+30h]; this
0x18000cd74  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000cd79  xor     esi, esi
0x18000cd7b  test    eax, eax
0x18000cd7d  cmovs   esi, eax
0x18000cd80  test    esi, esi
0x18000cd82  js      short loc_18000CDAD
0x18000cd84  lea     rcx, [rdi+18h]; this
0x18000cd88  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000cd8d  mov     esi, eax
0x18000cd8f  test    eax, eax
0x18000cd91  jnz     short loc_18000CDAD
0x18000cd93  mov     rax, [rdi]
0x18000cd96  mov     r8, r14
0x18000cd99  mov     rdx, r15
0x18000cd9c  mov     rcx, rdi
0x18000cd9f  mov     rax, [rax]
0x18000cda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda7  mov     esi, eax
0x18000cda9  test    eax, eax
0x18000cdab  jz      short loc_18000CDB5
0x18000cdad  mov     rcx, rdi; Block
0x18000cdb0  call    ??_G?$CComAggObject@VCMSMQApplication@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQApplication>::`scalar deleting destructor'(uint)
0x18000cdb5  mov     eax, esi
0x18000cdb7  add     rsp, 28h
0x18000cdbb  pop     r15
0x18000cdbd  pop     r14
0x18000cdbf  pop     rdi
0x18000cdc0  pop     rsi
0x18000cdc1  pop     rbp
0x18000cdc2  pop     rbx
0x18000cdc3  retn
```
