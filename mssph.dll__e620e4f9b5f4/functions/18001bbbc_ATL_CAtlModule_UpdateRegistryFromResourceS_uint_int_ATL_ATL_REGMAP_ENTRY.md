# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001bbbc`
- end: `0x18001be2c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c0c0`

## callees

- `0x180005eb0`
- `0x18000a630`
- `0x18000fcd0`
- `0x180010210`
- `0x180016634`
- `0x180016808`
- `0x180016d80`
- `0x180017eec`
- `0x18001a58c`
- `0x18001bbbc`
- `0x18001c8b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bcc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bcc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bd07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bd07`

## string_xrefs

- `0x18001bdef`: `REGISTRY`

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
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
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
0x18001bbbc  push    rbp
0x18001bbbe  push    rbx
0x18001bbbf  push    rsi
0x18001bbc0  push    rdi
0x18001bbc1  push    r12
0x18001bbc3  push    r14
0x18001bbc5  push    r15
0x18001bbc7  lea     rbp, [rsp-9E0h]
0x18001bbcf  sub     rsp, 0AE0h
0x18001bbd6  mov     rax, cs:__security_cookie
0x18001bbdd  xor     rax, rsp
0x18001bbe0  mov     [rbp+0A10h+var_40], rax
0x18001bbe7  mov     rbx, r9
0x18001bbea  mov     r14d, r8d
0x18001bbed  mov     r15d, edx
0x18001bbf0  mov     rsi, rcx
0x18001bbf3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001bbfa  mov     [rsp+0B10h+var_AD0], rax
0x18001bbff  xor     r12d, r12d
0x18001bc02  mov     [rsp+0B10h+var_AC8], r12
0x18001bc07  mov     [rsp+0B10h+var_AC0], r12
0x18001bc0c  mov     [rsp+0B10h+var_AB8], r12d
0x18001bc11  xorps   xmm0, xmm0
0x18001bc14  xor     eax, eax
0x18001bc16  movups  [rsp+0B10h+var_AB0], xmm0
0x18001bc1b  movups  [rsp+0B10h+var_AA0], xmm0
0x18001bc20  mov     [rbp+0A10h+var_A90], rax
0x18001bc24  mov     [rbp+0A10h+var_A88], r12b
0x18001bc28  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001bc2d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001bc32  mov     edi, eax
0x18001bc34  test    eax, eax
0x18001bc36  jns     short loc_18001BC65
0x18001bc38  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bc3d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001bc42  mov     eax, edi
0x18001bc44  mov     rcx, [rbp+0A10h+var_40]
0x18001bc4b  xor     rcx, rsp; StackCookie
0x18001bc4e  call    __security_check_cookie
0x18001bc53  add     rsp, 0AE0h
0x18001bc5a  pop     r15
0x18001bc5c  pop     r14
0x18001bc5e  pop     r12
0x18001bc60  pop     rdi
0x18001bc61  pop     rsi
0x18001bc62  pop     rbx
0x18001bc63  pop     rbp
0x18001bc64  retn
0x18001bc65  test    rbx, rbx
0x18001bc68  jz      short loc_18001BC89
0x18001bc6a  jmp     short loc_18001BC81
0x18001bc6c  mov     r8, [rbx+8]; wchar_t *
0x18001bc70  mov     rdx, rax; wchar_t *
0x18001bc73  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bc78  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001bc7d  lea     rbx, [rbx+10h]
0x18001bc81  mov     rax, [rbx]
0x18001bc84  test    rax, rax
0x18001bc87  jnz     short loc_18001BC6C
0x18001bc89  mov     rax, [rsi]
0x18001bc8c  lea     rdx, [rsp+0B10h+var_AD0]
0x18001bc91  mov     rcx, rsi
0x18001bc94  mov     rax, [rax+28h]
0x18001bc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc9d  mov     ebx, eax
0x18001bc9f  test    eax, eax
0x18001bca1  js      loc_18001BDD5
0x18001bca7  mov     [rsp+0B10h+var_AE0], r12
0x18001bcac  mov     rbx, cs:hModule
0x18001bcb3  mov     edi, 104h
0x18001bcb8  mov     r8d, edi; nSize
0x18001bcbb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001bcbf  mov     rcx, rbx; hModule
0x18001bcc2  call    cs:__imp_GetModuleFileNameW
0x18001bcc8  test    eax, eax
0x18001bcca  jnz     short loc_18001BCD8
0x18001bccc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001bcd1  mov     ebx, eax
0x18001bcd3  jmp     loc_18001BDCB
0x18001bcd8  cmp     eax, edi
0x18001bcda  jnz     short loc_18001BCF0
0x18001bcdc  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bce1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bce6  mov     ebx, 8007007Ah
0x18001bceb  jmp     loc_18001BDD5
0x18001bcf0  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18001bcf4  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18001bcfb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x18001bd00  test    rbx, rbx
0x18001bd03  jz      short loc_18001BD1B
0x18001bd05  xor     ecx, ecx; lpModuleName
0x18001bd07  call    cs:__imp_GetModuleHandleW
0x18001bd0d  cmp     rbx, rax
0x18001bd10  jz      short loc_18001BD1B
0x18001bd12  lea     r8, [rbp+0A10h+var_450]
0x18001bd19  jmp     short loc_18001BD96
0x18001bd1b  mov     ebx, 22h ; '"'
0x18001bd20  mov     [rbp+0A10h+var_870], bx
0x18001bd27  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18001bd2e  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18001bd35  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x18001bd3a  test    al, al
0x18001bd3c  jnz     short loc_18001BD52
0x18001bd3e  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bd43  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bd48  mov     ebx, 80004005h
0x18001bd4d  jmp     loc_18001BDD5
0x18001bd52  lea     rcx, [rbp+0A10h+var_870]
0x18001bd59  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bd5d  inc     rax
0x18001bd60  cmp     [rcx+rax*2], r12w
0x18001bd65  jnz     short loc_18001BD5D
0x18001bd67  cdqe
0x18001bd69  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001bd71  lea     rcx, ds:2[rax*2]
0x18001bd79  cmp     rcx, 418h
0x18001bd80  jnb     loc_18001BE26
0x18001bd86  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001bd8f  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18001bd96  lea     rdx, aModule; "Module"
0x18001bd9d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bda2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001bda7  mov     ebx, eax
0x18001bda9  test    eax, eax
0x18001bdab  js      short loc_18001BDCB
0x18001bdad  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18001bdb4  lea     rdx, aModuleRaw; "Module_Raw"
0x18001bdbb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bdc0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18001bdc5  mov     ebx, eax
0x18001bdc7  test    eax, eax
0x18001bdc9  jns     short loc_18001BDE6
0x18001bdcb  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bdd0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bdd5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bdda  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001bddf  mov     eax, ebx
0x18001bde1  jmp     loc_18001BC44
0x18001bde6  movzx   r8d, r15w; wchar_t *
0x18001bdea  mov     [rsp+0B10h+var_AD8], r12
0x18001bdef  lea     r9, aRegistry; "REGISTRY"
0x18001bdf6  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18001bdfa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bdff  test    r14d, r14d
0x18001be02  jz      short loc_18001BE0E
0x18001be04  mov     [rsp+0B10h+var_AF0], 1
0x18001be0c  jmp     short loc_18001BE13
0x18001be0e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001be13  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18001be18  mov     ebx, eax
0x18001be1a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001be1f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001be24  jmp     short loc_18001BDCB
0x18001be26  call    __report_rangecheckfailure
```
