# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001be34`
- end: `0x18001c0b4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c0d0`

## callees

- `0x180005eb0`
- `0x18000a630`
- `0x18000fcd0`
- `0x180010210`
- `0x180016634`
- `0x180016808`
- `0x180016d80`
- `0x180017eec`
- `0x18001a58c`
- `0x18001be34`
- `0x18001c8b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bf3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bf3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bf7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bf7f`

## string_xrefs

- `0x18001c081`: `REGISTRY`

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
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
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
0x18001be34  push    rbp
0x18001be36  push    rbx
0x18001be37  push    rsi
0x18001be38  push    rdi
0x18001be39  push    r12
0x18001be3b  push    r14
0x18001be3d  push    r15
0x18001be3f  lea     rbp, [rsp-9E0h]
0x18001be47  sub     rsp, 0AE0h
0x18001be4e  mov     rax, cs:__security_cookie
0x18001be55  xor     rax, rsp
0x18001be58  mov     [rbp+0A10h+var_40], rax
0x18001be5f  mov     rbx, r9
0x18001be62  mov     r15d, r8d
0x18001be65  mov     rdi, rdx
0x18001be68  mov     r14, rcx
0x18001be6b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001be72  mov     [rsp+0B10h+var_AD0], rax
0x18001be77  xor     r12d, r12d
0x18001be7a  mov     [rsp+0B10h+var_AC8], r12
0x18001be7f  mov     [rsp+0B10h+var_AC0], r12
0x18001be84  mov     [rsp+0B10h+var_AB8], r12d
0x18001be89  xorps   xmm0, xmm0
0x18001be8c  xor     eax, eax
0x18001be8e  movups  [rsp+0B10h+var_AB0], xmm0
0x18001be93  movups  [rsp+0B10h+var_AA0], xmm0
0x18001be98  mov     [rbp+0A10h+var_A90], rax
0x18001be9c  mov     [rbp+0A10h+var_A88], r12b
0x18001bea0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001bea5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001beaa  mov     esi, eax
0x18001beac  test    eax, eax
0x18001beae  jns     short loc_18001BEDD
0x18001beb0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001beb5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001beba  mov     eax, esi
0x18001bebc  mov     rcx, [rbp+0A10h+var_40]
0x18001bec3  xor     rcx, rsp; StackCookie
0x18001bec6  call    __security_check_cookie
0x18001becb  add     rsp, 0AE0h
0x18001bed2  pop     r15
0x18001bed4  pop     r14
0x18001bed6  pop     r12
0x18001bed8  pop     rdi
0x18001bed9  pop     rsi
0x18001beda  pop     rbx
0x18001bedb  pop     rbp
0x18001bedc  retn
0x18001bedd  test    rbx, rbx
0x18001bee0  jz      short loc_18001BF01
0x18001bee2  jmp     short loc_18001BEF9
0x18001bee4  mov     r8, [rbx+8]; wchar_t *
0x18001bee8  mov     rdx, rax; wchar_t *
0x18001beeb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bef0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001bef5  lea     rbx, [rbx+10h]
0x18001bef9  mov     rax, [rbx]
0x18001befc  test    rax, rax
0x18001beff  jnz     short loc_18001BEE4
0x18001bf01  mov     rax, [r14]
0x18001bf04  lea     rdx, [rsp+0B10h+var_AD0]
0x18001bf09  mov     rcx, r14
0x18001bf0c  mov     rax, [rax+28h]
0x18001bf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf15  mov     ebx, eax
0x18001bf17  test    eax, eax
0x18001bf19  js      loc_18001C04D
0x18001bf1f  mov     [rsp+0B10h+var_AE0], r12
0x18001bf24  mov     rbx, cs:hModule
0x18001bf2b  mov     esi, 104h
0x18001bf30  mov     r8d, esi; nSize
0x18001bf33  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001bf37  mov     rcx, rbx; hModule
0x18001bf3a  call    cs:__imp_GetModuleFileNameW
0x18001bf40  test    eax, eax
0x18001bf42  jnz     short loc_18001BF50
0x18001bf44  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001bf49  mov     ebx, eax
0x18001bf4b  jmp     loc_18001C043
0x18001bf50  cmp     eax, esi
0x18001bf52  jnz     short loc_18001BF68
0x18001bf54  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bf59  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bf5e  mov     ebx, 8007007Ah
0x18001bf63  jmp     loc_18001C04D
0x18001bf68  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18001bf6c  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18001bf73  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x18001bf78  test    rbx, rbx
0x18001bf7b  jz      short loc_18001BF93
0x18001bf7d  xor     ecx, ecx; lpModuleName
0x18001bf7f  call    cs:__imp_GetModuleHandleW
0x18001bf85  cmp     rbx, rax
0x18001bf88  jz      short loc_18001BF93
0x18001bf8a  lea     r8, [rbp+0A10h+var_450]
0x18001bf91  jmp     short loc_18001C00E
0x18001bf93  mov     ebx, 22h ; '"'
0x18001bf98  mov     [rbp+0A10h+var_870], bx
0x18001bf9f  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18001bfa6  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18001bfad  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x18001bfb2  test    al, al
0x18001bfb4  jnz     short loc_18001BFCA
0x18001bfb6  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bfbb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bfc0  mov     ebx, 80004005h
0x18001bfc5  jmp     loc_18001C04D
0x18001bfca  lea     rcx, [rbp+0A10h+var_870]
0x18001bfd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bfd5  inc     rax
0x18001bfd8  cmp     [rcx+rax*2], r12w
0x18001bfdd  jnz     short loc_18001BFD5
0x18001bfdf  cdqe
0x18001bfe1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001bfe9  lea     rcx, ds:2[rax*2]
0x18001bff1  cmp     rcx, 418h
0x18001bff8  jnb     loc_18001C0AE
0x18001bffe  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001c007  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18001c00e  lea     rdx, aModule; "Module"
0x18001c015  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c01a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001c01f  mov     ebx, eax
0x18001c021  test    eax, eax
0x18001c023  js      short loc_18001C043
0x18001c025  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18001c02c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001c033  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c038  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001c03d  mov     ebx, eax
0x18001c03f  test    eax, eax
0x18001c041  jns     short loc_18001C05E
0x18001c043  lea     rcx, [rsp+0B10h+var_AE0]
0x18001c048  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001c04d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c052  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001c057  mov     eax, ebx
0x18001c059  jmp     loc_18001BEBC
0x18001c05e  mov     [rsp+0B10h+var_AD8], r12
0x18001c063  test    r15d, r15d
0x18001c066  jz      short loc_18001C077
0x18001c068  test    rdi, rdi
0x18001c06b  jz      short loc_18001C09D
0x18001c06d  mov     [rsp+0B10h+var_AF0], 1
0x18001c075  jmp     short loc_18001C081
0x18001c077  test    rdi, rdi
0x18001c07a  jz      short loc_18001C09D
0x18001c07c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001c081  lea     r9, aRegistry; "REGISTRY"
0x18001c088  mov     r8, rdi; wchar_t *
0x18001c08b  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18001c08f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c094  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18001c099  mov     ebx, eax
0x18001c09b  jmp     short loc_18001C0A2
0x18001c09d  mov     ebx, 80070057h
0x18001c0a2  lea     rcx, [rsp+0B10h+var_AD8]
0x18001c0a7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001c0ac  jmp     short loc_18001C043
0x18001c0ae  call    __report_rangecheckfailure
```
