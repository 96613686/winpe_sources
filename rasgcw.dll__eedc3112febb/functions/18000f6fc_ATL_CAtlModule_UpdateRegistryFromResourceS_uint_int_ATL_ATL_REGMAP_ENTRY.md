# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000f6fc`
- end: `0x18000f96c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `29`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f370`
- `0x18000f390`
- `0x18000f3b0`
- `0x18000f3d0`
- `0x18000f3f0`
- `0x18000f410`
- `0x18000f430`
- `0x18000f450`
- `0x18000f470`
- `0x18000f490`
- `0x18000f4b0`
- `0x18000f4d0`
- `0x18000f4f0`
- `0x18000f510`
- `0x18000f530`
- `0x18000f550`
- `0x18000f570`
- `0x18000f590`
- `0x18000f5b0`
- `0x18000f5d0`
- `0x18000f5f0`
- `0x18000f610`
- `0x18000f630`
- `0x18000f650`
- `0x18000f670`
- `0x18000f690`
- `0x18000f6b0`
- `0x18000f6d0`
- `0x18000fc00`

## callees

- `0x1800027c8`
- `0x180004078`
- `0x1800051f4`
- `0x180006700`
- `0x180006f60`
- `0x18000c118`
- `0x18000c470`
- `0x18000df50`
- `0x18000f6fc`
- `0x1800102c0`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f847`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f847`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000f802`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000f802`

## string_xrefs

