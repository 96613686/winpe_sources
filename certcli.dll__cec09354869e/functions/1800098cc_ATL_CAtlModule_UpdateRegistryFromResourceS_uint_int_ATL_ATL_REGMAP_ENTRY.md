# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800098cc`
- end: `0x180009b68`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `668`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009e30`

## callees

- `0x180002078`
- `0x180004e8c`
- `0x18000527c`
- `0x1800057f0`
- `0x180006008`
- `0x180006c58`
- `0x180007494`
- `0x1800086f0`
- `0x1800098cc`
- `0x180009e4c`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800099e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800099e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a2b`

## string_xrefs

- `0x180009b21`: `REGISTRY`
- `0x180009b3f`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  _QWORD *v18; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-C8h] BYREF
  void **v20; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v20 = &ATL::CRegObject::`vftable';
  v19 = v21;
  v21[0] = 0;
  v21[1] = 0;
  v22 = 0;
  v18 = v23;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v23);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)&v20,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v20);
  if ( Error >= 0 )
  {
    v18 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
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
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
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
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v20, L"Module", v15);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v20, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v19 = 0;
          if ( a3 )
            Error = ATL::CRegObject::RegisterFromResource(
                      (ATL::CRegObject *)&v20,
                      Filename,
                      (const unsigned __int16 *)a2,
                      L"REGISTRY",
                      1);
          else
            Error = ATL::CRegObject::RegisterFromResource(
                      (ATL::CRegObject *)&v20,
                      Filename,
                      (const unsigned __int16 *)a2,
                      L"REGISTRY",
                      0);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800098cc  push    rbp
0x1800098ce  push    rbx
0x1800098cf  push    rsi
0x1800098d0  push    rdi
0x1800098d1  push    r12
0x1800098d3  push    r14
0x1800098d5  push    r15
0x1800098d7  lea     rbp, [rsp-9E0h]
0x1800098df  sub     rsp, 0AE0h
0x1800098e6  mov     rax, cs:__security_cookie
0x1800098ed  xor     rax, rsp
0x1800098f0  mov     [rbp+0A10h+var_40], rax
0x1800098f7  mov     rbx, r9
0x1800098fa  mov     r14d, r8d
0x1800098fd  mov     r15d, edx
0x180009900  mov     rsi, rcx
0x180009903  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000990a  mov     [rsp+0B10h+var_AD0], rax
0x18000990f  lea     rax, [rsp+0B10h+var_AC8]
0x180009914  mov     [rsp+0B10h+var_AD8], rax
0x180009919  xor     r12d, r12d
0x18000991c  mov     [rsp+0B10h+var_AC8], r12
0x180009921  mov     [rsp+0B10h+var_AC0], r12
0x180009926  mov     [rsp+0B10h+var_AB8], r12d
0x18000992b  lea     rax, [rsp+0B10h+var_AB0]
0x180009930  mov     [rsp+0B10h+var_AE0], rax
0x180009935  xorps   xmm0, xmm0
0x180009938  xor     eax, eax
0x18000993a  movups  [rsp+0B10h+var_AB0], xmm0
0x18000993f  movups  [rsp+0B10h+var_AA0], xmm0
0x180009944  mov     [rbp+0A10h+var_A90], rax
0x180009948  mov     [rbp+0A10h+var_A88], r12b
0x18000994c  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180009951  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009956  mov     edi, eax
0x180009958  test    eax, eax
0x18000995a  jns     short loc_180009989
0x18000995c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009961  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009966  mov     eax, edi
0x180009968  mov     rcx, [rbp+0A10h+var_40]
0x18000996f  xor     rcx, rsp; StackCookie
0x180009972  call    __security_check_cookie
0x180009977  add     rsp, 0AE0h
0x18000997e  pop     r15
0x180009980  pop     r14
0x180009982  pop     r12
0x180009984  pop     rdi
0x180009985  pop     rsi
0x180009986  pop     rbx
0x180009987  pop     rbp
0x180009988  retn
0x180009989  test    rbx, rbx
0x18000998c  jz      short loc_1800099AD
0x18000998e  jmp     short loc_1800099A5
0x180009990  mov     r8, [rbx+8]; unsigned __int16 *
0x180009994  mov     rdx, rax; unsigned __int16 *
0x180009997  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000999c  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800099a1  lea     rbx, [rbx+10h]
0x1800099a5  mov     rax, [rbx]
0x1800099a8  test    rax, rax
0x1800099ab  jnz     short loc_180009990
0x1800099ad  mov     rax, [rsi]
0x1800099b0  lea     rdx, [rsp+0B10h+var_AD0]
0x1800099b5  mov     rcx, rsi
0x1800099b8  mov     rax, [rax+28h]
0x1800099bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c1  mov     ebx, eax
0x1800099c3  test    eax, eax
0x1800099c5  js      loc_180009AFA
0x1800099cb  mov     [rsp+0B10h+var_AE0], r12
0x1800099d0  mov     rbx, cs:hModule
0x1800099d7  mov     edi, 104h
0x1800099dc  mov     r8d, edi; nSize
0x1800099df  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800099e3  mov     rcx, rbx; hModule
0x1800099e6  call    cs:__imp_GetModuleFileNameW
0x1800099ec  test    eax, eax
0x1800099ee  jnz     short loc_1800099FC
0x1800099f0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800099f5  mov     ebx, eax
0x1800099f7  jmp     loc_180009AEF
0x1800099fc  cmp     eax, edi
0x1800099fe  jnz     short loc_180009A14
0x180009a00  lea     rcx, [rsp+0B10h+var_AE0]
0x180009a05  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009a0a  mov     ebx, 8007007Ah
0x180009a0f  jmp     loc_180009AFA
0x180009a14  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009a18  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009a1f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180009a24  test    rbx, rbx
0x180009a27  jz      short loc_180009A3F
0x180009a29  xor     ecx, ecx; lpModuleName
0x180009a2b  call    cs:__imp_GetModuleHandleW
0x180009a31  cmp     rbx, rax
0x180009a34  jz      short loc_180009A3F
0x180009a36  lea     r8, [rbp+0A10h+var_450]
0x180009a3d  jmp     short loc_180009ABA
0x180009a3f  mov     ebx, 22h ; '"'
0x180009a44  mov     [rbp+0A10h+var_870], bx
0x180009a4b  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009a52  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180009a59  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180009a5e  test    al, al
0x180009a60  jnz     short loc_180009A76
0x180009a62  lea     rcx, [rsp+0B10h+var_AE0]
0x180009a67  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009a6c  mov     ebx, 80004005h
0x180009a71  jmp     loc_180009AFA
0x180009a76  lea     rcx, [rbp+0A10h+var_870]
0x180009a7d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a81  inc     rax
0x180009a84  cmp     [rcx+rax*2], r12w
0x180009a89  jnz     short loc_180009A81
0x180009a8b  cdqe
0x180009a8d  mov     [rbp+rax*2+0A10h+var_870], bx
0x180009a95  lea     rcx, ds:2[rax*2]
0x180009a9d  cmp     rcx, 418h
0x180009aa4  jnb     loc_180009B62
0x180009aaa  mov     [rbp+rcx+0A10h+var_870], r12w
0x180009ab3  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180009aba  lea     rdx, aModule; "Module"
0x180009ac1  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009ac6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009acb  mov     ebx, eax
0x180009acd  test    eax, eax
0x180009acf  js      short loc_180009AEF
0x180009ad1  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180009ad8  lea     rdx, aModuleRaw; "Module_Raw"
0x180009adf  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009ae4  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009ae9  mov     ebx, eax
0x180009aeb  test    eax, eax
0x180009aed  jns     short loc_180009B0B
0x180009aef  lea     rcx, [rsp+0B10h+var_AE0]
0x180009af4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009af9  nop
0x180009afa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009aff  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009b04  mov     eax, ebx
0x180009b06  jmp     loc_180009968
0x180009b0b  movzx   r8d, r15w; unsigned __int16 *
0x180009b0f  mov     [rsp+0B10h+var_AD8], r12
0x180009b14  test    r14d, r14d
0x180009b17  jz      short loc_180009B3A
0x180009b19  mov     [rsp+0B10h+var_AF0], 1; int
0x180009b21  lea     r9, aRegistry; "REGISTRY"
0x180009b28  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009b2c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009b31  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009b36  mov     ebx, eax
0x180009b38  jmp     short loc_180009B56
0x180009b3a  mov     [rsp+0B10h+var_AF0], r12d; int
0x180009b3f  lea     r9, aRegistry; "REGISTRY"
0x180009b46  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009b4a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009b4f  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009b54  mov     ebx, eax
0x180009b56  lea     rcx, [rsp+0B10h+var_AD8]
0x180009b5b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009b60  jmp     short loc_180009AEF
0x180009b62  call    __report_rangecheckfailure
```
