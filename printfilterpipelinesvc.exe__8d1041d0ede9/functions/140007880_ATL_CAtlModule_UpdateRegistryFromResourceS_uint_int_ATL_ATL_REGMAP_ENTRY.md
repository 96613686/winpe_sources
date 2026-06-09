# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140007880`
- end: `0x140007b1d`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `669`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007870`

## callees

- `0x140002070`
- `0x1400021c0`
- `0x140004528`
- `0x140004678`
- `0x140004b20`
- `0x140005358`
- `0x140005d64`
- `0x140006940`
- `0x140007880`
- `0x140007f20`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400079be`
- `KERNEL32!GetModuleHandleW` at `0x1400079be`
- `KERNEL32!GetModuleFileNameW` at `0x14000793c`
- `KERNEL32!GetModuleFileNameW` at `0x14000793c`

## string_xrefs

- `0x140007aab`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v5; // rdi
  int LastErrorAsHResult; // ebx
  HMODULE v8; // rbx
  DWORD ModuleFileNameW; // eax
  NCoreLibrary *v10; // rcx
  WCHAR *v11; // rdx
  __int64 v12; // rcx
  wchar_t v13; // r8
  wchar_t *v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  const wchar_t *v18; // r8
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  _OWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  char v26; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Source[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t v29; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE Destination[1054]; // [rsp+6B2h] [rbp+5B2h] BYREF

  v5 = ATL::_pAtlModule;
  v22[0] = &ATL::CRegObject::`vftable';
  v22[1] = 0;
  v22[2] = 0;
  v23 = 0;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 0;
  LastErrorAsHResult = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v24);
  if ( LastErrorAsHResult < 0 )
    goto LABEL_2;
  LastErrorAsHResult = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, _QWORD *))(*(_QWORD *)v5 + 40LL))(v5, v22);
  if ( LastErrorAsHResult < 0 )
    goto LABEL_2;
  v20 = 0;
  v8 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v10);
LABEL_25:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
    goto LABEL_2;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
    LastErrorAsHResult = -2147024774;
LABEL_2:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v22);
    return (unsigned int)LastErrorAsHResult;
  }
  v11 = Filename;
  v12 = 0;
  do
  {
    v13 = *v11;
    if ( !*v11 )
      break;
    Source[v12] = v13;
    if ( v13 == 39 && (unsigned int)v12 < 0x206 )
    {
      LODWORD(v12) = v12 + 1;
      Source[(unsigned int)v12] = 39;
    }
    ++v11;
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (unsigned int)v12 < 0x207 );
  Source[v12] = 0;
  if ( v8 && v8 != GetModuleHandleW(0) )
  {
    v14 = Source;
LABEL_23:
    LastErrorAsHResult = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v22, L"Module", v14);
    if ( LastErrorAsHResult >= 0 )
    {
      LastErrorAsHResult = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v22, L"Module_Raw", Source);
      if ( LastErrorAsHResult >= 0 )
      {
        v21 = 0;
        if ( a3 )
          v19 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v22, Filename, v18, L"REGISTRY", 1);
        else
          v19 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v22, Filename, v18, L"REGISTRY", 0);
        LastErrorAsHResult = v19;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
      }
    }
    goto LABEL_25;
  }
  v29 = 34;
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( Source[v16] );
  if ( !memcpy_s_0(Destination, 0x414u, Source, 2LL * ((int)v16 + 1)) )
  {
    do
      ++v15;
    while ( *(_WORD *)&Destination[2 * v15 - 2] );
    *(_WORD *)&Destination[2 * (int)v15 - 2] = 34;
    v17 = 2LL * (int)v15 + 2;
    if ( v17 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v17 - 2] = 0;
    v14 = &v29;
    goto LABEL_23;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v22);
  return 2147500037LL;
}

```

## disassembly

```asm
0x140007880  push    rbp
0x140007882  push    rbx
0x140007883  push    rsi
0x140007884  push    rdi
0x140007885  push    r14
0x140007887  lea     rbp, [rsp-9E0h]
0x14000788f  sub     rsp, 0AE0h
0x140007896  mov     rax, cs:__security_cookie
0x14000789d  xor     rax, rsp
0x1400078a0  mov     [rbp+0A00h+var_30], rax
0x1400078a7  mov     esi, r8d
0x1400078aa  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400078b1  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1400078b8  mov     [rsp+0B00h+var_AC0], rax
0x1400078bd  xor     r14d, r14d
0x1400078c0  mov     [rsp+0B00h+var_AB8], r14
0x1400078c5  mov     [rsp+0B00h+var_AB0], r14
0x1400078ca  mov     [rsp+0B00h+var_AA8], r14d
0x1400078cf  xorps   xmm0, xmm0
0x1400078d2  xor     eax, eax
0x1400078d4  movups  [rsp+0B00h+var_AA0], xmm0
0x1400078d9  movups  [rsp+0B00h+var_A90], xmm0
0x1400078de  mov     [rbp+0A00h+var_A80], rax
0x1400078e2  mov     [rbp+0A00h+var_A78], r14b
0x1400078e6  lea     rcx, [rsp+0B00h+var_AA0]; this
0x1400078eb  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1400078f0  mov     ebx, eax
0x1400078f2  test    eax, eax
0x1400078f4  jns     short loc_140007907
0x1400078f6  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1400078fb  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140007900  mov     eax, ebx
0x140007902  jmp     loc_140007B00
0x140007907  mov     rax, [rdi]
0x14000790a  lea     rdx, [rsp+0B00h+var_AC0]
0x14000790f  mov     rcx, rdi
0x140007912  mov     rax, [rax+28h]
0x140007916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000791b  mov     ebx, eax
0x14000791d  test    eax, eax
0x14000791f  js      short loc_1400078F6
0x140007921  mov     [rsp+0B00h+var_AD0], r14
0x140007926  mov     rbx, cs:hModule
0x14000792d  mov     edi, 104h
0x140007932  mov     r8d, edi; nSize
0x140007935  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x140007939  mov     rcx, rbx; hModule
0x14000793c  call    cs:__imp_GetModuleFileNameW
0x140007942  test    eax, eax
0x140007944  jnz     short loc_140007952
0x140007946  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000794b  mov     ebx, eax
0x14000794d  jmp     loc_140007A97
0x140007952  cmp     eax, edi
0x140007954  jnz     short loc_140007967
0x140007956  lea     rcx, [rsp+0B00h+var_AD0]
0x14000795b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140007960  mov     ebx, 8007007Ah
0x140007965  jmp     short loc_1400078F6
0x140007967  lea     rdx, [rbp+0A00h+Filename]
0x14000796b  mov     ecx, r14d
0x14000796e  mov     r9d, 27h ; '''
0x140007974  movzx   r8d, word ptr [rdx]
0x140007978  test    r8w, r8w
0x14000797c  jz      short loc_1400079AE
0x14000797e  mov     [rbp+rcx*2+0A00h+Source], r8w
0x140007987  cmp     r8w, r9w
0x14000798b  jnz     short loc_1400079A0
0x14000798d  cmp     ecx, 206h
0x140007993  jnb     short loc_1400079A0
0x140007995  inc     ecx
0x140007997  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1400079a0  add     rdx, 2
0x1400079a4  inc     ecx
0x1400079a6  cmp     ecx, 207h
0x1400079ac  jb      short loc_140007974
0x1400079ae  mov     [rbp+rcx*2+0A00h+Source], r14w
0x1400079b7  test    rbx, rbx
0x1400079ba  jz      short loc_1400079D5
0x1400079bc  xor     ecx, ecx; lpModuleName
0x1400079be  call    cs:__imp_GetModuleHandleW
0x1400079c4  cmp     rbx, rax
0x1400079c7  jz      short loc_1400079D5
0x1400079c9  lea     r8, [rbp+0A00h+Source]
0x1400079d0  jmp     loc_140007A62
0x1400079d5  mov     edi, 22h ; '"'
0x1400079da  mov     [rbp+0A00h+var_450], di
0x1400079e1  lea     rcx, [rbp+0A00h+Source]
0x1400079e8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400079ec  mov     rax, rbx
0x1400079ef  inc     rax
0x1400079f2  cmp     [rcx+rax*2], r14w
0x1400079f7  jnz     short loc_1400079EF
0x1400079f9  inc     eax
0x1400079fb  movsxd  r9, eax
0x1400079fe  add     r9, r9; SourceSize
0x140007a01  lea     r8, [rbp+0A00h+Source]; Source
0x140007a08  mov     edx, 414h; DestinationSize
0x140007a0d  lea     rcx, [rbp+0A00h+Destination]; Destination
0x140007a14  call    memcpy_s_0
0x140007a19  test    eax, eax
0x140007a1b  jnz     loc_140007AE7
0x140007a21  lea     rax, [rbp+0A00h+var_450]
0x140007a28  inc     rbx
0x140007a2b  cmp     [rax+rbx*2], r14w
0x140007a30  jnz     short loc_140007A28
0x140007a32  movsxd  rax, ebx
0x140007a35  mov     [rbp+rax*2+0A00h+var_450], di
0x140007a3d  lea     rcx, ds:2[rax*2]
0x140007a45  cmp     rcx, 418h
0x140007a4c  jnb     loc_140007AE1
0x140007a52  mov     [rbp+rcx+0A00h+var_450], r14w
0x140007a5b  lea     r8, [rbp+0A00h+var_450]; wchar_t *
0x140007a62  lea     rdx, aModule; "Module"
0x140007a69  lea     rcx, [rsp+0B00h+var_AC0]; this
0x140007a6e  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140007a73  mov     ebx, eax
0x140007a75  test    eax, eax
0x140007a77  js      short loc_140007A97
0x140007a79  lea     r8, [rbp+0A00h+Source]; wchar_t *
0x140007a80  lea     rdx, aModuleRaw; "Module_Raw"
0x140007a87  lea     rcx, [rsp+0B00h+var_AC0]; this
0x140007a8c  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140007a91  mov     ebx, eax
0x140007a93  test    eax, eax
0x140007a95  jns     short loc_140007AA6
0x140007a97  lea     rcx, [rsp+0B00h+var_AD0]
0x140007a9c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140007aa1  jmp     loc_1400078F6
0x140007aa6  mov     [rsp+0B00h+var_AC8], r14
0x140007aab  lea     r9, aRegistry; "REGISTRY"
0x140007ab2  lea     rdx, [rbp+0A00h+Filename]; wchar_t *
0x140007ab6  lea     rcx, [rsp+0B00h+var_AC0]; this
0x140007abb  test    esi, esi
0x140007abd  jz      short loc_140007AC9
0x140007abf  mov     [rsp+0B00h+var_AE0], 1
0x140007ac7  jmp     short loc_140007ACE
0x140007ac9  mov     [rsp+0B00h+var_AE0], r14d; int
0x140007ace  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x140007ad3  mov     ebx, eax
0x140007ad5  lea     rcx, [rsp+0B00h+var_AC8]
0x140007ada  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140007adf  jmp     short loc_140007A97
0x140007ae1  call    __report_rangecheckfailure
0x140007ae7  lea     rcx, [rsp+0B00h+var_AD0]
0x140007aec  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140007af1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x140007af6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140007afb  mov     eax, 80004005h
0x140007b00  mov     rcx, [rbp+0A00h+var_30]
0x140007b07  xor     rcx, rsp; StackCookie
0x140007b0a  call    __security_check_cookie
0x140007b0f  add     rsp, 0AE0h
0x140007b16  pop     r14
0x140007b18  pop     rdi
0x140007b19  pop     rsi
0x140007b1a  pop     rbx
0x140007b1b  pop     rbp
0x140007b1c  retn
```
