# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001bc54`
- end: `0x18001bed4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bef0`

## callees

- `0x180001e80`
- `0x180001ef0`
- `0x180016bd0`
- `0x180016ef0`
- `0x180017650`
- `0x180017f08`
- `0x180018e44`
- `0x1800196ec`
- `0x18001a668`
- `0x18001bc54`
- `0x18001befc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bd5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bd5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bd9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bd9f`

## string_xrefs

- `0x18001bea1`: `REGISTRY`

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
0x18001bc54  push    rbp
0x18001bc56  push    rbx
0x18001bc57  push    rsi
0x18001bc58  push    rdi
0x18001bc59  push    r12
0x18001bc5b  push    r14
0x18001bc5d  push    r15
0x18001bc5f  lea     rbp, [rsp-9E0h]
0x18001bc67  sub     rsp, 0AE0h
0x18001bc6e  mov     rax, cs:__security_cookie
0x18001bc75  xor     rax, rsp
0x18001bc78  mov     [rbp+0A10h+var_40], rax
0x18001bc7f  mov     rbx, r9
0x18001bc82  mov     r15d, r8d
0x18001bc85  mov     rdi, rdx
0x18001bc88  mov     r14, rcx
0x18001bc8b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001bc92  mov     [rsp+0B10h+var_AD0], rax
0x18001bc97  xor     r12d, r12d
0x18001bc9a  mov     [rsp+0B10h+var_AC8], r12
0x18001bc9f  mov     [rsp+0B10h+var_AC0], r12
0x18001bca4  mov     [rsp+0B10h+var_AB8], r12d
0x18001bca9  xorps   xmm0, xmm0
0x18001bcac  xor     eax, eax
0x18001bcae  movups  [rsp+0B10h+var_AB0], xmm0
0x18001bcb3  movups  [rsp+0B10h+var_AA0], xmm0
0x18001bcb8  mov     [rbp+0A10h+var_A90], rax
0x18001bcbc  mov     [rbp+0A10h+var_A88], r12b
0x18001bcc0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001bcc5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001bcca  mov     esi, eax
0x18001bccc  test    eax, eax
0x18001bcce  jns     short loc_18001BCFD
0x18001bcd0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bcd5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001bcda  mov     eax, esi
0x18001bcdc  mov     rcx, [rbp+0A10h+var_40]
0x18001bce3  xor     rcx, rsp; StackCookie
0x18001bce6  call    __security_check_cookie
0x18001bceb  add     rsp, 0AE0h
0x18001bcf2  pop     r15
0x18001bcf4  pop     r14
0x18001bcf6  pop     r12
0x18001bcf8  pop     rdi
0x18001bcf9  pop     rsi
0x18001bcfa  pop     rbx
0x18001bcfb  pop     rbp
0x18001bcfc  retn
0x18001bcfd  test    rbx, rbx
0x18001bd00  jz      short loc_18001BD21
0x18001bd02  jmp     short loc_18001BD19
0x18001bd04  mov     r8, [rbx+8]; unsigned __int16 *
0x18001bd08  mov     rdx, rax; unsigned __int16 *
0x18001bd0b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bd10  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001bd15  lea     rbx, [rbx+10h]
0x18001bd19  mov     rax, [rbx]
0x18001bd1c  test    rax, rax
0x18001bd1f  jnz     short loc_18001BD04
0x18001bd21  mov     rax, [r14]
0x18001bd24  lea     rdx, [rsp+0B10h+var_AD0]
0x18001bd29  mov     rcx, r14
0x18001bd2c  mov     rax, [rax+28h]
0x18001bd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd35  mov     ebx, eax
0x18001bd37  test    eax, eax
0x18001bd39  js      loc_18001BE6D
0x18001bd3f  mov     [rsp+0B10h+var_AE0], r12
0x18001bd44  mov     rbx, cs:hModule
0x18001bd4b  mov     esi, 104h
0x18001bd50  mov     r8d, esi; nSize
0x18001bd53  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001bd57  mov     rcx, rbx; hModule
0x18001bd5a  call    cs:__imp_GetModuleFileNameW
0x18001bd60  test    eax, eax
0x18001bd62  jnz     short loc_18001BD70
0x18001bd64  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001bd69  mov     ebx, eax
0x18001bd6b  jmp     loc_18001BE63
0x18001bd70  cmp     eax, esi
0x18001bd72  jnz     short loc_18001BD88
0x18001bd74  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bd79  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bd7e  mov     ebx, 8007007Ah
0x18001bd83  jmp     loc_18001BE6D
0x18001bd88  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001bd8c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001bd93  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001bd98  test    rbx, rbx
0x18001bd9b  jz      short loc_18001BDB3
0x18001bd9d  xor     ecx, ecx; lpModuleName
0x18001bd9f  call    cs:__imp_GetModuleHandleW
0x18001bda5  cmp     rbx, rax
0x18001bda8  jz      short loc_18001BDB3
0x18001bdaa  lea     r8, [rbp+0A10h+var_450]
0x18001bdb1  jmp     short loc_18001BE2E
0x18001bdb3  mov     ebx, 22h ; '"'
0x18001bdb8  mov     [rbp+0A10h+var_870], bx
0x18001bdbf  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001bdc6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001bdcd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001bdd2  test    al, al
0x18001bdd4  jnz     short loc_18001BDEA
0x18001bdd6  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bddb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bde0  mov     ebx, 80004005h
0x18001bde5  jmp     loc_18001BE6D
0x18001bdea  lea     rcx, [rbp+0A10h+var_870]
0x18001bdf1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bdf5  inc     rax
0x18001bdf8  cmp     [rcx+rax*2], r12w
0x18001bdfd  jnz     short loc_18001BDF5
0x18001bdff  cdqe
0x18001be01  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001be09  lea     rcx, ds:2[rax*2]
0x18001be11  cmp     rcx, 418h
0x18001be18  jnb     loc_18001BECE
0x18001be1e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001be27  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001be2e  lea     rdx, aModule; "Module"
0x18001be35  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001be3a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001be3f  mov     ebx, eax
0x18001be41  test    eax, eax
0x18001be43  js      short loc_18001BE63
0x18001be45  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001be4c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001be53  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001be58  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001be5d  mov     ebx, eax
0x18001be5f  test    eax, eax
0x18001be61  jns     short loc_18001BE7E
0x18001be63  lea     rcx, [rsp+0B10h+var_AE0]
0x18001be68  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001be6d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001be72  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001be77  mov     eax, ebx
0x18001be79  jmp     loc_18001BCDC
0x18001be7e  mov     [rsp+0B10h+var_AD8], r12
0x18001be83  test    r15d, r15d
0x18001be86  jz      short loc_18001BE97
0x18001be88  test    rdi, rdi
0x18001be8b  jz      short loc_18001BEBD
0x18001be8d  mov     [rsp+0B10h+var_AF0], 1
0x18001be95  jmp     short loc_18001BEA1
0x18001be97  test    rdi, rdi
0x18001be9a  jz      short loc_18001BEBD
0x18001be9c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001bea1  lea     r9, aRegistry; "REGISTRY"
0x18001bea8  mov     r8, rdi; unsigned __int16 *
0x18001beab  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001beaf  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001beb4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001beb9  mov     ebx, eax
0x18001bebb  jmp     short loc_18001BEC2
0x18001bebd  mov     ebx, 80070057h
0x18001bec2  lea     rcx, [rsp+0B10h+var_AD8]
0x18001bec7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001becc  jmp     short loc_18001BE63
0x18001bece  call    __report_rangecheckfailure
```
