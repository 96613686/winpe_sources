# ATL::CComCreator<ATL::CComObject<CMSMQApplication>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d814`
- end: `0x18000d8dc`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQApplication@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cb70`

## callees

- `0x18000173c`
- `0x18000a8b0`
- `0x18000d814`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQApplication>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v6; // edi
  CMSMQApplication *v7; // rax
  CMSMQApplication *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSMQApplication *)operator new(0x88u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQApplication::CMSMQApplication(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQApplication>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQApplication>::`vftable'{for `ATL::IDispatchImpl<IMSMQApplication3,&_GUID const IID_IMSMQApplication3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_180038608);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v6 = ATL::CComAutoDeleteCriticalSection::Init((CMSMQApplication *)((char *)v8 + 24));
    if ( v6 >= 0 )
      v6 = CMSMQQuery::FinalConstruct(v8);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMSMQApplication *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMSMQApplication *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d814  mov     [rsp+arg_0], rcx
0x18000d819  push    rbx
0x18000d81a  push    rbp
0x18000d81b  push    rsi
0x18000d81c  push    rdi
0x18000d81d  sub     rsp, 28h
0x18000d821  mov     rsi, r8
0x18000d824  mov     rbp, rdx
0x18000d827  test    r8, r8
0x18000d82a  jnz     short loc_18000D836
0x18000d82c  mov     eax, 80004003h
0x18000d831  jmp     loc_18000D8D3
0x18000d836  mov     qword ptr [r8], 0
0x18000d83d  mov     edi, 8007000Eh
0x18000d842  mov     ecx, 88h; Size
0x18000d847  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d84c  mov     rbx, rax
0x18000d84f  mov     [rsp+48h+arg_0], rax
0x18000d854  test    rax, rax
0x18000d857  jz      short loc_18000D87F
0x18000d859  mov     rcx, rax; this
0x18000d85c  call    ??0CMSMQApplication@@QEAA@XZ; CMSMQApplication::CMSMQApplication(void)
0x18000d861  lea     rax, ??_7?$CComObject@VCMSMQApplication@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQApplication>::`vftable'{for `ISupportErrorInfo'}
0x18000d868  mov     [rbx], rax
0x18000d86b  lea     rax, ??_7?$CComObject@VCMSMQApplication@@@ATL@@6B?$IDispatchImpl@UIMSMQApplication3@@$1?IID_IMSMQApplication3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQApplication>::`vftable'{for `ATL::IDispatchImpl<IMSMQApplication3,&_GUID const IID_IMSMQApplication3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d872  mov     [rbx+8], rax
0x18000d876  lock inc cs:dword_180038608
0x18000d87d  jmp     short loc_18000D881
0x18000d87f  xor     ebx, ebx
0x18000d881  test    rbx, rbx
0x18000d884  jz      short loc_18000D8D1
0x18000d886  lea     rcx, [rbx+18h]; this
0x18000d88a  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d88f  mov     edi, eax
0x18000d891  test    eax, eax
0x18000d893  js      short loc_18000D89F
0x18000d895  mov     rcx, rbx; this
0x18000d898  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d89d  mov     edi, eax
0x18000d89f  test    edi, edi
0x18000d8a1  jnz     short loc_18000D8BD
0x18000d8a3  mov     rax, [rbx]
0x18000d8a6  mov     r8, rsi
0x18000d8a9  mov     rdx, rbp
0x18000d8ac  mov     rcx, rbx
0x18000d8af  mov     rax, [rax]
0x18000d8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8b7  mov     edi, eax
0x18000d8b9  test    eax, eax
0x18000d8bb  jz      short loc_18000D8D1
0x18000d8bd  mov     rax, [rbx]
0x18000d8c0  mov     edx, 1
0x18000d8c5  mov     rcx, rbx
0x18000d8c8  mov     rax, [rax+28h]
0x18000d8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8d1  mov     eax, edi
0x18000d8d3  add     rsp, 28h
0x18000d8d7  pop     rdi
0x18000d8d8  pop     rsi
0x18000d8d9  pop     rbp
0x18000d8da  pop     rbx
0x18000d8db  retn
```