- `0x18000f92f`: `REGISTRY`

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
        *(unsigned __int16 *)((char *)&v28[-1] + v17) = 0;
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
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
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
0x18000f6fc  push    rbp
0x18000f6fe  push    rbx
0x18000f6ff  push    rsi
0x18000f700  push    rdi
0x18000f701  push    r12
0x18000f703  push    r14
0x18000f705  push    r15
0x18000f707  lea     rbp, [rsp-9E0h]
0x18000f70f  sub     rsp, 0AE0h
0x18000f716  mov     rax, cs:__security_cookie
0x18000f71d  xor     rax, rsp
0x18000f720  mov     [rbp+0A10h+var_40], rax
0x18000f727  mov     rbx, r9
0x18000f72a  mov     r14d, r8d
0x18000f72d  mov     r15d, edx
0x18000f730  mov     rsi, rcx
0x18000f733  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000f73a  mov     [rsp+0B10h+var_AD0], rax
0x18000f73f  xor     r12d, r12d
0x18000f742  mov     [rsp+0B10h+var_AC8], r12
0x18000f747  mov     [rsp+0B10h+var_AC0], r12
0x18000f74c  mov     [rsp+0B10h+var_AB8], r12d
0x18000f751  xorps   xmm0, xmm0
0x18000f754  xor     eax, eax
0x18000f756  movups  [rsp+0B10h+var_AB0], xmm0
0x18000f75b  movups  [rsp+0B10h+var_AA0], xmm0
0x18000f760  mov     [rbp+0A10h+var_A90], rax
0x18000f764  mov     [rbp+0A10h+var_A88], r12b
0x18000f768  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000f76d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000f772  mov     edi, eax
0x18000f774  test    eax, eax
0x18000f776  jns     short loc_18000F7A5
0x18000f778  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f77d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000f782  mov     eax, edi
0x18000f784  mov     rcx, [rbp+0A10h+var_40]
0x18000f78b  xor     rcx, rsp; StackCookie
0x18000f78e  call    __security_check_cookie
0x18000f793  add     rsp, 0AE0h
0x18000f79a  pop     r15
0x18000f79c  pop     r14
0x18000f79e  pop     r12
0x18000f7a0  pop     rdi
0x18000f7a1  pop     rsi
0x18000f7a2  pop     rbx
0x18000f7a3  pop     rbp
0x18000f7a4  retn
0x18000f7a5  test    rbx, rbx
0x18000f7a8  jz      short loc_18000F7C9
0x18000f7aa  jmp     short loc_18000F7C1
0x18000f7ac  mov     r8, [rbx+8]; unsigned __int16 *
0x18000f7b0  mov     rdx, rax; unsigned __int16 *
0x18000f7b3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f7b8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000f7bd  lea     rbx, [rbx+10h]
0x18000f7c1  mov     rax, [rbx]
0x18000f7c4  test    rax, rax
0x18000f7c7  jnz     short loc_18000F7AC
0x18000f7c9  mov     rax, [rsi]
0x18000f7cc  lea     rdx, [rsp+0B10h+var_AD0]
0x18000f7d1  mov     rcx, rsi
0x18000f7d4  mov     rax, [rax+28h]
0x18000f7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7dd  mov     ebx, eax
0x18000f7df  test    eax, eax
0x18000f7e1  js      loc_18000F915
0x18000f7e7  mov     [rsp+0B10h+var_AE0], r12
0x18000f7ec  mov     rbx, cs:hInst
0x18000f7f3  mov     edi, 104h
0x18000f7f8  mov     r8d, edi; nSize
0x18000f7fb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000f7ff  mov     rcx, rbx; hModule
0x18000f802  call    cs:__imp_GetModuleFileNameW
0x18000f808  test    eax, eax
0x18000f80a  jnz     short loc_18000F818
0x18000f80c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000f811  mov     ebx, eax
0x18000f813  jmp     loc_18000F90B
0x18000f818  cmp     eax, edi
0x18000f81a  jnz     short loc_18000F830
0x18000f81c  lea     rcx, [rsp+0B10h+var_AE0]
0x18000f821  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f826  mov     ebx, 8007007Ah
0x18000f82b  jmp     loc_18000F915
0x18000f830  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000f834  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000f83b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000f840  test    rbx, rbx
0x18000f843  jz      short loc_18000F85B
0x18000f845  xor     ecx, ecx; lpModuleName
0x18000f847  call    cs:__imp_GetModuleHandleW
0x18000f84d  cmp     rbx, rax
0x18000f850  jz      short loc_18000F85B
0x18000f852  lea     r8, [rbp+0A10h+var_450]
0x18000f859  jmp     short loc_18000F8D6
0x18000f85b  mov     ebx, 22h ; '"'
0x18000f860  mov     [rbp+0A10h+var_870], bx
0x18000f867  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000f86e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000f875  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000f87a  test    al, al
0x18000f87c  jnz     short loc_18000F892
0x18000f87e  lea     rcx, [rsp+0B10h+var_AE0]
0x18000f883  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f888  mov     ebx, 80004005h
0x18000f88d  jmp     loc_18000F915
0x18000f892  lea     rcx, [rbp+0A10h+var_870]
0x18000f899  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f89d  inc     rax
0x18000f8a0  cmp     [rcx+rax*2], r12w
0x18000f8a5  jnz     short loc_18000F89D
0x18000f8a7  cdqe
0x18000f8a9  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000f8b1  lea     rcx, ds:2[rax*2]
0x18000f8b9  cmp     rcx, 418h
0x18000f8c0  jnb     loc_18000F966
0x18000f8c6  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000f8cf  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000f8d6  lea     rdx, aModule; "Module"
0x18000f8dd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f8e2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000f8e7  mov     ebx, eax
0x18000f8e9  test    eax, eax
0x18000f8eb  js      short loc_18000F90B
0x18000f8ed  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000f8f4  lea     rdx, aModuleRaw; "Module_Raw"
0x18000f8fb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f900  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000f905  mov     ebx, eax
0x18000f907  test    eax, eax
0x18000f909  jns     short loc_18000F926
0x18000f90b  lea     rcx, [rsp+0B10h+var_AE0]
0x18000f910  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f915  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f91a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000f91f  mov     eax, ebx
0x18000f921  jmp     loc_18000F784
0x18000f926  movzx   r8d, r15w; unsigned __int16 *
0x18000f92a  mov     [rsp+0B10h+var_AD8], r12
0x18000f92f  lea     r9, aRegistry; "REGISTRY"
0x18000f936  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000f93a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000f93f  test    r14d, r14d
0x18000f942  jz      short loc_18000F94E
0x18000f944  mov     [rsp+0B10h+var_AF0], 1
0x18000f94c  jmp     short loc_18000F953
0x18000f94e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000f953  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000f958  mov     ebx, eax
0x18000f95a  lea     rcx, [rsp+0B10h+var_AD8]
0x18000f95f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f964  jmp     short loc_18000F90B
0x18000f966  call    __report_rangecheckfailure
```
