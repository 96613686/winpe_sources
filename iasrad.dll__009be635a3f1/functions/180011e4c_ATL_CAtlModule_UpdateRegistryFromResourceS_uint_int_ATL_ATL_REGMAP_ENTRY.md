# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180011e4c`
- end: `0x1800120bc`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012350`

## callees

- `0x180001fc8`
- `0x18000adb0`
- `0x18000e420`
- `0x18000e9d0`
- `0x18000f178`
- `0x1800100b8`
- `0x1800104bc`
- `0x180010e3c`
- `0x180011e4c`
- `0x1800123b8`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180011f97`
- `KERNEL32!GetModuleHandleW` at `0x180011f97`
- `KERNEL32!GetModuleFileNameW` at `0x180011f52`
- `KERNEL32!GetModuleFileNameW` at `0x180011f52`

## string_xrefs

- `0x18001207f`: `REGISTRY`

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
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
0x180011e4c  push    rbp
0x180011e4e  push    rbx
0x180011e4f  push    rsi
0x180011e50  push    rdi
0x180011e51  push    r12
0x180011e53  push    r14
0x180011e55  push    r15
0x180011e57  lea     rbp, [rsp-9E0h]
0x180011e5f  sub     rsp, 0AE0h
0x180011e66  mov     rax, cs:__security_cookie
0x180011e6d  xor     rax, rsp
0x180011e70  mov     [rbp+0A10h+var_40], rax
0x180011e77  mov     rbx, r9
0x180011e7a  mov     r14d, r8d
0x180011e7d  mov     r15d, edx
0x180011e80  mov     rsi, rcx
0x180011e83  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180011e8a  mov     [rsp+0B10h+var_AD0], rax
0x180011e8f  xor     r12d, r12d
0x180011e92  mov     [rsp+0B10h+var_AC8], r12
0x180011e97  mov     [rsp+0B10h+var_AC0], r12
0x180011e9c  mov     [rsp+0B10h+var_AB8], r12d
0x180011ea1  xorps   xmm0, xmm0
0x180011ea4  xor     eax, eax
0x180011ea6  movups  [rsp+0B10h+var_AB0], xmm0
0x180011eab  movups  [rsp+0B10h+var_AA0], xmm0
0x180011eb0  mov     [rbp+0A10h+var_A90], rax
0x180011eb4  mov     [rbp+0A10h+var_A88], r12b
0x180011eb8  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180011ebd  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180011ec2  mov     edi, eax
0x180011ec4  test    eax, eax
0x180011ec6  jns     short loc_180011EF5
0x180011ec8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180011ecd  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180011ed2  mov     eax, edi
0x180011ed4  mov     rcx, [rbp+0A10h+var_40]
0x180011edb  xor     rcx, rsp; StackCookie
0x180011ede  call    __security_check_cookie
0x180011ee3  add     rsp, 0AE0h
0x180011eea  pop     r15
0x180011eec  pop     r14
0x180011eee  pop     r12
0x180011ef0  pop     rdi
0x180011ef1  pop     rsi
0x180011ef2  pop     rbx
0x180011ef3  pop     rbp
0x180011ef4  retn
0x180011ef5  test    rbx, rbx
0x180011ef8  jz      short loc_180011F19
0x180011efa  jmp     short loc_180011F11
0x180011efc  mov     r8, [rbx+8]; unsigned __int16 *
0x180011f00  mov     rdx, rax; unsigned __int16 *
0x180011f03  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180011f08  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180011f0d  lea     rbx, [rbx+10h]
0x180011f11  mov     rax, [rbx]
0x180011f14  test    rax, rax
0x180011f17  jnz     short loc_180011EFC
0x180011f19  mov     rax, [rsi]
0x180011f1c  lea     rdx, [rsp+0B10h+var_AD0]
0x180011f21  mov     rcx, rsi
0x180011f24  mov     rax, [rax+28h]
0x180011f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f2d  mov     ebx, eax
0x180011f2f  test    eax, eax
0x180011f31  js      loc_180012065
0x180011f37  mov     [rsp+0B10h+var_AE0], r12
0x180011f3c  mov     rbx, cs:hInstance
0x180011f43  mov     edi, 104h
0x180011f48  mov     r8d, edi; nSize
0x180011f4b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180011f4f  mov     rcx, rbx; hModule
0x180011f52  call    cs:__imp_GetModuleFileNameW
0x180011f58  test    eax, eax
0x180011f5a  jnz     short loc_180011F68
0x180011f5c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011f61  mov     ebx, eax
0x180011f63  jmp     loc_18001205B
0x180011f68  cmp     eax, edi
0x180011f6a  jnz     short loc_180011F80
0x180011f6c  lea     rcx, [rsp+0B10h+var_AE0]
0x180011f71  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011f76  mov     ebx, 8007007Ah
0x180011f7b  jmp     loc_180012065
0x180011f80  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180011f84  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180011f8b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180011f90  test    rbx, rbx
0x180011f93  jz      short loc_180011FAB
0x180011f95  xor     ecx, ecx; lpModuleName
0x180011f97  call    cs:__imp_GetModuleHandleW
0x180011f9d  cmp     rbx, rax
0x180011fa0  jz      short loc_180011FAB
0x180011fa2  lea     r8, [rbp+0A10h+var_450]
0x180011fa9  jmp     short loc_180012026
0x180011fab  mov     ebx, 22h ; '"'
0x180011fb0  mov     [rbp+0A10h+var_870], bx
0x180011fb7  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180011fbe  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180011fc5  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180011fca  test    al, al
0x180011fcc  jnz     short loc_180011FE2
0x180011fce  lea     rcx, [rsp+0B10h+var_AE0]
0x180011fd3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011fd8  mov     ebx, 80004005h
0x180011fdd  jmp     loc_180012065
0x180011fe2  lea     rcx, [rbp+0A10h+var_870]
0x180011fe9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011fed  inc     rax
0x180011ff0  cmp     [rcx+rax*2], r12w
0x180011ff5  jnz     short loc_180011FED
0x180011ff7  cdqe
0x180011ff9  mov     [rbp+rax*2+0A10h+var_870], bx
0x180012001  lea     rcx, ds:2[rax*2]
0x180012009  cmp     rcx, 418h
0x180012010  jnb     loc_1800120B6
0x180012016  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001201f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180012026  lea     rdx, aModule; "Module"
0x18001202d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012032  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012037  mov     ebx, eax
0x180012039  test    eax, eax
0x18001203b  js      short loc_18001205B
0x18001203d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180012044  lea     rdx, aModuleRaw; "Module_Raw"
0x18001204b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012050  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012055  mov     ebx, eax
0x180012057  test    eax, eax
0x180012059  jns     short loc_180012076
0x18001205b  lea     rcx, [rsp+0B10h+var_AE0]
0x180012060  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012065  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001206a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001206f  mov     eax, ebx
0x180012071  jmp     loc_180011ED4
0x180012076  movzx   r8d, r15w; unsigned __int16 *
0x18001207a  mov     [rsp+0B10h+var_AD8], r12
0x18001207f  lea     r9, aRegistry; "REGISTRY"
0x180012086  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001208a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001208f  test    r14d, r14d
0x180012092  jz      short loc_18001209E
0x180012094  mov     [rsp+0B10h+var_AF0], 1
0x18001209c  jmp     short loc_1800120A3
0x18001209e  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800120a3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800120a8  mov     ebx, eax
0x1800120aa  lea     rcx, [rsp+0B10h+var_AD8]
0x1800120af  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800120b4  jmp     short loc_18001205B
0x1800120b6  call    __report_rangecheckfailure
```
