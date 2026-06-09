# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000b7bc`
- end: `0x18000ba2c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000bcc0`

## callees

- `0x180001a58`
- `0x180002d44`
- `0x180008bf4`
- `0x180008d34`
- `0x180009120`
- `0x180009948`
- `0x18000a1a8`
- `0x18000ac80`
- `0x18000b7bc`
- `0x18000bcdc`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000b8c2`
- `KERNEL32!GetModuleFileNameW` at `0x18000b8c2`
- `KERNEL32!GetModuleHandleW` at `0x18000b907`
- `KERNEL32!GetModuleHandleW` at `0x18000b907`

## string_xrefs

- `0x18000b9ef`: `REGISTRY`

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
        *(unsigned __int16 *)((char *)&v28[-1] + v17) = 0;
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
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
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
0x18000b7bc  push    rbp
0x18000b7be  push    rbx
0x18000b7bf  push    rsi
0x18000b7c0  push    rdi
0x18000b7c1  push    r12
0x18000b7c3  push    r14
0x18000b7c5  push    r15
0x18000b7c7  lea     rbp, [rsp-9E0h]
0x18000b7cf  sub     rsp, 0AE0h
0x18000b7d6  mov     rax, cs:__security_cookie
0x18000b7dd  xor     rax, rsp
0x18000b7e0  mov     [rbp+0A10h+var_40], rax
0x18000b7e7  mov     rbx, r9
0x18000b7ea  mov     r14d, r8d
0x18000b7ed  mov     r15d, edx
0x18000b7f0  mov     rsi, rcx
0x18000b7f3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000b7fa  mov     [rsp+0B10h+var_AD0], rax
0x18000b7ff  xor     r12d, r12d
0x18000b802  mov     [rsp+0B10h+var_AC8], r12
0x18000b807  mov     [rsp+0B10h+var_AC0], r12
0x18000b80c  mov     [rsp+0B10h+var_AB8], r12d
0x18000b811  xorps   xmm0, xmm0
0x18000b814  xor     eax, eax
0x18000b816  movups  [rsp+0B10h+var_AB0], xmm0
0x18000b81b  movups  [rsp+0B10h+var_AA0], xmm0
0x18000b820  mov     [rbp+0A10h+var_A90], rax
0x18000b824  mov     [rbp+0A10h+var_A88], r12b
0x18000b828  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000b82d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000b832  mov     edi, eax
0x18000b834  test    eax, eax
0x18000b836  jns     short loc_18000B865
0x18000b838  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000b83d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b842  mov     eax, edi
0x18000b844  mov     rcx, [rbp+0A10h+var_40]
0x18000b84b  xor     rcx, rsp; StackCookie
0x18000b84e  call    __security_check_cookie
0x18000b853  add     rsp, 0AE0h
0x18000b85a  pop     r15
0x18000b85c  pop     r14
0x18000b85e  pop     r12
0x18000b860  pop     rdi
0x18000b861  pop     rsi
0x18000b862  pop     rbx
0x18000b863  pop     rbp
0x18000b864  retn
0x18000b865  test    rbx, rbx
0x18000b868  jz      short loc_18000B889
0x18000b86a  jmp     short loc_18000B881
0x18000b86c  mov     r8, [rbx+8]; unsigned __int16 *
0x18000b870  mov     rdx, rax; unsigned __int16 *
0x18000b873  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000b878  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000b87d  lea     rbx, [rbx+10h]
0x18000b881  mov     rax, [rbx]
0x18000b884  test    rax, rax
0x18000b887  jnz     short loc_18000B86C
0x18000b889  mov     rax, [rsi]
0x18000b88c  lea     rdx, [rsp+0B10h+var_AD0]
0x18000b891  mov     rcx, rsi
0x18000b894  mov     rax, [rax+28h]
0x18000b898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b89d  mov     ebx, eax
0x18000b89f  test    eax, eax
0x18000b8a1  js      loc_18000B9D5
0x18000b8a7  mov     [rsp+0B10h+var_AE0], r12
0x18000b8ac  mov     rbx, cs:hModule
0x18000b8b3  mov     edi, 104h
0x18000b8b8  mov     r8d, edi; nSize
0x18000b8bb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000b8bf  mov     rcx, rbx; hModule
0x18000b8c2  call    cs:__imp_GetModuleFileNameW
0x18000b8c8  test    eax, eax
0x18000b8ca  jnz     short loc_18000B8D8
0x18000b8cc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b8d1  mov     ebx, eax
0x18000b8d3  jmp     loc_18000B9CB
0x18000b8d8  cmp     eax, edi
0x18000b8da  jnz     short loc_18000B8F0
0x18000b8dc  lea     rcx, [rsp+0B10h+var_AE0]
0x18000b8e1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b8e6  mov     ebx, 8007007Ah
0x18000b8eb  jmp     loc_18000B9D5
0x18000b8f0  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000b8f4  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000b8fb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000b900  test    rbx, rbx
0x18000b903  jz      short loc_18000B91B
0x18000b905  xor     ecx, ecx; lpModuleName
0x18000b907  call    cs:__imp_GetModuleHandleW
0x18000b90d  cmp     rbx, rax
0x18000b910  jz      short loc_18000B91B
0x18000b912  lea     r8, [rbp+0A10h+var_450]
0x18000b919  jmp     short loc_18000B996
0x18000b91b  mov     ebx, 22h ; '"'
0x18000b920  mov     [rbp+0A10h+var_870], bx
0x18000b927  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000b92e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000b935  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000b93a  test    al, al
0x18000b93c  jnz     short loc_18000B952
0x18000b93e  lea     rcx, [rsp+0B10h+var_AE0]
0x18000b943  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b948  mov     ebx, 80004005h
0x18000b94d  jmp     loc_18000B9D5
0x18000b952  lea     rcx, [rbp+0A10h+var_870]
0x18000b959  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b95d  inc     rax
0x18000b960  cmp     [rcx+rax*2], r12w
0x18000b965  jnz     short loc_18000B95D
0x18000b967  cdqe
0x18000b969  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000b971  lea     rcx, ds:2[rax*2]
0x18000b979  cmp     rcx, 418h
0x18000b980  jnb     loc_18000BA26
0x18000b986  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000b98f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000b996  lea     rdx, aModule; "Module"
0x18000b99d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000b9a2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000b9a7  mov     ebx, eax
0x18000b9a9  test    eax, eax
0x18000b9ab  js      short loc_18000B9CB
0x18000b9ad  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000b9b4  lea     rdx, aModuleRaw; "Module_Raw"
0x18000b9bb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000b9c0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000b9c5  mov     ebx, eax
0x18000b9c7  test    eax, eax
0x18000b9c9  jns     short loc_18000B9E6
0x18000b9cb  lea     rcx, [rsp+0B10h+var_AE0]
0x18000b9d0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b9d5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000b9da  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b9df  mov     eax, ebx
0x18000b9e1  jmp     loc_18000B844
0x18000b9e6  movzx   r8d, r15w; unsigned __int16 *
0x18000b9ea  mov     [rsp+0B10h+var_AD8], r12
0x18000b9ef  lea     r9, aRegistry; "REGISTRY"
0x18000b9f6  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000b9fa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000b9ff  test    r14d, r14d
0x18000ba02  jz      short loc_18000BA0E
0x18000ba04  mov     [rsp+0B10h+var_AF0], 1
0x18000ba0c  jmp     short loc_18000BA13
0x18000ba0e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000ba13  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000ba18  mov     ebx, eax
0x18000ba1a  lea     rcx, [rsp+0B10h+var_AD8]
0x18000ba1f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ba24  jmp     short loc_18000B9CB
0x18000ba26  call    __report_rangecheckfailure
```
