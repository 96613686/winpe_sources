# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180013ad8`
- end: `0x180013da6`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `718`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `13`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013ac0`
- `0x180015460`
- `0x180015e20`
- `0x180016760`
- `0x18001d320`
- `0x1800274e0`
- `0x180028ac0`
- `0x18002bcf0`
- `0x180030190`
- `0x180033b40`
- `0x180039f80`
- `0x18003dd30`
- `0x18004217c`

## callees

- `0x180005fa4`
- `0x180010578`
- `0x180010fec`
- `0x180011024`
- `0x18001112c`
- `0x180011490`
- `0x180011b10`
- `0x180012f9c`
- `0x180013ad8`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013c80`
- `msvcrt!memcpy_s` at `0x180013c80`
- `KERNEL32!GetModuleFileNameW` at `0x180013ba5`
- `KERNEL32!GetModuleFileNameW` at `0x180013ba5`
- `KERNEL32!GetModuleHandleW` at `0x180013c2a`
- `KERNEL32!GetModuleHandleW` at `0x180013c2a`

## string_xrefs

- `0x180013d20`: `REGISTRY`

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
0x180013ad8  mov     [rsp-8+arg_0], rbx
0x180013add  mov     [rsp-8+arg_10], rsi
0x180013ae2  push    rbp
0x180013ae3  push    rdi
0x180013ae4  push    r12
0x180013ae6  push    r14
0x180013ae8  push    r15
0x180013aea  lea     rbp, [rsp-9E0h]
0x180013af2  sub     rsp, 0AE0h
0x180013af9  mov     rax, cs:__security_cookie
0x180013b00  xor     rax, rsp
0x180013b03  mov     [rbp+0A00h+var_30], rax
0x180013b0a  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013b11  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013b16  mov     rbx, r9
0x180013b19  mov     r15d, edx
0x180013b1c  mov     r14d, r8d
0x180013b1f  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x180013b24  lea     rcx, [rsp+0B00h+var_AA0]; this
0x180013b29  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180013b2e  xor     r12d, r12d
0x180013b31  mov     edi, eax
0x180013b33  test    eax, eax
0x180013b35  jns     short loc_180013B48
0x180013b37  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013b3c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013b41  mov     eax, edi
0x180013b43  jmp     loc_180013D7B
0x180013b48  test    rbx, rbx
0x180013b4b  jz      short loc_180013B6C
0x180013b4d  jmp     short loc_180013B64
0x180013b4f  mov     r8, [rbx+8]; unsigned __int16 *
0x180013b53  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013b58  mov     rdx, rax; unsigned __int16 *
0x180013b5b  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180013b60  lea     rbx, [rbx+10h]
0x180013b64  mov     rax, [rbx]
0x180013b67  test    rax, rax
0x180013b6a  jnz     short loc_180013B4F
0x180013b6c  mov     rax, [rsi]
0x180013b6f  lea     rdx, [rsp+0B00h+var_AC0]
0x180013b74  mov     rcx, rsi
0x180013b77  mov     rax, [rax+28h]
0x180013b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b80  mov     ebx, eax
0x180013b82  test    eax, eax
0x180013b84  js      loc_180013D0E
0x180013b8a  mov     rbx, cs:hModule
0x180013b91  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180013b95  mov     edi, 104h
0x180013b9a  mov     [rsp+0B00h+var_AD0], r12
0x180013b9f  mov     r8d, edi; nSize
0x180013ba2  mov     rcx, rbx; hModule
0x180013ba5  call    cs:__imp_GetModuleFileNameW
0x180013bab  test    eax, eax
0x180013bad  jnz     short loc_180013BBB
0x180013baf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013bb4  mov     ebx, eax
0x180013bb6  jmp     loc_180013D04
0x180013bbb  cmp     eax, edi
0x180013bbd  jnz     short loc_180013BD3
0x180013bbf  lea     rcx, [rsp+0B00h+var_AD0]
0x180013bc4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013bc9  mov     ebx, 8007007Ah
0x180013bce  jmp     loc_180013D0E
0x180013bd3  lea     rdx, [rbp+0A00h+Filename]
0x180013bd7  mov     ecx, r12d
0x180013bda  mov     r9d, 27h ; '''
0x180013be0  movzx   r8d, word ptr [rdx]
0x180013be4  test    r8w, r8w
0x180013be8  jz      short loc_180013C1A
0x180013bea  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180013bf3  cmp     r8w, r9w
0x180013bf7  jnz     short loc_180013C0C
0x180013bf9  cmp     ecx, 206h
0x180013bff  jnb     short loc_180013C0C
0x180013c01  inc     ecx
0x180013c03  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180013c0c  add     rdx, 2
0x180013c10  inc     ecx
0x180013c12  cmp     ecx, 207h
0x180013c18  jb      short loc_180013BE0
0x180013c1a  mov     [rbp+rcx*2+0A00h+Source], r12w
0x180013c23  test    rbx, rbx
0x180013c26  jz      short loc_180013C41
0x180013c28  xor     ecx, ecx; lpModuleName
0x180013c2a  call    cs:__imp_GetModuleHandleW
0x180013c30  cmp     rbx, rax
0x180013c33  jz      short loc_180013C41
0x180013c35  lea     r8, [rbp+0A00h+Source]
0x180013c3c  jmp     loc_180013CCF
0x180013c41  mov     edi, 22h ; '"'
0x180013c46  lea     rcx, [rbp+0A00h+Source]
0x180013c4d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013c51  mov     [rbp+0A00h+var_450], di
0x180013c58  mov     rax, rbx
0x180013c5b  inc     rax
0x180013c5e  cmp     [rcx+rax*2], r12w
0x180013c63  jnz     short loc_180013C5B
0x180013c65  inc     eax
0x180013c67  lea     r8, [rbp+0A00h+Source]; Source
0x180013c6e  movsxd  r9, eax
0x180013c71  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180013c78  add     r9, r9; SourceSize
0x180013c7b  mov     edx, 414h; DestinationSize
0x180013c80  call    cs:__imp_memcpy_s
0x180013c86  test    eax, eax
0x180013c88  jnz     loc_180013D62
0x180013c8e  lea     rax, [rbp+0A00h+var_450]
0x180013c95  inc     rbx
0x180013c98  cmp     [rax+rbx*2], r12w
0x180013c9d  jnz     short loc_180013C95
0x180013c9f  movsxd  rax, ebx
0x180013ca2  lea     rcx, ds:2[rax*2]
0x180013caa  mov     [rbp+rax*2+0A00h+var_450], di
0x180013cb2  cmp     rcx, 418h
0x180013cb9  jnb     loc_180013D5C
0x180013cbf  mov     [rbp+rcx+0A00h+var_450], r12w
0x180013cc8  lea     r8, [rbp+0A00h+var_450]; unsigned __int16 *
0x180013ccf  lea     rdx, aModule; "Module"
0x180013cd6  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013cdb  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180013ce0  mov     ebx, eax
0x180013ce2  test    eax, eax
0x180013ce4  js      short loc_180013D04
0x180013ce6  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180013ced  lea     rdx, aModuleRaw; "Module_Raw"
0x180013cf4  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013cf9  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180013cfe  mov     ebx, eax
0x180013d00  test    eax, eax
0x180013d02  jns     short loc_180013D1C
0x180013d04  lea     rcx, [rsp+0B00h+var_AD0]
0x180013d09  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013d0e  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013d13  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013d18  mov     eax, ebx
0x180013d1a  jmp     short loc_180013D7B
0x180013d1c  movzx   r8d, r15w; unsigned __int16 *
0x180013d20  lea     r9, aRegistry; "REGISTRY"
0x180013d27  mov     [rsp+0B00h+var_AC8], r12
0x180013d2c  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180013d30  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013d35  test    r14d, r14d
0x180013d38  jz      short loc_180013D44
0x180013d3a  mov     [rsp+0B00h+var_AE0], 1
0x180013d42  jmp     short loc_180013D49
0x180013d44  mov     [rsp+0B00h+var_AE0], r12d; int
0x180013d49  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180013d4e  lea     rcx, [rsp+0B00h+var_AC8]
0x180013d53  mov     ebx, eax
0x180013d55  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013d5a  jmp     short loc_180013D04
0x180013d5c  call    __report_rangecheckfailure
0x180013d62  lea     rcx, [rsp+0B00h+var_AD0]
0x180013d67  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013d6c  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180013d71  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013d76  mov     eax, 80004005h
0x180013d7b  mov     rcx, [rbp+0A00h+var_30]
0x180013d82  xor     rcx, rsp; StackCookie
0x180013d85  call    __security_check_cookie
0x180013d8a  lea     r11, [rsp+0B00h+var_20]
0x180013d92  mov     rbx, [r11+30h]
0x180013d96  mov     rsi, [r11+40h]
0x180013d9a  mov     rsp, r11
0x180013d9d  pop     r15
0x180013d9f  pop     r14
0x180013da1  pop     r12
0x180013da3  pop     rdi
0x180013da4  pop     rbp
0x180013da5  retn
```
