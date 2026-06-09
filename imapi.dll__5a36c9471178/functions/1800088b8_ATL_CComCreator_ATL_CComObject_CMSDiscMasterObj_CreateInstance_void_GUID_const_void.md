# ATL::CComCreator<ATL::CComObject<CMSDiscMasterObj>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800088b8`
- end: `0x1800089ec`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSDiscMasterObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008770`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x1800088b8`
- `0x18000b1a4`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSDiscMasterObj>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  CMSDiscMasterObj *v7; // rax
  CMSDiscMasterObj *v8; // rbx
  ATL::CAtlModule *v9; // rcx
  volatile signed __int32 *v10; // rdi
  signed __int32 v11; // eax
  int v12; // eax
  int v13; // ecx
  signed __int32 v14; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSDiscMasterObj *)operator new(0x280u);
  v8 = v7;
  if ( v7 )
  {
    CMSDiscMasterObj::CMSDiscMasterObj(v7);
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IDiscMaster'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IJolietDiscMaster'};
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IRedbookDiscMaster'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<1,CMSDiscMasterObj,&_GUID const IID_DDiscFormat2DataEvents>'};
    *((_QWORD *)v8 + 9) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<2,CMSDiscMasterObj,&_GUID const IID_DDiscMaster2Events>'};
    *((_QWORD *)v8 + 15) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = (volatile signed __int32 *)((char *)v8 + 128);
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v11 = *v10;
    }
    while ( v11 != _InterlockedCompareExchange(v10, v11 + 1, v11) );
    v12 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v8 + 136));
    if ( v12 >= 0 )
      *((_BYTE *)v8 + 176) = 1;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v6 = 0;
    if ( v13 < 0 )
      v6 = v13;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v14 = *v10;
    }
    while ( v14 != _InterlockedCompareExchange(v10, v14 - 1, v14) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMSDiscMasterObj *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMSDiscMasterObj *, __int64))(*(_QWORD *)v8 + 144LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800088b8  push    rbx
0x1800088ba  push    rbp
0x1800088bb  push    rsi
0x1800088bc  push    rdi
0x1800088bd  push    r14
0x1800088bf  push    r15
0x1800088c1  sub     rsp, 28h
0x1800088c5  mov     r14, r8
0x1800088c8  mov     rbp, rdx
0x1800088cb  test    r8, r8
0x1800088ce  jnz     short loc_1800088DA
0x1800088d0  mov     eax, 80004003h
0x1800088d5  jmp     loc_1800089DF
0x1800088da  mov     ecx, 280h; Size
0x1800088df  mov     qword ptr [r8], 0
0x1800088e6  mov     esi, 8007000Eh
0x1800088eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800088f0  mov     rbx, rax
0x1800088f3  test    rax, rax
0x1800088f6  jz      loc_1800089DD
0x1800088fc  mov     rcx, rax; this
0x1800088ff  call    ??0CMSDiscMasterObj@@QEAA@XZ; CMSDiscMasterObj::CMSDiscMasterObj(void)
0x180008904  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000890b  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BIDiscMaster@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IDiscMaster'}
0x180008912  mov     [rbx], rax
0x180008915  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BIJolietDiscMaster@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IJolietDiscMaster'}
0x18000891c  mov     [rbx+8], rax
0x180008920  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BIRedbookDiscMaster@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IRedbookDiscMaster'}
0x180008927  mov     [rbx+10h], rax
0x18000892b  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6B?$IDispEventSimpleImpl@$00VCMSDiscMasterObj@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B@1@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<1,CMSDiscMasterObj,&_GUID const IID_DDiscFormat2DataEvents>'}
0x180008932  mov     [rbx+18h], rax
0x180008936  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6B?$IDispEventSimpleImpl@$01VCMSDiscMasterObj@@$1?IID_DDiscMaster2Events@@3U_GUID@@B@1@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<2,CMSDiscMasterObj,&_GUID const IID_DDiscMaster2Events>'}
0x18000893d  mov     [rbx+48h], rax
0x180008941  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ISupportErrorInfo'}
0x180008948  mov     [rbx+78h], rax
0x18000894c  mov     rax, [rcx]
0x18000894f  mov     rax, [rax+8]
0x180008953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008958  lea     rdi, [rbx+80h]
0x18000895f  mov     r15d, 7FFFFFFFh
0x180008965  jmp     short loc_180008970
0x180008967  lea     ecx, [rax+1]
0x18000896a  lock cmpxchg [rdi], ecx
0x18000896e  jz      short loc_180008977
0x180008970  mov     eax, [rdi]
0x180008972  cmp     eax, r15d
0x180008975  jnz     short loc_180008967
0x180008977  lea     rcx, [rdi+8]; this
0x18000897b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008980  test    eax, eax
0x180008982  js      short loc_180008988
0x180008984  mov     byte ptr [rdi+30h], 1
0x180008988  xor     ecx, ecx
0x18000898a  test    eax, eax
0x18000898c  cmovs   ecx, eax
0x18000898f  xor     esi, esi
0x180008991  test    ecx, ecx
0x180008993  cmovs   esi, ecx
0x180008996  jmp     short loc_1800089A1
0x180008998  lea     ecx, [rax-1]
0x18000899b  lock cmpxchg [rdi], ecx
0x18000899f  jz      short loc_1800089A8
0x1800089a1  mov     eax, [rdi]
0x1800089a3  cmp     eax, r15d
0x1800089a6  jnz     short loc_180008998
0x1800089a8  test    esi, esi
0x1800089aa  jnz     short loc_1800089C6
0x1800089ac  mov     rax, [rbx]
0x1800089af  mov     r8, r14
0x1800089b2  mov     rdx, rbp
0x1800089b5  mov     rcx, rbx
0x1800089b8  mov     rax, [rax]
0x1800089bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c0  mov     esi, eax
0x1800089c2  test    eax, eax
0x1800089c4  jz      short loc_1800089DD
0x1800089c6  mov     r8, [rbx]
0x1800089c9  mov     edx, 1
0x1800089ce  mov     rcx, rbx
0x1800089d1  mov     rax, [r8+90h]
0x1800089d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089dd  mov     eax, esi
0x1800089df  add     rsp, 28h
0x1800089e3  pop     r15
0x1800089e5  pop     r14
0x1800089e7  pop     rdi
0x1800089e8  pop     rsi
0x1800089e9  pop     rbp
0x1800089ea  pop     rbx
0x1800089eb  retn
```
