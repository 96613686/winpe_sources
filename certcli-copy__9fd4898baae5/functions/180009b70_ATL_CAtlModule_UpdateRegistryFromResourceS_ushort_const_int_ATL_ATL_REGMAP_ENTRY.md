# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009b70`
- end: `0x180009e24`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `692`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009e40`

## callees

- `0x180002078`
- `0x180004e8c`
- `0x18000527c`
- `0x1800057f0`
- `0x180006008`
- `0x180006c58`
- `0x180007494`
- `0x1800086f0`
- `0x180009b70`
- `0x180009e4c`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009c8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009c8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ccf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ccf`

## string_xrefs

- `0x180009dc6`: `REGISTRY`
- `0x180009dee`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  _OWORD *v18; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-C8h] BYREF
  void **v20; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v20 = &ATL::CRegObject::`vftable';
  v19 = v21;
  v21[0] = 0;
  v21[1] = 0;
  v22 = 0;
  v18 = v23;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v23);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)&v20,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v20);
  if ( Error >= 0 )
  {
    v18 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
      Error = -2147024774;
      goto LABEL_24;
    }
    ATL::CAtlModule::EscapeSingleQuote(v29, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v14, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
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
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v20, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v20, L"Module_Raw", v29);
    if ( Error < 0 )
      goto LABEL_23;
    v19 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v20, Filename, a2, L"REGISTRY", 1);
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        goto LABEL_23;
      }
    }
    else if ( a2 )
    {
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v20, Filename, a2, L"REGISTRY", 0);
      goto LABEL_32;
    }
    Error = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180009b70  push    rbp
0x180009b72  push    rbx
0x180009b73  push    rsi
0x180009b74  push    rdi
0x180009b75  push    r12
0x180009b77  push    r14
0x180009b79  push    r15
0x180009b7b  lea     rbp, [rsp-9E0h]
0x180009b83  sub     rsp, 0AE0h
0x180009b8a  mov     rax, cs:__security_cookie
0x180009b91  xor     rax, rsp
0x180009b94  mov     [rbp+0A10h+var_40], rax
0x180009b9b  mov     rbx, r9
0x180009b9e  mov     r15d, r8d
0x180009ba1  mov     rdi, rdx
0x180009ba4  mov     r14, rcx
0x180009ba7  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009bae  mov     [rsp+0B10h+var_AD0], rax
0x180009bb3  lea     rax, [rsp+0B10h+var_AC8]
0x180009bb8  mov     [rsp+0B10h+var_AD8], rax
0x180009bbd  xor     r12d, r12d
0x180009bc0  mov     [rsp+0B10h+var_AC8], r12
0x180009bc5  mov     [rsp+0B10h+var_AC0], r12
0x180009bca  mov     [rsp+0B10h+var_AB8], r12d
0x180009bcf  lea     rax, [rsp+0B10h+var_AB0]
0x180009bd4  mov     [rsp+0B10h+var_AE0], rax
0x180009bd9  xorps   xmm0, xmm0
0x180009bdc  xor     eax, eax
0x180009bde  movups  [rsp+0B10h+var_AB0], xmm0
0x180009be3  movups  [rsp+0B10h+var_AA0], xmm0
0x180009be8  mov     [rbp+0A10h+var_A90], rax
0x180009bec  mov     [rbp+0A10h+var_A88], r12b
0x180009bf0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180009bf5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009bfa  mov     esi, eax
0x180009bfc  test    eax, eax
0x180009bfe  jns     short loc_180009C2D
0x180009c00  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009c05  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009c0a  mov     eax, esi
0x180009c0c  mov     rcx, [rbp+0A10h+var_40]
0x180009c13  xor     rcx, rsp; StackCookie
0x180009c16  call    __security_check_cookie
0x180009c1b  add     rsp, 0AE0h
0x180009c22  pop     r15
0x180009c24  pop     r14
0x180009c26  pop     r12
0x180009c28  pop     rdi
0x180009c29  pop     rsi
0x180009c2a  pop     rbx
0x180009c2b  pop     rbp
0x180009c2c  retn
0x180009c2d  test    rbx, rbx
0x180009c30  jz      short loc_180009C51
0x180009c32  jmp     short loc_180009C49
0x180009c34  mov     r8, [rbx+8]; unsigned __int16 *
0x180009c38  mov     rdx, rax; unsigned __int16 *
0x180009c3b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009c40  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009c45  lea     rbx, [rbx+10h]
0x180009c49  mov     rax, [rbx]
0x180009c4c  test    rax, rax
0x180009c4f  jnz     short loc_180009C34
0x180009c51  mov     rax, [r14]
0x180009c54  lea     rdx, [rsp+0B10h+var_AD0]
0x180009c59  mov     rcx, r14
0x180009c5c  mov     rax, [rax+28h]
0x180009c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c65  mov     ebx, eax
0x180009c67  test    eax, eax
0x180009c69  js      loc_180009D9E
0x180009c6f  mov     [rsp+0B10h+var_AE0], r12
0x180009c74  mov     rbx, cs:hModule
0x180009c7b  mov     esi, 104h
0x180009c80  mov     r8d, esi; nSize
0x180009c83  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180009c87  mov     rcx, rbx; hModule
0x180009c8a  call    cs:__imp_GetModuleFileNameW
0x180009c90  test    eax, eax
0x180009c92  jnz     short loc_180009CA0
0x180009c94  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009c99  mov     ebx, eax
0x180009c9b  jmp     loc_180009D93
0x180009ca0  cmp     eax, esi
0x180009ca2  jnz     short loc_180009CB8
0x180009ca4  lea     rcx, [rsp+0B10h+var_AE0]
0x180009ca9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009cae  mov     ebx, 8007007Ah
0x180009cb3  jmp     loc_180009D9E
0x180009cb8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009cbc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009cc3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180009cc8  test    rbx, rbx
0x180009ccb  jz      short loc_180009CE3
0x180009ccd  xor     ecx, ecx; lpModuleName
0x180009ccf  call    cs:__imp_GetModuleHandleW
0x180009cd5  cmp     rbx, rax
0x180009cd8  jz      short loc_180009CE3
0x180009cda  lea     r8, [rbp+0A10h+var_450]
0x180009ce1  jmp     short loc_180009D5E
0x180009ce3  mov     ebx, 22h ; '"'
0x180009ce8  mov     [rbp+0A10h+var_870], bx
0x180009cef  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009cf6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180009cfd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180009d02  test    al, al
0x180009d04  jnz     short loc_180009D1A
0x180009d06  lea     rcx, [rsp+0B10h+var_AE0]
0x180009d0b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009d10  mov     ebx, 80004005h
0x180009d15  jmp     loc_180009D9E
0x180009d1a  lea     rcx, [rbp+0A10h+var_870]
0x180009d21  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d25  inc     rax
0x180009d28  cmp     [rcx+rax*2], r12w
0x180009d2d  jnz     short loc_180009D25
0x180009d2f  cdqe
0x180009d31  mov     [rbp+rax*2+0A10h+var_870], bx
0x180009d39  lea     rcx, ds:2[rax*2]
0x180009d41  cmp     rcx, 418h
0x180009d48  jnb     loc_180009E1E
0x180009d4e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180009d57  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180009d5e  lea     rdx, aModule; "Module"
0x180009d65  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009d6a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009d6f  mov     ebx, eax
0x180009d71  test    eax, eax
0x180009d73  js      short loc_180009D93
0x180009d75  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009d7c  lea     rdx, aModuleRaw; "Module_Raw"
0x180009d83  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009d88  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009d8d  mov     ebx, eax
0x180009d8f  test    eax, eax
0x180009d91  jns     short loc_180009DAF
0x180009d93  lea     rcx, [rsp+0B10h+var_AE0]
0x180009d98  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009d9d  nop
0x180009d9e  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009da3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009da8  mov     eax, ebx
0x180009daa  jmp     loc_180009C0C
0x180009daf  mov     [rsp+0B10h+var_AD8], r12
0x180009db4  test    r15d, r15d
0x180009db7  jz      short loc_180009DE4
0x180009db9  test    rdi, rdi
0x180009dbc  jz      short loc_180009DE2
0x180009dbe  mov     [rsp+0B10h+var_AF0], 1; int
0x180009dc6  lea     r9, aRegistry; "REGISTRY"
0x180009dcd  mov     r8, rdi; unsigned __int16 *
0x180009dd0  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009dd4  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009dd9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009dde  mov     ebx, eax
0x180009de0  jmp     short loc_180009E0F
0x180009de2  jmp     short loc_180009E0A
0x180009de4  test    rdi, rdi
0x180009de7  jz      short loc_180009E0A
0x180009de9  mov     [rsp+0B10h+var_AF0], r12d; int
0x180009dee  lea     r9, aRegistry; "REGISTRY"
0x180009df5  mov     r8, rdi; unsigned __int16 *
0x180009df8  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009dfc  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009e01  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009e06  mov     ebx, eax
0x180009e08  jmp     short loc_180009E0F
0x180009e0a  mov     ebx, 80070057h
0x180009e0f  lea     rcx, [rsp+0B10h+var_AD8]
0x180009e14  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009e19  jmp     loc_180009D93
0x180009e1e  call    __report_rangecheckfailure
```
