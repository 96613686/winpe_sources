# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800090ec`
- end: `0x18000935c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800095f0`

## callees

- `0x180001c88`
- `0x180002b00`
- `0x180003188`
- `0x180003d40`
- `0x1800044e8`
- `0x1800064b8`
- `0x180006cd4`
- `0x180007b4c`
- `0x1800090ec`
- `0x180009ea0`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180009237`
- `KERNEL32!GetModuleHandleW` at `0x180009237`
- `KERNEL32!GetModuleFileNameW` at `0x1800091f2`
- `KERNEL32!GetModuleFileNameW` at `0x1800091f2`

## string_xrefs

- `0x18000931f`: `REGISTRY`

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
          _report_rangecheckfailure(v17);
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
0x1800090ec  push    rbp
0x1800090ee  push    rbx
0x1800090ef  push    rsi
0x1800090f0  push    rdi
0x1800090f1  push    r12
0x1800090f3  push    r14
0x1800090f5  push    r15
0x1800090f7  lea     rbp, [rsp-9E0h]
0x1800090ff  sub     rsp, 0AE0h
0x180009106  mov     rax, cs:__security_cookie
0x18000910d  xor     rax, rsp
0x180009110  mov     [rbp+0A10h+var_40], rax
0x180009117  mov     rbx, r9
0x18000911a  mov     r14d, r8d
0x18000911d  mov     r15d, edx
0x180009120  mov     rsi, rcx
0x180009123  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000912a  mov     [rsp+0B10h+var_AD0], rax
0x18000912f  xor     r12d, r12d
0x180009132  mov     [rsp+0B10h+var_AC8], r12
0x180009137  mov     [rsp+0B10h+var_AC0], r12
0x18000913c  mov     [rsp+0B10h+var_AB8], r12d
0x180009141  xorps   xmm0, xmm0
0x180009144  xor     eax, eax
0x180009146  movups  [rsp+0B10h+var_AB0], xmm0
0x18000914b  movups  [rsp+0B10h+var_AA0], xmm0
0x180009150  mov     [rbp+0A10h+var_A90], rax
0x180009154  mov     [rbp+0A10h+var_A88], r12b
0x180009158  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000915d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009162  mov     edi, eax
0x180009164  test    eax, eax
0x180009166  jns     short loc_180009195
0x180009168  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000916d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009172  mov     eax, edi
0x180009174  mov     rcx, [rbp+0A10h+var_40]
0x18000917b  xor     rcx, rsp; StackCookie
0x18000917e  call    __security_check_cookie
0x180009183  add     rsp, 0AE0h
0x18000918a  pop     r15
0x18000918c  pop     r14
0x18000918e  pop     r12
0x180009190  pop     rdi
0x180009191  pop     rsi
0x180009192  pop     rbx
0x180009193  pop     rbp
0x180009194  retn
0x180009195  test    rbx, rbx
0x180009198  jz      short loc_1800091B9
0x18000919a  jmp     short loc_1800091B1
0x18000919c  mov     r8, [rbx+8]; unsigned __int16 *
0x1800091a0  mov     rdx, rax; unsigned __int16 *
0x1800091a3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800091a8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800091ad  lea     rbx, [rbx+10h]
0x1800091b1  mov     rax, [rbx]
0x1800091b4  test    rax, rax
0x1800091b7  jnz     short loc_18000919C
0x1800091b9  mov     rax, [rsi]
0x1800091bc  lea     rdx, [rsp+0B10h+var_AD0]
0x1800091c1  mov     rcx, rsi
0x1800091c4  mov     rax, [rax+28h]
0x1800091c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091cd  mov     ebx, eax
0x1800091cf  test    eax, eax
0x1800091d1  js      loc_180009305
0x1800091d7  mov     [rsp+0B10h+var_AE0], r12
0x1800091dc  mov     rbx, cs:hInstance
0x1800091e3  mov     edi, 104h
0x1800091e8  mov     r8d, edi; nSize
0x1800091eb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800091ef  mov     rcx, rbx; hModule
0x1800091f2  call    cs:__imp_GetModuleFileNameW
0x1800091f8  test    eax, eax
0x1800091fa  jnz     short loc_180009208
0x1800091fc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009201  mov     ebx, eax
0x180009203  jmp     loc_1800092FB
0x180009208  cmp     eax, edi
0x18000920a  jnz     short loc_180009220
0x18000920c  lea     rcx, [rsp+0B10h+var_AE0]
0x180009211  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009216  mov     ebx, 8007007Ah
0x18000921b  jmp     loc_180009305
0x180009220  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180009224  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000922b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180009230  test    rbx, rbx
0x180009233  jz      short loc_18000924B
0x180009235  xor     ecx, ecx; lpModuleName
0x180009237  call    cs:__imp_GetModuleHandleW
0x18000923d  cmp     rbx, rax
0x180009240  jz      short loc_18000924B
0x180009242  lea     r8, [rbp+0A10h+var_450]
0x180009249  jmp     short loc_1800092C6
0x18000924b  mov     ebx, 22h ; '"'
0x180009250  mov     [rbp+0A10h+var_870], bx
0x180009257  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000925e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180009265  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000926a  test    al, al
0x18000926c  jnz     short loc_180009282
0x18000926e  lea     rcx, [rsp+0B10h+var_AE0]
0x180009273  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009278  mov     ebx, 80004005h
0x18000927d  jmp     loc_180009305
0x180009282  lea     rcx, [rbp+0A10h+var_870]
0x180009289  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000928d  inc     rax
0x180009290  cmp     [rcx+rax*2], r12w
0x180009295  jnz     short loc_18000928D
0x180009297  cdqe
0x180009299  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800092a1  lea     rcx, ds:2[rax*2]
0x1800092a9  cmp     rcx, 418h
0x1800092b0  jnb     loc_180009356
0x1800092b6  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800092bf  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x1800092c6  lea     rdx, aModule; "Module"
0x1800092cd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800092d2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800092d7  mov     ebx, eax
0x1800092d9  test    eax, eax
0x1800092db  js      short loc_1800092FB
0x1800092dd  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800092e4  lea     rdx, aModuleRaw; "Module_Raw"
0x1800092eb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800092f0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800092f5  mov     ebx, eax
0x1800092f7  test    eax, eax
0x1800092f9  jns     short loc_180009316
0x1800092fb  lea     rcx, [rsp+0B10h+var_AE0]
0x180009300  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009305  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000930a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000930f  mov     eax, ebx
0x180009311  jmp     loc_180009174
0x180009316  movzx   r8d, r15w; unsigned __int16 *
0x18000931a  mov     [rsp+0B10h+var_AD8], r12
0x18000931f  lea     r9, aRegistry; "REGISTRY"
0x180009326  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000932a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000932f  test    r14d, r14d
0x180009332  jz      short loc_18000933E
0x180009334  mov     [rsp+0B10h+var_AF0], 1
0x18000933c  jmp     short loc_180009343
0x18000933e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180009343  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009348  mov     ebx, eax
0x18000934a  lea     rcx, [rsp+0B10h+var_AD8]
0x18000934f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009354  jmp     short loc_1800092FB
0x180009356  call    __report_rangecheckfailure
```
