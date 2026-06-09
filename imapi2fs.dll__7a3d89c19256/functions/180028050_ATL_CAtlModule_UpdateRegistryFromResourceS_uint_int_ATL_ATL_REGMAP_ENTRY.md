# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180028050`
- end: `0x180028307`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `695`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `13`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18002800c`
- `0x18002a9d0`
- `0x18002a9f0`
- `0x18002aa10`
- `0x18002aa30`
- `0x18002aa50`
- `0x18002aa70`
- `0x18002aa90`
- `0x18002d700`
- `0x18002d720`
- `0x18002d740`
- `0x18002d760`
- `0x18002d780`

## callees

- `0x180019034`
- `0x180024ca8`
- `0x180025934`
- `0x180025a24`
- `0x180025cf0`
- `0x1800275c0`
- `0x180028050`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800281e6`
- `msvcrt!memcpy_s` at `0x1800281e6`
- `KERNEL32!GetModuleHandleW` at `0x180028190`
- `KERNEL32!GetModuleHandleW` at `0x180028190`
- `KERNEL32!GetModuleFileNameW` at `0x18002810a`
- `KERNEL32!GetModuleFileNameW` at `0x18002810a`

## string_xrefs

- `0x18002828b`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  struct ATL::CAtlModule *v7; // rdi
  const unsigned __int16 *i; // rax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // r8
  unsigned __int16 *v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  void **v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 Source[520]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v28; // [rsp+690h] [rbp+590h] BYREF
  _BYTE Destination[1054]; // [rsp+692h] [rbp+592h] BYREF

  v4 = a4;
  v23 = &ATL::CRegObject::`vftable';
  v24 = 0;
  v25 = 0;
  v7 = ATL::_pAtlModule;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v23, i, v4[1]);
      v4 += 2;
    }
  }
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v7 + 40LL))(v7, &v23);
  if ( Error < 0 )
    goto LABEL_28;
  v21 = 0;
  v10 = (HMODULE)hInstance;
  ModuleFileNameW = GetModuleFileNameW((HMODULE)hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_27:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    goto LABEL_28;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    Error = -2147024774;
LABEL_28:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v23);
    return (unsigned int)Error;
  }
  v12 = Filename;
  v13 = 0;
  do
  {
    v14 = *v12;
    if ( !*v12 )
      break;
    Source[v13] = v14;
    if ( v14 == 39 && (unsigned int)v13 < 0x206 )
    {
      LODWORD(v13) = v13 + 1;
      Source[(unsigned int)v13] = 39;
    }
    ++v12;
    v13 = (unsigned int)(v13 + 1);
  }
  while ( (unsigned int)v13 < 0x207 );
  Source[v13] = 0;
  if ( v10 && v10 != GetModuleHandleW(0) )
  {
    v15 = Source;
LABEL_25:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v23, L"Module", v15);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v23, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v22 = 0;
        if ( a3 )
          v20 = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  1);
        else
          v20 = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  0);
        Error = v20;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v22);
      }
    }
    goto LABEL_27;
  }
  v28 = 34;
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( Source[v17] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v17 + 1)) )
  {
    do
      ++v16;
    while ( *(_WORD *)&Destination[2 * v16 - 2] );
    *(_WORD *)&Destination[2 * (int)v16 - 2] = 34;
    v18 = 2LL * (int)v16 + 2;
    if ( v18 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v18 - 2] = 0;
    v15 = &v28;
    goto LABEL_25;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v23);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180028050  mov     [rsp-8+arg_0], rbx
0x180028055  push    rbp
0x180028056  push    rsi
0x180028057  push    rdi
0x180028058  push    r14
0x18002805a  push    r15
0x18002805c  lea     rbp, [rsp-9C0h]
0x180028064  sub     rsp, 0AC0h
0x18002806b  mov     rax, cs:__security_cookie
0x180028072  xor     rax, rsp
0x180028075  mov     [rbp+9E0h+var_30], rax
0x18002807c  mov     rbx, r9
0x18002807f  mov     esi, r8d
0x180028082  mov     r14d, edx
0x180028085  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002808c  mov     [rsp+0AE0h+var_AA0], rax
0x180028091  xorps   xmm0, xmm0
0x180028094  movdqu  [rsp+0AE0h+var_A98], xmm0
0x18002809a  xor     r15d, r15d
0x18002809d  mov     [rsp+0AE0h+var_A88], r15d
0x1800280a2  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800280a9  test    r9, r9
0x1800280ac  jz      short loc_1800280D0
0x1800280ae  mov     rax, [r9]
0x1800280b1  jmp     short loc_1800280CB
0x1800280b3  mov     r8, [rbx+8]; unsigned __int16 *
0x1800280b7  mov     rdx, rax; unsigned __int16 *
0x1800280ba  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800280bf  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800280c4  lea     rbx, [rbx+10h]
0x1800280c8  mov     rax, [rbx]
0x1800280cb  test    rax, rax
0x1800280ce  jnz     short loc_1800280B3
0x1800280d0  mov     rax, [rdi]
0x1800280d3  lea     rdx, [rsp+0AE0h+var_AA0]
0x1800280d8  mov     rcx, rdi
0x1800280db  mov     rax, [rax+28h]
0x1800280df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e4  mov     ebx, eax
0x1800280e6  test    eax, eax
0x1800280e8  js      loc_180028274
0x1800280ee  mov     [rsp+0AE0h+var_AB0], r15
0x1800280f3  mov     rbx, cs:hInstance
0x1800280fa  mov     edi, 104h
0x1800280ff  mov     r8d, edi; nSize
0x180028102  lea     rdx, [rsp+0AE0h+Filename]; lpFilename
0x180028107  mov     rcx, rbx; hModule
0x18002810a  call    cs:__imp_GetModuleFileNameW
0x180028110  test    eax, eax
0x180028112  jnz     short loc_180028120
0x180028114  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028119  mov     ebx, eax
0x18002811b  jmp     loc_18002826A
0x180028120  cmp     eax, edi
0x180028122  jnz     short loc_180028138
0x180028124  lea     rcx, [rsp+0AE0h+var_AB0]
0x180028129  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002812e  mov     ebx, 8007007Ah
0x180028133  jmp     loc_180028274
0x180028138  lea     rdx, [rsp+0AE0h+Filename]
0x18002813d  mov     ecx, r15d
0x180028140  mov     r9d, 27h ; '''
0x180028146  movzx   r8d, word ptr [rdx]
0x18002814a  test    r8w, r8w
0x18002814e  jz      short loc_180028180
0x180028150  mov     [rbp+rcx*2+9E0h+Source], r8w
0x180028159  cmp     r8w, r9w
0x18002815d  jnz     short loc_180028172
0x18002815f  cmp     ecx, 206h
0x180028165  jnb     short loc_180028172
0x180028167  inc     ecx
0x180028169  mov     [rbp+rcx*2+9E0h+Source], r9w
0x180028172  add     rdx, 2
0x180028176  inc     ecx
0x180028178  cmp     ecx, 207h
0x18002817e  jb      short loc_180028146
0x180028180  mov     [rbp+rcx*2+9E0h+Source], r15w
0x180028189  test    rbx, rbx
0x18002818c  jz      short loc_1800281A7
0x18002818e  xor     ecx, ecx; lpModuleName
0x180028190  call    cs:__imp_GetModuleHandleW
0x180028196  cmp     rbx, rax
0x180028199  jz      short loc_1800281A7
0x18002819b  lea     r8, [rbp+9E0h+Source]
0x1800281a2  jmp     loc_180028235
0x1800281a7  mov     edi, 22h ; '"'
0x1800281ac  mov     [rbp+9E0h+var_450], di
0x1800281b3  lea     rcx, [rbp+9E0h+Source]
0x1800281ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800281be  mov     rax, rbx
0x1800281c1  inc     rax
0x1800281c4  cmp     [rcx+rax*2], r15w
0x1800281c9  jnz     short loc_1800281C1
0x1800281cb  inc     eax
0x1800281cd  movsxd  r9, eax
0x1800281d0  add     r9, r9; SourceSize
0x1800281d3  lea     r8, [rbp+9E0h+Source]; Source
0x1800281da  mov     edx, 414h; DestinationSize
0x1800281df  lea     rcx, [rbp+9E0h+Destination]; Destination
0x1800281e6  call    cs:__imp_memcpy_s
0x1800281ec  test    eax, eax
0x1800281ee  jnz     loc_1800282C8
0x1800281f4  lea     rax, [rbp+9E0h+var_450]
0x1800281fb  inc     rbx
0x1800281fe  cmp     [rax+rbx*2], r15w
0x180028203  jnz     short loc_1800281FB
0x180028205  movsxd  rax, ebx
0x180028208  mov     [rbp+rax*2+9E0h+var_450], di
0x180028210  lea     rcx, ds:2[rax*2]
0x180028218  cmp     rcx, 418h
0x18002821f  jnb     loc_1800282C2
0x180028225  mov     [rbp+rcx+9E0h+var_450], r15w
0x18002822e  lea     r8, [rbp+9E0h+var_450]; unsigned __int16 *
0x180028235  lea     rdx, aModule; "Module"
0x18002823c  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180028241  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180028246  mov     ebx, eax
0x180028248  test    eax, eax
0x18002824a  js      short loc_18002826A
0x18002824c  lea     r8, [rbp+9E0h+Source]; unsigned __int16 *
0x180028253  lea     rdx, aModuleRaw; "Module_Raw"
0x18002825a  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002825f  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180028264  mov     ebx, eax
0x180028266  test    eax, eax
0x180028268  jns     short loc_180028282
0x18002826a  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002826f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180028274  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180028279  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002827e  mov     eax, ebx
0x180028280  jmp     short loc_1800282E1
0x180028282  movzx   r8d, r14w; unsigned __int16 *
0x180028286  mov     [rsp+0AE0h+var_AA8], r15
0x18002828b  lea     r9, aRegistry; "REGISTRY"
0x180028292  lea     rdx, [rsp+0AE0h+Filename]; unsigned __int16 *
0x180028297  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002829c  test    esi, esi
0x18002829e  jz      short loc_1800282AA
0x1800282a0  mov     [rsp+0AE0h+var_AC0], 1
0x1800282a8  jmp     short loc_1800282AF
0x1800282aa  mov     [rsp+0AE0h+var_AC0], r15d; int
0x1800282af  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800282b4  mov     ebx, eax
0x1800282b6  lea     rcx, [rsp+0AE0h+var_AA8]
0x1800282bb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800282c0  jmp     short loc_18002826A
0x1800282c2  call    __report_rangecheckfailure
0x1800282c8  lea     rcx, [rsp+0AE0h+var_AB0]
0x1800282cd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800282d2  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800282d7  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800282dc  mov     eax, 80004005h
0x1800282e1  mov     rcx, [rbp+9E0h+var_30]
0x1800282e8  xor     rcx, rsp; StackCookie
0x1800282eb  call    __security_check_cookie
0x1800282f0  mov     rbx, [rsp+0AE0h+arg_0]
0x1800282f8  add     rsp, 0AC0h
0x1800282ff  pop     r15
0x180028301  pop     r14
0x180028303  pop     rdi
0x180028304  pop     rsi
0x180028305  pop     rbp
0x180028306  retn
```
