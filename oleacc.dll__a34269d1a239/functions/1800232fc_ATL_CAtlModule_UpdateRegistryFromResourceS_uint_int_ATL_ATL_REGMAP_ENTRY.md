# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800232fc`
- end: `0x18002353e`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `578`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800232b0`
- `0x1800232d0`
- `0x1800237a0`

## callees

- `0x18001e4c0`
- `0x18001e610`
- `0x1800206d0`
- `0x180020810`
- `0x180020c00`
- `0x180021378`
- `0x18002186c`
- `0x180022920`
- `0x1800232fc`
- `0x1800237bc`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800233b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800233b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800233f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800233f8`

## string_xrefs

- `0x180023501`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *i; // rax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  void **v21; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v25; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v26[527]; // [rsp+282h] [rbp+182h] BYREF
  unsigned __int16 v27[520]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v4 = a4;
  v21 = &ATL::CRegObject::`vftable';
  v22 = 0;
  v23 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, i, v4[1]);
      v4 += 2;
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v10 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_21:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_22;
    }
    if ( ModuleFileNameW != 260 )
    {
      ATL::CAtlModule::EscapeSingleQuote(v27, v12, Filename);
      if ( !v10 || v10 == GetModuleHandleW(0) )
      {
        v25 = 34;
        if ( !ocscpy_s(v26, v13, v27) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_22;
        }
        v15 = -1;
        do
          ++v15;
        while ( v26[v15 - 1] );
        v26[(int)v15 - 1] = 34;
        v16 = 2LL * (int)v15 + 2;
        if ( v16 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v26[-1] + v16) = 0;
        v14 = &v25;
      }
      else
      {
        v14 = v27;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module", v14);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module_Raw", v27);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_21;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_22:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800232fc  mov     [rsp-8+arg_10], rbx
0x180023301  push    rbp
0x180023302  push    rsi
0x180023303  push    rdi
0x180023304  push    r14
0x180023306  push    r15
0x180023308  lea     rbp, [rsp-9C0h]
0x180023310  sub     rsp, 0AC0h
0x180023317  mov     rax, cs:__security_cookie
0x18002331e  xor     rax, rsp
0x180023321  mov     [rbp+9E0h+var_30], rax
0x180023328  mov     rbx, r9
0x18002332b  mov     esi, r8d
0x18002332e  mov     r14d, edx
0x180023331  mov     rdi, rcx
0x180023334  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002333b  mov     [rsp+0AE0h+var_AA0], rax
0x180023340  xorps   xmm0, xmm0
0x180023343  movdqu  [rsp+0AE0h+var_A98], xmm0
0x180023349  xor     r15d, r15d
0x18002334c  mov     [rsp+0AE0h+var_A88], r15d
0x180023351  test    r9, r9
0x180023354  jz      short loc_180023378
0x180023356  mov     rax, [r9]
0x180023359  jmp     short loc_180023373
0x18002335b  mov     r8, [rbx+8]; unsigned __int16 *
0x18002335f  mov     rdx, rax; unsigned __int16 *
0x180023362  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180023367  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002336c  lea     rbx, [rbx+10h]
0x180023370  mov     rax, [rbx]
0x180023373  test    rax, rax
0x180023376  jnz     short loc_18002335B
0x180023378  mov     rax, [rdi]
0x18002337b  lea     rdx, [rsp+0AE0h+var_AA0]
0x180023380  mov     rcx, rdi
0x180023383  mov     rax, [rax+28h]
0x180023387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002338c  mov     ebx, eax
0x18002338e  test    eax, eax
0x180023390  js      loc_1800234C6
0x180023396  mov     [rsp+0AE0h+var_AB0], r15
0x18002339b  mov     rbx, cs:hInstance
0x1800233a2  mov     edi, 104h
0x1800233a7  mov     r8d, edi; nSize
0x1800233aa  lea     rdx, [rsp+0AE0h+Filename]; lpFilename
0x1800233af  mov     rcx, rbx; hModule
0x1800233b2  call    cs:__imp_GetModuleFileNameW
0x1800233b8  test    eax, eax
0x1800233ba  jnz     short loc_1800233C8
0x1800233bc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800233c1  mov     ebx, eax
0x1800233c3  jmp     loc_1800234BC
0x1800233c8  cmp     eax, edi
0x1800233ca  jnz     short loc_1800233E0
0x1800233cc  lea     rcx, [rsp+0AE0h+var_AB0]
0x1800233d1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800233d6  mov     ebx, 8007007Ah
0x1800233db  jmp     loc_1800234C6
0x1800233e0  lea     r8, [rsp+0AE0h+Filename]; unsigned __int16 *
0x1800233e5  lea     rcx, [rbp+9E0h+var_440]; unsigned __int16 *
0x1800233ec  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800233f1  test    rbx, rbx
0x1800233f4  jz      short loc_18002340C
0x1800233f6  xor     ecx, ecx; lpModuleName
0x1800233f8  call    cs:__imp_GetModuleHandleW
0x1800233fe  cmp     rbx, rax
0x180023401  jz      short loc_18002340C
0x180023403  lea     r8, [rbp+9E0h+var_440]
0x18002340a  jmp     short loc_180023487
0x18002340c  mov     ebx, 22h ; '"'
0x180023411  mov     [rbp+9E0h+var_860], bx
0x180023418  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002341f  lea     rcx, [rbp+9E0h+var_85E]; unsigned __int16 *
0x180023426  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18002342b  test    al, al
0x18002342d  jnz     short loc_180023443
0x18002342f  lea     rcx, [rsp+0AE0h+var_AB0]
0x180023434  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180023439  mov     ebx, 80004005h
0x18002343e  jmp     loc_1800234C6
0x180023443  lea     rcx, [rbp+9E0h+var_860]
0x18002344a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002344e  inc     rax
0x180023451  cmp     [rcx+rax*2], r15w
0x180023456  jnz     short loc_18002344E
0x180023458  cdqe
0x18002345a  mov     [rbp+rax*2+9E0h+var_860], bx
0x180023462  lea     rcx, ds:2[rax*2]
0x18002346a  cmp     rcx, 418h
0x180023471  jnb     loc_180023538
0x180023477  mov     [rbp+rcx+9E0h+var_860], r15w
0x180023480  lea     r8, [rbp+9E0h+var_860]; unsigned __int16 *
0x180023487  lea     rdx, aModule; "Module"
0x18002348e  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180023493  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180023498  mov     ebx, eax
0x18002349a  test    eax, eax
0x18002349c  js      short loc_1800234BC
0x18002349e  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x1800234a5  lea     rdx, aModuleRaw; "Module_Raw"
0x1800234ac  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800234b1  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800234b6  mov     ebx, eax
0x1800234b8  test    eax, eax
0x1800234ba  jns     short loc_1800234F8
0x1800234bc  lea     rcx, [rsp+0AE0h+var_AB0]
0x1800234c1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800234c6  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x1800234cb  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800234d0  mov     eax, ebx
0x1800234d2  mov     rcx, [rbp+9E0h+var_30]
0x1800234d9  xor     rcx, rsp; StackCookie
0x1800234dc  call    __security_check_cookie
0x1800234e1  mov     rbx, [rsp+0AE0h+arg_10]
0x1800234e9  add     rsp, 0AC0h
0x1800234f0  pop     r15
0x1800234f2  pop     r14
0x1800234f4  pop     rdi
0x1800234f5  pop     rsi
0x1800234f6  pop     rbp
0x1800234f7  retn
0x1800234f8  movzx   r8d, r14w; unsigned __int16 *
0x1800234fc  mov     [rsp+0AE0h+var_AA8], r15
0x180023501  lea     r9, aRegistry; "REGISTRY"
0x180023508  lea     rdx, [rsp+0AE0h+Filename]; unsigned __int16 *
0x18002350d  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x180023512  test    esi, esi
0x180023514  jz      short loc_180023520
0x180023516  mov     [rsp+0AE0h+var_AC0], 1
0x18002351e  jmp     short loc_180023525
0x180023520  mov     [rsp+0AE0h+var_AC0], r15d; int
0x180023525  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18002352a  mov     ebx, eax
0x18002352c  lea     rcx, [rsp+0AE0h+var_AA8]
0x180023531  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180023536  jmp     short loc_1800234BC
0x180023538  call    __report_rangecheckfailure
```
