# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009364`
- end: `0x1800095e4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009600`

## callees

- `0x180001c88`
- `0x180002b00`
- `0x180003188`
- `0x180003d40`
- `0x1800044e8`
- `0x1800064b8`
- `0x180006cd4`
- `0x180007b4c`
- `0x180009364`
- `0x180009ea0`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800094af`
- `KERNEL32!GetModuleHandleW` at `0x1800094af`
- `KERNEL32!GetModuleFileNameW` at `0x18000946a`
- `KERNEL32!GetModuleFileNameW` at `0x18000946a`

## string_xrefs

- `0x1800095b1`: `REGISTRY`

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
        _report_rangecheckfailure(v17);
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
0x180009364  push    rbp
0x180009366  push    rbx
0x180009367  push    rsi
0x180009368  push    rdi
0x180009369  push    r12
0x18000936b  push    r14
0x18000936d  push    r15
0x18000936f  lea     rbp, [rsp-9E0h]
0x180009377  sub     rsp, 0AE0h
0x18000937e  mov     rax, cs:__security_cookie
0x180009385  xor     rax, rsp
0x180009388  mov     [rbp+0A10h+var_40], rax
0x18000938f  mov     rbx, r9
0x180009392  mov     r15d, r8d
0x180009395  mov     rdi, rdx
0x180009398  mov     r14, rcx
0x18000939b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800093a2  mov     [rsp+0B10h+var_AD0], rax
0x1800093a7  xor     r12d, r12d
0x1800093aa  mov     [rsp+0B10h+var_AC8], r12
0x1800093af  mov     [rsp+0B10h+var_AC0], r12
0x1800093b4  mov     [rsp+0B10h+var_AB8], r12d
0x1800093b9  xorps   xmm0, xmm0
0x1800093bc  xor     eax, eax
0x1800093be  movups  [rsp+0B10h+var_AB0], xmm0
0x1800093c3  movups  [rsp+0B10h+var_AA0], xmm0
0x1800093c8  mov     [rbp+0A10h+var_A90], rax
0x1800093cc  mov     [rbp+0A10h+var_A88], r12b
0x1800093d0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x1800093d5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800093da  mov     esi, eax
0x1800093dc  test    eax, eax
0x1800093de  jns     short loc_18000940D
0x1800093e0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800093e5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800093ea  mov     eax, esi
0x1800093ec  mov     rcx, [rbp+0A10h+var_40]
0x1800093f3  xor     rcx, rsp; StackCookie
0x1800093f6  call    __security_check_cookie
0x1800093fb  add     rsp, 0AE0h
0x180009402  pop     r15
0x180009404  pop     r14
0x180009406  pop     r12
0x180009408  pop     rdi
0x180009409  pop     rsi
0x18000940a  pop     rbx
0x18000940b  pop     rbp
0x18000940c  retn
0x18000940d  test    rbx, rbx
0x180009410  jz      short loc_180009431
0x180009412  jmp     short loc_180009429
0x180009414  mov     r8, [rbx+8]; unsigned __int16 *
0x180009418  mov     rdx, rax; unsigned __int16 *
0x18000941b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009420  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009425  lea     rbx, [rbx+10h]
0x180009429  mov     rax, [rbx]
0x18000942c  test    rax, rax
0x18000942f  jnz     short loc_180009414
0x180009431  mov     rax, [r14]
0x180009434  lea     rdx, [rsp+0B10h+var_AD0]
0x180009439  mov     rcx, r14
0x18000943c  mov     rax, [rax+28h]
0x180009440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009445  mov     ebx, eax
0x180009447  test    eax, eax
0x180009449  js      loc_18000957D
0x18000944f  mov     [rsp+0B10h+var_AE0], r12
0x180009454  mov     rbx, cs:hInstance
0x18000945b  mov     esi, 104h
0x180009460  mov     r8d, esi; nSize
0x180009463  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180009467  mov     rcx, rbx; hModule
0x18000946a  call    cs:__imp_GetModuleFileNameW
0x180009470  test    eax, eax
0x180009472  jnz     short loc_180009480
0x180009474  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009479  mov     ebx, eax
0x18000947b  jmp     loc_180009573
0x180009480  cmp     eax, esi
0x180009482  jnz     short loc_180009498
0x180009484  lea     rcx, [rsp+0B10h+var_AE0]
0x180009489  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000948e  mov     ebx, 8007007Ah
0x180009493  jmp     loc_18000957D
0x180009498  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000949c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800094a3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800094a8  test    rbx, rbx
0x1800094ab  jz      short loc_1800094C3
0x1800094ad  xor     ecx, ecx; lpModuleName
0x1800094af  call    cs:__imp_GetModuleHandleW
0x1800094b5  cmp     rbx, rax
0x1800094b8  jz      short loc_1800094C3
0x1800094ba  lea     r8, [rbp+0A10h+var_450]
0x1800094c1  jmp     short loc_18000953E
0x1800094c3  mov     ebx, 22h ; '"'
0x1800094c8  mov     [rbp+0A10h+var_870], bx
0x1800094cf  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800094d6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x1800094dd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800094e2  test    al, al
0x1800094e4  jnz     short loc_1800094FA
0x1800094e6  lea     rcx, [rsp+0B10h+var_AE0]
0x1800094eb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800094f0  mov     ebx, 80004005h
0x1800094f5  jmp     loc_18000957D
0x1800094fa  lea     rcx, [rbp+0A10h+var_870]
0x180009501  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009505  inc     rax
0x180009508  cmp     [rcx+rax*2], r12w
0x18000950d  jnz     short loc_180009505
0x18000950f  cdqe
0x180009511  mov     [rbp+rax*2+0A10h+var_870], bx
0x180009519  lea     rcx, ds:2[rax*2]
0x180009521  cmp     rcx, 418h
0x180009528  jnb     loc_1800095DE
0x18000952e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180009537  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000953e  lea     rdx, aModule; "Module"
0x180009545  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000954a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000954f  mov     ebx, eax
0x180009551  test    eax, eax
0x180009553  js      short loc_180009573
0x180009555  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000955c  lea     rdx, aModuleRaw; "Module_Raw"
0x180009563  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009568  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000956d  mov     ebx, eax
0x18000956f  test    eax, eax
0x180009571  jns     short loc_18000958E
0x180009573  lea     rcx, [rsp+0B10h+var_AE0]
0x180009578  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000957d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180009582  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009587  mov     eax, ebx
0x180009589  jmp     loc_1800093EC
0x18000958e  mov     [rsp+0B10h+var_AD8], r12
0x180009593  test    r15d, r15d
0x180009596  jz      short loc_1800095A7
0x180009598  test    rdi, rdi
0x18000959b  jz      short loc_1800095CD
0x18000959d  mov     [rsp+0B10h+var_AF0], 1
0x1800095a5  jmp     short loc_1800095B1
0x1800095a7  test    rdi, rdi
0x1800095aa  jz      short loc_1800095CD
0x1800095ac  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800095b1  lea     r9, aRegistry; "REGISTRY"
0x1800095b8  mov     r8, rdi; unsigned __int16 *
0x1800095bb  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800095bf  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800095c4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800095c9  mov     ebx, eax
0x1800095cb  jmp     short loc_1800095D2
0x1800095cd  mov     ebx, 80070057h
0x1800095d2  lea     rcx, [rsp+0B10h+var_AD8]
0x1800095d7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800095dc  jmp     short loc_180009573
0x1800095de  call    __report_rangecheckfailure
```
