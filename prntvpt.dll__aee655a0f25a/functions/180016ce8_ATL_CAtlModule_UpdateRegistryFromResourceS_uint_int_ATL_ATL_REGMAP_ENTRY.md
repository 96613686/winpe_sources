# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180016ce8`
- end: `0x180016fb5`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `717`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016cb0`
- `0x180016cd0`
- `0x180018544`
- `0x180018588`

## callees

- `0x18000d3c8`
- `0x18000f970`
- `0x18000f9b0`
- `0x180010e58`
- `0x180010f88`
- `0x180011218`
- `0x180011950`
- `0x180011fc4`
- `0x1800138c0`
- `0x180015464`
- `0x180016ce8`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180016e3a`
- `KERNEL32!GetModuleHandleW` at `0x180016e3a`
- `KERNEL32!GetModuleFileNameW` at `0x180016db5`
- `KERNEL32!GetModuleFileNameW` at `0x180016db5`

## string_xrefs

- `0x180016f2f`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v4; // rsi
  int v8; // edi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v15; // r8
  unsigned __int16 *v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[48]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Source[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v27; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE Destination[1054]; // [rsp+6B2h] [rbp+5B2h] BYREF

  v4 = ATL::_pAtlModule;
  ATL::CRegObject::CRegObject((ATL::CRegObject *)v23);
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v24);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v23,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, _BYTE *))(*(_QWORD *)v4 + 40LL))(v4, v23);
  if ( Error < 0 )
    goto LABEL_30;
  v11 = hModule;
  v21 = 0;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_29:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    goto LABEL_30;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    Error = -2147024774;
LABEL_30:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
    return (unsigned int)Error;
  }
  v13 = Filename;
  v14 = 0;
  do
  {
    v15 = *v13;
    if ( !*v13 )
      break;
    Source[v14] = v15;
    if ( v15 == 39 && (unsigned int)v14 < 0x206 )
    {
      LODWORD(v14) = v14 + 1;
      Source[(unsigned int)v14] = 39;
    }
    ++v13;
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < 0x207 );
  Source[v14] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v16 = Source;
