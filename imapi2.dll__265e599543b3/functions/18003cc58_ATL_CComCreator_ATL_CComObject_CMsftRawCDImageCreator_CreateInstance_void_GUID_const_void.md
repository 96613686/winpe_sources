# ATL::CComCreator<ATL::CComObject<CMsftRawCDImageCreator>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18003cc58`
- end: `0x18003cd88`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsftRawCDImageCreator@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003cc30`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x180010e70`
- `0x18003cc58`
- `0x18003d884`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsftRawCDImageCreator>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  char *v7; // rax
  char *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (char *)operator new(0xA948u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 4) = 0;
    *(_OWORD *)(v7 + 24) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *((_QWORD *)v7 + 7) = 0;
    v7[64] = 0;
    *(_QWORD *)v7 = &CMsftRawCDImageCreator::`vftable'{for `ATL::IDispatchImpl<IRawCDImageCreator,&_GUID const IID_IRawCDImageCreator,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 1) = &CMsftRawCDImageCreator::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v7 + 12) = 0;
    `vector constructor iterator'(v7 + 128, 0x1B0u, 0x64u, (void *(*)(void *))CTrackData::CTrackData);
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<CMsftRawCDImageCreator>::`vftable'{for `ATL::IDispatchImpl<IRawCDImageCreator,&_GUID const IID_IRawCDImageCreator,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMsftRawCDImageCreator>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 4);
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 24));
    if ( v10 >= 0 )
      v10 = CMsftRawCDImageCreator::FinalConstruct((CMsftRawCDImageCreator *)v8);
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 208LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18003cc58  push    rbx
0x18003cc5a  push    rbp
0x18003cc5b  push    rsi
0x18003cc5c  push    rdi
0x18003cc5d  push    r14
0x18003cc5f  sub     rsp, 20h
0x18003cc63  mov     rsi, r8
0x18003cc66  mov     rbp, rdx
0x18003cc69  test    r8, r8
0x18003cc6c  jnz     short loc_18003CC78
0x18003cc6e  mov     eax, 80004003h
0x18003cc73  jmp     loc_18003CD7D
0x18003cc78  mov     ecx, 0A948h; Size
0x18003cc7d  mov     qword ptr [r8], 0
0x18003cc84  mov     edi, 8007000Eh
0x18003cc89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cc8e  mov     rbx, rax
0x18003cc91  test    rax, rax
0x18003cc94  jz      loc_18003CD7B
0x18003cc9a  mov     dword ptr [rax+10h], 0
0x18003cca1  lea     rcx, [rbx+80h]; void *
0x18003cca8  xor     eax, eax
0x18003ccaa  lea     r9, ??0CTrackData@@QEAA@XZ; void *(*)(void *)
0x18003ccb1  xorps   xmm0, xmm0
0x18003ccb4  mov     edx, 1B0h; unsigned __int64
0x18003ccb9  movups  xmmword ptr [rbx+18h], xmm0
0x18003ccbd  mov     r8d, 64h ; 'd'; unsigned __int64
0x18003ccc3  movups  xmmword ptr [rbx+28h], xmm0
0x18003ccc7  mov     [rbx+38h], rax
0x18003cccb  mov     [rbx+40h], al
0x18003ccce  lea     rax, ??_7CMsftRawCDImageCreator@@6B?$IDispatchImpl@UIRawCDImageCreator@@$1?IID_IRawCDImageCreator@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CMsftRawCDImageCreator::`vftable'{for `ATL::IDispatchImpl<IRawCDImageCreator,&_GUID const IID_IRawCDImageCreator,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18003ccd5  mov     [rbx], rax
0x18003ccd8  lea     rax, ??_7CMsftRawCDImageCreator@@6BISupportErrorInfo@@@; const CMsftRawCDImageCreator::`vftable'{for `ISupportErrorInfo'}
0x18003ccdf  mov     [rbx+8], rax
0x18003cce3  mov     qword ptr [rbx+60h], 0
0x18003cceb  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003ccf0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003ccf7  lea     rax, ??_7?$CComObject@VCMsftRawCDImageCreator@@@ATL@@6B?$IDispatchImpl@UIRawCDImageCreator@@$1?IID_IRawCDImageCreator@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftRawCDImageCreator>::`vftable'{for `ATL::IDispatchImpl<IRawCDImageCreator,&_GUID const IID_IRawCDImageCreator,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18003ccfe  mov     [rbx], rax
0x18003cd01  lea     rax, ??_7?$CComObject@VCMsftRawCDImageCreator@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftRawCDImageCreator>::`vftable'{for `ISupportErrorInfo'}
0x18003cd08  mov     [rbx+8], rax
0x18003cd0c  mov     rax, [rcx]
0x18003cd0f  mov     rax, [rax+8]
0x18003cd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd18  lea     rcx, [rbx+10h]; volatile int *
0x18003cd1c  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18003cd21  lea     rcx, [rbx+18h]; this
0x18003cd25  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18003cd2a  test    eax, eax
0x18003cd2c  js      short loc_18003CD36
0x18003cd2e  mov     rcx, rbx; this
0x18003cd31  call    ?FinalConstruct@CMsftRawCDImageCreator@@QEAAJXZ; CMsftRawCDImageCreator::FinalConstruct(void)
0x18003cd36  xor     edi, edi
0x18003cd38  lea     rcx, [rbx+10h]; volatile int *
0x18003cd3c  test    eax, eax
0x18003cd3e  cmovs   edi, eax
0x18003cd41  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18003cd46  test    edi, edi
0x18003cd48  jnz     short loc_18003CD64
0x18003cd4a  mov     rax, [rbx]
0x18003cd4d  mov     r8, rsi
0x18003cd50  mov     rdx, rbp
0x18003cd53  mov     rcx, rbx
0x18003cd56  mov     rax, [rax]
0x18003cd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd5e  mov     edi, eax
0x18003cd60  test    eax, eax
0x18003cd62  jz      short loc_18003CD7B
0x18003cd64  mov     rcx, [rbx]
0x18003cd67  mov     edx, 1
0x18003cd6c  mov     rax, [rcx+0D0h]
0x18003cd73  mov     rcx, rbx
0x18003cd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd7b  mov     eax, edi
0x18003cd7d  add     rsp, 20h
0x18003cd81  pop     r14
0x18003cd83  pop     rdi
0x18003cd84  pop     rsi
0x18003cd85  pop     rbp
0x18003cd86  pop     rbx
0x18003cd87  retn
```
