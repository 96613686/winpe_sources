# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180017584`
- end: `0x180017804`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017820`

## callees

- `0x180003368`
- `0x180013378`
- `0x18001350c`
- `0x180013920`
- `0x18001405c`
- `0x180015250`
- `0x1800155b4`
- `0x1800162bc`
- `0x180017584`
- `0x180017844`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001768a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001768a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800176cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800176cf`

## string_xrefs

- `0x1800177d1`: `REGISTRY`

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
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
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
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
0x180017584  push    rbp
0x180017586  push    rbx
0x180017587  push    rsi
0x180017588  push    rdi
0x180017589  push    r12
0x18001758b  push    r14
0x18001758d  push    r15
0x18001758f  lea     rbp, [rsp-9E0h]
0x180017597  sub     rsp, 0AE0h
0x18001759e  mov     rax, cs:__security_cookie
0x1800175a5  xor     rax, rsp
0x1800175a8  mov     [rbp+0A10h+var_40], rax
0x1800175af  mov     rbx, r9
0x1800175b2  mov     r15d, r8d
0x1800175b5  mov     rdi, rdx
0x1800175b8  mov     r14, rcx
0x1800175bb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800175c2  mov     [rsp+0B10h+var_AD0], rax
0x1800175c7  xor     r12d, r12d
0x1800175ca  mov     [rsp+0B10h+var_AC8], r12
0x1800175cf  mov     [rsp+0B10h+var_AC0], r12
0x1800175d4  mov     [rsp+0B10h+var_AB8], r12d
0x1800175d9  xorps   xmm0, xmm0
0x1800175dc  xor     eax, eax
0x1800175de  movups  [rsp+0B10h+var_AB0], xmm0
0x1800175e3  movups  [rsp+0B10h+var_AA0], xmm0
0x1800175e8  mov     [rbp+0A10h+var_A90], rax
0x1800175ec  mov     [rbp+0A10h+var_A88], r12b
0x1800175f0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x1800175f5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800175fa  mov     esi, eax
0x1800175fc  test    eax, eax
0x1800175fe  jns     short loc_18001762D
0x180017600  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180017605  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001760a  mov     eax, esi
0x18001760c  mov     rcx, [rbp+0A10h+var_40]
0x180017613  xor     rcx, rsp; StackCookie
0x180017616  call    __security_check_cookie
0x18001761b  add     rsp, 0AE0h
0x180017622  pop     r15
0x180017624  pop     r14
0x180017626  pop     r12
0x180017628  pop     rdi
0x180017629  pop     rsi
0x18001762a  pop     rbx
0x18001762b  pop     rbp
0x18001762c  retn
0x18001762d  test    rbx, rbx
0x180017630  jz      short loc_180017651
0x180017632  jmp     short loc_180017649
0x180017634  mov     r8, [rbx+8]; unsigned __int16 *
0x180017638  mov     rdx, rax; unsigned __int16 *
0x18001763b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180017640  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180017645  lea     rbx, [rbx+10h]
0x180017649  mov     rax, [rbx]
0x18001764c  test    rax, rax
0x18001764f  jnz     short loc_180017634
0x180017651  mov     rax, [r14]
0x180017654  lea     rdx, [rsp+0B10h+var_AD0]
0x180017659  mov     rcx, r14
0x18001765c  mov     rax, [rax+28h]
0x180017660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017665  mov     ebx, eax
0x180017667  test    eax, eax
0x180017669  js      loc_18001779D
0x18001766f  mov     [rsp+0B10h+var_AE0], r12
0x180017674  mov     rbx, cs:hInstance
0x18001767b  mov     esi, 104h
0x180017680  mov     r8d, esi; nSize
0x180017683  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180017687  mov     rcx, rbx; hModule
0x18001768a  call    cs:__imp_GetModuleFileNameW
0x180017690  test    eax, eax
0x180017692  jnz     short loc_1800176A0
0x180017694  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017699  mov     ebx, eax
0x18001769b  jmp     loc_180017793
0x1800176a0  cmp     eax, esi
0x1800176a2  jnz     short loc_1800176B8
0x1800176a4  lea     rcx, [rsp+0B10h+var_AE0]
0x1800176a9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800176ae  mov     ebx, 8007007Ah
0x1800176b3  jmp     loc_18001779D
0x1800176b8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800176bc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800176c3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800176c8  test    rbx, rbx
0x1800176cb  jz      short loc_1800176E3
0x1800176cd  xor     ecx, ecx; lpModuleName
0x1800176cf  call    cs:__imp_GetModuleHandleW
0x1800176d5  cmp     rbx, rax
0x1800176d8  jz      short loc_1800176E3
0x1800176da  lea     r8, [rbp+0A10h+var_450]
0x1800176e1  jmp     short loc_18001775E
0x1800176e3  mov     ebx, 22h ; '"'
0x1800176e8  mov     [rbp+0A10h+var_870], bx
0x1800176ef  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800176f6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x1800176fd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180017702  test    al, al
0x180017704  jnz     short loc_18001771A
0x180017706  lea     rcx, [rsp+0B10h+var_AE0]
0x18001770b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017710  mov     ebx, 80004005h
0x180017715  jmp     loc_18001779D
0x18001771a  lea     rcx, [rbp+0A10h+var_870]
0x180017721  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017725  inc     rax
0x180017728  cmp     [rcx+rax*2], r12w
0x18001772d  jnz     short loc_180017725
0x18001772f  cdqe
0x180017731  mov     [rbp+rax*2+0A10h+var_870], bx
0x180017739  lea     rcx, ds:2[rax*2]
0x180017741  cmp     rcx, 418h
0x180017748  jnb     loc_1800177FE
0x18001774e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180017757  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001775e  lea     rdx, aModule; "Module"
0x180017765  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001776a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001776f  mov     ebx, eax
0x180017771  test    eax, eax
0x180017773  js      short loc_180017793
0x180017775  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001777c  lea     rdx, aModuleRaw; "Module_Raw"
0x180017783  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180017788  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001778d  mov     ebx, eax
0x18001778f  test    eax, eax
0x180017791  jns     short loc_1800177AE
0x180017793  lea     rcx, [rsp+0B10h+var_AE0]
0x180017798  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001779d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800177a2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800177a7  mov     eax, ebx
0x1800177a9  jmp     loc_18001760C
0x1800177ae  mov     [rsp+0B10h+var_AD8], r12
0x1800177b3  test    r15d, r15d
0x1800177b6  jz      short loc_1800177C7
0x1800177b8  test    rdi, rdi
0x1800177bb  jz      short loc_1800177ED
0x1800177bd  mov     [rsp+0B10h+var_AF0], 1
0x1800177c5  jmp     short loc_1800177D1
0x1800177c7  test    rdi, rdi
0x1800177ca  jz      short loc_1800177ED
0x1800177cc  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800177d1  lea     r9, aRegistry; "REGISTRY"
0x1800177d8  mov     r8, rdi; unsigned __int16 *
0x1800177db  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800177df  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800177e4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800177e9  mov     ebx, eax
0x1800177eb  jmp     short loc_1800177F2
0x1800177ed  mov     ebx, 80070057h
0x1800177f2  lea     rcx, [rsp+0B10h+var_AD8]
0x1800177f7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800177fc  jmp     short loc_180017793
0x1800177fe  call    __report_rangecheckfailure
```
