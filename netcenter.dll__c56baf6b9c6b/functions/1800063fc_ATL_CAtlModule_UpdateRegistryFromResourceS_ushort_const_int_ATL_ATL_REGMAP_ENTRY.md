# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800063fc`
- end: `0x180006684`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `648`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800066a0`

## callees

- `0x180002270`
- `0x1800022b0`
- `0x180003ee8`
- `0x180003fc0`
- `0x1800043a0`
- `0x180004aec`
- `0x180004e08`
- `0x180004fbc`
- `0x180005760`
- `0x1800063fc`
- `0x1800066ac`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800064dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800064dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000652b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000652b`

## string_xrefs

- `0x18000661a`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // eax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v23);
  if ( v8 < 0 )
  {
    Error = v8;
    goto LABEL_33;
  }
  v25 = 1;
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v21,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v10 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_9:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_33;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_33;
    }
    ATL::CAtlModule::EscapeSingleQuote(v29, v12, Filename);
    if ( !v10 || v10 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v13, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_33;
      }
      v15 = -1;
      do
        ++v15;
      while ( v28[v15 - 1] );
      v28[(int)v15 - 1] = 34;
      v16 = 2LL * (int)v15 + 2;
      if ( v16 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v28[-1] + v16) = 0;
      v14 = &v27;
    }
    else
    {
      v14 = v29;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v14);
    if ( Error < 0 )
      goto LABEL_9;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
    if ( Error < 0 )
      goto LABEL_9;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_28:
        Error = v17;
LABEL_30:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_9;
      }
    }
    else if ( a2 )
    {
      v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_28;
    }
    Error = -2147024809;
    goto LABEL_30;
  }