LABEL_27:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v23, L"Module", v16);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v23, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v22 = 0;
        if ( a3 )
          v20 = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  1);
        else
          v20 = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  0);
        Error = v20;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v22);
      }
    }
    goto LABEL_29;
  }
  v17 = -1;
  v27 = 34;
  v18 = -1;
  do
    ++v18;
  while ( Source[v18] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v18 + 1)) )
  {
    do
      ++v17;
    while ( *(_WORD *)&Destination[2 * v17 - 2] );
    v19 = 2LL * (int)v17 + 2;
    *(_WORD *)&Destination[2 * (int)v17 - 2] = 34;
    if ( v19 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v19 - 2] = 0;
    v16 = &v27;
    goto LABEL_27;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180016ce8  mov     [rsp-8+arg_0], rbx
0x180016ced  mov     [rsp-8+arg_10], rsi
0x180016cf2  push    rbp
0x180016cf3  push    rdi
0x180016cf4  push    r12
0x180016cf6  push    r14
0x180016cf8  push    r15
0x180016cfa  lea     rbp, [rsp-9E0h]
0x180016d02  sub     rsp, 0AE0h
0x180016d09  mov     rax, cs:__security_cookie
0x180016d10  xor     rax, rsp
0x180016d13  mov     [rbp+0A00h+var_30], rax
0x180016d1a  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180016d21  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016d26  mov     rbx, r9
0x180016d29  mov     r15d, edx
0x180016d2c  mov     r14d, r8d
0x180016d2f  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x180016d34  lea     rcx, [rsp+0B00h+var_AA0]; this
0x180016d39  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180016d3e  xor     r12d, r12d
0x180016d41  mov     edi, eax
0x180016d43  test    eax, eax
0x180016d45  jns     short loc_180016D58
0x180016d47  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016d4c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180016d51  mov     eax, edi
0x180016d53  jmp     loc_180016F8A
0x180016d58  test    rbx, rbx
0x180016d5b  jz      short loc_180016D7C
0x180016d5d  jmp     short loc_180016D74
0x180016d5f  mov     r8, [rbx+8]; unsigned __int16 *
0x180016d63  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016d68  mov     rdx, rax; unsigned __int16 *
0x180016d6b  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180016d70  lea     rbx, [rbx+10h]
0x180016d74  mov     rax, [rbx]
0x180016d77  test    rax, rax
0x180016d7a  jnz     short loc_180016D5F
0x180016d7c  mov     rax, [rsi]
0x180016d7f  lea     rdx, [rsp+0B00h+var_AC0]
0x180016d84  mov     rcx, rsi
0x180016d87  mov     rax, [rax+28h]
0x180016d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d90  mov     ebx, eax
0x180016d92  test    eax, eax
0x180016d94  js      loc_180016F1D
0x180016d9a  mov     rbx, cs:hModule
0x180016da1  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180016da5  mov     edi, 104h
0x180016daa  mov     [rsp+0B00h+var_AD0], r12
0x180016daf  mov     r8d, edi; nSize
0x180016db2  mov     rcx, rbx; hModule
0x180016db5  call    cs:__imp_GetModuleFileNameW
0x180016dbb  test    eax, eax
0x180016dbd  jnz     short loc_180016DCB
0x180016dbf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180016dc4  mov     ebx, eax
0x180016dc6  jmp     loc_180016F13
0x180016dcb  cmp     eax, edi
0x180016dcd  jnz     short loc_180016DE3
0x180016dcf  lea     rcx, [rsp+0B00h+var_AD0]
0x180016dd4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180016dd9  mov     ebx, 8007007Ah
0x180016dde  jmp     loc_180016F1D
0x180016de3  lea     rdx, [rbp+0A00h+Filename]
0x180016de7  mov     ecx, r12d
0x180016dea  mov     r9d, 27h ; '''
0x180016df0  movzx   r8d, word ptr [rdx]
0x180016df4  test    r8w, r8w
0x180016df8  jz      short loc_180016E2A
0x180016dfa  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180016e03  cmp     r8w, r9w
0x180016e07  jnz     short loc_180016E1C
0x180016e09  cmp     ecx, 206h
0x180016e0f  jnb     short loc_180016E1C
0x180016e11  inc     ecx
0x180016e13  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180016e1c  add     rdx, 2
0x180016e20  inc     ecx
0x180016e22  cmp     ecx, 207h
0x180016e28  jb      short loc_180016DF0
0x180016e2a  mov     [rbp+rcx*2+0A00h+Source], r12w
0x180016e33  test    rbx, rbx
0x180016e36  jz      short loc_180016E51
0x180016e38  xor     ecx, ecx; lpModuleName
0x180016e3a  call    cs:__imp_GetModuleHandleW
0x180016e40  cmp     rbx, rax
0x180016e43  jz      short loc_180016E51
0x180016e45  lea     r8, [rbp+0A00h+Source]
0x180016e4c  jmp     loc_180016EDE
0x180016e51  mov     edi, 22h ; '"'
0x180016e56  lea     rcx, [rbp+0A00h+Source]
0x180016e5d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016e61  mov     [rbp+0A00h+var_450], di
0x180016e68  mov     rax, rbx
0x180016e6b  inc     rax
0x180016e6e  cmp     [rcx+rax*2], r12w
0x180016e73  jnz     short loc_180016E6B
0x180016e75  inc     eax
0x180016e77  lea     r8, [rbp+0A00h+Source]; Source
0x180016e7e  movsxd  r9, eax
0x180016e81  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180016e88  add     r9, r9; SourceSize
0x180016e8b  mov     edx, 414h; DestinationSize
0x180016e90  call    memcpy_s
0x180016e95  test    eax, eax
0x180016e97  jnz     loc_180016F71
0x180016e9d  lea     rax, [rbp+0A00h+var_450]
0x180016ea4  inc     rbx
0x180016ea7  cmp     [rax+rbx*2], r12w
0x180016eac  jnz     short loc_180016EA4
0x180016eae  movsxd  rax, ebx
0x180016eb1  lea     rcx, ds:2[rax*2]
0x180016eb9  mov     [rbp+rax*2+0A00h+var_450], di
0x180016ec1  cmp     rcx, 418h
0x180016ec8  jnb     loc_180016F6B
0x180016ece  mov     [rbp+rcx+0A00h+var_450], r12w
0x180016ed7  lea     r8, [rbp+0A00h+var_450]; unsigned __int16 *
0x180016ede  lea     rdx, aModule; "Module"
0x180016ee5  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016eea  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180016eef  mov     ebx, eax
0x180016ef1  test    eax, eax
0x180016ef3  js      short loc_180016F13
0x180016ef5  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180016efc  lea     rdx, aModuleRaw; "Module_Raw"
0x180016f03  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016f08  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180016f0d  mov     ebx, eax
0x180016f0f  test    eax, eax
0x180016f11  jns     short loc_180016F2B
0x180016f13  lea     rcx, [rsp+0B00h+var_AD0]
0x180016f18  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180016f1d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016f22  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180016f27  mov     eax, ebx
0x180016f29  jmp     short loc_180016F8A
0x180016f2b  movzx   r8d, r15w; unsigned __int16 *
0x180016f2f  lea     r9, aRegistry; "REGISTRY"
0x180016f36  mov     [rsp+0B00h+var_AC8], r12
0x180016f3b  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180016f3f  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016f44  test    r14d, r14d
0x180016f47  jz      short loc_180016F53
0x180016f49  mov     [rsp+0B00h+var_AE0], 1
0x180016f51  jmp     short loc_180016F58
0x180016f53  mov     [rsp+0B00h+var_AE0], r12d; int
0x180016f58  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180016f5d  lea     rcx, [rsp+0B00h+var_AC8]
0x180016f62  mov     ebx, eax
0x180016f64  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180016f69  jmp     short loc_180016F13
0x180016f6b  call    __report_rangecheckfailure
0x180016f71  lea     rcx, [rsp+0B00h+var_AD0]
0x180016f76  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180016f7b  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180016f80  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180016f85  mov     eax, 80004005h
0x180016f8a  mov     rcx, [rbp+0A00h+var_30]
0x180016f91  xor     rcx, rsp; StackCookie
0x180016f94  call    __security_check_cookie
0x180016f99  lea     r11, [rsp+0B00h+var_20]
0x180016fa1  mov     rbx, [r11+30h]
0x180016fa5  mov     rsi, [r11+40h]
0x180016fa9  mov     rsp, r11
0x180016fac  pop     r15
0x180016fae  pop     r14
0x180016fb0  pop     r12
0x180016fb2  pop     rdi
0x180016fb3  pop     rbp
0x180016fb4  retn
```
