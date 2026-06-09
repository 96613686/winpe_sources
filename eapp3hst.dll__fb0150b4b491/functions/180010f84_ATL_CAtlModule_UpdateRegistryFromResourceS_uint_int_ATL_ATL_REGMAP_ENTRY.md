# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180010f84`
- end: `0x18001121f`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `667`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004980`
- `0x180004a20`

## callees

- `0x1800017a0`
- `0x180001d70`
- `0x180003938`
- `0x180004424`
- `0x18000ee68`
- `0x18000ef24`
- `0x18000f260`
- `0x18000fac0`
- `0x1800105b0`
- `0x180010f84`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800110c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800110c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011040`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011040`

## string_xrefs

- `0x1800111ae`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int Error; // ebx
  HMODULE v7; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v9; // rdx
  __int64 v10; // rcx
  wchar_t v11; // r8
  wchar_t *v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  const wchar_t *v16; // r8
  int v17; // eax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v20[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h]
  _OWORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  char v24; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Source[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t v27; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE Destination[1054]; // [rsp+6B2h] [rbp+5B2h] BYREF

  v20[0] = &ATL::CRegObject::`vftable';
  v20[1] = 0;
  v20[2] = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  Error = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v22);
  if ( Error < 0 )
    goto LABEL_2;
  Error = (*(__int64 (__fastcall **)(void *, _QWORD *))(qword_18004B000 + 40LL))(&qword_18004B000, v20);
  if ( Error < 0 )
    goto LABEL_2;
  v18 = 0;
  v7 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_25:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
    goto LABEL_2;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
    Error = -2147024774;
LABEL_2:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v20);
    return (unsigned int)Error;
  }
  v9 = Filename;
  v10 = 0;
  do
  {
    v11 = *v9;
    if ( !*v9 )
      break;
    Source[v10] = v11;
    if ( v11 == 39 && (unsigned int)v10 < 0x206 )
    {
      LODWORD(v10) = v10 + 1;
      Source[(unsigned int)v10] = 39;
    }
    ++v9;
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < 0x207 );
  Source[v10] = 0;
  if ( v7 && v7 != GetModuleHandleW(0) )
  {
    v12 = Source;
LABEL_23:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v20, L"Module", v12);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v20, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v19 = 0;
        if ( a3 )
          v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v20, Filename, v16, L"REGISTRY", 1);
        else
          v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v20, Filename, v16, L"REGISTRY", 0);
        Error = v17;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      }
    }
    goto LABEL_25;
  }
  v27 = 34;
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( Source[v14] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v14 + 1)) )
  {
    do
      ++v13;
    while ( *(_WORD *)&Destination[2 * v13 - 2] );
    *(_WORD *)&Destination[2 * (int)v13 - 2] = 34;
    v15 = 2LL * (int)v13 + 2;
    if ( v15 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v15 - 2] = 0;
    v12 = &v27;
    goto LABEL_23;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v20);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180010f84  push    rbp
