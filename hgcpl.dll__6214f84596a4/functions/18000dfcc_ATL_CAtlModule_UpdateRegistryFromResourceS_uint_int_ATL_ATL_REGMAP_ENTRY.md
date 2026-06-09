# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000dfcc`
- end: `0x18000e21b`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `591`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e490`

## callees

- `0x180002c28`
- `0x18000bc5c`
- `0x18000bc94`
- `0x18000bd50`
- `0x18000c050`
- `0x18000c7d8`
- `0x18000cbf4`
- `0x18000ceac`
- `0x18000d5d0`
- `0x18000dfcc`
- `0x18000e4ac`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000e084`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000e084`

## string_xrefs

- `0x18000e1a3`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // eax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v21[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[48]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v25[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v26[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  ATL::CRegObject::CRegObject((ATL::CRegObject *)v21);
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v22);
  if ( v8 < 0 )
  {
    Error = v8;
    goto LABEL_29;
  }
  v22[40] = 1;
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
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _BYTE *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v10 = hModule;
    v19 = 0;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147024774;
        goto LABEL_29;
      }
      ATL::CAtlModule::EscapeSingleQuote(v26, v12, Filename);
      if ( !v10 || v10 == GetModuleHandleW(0) )
      {
        v24 = 34;
        if ( !ocscpy_s(v25, v13, v26) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_29;
        }
        v15 = -1;
        do
          ++v15;
        while ( v25[v15 - 1] );
        v16 = 2LL * (int)v15 + 2;
        v25[(int)v15 - 1] = 34;
        if ( v16 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v25[-1] + v16) = 0;
        v14 = &v24;
      }
      else
      {
        v14 = v26;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v14);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v26);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v17;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  }
LABEL_29:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000dfcc  mov     [rsp-8+arg_10], rbx
0x18000dfd1  push    rbp
0x18000dfd2  push    rsi
0x18000dfd3  push    rdi
0x18000dfd4  push    r14
0x18000dfd6  push    r15
0x18000dfd8  lea     rbp, [rsp-9E0h]
0x18000dfe0  sub     rsp, 0AE0h
0x18000dfe7  mov     rax, cs:__security_cookie
0x18000dfee  xor     rax, rsp
0x18000dff1  mov     [rbp+0A00h+var_30], rax
0x18000dff8  mov     rdi, rcx
0x18000dffb  mov     r14d, edx
0x18000dffe  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e003  mov     rbx, r9
0x18000e006  mov     esi, r8d
0x18000e009  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x18000e00e  lea     rcx, [rsp+0B00h+var_AA0]; this
0x18000e013  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000e018  xor     r15d, r15d
0x18000e01b  test    eax, eax
0x18000e01d  js      loc_18000E1E7
0x18000e023  mov     [rbp+0A00h+var_A78], 1
0x18000e027  test    rbx, rbx
0x18000e02a  jz      short loc_18000E04B
0x18000e02c  jmp     short loc_18000E043
0x18000e02e  mov     r8, [rbx+8]; unsigned __int16 *
0x18000e032  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e037  mov     rdx, rax; unsigned __int16 *
0x18000e03a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000e03f  lea     rbx, [rbx+10h]
0x18000e043  mov     rax, [rbx]
0x18000e046  test    rax, rax
0x18000e049  jnz     short loc_18000E02E
0x18000e04b  mov     rax, [rdi]
0x18000e04e  lea     rdx, [rsp+0B00h+var_AC0]
0x18000e053  mov     rcx, rdi
0x18000e056  mov     rax, [rax+28h]
0x18000e05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e05f  mov     ebx, eax
0x18000e061  test    eax, eax
0x18000e063  js      loc_18000E1E9
0x18000e069  mov     rbx, cs:hModule
0x18000e070  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000e074  mov     edi, 104h
0x18000e079  mov     [rsp+0B00h+var_AD0], r15
0x18000e07e  mov     r8d, edi; nSize
0x18000e081  mov     rcx, rbx; hModule
0x18000e084  call    cs:__imp_GetModuleFileNameW
0x18000e08a  test    eax, eax
0x18000e08c  jnz     short loc_18000E0A4
0x18000e08e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000e093  mov     ebx, eax
0x18000e095  lea     rcx, [rsp+0B00h+var_AD0]
0x18000e09a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e09f  jmp     loc_18000E1E9
0x18000e0a4  cmp     eax, edi
0x18000e0a6  jnz     short loc_18000E0BC
0x18000e0a8  lea     rcx, [rsp+0B00h+var_AD0]
0x18000e0ad  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e0b2  mov     ebx, 8007007Ah
0x18000e0b7  jmp     loc_18000E1E9
0x18000e0bc  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000e0c0  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000e0c7  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000e0cc  test    rbx, rbx
0x18000e0cf  jz      short loc_18000E0E7
0x18000e0d1  xor     ecx, ecx; lpModuleName
0x18000e0d3  call    cs:__imp_GetModuleHandleW
0x18000e0d9  cmp     rbx, rax
0x18000e0dc  jz      short loc_18000E0E7
0x18000e0de  lea     r8, [rbp+0A00h+var_440]
0x18000e0e5  jmp     short loc_18000E162
0x18000e0e7  mov     ebx, 22h ; '"'
0x18000e0ec  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000e0f3  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x18000e0fa  mov     [rbp+0A00h+var_860], bx
0x18000e101  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000e106  test    al, al
0x18000e108  jnz     short loc_18000E11E
0x18000e10a  lea     rcx, [rsp+0B00h+var_AD0]
0x18000e10f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e114  mov     ebx, 80004005h
0x18000e119  jmp     loc_18000E1E9
0x18000e11e  lea     rcx, [rbp+0A00h+var_860]
0x18000e125  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e129  inc     rax
0x18000e12c  cmp     [rcx+rax*2], r15w
0x18000e131  jnz     short loc_18000E129
0x18000e133  cdqe
0x18000e135  lea     rcx, ds:2[rax*2]
0x18000e13d  mov     [rbp+rax*2+0A00h+var_860], bx
0x18000e145  cmp     rcx, 418h
0x18000e14c  jnb     loc_18000E1E1
0x18000e152  mov     [rbp+rcx+0A00h+var_860], r15w
0x18000e15b  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x18000e162  lea     rdx, aModule; "Module"
0x18000e169  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e16e  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000e173  mov     ebx, eax
0x18000e175  test    eax, eax
0x18000e177  js      loc_18000E095
0x18000e17d  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000e184  lea     rdx, aModuleRaw; "Module_Raw"
0x18000e18b  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e190  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000e195  mov     ebx, eax
0x18000e197  test    eax, eax
0x18000e199  js      loc_18000E095
0x18000e19f  movzx   r8d, r14w; unsigned __int16 *
0x18000e1a3  lea     r9, aRegistry; "REGISTRY"
0x18000e1aa  mov     [rsp+0B00h+var_AC8], r15
0x18000e1af  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000e1b3  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e1b8  test    esi, esi
0x18000e1ba  jz      short loc_18000E1C6
0x18000e1bc  mov     [rsp+0B00h+var_AE0], 1
0x18000e1c4  jmp     short loc_18000E1CB
0x18000e1c6  mov     [rsp+0B00h+var_AE0], r15d; int
0x18000e1cb  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000e1d0  lea     rcx, [rsp+0B00h+var_AC8]
0x18000e1d5  mov     ebx, eax
0x18000e1d7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e1dc  jmp     loc_18000E095
0x18000e1e1  call    __report_rangecheckfailure
0x18000e1e7  mov     ebx, eax
0x18000e1e9  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18000e1ee  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000e1f3  mov     eax, ebx
0x18000e1f5  mov     rcx, [rbp+0A00h+var_30]
0x18000e1fc  xor     rcx, rsp; StackCookie
0x18000e1ff  call    __security_check_cookie
0x18000e204  mov     rbx, [rsp+0B00h+arg_10]
0x18000e20c  add     rsp, 0AE0h
0x18000e213  pop     r15
0x18000e215  pop     r14
0x18000e217  pop     rdi
0x18000e218  pop     rsi
0x18000e219  pop     rbp
0x18000e21a  retn
```
