# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001212c`
- end: `0x18001239c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012630`

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
- `0x18001212c`
- `0x180012eac`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012277`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012277`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180012232`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180012232`

## string_xrefs

- `0x18001235f`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const wchar_t *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const wchar_t *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001212c  push    rbp
0x18001212e  push    rbx
0x18001212f  push    rsi
0x180012130  push    rdi
0x180012131  push    r12
0x180012133  push    r14
0x180012135  push    r15
0x180012137  lea     rbp, [rsp-9E0h]
0x18001213f  sub     rsp, 0AE0h
0x180012146  mov     rax, cs:__security_cookie
0x18001214d  xor     rax, rsp
0x180012150  mov     [rbp+0A10h+var_40], rax
0x180012157  mov     rbx, r9
0x18001215a  mov     r14d, r8d
0x18001215d  mov     r15d, edx
0x180012160  mov     rsi, rcx
0x180012163  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001216a  mov     [rsp+0B10h+var_AD0], rax
0x18001216f  xor     r12d, r12d
0x180012172  mov     [rsp+0B10h+var_AC8], r12
0x180012177  mov     [rsp+0B10h+var_AC0], r12
0x18001217c  mov     [rsp+0B10h+var_AB8], r12d
0x180012181  xorps   xmm0, xmm0
0x180012184  xor     eax, eax
0x180012186  movups  [rsp+0B10h+var_AB0], xmm0
0x18001218b  movups  [rsp+0B10h+var_AA0], xmm0
0x180012190  mov     [rbp+0A10h+var_A90], rax
0x180012194  mov     [rbp+0A10h+var_A88], r12b
0x180012198  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001219d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800121a2  mov     edi, eax
0x1800121a4  test    eax, eax
0x1800121a6  jns     short loc_1800121D5
0x1800121a8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800121ad  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800121b2  mov     eax, edi
0x1800121b4  mov     rcx, [rbp+0A10h+var_40]
0x1800121bb  xor     rcx, rsp; StackCookie
0x1800121be  call    __security_check_cookie
0x1800121c3  add     rsp, 0AE0h
0x1800121ca  pop     r15
0x1800121cc  pop     r14
0x1800121ce  pop     r12
0x1800121d0  pop     rdi
0x1800121d1  pop     rsi
0x1800121d2  pop     rbx
0x1800121d3  pop     rbp
0x1800121d4  retn
0x1800121d5  test    rbx, rbx
0x1800121d8  jz      short loc_1800121F9
0x1800121da  jmp     short loc_1800121F1
0x1800121dc  mov     r8, [rbx+8]; wchar_t *
0x1800121e0  mov     rdx, rax; wchar_t *
0x1800121e3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800121e8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x1800121ed  lea     rbx, [rbx+10h]
0x1800121f1  mov     rax, [rbx]
0x1800121f4  test    rax, rax
0x1800121f7  jnz     short loc_1800121DC
0x1800121f9  mov     rax, [rsi]
0x1800121fc  lea     rdx, [rsp+0B10h+var_AD0]
0x180012201  mov     rcx, rsi
0x180012204  mov     rax, [rax+28h]
0x180012208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001220d  mov     ebx, eax
0x18001220f  test    eax, eax
0x180012211  js      loc_180012345
0x180012217  mov     [rsp+0B10h+var_AE0], r12
0x18001221c  mov     rbx, cs:off_180053498
0x180012223  mov     edi, 104h
0x180012228  mov     r8d, edi; nSize
0x18001222b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001222f  mov     rcx, rbx; hModule
0x180012232  call    cs:__imp_GetModuleFileNameW
0x180012238  test    eax, eax
0x18001223a  jnz     short loc_180012248
0x18001223c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180012241  mov     ebx, eax
0x180012243  jmp     loc_18001233B
0x180012248  cmp     eax, edi
0x18001224a  jnz     short loc_180012260
0x18001224c  lea     rcx, [rsp+0B10h+var_AE0]
0x180012251  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012256  mov     ebx, 8007007Ah
0x18001225b  jmp     loc_180012345
0x180012260  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x180012264  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18001226b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x180012270  test    rbx, rbx
0x180012273  jz      short loc_18001228B
0x180012275  xor     ecx, ecx; lpModuleName
0x180012277  call    cs:__imp_GetModuleHandleW
0x18001227d  cmp     rbx, rax
0x180012280  jz      short loc_18001228B
0x180012282  lea     r8, [rbp+0A10h+var_450]
0x180012289  jmp     short loc_180012306
0x18001228b  mov     ebx, 22h ; '"'
0x180012290  mov     [rbp+0A10h+var_870], bx
0x180012297  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18001229e  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x1800122a5  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x1800122aa  test    al, al
0x1800122ac  jnz     short loc_1800122C2
0x1800122ae  lea     rcx, [rsp+0B10h+var_AE0]
0x1800122b3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800122b8  mov     ebx, 80004005h
0x1800122bd  jmp     loc_180012345
0x1800122c2  lea     rcx, [rbp+0A10h+var_870]
0x1800122c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800122cd  inc     rax
0x1800122d0  cmp     [rcx+rax*2], r12w
0x1800122d5  jnz     short loc_1800122CD
0x1800122d7  cdqe
0x1800122d9  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800122e1  lea     rcx, ds:2[rax*2]
0x1800122e9  cmp     rcx, 418h
0x1800122f0  jnb     loc_180012396
0x1800122f6  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800122ff  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x180012306  lea     rdx, aModule; "Module"
0x18001230d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012312  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180012317  mov     ebx, eax
0x180012319  test    eax, eax
0x18001231b  js      short loc_18001233B
0x18001231d  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x180012324  lea     rdx, aModuleRaw; "Module_Raw"
0x18001232b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012330  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180012335  mov     ebx, eax
0x180012337  test    eax, eax
0x180012339  jns     short loc_180012356
0x18001233b  lea     rcx, [rsp+0B10h+var_AE0]
0x180012340  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012345  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001234a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001234f  mov     eax, ebx
0x180012351  jmp     loc_1800121B4
0x180012356  movzx   r8d, r15w; wchar_t *
0x18001235a  mov     [rsp+0B10h+var_AD8], r12
0x18001235f  lea     r9, aRegistry; "REGISTRY"
0x180012366  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18001236a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001236f  test    r14d, r14d
0x180012372  jz      short loc_18001237E
0x180012374  mov     [rsp+0B10h+var_AF0], 1
0x18001237c  jmp     short loc_180012383
0x18001237e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180012383  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180012388  mov     ebx, eax
0x18001238a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001238f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012394  jmp     short loc_18001233B
0x180012396  call    __report_rangecheckfailure
```