0x180010f86  push    rbx
0x180010f87  push    rsi
0x180010f88  push    rdi
0x180010f89  push    r14
0x180010f8b  lea     rbp, [rsp-9E0h]
0x180010f93  sub     rsp, 0AE0h
0x180010f9a  mov     rax, cs:__security_cookie
0x180010fa1  xor     rax, rsp
0x180010fa4  mov     [rbp+0A00h+var_30], rax
0x180010fab  mov     edi, r8d
0x180010fae  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180010fb5  mov     [rsp+0B00h+var_AC0], rax
0x180010fba  xor     esi, esi
0x180010fbc  mov     [rsp+0B00h+var_AB8], rsi
0x180010fc1  mov     [rsp+0B00h+var_AB0], rsi
0x180010fc6  mov     [rsp+0B00h+var_AA8], esi
0x180010fca  xorps   xmm0, xmm0
0x180010fcd  xor     eax, eax
0x180010fcf  movups  [rsp+0B00h+var_AA0], xmm0
0x180010fd4  movups  [rsp+0B00h+var_A90], xmm0
0x180010fd9  mov     [rbp+0A00h+var_A80], rax
0x180010fdd  mov     [rbp+0A00h+var_A78], sil
0x180010fe1  lea     rcx, [rsp+0B00h+var_AA0]; this
0x180010fe6  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180010feb  mov     ebx, eax
0x180010fed  test    eax, eax
0x180010fef  jns     short loc_180011002
0x180010ff1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180010ff6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180010ffb  mov     eax, ebx
0x180010ffd  jmp     loc_180011202
0x180011002  mov     rax, cs:qword_18004B000
0x180011009  lea     rdx, [rsp+0B00h+var_AC0]
0x18001100e  lea     rcx, qword_18004B000
0x180011015  mov     rax, [rax+28h]
0x180011019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001101e  mov     ebx, eax
0x180011020  test    eax, eax
0x180011022  js      short loc_180010FF1
0x180011024  mov     [rsp+0B00h+var_AD0], rsi
0x180011029  mov     rbx, cs:hModule
0x180011030  mov     r14d, 104h
0x180011036  mov     r8d, r14d; nSize
0x180011039  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18001103d  mov     rcx, rbx; hModule
0x180011040  call    cs:__imp_GetModuleFileNameW
0x180011046  test    eax, eax
0x180011048  jnz     short loc_180011056
0x18001104a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001104f  mov     ebx, eax
0x180011051  jmp     loc_18001119A
0x180011056  cmp     eax, r14d
0x180011059  jnz     short loc_18001106C
0x18001105b  lea     rcx, [rsp+0B00h+var_AD0]
0x180011060  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011065  mov     ebx, 8007007Ah
0x18001106a  jmp     short loc_180010FF1
0x18001106c  lea     rdx, [rbp+0A00h+Filename]
0x180011070  mov     ecx, esi
0x180011072  mov     r9d, 27h ; '''
0x180011078  movzx   r8d, word ptr [rdx]
0x18001107c  test    r8w, r8w
0x180011080  jz      short loc_1800110B2
0x180011082  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18001108b  cmp     r8w, r9w
0x18001108f  jnz     short loc_1800110A4
0x180011091  cmp     ecx, 206h
0x180011097  jnb     short loc_1800110A4
0x180011099  inc     ecx
0x18001109b  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800110a4  add     rdx, 2
0x1800110a8  inc     ecx
0x1800110aa  cmp     ecx, 207h
0x1800110b0  jb      short loc_180011078
0x1800110b2  mov     [rbp+rcx*2+0A00h+Source], si
0x1800110ba  test    rbx, rbx
0x1800110bd  jz      short loc_1800110D8
0x1800110bf  xor     ecx, ecx; lpModuleName
0x1800110c1  call    cs:__imp_GetModuleHandleW
0x1800110c7  cmp     rbx, rax
0x1800110ca  jz      short loc_1800110D8
0x1800110cc  lea     r8, [rbp+0A00h+Source]
0x1800110d3  jmp     loc_180011165
0x1800110d8  mov     r14d, 22h ; '"'
0x1800110de  mov     [rbp+0A00h+var_450], r14w
0x1800110e6  lea     rcx, [rbp+0A00h+Source]
0x1800110ed  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800110f1  mov     rax, rbx
0x1800110f4  inc     rax
0x1800110f7  cmp     [rcx+rax*2], si
0x1800110fb  jnz     short loc_1800110F4
0x1800110fd  inc     eax
0x1800110ff  movsxd  r9, eax
0x180011102  add     r9, r9; SourceSize
0x180011105  lea     r8, [rbp+0A00h+Source]; Source
0x18001110c  mov     edx, 414h; DestinationSize
0x180011111  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180011118  call    memcpy_s
0x18001111d  test    eax, eax
0x18001111f  jnz     loc_1800111E9
0x180011125  lea     rax, [rbp+0A00h+var_450]
0x18001112c  inc     rbx
0x18001112f  cmp     [rax+rbx*2], si
0x180011133  jnz     short loc_18001112C
0x180011135  movsxd  rax, ebx
0x180011138  mov     [rbp+rax*2+0A00h+var_450], r14w
0x180011141  lea     rcx, ds:2[rax*2]
0x180011149  cmp     rcx, 418h
0x180011150  jnb     loc_1800111E3
0x180011156  mov     [rbp+rcx+0A00h+var_450], si
0x18001115e  lea     r8, [rbp+0A00h+var_450]; wchar_t *
0x180011165  lea     rdx, aModule; "Module"
0x18001116c  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180011171  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180011176  mov     ebx, eax
0x180011178  test    eax, eax
0x18001117a  js      short loc_18001119A
0x18001117c  lea     r8, [rbp+0A00h+Source]; wchar_t *
0x180011183  lea     rdx, aModuleRaw; "Module_Raw"
0x18001118a  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18001118f  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180011194  mov     ebx, eax
0x180011196  test    eax, eax
0x180011198  jns     short loc_1800111A9
0x18001119a  lea     rcx, [rsp+0B00h+var_AD0]
0x18001119f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800111a4  jmp     loc_180010FF1
0x1800111a9  mov     [rsp+0B00h+var_AC8], rsi
0x1800111ae  lea     r9, aRegistry_0; "REGISTRY"
0x1800111b5  lea     rdx, [rbp+0A00h+Filename]; wchar_t *
0x1800111b9  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800111be  test    edi, edi
0x1800111c0  jz      short loc_1800111CC
0x1800111c2  mov     [rsp+0B00h+var_AE0], 1
0x1800111ca  jmp     short loc_1800111D0
0x1800111cc  mov     [rsp+0B00h+var_AE0], esi; int
0x1800111d0  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x1800111d5  mov     ebx, eax
0x1800111d7  lea     rcx, [rsp+0B00h+var_AC8]
0x1800111dc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800111e1  jmp     short loc_18001119A
0x1800111e3  call    __report_rangecheckfailure
0x1800111e9  lea     rcx, [rsp+0B00h+var_AD0]
0x1800111ee  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800111f3  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800111f8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800111fd  mov     eax, 80004005h
0x180011202  mov     rcx, [rbp+0A00h+var_30]
0x180011209  xor     rcx, rsp; StackCookie
0x18001120c  call    __security_check_cookie
0x180011211  add     rsp, 0AE0h
0x180011218  pop     r14
0x18001121a  pop     rdi
0x18001121b  pop     rsi
0x18001121c  pop     rbx
0x18001121d  pop     rbp
0x18001121e  retn
```
