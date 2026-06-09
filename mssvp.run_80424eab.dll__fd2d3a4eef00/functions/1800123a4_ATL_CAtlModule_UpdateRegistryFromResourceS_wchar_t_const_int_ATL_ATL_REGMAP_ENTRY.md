# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800123a4`
- end: `0x180012624`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012640`

## callees

- `0x180004820`
- `0x18000557c`
- `0x180006270`
- `0x1800066a0`
- `0x180009eb8`
- `0x18000a69c`
- `0x18000b630`
- `0x18000d708`
- `0x1800103dc`
- `0x1800123a4`
- `0x180012eac`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800124ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800124ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800124aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800124aa`

## string_xrefs

- `0x1800125f1`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const wchar_t *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
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
    v11 = off_180053498;
    ModuleFileNameW = GetModuleFileNameW(off_180053498, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ResultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_24;
    }
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
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
    if ( Error < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        Error = v18;
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_23;
      }
    }
    else if ( a2 )
    {
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_30;
    }
    Error = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800123a4  push    rbp
0x1800123a6  push    rbx
0x1800123a7  push    rsi
0x1800123a8  push    rdi
0x1800123a9  push    r12
0x1800123ab  push    r14
0x1800123ad  push    r15
0x1800123af  lea     rbp, [rsp-9E0h]
0x1800123b7  sub     rsp, 0AE0h
0x1800123be  mov     rax, cs:__security_cookie
0x1800123c5  xor     rax, rsp
0x1800123c8  mov     [rbp+0A10h+var_40], rax
0x1800123cf  mov     rbx, r9
0x1800123d2  mov     r15d, r8d
0x1800123d5  mov     rdi, rdx
0x1800123d8  mov     r14, rcx
0x1800123db  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800123e2  mov     [rsp+0B10h+var_AD0], rax
0x1800123e7  xor     r12d, r12d
0x1800123ea  mov     [rsp+0B10h+var_AC8], r12
0x1800123ef  mov     [rsp+0B10h+var_AC0], r12
0x1800123f4  mov     [rsp+0B10h+var_AB8], r12d
0x1800123f9  xorps   xmm0, xmm0
0x1800123fc  xor     eax, eax
0x1800123fe  movups  [rsp+0B10h+var_AB0], xmm0
0x180012403  movups  [rsp+0B10h+var_AA0], xmm0
0x180012408  mov     [rbp+0A10h+var_A90], rax
0x18001240c  mov     [rbp+0A10h+var_A88], r12b
0x180012410  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180012415  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001241a  mov     esi, eax
0x18001241c  test    eax, eax
0x18001241e  jns     short loc_18001244D
0x180012420  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012425  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001242a  mov     eax, esi
0x18001242c  mov     rcx, [rbp+0A10h+var_40]
0x180012433  xor     rcx, rsp; StackCookie
0x180012436  call    __security_check_cookie
0x18001243b  add     rsp, 0AE0h
0x180012442  pop     r15
0x180012444  pop     r14
0x180012446  pop     r12
0x180012448  pop     rdi
0x180012449  pop     rsi
0x18001244a  pop     rbx
0x18001244b  pop     rbp
0x18001244c  retn
0x18001244d  test    rbx, rbx
0x180012450  jz      short loc_180012471
0x180012452  jmp     short loc_180012469
0x180012454  mov     r8, [rbx+8]; wchar_t *
0x180012458  mov     rdx, rax; wchar_t *
0x18001245b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012460  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180012465  lea     rbx, [rbx+10h]
0x180012469  mov     rax, [rbx]
0x18001246c  test    rax, rax
0x18001246f  jnz     short loc_180012454
0x180012471  mov     rax, [r14]
0x180012474  lea     rdx, [rsp+0B10h+var_AD0]
0x180012479  mov     rcx, r14
0x18001247c  mov     rax, [rax+28h]
0x180012480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012485  mov     ebx, eax
0x180012487  test    eax, eax
0x180012489  js      loc_1800125BD
0x18001248f  mov     [rsp+0B10h+var_AE0], r12
0x180012494  mov     rbx, cs:off_180053498
0x18001249b  mov     esi, 104h
0x1800124a0  mov     r8d, esi; nSize
0x1800124a3  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800124a7  mov     rcx, rbx; hModule
0x1800124aa  call    cs:__imp_GetModuleFileNameW
0x1800124b0  test    eax, eax
0x1800124b2  jnz     short loc_1800124C0
0x1800124b4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800124b9  mov     ebx, eax
0x1800124bb  jmp     loc_1800125B3
0x1800124c0  cmp     eax, esi
0x1800124c2  jnz     short loc_1800124D8
0x1800124c4  lea     rcx, [rsp+0B10h+var_AE0]
0x1800124c9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800124ce  mov     ebx, 8007007Ah
0x1800124d3  jmp     loc_1800125BD
0x1800124d8  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x1800124dc  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x1800124e3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x1800124e8  test    rbx, rbx
0x1800124eb  jz      short loc_180012503
0x1800124ed  xor     ecx, ecx; lpModuleName
0x1800124ef  call    cs:__imp_GetModuleHandleW
0x1800124f5  cmp     rbx, rax
0x1800124f8  jz      short loc_180012503
0x1800124fa  lea     r8, [rbp+0A10h+var_450]
0x180012501  jmp     short loc_18001257E
0x180012503  mov     ebx, 22h ; '"'
0x180012508  mov     [rbp+0A10h+var_870], bx
0x18001250f  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x180012516  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18001251d  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x180012522  test    al, al
0x180012524  jnz     short loc_18001253A
0x180012526  lea     rcx, [rsp+0B10h+var_AE0]
0x18001252b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012530  mov     ebx, 80004005h
0x180012535  jmp     loc_1800125BD
0x18001253a  lea     rcx, [rbp+0A10h+var_870]
0x180012541  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012545  inc     rax
0x180012548  cmp     [rcx+rax*2], r12w
0x18001254d  jnz     short loc_180012545
0x18001254f  cdqe
0x180012551  mov     [rbp+rax*2+0A10h+var_870], bx
0x180012559  lea     rcx, ds:2[rax*2]
0x180012561  cmp     rcx, 418h
0x180012568  jnb     loc_18001261E
0x18001256e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180012577  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18001257e  lea     rdx, aModule; "Module"
0x180012585  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001258a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001258f  mov     ebx, eax
0x180012591  test    eax, eax
0x180012593  js      short loc_1800125B3
0x180012595  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18001259c  lea     rdx, aModuleRaw; "Module_Raw"
0x1800125a3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800125a8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x1800125ad  mov     ebx, eax
0x1800125af  test    eax, eax
0x1800125b1  jns     short loc_1800125CE
0x1800125b3  lea     rcx, [rsp+0B10h+var_AE0]
0x1800125b8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800125bd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800125c2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800125c7  mov     eax, ebx
0x1800125c9  jmp     loc_18001242C
0x1800125ce  mov     [rsp+0B10h+var_AD8], r12
0x1800125d3  test    r15d, r15d
0x1800125d6  jz      short loc_1800125E7
0x1800125d8  test    rdi, rdi
0x1800125db  jz      short loc_18001260D
0x1800125dd  mov     [rsp+0B10h+var_AF0], 1
0x1800125e5  jmp     short loc_1800125F1
0x1800125e7  test    rdi, rdi
0x1800125ea  jz      short loc_18001260D
0x1800125ec  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800125f1  lea     r9, aRegistry; "REGISTRY"
0x1800125f8  mov     r8, rdi; wchar_t *
0x1800125fb  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x1800125ff  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012604  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180012609  mov     ebx, eax
0x18001260b  jmp     short loc_180012612
0x18001260d  mov     ebx, 80070057h
0x180012612  lea     rcx, [rsp+0B10h+var_AD8]
0x180012617  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001261c  jmp     short loc_1800125B3
0x18001261e  call    __report_rangecheckfailure
```
