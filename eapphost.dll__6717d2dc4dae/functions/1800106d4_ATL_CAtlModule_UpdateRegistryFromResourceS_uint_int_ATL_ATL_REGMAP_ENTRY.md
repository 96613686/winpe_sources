# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800106d4`
- end: `0x180010944`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f200`
- `0x18000f29c`
- `0x18002a8c0`

## callees

- `0x180002a90`
- `0x180002eb0`
- `0x18000b770`
- `0x18000e43c`
- `0x18000e4d0`
- `0x18000e820`
- `0x18000f040`
- `0x18000f398`
- `0x18000fcf0`
- `0x1800106d4`
- `0x18001094c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001081f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001081f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800107da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800107da`

## string_xrefs

- `0x180010907`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  wchar_t *v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wchar_t v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v23);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, *(const wchar_t **)a4, *((const wchar_t **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW != 260 )
    {
      ATL::CAtlModule::EscapeSingleQuote(v29, v13, Filename);
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v27 = 34;
        if ( !ocscpy_s(v28, v14, v29) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_24;
        }
        v16 = -1;
        do
          ++v16;
        while ( v28[v16 - 1] );
        v28[(int)v16 - 1] = 34;
        v17 = 2LL * (int)v16 + 2;
        if ( v17 >= 0x418 )
          _report_rangecheckfailure();
        *(wchar_t *)((char *)&v28[-1] + v17) = 0;
        v15 = &v27;
      }
      else
      {
        v15 = v29;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const wchar_t *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const wchar_t *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800106d4  push    rbp
0x1800106d6  push    rbx
0x1800106d7  push    rsi
0x1800106d8  push    rdi
0x1800106d9  push    r12
0x1800106db  push    r14
0x1800106dd  push    r15
0x1800106df  lea     rbp, [rsp-9E0h]
0x1800106e7  sub     rsp, 0AE0h
0x1800106ee  mov     rax, cs:__security_cookie
0x1800106f5  xor     rax, rsp
0x1800106f8  mov     [rbp+0A10h+var_40], rax
0x1800106ff  mov     rbx, r9
0x180010702  mov     r14d, r8d
0x180010705  mov     r15d, edx
0x180010708  mov     rsi, rcx
0x18001070b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180010712  mov     [rsp+0B10h+var_AD0], rax
0x180010717  xor     r12d, r12d
0x18001071a  mov     [rsp+0B10h+var_AC8], r12
0x18001071f  mov     [rsp+0B10h+var_AC0], r12
0x180010724  mov     [rsp+0B10h+var_AB8], r12d
0x180010729  xorps   xmm0, xmm0
0x18001072c  xor     eax, eax
0x18001072e  movups  [rsp+0B10h+var_AB0], xmm0
0x180010733  movups  [rsp+0B10h+var_AA0], xmm0
0x180010738  mov     [rbp+0A10h+var_A90], rax
0x18001073c  mov     [rbp+0A10h+var_A88], r12b
0x180010740  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180010745  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001074a  mov     edi, eax
0x18001074c  test    eax, eax
0x18001074e  jns     short loc_18001077D
0x180010750  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010755  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001075a  mov     eax, edi
0x18001075c  mov     rcx, [rbp+0A10h+var_40]
0x180010763  xor     rcx, rsp; StackCookie
0x180010766  call    __security_check_cookie
0x18001076b  add     rsp, 0AE0h
0x180010772  pop     r15
0x180010774  pop     r14
0x180010776  pop     r12
0x180010778  pop     rdi
0x180010779  pop     rsi
0x18001077a  pop     rbx
0x18001077b  pop     rbp
0x18001077c  retn
0x18001077d  test    rbx, rbx
0x180010780  jz      short loc_1800107A1
0x180010782  jmp     short loc_180010799
0x180010784  mov     r8, [rbx+8]; wchar_t *
0x180010788  mov     rdx, rax; wchar_t *
0x18001078b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010790  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180010795  lea     rbx, [rbx+10h]
0x180010799  mov     rax, [rbx]
0x18001079c  test    rax, rax
0x18001079f  jnz     short loc_180010784
0x1800107a1  mov     rax, [rsi]
0x1800107a4  lea     rdx, [rsp+0B10h+var_AD0]
0x1800107a9  mov     rcx, rsi
0x1800107ac  mov     rax, [rax+28h]
0x1800107b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107b5  mov     ebx, eax
0x1800107b7  test    eax, eax
0x1800107b9  js      loc_1800108ED
0x1800107bf  mov     [rsp+0B10h+var_AE0], r12
0x1800107c4  mov     rbx, cs:hModule
0x1800107cb  mov     edi, 104h
0x1800107d0  mov     r8d, edi; nSize
0x1800107d3  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800107d7  mov     rcx, rbx; hModule
0x1800107da  call    cs:__imp_GetModuleFileNameW
0x1800107e0  test    eax, eax
0x1800107e2  jnz     short loc_1800107F0
0x1800107e4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800107e9  mov     ebx, eax
0x1800107eb  jmp     loc_1800108E3
0x1800107f0  cmp     eax, edi
0x1800107f2  jnz     short loc_180010808
0x1800107f4  lea     rcx, [rsp+0B10h+var_AE0]
0x1800107f9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800107fe  mov     ebx, 8007007Ah
0x180010803  jmp     loc_1800108ED
0x180010808  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18001080c  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x180010813  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x180010818  test    rbx, rbx
0x18001081b  jz      short loc_180010833
0x18001081d  xor     ecx, ecx; lpModuleName
0x18001081f  call    cs:__imp_GetModuleHandleW
0x180010825  cmp     rbx, rax
0x180010828  jz      short loc_180010833
0x18001082a  lea     r8, [rbp+0A10h+var_450]
0x180010831  jmp     short loc_1800108AE
0x180010833  mov     ebx, 22h ; '"'
0x180010838  mov     [rbp+0A10h+var_870], bx
0x18001083f  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x180010846  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18001084d  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x180010852  test    al, al
0x180010854  jnz     short loc_18001086A
0x180010856  lea     rcx, [rsp+0B10h+var_AE0]
0x18001085b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010860  mov     ebx, 80004005h
0x180010865  jmp     loc_1800108ED
0x18001086a  lea     rcx, [rbp+0A10h+var_870]
0x180010871  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010875  inc     rax
0x180010878  cmp     [rcx+rax*2], r12w
0x18001087d  jnz     short loc_180010875
0x18001087f  cdqe
0x180010881  mov     [rbp+rax*2+0A10h+var_870], bx
0x180010889  lea     rcx, ds:2[rax*2]
0x180010891  cmp     rcx, 418h
0x180010898  jnb     loc_18001093E
0x18001089e  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800108a7  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x1800108ae  lea     rdx, aModule_0; "Module"
0x1800108b5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800108ba  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x1800108bf  mov     ebx, eax
0x1800108c1  test    eax, eax
0x1800108c3  js      short loc_1800108E3
0x1800108c5  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x1800108cc  lea     rdx, aModuleRaw; "Module_Raw"
0x1800108d3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800108d8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x1800108dd  mov     ebx, eax
0x1800108df  test    eax, eax
0x1800108e1  jns     short loc_1800108FE
0x1800108e3  lea     rcx, [rsp+0B10h+var_AE0]
0x1800108e8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800108ed  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800108f2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800108f7  mov     eax, ebx
0x1800108f9  jmp     loc_18001075C
0x1800108fe  movzx   r8d, r15w; wchar_t *
0x180010902  mov     [rsp+0B10h+var_AD8], r12
0x180010907  lea     r9, aRegistry; "REGISTRY"
0x18001090e  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x180010912  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010917  test    r14d, r14d
0x18001091a  jz      short loc_180010926
0x18001091c  mov     [rsp+0B10h+var_AF0], 1
0x180010924  jmp     short loc_18001092B
0x180010926  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001092b  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180010930  mov     ebx, eax
0x180010932  lea     rcx, [rsp+0B10h+var_AD8]
0x180010937  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001093c  jmp     short loc_1800108E3
0x18001093e  call    __report_rangecheckfailure
```
