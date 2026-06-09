# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180023544`
- end: `0x18002379a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `598`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800237b0`

## callees

- `0x18001e4c0`
- `0x18001e610`
- `0x1800206d0`
- `0x180020810`
- `0x180020c00`
- `0x180021378`
- `0x18002186c`
- `0x180022920`
- `0x180023544`
- `0x1800237bc`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800235fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800235fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023640`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023640`

## string_xrefs

- `0x180023763`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *i; // rax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  void **v21; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v25; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v26[527]; // [rsp+282h] [rbp+182h] BYREF
  unsigned __int16 v27[520]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v4 = a4;
  v21 = &ATL::CRegObject::`vftable';
  v22 = 0;
  v23 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, i, v4[1]);
      v4 += 2;
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v10 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_21:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_22;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_22;
    }
    ATL::CAtlModule::EscapeSingleQuote(v27, v12, Filename);
    if ( !v10 || v10 == GetModuleHandleW(0) )
    {
      v25 = 34;
      if ( !ocscpy_s(v26, v13, v27) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_22;
      }
      v15 = -1;
      do
        ++v15;
      while ( v26[v15 - 1] );
      v26[(int)v15 - 1] = 34;
      v16 = 2LL * (int)v15 + 2;
      if ( v16 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v26[-1] + v16) = 0;
      v14 = &v25;
    }
    else
    {
      v14 = v27;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module", v14);
    if ( Error < 0 )
      goto LABEL_21;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module_Raw", v27);
    if ( Error < 0 )
      goto LABEL_21;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v21, Filename, a2, L"REGISTRY", 1);
LABEL_28:
        Error = v18;
LABEL_30:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_21;
      }
    }
    else if ( a2 )
    {
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_28;
    }
    Error = -2147024809;
    goto LABEL_30;
  }
LABEL_22:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180023544  mov     [rsp-8+arg_10], rbx
0x180023549  push    rbp
0x18002354a  push    rsi
0x18002354b  push    rdi
0x18002354c  push    r14
0x18002354e  push    r15
0x180023550  lea     rbp, [rsp-9C0h]
0x180023558  sub     rsp, 0AC0h
0x18002355f  mov     rax, cs:__security_cookie
0x180023566  xor     rax, rsp
0x180023569  mov     [rbp+9E0h+var_30], rax
0x180023570  mov     rbx, r9
0x180023573  mov     r14d, r8d
0x180023576  mov     rdi, rdx
0x180023579  mov     rsi, rcx
0x18002357c  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180023583  mov     [rsp+0AE0h+var_AA0], rax
0x180023588  xorps   xmm0, xmm0
0x18002358b  movdqu  [rsp+0AE0h+var_A98], xmm0
0x180023591  xor     r15d, r15d
0x180023594  mov     [rsp+0AE0h+var_A88], r15d
0x180023599  test    r9, r9
0x18002359c  jz      short loc_1800235C0
0x18002359e  mov     rax, [r9]
0x1800235a1  jmp     short loc_1800235BB
0x1800235a3  mov     r8, [rbx+8]; unsigned __int16 *
0x1800235a7  mov     rdx, rax; unsigned __int16 *
0x1800235aa  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800235af  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800235b4  lea     rbx, [rbx+10h]
0x1800235b8  mov     rax, [rbx]
0x1800235bb  test    rax, rax
0x1800235be  jnz     short loc_1800235A3
0x1800235c0  mov     rax, [rsi]
0x1800235c3  lea     rdx, [rsp+0AE0h+var_AA0]
0x1800235c8  mov     rcx, rsi
0x1800235cb  mov     rax, [rax+28h]
0x1800235cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235d4  mov     ebx, eax
0x1800235d6  test    eax, eax
0x1800235d8  js      loc_18002370E
0x1800235de  mov     [rsp+0AE0h+var_AB0], r15
0x1800235e3  mov     rbx, cs:hInstance
0x1800235ea  mov     esi, 104h
0x1800235ef  mov     r8d, esi; nSize
0x1800235f2  lea     rdx, [rsp+0AE0h+Filename]; lpFilename
0x1800235f7  mov     rcx, rbx; hModule
0x1800235fa  call    cs:__imp_GetModuleFileNameW
0x180023600  test    eax, eax
0x180023602  jnz     short loc_180023610
0x180023604  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180023609  mov     ebx, eax
0x18002360b  jmp     loc_180023704
0x180023610  cmp     eax, esi
0x180023612  jnz     short loc_180023628
0x180023614  lea     rcx, [rsp+0AE0h+var_AB0]
0x180023619  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002361e  mov     ebx, 8007007Ah
0x180023623  jmp     loc_18002370E
0x180023628  lea     r8, [rsp+0AE0h+Filename]; unsigned __int16 *
0x18002362d  lea     rcx, [rbp+9E0h+var_440]; unsigned __int16 *
0x180023634  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180023639  test    rbx, rbx
0x18002363c  jz      short loc_180023654
0x18002363e  xor     ecx, ecx; lpModuleName
0x180023640  call    cs:__imp_GetModuleHandleW
0x180023646  cmp     rbx, rax
0x180023649  jz      short loc_180023654
0x18002364b  lea     r8, [rbp+9E0h+var_440]
0x180023652  jmp     short loc_1800236CF
0x180023654  mov     ebx, 22h ; '"'
0x180023659  mov     [rbp+9E0h+var_860], bx
0x180023660  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x180023667  lea     rcx, [rbp+9E0h+var_85E]; unsigned __int16 *
0x18002366e  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180023673  test    al, al
0x180023675  jnz     short loc_18002368B
0x180023677  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002367c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180023681  mov     ebx, 80004005h
0x180023686  jmp     loc_18002370E
0x18002368b  lea     rcx, [rbp+9E0h+var_860]
0x180023692  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023696  inc     rax
0x180023699  cmp     [rcx+rax*2], r15w
0x18002369e  jnz     short loc_180023696
0x1800236a0  cdqe
0x1800236a2  mov     [rbp+rax*2+9E0h+var_860], bx
0x1800236aa  lea     rcx, ds:2[rax*2]
0x1800236b2  cmp     rcx, 418h
0x1800236b9  jnb     loc_180023794
0x1800236bf  mov     [rbp+rcx+9E0h+var_860], r15w
0x1800236c8  lea     r8, [rbp+9E0h+var_860]; unsigned __int16 *
0x1800236cf  lea     rdx, aModule; "Module"
0x1800236d6  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800236db  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800236e0  mov     ebx, eax
0x1800236e2  test    eax, eax
0x1800236e4  js      short loc_180023704
0x1800236e6  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x1800236ed  lea     rdx, aModuleRaw; "Module_Raw"
0x1800236f4  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800236f9  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800236fe  mov     ebx, eax
0x180023700  test    eax, eax
0x180023702  jns     short loc_180023740
0x180023704  lea     rcx, [rsp+0AE0h+var_AB0]
0x180023709  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002370e  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180023713  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180023718  mov     eax, ebx
0x18002371a  mov     rcx, [rbp+9E0h+var_30]
0x180023721  xor     rcx, rsp; StackCookie
0x180023724  call    __security_check_cookie
0x180023729  mov     rbx, [rsp+0AE0h+arg_10]
0x180023731  add     rsp, 0AC0h
0x180023738  pop     r15
0x18002373a  pop     r14
0x18002373c  pop     rdi
0x18002373d  pop     rsi
0x18002373e  pop     rbp
0x18002373f  retn
0x180023740  mov     [rsp+0AE0h+var_AA8], r15
0x180023745  test    r14d, r14d
0x180023748  jz      short loc_180023759
0x18002374a  test    rdi, rdi
0x18002374d  jz      short loc_180023780
0x18002374f  mov     [rsp+0AE0h+var_AC0], 1
0x180023757  jmp     short loc_180023763
0x180023759  test    rdi, rdi
0x18002375c  jz      short loc_180023780
0x18002375e  mov     [rsp+0AE0h+var_AC0], r15d; int
0x180023763  lea     r9, aRegistry; "REGISTRY"
0x18002376a  mov     r8, rdi; unsigned __int16 *
0x18002376d  lea     rdx, [rsp+0AE0h+Filename]; unsigned __int16 *
0x180023772  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180023777  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18002377c  mov     ebx, eax
0x18002377e  jmp     short loc_180023785
0x180023780  mov     ebx, 80070057h
0x180023785  lea     rcx, [rsp+0AE0h+var_AA8]
0x18002378a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002378f  jmp     loc_180023704
0x180023794  call    __report_rangecheckfailure
```
