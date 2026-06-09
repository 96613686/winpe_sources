# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001730c`
- end: `0x18001757c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017810`

## callees

- `0x180003368`
- `0x180013378`
- `0x18001350c`
- `0x180013920`
- `0x18001405c`
- `0x180015250`
- `0x1800155b4`
- `0x1800162bc`
- `0x18001730c`
- `0x180017844`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017412`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017412`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017457`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017457`

## string_xrefs

- `0x18001753f`: `REGISTRY`

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
0x18001730c  push    rbp
0x18001730e  push    rbx
0x18001730f  push    rsi
0x180017310  push    rdi
0x180017311  push    r12
0x180017313  push    r14
0x180017315  push    r15
0x180017317  lea     rbp, [rsp-9E0h]
0x18001731f  sub     rsp, 0AE0h
0x180017326  mov     rax, cs:__security_cookie
0x18001732d  xor     rax, rsp
0x180017330  mov     [rbp+0A10h+var_40], rax
0x180017337  mov     rbx, r9
0x18001733a  mov     r14d, r8d
0x18001733d  mov     r15d, edx
0x180017340  mov     rsi, rcx
0x180017343  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001734a  mov     [rsp+0B10h+var_AD0], rax
0x18001734f  xor     r12d, r12d
0x180017352  mov     [rsp+0B10h+var_AC8], r12
0x180017357  mov     [rsp+0B10h+var_AC0], r12
0x18001735c  mov     [rsp+0B10h+var_AB8], r12d
0x180017361  xorps   xmm0, xmm0
0x180017364  xor     eax, eax
0x180017366  movups  [rsp+0B10h+var_AB0], xmm0
0x18001736b  movups  [rsp+0B10h+var_AA0], xmm0
0x180017370  mov     [rbp+0A10h+var_A90], rax
0x180017374  mov     [rbp+0A10h+var_A88], r12b
0x180017378  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001737d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180017382  mov     edi, eax
0x180017384  test    eax, eax
0x180017386  jns     short loc_1800173B5
0x180017388  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001738d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180017392  mov     eax, edi
0x180017394  mov     rcx, [rbp+0A10h+var_40]
0x18001739b  xor     rcx, rsp; StackCookie
0x18001739e  call    __security_check_cookie
0x1800173a3  add     rsp, 0AE0h
0x1800173aa  pop     r15
0x1800173ac  pop     r14
0x1800173ae  pop     r12
0x1800173b0  pop     rdi
0x1800173b1  pop     rsi
0x1800173b2  pop     rbx
0x1800173b3  pop     rbp
0x1800173b4  retn
0x1800173b5  test    rbx, rbx
0x1800173b8  jz      short loc_1800173D9
0x1800173ba  jmp     short loc_1800173D1
0x1800173bc  mov     r8, [rbx+8]; unsigned __int16 *
0x1800173c0  mov     rdx, rax; unsigned __int16 *
0x1800173c3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800173c8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800173cd  lea     rbx, [rbx+10h]
0x1800173d1  mov     rax, [rbx]
0x1800173d4  test    rax, rax
0x1800173d7  jnz     short loc_1800173BC
0x1800173d9  mov     rax, [rsi]
0x1800173dc  lea     rdx, [rsp+0B10h+var_AD0]
0x1800173e1  mov     rcx, rsi
0x1800173e4  mov     rax, [rax+28h]
0x1800173e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173ed  mov     ebx, eax
0x1800173ef  test    eax, eax
0x1800173f1  js      loc_180017525
0x1800173f7  mov     [rsp+0B10h+var_AE0], r12
0x1800173fc  mov     rbx, cs:hInstance
0x180017403  mov     edi, 104h
0x180017408  mov     r8d, edi; nSize
0x18001740b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001740f  mov     rcx, rbx; hModule
0x180017412  call    cs:__imp_GetModuleFileNameW
0x180017418  test    eax, eax
0x18001741a  jnz     short loc_180017428
0x18001741c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017421  mov     ebx, eax
0x180017423  jmp     loc_18001751B
0x180017428  cmp     eax, edi
0x18001742a  jnz     short loc_180017440
0x18001742c  lea     rcx, [rsp+0B10h+var_AE0]
0x180017431  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017436  mov     ebx, 8007007Ah
0x18001743b  jmp     loc_180017525
0x180017440  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180017444  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001744b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180017450  test    rbx, rbx
0x180017453  jz      short loc_18001746B
0x180017455  xor     ecx, ecx; lpModuleName
0x180017457  call    cs:__imp_GetModuleHandleW
0x18001745d  cmp     rbx, rax
0x180017460  jz      short loc_18001746B
0x180017462  lea     r8, [rbp+0A10h+var_450]
0x180017469  jmp     short loc_1800174E6
0x18001746b  mov     ebx, 22h ; '"'
0x180017470  mov     [rbp+0A10h+var_870], bx
0x180017477  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001747e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180017485  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001748a  test    al, al
0x18001748c  jnz     short loc_1800174A2
0x18001748e  lea     rcx, [rsp+0B10h+var_AE0]
0x180017493  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017498  mov     ebx, 80004005h
0x18001749d  jmp     loc_180017525
0x1800174a2  lea     rcx, [rbp+0A10h+var_870]
0x1800174a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800174ad  inc     rax
0x1800174b0  cmp     [rcx+rax*2], r12w
0x1800174b5  jnz     short loc_1800174AD
0x1800174b7  cdqe
0x1800174b9  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800174c1  lea     rcx, ds:2[rax*2]
0x1800174c9  cmp     rcx, 418h
0x1800174d0  jnb     loc_180017576
0x1800174d6  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800174df  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x1800174e6  lea     rdx, aModule; "Module"
0x1800174ed  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800174f2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800174f7  mov     ebx, eax
0x1800174f9  test    eax, eax
0x1800174fb  js      short loc_18001751B
0x1800174fd  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180017504  lea     rdx, aModuleRaw; "Module_Raw"
0x18001750b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180017510  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180017515  mov     ebx, eax
0x180017517  test    eax, eax
0x180017519  jns     short loc_180017536
0x18001751b  lea     rcx, [rsp+0B10h+var_AE0]
0x180017520  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017525  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001752a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001752f  mov     eax, ebx
0x180017531  jmp     loc_180017394
0x180017536  movzx   r8d, r15w; unsigned __int16 *
0x18001753a  mov     [rsp+0B10h+var_AD8], r12
0x18001753f  lea     r9, aRegistry; "REGISTRY"
0x180017546  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001754a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001754f  test    r14d, r14d
0x180017552  jz      short loc_18001755E
0x180017554  mov     [rsp+0B10h+var_AF0], 1
0x18001755c  jmp     short loc_180017563
0x18001755e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180017563  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180017568  mov     ebx, eax
0x18001756a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001756f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017574  jmp     short loc_18001751B
0x180017576  call    __report_rangecheckfailure
```
