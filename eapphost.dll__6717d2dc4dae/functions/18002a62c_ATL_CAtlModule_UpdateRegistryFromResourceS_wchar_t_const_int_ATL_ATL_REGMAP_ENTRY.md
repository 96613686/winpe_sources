# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18002a62c`
- end: `0x18002a8ac`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002a8d0`

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
- `0x18001094c`
- `0x18002a62c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a777`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a777`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002a732`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002a732`

## string_xrefs

- `0x18002a879`: `REGISTRY`

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
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
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
0x18002a62c  push    rbp
0x18002a62e  push    rbx
0x18002a62f  push    rsi
0x18002a630  push    rdi
0x18002a631  push    r12
0x18002a633  push    r14
0x18002a635  push    r15
0x18002a637  lea     rbp, [rsp-9E0h]
0x18002a63f  sub     rsp, 0AE0h
0x18002a646  mov     rax, cs:__security_cookie
0x18002a64d  xor     rax, rsp
0x18002a650  mov     [rbp+0A10h+var_40], rax
0x18002a657  mov     rbx, r9
0x18002a65a  mov     r15d, r8d
0x18002a65d  mov     rdi, rdx
0x18002a660  mov     r14, rcx
0x18002a663  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002a66a  mov     [rsp+0B10h+var_AD0], rax
0x18002a66f  xor     r12d, r12d
0x18002a672  mov     [rsp+0B10h+var_AC8], r12
0x18002a677  mov     [rsp+0B10h+var_AC0], r12
0x18002a67c  mov     [rsp+0B10h+var_AB8], r12d
0x18002a681  xorps   xmm0, xmm0
0x18002a684  xor     eax, eax
0x18002a686  movups  [rsp+0B10h+var_AB0], xmm0
0x18002a68b  movups  [rsp+0B10h+var_AA0], xmm0
0x18002a690  mov     [rbp+0A10h+var_A90], rax
0x18002a694  mov     [rbp+0A10h+var_A88], r12b
0x18002a698  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18002a69d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18002a6a2  mov     esi, eax
0x18002a6a4  test    eax, eax
0x18002a6a6  jns     short loc_18002A6D5
0x18002a6a8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002a6ad  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002a6b2  mov     eax, esi
0x18002a6b4  mov     rcx, [rbp+0A10h+var_40]
0x18002a6bb  xor     rcx, rsp; StackCookie
0x18002a6be  call    __security_check_cookie
0x18002a6c3  add     rsp, 0AE0h
0x18002a6ca  pop     r15
0x18002a6cc  pop     r14
0x18002a6ce  pop     r12
0x18002a6d0  pop     rdi
0x18002a6d1  pop     rsi
0x18002a6d2  pop     rbx
0x18002a6d3  pop     rbp
0x18002a6d4  retn
0x18002a6d5  test    rbx, rbx
0x18002a6d8  jz      short loc_18002A6F9
0x18002a6da  jmp     short loc_18002A6F1
0x18002a6dc  mov     r8, [rbx+8]; wchar_t *
0x18002a6e0  mov     rdx, rax; wchar_t *
0x18002a6e3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002a6e8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18002a6ed  lea     rbx, [rbx+10h]
0x18002a6f1  mov     rax, [rbx]
0x18002a6f4  test    rax, rax
0x18002a6f7  jnz     short loc_18002A6DC
0x18002a6f9  mov     rax, [r14]
0x18002a6fc  lea     rdx, [rsp+0B10h+var_AD0]
0x18002a701  mov     rcx, r14
0x18002a704  mov     rax, [rax+28h]
0x18002a708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a70d  mov     ebx, eax
0x18002a70f  test    eax, eax
0x18002a711  js      loc_18002A845
0x18002a717  mov     [rsp+0B10h+var_AE0], r12
0x18002a71c  mov     rbx, cs:hModule
0x18002a723  mov     esi, 104h
0x18002a728  mov     r8d, esi; nSize
0x18002a72b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18002a72f  mov     rcx, rbx; hModule
0x18002a732  call    cs:__imp_GetModuleFileNameW
0x18002a738  test    eax, eax
0x18002a73a  jnz     short loc_18002A748
0x18002a73c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002a741  mov     ebx, eax
0x18002a743  jmp     loc_18002A83B
0x18002a748  cmp     eax, esi
0x18002a74a  jnz     short loc_18002A760
0x18002a74c  lea     rcx, [rsp+0B10h+var_AE0]
0x18002a751  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002a756  mov     ebx, 8007007Ah
0x18002a75b  jmp     loc_18002A845
0x18002a760  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18002a764  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18002a76b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a770  test    rbx, rbx
0x18002a773  jz      short loc_18002A78B
0x18002a775  xor     ecx, ecx; lpModuleName
0x18002a777  call    cs:__imp_GetModuleHandleW
0x18002a77d  cmp     rbx, rax
0x18002a780  jz      short loc_18002A78B
0x18002a782  lea     r8, [rbp+0A10h+var_450]
0x18002a789  jmp     short loc_18002A806
0x18002a78b  mov     ebx, 22h ; '"'
0x18002a790  mov     [rbp+0A10h+var_870], bx
0x18002a797  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18002a79e  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18002a7a5  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a7aa  test    al, al
0x18002a7ac  jnz     short loc_18002A7C2
0x18002a7ae  lea     rcx, [rsp+0B10h+var_AE0]
0x18002a7b3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002a7b8  mov     ebx, 80004005h
0x18002a7bd  jmp     loc_18002A845
0x18002a7c2  lea     rcx, [rbp+0A10h+var_870]
0x18002a7c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a7cd  inc     rax
0x18002a7d0  cmp     [rcx+rax*2], r12w
0x18002a7d5  jnz     short loc_18002A7CD
0x18002a7d7  cdqe
0x18002a7d9  mov     [rbp+rax*2+0A10h+var_870], bx
0x18002a7e1  lea     rcx, ds:2[rax*2]
0x18002a7e9  cmp     rcx, 418h
0x18002a7f0  jnb     loc_18002A8A6
0x18002a7f6  mov     [rbp+rcx+0A10h+var_870], r12w
0x18002a7ff  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18002a806  lea     rdx, aModule_0; "Module"
0x18002a80d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002a812  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18002a817  mov     ebx, eax
0x18002a819  test    eax, eax
0x18002a81b  js      short loc_18002A83B
0x18002a81d  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18002a824  lea     rdx, aModuleRaw; "Module_Raw"
0x18002a82b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002a830  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18002a835  mov     ebx, eax
0x18002a837  test    eax, eax
0x18002a839  jns     short loc_18002A856
0x18002a83b  lea     rcx, [rsp+0B10h+var_AE0]
0x18002a840  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002a845  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002a84a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002a84f  mov     eax, ebx
0x18002a851  jmp     loc_18002A6B4
0x18002a856  mov     [rsp+0B10h+var_AD8], r12
0x18002a85b  test    r15d, r15d
0x18002a85e  jz      short loc_18002A86F
0x18002a860  test    rdi, rdi
0x18002a863  jz      short loc_18002A895
0x18002a865  mov     [rsp+0B10h+var_AF0], 1
0x18002a86d  jmp     short loc_18002A879
0x18002a86f  test    rdi, rdi
0x18002a872  jz      short loc_18002A895
0x18002a874  mov     [rsp+0B10h+var_AF0], r12d; int
0x18002a879  lea     r9, aRegistry; "REGISTRY"
0x18002a880  mov     r8, rdi; wchar_t *
0x18002a883  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18002a887  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002a88c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18002a891  mov     ebx, eax
0x18002a893  jmp     short loc_18002A89A
0x18002a895  mov     ebx, 80070057h
0x18002a89a  lea     rcx, [rsp+0B10h+var_AD8]
0x18002a89f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002a8a4  jmp     short loc_18002A83B
0x18002a8a6  call    __report_rangecheckfailure
```
