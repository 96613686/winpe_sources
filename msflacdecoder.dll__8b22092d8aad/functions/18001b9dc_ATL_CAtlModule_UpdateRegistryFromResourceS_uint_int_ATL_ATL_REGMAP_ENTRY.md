# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001b9dc`
- end: `0x18001bc4c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b9b0`
- `0x18001bee0`

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
- `0x18001b9dc`
- `0x18001befc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bae2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bae2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bb27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bb27`

## string_xrefs

- `0x18001bc0f`: `REGISTRY`

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
0x18001b9dc  push    rbp
0x18001b9de  push    rbx
0x18001b9df  push    rsi
0x18001b9e0  push    rdi
0x18001b9e1  push    r12
0x18001b9e3  push    r14
0x18001b9e5  push    r15
0x18001b9e7  lea     rbp, [rsp-9E0h]
0x18001b9ef  sub     rsp, 0AE0h
0x18001b9f6  mov     rax, cs:__security_cookie
0x18001b9fd  xor     rax, rsp
0x18001ba00  mov     [rbp+0A10h+var_40], rax
0x18001ba07  mov     rbx, r9
0x18001ba0a  mov     r14d, r8d
0x18001ba0d  mov     r15d, edx
0x18001ba10  mov     rsi, rcx
0x18001ba13  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001ba1a  mov     [rsp+0B10h+var_AD0], rax
0x18001ba1f  xor     r12d, r12d
0x18001ba22  mov     [rsp+0B10h+var_AC8], r12
0x18001ba27  mov     [rsp+0B10h+var_AC0], r12
0x18001ba2c  mov     [rsp+0B10h+var_AB8], r12d
0x18001ba31  xorps   xmm0, xmm0
0x18001ba34  xor     eax, eax
0x18001ba36  movups  [rsp+0B10h+var_AB0], xmm0
0x18001ba3b  movups  [rsp+0B10h+var_AA0], xmm0
0x18001ba40  mov     [rbp+0A10h+var_A90], rax
0x18001ba44  mov     [rbp+0A10h+var_A88], r12b
0x18001ba48  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001ba4d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001ba52  mov     edi, eax
0x18001ba54  test    eax, eax
0x18001ba56  jns     short loc_18001BA85
0x18001ba58  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ba5d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001ba62  mov     eax, edi
0x18001ba64  mov     rcx, [rbp+0A10h+var_40]
0x18001ba6b  xor     rcx, rsp; StackCookie
0x18001ba6e  call    __security_check_cookie
0x18001ba73  add     rsp, 0AE0h
0x18001ba7a  pop     r15
0x18001ba7c  pop     r14
0x18001ba7e  pop     r12
0x18001ba80  pop     rdi
0x18001ba81  pop     rsi
0x18001ba82  pop     rbx
0x18001ba83  pop     rbp
0x18001ba84  retn
0x18001ba85  test    rbx, rbx
0x18001ba88  jz      short loc_18001BAA9
0x18001ba8a  jmp     short loc_18001BAA1
0x18001ba8c  mov     r8, [rbx+8]; unsigned __int16 *
0x18001ba90  mov     rdx, rax; unsigned __int16 *
0x18001ba93  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ba98  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ba9d  lea     rbx, [rbx+10h]
0x18001baa1  mov     rax, [rbx]
0x18001baa4  test    rax, rax
0x18001baa7  jnz     short loc_18001BA8C
0x18001baa9  mov     rax, [rsi]
0x18001baac  lea     rdx, [rsp+0B10h+var_AD0]
0x18001bab1  mov     rcx, rsi
0x18001bab4  mov     rax, [rax+28h]
0x18001bab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001babd  mov     ebx, eax
0x18001babf  test    eax, eax
0x18001bac1  js      loc_18001BBF5
0x18001bac7  mov     [rsp+0B10h+var_AE0], r12
0x18001bacc  mov     rbx, cs:hModule
0x18001bad3  mov     edi, 104h
0x18001bad8  mov     r8d, edi; nSize
0x18001badb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001badf  mov     rcx, rbx; hModule
0x18001bae2  call    cs:__imp_GetModuleFileNameW
0x18001bae8  test    eax, eax
0x18001baea  jnz     short loc_18001BAF8
0x18001baec  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001baf1  mov     ebx, eax
0x18001baf3  jmp     loc_18001BBEB
0x18001baf8  cmp     eax, edi
0x18001bafa  jnz     short loc_18001BB10
0x18001bafc  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bb01  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bb06  mov     ebx, 8007007Ah
0x18001bb0b  jmp     loc_18001BBF5
0x18001bb10  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001bb14  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001bb1b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001bb20  test    rbx, rbx
0x18001bb23  jz      short loc_18001BB3B
0x18001bb25  xor     ecx, ecx; lpModuleName
0x18001bb27  call    cs:__imp_GetModuleHandleW
0x18001bb2d  cmp     rbx, rax
0x18001bb30  jz      short loc_18001BB3B
0x18001bb32  lea     r8, [rbp+0A10h+var_450]
0x18001bb39  jmp     short loc_18001BBB6
0x18001bb3b  mov     ebx, 22h ; '"'
0x18001bb40  mov     [rbp+0A10h+var_870], bx
0x18001bb47  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001bb4e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001bb55  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001bb5a  test    al, al
0x18001bb5c  jnz     short loc_18001BB72
0x18001bb5e  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bb63  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bb68  mov     ebx, 80004005h
0x18001bb6d  jmp     loc_18001BBF5
0x18001bb72  lea     rcx, [rbp+0A10h+var_870]
0x18001bb79  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bb7d  inc     rax
0x18001bb80  cmp     [rcx+rax*2], r12w
0x18001bb85  jnz     short loc_18001BB7D
0x18001bb87  cdqe
0x18001bb89  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001bb91  lea     rcx, ds:2[rax*2]
0x18001bb99  cmp     rcx, 418h
0x18001bba0  jnb     loc_18001BC46
0x18001bba6  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001bbaf  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001bbb6  lea     rdx, aModule; "Module"
0x18001bbbd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bbc2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001bbc7  mov     ebx, eax
0x18001bbc9  test    eax, eax
0x18001bbcb  js      short loc_18001BBEB
0x18001bbcd  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001bbd4  lea     rdx, aModuleRaw; "Module_Raw"
0x18001bbdb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bbe0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001bbe5  mov     ebx, eax
0x18001bbe7  test    eax, eax
0x18001bbe9  jns     short loc_18001BC06
0x18001bbeb  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bbf0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bbf5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bbfa  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001bbff  mov     eax, ebx
0x18001bc01  jmp     loc_18001BA64
0x18001bc06  movzx   r8d, r15w; unsigned __int16 *
0x18001bc0a  mov     [rsp+0B10h+var_AD8], r12
0x18001bc0f  lea     r9, aRegistry; "REGISTRY"
0x18001bc16  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001bc1a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bc1f  test    r14d, r14d
0x18001bc22  jz      short loc_18001BC2E
0x18001bc24  mov     [rsp+0B10h+var_AF0], 1
0x18001bc2c  jmp     short loc_18001BC33
0x18001bc2e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001bc33  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001bc38  mov     ebx, eax
0x18001bc3a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001bc3f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bc44  jmp     short loc_18001BBEB
0x18001bc46  call    __report_rangecheckfailure
```
