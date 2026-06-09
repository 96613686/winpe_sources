# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180017f7c`
- end: `0x1800181fc`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `20`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017d10`
- `0x180017d30`
- `0x180017d50`
- `0x180017d70`
- `0x180017d90`
- `0x180017db0`
- `0x180017dd0`
- `0x180017df0`
- `0x180017e10`
- `0x180017e30`
- `0x180017e50`
- `0x180017e70`
- `0x180017e90`
- `0x180017eb0`
- `0x180017ed0`
- `0x180017ef0`
- `0x180017f10`
- `0x180017f30`
- `0x180017f50`
- `0x1800184a0`

## callees

- `0x180001710`
- `0x180001a10`
- `0x180002320`
- `0x1800071a0`
- `0x18000867c`
- `0x18000a110`
- `0x18000a984`
- `0x18000fe28`
- `0x18001186c`
- `0x180014b7c`
- `0x180017f7c`
- `0x180018db0`
- `0x180036010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180018092`
- `KERNEL32!GetModuleFileNameW` at `0x180018092`
- `KERNEL32!GetModuleHandleW` at `0x1800180d7`
- `KERNEL32!GetModuleHandleW` at `0x1800180d7`

## string_xrefs

- `0x1800181bf`: `REGISTRY`

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

  memset_0(v21, 0, 0x50u);
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
0x180017f7c  push    rbp
0x180017f7e  push    rbx
0x180017f7f  push    rsi
0x180017f80  push    rdi
0x180017f81  push    r12
0x180017f83  push    r14
0x180017f85  push    r15
0x180017f87  lea     rbp, [rsp-9E0h]
0x180017f8f  sub     rsp, 0AE0h
0x180017f96  mov     rax, cs:__security_cookie
0x180017f9d  xor     rax, rsp
0x180017fa0  mov     [rbp+0A10h+var_40], rax
0x180017fa7  mov     rbx, r9
0x180017faa  mov     r14d, r8d
0x180017fad  mov     r15d, edx
0x180017fb0  mov     rsi, rcx
0x180017fb3  xor     edx, edx; Val
0x180017fb5  lea     r8d, [rdx+50h]; Size
0x180017fb9  lea     rcx, [rsp+0B10h+var_AD0]; void *
0x180017fbe  call    memset_0
0x180017fc3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180017fca  mov     [rsp+0B10h+var_AD0], rax
0x180017fcf  xor     r12d, r12d
0x180017fd2  mov     [rsp+0B10h+var_AC8], r12
0x180017fd7  mov     [rsp+0B10h+var_AC0], r12
0x180017fdc  mov     [rsp+0B10h+var_AB8], r12d
0x180017fe1  xorps   xmm0, xmm0
0x180017fe4  xor     eax, eax
0x180017fe6  movups  [rsp+0B10h+var_AB0], xmm0
0x180017feb  movups  [rsp+0B10h+var_AA0], xmm0
0x180017ff0  mov     [rbp+0A10h+var_A90], rax
0x180017ff4  mov     [rbp+0A10h+var_A88], r12b
0x180017ff8  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180017ffd  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180018002  mov     edi, eax
0x180018004  test    eax, eax
0x180018006  jns     short loc_180018035
0x180018008  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001800d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180018012  mov     eax, edi
0x180018014  mov     rcx, [rbp+0A10h+var_40]
0x18001801b  xor     rcx, rsp; StackCookie
0x18001801e  call    __security_check_cookie
0x180018023  add     rsp, 0AE0h
0x18001802a  pop     r15
0x18001802c  pop     r14
0x18001802e  pop     r12
0x180018030  pop     rdi
0x180018031  pop     rsi
0x180018032  pop     rbx
0x180018033  pop     rbp
0x180018034  retn
0x180018035  test    rbx, rbx
0x180018038  jz      short loc_180018059
0x18001803a  jmp     short loc_180018051
0x18001803c  mov     r8, [rbx+8]; unsigned __int16 *
0x180018040  mov     rdx, rax; unsigned __int16 *
0x180018043  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018048  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001804d  lea     rbx, [rbx+10h]
0x180018051  mov     rax, [rbx]
0x180018054  test    rax, rax
0x180018057  jnz     short loc_18001803C
0x180018059  mov     rax, [rsi]
0x18001805c  lea     rdx, [rsp+0B10h+var_AD0]
0x180018061  mov     rcx, rsi
0x180018064  mov     rax, [rax+28h]
0x180018068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001806d  mov     ebx, eax
0x18001806f  test    eax, eax
0x180018071  js      loc_1800181A5
0x180018077  mov     [rsp+0B10h+var_AE0], r12
0x18001807c  mov     rbx, cs:hModule
0x180018083  mov     edi, 104h
0x180018088  mov     r8d, edi; nSize
0x18001808b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001808f  mov     rcx, rbx; hModule
0x180018092  call    cs:__imp_GetModuleFileNameW
0x180018098  test    eax, eax
0x18001809a  jnz     short loc_1800180A8
0x18001809c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800180a1  mov     ebx, eax
0x1800180a3  jmp     loc_18001819B
0x1800180a8  cmp     eax, edi
0x1800180aa  jnz     short loc_1800180C0
0x1800180ac  lea     rcx, [rsp+0B10h+var_AE0]
0x1800180b1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800180b6  mov     ebx, 8007007Ah
0x1800180bb  jmp     loc_1800181A5
0x1800180c0  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800180c4  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800180cb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800180d0  test    rbx, rbx
0x1800180d3  jz      short loc_1800180EB
0x1800180d5  xor     ecx, ecx; lpModuleName
0x1800180d7  call    cs:__imp_GetModuleHandleW
0x1800180dd  cmp     rbx, rax
0x1800180e0  jz      short loc_1800180EB
0x1800180e2  lea     r8, [rbp+0A10h+var_450]
0x1800180e9  jmp     short loc_180018166
0x1800180eb  mov     ebx, 22h ; '"'
0x1800180f0  mov     [rbp+0A10h+var_870], bx
0x1800180f7  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800180fe  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180018105  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001810a  test    al, al
0x18001810c  jnz     short loc_180018122
0x18001810e  lea     rcx, [rsp+0B10h+var_AE0]
0x180018113  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018118  mov     ebx, 80004005h
0x18001811d  jmp     loc_1800181A5
0x180018122  lea     rcx, [rbp+0A10h+var_870]
0x180018129  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001812d  inc     rax
0x180018130  cmp     [rcx+rax*2], r12w
0x180018135  jnz     short loc_18001812D
0x180018137  cdqe
0x180018139  mov     [rbp+rax*2+0A10h+var_870], bx
0x180018141  lea     rcx, ds:2[rax*2]
0x180018149  cmp     rcx, 418h
0x180018150  jnb     loc_1800181F6
0x180018156  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001815f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180018166  lea     rdx, aModule; "Module"
0x18001816d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018172  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180018177  mov     ebx, eax
0x180018179  test    eax, eax
0x18001817b  js      short loc_18001819B
0x18001817d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180018184  lea     rdx, aModuleRaw; "Module_Raw"
0x18001818b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180018190  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180018195  mov     ebx, eax
0x180018197  test    eax, eax
0x180018199  jns     short loc_1800181B6
0x18001819b  lea     rcx, [rsp+0B10h+var_AE0]
0x1800181a0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800181a5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800181aa  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800181af  mov     eax, ebx
0x1800181b1  jmp     loc_180018014
0x1800181b6  movzx   r8d, r15w; unsigned __int16 *
0x1800181ba  mov     [rsp+0B10h+var_AD8], r12
0x1800181bf  lea     r9, aRegistry; "REGISTRY"
0x1800181c6  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800181ca  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800181cf  test    r14d, r14d
0x1800181d2  jz      short loc_1800181DE
0x1800181d4  mov     [rsp+0B10h+var_AF0], 1
0x1800181dc  jmp     short loc_1800181E3
0x1800181de  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800181e3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800181e8  mov     ebx, eax
0x1800181ea  lea     rcx, [rsp+0B10h+var_AD8]
0x1800181ef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800181f4  jmp     short loc_18001819B
0x1800181f6  call    __report_rangecheckfailure
```
