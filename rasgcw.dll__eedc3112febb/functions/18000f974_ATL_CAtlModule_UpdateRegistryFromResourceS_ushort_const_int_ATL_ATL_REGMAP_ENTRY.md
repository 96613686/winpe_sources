# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000f974`
- end: `0x18000fbf4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fc10`

## callees

- `0x1800027c8`
- `0x180004078`
- `0x1800051f4`
- `0x180006700`
- `0x180006f60`
- `0x18000c118`
- `0x18000c470`
- `0x18000df50`
- `0x18000f974`
- `0x1800102c0`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fabf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fabf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000fa7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000fa7a`

## string_xrefs

- `0x18000fbc1`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // r8
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
    v11 = hInst;
    ModuleFileNameW = GetModuleFileNameW(hInst, Filename, 0x104u);
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
      *(unsigned __int16 *)((char *)&v28[-1] + v17) = 0;
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
0x18000f974  push    rbp
0x18000f976  push    rbx
0x18000f977  push    rsi
0x18000f978  push    rdi
0x18000f979  push    r12
0x18000f97b  push    r14
0x18000f97d  push    r15
0x18000f97f  lea     rbp, [rsp-9E0h]
0x18000f987  sub     rsp, 0AE0h
0x18000f98e  mov     rax, cs:__security_cookie
0x18000f995  xor     rax, rsp
0x18000f998  mov     [rbp+0A10h+var_40], rax
0x18000f99f  mov     rbx, r9
0x18000f9a2  mov     r15d, r8d
0x18000f9a5  mov     rdi, rdx
0x18000f9a8  mov     r14, rcx
0x18000f9ab  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000f9b2  mov     [rsp+0B10h+var_AD0], rax
0x18000f9b7  xor     r12d, r12d
0x18000f9ba  mov     [rsp+0B10h+var_AC8], r12
0x18000f9bf  mov     [rsp+0B10h+var_AC0], r12
0x18000f9c4  mov     [rsp+0B10h+var_AB8], r12d
0x18000f9c9  xorps   xmm0, xmm0
0x18000f9cc  xor     eax, eax
0x18000f9ce  movups  [rsp+0B10h+var_AB0], xmm0
0x18000f9d3  movups  [rsp+0B10h+var_AA0], xmm0
0x18000f9d8  mov     [rbp+0A10h+var_A90], rax
0x18000f9dc  mov     [rbp+0A10h+var_A88], r12b
0x18000f9e0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000f9e5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000f9ea  mov     esi, eax
0x18000f9ec  test    eax, eax
0x18000f9ee  jns     short loc_18000FA1D
0x18000f9f0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f9f5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000f9fa  mov     eax, esi
0x18000f9fc  mov     rcx, [rbp+0A10h+var_40]
0x18000fa03  xor     rcx, rsp; StackCookie
0x18000fa06  call    __security_check_cookie
0x18000fa0b  add     rsp, 0AE0h
0x18000fa12  pop     r15
0x18000fa14  pop     r14
0x18000fa16  pop     r12
0x18000fa18  pop     rdi
0x18000fa19  pop     rsi
0x18000fa1a  pop     rbx
0x18000fa1b  pop     rbp
0x18000fa1c  retn
0x18000fa1d  test    rbx, rbx
0x18000fa20  jz      short loc_18000FA41
0x18000fa22  jmp     short loc_18000FA39
0x18000fa24  mov     r8, [rbx+8]; unsigned __int16 *
0x18000fa28  mov     rdx, rax; unsigned __int16 *
0x18000fa2b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fa30  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fa35  lea     rbx, [rbx+10h]
0x18000fa39  mov     rax, [rbx]
0x18000fa3c  test    rax, rax
0x18000fa3f  jnz     short loc_18000FA24
0x18000fa41  mov     rax, [r14]
0x18000fa44  lea     rdx, [rsp+0B10h+var_AD0]
0x18000fa49  mov     rcx, r14
0x18000fa4c  mov     rax, [rax+28h]
0x18000fa50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa55  mov     ebx, eax
0x18000fa57  test    eax, eax
0x18000fa59  js      loc_18000FB8D
0x18000fa5f  mov     [rsp+0B10h+var_AE0], r12
0x18000fa64  mov     rbx, cs:hInst
0x18000fa6b  mov     esi, 104h
0x18000fa70  mov     r8d, esi; nSize
0x18000fa73  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000fa77  mov     rcx, rbx; hModule
0x18000fa7a  call    cs:__imp_GetModuleFileNameW
0x18000fa80  test    eax, eax
0x18000fa82  jnz     short loc_18000FA90
0x18000fa84  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fa89  mov     ebx, eax
0x18000fa8b  jmp     loc_18000FB83
0x18000fa90  cmp     eax, esi
0x18000fa92  jnz     short loc_18000FAA8
0x18000fa94  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fa99  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fa9e  mov     ebx, 8007007Ah
0x18000faa3  jmp     loc_18000FB8D
0x18000faa8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000faac  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fab3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000fab8  test    rbx, rbx
0x18000fabb  jz      short loc_18000FAD3
0x18000fabd  xor     ecx, ecx; lpModuleName
0x18000fabf  call    cs:__imp_GetModuleHandleW
0x18000fac5  cmp     rbx, rax
0x18000fac8  jz      short loc_18000FAD3
0x18000faca  lea     r8, [rbp+0A10h+var_450]
0x18000fad1  jmp     short loc_18000FB4E
0x18000fad3  mov     ebx, 22h ; '"'
0x18000fad8  mov     [rbp+0A10h+var_870], bx
0x18000fadf  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fae6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000faed  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000faf2  test    al, al
0x18000faf4  jnz     short loc_18000FB0A
0x18000faf6  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fafb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fb00  mov     ebx, 80004005h
0x18000fb05  jmp     loc_18000FB8D
0x18000fb0a  lea     rcx, [rbp+0A10h+var_870]
0x18000fb11  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fb15  inc     rax
0x18000fb18  cmp     [rcx+rax*2], r12w
0x18000fb1d  jnz     short loc_18000FB15
0x18000fb1f  cdqe
0x18000fb21  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000fb29  lea     rcx, ds:2[rax*2]
0x18000fb31  cmp     rcx, 418h
0x18000fb38  jnb     loc_18000FBEE
0x18000fb3e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000fb47  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000fb4e  lea     rdx, aModule; "Module"
0x18000fb55  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fb5a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fb5f  mov     ebx, eax
0x18000fb61  test    eax, eax
0x18000fb63  js      short loc_18000FB83
0x18000fb65  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fb6c  lea     rdx, aModuleRaw; "Module_Raw"
0x18000fb73  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fb78  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fb7d  mov     ebx, eax
0x18000fb7f  test    eax, eax
0x18000fb81  jns     short loc_18000FB9E
0x18000fb83  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fb88  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fb8d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fb92  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000fb97  mov     eax, ebx
0x18000fb99  jmp     loc_18000F9FC
0x18000fb9e  mov     [rsp+0B10h+var_AD8], r12
0x18000fba3  test    r15d, r15d
0x18000fba6  jz      short loc_18000FBB7
0x18000fba8  test    rdi, rdi
0x18000fbab  jz      short loc_18000FBDD
0x18000fbad  mov     [rsp+0B10h+var_AF0], 1
0x18000fbb5  jmp     short loc_18000FBC1
0x18000fbb7  test    rdi, rdi
0x18000fbba  jz      short loc_18000FBDD
0x18000fbbc  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000fbc1  lea     r9, aRegistry; "REGISTRY"
0x18000fbc8  mov     r8, rdi; unsigned __int16 *
0x18000fbcb  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000fbcf  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fbd4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000fbd9  mov     ebx, eax
0x18000fbdb  jmp     short loc_18000FBE2
0x18000fbdd  mov     ebx, 80070057h
0x18000fbe2  lea     rcx, [rsp+0B10h+var_AD8]
0x18000fbe7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fbec  jmp     short loc_18000FB83
0x18000fbee  call    __report_rangecheckfailure
```
