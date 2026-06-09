# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800120c4`
- end: `0x180012344`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012360`

## callees

- `0x180001fc8`
- `0x18000adb0`
- `0x18000e420`
- `0x18000e9d0`
- `0x18000f178`
- `0x1800100b8`
- `0x1800104bc`
- `0x180010e3c`
- `0x1800120c4`
- `0x1800123b8`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001220f`
- `KERNEL32!GetModuleHandleW` at `0x18001220f`
- `KERNEL32!GetModuleFileNameW` at `0x1800121ca`
- `KERNEL32!GetModuleFileNameW` at `0x1800121ca`

## string_xrefs

- `0x180012311`: `REGISTRY`

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
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
0x1800120c4  push    rbp
0x1800120c6  push    rbx
0x1800120c7  push    rsi
0x1800120c8  push    rdi
0x1800120c9  push    r12
0x1800120cb  push    r14
0x1800120cd  push    r15
0x1800120cf  lea     rbp, [rsp-9E0h]
0x1800120d7  sub     rsp, 0AE0h
0x1800120de  mov     rax, cs:__security_cookie
0x1800120e5  xor     rax, rsp
0x1800120e8  mov     [rbp+0A10h+var_40], rax
0x1800120ef  mov     rbx, r9
0x1800120f2  mov     r15d, r8d
0x1800120f5  mov     rdi, rdx
0x1800120f8  mov     r14, rcx
0x1800120fb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180012102  mov     [rsp+0B10h+var_AD0], rax
0x180012107  xor     r12d, r12d
0x18001210a  mov     [rsp+0B10h+var_AC8], r12
0x18001210f  mov     [rsp+0B10h+var_AC0], r12
0x180012114  mov     [rsp+0B10h+var_AB8], r12d
0x180012119  xorps   xmm0, xmm0
0x18001211c  xor     eax, eax
0x18001211e  movups  [rsp+0B10h+var_AB0], xmm0
0x180012123  movups  [rsp+0B10h+var_AA0], xmm0
0x180012128  mov     [rbp+0A10h+var_A90], rax
0x18001212c  mov     [rbp+0A10h+var_A88], r12b
0x180012130  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180012135  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001213a  mov     esi, eax
0x18001213c  test    eax, eax
0x18001213e  jns     short loc_18001216D
0x180012140  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012145  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001214a  mov     eax, esi
0x18001214c  mov     rcx, [rbp+0A10h+var_40]
0x180012153  xor     rcx, rsp; StackCookie
0x180012156  call    __security_check_cookie
0x18001215b  add     rsp, 0AE0h
0x180012162  pop     r15
0x180012164  pop     r14
0x180012166  pop     r12
0x180012168  pop     rdi
0x180012169  pop     rsi
0x18001216a  pop     rbx
0x18001216b  pop     rbp
0x18001216c  retn
0x18001216d  test    rbx, rbx
0x180012170  jz      short loc_180012191
0x180012172  jmp     short loc_180012189
0x180012174  mov     r8, [rbx+8]; unsigned __int16 *
0x180012178  mov     rdx, rax; unsigned __int16 *
0x18001217b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012180  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012185  lea     rbx, [rbx+10h]
0x180012189  mov     rax, [rbx]
0x18001218c  test    rax, rax
0x18001218f  jnz     short loc_180012174
0x180012191  mov     rax, [r14]
0x180012194  lea     rdx, [rsp+0B10h+var_AD0]
0x180012199  mov     rcx, r14
0x18001219c  mov     rax, [rax+28h]
0x1800121a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121a5  mov     ebx, eax
0x1800121a7  test    eax, eax
0x1800121a9  js      loc_1800122DD
0x1800121af  mov     [rsp+0B10h+var_AE0], r12
0x1800121b4  mov     rbx, cs:hInstance
0x1800121bb  mov     esi, 104h
0x1800121c0  mov     r8d, esi; nSize
0x1800121c3  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800121c7  mov     rcx, rbx; hModule
0x1800121ca  call    cs:__imp_GetModuleFileNameW
0x1800121d0  test    eax, eax
0x1800121d2  jnz     short loc_1800121E0
0x1800121d4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800121d9  mov     ebx, eax
0x1800121db  jmp     loc_1800122D3
0x1800121e0  cmp     eax, esi
0x1800121e2  jnz     short loc_1800121F8
0x1800121e4  lea     rcx, [rsp+0B10h+var_AE0]
0x1800121e9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800121ee  mov     ebx, 8007007Ah
0x1800121f3  jmp     loc_1800122DD
0x1800121f8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800121fc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180012203  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180012208  test    rbx, rbx
0x18001220b  jz      short loc_180012223
0x18001220d  xor     ecx, ecx; lpModuleName
0x18001220f  call    cs:__imp_GetModuleHandleW
0x180012215  cmp     rbx, rax
0x180012218  jz      short loc_180012223
0x18001221a  lea     r8, [rbp+0A10h+var_450]
0x180012221  jmp     short loc_18001229E
0x180012223  mov     ebx, 22h ; '"'
0x180012228  mov     [rbp+0A10h+var_870], bx
0x18001222f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180012236  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001223d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180012242  test    al, al
0x180012244  jnz     short loc_18001225A
0x180012246  lea     rcx, [rsp+0B10h+var_AE0]
0x18001224b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012250  mov     ebx, 80004005h
0x180012255  jmp     loc_1800122DD
0x18001225a  lea     rcx, [rbp+0A10h+var_870]
0x180012261  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012265  inc     rax
0x180012268  cmp     [rcx+rax*2], r12w
0x18001226d  jnz     short loc_180012265
0x18001226f  cdqe
0x180012271  mov     [rbp+rax*2+0A10h+var_870], bx
0x180012279  lea     rcx, ds:2[rax*2]
0x180012281  cmp     rcx, 418h
0x180012288  jnb     loc_18001233E
0x18001228e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180012297  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001229e  lea     rdx, aModule; "Module"
0x1800122a5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800122aa  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800122af  mov     ebx, eax
0x1800122b1  test    eax, eax
0x1800122b3  js      short loc_1800122D3
0x1800122b5  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800122bc  lea     rdx, aModuleRaw; "Module_Raw"
0x1800122c3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800122c8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800122cd  mov     ebx, eax
0x1800122cf  test    eax, eax
0x1800122d1  jns     short loc_1800122EE
0x1800122d3  lea     rcx, [rsp+0B10h+var_AE0]
0x1800122d8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800122dd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800122e2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800122e7  mov     eax, ebx
0x1800122e9  jmp     loc_18001214C
0x1800122ee  mov     [rsp+0B10h+var_AD8], r12
0x1800122f3  test    r15d, r15d
0x1800122f6  jz      short loc_180012307
0x1800122f8  test    rdi, rdi
0x1800122fb  jz      short loc_18001232D
0x1800122fd  mov     [rsp+0B10h+var_AF0], 1
0x180012305  jmp     short loc_180012311
0x180012307  test    rdi, rdi
0x18001230a  jz      short loc_18001232D
0x18001230c  mov     [rsp+0B10h+var_AF0], r12d; int
0x180012311  lea     r9, aRegistry; "REGISTRY"
0x180012318  mov     r8, rdi; unsigned __int16 *
0x18001231b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001231f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180012324  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180012329  mov     ebx, eax
0x18001232b  jmp     short loc_180012332
0x18001232d  mov     ebx, 80070057h
0x180012332  lea     rcx, [rsp+0B10h+var_AD8]
0x180012337  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001233c  jmp     short loc_1800122D3
0x18001233e  call    __report_rangecheckfailure
```
