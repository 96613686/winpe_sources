# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180010e14`
- end: `0x180011091`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `637`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f804`
- `0x18000f8a4`
- `0x18002b6f0`

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
- `0x180010e14`
- `0x1800110b4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010f66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010f66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010f1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010f1b`

## string_xrefs

- `0x180011054`: `REGISTRY`

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
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
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
0x180010e14  push    rbp
0x180010e16  push    rbx
0x180010e17  push    rsi
0x180010e18  push    rdi
0x180010e19  push    r12
0x180010e1b  push    r14
0x180010e1d  push    r15
0x180010e1f  lea     rbp, [rsp-9E0h]
0x180010e27  sub     rsp, 0AE0h
0x180010e2e  mov     rax, cs:__security_cookie
0x180010e35  xor     rax, rsp
0x180010e38  mov     [rbp+0A10h+var_40], rax
0x180010e3f  mov     rbx, r9
0x180010e42  mov     r14d, r8d
0x180010e45  mov     r15d, edx
0x180010e48  mov     rsi, rcx
0x180010e4b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180010e52  mov     [rsp+0B10h+var_AD0], rax
0x180010e57  xor     r12d, r12d
0x180010e5a  mov     [rsp+0B10h+var_AC8], r12
0x180010e5f  mov     [rsp+0B10h+var_AC0], r12
0x180010e64  mov     [rsp+0B10h+var_AB8], r12d
0x180010e69  xorps   xmm0, xmm0
0x180010e6c  xor     eax, eax
0x180010e6e  movups  [rsp+0B10h+var_AB0], xmm0
0x180010e73  movups  [rsp+0B10h+var_AA0], xmm0
0x180010e78  mov     [rbp+0A10h+var_A90], rax
0x180010e7c  mov     [rbp+0A10h+var_A88], r12b
0x180010e80  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180010e85  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180010e8a  mov     edi, eax
0x180010e8c  test    eax, eax
0x180010e8e  jns     short loc_180010EBE
0x180010e90  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010e95  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180010e9a  mov     eax, edi
0x180010e9c  mov     rcx, [rbp+0A10h+var_40]
0x180010ea3  xor     rcx, rsp; StackCookie
0x180010ea6  call    __security_check_cookie
0x180010eab  add     rsp, 0AE0h
0x180010eb2  pop     r15
0x180010eb4  pop     r14
0x180010eb6  pop     r12
0x180010eb8  pop     rdi
0x180010eb9  pop     rsi
0x180010eba  pop     rbx
0x180010ebb  pop     rbp
0x180010ebc  retn
0x180010ebe  test    rbx, rbx
0x180010ec1  jz      short loc_180010EE2
0x180010ec3  jmp     short loc_180010EDA
0x180010ec5  mov     r8, [rbx+8]; wchar_t *
0x180010ec9  mov     rdx, rax; wchar_t *
0x180010ecc  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010ed1  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180010ed6  lea     rbx, [rbx+10h]
0x180010eda  mov     rax, [rbx]
0x180010edd  test    rax, rax
0x180010ee0  jnz     short loc_180010EC5
0x180010ee2  mov     rax, [rsi]
0x180010ee5  lea     rdx, [rsp+0B10h+var_AD0]
0x180010eea  mov     rcx, rsi
0x180010eed  mov     rax, [rax+28h]
0x180010ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef6  mov     ebx, eax
0x180010ef8  test    eax, eax
0x180010efa  js      loc_18001103A
0x180010f00  mov     [rsp+0B10h+var_AE0], r12
0x180010f05  mov     rbx, cs:hModule
0x180010f0c  mov     edi, 104h
0x180010f11  mov     r8d, edi; nSize
0x180010f14  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180010f18  mov     rcx, rbx; hModule
0x180010f1b  call    cs:__imp_GetModuleFileNameW
0x180010f22  nop     dword ptr [rax+rax+00h]
0x180010f27  test    eax, eax
0x180010f29  jnz     short loc_180010F37
0x180010f2b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010f30  mov     ebx, eax
0x180010f32  jmp     loc_180011030
0x180010f37  cmp     eax, edi
0x180010f39  jnz     short loc_180010F4F
0x180010f3b  lea     rcx, [rsp+0B10h+var_AE0]
0x180010f40  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010f45  mov     ebx, 8007007Ah
0x180010f4a  jmp     loc_18001103A
0x180010f4f  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x180010f53  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x180010f5a  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x180010f5f  test    rbx, rbx
0x180010f62  jz      short loc_180010F80
0x180010f64  xor     ecx, ecx; lpModuleName
0x180010f66  call    cs:__imp_GetModuleHandleW
0x180010f6d  nop     dword ptr [rax+rax+00h]
0x180010f72  cmp     rbx, rax
0x180010f75  jz      short loc_180010F80
0x180010f77  lea     r8, [rbp+0A10h+var_450]
0x180010f7e  jmp     short loc_180010FFB
0x180010f80  mov     ebx, 22h ; '"'
0x180010f85  mov     [rbp+0A10h+var_870], bx
0x180010f8c  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x180010f93  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x180010f9a  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x180010f9f  test    al, al
0x180010fa1  jnz     short loc_180010FB7
0x180010fa3  lea     rcx, [rsp+0B10h+var_AE0]
0x180010fa8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010fad  mov     ebx, 80004005h
0x180010fb2  jmp     loc_18001103A
0x180010fb7  lea     rcx, [rbp+0A10h+var_870]
0x180010fbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010fc2  inc     rax
0x180010fc5  cmp     [rcx+rax*2], r12w
0x180010fca  jnz     short loc_180010FC2
0x180010fcc  cdqe
0x180010fce  mov     [rbp+rax*2+0A10h+var_870], bx
0x180010fd6  lea     rcx, ds:2[rax*2]
0x180010fde  cmp     rcx, 418h
0x180010fe5  jnb     loc_18001108B
0x180010feb  mov     [rbp+rcx+0A10h+var_870], r12w
0x180010ff4  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x180010ffb  lea     rdx, aModule_0; "Module"
0x180011002  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180011007  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001100c  mov     ebx, eax
0x18001100e  test    eax, eax
0x180011010  js      short loc_180011030
0x180011012  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x180011019  lea     rdx, aModuleRaw; "Module_Raw"
0x180011020  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180011025  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001102a  mov     ebx, eax
0x18001102c  test    eax, eax
0x18001102e  jns     short loc_18001104B
0x180011030  lea     rcx, [rsp+0B10h+var_AE0]
0x180011035  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001103a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001103f  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180011044  mov     eax, ebx
0x180011046  jmp     loc_180010E9C
0x18001104b  movzx   r8d, r15w; wchar_t *
0x18001104f  mov     [rsp+0B10h+var_AD8], r12
0x180011054  lea     r9, aRegistry; "REGISTRY"
0x18001105b  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18001105f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180011064  test    r14d, r14d
0x180011067  jz      short loc_180011073
0x180011069  mov     [rsp+0B10h+var_AF0], 1
0x180011071  jmp     short loc_180011078
0x180011073  mov     [rsp+0B10h+var_AF0], r12d; int
0x180011078  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18001107d  mov     ebx, eax
0x18001107f  lea     rcx, [rsp+0B10h+var_AD8]
0x180011084  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011089  jmp     short loc_180011030
0x18001108b  call    __report_rangecheckfailure
```
