# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006664`
- end: `0x18000690d`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `681`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006610`
- `0x180006630`
- `0x180006650`

## callees

- `0x1800021a8`
- `0x180002f64`
- `0x180003398`
- `0x180003a70`
- `0x1800041d0`
- `0x180004f34`
- `0x1800058e0`
- `0x180006664`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800067fd`
- `msvcrt!memcpy_s` at `0x1800067fd`
- `KERNEL32!GetModuleFileNameW` at `0x180006725`
- `KERNEL32!GetModuleFileNameW` at `0x180006725`
- `KERNEL32!GetModuleHandleW` at `0x1800067a7`
- `KERNEL32!GetModuleHandleW` at `0x1800067a7`

## string_xrefs

- `0x180006899`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v6; // rdi
  int Error; // ebx
  HMODULE v9; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 v13; // r8
  unsigned __int16 *v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Source[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v27; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE Destination[1054]; // [rsp+6B2h] [rbp+5B2h] BYREF

  v6 = ATL::_pAtlModule;
  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(&v23, 0, sizeof(v23));
  v24 = 0;
  Error = ATL::CComSafeDeleteCriticalSection::Init(&v23);
  if ( Error < 0 )
    goto LABEL_2;
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, _QWORD *))(*(_QWORD *)v6 + 40LL))(v6, v21);
  if ( Error < 0 )
    goto LABEL_2;
  v19 = 0;
  v9 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_25:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    goto LABEL_2;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
