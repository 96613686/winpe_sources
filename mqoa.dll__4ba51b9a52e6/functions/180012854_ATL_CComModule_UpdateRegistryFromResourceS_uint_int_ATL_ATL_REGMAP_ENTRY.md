# ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180012854`
- end: `0x1800129ed`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `409`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `12`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800126e0`
- `0x180012700`
- `0x180012720`
- `0x180012740`
- `0x180012760`
- `0x180012780`
- `0x1800127a0`
- `0x1800127c0`
- `0x1800127e0`
- `0x180012800`
- `0x180012820`
- `0x180012840`

## callees

- `0x18000aa00`
- `0x18000b194`
- `0x18000ba00`
- `0x18000c338`
- `0x1800112e8`
- `0x180012854`
- `0x18002737e`
- `0x1800273b0`

## import_xrefs

- `msvcrt!malloc` at `0x1800128a0`
- `msvcrt!malloc` at `0x1800128a0`
- `KERNEL32!GetModuleFileNameW` at `0x1800128d5`
- `KERNEL32!GetModuleFileNameW` at `0x1800128d5`

## string_xrefs

- `0x18001296d`: `REGISTRY`
- `0x18001298c`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CComModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  DWORD ModuleFileNameW; // eax
  int Error; // ebx
  wchar_t *v8; // rcx
  WCHAR v9; // ax
  WCHAR *v10; // rdx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  void *v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+44h] [rbp-BCh]
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v18[528]; // [rsp+270h] [rbp+170h] BYREF

  v16 = 0;
  v14 = 0;
  v15 = 10;
  v13 = malloc(0x50u);
  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(*((HMODULE *)ATL::_pModule + 1), Filename, 0x104u);
  if ( ModuleFileNameW == 260 )
  {
    Error = -2147024785;
  }
  else if ( ModuleFileNameW )
  {
    v8 = v18;
    v9 = Filename[0];
    if ( Filename[0] )
    {
      v10 = Filename;
      do
      {
        *v8++ = v9;
        if ( v9 == 39 )
          *v8++ = 39;
        v9 = *++v10;
      }
      while ( *v10 );
    }
    *v8 = 0;
    Error = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v13, L"Module", v18);
    if ( Error >= 0 )
    {
      v12 = 0;
      if ( a3 )
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v13,
                  Filename,
                  (const wchar_t *)a2,
                  L"REGISTRY",
                  1);
      else
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v13,
                  Filename,
                  (const wchar_t *)a2,
                  L"REGISTRY",
                  0);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v12);
    }
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v13);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v16);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180012854  mov     [rsp-8+arg_0], rbx
0x180012859  mov     [rsp-8+arg_10], rsi
0x18001285e  push    rbp
0x18001285f  push    rdi
0x180012860  push    r14
0x180012862  lea     rbp, [rsp-5A0h]
0x18001286a  sub     rsp, 6A0h
0x180012871  mov     rax, cs:__security_cookie
0x180012878  xor     rax, rsp
0x18001287b  mov     [rbp+5B0h+var_20], rax
0x180012882  mov     edi, r8d
0x180012885  mov     esi, edx
0x180012887  xor     r14d, r14d
0x18001288a  mov     [rsp+6B0h+var_660], r14
0x18001288f  mov     [rsp+6B0h+var_670], r14d
0x180012894  mov     [rsp+6B0h+var_66C], 0Ah
0x18001289c  lea     ecx, [r14+50h]; Size
0x1800128a0  call    cs:__imp_malloc
0x1800128a6  mov     [rsp+6B0h+var_678], rax
0x1800128ab  xor     edx, edx; Val
0x1800128ad  mov     r8d, 20Ah; Size
0x1800128b3  lea     rcx, [rsp+6B0h+Filename]; void *
0x1800128b8  call    memset_0
0x1800128bd  mov     ebx, 104h
0x1800128c2  mov     r8d, ebx; nSize
0x1800128c5  lea     rdx, [rsp+6B0h+Filename]; lpFilename
0x1800128ca  mov     rcx, cs:?_pModule@ATL@@3PEAVCComModule@1@EA; ATL::CComModule * ATL::_pModule
0x1800128d1  mov     rcx, [rcx+8]; hModule
0x1800128d5  call    cs:__imp_GetModuleFileNameW
0x1800128db  cmp     eax, ebx
0x1800128dd  jnz     short loc_1800128E9
0x1800128df  mov     ebx, 8007006Fh
0x1800128e4  jmp     loc_1800129AF
0x1800128e9  test    eax, eax
0x1800128eb  jnz     short loc_1800128F9
0x1800128ed  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800128f2  mov     ebx, eax
0x1800128f4  jmp     loc_1800129AF
0x1800128f9  lea     rcx, [rbp+5B0h+var_440]
0x180012900  movzx   eax, [rsp+6B0h+Filename]
0x180012905  test    ax, ax
0x180012908  jz      short loc_180012936
0x18001290a  lea     rdx, [rsp+6B0h+Filename]
0x18001290f  mov     r8d, 27h ; '''
0x180012915  mov     [rcx], ax
0x180012918  add     rcx, 2
0x18001291c  cmp     ax, r8w
0x180012920  jnz     short loc_18001292A
0x180012922  mov     [rcx], r8w
0x180012926  add     rcx, 2
0x18001292a  add     rdx, 2
0x18001292e  movzx   eax, word ptr [rdx]
0x180012931  test    ax, ax
0x180012934  jnz     short loc_180012915
0x180012936  mov     [rcx], r14w
0x18001293a  lea     r8, [rbp+5B0h+var_440]; wchar_t *
0x180012941  lea     rdx, aModule; "Module"
0x180012948  lea     rcx, [rsp+6B0h+var_678]; this
0x18001294d  call    ?Add@CExpansionVector@ATL@@QEAAJPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180012952  mov     ebx, eax
0x180012954  test    eax, eax
0x180012956  js      short loc_1800129AF
0x180012958  movzx   r8d, si; wchar_t *
0x18001295c  mov     [rsp+6B0h+var_680], r14
0x180012961  test    edi, edi
0x180012963  jz      short loc_180012987
0x180012965  mov     [rsp+6B0h+var_690], 1; int
0x18001296d  lea     r9, aRegistry; "REGISTRY"
0x180012974  lea     rdx, [rsp+6B0h+Filename]; wchar_t *
0x180012979  lea     rcx, [rsp+6B0h+var_678]; this
0x18001297e  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180012983  mov     ebx, eax
0x180012985  jmp     short loc_1800129A4
0x180012987  mov     [rsp+6B0h+var_690], r14d; int
0x18001298c  lea     r9, aRegistry; "REGISTRY"
0x180012993  lea     rdx, [rsp+6B0h+Filename]; wchar_t *
0x180012998  lea     rcx, [rsp+6B0h+var_678]; this
0x18001299d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x1800129a2  mov     ebx, eax
0x1800129a4  lea     rcx, [rsp+6B0h+var_680]
0x1800129a9  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800129ae  nop
0x1800129af  lea     rcx, [rsp+6B0h+var_678]; this
0x1800129b4  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800129b9  nop
0x1800129ba  lea     rcx, [rsp+6B0h+var_660]
0x1800129bf  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800129c4  mov     eax, ebx
0x1800129c6  mov     rcx, [rbp+5B0h+var_20]
0x1800129cd  xor     rcx, rsp; StackCookie
0x1800129d0  call    __security_check_cookie
0x1800129d5  lea     r11, [rsp+6B0h+var_10]
0x1800129dd  mov     rbx, [r11+20h]
0x1800129e1  mov     rsi, [r11+30h]
0x1800129e5  mov     rsp, r11
0x1800129e8  pop     r14
0x1800129ea  pop     rdi
0x1800129eb  pop     rbp
0x1800129ec  retn
```