LABEL_33:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800063fc  mov     [rsp-8+arg_10], rbx
0x180006401  push    rbp
0x180006402  push    rsi
0x180006403  push    rdi
0x180006404  push    r14
0x180006406  push    r15
0x180006408  lea     rbp, [rsp-9E0h]
0x180006410  sub     rsp, 0AE0h
0x180006417  mov     rax, cs:__security_cookie
0x18000641e  xor     rax, rsp
0x180006421  mov     [rbp+0A00h+var_30], rax
0x180006428  mov     rbx, r9
0x18000642b  mov     r14d, r8d
0x18000642e  mov     rdi, rdx
0x180006431  mov     rsi, rcx
0x180006434  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000643b  mov     [rsp+0B00h+var_AC0], rax
0x180006440  xor     r15d, r15d
0x180006443  mov     [rsp+0B00h+var_AB8], r15
0x180006448  mov     [rsp+0B00h+var_AB0], r15
0x18000644d  mov     [rsp+0B00h+var_AA8], r15d
0x180006452  xorps   xmm0, xmm0
0x180006455  xor     eax, eax
0x180006457  movups  [rsp+0B00h+var_AA0], xmm0
0x18000645c  movups  [rsp+0B00h+var_A90], xmm0
0x180006461  mov     [rbp+0A00h+var_A80], rax
0x180006465  mov     [rbp+0A00h+var_A78], r15b
0x180006469  lea     rcx, [rsp+0B00h+var_AA0]; this
0x18000646e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006473  test    eax, eax
0x180006475  js      loc_180006650
0x18000647b  mov     [rbp+0A00h+var_A78], 1
0x18000647f  test    rbx, rbx
0x180006482  jz      short loc_1800064A3
0x180006484  jmp     short loc_18000649B
0x180006486  mov     r8, [rbx+8]; unsigned __int16 *
0x18000648a  mov     rdx, rax; unsigned __int16 *
0x18000648d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180006492  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006497  lea     rbx, [rbx+10h]
0x18000649b  mov     rax, [rbx]
0x18000649e  test    rax, rax
0x1800064a1  jnz     short loc_180006486
0x1800064a3  mov     rax, [rsi]
0x1800064a6  lea     rdx, [rsp+0B00h+var_AC0]
0x1800064ab  mov     rcx, rsi
0x1800064ae  mov     rax, [rax+28h]
0x1800064b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b7  mov     ebx, eax
0x1800064b9  test    eax, eax
0x1800064bb  js      loc_180006652
0x1800064c1  mov     [rsp+0B00h+var_AD0], r15
0x1800064c6  mov     rbx, cs:hModule
0x1800064cd  mov     esi, 104h
0x1800064d2  mov     r8d, esi; nSize
0x1800064d5  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800064d9  mov     rcx, rbx; hModule
0x1800064dc  call    cs:__imp_GetModuleFileNameW
0x1800064e2  test    eax, eax
0x1800064e4  jnz     short loc_1800064FC
0x1800064e6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800064eb  mov     ebx, eax
0x1800064ed  lea     rcx, [rsp+0B00h+var_AD0]
0x1800064f2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800064f7  jmp     loc_180006652
0x1800064fc  cmp     eax, esi
0x1800064fe  jnz     short loc_180006514
0x180006500  lea     rcx, [rsp+0B00h+var_AD0]
0x180006505  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000650a  mov     ebx, 8007007Ah
0x18000650f  jmp     loc_180006652
0x180006514  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006518  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000651f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180006524  test    rbx, rbx
0x180006527  jz      short loc_18000653F
0x180006529  xor     ecx, ecx; lpModuleName
0x18000652b  call    cs:__imp_GetModuleHandleW
0x180006531  cmp     rbx, rax
0x180006534  jz      short loc_18000653F
0x180006536  lea     r8, [rbp+0A00h+var_440]
0x18000653d  jmp     short loc_1800065BA
0x18000653f  mov     ebx, 22h ; '"'
0x180006544  mov     [rbp+0A00h+var_860], bx
0x18000654b  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x180006552  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x180006559  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000655e  test    al, al
0x180006560  jnz     short loc_180006576
0x180006562  lea     rcx, [rsp+0B00h+var_AD0]
0x180006567  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000656c  mov     ebx, 80004005h
0x180006571  jmp     loc_180006652
0x180006576  lea     rcx, [rbp+0A00h+var_860]
0x18000657d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006581  inc     rax
0x180006584  cmp     [rcx+rax*2], r15w
0x180006589  jnz     short loc_180006581
0x18000658b  cdqe
0x18000658d  mov     [rbp+rax*2+0A00h+var_860], bx
0x180006595  lea     rcx, ds:2[rax*2]
0x18000659d  cmp     rcx, 418h
0x1800065a4  jnb     loc_18000664A
0x1800065aa  mov     [rbp+rcx+0A00h+var_860], r15w
0x1800065b3  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x1800065ba  lea     rdx, aModule; "Module"
0x1800065c1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800065c6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800065cb  mov     ebx, eax
0x1800065cd  test    eax, eax
0x1800065cf  js      loc_1800064ED
0x1800065d5  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800065dc  lea     rdx, aModuleRaw; "Module_Raw"
0x1800065e3  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800065e8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800065ed  mov     ebx, eax
0x1800065ef  test    eax, eax
0x1800065f1  js      loc_1800064ED
0x1800065f7  mov     [rsp+0B00h+var_AC8], r15
0x1800065fc  test    r14d, r14d
0x1800065ff  jz      short loc_180006610
0x180006601  test    rdi, rdi
0x180006604  jz      short loc_180006636
0x180006606  mov     [rsp+0B00h+var_AE0], 1
0x18000660e  jmp     short loc_18000661A
0x180006610  test    rdi, rdi
0x180006613  jz      short loc_180006636
0x180006615  mov     [rsp+0B00h+var_AE0], r15d; int
0x18000661a  lea     r9, aRegistry; "REGISTRY"
0x180006621  mov     r8, rdi; unsigned __int16 *
0x180006624  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006628  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000662d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006632  mov     ebx, eax
0x180006634  jmp     short loc_18000663B
0x180006636  mov     ebx, 80070057h
0x18000663b  lea     rcx, [rsp+0B00h+var_AC8]
0x180006640  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006645  jmp     loc_1800064ED
0x18000664a  call    __report_rangecheckfailure
0x180006650  mov     ebx, eax
0x180006652  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180006657  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000665c  mov     eax, ebx
0x18000665e  mov     rcx, [rbp+0A00h+var_30]
0x180006665  xor     rcx, rsp; StackCookie
0x180006668  call    __security_check_cookie
0x18000666d  mov     rbx, [rsp+0B00h+arg_10]
0x180006675  add     rsp, 0AE0h
0x18000667c  pop     r15
0x18000667e  pop     r14
0x180006680  pop     rdi
0x180006681  pop     rsi
0x180006682  pop     rbp
0x180006683  retn
```
