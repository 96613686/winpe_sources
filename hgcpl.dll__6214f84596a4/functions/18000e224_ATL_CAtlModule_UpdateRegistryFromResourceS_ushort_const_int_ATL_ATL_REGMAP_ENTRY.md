# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000e224`
- end: `0x18000e484`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `608`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e4a0`

## callees

- `0x180002c28`
- `0x18000bc5c`
- `0x18000bc94`
- `0x18000bd50`
- `0x18000c050`
- `0x18000c7d8`
- `0x18000cbf4`
- `0x18000ceac`
- `0x18000d5d0`
- `0x18000e224`
- `0x18000e4ac`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e32b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e32b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000e2dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000e2dc`

## string_xrefs

- `0x18000e41a`: `REGISTRY`

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
  _BYTE v21[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[48]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v25[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v26[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  ATL::CRegObject::CRegObject((ATL::CRegObject *)v21);
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v22);
  if ( v8 < 0 )
  {
    Error = v8;
    goto LABEL_33;
  }
  v22[40] = 1;
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
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _BYTE *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v10 = hModule;
    v19 = 0;
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
    ATL::CAtlModule::EscapeSingleQuote(v26, v12, Filename);
    if ( !v10 || v10 == GetModuleHandleW(0) )
    {
      v24 = 34;
      if ( !ocscpy_s(v25, v13, v26) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_33;
      }
      v15 = -1;
      do
        ++v15;
      while ( v25[v15 - 1] );
      v16 = 2LL * (int)v15 + 2;
      v25[(int)v15 - 1] = 34;
      if ( v16 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v25[-1] + v16) = 0;
      v14 = &v24;
    }
    else
    {
      v14 = v26;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v14);
    if ( Error < 0 )
      goto LABEL_9;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v26);
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
0x18000e224  mov     [rsp-8+arg_10], rbx
0x18000e229  push    rbp
0x18000e22a  push    rsi
0x18000e22b  push    rdi
0x18000e22c  push    r14
0x18000e22e  push    r15
0x18000e230  lea     rbp, [rsp-9E0h]
0x18000e238  sub     rsp, 0AE0h
0x18000e23f  mov     rax, cs:__security_cookie
0x18000e246  xor     rax, rsp
0x18000e249  mov     [rbp+0A00h+var_30], rax
0x18000e250  mov     rsi, rcx
0x18000e253  mov     rbx, r9
0x18000e256  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e25b  mov     r14d, r8d
0x18000e25e  mov     rdi, rdx
0x18000e261  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x18000e266  lea     rcx, [rsp+0B00h+var_AA0]; this
0x18000e26b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000e270  xor     r15d, r15d
0x18000e273  test    eax, eax
0x18000e275  js      loc_18000E450
0x18000e27b  mov     [rbp+0A00h+var_A78], 1
0x18000e27f  test    rbx, rbx
0x18000e282  jz      short loc_18000E2A3
0x18000e284  jmp     short loc_18000E29B
0x18000e286  mov     r8, [rbx+8]; unsigned __int16 *
0x18000e28a  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e28f  mov     rdx, rax; unsigned __int16 *
0x18000e292  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000e297  lea     rbx, [rbx+10h]
0x18000e29b  mov     rax, [rbx]
0x18000e29e  test    rax, rax
0x18000e2a1  jnz     short loc_18000E286
0x18000e2a3  mov     rax, [rsi]
0x18000e2a6  lea     rdx, [rsp+0B00h+var_AC0]
0x18000e2ab  mov     rcx, rsi
0x18000e2ae  mov     rax, [rax+28h]
0x18000e2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2b7  mov     ebx, eax
0x18000e2b9  test    eax, eax
0x18000e2bb  js      loc_18000E452
0x18000e2c1  mov     rbx, cs:hModule
0x18000e2c8  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000e2cc  mov     esi, 104h
0x18000e2d1  mov     [rsp+0B00h+var_AD0], r15
0x18000e2d6  mov     r8d, esi; nSize
0x18000e2d9  mov     rcx, rbx; hModule
0x18000e2dc  call    cs:__imp_GetModuleFileNameW
0x18000e2e2  test    eax, eax
0x18000e2e4  jnz     short loc_18000E2FC
0x18000e2e6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000e2eb  mov     ebx, eax
0x18000e2ed  lea     rcx, [rsp+0B00h+var_AD0]
0x18000e2f2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e2f7  jmp     loc_18000E452
0x18000e2fc  cmp     eax, esi
0x18000e2fe  jnz     short loc_18000E314
0x18000e300  lea     rcx, [rsp+0B00h+var_AD0]
0x18000e305  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e30a  mov     ebx, 8007007Ah
0x18000e30f  jmp     loc_18000E452
0x18000e314  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000e318  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000e31f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000e324  test    rbx, rbx
0x18000e327  jz      short loc_18000E33F
0x18000e329  xor     ecx, ecx; lpModuleName
0x18000e32b  call    cs:__imp_GetModuleHandleW
0x18000e331  cmp     rbx, rax
0x18000e334  jz      short loc_18000E33F
0x18000e336  lea     r8, [rbp+0A00h+var_440]
0x18000e33d  jmp     short loc_18000E3BA
0x18000e33f  mov     ebx, 22h ; '"'
0x18000e344  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000e34b  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x18000e352  mov     [rbp+0A00h+var_860], bx
0x18000e359  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000e35e  test    al, al
0x18000e360  jnz     short loc_18000E376
0x18000e362  lea     rcx, [rsp+0B00h+var_AD0]
0x18000e367  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e36c  mov     ebx, 80004005h
0x18000e371  jmp     loc_18000E452
0x18000e376  lea     rcx, [rbp+0A00h+var_860]
0x18000e37d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e381  inc     rax
0x18000e384  cmp     [rcx+rax*2], r15w
0x18000e389  jnz     short loc_18000E381
0x18000e38b  cdqe
0x18000e38d  lea     rcx, ds:2[rax*2]
0x18000e395  mov     [rbp+rax*2+0A00h+var_860], bx
0x18000e39d  cmp     rcx, 418h
0x18000e3a4  jnb     loc_18000E44A
0x18000e3aa  mov     [rbp+rcx+0A00h+var_860], r15w
0x18000e3b3  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x18000e3ba  lea     rdx, aModule; "Module"
0x18000e3c1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e3c6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000e3cb  mov     ebx, eax
0x18000e3cd  test    eax, eax
0x18000e3cf  js      loc_18000E2ED
0x18000e3d5  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000e3dc  lea     rdx, aModuleRaw; "Module_Raw"
0x18000e3e3  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e3e8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000e3ed  mov     ebx, eax
0x18000e3ef  test    eax, eax
0x18000e3f1  js      loc_18000E2ED
0x18000e3f7  mov     [rsp+0B00h+var_AC8], r15
0x18000e3fc  test    r14d, r14d
0x18000e3ff  jz      short loc_18000E410
0x18000e401  test    rdi, rdi
0x18000e404  jz      short loc_18000E436
0x18000e406  mov     [rsp+0B00h+var_AE0], 1
0x18000e40e  jmp     short loc_18000E41A
0x18000e410  test    rdi, rdi
0x18000e413  jz      short loc_18000E436
0x18000e415  mov     [rsp+0B00h+var_AE0], r15d; int
0x18000e41a  lea     r9, aRegistry; "REGISTRY"
0x18000e421  mov     r8, rdi; unsigned __int16 *
0x18000e424  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000e428  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e42d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000e432  mov     ebx, eax
0x18000e434  jmp     short loc_18000E43B
0x18000e436  mov     ebx, 80070057h
0x18000e43b  lea     rcx, [rsp+0B00h+var_AC8]
0x18000e440  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e445  jmp     loc_18000E2ED
0x18000e44a  call    __report_rangecheckfailure
0x18000e450  mov     ebx, eax
0x18000e452  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e457  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000e45c  mov     eax, ebx
0x18000e45e  mov     rcx, [rbp+0A00h+var_30]
0x18000e465  xor     rcx, rsp; StackCookie
0x18000e468  call    __security_check_cookie
0x18000e46d  mov     rbx, [rsp+0B00h+arg_10]
0x18000e475  add     rsp, 0AE0h
0x18000e47c  pop     r15
0x18000e47e  pop     r14
0x18000e480  pop     rdi
0x18000e481  pop     rsi
0x18000e482  pop     rbp
0x18000e483  retn
```
