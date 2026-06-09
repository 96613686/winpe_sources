# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800099bc`
- end: `0x180009c2c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009990`
- `0x180009ec0`

## callees

- `0x180001d98`
- `0x180006688`
- `0x180006890`
- `0x180006d80`
- `0x1800075e0`
- `0x18000802c`
- `0x180008324`
- `0x180008c20`
- `0x1800099bc`
- `0x180009edc`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009ac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009ac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b07`

## string_xrefs

- `0x180009bef`: `REGISTRY`

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
0x1800099bc  push    rbp
0x1800099be  push    rbx
0x1800099bf  push    rsi
0x1800099c0  push    rdi
0x1800099c1  push    r12
0x1800099c3  push    r14
0x1800099c5  push    r15
0x1800099c7  lea     rbp, [rsp-9E0h]
0x1800099cf  sub     rsp, 0AE0h
0x1800099d6  mov     rax, cs:__security_cookie
0x1800099dd  xor     rax, rsp
0x1800099e0  mov     [rbp+0A10h+var_40], rax
0x1800099e7  mov     rbx, r9
0x1800099ea  mov     r14d, r8d
0x1800099ed  mov     r15d, edx
0x1800099f0  mov     rsi, rcx
0x1800099f3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800099fa  mov     [rsp+0B10h+var_AD0], rax
0x1800099ff  xor     r12d, r12d
0x180009a02  mov     [rsp+0B10h+var_AC8], r12
0x180009a07  mov     [rsp+0B10h+var_AC0], r12
0x180009a0c  mov     [rsp+0B10h+var_AB8], r12d
0x180009a11  xorps   xmm0, xmm0
0x180009a14  xor     eax, eax
0x180009a16  movups  [rsp+0B10h+var_AB0], xmm0
0x180009a1b  movups  [rsp+0B10h+var_AA0], xmm0
0x180009a20  mov     [rbp+0A10h+var_A90], rax
0x180009a24  mov     [rbp+0A10h+var_A88], r12b
0x180009a28  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180009a2d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009a32  mov     edi, eax
0x180009a34  test    eax, eax
0x180009a36  jns     short loc_180009A65
0x180009a38  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009a3d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009a42  mov     eax, edi
0x180009a44  mov     rcx, [rbp+0A10h+var_40]
0x180009a4b  xor     rcx, rsp; StackCookie
0x180009a4e  call    __security_check_cookie
0x180009a53  add     rsp, 0AE0h
0x180009a5a  pop     r15
0x180009a5c  pop     r14
0x180009a5e  pop     r12
0x180009a60  pop     rdi
0x180009a61  pop     rsi
0x180009a62  pop     rbx
0x180009a63  pop     rbp
0x180009a64  retn
0x180009a65  test    rbx, rbx
0x180009a68  jz      short loc_180009A89
0x180009a6a  jmp     short loc_180009A81
0x180009a6c  mov     r8, [rbx+8]; unsigned __int16 *
0x180009a70  mov     rdx, rax; unsigned __int16 *
0x180009a73  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009a78  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009a7d  lea     rbx, [rbx+10h]
0x180009a81  mov     rax, [rbx]
0x180009a84  test    rax, rax
0x180009a87  jnz     short loc_180009A6C
0x180009a89  mov     rax, [rsi]
0x180009a8c  lea     rdx, [rsp+0B10h+var_AD0]
0x180009a91  mov     rcx, rsi
0x180009a94  mov     rax, [rax+28h]
0x180009a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a9d  mov     ebx, eax
0x180009a9f  test    eax, eax
0x180009aa1  js      loc_180009BD5
0x180009aa7  mov     [rsp+0B10h+var_AE0], r12
0x180009aac  mov     rbx, cs:hModule
0x180009ab3  mov     edi, 104h
0x180009ab8  mov     r8d, edi; nSize
0x180009abb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180009abf  mov     rcx, rbx; hModule
0x180009ac2  call    cs:__imp_GetModuleFileNameW
0x180009ac8  test    eax, eax
0x180009aca  jnz     short loc_180009AD8
0x180009acc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009ad1  mov     ebx, eax
0x180009ad3  jmp     loc_180009BCB
0x180009ad8  cmp     eax, edi
0x180009ada  jnz     short loc_180009AF0
0x180009adc  lea     rcx, [rsp+0B10h+var_AE0]
0x180009ae1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009ae6  mov     ebx, 8007007Ah
0x180009aeb  jmp     loc_180009BD5
0x180009af0  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009af4  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009afb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180009b00  test    rbx, rbx
0x180009b03  jz      short loc_180009B1B
0x180009b05  xor     ecx, ecx; lpModuleName
0x180009b07  call    cs:__imp_GetModuleHandleW
0x180009b0d  cmp     rbx, rax
0x180009b10  jz      short loc_180009B1B
0x180009b12  lea     r8, [rbp+0A10h+var_450]
0x180009b19  jmp     short loc_180009B96
0x180009b1b  mov     ebx, 22h ; '"'
0x180009b20  mov     [rbp+0A10h+var_870], bx
0x180009b27  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009b2e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180009b35  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180009b3a  test    al, al
0x180009b3c  jnz     short loc_180009B52
0x180009b3e  lea     rcx, [rsp+0B10h+var_AE0]
0x180009b43  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009b48  mov     ebx, 80004005h
0x180009b4d  jmp     loc_180009BD5
0x180009b52  lea     rcx, [rbp+0A10h+var_870]
0x180009b59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009b5d  inc     rax
0x180009b60  cmp     [rcx+rax*2], r12w
0x180009b65  jnz     short loc_180009B5D
0x180009b67  cdqe
0x180009b69  mov     [rbp+rax*2+0A10h+var_870], bx
0x180009b71  lea     rcx, ds:2[rax*2]
0x180009b79  cmp     rcx, 418h
0x180009b80  jnb     loc_180009C26
0x180009b86  mov     [rbp+rcx+0A10h+var_870], r12w
0x180009b8f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180009b96  lea     rdx, aModule; "Module"
0x180009b9d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009ba2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009ba7  mov     ebx, eax
0x180009ba9  test    eax, eax
0x180009bab  js      short loc_180009BCB
0x180009bad  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009bb4  lea     rdx, aModuleRaw; "Module_Raw"
0x180009bbb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009bc0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009bc5  mov     ebx, eax
0x180009bc7  test    eax, eax
0x180009bc9  jns     short loc_180009BE6
0x180009bcb  lea     rcx, [rsp+0B10h+var_AE0]
0x180009bd0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009bd5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009bda  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009bdf  mov     eax, ebx
0x180009be1  jmp     loc_180009A44
0x180009be6  movzx   r8d, r15w; unsigned __int16 *
0x180009bea  mov     [rsp+0B10h+var_AD8], r12
0x180009bef  lea     r9, aRegistry; "REGISTRY"
0x180009bf6  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009bfa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009bff  test    r14d, r14d
0x180009c02  jz      short loc_180009C0E
0x180009c04  mov     [rsp+0B10h+var_AF0], 1
0x180009c0c  jmp     short loc_180009C13
0x180009c0e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180009c13  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009c18  mov     ebx, eax
0x180009c1a  lea     rcx, [rsp+0B10h+var_AD8]
0x180009c1f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009c24  jmp     short loc_180009BCB
0x180009c26  call    __report_rangecheckfailure
```
