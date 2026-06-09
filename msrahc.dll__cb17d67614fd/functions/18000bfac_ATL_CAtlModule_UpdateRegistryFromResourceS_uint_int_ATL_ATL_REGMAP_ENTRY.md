# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000bfac`
- end: `0x18000c21c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000bf80`
- `0x18000c4b0`

## callees

- `0x180001f88`
- `0x18000882c`
- `0x180008a2c`
- `0x180008e80`
- `0x1800096f4`
- `0x18000a450`
- `0x18000a970`
- `0x18000b1f4`
- `0x18000bfac`
- `0x18000c4cc`
- `0x18001a5e0`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000c0b2`
- `KERNEL32!GetModuleFileNameW` at `0x18000c0b2`
- `KERNEL32!GetModuleHandleW` at `0x18000c0f7`
- `KERNEL32!GetModuleHandleW` at `0x18000c0f7`

## string_xrefs

- `0x18000c1df`: `REGISTRY`

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
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v27[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v28[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(&v23, 0, sizeof(v23));
  v24 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init(&v23);
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
      ATL::CAtlModule::EscapeSingleQuote(v28, v13, Filename);
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v26 = 34;
        if ( !ocscpy_s(v27, v14, v28) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_24;
        }
        v16 = -1;
        do
          ++v16;
        while ( v27[v16 - 1] );
        v27[(int)v16 - 1] = 34;
        v17 = 2LL * (int)v16 + 2;
        if ( v17 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v27[-1] + v17) = 0;
        v15 = &v26;
      }
      else
      {
        v15 = v28;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v28);
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
0x18000bfac  push    rbp
0x18000bfae  push    rbx
0x18000bfaf  push    rsi
0x18000bfb0  push    rdi
0x18000bfb1  push    r12
0x18000bfb3  push    r14
0x18000bfb5  push    r15
0x18000bfb7  lea     rbp, [rsp-9E0h]
0x18000bfbf  sub     rsp, 0AE0h
0x18000bfc6  mov     rax, cs:__security_cookie
0x18000bfcd  xor     rax, rsp
0x18000bfd0  mov     [rbp+0A10h+var_40], rax
0x18000bfd7  mov     rbx, r9
0x18000bfda  mov     r14d, r8d
0x18000bfdd  mov     r15d, edx
0x18000bfe0  mov     rsi, rcx
0x18000bfe3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000bfea  mov     [rsp+0B10h+var_AD0], rax
0x18000bfef  xor     r12d, r12d
0x18000bff2  mov     [rsp+0B10h+var_AC8], r12
0x18000bff7  mov     [rsp+0B10h+var_AC0], r12
0x18000bffc  mov     [rsp+0B10h+var_AB8], r12d
0x18000c001  xorps   xmm0, xmm0
0x18000c004  xor     eax, eax
0x18000c006  movups  [rsp+0B10h+var_AB0], xmm0
0x18000c00b  movups  [rsp+0B10h+var_AA0], xmm0
0x18000c010  mov     [rbp+0A10h+var_A90], rax
0x18000c014  mov     [rbp+0A10h+var_A88], r12b
0x18000c018  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000c01d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000c022  mov     edi, eax
0x18000c024  test    eax, eax
0x18000c026  jns     short loc_18000C055
0x18000c028  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c02d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c032  mov     eax, edi
0x18000c034  mov     rcx, [rbp+0A10h+var_40]
0x18000c03b  xor     rcx, rsp; StackCookie
0x18000c03e  call    __security_check_cookie
0x18000c043  add     rsp, 0AE0h
0x18000c04a  pop     r15
0x18000c04c  pop     r14
0x18000c04e  pop     r12
0x18000c050  pop     rdi
0x18000c051  pop     rsi
0x18000c052  pop     rbx
0x18000c053  pop     rbp
0x18000c054  retn
0x18000c055  test    rbx, rbx
0x18000c058  jz      short loc_18000C079
0x18000c05a  jmp     short loc_18000C071
0x18000c05c  mov     r8, [rbx+8]; unsigned __int16 *
0x18000c060  mov     rdx, rax; unsigned __int16 *
0x18000c063  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c068  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c06d  lea     rbx, [rbx+10h]
0x18000c071  mov     rax, [rbx]
0x18000c074  test    rax, rax
0x18000c077  jnz     short loc_18000C05C
0x18000c079  mov     rax, [rsi]
0x18000c07c  lea     rdx, [rsp+0B10h+var_AD0]
0x18000c081  mov     rcx, rsi
0x18000c084  mov     rax, [rax+28h]
0x18000c088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c08d  mov     ebx, eax
0x18000c08f  test    eax, eax
0x18000c091  js      loc_18000C1C5
0x18000c097  mov     [rsp+0B10h+var_AE0], r12
0x18000c09c  mov     rbx, cs:hModule
0x18000c0a3  mov     edi, 104h
0x18000c0a8  mov     r8d, edi; nSize
0x18000c0ab  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000c0af  mov     rcx, rbx; hModule
0x18000c0b2  call    cs:__imp_GetModuleFileNameW
0x18000c0b8  test    eax, eax
0x18000c0ba  jnz     short loc_18000C0C8
0x18000c0bc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c0c1  mov     ebx, eax
0x18000c0c3  jmp     loc_18000C1BB
0x18000c0c8  cmp     eax, edi
0x18000c0ca  jnz     short loc_18000C0E0
0x18000c0cc  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c0d1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c0d6  mov     ebx, 8007007Ah
0x18000c0db  jmp     loc_18000C1C5
0x18000c0e0  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c0e4  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c0eb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000c0f0  test    rbx, rbx
0x18000c0f3  jz      short loc_18000C10B
0x18000c0f5  xor     ecx, ecx; lpModuleName
0x18000c0f7  call    cs:__imp_GetModuleHandleW
0x18000c0fd  cmp     rbx, rax
0x18000c100  jz      short loc_18000C10B
0x18000c102  lea     r8, [rbp+0A10h+var_450]
0x18000c109  jmp     short loc_18000C186
0x18000c10b  mov     ebx, 22h ; '"'
0x18000c110  mov     [rbp+0A10h+var_870], bx
0x18000c117  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c11e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000c125  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000c12a  test    al, al
0x18000c12c  jnz     short loc_18000C142
0x18000c12e  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c133  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c138  mov     ebx, 80004005h
0x18000c13d  jmp     loc_18000C1C5
0x18000c142  lea     rcx, [rbp+0A10h+var_870]
0x18000c149  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c14d  inc     rax
0x18000c150  cmp     [rcx+rax*2], r12w
0x18000c155  jnz     short loc_18000C14D
0x18000c157  cdqe
0x18000c159  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000c161  lea     rcx, ds:2[rax*2]
0x18000c169  cmp     rcx, 418h
0x18000c170  jnb     loc_18000C216
0x18000c176  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000c17f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000c186  lea     rdx, aModule; "Module"
0x18000c18d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c192  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c197  mov     ebx, eax
0x18000c199  test    eax, eax
0x18000c19b  js      short loc_18000C1BB
0x18000c19d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c1a4  lea     rdx, aModuleRaw; "Module_Raw"
0x18000c1ab  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1b0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c1b5  mov     ebx, eax
0x18000c1b7  test    eax, eax
0x18000c1b9  jns     short loc_18000C1D6
0x18000c1bb  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c1c0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c1c5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1ca  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c1cf  mov     eax, ebx
0x18000c1d1  jmp     loc_18000C034
0x18000c1d6  movzx   r8d, r15w; unsigned __int16 *
0x18000c1da  mov     [rsp+0B10h+var_AD8], r12
0x18000c1df  lea     r9, aRegistry; "REGISTRY"
0x18000c1e6  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c1ea  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1ef  test    r14d, r14d
0x18000c1f2  jz      short loc_18000C1FE
0x18000c1f4  mov     [rsp+0B10h+var_AF0], 1
0x18000c1fc  jmp     short loc_18000C203
0x18000c1fe  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000c203  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000c208  mov     ebx, eax
0x18000c20a  lea     rcx, [rsp+0B10h+var_AD8]
0x18000c20f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c214  jmp     short loc_18000C1BB
0x18000c216  call    __report_rangecheckfailure
```
