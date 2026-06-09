# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009c34`
- end: `0x180009eb4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009ed0`

## callees

- `0x180001d98`
- `0x180006688`
- `0x180006890`
- `0x180006d80`
- `0x1800075e0`
- `0x18000802c`
- `0x180008324`
- `0x180008c20`
- `0x180009c34`
- `0x180009edc`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009d3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009d3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d7f`

## string_xrefs

- `0x180009e81`: `REGISTRY`

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
0x180009c34  push    rbp
0x180009c36  push    rbx
0x180009c37  push    rsi
0x180009c38  push    rdi
0x180009c39  push    r12
0x180009c3b  push    r14
0x180009c3d  push    r15
0x180009c3f  lea     rbp, [rsp-9E0h]
0x180009c47  sub     rsp, 0AE0h
0x180009c4e  mov     rax, cs:__security_cookie
0x180009c55  xor     rax, rsp
0x180009c58  mov     [rbp+0A10h+var_40], rax
0x180009c5f  mov     rbx, r9
0x180009c62  mov     r15d, r8d
0x180009c65  mov     rdi, rdx
0x180009c68  mov     r14, rcx
0x180009c6b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009c72  mov     [rsp+0B10h+var_AD0], rax
0x180009c77  xor     r12d, r12d
0x180009c7a  mov     [rsp+0B10h+var_AC8], r12
0x180009c7f  mov     [rsp+0B10h+var_AC0], r12
0x180009c84  mov     [rsp+0B10h+var_AB8], r12d
0x180009c89  xorps   xmm0, xmm0
0x180009c8c  xor     eax, eax
0x180009c8e  movups  [rsp+0B10h+var_AB0], xmm0
0x180009c93  movups  [rsp+0B10h+var_AA0], xmm0
0x180009c98  mov     [rbp+0A10h+var_A90], rax
0x180009c9c  mov     [rbp+0A10h+var_A88], r12b
0x180009ca0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180009ca5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009caa  mov     esi, eax
0x180009cac  test    eax, eax
0x180009cae  jns     short loc_180009CDD
0x180009cb0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009cb5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009cba  mov     eax, esi
0x180009cbc  mov     rcx, [rbp+0A10h+var_40]
0x180009cc3  xor     rcx, rsp; StackCookie
0x180009cc6  call    __security_check_cookie
0x180009ccb  add     rsp, 0AE0h
0x180009cd2  pop     r15
0x180009cd4  pop     r14
0x180009cd6  pop     r12
0x180009cd8  pop     rdi
0x180009cd9  pop     rsi
0x180009cda  pop     rbx
0x180009cdb  pop     rbp
0x180009cdc  retn
0x180009cdd  test    rbx, rbx
0x180009ce0  jz      short loc_180009D01
0x180009ce2  jmp     short loc_180009CF9
0x180009ce4  mov     r8, [rbx+8]; unsigned __int16 *
0x180009ce8  mov     rdx, rax; unsigned __int16 *
0x180009ceb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009cf0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009cf5  lea     rbx, [rbx+10h]
0x180009cf9  mov     rax, [rbx]
0x180009cfc  test    rax, rax
0x180009cff  jnz     short loc_180009CE4
0x180009d01  mov     rax, [r14]
0x180009d04  lea     rdx, [rsp+0B10h+var_AD0]
0x180009d09  mov     rcx, r14
0x180009d0c  mov     rax, [rax+28h]
0x180009d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d15  mov     ebx, eax
0x180009d17  test    eax, eax
0x180009d19  js      loc_180009E4D
0x180009d1f  mov     [rsp+0B10h+var_AE0], r12
0x180009d24  mov     rbx, cs:hModule
0x180009d2b  mov     esi, 104h
0x180009d30  mov     r8d, esi; nSize
0x180009d33  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180009d37  mov     rcx, rbx; hModule
0x180009d3a  call    cs:__imp_GetModuleFileNameW
0x180009d40  test    eax, eax
0x180009d42  jnz     short loc_180009D50
0x180009d44  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009d49  mov     ebx, eax
0x180009d4b  jmp     loc_180009E43
0x180009d50  cmp     eax, esi
0x180009d52  jnz     short loc_180009D68
0x180009d54  lea     rcx, [rsp+0B10h+var_AE0]
0x180009d59  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009d5e  mov     ebx, 8007007Ah
0x180009d63  jmp     loc_180009E4D
0x180009d68  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009d6c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009d73  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180009d78  test    rbx, rbx
0x180009d7b  jz      short loc_180009D93
0x180009d7d  xor     ecx, ecx; lpModuleName
0x180009d7f  call    cs:__imp_GetModuleHandleW
0x180009d85  cmp     rbx, rax
0x180009d88  jz      short loc_180009D93
0x180009d8a  lea     r8, [rbp+0A10h+var_450]
0x180009d91  jmp     short loc_180009E0E
0x180009d93  mov     ebx, 22h ; '"'
0x180009d98  mov     [rbp+0A10h+var_870], bx
0x180009d9f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009da6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180009dad  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180009db2  test    al, al
0x180009db4  jnz     short loc_180009DCA
0x180009db6  lea     rcx, [rsp+0B10h+var_AE0]
0x180009dbb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009dc0  mov     ebx, 80004005h
0x180009dc5  jmp     loc_180009E4D
0x180009dca  lea     rcx, [rbp+0A10h+var_870]
0x180009dd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009dd5  inc     rax
0x180009dd8  cmp     [rcx+rax*2], r12w
0x180009ddd  jnz     short loc_180009DD5
0x180009ddf  cdqe
0x180009de1  mov     [rbp+rax*2+0A10h+var_870], bx
0x180009de9  lea     rcx, ds:2[rax*2]
0x180009df1  cmp     rcx, 418h
0x180009df8  jnb     loc_180009EAE
0x180009dfe  mov     [rbp+rcx+0A10h+var_870], r12w
0x180009e07  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180009e0e  lea     rdx, aModule; "Module"
0x180009e15  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009e1a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009e1f  mov     ebx, eax
0x180009e21  test    eax, eax
0x180009e23  js      short loc_180009E43
0x180009e25  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009e2c  lea     rdx, aModuleRaw; "Module_Raw"
0x180009e33  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009e38  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009e3d  mov     ebx, eax
0x180009e3f  test    eax, eax
0x180009e41  jns     short loc_180009E5E
0x180009e43  lea     rcx, [rsp+0B10h+var_AE0]
0x180009e48  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009e4d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009e52  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009e57  mov     eax, ebx
0x180009e59  jmp     loc_180009CBC
0x180009e5e  mov     [rsp+0B10h+var_AD8], r12
0x180009e63  test    r15d, r15d
0x180009e66  jz      short loc_180009E77
0x180009e68  test    rdi, rdi
0x180009e6b  jz      short loc_180009E9D
0x180009e6d  mov     [rsp+0B10h+var_AF0], 1
0x180009e75  jmp     short loc_180009E81
0x180009e77  test    rdi, rdi
0x180009e7a  jz      short loc_180009E9D
0x180009e7c  mov     [rsp+0B10h+var_AF0], r12d; int
0x180009e81  lea     r9, aRegistry; "REGISTRY"
0x180009e88  mov     r8, rdi; unsigned __int16 *
0x180009e8b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009e8f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009e94  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009e99  mov     ebx, eax
0x180009e9b  jmp     short loc_180009EA2
0x180009e9d  mov     ebx, 80070057h
0x180009ea2  lea     rcx, [rsp+0B10h+var_AD8]
0x180009ea7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009eac  jmp     short loc_180009E43
0x180009eae  call    __report_rangecheckfailure
```
