# ATL::CComCreator<ATL::CComAggObject<CMSDiscMasterObj>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008784`
- end: `0x1800088af`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSDiscMasterObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008770`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x180008784`
- `0x18000b1a4`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSDiscMasterObj>>::CreateInstance(
        ULONG_PTR a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  struct _RTL_CRITICAL_SECTION *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  ATL::CAtlModule *v10; // rcx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (struct _RTL_CRITICAL_SECTION *)operator new(0x298u);
  v9 = v8;
  if ( v8 )
  {
    v8->LockCount = 0;
    v8->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMSDiscMasterObj>::`vftable';
    CMSDiscMasterObj::CMSDiscMasterObj((CMSDiscMasterObj *)&v8->LockSemaphore);
    v10 = ATL::_pAtlModule;
    v9->LockSemaphore = &ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `IDiscMaster'};
    v9->SpinCount = (ULONG_PTR)&ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `IJolietDiscMaster'};
    v9[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `IRedbookDiscMaster'};
    *(_QWORD *)&v9[1].LockCount = &ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<1,CMSDiscMasterObj,&_GUID const IID_DDiscFormat2DataEvents>'};
    v9[2].OwningThread = &ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<2,CMSDiscMasterObj,&_GUID const IID_DDiscMaster2Events>'};
    v9[3].LockSemaphore = &ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `ISupportErrorInfo'};
    v9[3].SpinCount = a1;
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = ATL::CComCriticalSection::Init(v9 + 4);
    if ( v11 >= 0 )
      LOBYTE(v9[5].DebugInfo) = 1;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v7 = 0;
    if ( v13 < 0 )
      v7 = v13;
    if ( v7
      || (v7 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v9->DebugInfo->Type)(
                 v9,
                 a2,
                 a3)) != 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v9->DebugInfo->ProcessLocksList.Blink)(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180008784  push    rbx
0x180008786  push    rbp
0x180008787  push    rsi
0x180008788  push    rdi
0x180008789  push    r14
0x18000878b  sub     rsp, 20h
0x18000878f  mov     rsi, r8
0x180008792  mov     rbp, rdx
0x180008795  mov     r14, rcx
0x180008798  test    r8, r8
0x18000879b  jnz     short loc_1800087A7
0x18000879d  mov     eax, 80004003h
0x1800087a2  jmp     loc_1800088A4
0x1800087a7  mov     ecx, 298h; Size
0x1800087ac  mov     qword ptr [r8], 0
0x1800087b3  mov     ebx, 8007000Eh
0x1800087b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800087bd  mov     rdi, rax
0x1800087c0  test    rax, rax
0x1800087c3  jz      loc_1800088A2
0x1800087c9  mov     dword ptr [rax+8], 0
0x1800087d0  lea     rcx, [rdi+18h]; this
0x1800087d4  lea     rax, ??_7?$CComAggObject@VCMSDiscMasterObj@@@ATL@@6B@; const ATL::CComAggObject<CMSDiscMasterObj>::`vftable'
0x1800087db  mov     [rdi], rax
0x1800087de  call    ??0CMSDiscMasterObj@@QEAA@XZ; CMSDiscMasterObj::CMSDiscMasterObj(void)
0x1800087e3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800087ea  lea     rax, ??_7?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@6BIDiscMaster@@@; const ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `IDiscMaster'}
0x1800087f1  mov     [rdi+18h], rax
0x1800087f5  lea     rax, ??_7?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@6BIJolietDiscMaster@@@; const ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `IJolietDiscMaster'}
0x1800087fc  mov     [rdi+20h], rax
0x180008800  lea     rax, ??_7?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@6BIRedbookDiscMaster@@@; const ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `IRedbookDiscMaster'}
0x180008807  mov     [rdi+28h], rax
0x18000880b  lea     rax, ??_7?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@6B?$IDispEventSimpleImpl@$00VCMSDiscMasterObj@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B@1@@; const ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<1,CMSDiscMasterObj,&_GUID const IID_DDiscFormat2DataEvents>'}
0x180008812  mov     [rdi+30h], rax
0x180008816  lea     rax, ??_7?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@6B?$IDispEventSimpleImpl@$01VCMSDiscMasterObj@@$1?IID_DDiscMaster2Events@@3U_GUID@@B@1@@; const ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<2,CMSDiscMasterObj,&_GUID const IID_DDiscMaster2Events>'}
0x18000881d  mov     [rdi+60h], rax
0x180008821  lea     rax, ??_7?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSDiscMasterObj>::`vftable'{for `ISupportErrorInfo'}
0x180008828  mov     [rdi+90h], rax
0x18000882f  mov     [rdi+98h], r14
0x180008836  mov     rax, [rcx]
0x180008839  mov     rax, [rax+8]
0x18000883d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008842  lea     rbx, [rdi+0A0h]
0x180008849  mov     rcx, rbx; this
0x18000884c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008851  mov     ecx, eax
0x180008853  test    eax, eax
0x180008855  js      short loc_18000885B
0x180008857  mov     byte ptr [rbx+28h], 1
0x18000885b  xor     eax, eax
0x18000885d  test    ecx, ecx
0x18000885f  cmovs   eax, ecx
0x180008862  xor     ecx, ecx
0x180008864  test    eax, eax
0x180008866  cmovs   ecx, eax
0x180008869  xor     ebx, ebx
0x18000886b  test    ecx, ecx
0x18000886d  cmovs   ebx, ecx
0x180008870  test    ebx, ebx
0x180008872  jnz     short loc_18000888E
0x180008874  mov     rax, [rdi]
0x180008877  mov     r8, rsi
0x18000887a  mov     rdx, rbp
0x18000887d  mov     rcx, rdi
0x180008880  mov     rax, [rax]
0x180008883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008888  mov     ebx, eax
0x18000888a  test    eax, eax
0x18000888c  jz      short loc_1800088A2
0x18000888e  mov     rcx, [rdi]
0x180008891  mov     edx, 1
0x180008896  mov     rax, [rcx+18h]
0x18000889a  mov     rcx, rdi
0x18000889d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088a2  mov     eax, ebx
0x1800088a4  add     rsp, 20h
0x1800088a8  pop     r14
0x1800088aa  pop     rdi
0x1800088ab  pop     rsi
0x1800088ac  pop     rbp
0x1800088ad  pop     rbx
0x1800088ae  retn
```
