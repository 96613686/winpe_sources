# ATL::CComCreator<ATL::CComAggObject<CMsftDiscRecorder2>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180029394`
- end: `0x18002948f`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMsftDiscRecorder2@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005cc0`

## callees

- `0x180005fa4`
- `0x18000c954`
- `0x18000f680`
- `0x18000fdd4`
- `0x180029394`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMsftDiscRecorder2>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  _QWORD *v10; // rcx
  int v11; // eax
  int v12; // edx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x110u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CMsftDiscRecorder2>::`vftable';
    CMsftDiscRecorder2::CMsftDiscRecorder2((CMsftDiscRecorder2 *)(v8 + 6));
    v10[3] = a1;
    v10[1] = &ATL::CComContainedObject<CMsftDiscRecorder2>::`vftable'{for `IDiscRecorder2Ex'};
    *v10 = &ATL::CComContainedObject<CMsftDiscRecorder2>::`vftable'{for `ATL::IDispatchImpl<IDiscRecorder2,&_GUID const IID_IDiscRecorder2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    v10[2] = &ATL::CComContainedObject<CMsftDiscRecorder2>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v11 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 14));
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    if ( v12 >= 0 )
      v12 = CMsftDiscRecorder2::FinalConstruct((CMsftDiscRecorder2 *)(v9 + 6));
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180029394  push    rbx
0x180029396  push    rbp
0x180029397  push    rsi
0x180029398  push    rdi
0x180029399  push    r14
0x18002939b  sub     rsp, 20h
0x18002939f  mov     rsi, r8
0x1800293a2  mov     rbp, rdx
0x1800293a5  mov     r14, rcx
0x1800293a8  test    r8, r8
0x1800293ab  jnz     short loc_1800293B7
0x1800293ad  mov     eax, 80004003h
0x1800293b2  jmp     loc_180029484
0x1800293b7  mov     ecx, 110h; Size
0x1800293bc  mov     qword ptr [r8], 0
0x1800293c3  mov     ebx, 8007000Eh
0x1800293c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800293cd  mov     rdi, rax
0x1800293d0  test    rax, rax
0x1800293d3  jz      loc_180029482
0x1800293d9  mov     dword ptr [rax+8], 0
0x1800293e0  lea     rcx, [rdi+18h]; this
0x1800293e4  lea     rax, ??_7?$CComAggObject@VCMsftDiscRecorder2@@@ATL@@6B@; const ATL::CComAggObject<CMsftDiscRecorder2>::`vftable'
0x1800293eb  mov     [rdi], rax
0x1800293ee  call    ??0CMsftDiscRecorder2@@QEAA@XZ; CMsftDiscRecorder2::CMsftDiscRecorder2(void)
0x1800293f3  mov     [rcx+18h], r14
0x1800293f7  lea     rax, ??_7?$CComContainedObject@VCMsftDiscRecorder2@@@ATL@@6BIDiscRecorder2Ex@@@; const ATL::CComContainedObject<CMsftDiscRecorder2>::`vftable'{for `IDiscRecorder2Ex'}
0x1800293fe  mov     [rcx+8], rax
0x180029402  lea     r8, ??_7?$CComContainedObject@VCMsftDiscRecorder2@@@ATL@@6B?$IDispatchImpl@UIDiscRecorder2@@$1?IID_IDiscRecorder2@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMsftDiscRecorder2>::`vftable'{for `ATL::IDispatchImpl<IDiscRecorder2,&_GUID const IID_IDiscRecorder2,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180029409  mov     [rcx], r8
0x18002940c  lea     rax, ??_7?$CComContainedObject@VCMsftDiscRecorder2@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMsftDiscRecorder2>::`vftable'{for `ISupportErrorInfo'}
0x180029413  mov     [rcx+10h], rax
0x180029417  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002941e  mov     rax, [rcx]
0x180029421  mov     rax, [rax+8]
0x180029425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002942a  lea     rcx, [rdi+38h]; this
0x18002942e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180029433  xor     edx, edx
0x180029435  test    eax, eax
0x180029437  cmovs   edx, eax
0x18002943a  test    edx, edx
0x18002943c  js      short loc_180029449
0x18002943e  lea     rcx, [rdi+18h]; this
0x180029442  call    ?FinalConstruct@CMsftDiscRecorder2@@QEAAJXZ; CMsftDiscRecorder2::FinalConstruct(void)
0x180029447  mov     edx, eax
0x180029449  xor     ebx, ebx
0x18002944b  test    edx, edx
0x18002944d  cmovs   ebx, edx
0x180029450  test    ebx, ebx
0x180029452  jnz     short loc_18002946E
0x180029454  mov     rax, [rdi]
0x180029457  mov     r8, rsi
0x18002945a  mov     rdx, rbp
0x18002945d  mov     rcx, rdi
0x180029460  mov     rax, [rax]
0x180029463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029468  mov     ebx, eax
0x18002946a  test    eax, eax
0x18002946c  jz      short loc_180029482
0x18002946e  mov     rcx, [rdi]
0x180029471  mov     edx, 1
0x180029476  mov     rax, [rcx+18h]
0x18002947a  mov     rcx, rdi
0x18002947d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029482  mov     eax, ebx
0x180029484  add     rsp, 20h
0x180029488  pop     r14
0x18002948a  pop     rdi
0x18002948b  pop     rsi
0x18002948c  pop     rbp
0x18002948d  pop     rbx
0x18002948e  retn
```
