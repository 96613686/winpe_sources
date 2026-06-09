# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000c224`
- end: `0x18000c4a4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c4c0`

## callees

- `0x180001f88`
- `0x18000882c`
- `0x180008a2c`
- `0x180008e80`
- `0x1800096f4`
- `0x18000a450`
- `0x18000a970`
- `0x18000b1f4`
- `0x18000c224`
- `0x18000c4cc`
- `0x18001a5e0`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000c32a`
- `KERNEL32!GetModuleFileNameW` at `0x18000c32a`
- `KERNEL32!GetModuleHandleW` at `0x18000c36f`
- `KERNEL32!GetModuleHandleW` at `0x18000c36f`

## string_xrefs

- `0x18000c471`: `REGISTRY`

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
  struct _RTL_CRITICAL_SECTION v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v27[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v28[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(&v23, 0, sizeof(v23));
  v24 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init(&v23);
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
    ATL::CAtlModule::EscapeSingleQuote(v28, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v26 = 34;
      if ( !ocscpy_s(v27, v14, v28) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v27[v16 - 1] );
      v27[(int)v16 - 1] = 34;
      v17 = 2LL * (int)v16 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v27[-1] + v17) = 0;
      v15 = &v26;
    }
    else
    {
      v15 = v28;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v28);
    if ( Error < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((const wchar_t *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        Error = v18;
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_23;
      }
    }
    else if ( a2 )
    {
      v18 = ATL::CRegObject::RegisterFromResource((const wchar_t *)v21, Filename, a2, L"REGISTRY", 0);
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
0x18000c224  push    rbp
0x18000c226  push    rbx
0x18000c227  push    rsi
0x18000c228  push    rdi
0x18000c229  push    r12
0x18000c22b  push    r14
0x18000c22d  push    r15
0x18000c22f  lea     rbp, [rsp-9E0h]
0x18000c237  sub     rsp, 0AE0h
0x18000c23e  mov     rax, cs:__security_cookie
0x18000c245  xor     rax, rsp
0x18000c248  mov     [rbp+0A10h+var_40], rax
0x18000c24f  mov     rbx, r9
0x18000c252  mov     r15d, r8d
0x18000c255  mov     rdi, rdx
0x18000c258  mov     r14, rcx
0x18000c25b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000c262  mov     [rsp+0B10h+var_AD0], rax
0x18000c267  xor     r12d, r12d
0x18000c26a  mov     [rsp+0B10h+var_AC8], r12
0x18000c26f  mov     [rsp+0B10h+var_AC0], r12
0x18000c274  mov     [rsp+0B10h+var_AB8], r12d
0x18000c279  xorps   xmm0, xmm0
0x18000c27c  xor     eax, eax
0x18000c27e  movups  [rsp+0B10h+var_AB0], xmm0
0x18000c283  movups  [rsp+0B10h+var_AA0], xmm0
0x18000c288  mov     [rbp+0A10h+var_A90], rax
0x18000c28c  mov     [rbp+0A10h+var_A88], r12b
0x18000c290  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000c295  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000c29a  mov     esi, eax
0x18000c29c  test    eax, eax
0x18000c29e  jns     short loc_18000C2CD
0x18000c2a0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c2a5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c2aa  mov     eax, esi
0x18000c2ac  mov     rcx, [rbp+0A10h+var_40]
0x18000c2b3  xor     rcx, rsp; StackCookie
0x18000c2b6  call    __security_check_cookie
0x18000c2bb  add     rsp, 0AE0h
0x18000c2c2  pop     r15
0x18000c2c4  pop     r14
0x18000c2c6  pop     r12
0x18000c2c8  pop     rdi
0x18000c2c9  pop     rsi
0x18000c2ca  pop     rbx
0x18000c2cb  pop     rbp
0x18000c2cc  retn
0x18000c2cd  test    rbx, rbx
0x18000c2d0  jz      short loc_18000C2F1
0x18000c2d2  jmp     short loc_18000C2E9
0x18000c2d4  mov     r8, [rbx+8]; unsigned __int16 *
0x18000c2d8  mov     rdx, rax; unsigned __int16 *
0x18000c2db  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c2e0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c2e5  lea     rbx, [rbx+10h]
0x18000c2e9  mov     rax, [rbx]
0x18000c2ec  test    rax, rax
0x18000c2ef  jnz     short loc_18000C2D4
0x18000c2f1  mov     rax, [r14]
0x18000c2f4  lea     rdx, [rsp+0B10h+var_AD0]
0x18000c2f9  mov     rcx, r14
0x18000c2fc  mov     rax, [rax+28h]
0x18000c300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c305  mov     ebx, eax
0x18000c307  test    eax, eax
0x18000c309  js      loc_18000C43D
0x18000c30f  mov     [rsp+0B10h+var_AE0], r12
0x18000c314  mov     rbx, cs:hModule
0x18000c31b  mov     esi, 104h
0x18000c320  mov     r8d, esi; nSize
0x18000c323  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000c327  mov     rcx, rbx; hModule
0x18000c32a  call    cs:__imp_GetModuleFileNameW
0x18000c330  test    eax, eax
0x18000c332  jnz     short loc_18000C340
0x18000c334  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c339  mov     ebx, eax
0x18000c33b  jmp     loc_18000C433
0x18000c340  cmp     eax, esi
0x18000c342  jnz     short loc_18000C358
0x18000c344  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c349  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c34e  mov     ebx, 8007007Ah
0x18000c353  jmp     loc_18000C43D
0x18000c358  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c35c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c363  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000c368  test    rbx, rbx
0x18000c36b  jz      short loc_18000C383
0x18000c36d  xor     ecx, ecx; lpModuleName
0x18000c36f  call    cs:__imp_GetModuleHandleW
0x18000c375  cmp     rbx, rax
0x18000c378  jz      short loc_18000C383
0x18000c37a  lea     r8, [rbp+0A10h+var_450]
0x18000c381  jmp     short loc_18000C3FE
0x18000c383  mov     ebx, 22h ; '"'
0x18000c388  mov     [rbp+0A10h+var_870], bx
0x18000c38f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c396  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000c39d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000c3a2  test    al, al
0x18000c3a4  jnz     short loc_18000C3BA
0x18000c3a6  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c3ab  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c3b0  mov     ebx, 80004005h
0x18000c3b5  jmp     loc_18000C43D
0x18000c3ba  lea     rcx, [rbp+0A10h+var_870]
0x18000c3c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c3c5  inc     rax
0x18000c3c8  cmp     [rcx+rax*2], r12w
0x18000c3cd  jnz     short loc_18000C3C5
0x18000c3cf  cdqe
0x18000c3d1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000c3d9  lea     rcx, ds:2[rax*2]
0x18000c3e1  cmp     rcx, 418h
0x18000c3e8  jnb     loc_18000C49E
0x18000c3ee  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000c3f7  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000c3fe  lea     rdx, aModule; "Module"
0x18000c405  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c40a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c40f  mov     ebx, eax
0x18000c411  test    eax, eax
0x18000c413  js      short loc_18000C433
0x18000c415  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c41c  lea     rdx, aModuleRaw; "Module_Raw"
0x18000c423  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c428  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c42d  mov     ebx, eax
0x18000c42f  test    eax, eax
0x18000c431  jns     short loc_18000C44E
0x18000c433  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c438  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c43d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c442  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c447  mov     eax, ebx
0x18000c449  jmp     loc_18000C2AC
0x18000c44e  mov     [rsp+0B10h+var_AD8], r12
0x18000c453  test    r15d, r15d
0x18000c456  jz      short loc_18000C467
0x18000c458  test    rdi, rdi
0x18000c45b  jz      short loc_18000C48D
0x18000c45d  mov     [rsp+0B10h+var_AF0], 1
0x18000c465  jmp     short loc_18000C471
0x18000c467  test    rdi, rdi
0x18000c46a  jz      short loc_18000C48D
0x18000c46c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000c471  lea     r9, aRegistry; "REGISTRY"
0x18000c478  mov     r8, rdi; unsigned __int16 *
0x18000c47b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c47f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c484  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000c489  mov     ebx, eax
0x18000c48b  jmp     short loc_18000C492
0x18000c48d  mov     ebx, 80070057h
0x18000c492  lea     rcx, [rsp+0B10h+var_AD8]
0x18000c497  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c49c  jmp     short loc_18000C433
0x18000c49e  call    __report_rangecheckfailure
```
