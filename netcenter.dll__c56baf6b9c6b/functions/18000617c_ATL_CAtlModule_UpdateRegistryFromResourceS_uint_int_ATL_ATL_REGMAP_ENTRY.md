# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000617c`
- end: `0x1800063f3`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `631`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006690`

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
- `0x18000617c`
- `0x1800066ac`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000625c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000625c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062ab`

## string_xrefs

- `0x180006380`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
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
    goto LABEL_29;
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
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147024774;
        goto LABEL_29;
      }
      ATL::CAtlModule::EscapeSingleQuote(v29, v12, Filename);
      if ( !v10 || v10 == GetModuleHandleW(0) )
      {
        v27 = 34;
        if ( !ocscpy_s(v28, v13, v29) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_29;
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v17;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  }
LABEL_29:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000617c  mov     [rsp-8+arg_10], rbx
0x180006181  push    rbp
0x180006182  push    rsi
0x180006183  push    rdi
0x180006184  push    r14
0x180006186  push    r15
0x180006188  lea     rbp, [rsp-9E0h]
0x180006190  sub     rsp, 0AE0h
0x180006197  mov     rax, cs:__security_cookie
0x18000619e  xor     rax, rsp
0x1800061a1  mov     [rbp+0A00h+var_30], rax
0x1800061a8  mov     rbx, r9
0x1800061ab  mov     esi, r8d
0x1800061ae  mov     r14d, edx
0x1800061b1  mov     rdi, rcx
0x1800061b4  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800061bb  mov     [rsp+0B00h+var_AC0], rax
0x1800061c0  xor     r15d, r15d
0x1800061c3  mov     [rsp+0B00h+var_AB8], r15
0x1800061c8  mov     [rsp+0B00h+var_AB0], r15
0x1800061cd  mov     [rsp+0B00h+var_AA8], r15d
0x1800061d2  xorps   xmm0, xmm0
0x1800061d5  xor     eax, eax
0x1800061d7  movups  [rsp+0B00h+var_AA0], xmm0
0x1800061dc  movups  [rsp+0B00h+var_A90], xmm0
0x1800061e1  mov     [rbp+0A00h+var_A80], rax
0x1800061e5  mov     [rbp+0A00h+var_A78], r15b
0x1800061e9  lea     rcx, [rsp+0B00h+var_AA0]; this
0x1800061ee  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800061f3  test    eax, eax
0x1800061f5  js      loc_1800063BF
0x1800061fb  mov     [rbp+0A00h+var_A78], 1
0x1800061ff  test    rbx, rbx
0x180006202  jz      short loc_180006223
0x180006204  jmp     short loc_18000621B
0x180006206  mov     r8, [rbx+8]; unsigned __int16 *
0x18000620a  mov     rdx, rax; unsigned __int16 *
0x18000620d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180006212  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006217  lea     rbx, [rbx+10h]
0x18000621b  mov     rax, [rbx]
0x18000621e  test    rax, rax
0x180006221  jnz     short loc_180006206
0x180006223  mov     rax, [rdi]
0x180006226  lea     rdx, [rsp+0B00h+var_AC0]
0x18000622b  mov     rcx, rdi
0x18000622e  mov     rax, [rax+28h]
0x180006232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006237  mov     ebx, eax
0x180006239  test    eax, eax
0x18000623b  js      loc_1800063C1
0x180006241  mov     [rsp+0B00h+var_AD0], r15
0x180006246  mov     rbx, cs:hModule
0x18000624d  mov     edi, 104h
0x180006252  mov     r8d, edi; nSize
0x180006255  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180006259  mov     rcx, rbx; hModule
0x18000625c  call    cs:__imp_GetModuleFileNameW
0x180006262  test    eax, eax
0x180006264  jnz     short loc_18000627C
0x180006266  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000626b  mov     ebx, eax
0x18000626d  lea     rcx, [rsp+0B00h+var_AD0]
0x180006272  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006277  jmp     loc_1800063C1
0x18000627c  cmp     eax, edi
0x18000627e  jnz     short loc_180006294
0x180006280  lea     rcx, [rsp+0B00h+var_AD0]
0x180006285  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000628a  mov     ebx, 8007007Ah
0x18000628f  jmp     loc_1800063C1
0x180006294  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006298  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000629f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800062a4  test    rbx, rbx
0x1800062a7  jz      short loc_1800062BF
0x1800062a9  xor     ecx, ecx; lpModuleName
0x1800062ab  call    cs:__imp_GetModuleHandleW
0x1800062b1  cmp     rbx, rax
0x1800062b4  jz      short loc_1800062BF
0x1800062b6  lea     r8, [rbp+0A00h+var_440]
0x1800062bd  jmp     short loc_18000633A
0x1800062bf  mov     ebx, 22h ; '"'
0x1800062c4  mov     [rbp+0A00h+var_860], bx
0x1800062cb  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800062d2  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x1800062d9  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800062de  test    al, al
0x1800062e0  jnz     short loc_1800062F6
0x1800062e2  lea     rcx, [rsp+0B00h+var_AD0]
0x1800062e7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800062ec  mov     ebx, 80004005h
0x1800062f1  jmp     loc_1800063C1
0x1800062f6  lea     rcx, [rbp+0A00h+var_860]
0x1800062fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006301  inc     rax
0x180006304  cmp     [rcx+rax*2], r15w
0x180006309  jnz     short loc_180006301
0x18000630b  cdqe
0x18000630d  mov     [rbp+rax*2+0A00h+var_860], bx
0x180006315  lea     rcx, ds:2[rax*2]
0x18000631d  cmp     rcx, 418h
0x180006324  jnb     loc_1800063B9
0x18000632a  mov     [rbp+rcx+0A00h+var_860], r15w
0x180006333  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x18000633a  lea     rdx, aModule; "Module"
0x180006341  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180006346  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000634b  mov     ebx, eax
0x18000634d  test    eax, eax
0x18000634f  js      loc_18000626D
0x180006355  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000635c  lea     rdx, aModuleRaw; "Module_Raw"
0x180006363  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180006368  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000636d  mov     ebx, eax
0x18000636f  test    eax, eax
0x180006371  js      loc_18000626D
0x180006377  movzx   r8d, r14w; unsigned __int16 *
0x18000637b  mov     [rsp+0B00h+var_AC8], r15
0x180006380  lea     r9, aRegistry; "REGISTRY"
0x180006387  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000638b  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180006390  test    esi, esi
0x180006392  jz      short loc_18000639E
0x180006394  mov     [rsp+0B00h+var_AE0], 1
0x18000639c  jmp     short loc_1800063A3
0x18000639e  mov     [rsp+0B00h+var_AE0], r15d; int
0x1800063a3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800063a8  mov     ebx, eax
0x1800063aa  lea     rcx, [rsp+0B00h+var_AC8]
0x1800063af  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800063b4  jmp     loc_18000626D
0x1800063b9  call    __report_rangecheckfailure
0x1800063bf  mov     ebx, eax
0x1800063c1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800063c6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800063cb  mov     eax, ebx
0x1800063cd  mov     rcx, [rbp+0A00h+var_30]
0x1800063d4  xor     rcx, rsp; StackCookie
0x1800063d7  call    __security_check_cookie
0x1800063dc  mov     rbx, [rsp+0B00h+arg_10]
0x1800063e4  add     rsp, 0AE0h
0x1800063eb  pop     r15
0x1800063ed  pop     r14
0x1800063ef  pop     rdi
0x1800063f0  pop     rsi
0x1800063f1  pop     rbp
0x1800063f2  retn
```
