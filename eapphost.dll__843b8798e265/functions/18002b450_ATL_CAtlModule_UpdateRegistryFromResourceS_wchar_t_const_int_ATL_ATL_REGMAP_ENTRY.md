# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18002b450`
- end: `0x18002b6dd`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `653`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b700`

## callees

- `0x180002af0`
- `0x180002f10`
- `0x18000bc68`
- `0x18000ea04`
- `0x18000eaa4`
- `0x18000ee10`
- `0x18000f5a4`
- `0x18000f9c0`
- `0x1800103cc`
- `0x1800110b4`
- `0x18002b450`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b5a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b5a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002b557`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002b557`

## string_xrefs

- `0x18002b6aa`: `REGISTRY`

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
0x18002b450  push    rbp
0x18002b452  push    rbx
0x18002b453  push    rsi
0x18002b454  push    rdi
0x18002b455  push    r12
0x18002b457  push    r14
0x18002b459  push    r15
0x18002b45b  lea     rbp, [rsp-9E0h]
0x18002b463  sub     rsp, 0AE0h
0x18002b46a  mov     rax, cs:__security_cookie
0x18002b471  xor     rax, rsp
0x18002b474  mov     [rbp+0A10h+var_40], rax
0x18002b47b  mov     rbx, r9
0x18002b47e  mov     r15d, r8d
0x18002b481  mov     rdi, rdx
0x18002b484  mov     r14, rcx
0x18002b487  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002b48e  mov     [rsp+0B10h+var_AD0], rax
0x18002b493  xor     r12d, r12d
0x18002b496  mov     [rsp+0B10h+var_AC8], r12
0x18002b49b  mov     [rsp+0B10h+var_AC0], r12
0x18002b4a0  mov     [rsp+0B10h+var_AB8], r12d
0x18002b4a5  xorps   xmm0, xmm0
0x18002b4a8  xor     eax, eax
0x18002b4aa  movups  [rsp+0B10h+var_AB0], xmm0
0x18002b4af  movups  [rsp+0B10h+var_AA0], xmm0
0x18002b4b4  mov     [rbp+0A10h+var_A90], rax
0x18002b4b8  mov     [rbp+0A10h+var_A88], r12b
0x18002b4bc  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18002b4c1  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18002b4c6  mov     esi, eax
0x18002b4c8  test    eax, eax
0x18002b4ca  jns     short loc_18002B4FA
0x18002b4cc  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002b4d1  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002b4d6  mov     eax, esi
0x18002b4d8  mov     rcx, [rbp+0A10h+var_40]
0x18002b4df  xor     rcx, rsp; StackCookie
0x18002b4e2  call    __security_check_cookie
0x18002b4e7  add     rsp, 0AE0h
0x18002b4ee  pop     r15
0x18002b4f0  pop     r14
0x18002b4f2  pop     r12
0x18002b4f4  pop     rdi
0x18002b4f5  pop     rsi
0x18002b4f6  pop     rbx
0x18002b4f7  pop     rbp
0x18002b4f8  retn
0x18002b4fa  test    rbx, rbx
0x18002b4fd  jz      short loc_18002B51E
0x18002b4ff  jmp     short loc_18002B516
0x18002b501  mov     r8, [rbx+8]; wchar_t *
0x18002b505  mov     rdx, rax; wchar_t *
0x18002b508  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002b50d  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18002b512  lea     rbx, [rbx+10h]
0x18002b516  mov     rax, [rbx]
0x18002b519  test    rax, rax
0x18002b51c  jnz     short loc_18002B501
0x18002b51e  mov     rax, [r14]
0x18002b521  lea     rdx, [rsp+0B10h+var_AD0]
0x18002b526  mov     rcx, r14
0x18002b529  mov     rax, [rax+28h]
0x18002b52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b532  mov     ebx, eax
0x18002b534  test    eax, eax
0x18002b536  js      loc_18002B676
0x18002b53c  mov     [rsp+0B10h+var_AE0], r12
0x18002b541  mov     rbx, cs:hModule
0x18002b548  mov     esi, 104h
0x18002b54d  mov     r8d, esi; nSize
0x18002b550  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18002b554  mov     rcx, rbx; hModule
0x18002b557  call    cs:__imp_GetModuleFileNameW
0x18002b55e  nop     dword ptr [rax+rax+00h]
0x18002b563  test    eax, eax
0x18002b565  jnz     short loc_18002B573
0x18002b567  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002b56c  mov     ebx, eax
0x18002b56e  jmp     loc_18002B66C
0x18002b573  cmp     eax, esi
0x18002b575  jnz     short loc_18002B58B
0x18002b577  lea     rcx, [rsp+0B10h+var_AE0]
0x18002b57c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002b581  mov     ebx, 8007007Ah
0x18002b586  jmp     loc_18002B676
0x18002b58b  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18002b58f  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18002b596  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x18002b59b  test    rbx, rbx
0x18002b59e  jz      short loc_18002B5BC
0x18002b5a0  xor     ecx, ecx; lpModuleName
0x18002b5a2  call    cs:__imp_GetModuleHandleW
0x18002b5a9  nop     dword ptr [rax+rax+00h]
0x18002b5ae  cmp     rbx, rax
0x18002b5b1  jz      short loc_18002B5BC
0x18002b5b3  lea     r8, [rbp+0A10h+var_450]
0x18002b5ba  jmp     short loc_18002B637
0x18002b5bc  mov     ebx, 22h ; '"'
0x18002b5c1  mov     [rbp+0A10h+var_870], bx
0x18002b5c8  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18002b5cf  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18002b5d6  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x18002b5db  test    al, al
0x18002b5dd  jnz     short loc_18002B5F3
0x18002b5df  lea     rcx, [rsp+0B10h+var_AE0]
0x18002b5e4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002b5e9  mov     ebx, 80004005h
0x18002b5ee  jmp     loc_18002B676
0x18002b5f3  lea     rcx, [rbp+0A10h+var_870]
0x18002b5fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b5fe  inc     rax
0x18002b601  cmp     [rcx+rax*2], r12w
0x18002b606  jnz     short loc_18002B5FE
0x18002b608  cdqe
0x18002b60a  mov     [rbp+rax*2+0A10h+var_870], bx
0x18002b612  lea     rcx, ds:2[rax*2]
0x18002b61a  cmp     rcx, 418h
0x18002b621  jnb     loc_18002B6D7
0x18002b627  mov     [rbp+rcx+0A10h+var_870], r12w
0x18002b630  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18002b637  lea     rdx, aModule_0; "Module"
0x18002b63e  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002b643  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18002b648  mov     ebx, eax
0x18002b64a  test    eax, eax
0x18002b64c  js      short loc_18002B66C
0x18002b64e  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18002b655  lea     rdx, aModuleRaw; "Module_Raw"
0x18002b65c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002b661  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18002b666  mov     ebx, eax
0x18002b668  test    eax, eax
0x18002b66a  jns     short loc_18002B687
0x18002b66c  lea     rcx, [rsp+0B10h+var_AE0]
0x18002b671  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002b676  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002b67b  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002b680  mov     eax, ebx
0x18002b682  jmp     loc_18002B4D8
0x18002b687  mov     [rsp+0B10h+var_AD8], r12
0x18002b68c  test    r15d, r15d
0x18002b68f  jz      short loc_18002B6A0
0x18002b691  test    rdi, rdi
0x18002b694  jz      short loc_18002B6C6
0x18002b696  mov     [rsp+0B10h+var_AF0], 1
0x18002b69e  jmp     short loc_18002B6AA
0x18002b6a0  test    rdi, rdi
0x18002b6a3  jz      short loc_18002B6C6
0x18002b6a5  mov     [rsp+0B10h+var_AF0], r12d; int
0x18002b6aa  lea     r9, aRegistry; "REGISTRY"
0x18002b6b1  mov     r8, rdi; wchar_t *
0x18002b6b4  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18002b6b8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18002b6bd  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18002b6c2  mov     ebx, eax
0x18002b6c4  jmp     short loc_18002B6CB
0x18002b6c6  mov     ebx, 80070057h
0x18002b6cb  lea     rcx, [rsp+0B10h+var_AD8]
0x18002b6d0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002b6d5  jmp     short loc_18002B66C
0x18002b6d7  call    __report_rangecheckfailure
```
