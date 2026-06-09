# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180018204`
- end: `0x180018494`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `656`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800184b0`

## callees

- `0x180001710`
- `0x180001a10`
- `0x180002320`
- `0x1800071a0`
- `0x18000867c`
- `0x18000a110`
- `0x18000a984`
- `0x18000fe28`
- `0x18001186c`
- `0x180014b7c`
- `0x180018204`
- `0x180018db0`
- `0x180036010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18001831a`
- `KERNEL32!GetModuleFileNameW` at `0x18001831a`
- `KERNEL32!GetModuleHandleW` at `0x18001835f`
- `KERNEL32!GetModuleHandleW` at `0x18001835f`

## string_xrefs

- `0x180018461`: `REGISTRY`

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

  memset_0(v21, 0, 0x50u);
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
0x180018204  push    rbp
0x180018206  push    rbx
0x180018207  push    rsi
0x180018208  push    rdi
0x180018209  push    r12
0x18001820b  push    r14
0x18001820d  push    r15
0x18001820f  lea     rbp, [rsp-9E0h]
0x180018217  sub     rsp, 0AE0h
0x18001821e  mov     rax, cs:__security_cookie
0x180018225  xor     rax, rsp
0x180018228  mov     [rbp+0A10h+var_40], rax
0x18001822f  mov     rbx, r9
0x180018232  mov     r15d, r8d
0x180018235  mov     rdi, rdx
0x180018238  mov     r14, rcx
0x18001823b  xor     edx, edx; Val
0x18001823d  lea     r8d, [rdx+50h]; Size
0x180018241  lea     rcx, [rsp+0B10h+var_AD0]; void *
0x180018246  call    memset_0
0x18001824b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180018252  mov     [rsp+0B10h+var_AD0], rax
0x180018257  xor     r12d, r12d
0x18001825a  mov     [rsp+0B10h+var_AC8], r12
0x18001825f  mov     [rsp+0B10h+var_AC0], r12
0x180018264  mov     [rsp+0B10h+var_AB8], r12d
0x180018269  xorps   xmm0, xmm0
0x18001826c  xor     eax, eax
0x18001826e  movups  [rsp+0B10h+var_AB0], xmm0
0x180018273  movups  [rsp+0B10h+var_AA0], xmm0
0x180018278  mov     [rbp+0A10h+var_A90], rax
0x18001827c  mov     [rbp+0A10h+var_A88], r12b
0x180018280  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180018285  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001828a  mov     esi, eax
0x18001828c  test    eax, eax
0x18001828e  jns     short loc_1800182BD
0x180018290  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018295  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001829a  mov     eax, esi
0x18001829c  mov     rcx, [rbp+0A10h+var_40]
0x1800182a3  xor     rcx, rsp; StackCookie
0x1800182a6  call    __security_check_cookie
0x1800182ab  add     rsp, 0AE0h
0x1800182b2  pop     r15
0x1800182b4  pop     r14
0x1800182b6  pop     r12
0x1800182b8  pop     rdi
0x1800182b9  pop     rsi
0x1800182ba  pop     rbx
0x1800182bb  pop     rbp
0x1800182bc  retn
0x1800182bd  test    rbx, rbx
0x1800182c0  jz      short loc_1800182E1
0x1800182c2  jmp     short loc_1800182D9
0x1800182c4  mov     r8, [rbx+8]; unsigned __int16 *
0x1800182c8  mov     rdx, rax; unsigned __int16 *
0x1800182cb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800182d0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800182d5  lea     rbx, [rbx+10h]
0x1800182d9  mov     rax, [rbx]
0x1800182dc  test    rax, rax
0x1800182df  jnz     short loc_1800182C4
0x1800182e1  mov     rax, [r14]
0x1800182e4  lea     rdx, [rsp+0B10h+var_AD0]
0x1800182e9  mov     rcx, r14
0x1800182ec  mov     rax, [rax+28h]
0x1800182f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182f5  mov     ebx, eax
0x1800182f7  test    eax, eax
0x1800182f9  js      loc_18001842D
0x1800182ff  mov     [rsp+0B10h+var_AE0], r12
0x180018304  mov     rbx, cs:hModule
0x18001830b  mov     esi, 104h
0x180018310  mov     r8d, esi; nSize
0x180018313  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180018317  mov     rcx, rbx; hModule
0x18001831a  call    cs:__imp_GetModuleFileNameW
0x180018320  test    eax, eax
0x180018322  jnz     short loc_180018330
0x180018324  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018329  mov     ebx, eax
0x18001832b  jmp     loc_180018423
0x180018330  cmp     eax, esi
0x180018332  jnz     short loc_180018348
0x180018334  lea     rcx, [rsp+0B10h+var_AE0]
0x180018339  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001833e  mov     ebx, 8007007Ah
0x180018343  jmp     loc_18001842D
0x180018348  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001834c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180018353  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180018358  test    rbx, rbx
0x18001835b  jz      short loc_180018373
0x18001835d  xor     ecx, ecx; lpModuleName
0x18001835f  call    cs:__imp_GetModuleHandleW
0x180018365  cmp     rbx, rax
0x180018368  jz      short loc_180018373
0x18001836a  lea     r8, [rbp+0A10h+var_450]
0x180018371  jmp     short loc_1800183EE
0x180018373  mov     ebx, 22h ; '"'
0x180018378  mov     [rbp+0A10h+var_870], bx
0x18001837f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180018386  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001838d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180018392  test    al, al
0x180018394  jnz     short loc_1800183AA
0x180018396  lea     rcx, [rsp+0B10h+var_AE0]
0x18001839b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800183a0  mov     ebx, 80004005h
0x1800183a5  jmp     loc_18001842D
0x1800183aa  lea     rcx, [rbp+0A10h+var_870]
0x1800183b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800183b5  inc     rax
0x1800183b8  cmp     [rcx+rax*2], r12w
0x1800183bd  jnz     short loc_1800183B5
0x1800183bf  cdqe
0x1800183c1  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800183c9  lea     rcx, ds:2[rax*2]
0x1800183d1  cmp     rcx, 418h
0x1800183d8  jnb     loc_18001848E
0x1800183de  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800183e7  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x1800183ee  lea     rdx, aModule; "Module"
0x1800183f5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800183fa  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800183ff  mov     ebx, eax
0x180018401  test    eax, eax
0x180018403  js      short loc_180018423
0x180018405  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001840c  lea     rdx, aModuleRaw; "Module_Raw"
0x180018413  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018418  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001841d  mov     ebx, eax
0x18001841f  test    eax, eax
0x180018421  jns     short loc_18001843E
0x180018423  lea     rcx, [rsp+0B10h+var_AE0]
0x180018428  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001842d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018432  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180018437  mov     eax, ebx
0x180018439  jmp     loc_18001829C
0x18001843e  mov     [rsp+0B10h+var_AD8], r12
0x180018443  test    r15d, r15d
0x180018446  jz      short loc_180018457
0x180018448  test    rdi, rdi
0x18001844b  jz      short loc_18001847D
0x18001844d  mov     [rsp+0B10h+var_AF0], 1
0x180018455  jmp     short loc_180018461
0x180018457  test    rdi, rdi
0x18001845a  jz      short loc_18001847D
0x18001845c  mov     [rsp+0B10h+var_AF0], r12d; int
0x180018461  lea     r9, aRegistry; "REGISTRY"
0x180018468  mov     r8, rdi; unsigned __int16 *
0x18001846b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001846f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018474  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180018479  mov     ebx, eax
0x18001847b  jmp     short loc_180018482
0x18001847d  mov     ebx, 80070057h
0x180018482  lea     rcx, [rsp+0B10h+var_AD8]
0x180018487  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001848c  jmp     short loc_180018423
0x18001848e  call    __report_rangecheckfailure
```
