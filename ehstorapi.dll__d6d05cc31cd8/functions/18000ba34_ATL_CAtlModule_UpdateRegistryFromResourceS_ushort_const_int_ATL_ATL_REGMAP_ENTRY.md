# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000ba34`
- end: `0x18000bcb4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000bcd0`

## callees

- `0x180001a58`
- `0x180002d44`
- `0x180008bf4`
- `0x180008d34`
- `0x180009120`
- `0x180009948`
- `0x18000a1a8`
- `0x18000ac80`
- `0x18000ba34`
- `0x18000bcdc`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000bb3a`
- `KERNEL32!GetModuleFileNameW` at `0x18000bb3a`
- `KERNEL32!GetModuleHandleW` at `0x18000bb7f`
- `KERNEL32!GetModuleHandleW` at `0x18000bb7f`

## string_xrefs

- `0x18000bc81`: `REGISTRY`

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
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
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
0x18000ba34  push    rbp
0x18000ba36  push    rbx
0x18000ba37  push    rsi
0x18000ba38  push    rdi
0x18000ba39  push    r12
0x18000ba3b  push    r14
0x18000ba3d  push    r15
0x18000ba3f  lea     rbp, [rsp-9E0h]
0x18000ba47  sub     rsp, 0AE0h
0x18000ba4e  mov     rax, cs:__security_cookie
0x18000ba55  xor     rax, rsp
0x18000ba58  mov     [rbp+0A10h+var_40], rax
0x18000ba5f  mov     rbx, r9
0x18000ba62  mov     r15d, r8d
0x18000ba65  mov     rdi, rdx
0x18000ba68  mov     r14, rcx
0x18000ba6b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000ba72  mov     [rsp+0B10h+var_AD0], rax
0x18000ba77  xor     r12d, r12d
0x18000ba7a  mov     [rsp+0B10h+var_AC8], r12
0x18000ba7f  mov     [rsp+0B10h+var_AC0], r12
0x18000ba84  mov     [rsp+0B10h+var_AB8], r12d
0x18000ba89  xorps   xmm0, xmm0
0x18000ba8c  xor     eax, eax
0x18000ba8e  movups  [rsp+0B10h+var_AB0], xmm0
0x18000ba93  movups  [rsp+0B10h+var_AA0], xmm0
0x18000ba98  mov     [rbp+0A10h+var_A90], rax
0x18000ba9c  mov     [rbp+0A10h+var_A88], r12b
0x18000baa0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000baa5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000baaa  mov     esi, eax
0x18000baac  test    eax, eax
0x18000baae  jns     short loc_18000BADD
0x18000bab0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000bab5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000baba  mov     eax, esi
0x18000babc  mov     rcx, [rbp+0A10h+var_40]
0x18000bac3  xor     rcx, rsp; StackCookie
0x18000bac6  call    __security_check_cookie
0x18000bacb  add     rsp, 0AE0h
0x18000bad2  pop     r15
0x18000bad4  pop     r14
0x18000bad6  pop     r12
0x18000bad8  pop     rdi
0x18000bad9  pop     rsi
0x18000bada  pop     rbx
0x18000badb  pop     rbp
0x18000badc  retn
0x18000badd  test    rbx, rbx
0x18000bae0  jz      short loc_18000BB01
0x18000bae2  jmp     short loc_18000BAF9
0x18000bae4  mov     r8, [rbx+8]; unsigned __int16 *
0x18000bae8  mov     rdx, rax; unsigned __int16 *
0x18000baeb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000baf0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000baf5  lea     rbx, [rbx+10h]
0x18000baf9  mov     rax, [rbx]
0x18000bafc  test    rax, rax
0x18000baff  jnz     short loc_18000BAE4
0x18000bb01  mov     rax, [r14]
0x18000bb04  lea     rdx, [rsp+0B10h+var_AD0]
0x18000bb09  mov     rcx, r14
0x18000bb0c  mov     rax, [rax+28h]
0x18000bb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb15  mov     ebx, eax
0x18000bb17  test    eax, eax
0x18000bb19  js      loc_18000BC4D
0x18000bb1f  mov     [rsp+0B10h+var_AE0], r12
0x18000bb24  mov     rbx, cs:hModule
0x18000bb2b  mov     esi, 104h
0x18000bb30  mov     r8d, esi; nSize
0x18000bb33  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000bb37  mov     rcx, rbx; hModule
0x18000bb3a  call    cs:__imp_GetModuleFileNameW
0x18000bb40  test    eax, eax
0x18000bb42  jnz     short loc_18000BB50
0x18000bb44  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bb49  mov     ebx, eax
0x18000bb4b  jmp     loc_18000BC43
0x18000bb50  cmp     eax, esi
0x18000bb52  jnz     short loc_18000BB68
0x18000bb54  lea     rcx, [rsp+0B10h+var_AE0]
0x18000bb59  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000bb5e  mov     ebx, 8007007Ah
0x18000bb63  jmp     loc_18000BC4D
0x18000bb68  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000bb6c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000bb73  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000bb78  test    rbx, rbx
0x18000bb7b  jz      short loc_18000BB93
0x18000bb7d  xor     ecx, ecx; lpModuleName
0x18000bb7f  call    cs:__imp_GetModuleHandleW
0x18000bb85  cmp     rbx, rax
0x18000bb88  jz      short loc_18000BB93
0x18000bb8a  lea     r8, [rbp+0A10h+var_450]
0x18000bb91  jmp     short loc_18000BC0E
0x18000bb93  mov     ebx, 22h ; '"'
0x18000bb98  mov     [rbp+0A10h+var_870], bx
0x18000bb9f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000bba6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000bbad  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000bbb2  test    al, al
0x18000bbb4  jnz     short loc_18000BBCA
0x18000bbb6  lea     rcx, [rsp+0B10h+var_AE0]
0x18000bbbb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000bbc0  mov     ebx, 80004005h
0x18000bbc5  jmp     loc_18000BC4D
0x18000bbca  lea     rcx, [rbp+0A10h+var_870]
0x18000bbd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bbd5  inc     rax
0x18000bbd8  cmp     [rcx+rax*2], r12w
0x18000bbdd  jnz     short loc_18000BBD5
0x18000bbdf  cdqe
0x18000bbe1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000bbe9  lea     rcx, ds:2[rax*2]
0x18000bbf1  cmp     rcx, 418h
0x18000bbf8  jnb     loc_18000BCAE
0x18000bbfe  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000bc07  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000bc0e  lea     rdx, aModule; "Module"
0x18000bc15  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000bc1a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000bc1f  mov     ebx, eax
0x18000bc21  test    eax, eax
0x18000bc23  js      short loc_18000BC43
0x18000bc25  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000bc2c  lea     rdx, aModuleRaw; "Module_Raw"
0x18000bc33  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000bc38  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000bc3d  mov     ebx, eax
0x18000bc3f  test    eax, eax
0x18000bc41  jns     short loc_18000BC5E
0x18000bc43  lea     rcx, [rsp+0B10h+var_AE0]
0x18000bc48  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000bc4d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000bc52  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000bc57  mov     eax, ebx
0x18000bc59  jmp     loc_18000BABC
0x18000bc5e  mov     [rsp+0B10h+var_AD8], r12
0x18000bc63  test    r15d, r15d
0x18000bc66  jz      short loc_18000BC77
0x18000bc68  test    rdi, rdi
0x18000bc6b  jz      short loc_18000BC9D
0x18000bc6d  mov     [rsp+0B10h+var_AF0], 1
0x18000bc75  jmp     short loc_18000BC81
0x18000bc77  test    rdi, rdi
0x18000bc7a  jz      short loc_18000BC9D
0x18000bc7c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000bc81  lea     r9, aRegistry; "REGISTRY"
0x18000bc88  mov     r8, rdi; unsigned __int16 *
0x18000bc8b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000bc8f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000bc94  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000bc99  mov     ebx, eax
0x18000bc9b  jmp     short loc_18000BCA2
0x18000bc9d  mov     ebx, 80070057h
0x18000bca2  lea     rcx, [rsp+0B10h+var_AD8]
0x18000bca7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000bcac  jmp     short loc_18000BC43
0x18000bcae  call    __report_rangecheckfailure
```