LABEL_2:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
    return (unsigned int)Error;
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
  if ( v9 && v9 != GetModuleHandleW(0) )
  {
    v14 = Source;
LABEL_23:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v14);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v20 = 0;
        if ( a3 )
          v18 = ATL::CRegObject::RegisterFromResource(
                  (const wchar_t *)v21,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  1);
        else
          v18 = ATL::CRegObject::RegisterFromResource(
                  (const wchar_t *)v21,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  0);
        Error = v18;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
      }
    }
    goto LABEL_25;
  }
  v27 = 34;
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( Source[v16] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v16 + 1)) )
  {
    do
      ++v15;
    while ( *(_WORD *)&Destination[2 * v15 - 2] );
    *(_WORD *)&Destination[2 * (int)v15 - 2] = 34;
    v17 = 2LL * (int)v15 + 2;
    if ( v17 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v17 - 2] = 0;
    v14 = &v27;
    goto LABEL_23;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180006664  push    rbp
0x180006666  push    rbx
0x180006667  push    rsi
0x180006668  push    rdi
0x180006669  push    r14
0x18000666b  push    r15
0x18000666d  lea     rbp, [rsp-9E8h]
0x180006675  sub     rsp, 0AE8h
0x18000667c  mov     rax, cs:__security_cookie
0x180006683  xor     rax, rsp
0x180006686  mov     [rbp+0A10h+var_40], rax
0x18000668d  mov     esi, r8d
0x180006690  mov     r14d, edx
0x180006693  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000669a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800066a1  mov     [rsp+0B10h+var_AD0], rax
0x1800066a6  xor     r15d, r15d
0x1800066a9  mov     [rsp+0B10h+var_AC8], r15
0x1800066ae  mov     [rsp+0B10h+var_AC0], r15
0x1800066b3  mov     [rsp+0B10h+var_AB8], r15d
0x1800066b8  xorps   xmm0, xmm0
0x1800066bb  xor     eax, eax
0x1800066bd  movups  [rsp+0B10h+var_AB0], xmm0
0x1800066c2  movups  [rsp+0B10h+var_AA0], xmm0
0x1800066c7  mov     [rbp+0A10h+var_A90], rax
0x1800066cb  mov     [rbp+0A10h+var_A88], r15b
0x1800066cf  lea     rcx, [rsp+0B10h+var_AB0]; this
0x1800066d4  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800066d9  mov     ebx, eax
0x1800066db  test    eax, eax
0x1800066dd  jns     short loc_1800066F0
0x1800066df  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800066e4  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800066e9  mov     eax, ebx
0x1800066eb  jmp     loc_1800068EE
0x1800066f0  mov     rax, [rdi]
0x1800066f3  lea     rdx, [rsp+0B10h+var_AD0]
0x1800066f8  mov     rcx, rdi
0x1800066fb  mov     rax, [rax+28h]
0x1800066ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006704  mov     ebx, eax
0x180006706  test    eax, eax
0x180006708  js      short loc_1800066DF
0x18000670a  mov     [rsp+0B10h+var_AE0], r15
0x18000670f  mov     rbx, cs:hInstance
0x180006716  mov     edi, 104h
0x18000671b  mov     r8d, edi; nSize
0x18000671e  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180006722  mov     rcx, rbx; hModule
0x180006725  call    cs:__imp_GetModuleFileNameW
0x18000672b  test    eax, eax
0x18000672d  jnz     short loc_18000673B
0x18000672f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006734  mov     ebx, eax
0x180006736  jmp     loc_180006881
0x18000673b  cmp     eax, edi
0x18000673d  jnz     short loc_180006750
0x18000673f  lea     rcx, [rsp+0B10h+var_AE0]
0x180006744  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006749  mov     ebx, 8007007Ah
0x18000674e  jmp     short loc_1800066DF
0x180006750  lea     rdx, [rbp+0A10h+Filename]
0x180006754  mov     ecx, r15d
0x180006757  mov     r9d, 27h ; '''
0x18000675d  movzx   r8d, word ptr [rdx]
0x180006761  test    r8w, r8w
0x180006765  jz      short loc_180006797
0x180006767  mov     [rbp+rcx*2+0A10h+Source], r8w
0x180006770  cmp     r8w, r9w
0x180006774  jnz     short loc_180006789
0x180006776  cmp     ecx, 206h
0x18000677c  jnb     short loc_180006789
0x18000677e  inc     ecx
0x180006780  mov     [rbp+rcx*2+0A10h+Source], r9w
0x180006789  add     rdx, 2
0x18000678d  inc     ecx
0x18000678f  cmp     ecx, 207h
0x180006795  jb      short loc_18000675D
0x180006797  mov     [rbp+rcx*2+0A10h+Source], r15w
0x1800067a0  test    rbx, rbx
0x1800067a3  jz      short loc_1800067BE
0x1800067a5  xor     ecx, ecx; lpModuleName
0x1800067a7  call    cs:__imp_GetModuleHandleW
0x1800067ad  cmp     rbx, rax
0x1800067b0  jz      short loc_1800067BE
0x1800067b2  lea     r8, [rbp+0A10h+Source]
0x1800067b9  jmp     loc_18000684C
0x1800067be  mov     edi, 22h ; '"'
0x1800067c3  mov     [rbp+0A10h+var_460], di
0x1800067ca  lea     rcx, [rbp+0A10h+Source]
0x1800067d1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800067d5  mov     rax, rbx
0x1800067d8  inc     rax
0x1800067db  cmp     [rcx+rax*2], r15w
0x1800067e0  jnz     short loc_1800067D8
0x1800067e2  inc     eax
0x1800067e4  movsxd  r9, eax
0x1800067e7  add     r9, r9; SourceSize
0x1800067ea  lea     r8, [rbp+0A10h+Source]; Source
0x1800067f1  mov     edx, 414h; DestinationSize
0x1800067f6  lea     rcx, [rbp+0A10h+Destination]; Destination
0x1800067fd  call    cs:__imp_memcpy_s
0x180006803  test    eax, eax
0x180006805  jnz     loc_1800068D5
0x18000680b  lea     rax, [rbp+0A10h+var_460]
0x180006812  inc     rbx
0x180006815  cmp     [rax+rbx*2], r15w
0x18000681a  jnz     short loc_180006812
0x18000681c  movsxd  rax, ebx
0x18000681f  mov     [rbp+rax*2+0A10h+var_460], di
0x180006827  lea     rcx, ds:2[rax*2]
0x18000682f  cmp     rcx, 418h
0x180006836  jnb     loc_1800068CF
0x18000683c  mov     [rbp+rcx+0A10h+var_460], r15w
0x180006845  lea     r8, [rbp+0A10h+var_460]; unsigned __int16 *
0x18000684c  lea     rdx, aModule; "Module"
0x180006853  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180006858  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000685d  mov     ebx, eax
0x18000685f  test    eax, eax
0x180006861  js      short loc_180006881
0x180006863  lea     r8, [rbp+0A10h+Source]; unsigned __int16 *
0x18000686a  lea     rdx, aModuleRaw; "Module_Raw"
0x180006871  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180006876  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000687b  mov     ebx, eax
0x18000687d  test    eax, eax
0x18000687f  jns     short loc_180006890
0x180006881  lea     rcx, [rsp+0B10h+var_AE0]
0x180006886  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000688b  jmp     loc_1800066DF
0x180006890  movzx   r8d, r14w; unsigned __int16 *
0x180006894  mov     [rsp+0B10h+var_AD8], r15
0x180006899  lea     r9, aRegistry; "REGISTRY"
0x1800068a0  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800068a4  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800068a9  test    esi, esi
0x1800068ab  jz      short loc_1800068B7
0x1800068ad  mov     [rsp+0B10h+var_AF0], 1
0x1800068b5  jmp     short loc_1800068BC
0x1800068b7  mov     [rsp+0B10h+var_AF0], r15d; int
0x1800068bc  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800068c1  mov     ebx, eax
0x1800068c3  lea     rcx, [rsp+0B10h+var_AD8]
0x1800068c8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800068cd  jmp     short loc_180006881
0x1800068cf  call    __report_rangecheckfailure
0x1800068d5  lea     rcx, [rsp+0B10h+var_AE0]
0x1800068da  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800068df  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800068e4  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800068e9  mov     eax, 80004005h
0x1800068ee  mov     rcx, [rbp+0A10h+var_40]
0x1800068f5  xor     rcx, rsp; StackCookie
0x1800068f8  call    __security_check_cookie
0x1800068fd  add     rsp, 0AE8h
0x180006904  pop     r15
0x180006906  pop     r14
0x180006908  pop     rdi
0x180006909  pop     rsi
0x18000690a  pop     rbx
0x18000690b  pop     rbp
0x18000690c  retn
```
