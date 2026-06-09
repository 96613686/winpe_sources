# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180012e20`
- end: `0x180013085`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180012e10`

## callees

- `0x1800024e0`
- `0x180002950`
- `0x180002eb2`
- `0x1800040d9`
- `0x18000d250`
- `0x18000d95c`
- `0x18000e3bc`
- `0x1800118e8`
- `0x180012e20`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012fe4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012fe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180012ea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180012ea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012f1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012f1c`

## string_xrefs

- `0x180013051`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v4; // esi
  signed int v5; // ebx
  HMODULE v6; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  unsigned __int16 v12; // r8
  unsigned __int16 *v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rax
  size_t v16; // r8
  unsigned __int64 v17; // rcx
  int v20; // eax
  const unsigned __int16 *v21; // r8
  void **v22; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Src[520]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v27; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v28[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = a3;
  v22 = &ATL::CRegObject::`vftable';
  v23 = 0;
  v24 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***, __int64, struct ATL::_ATL_REGMAP_ENTRY *))(*(_QWORD *)ATL::_pAtlModule + 40LL))(
         ATL::_pAtlModule,
         &v22,
         a3,
         a4);
  if ( v5 < 0 )
    goto LABEL_28;
  v6 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW == 260 )
    {
      v5 = -2147024774;
      goto LABEL_28;
    }
    v9 = Filename;
    v10 = 0;
    v11 = 39;
    do
    {
      v12 = *v9;
      if ( !*v9 )
        break;
      Src[v10] = v12;
      if ( v12 == 39 && (unsigned int)v10 < 0x206 )
      {
        LODWORD(v10) = v10 + 1;
        Src[(unsigned int)v10] = 39;
      }
      ++v9;
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < 0x207 );
    Src[v10] = 0;
    if ( !v6 || v6 == GetModuleHandleW(0) )
    {
      v27 = 34;
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      v16 = 2LL * ((int)v15 + 1);
      if ( v16 )
      {
        if ( v16 > 0x414 )
        {
          *(_DWORD *)_o__errno(Src, v9, v16) = 34;
          invalid_parameter_noinfo();
          ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v22);
          return 2147500037LL;
        }
        memcpy_0(v28, Src, v16);
      }
      do
        ++v14;
      while ( *(_WORD *)&v28[2 * v14 - 2] );
      *(_WORD *)&v28[2 * (int)v14 - 2] = 34;
      v17 = 2LL * (int)v14 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure(v17, v9, v16, v11);
      *(_WORD *)&v28[v17 - 2] = 0;
      v13 = &v27;
    }
    else
    {
      v13 = Src;
    }
    if ( !-ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v23, L"Module", v13) )
    {
      v5 = -2147024882;
      goto LABEL_28;
    }
    v20 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v23, L"Module_Raw", Src);
    v5 = v20 == 0 ? 0x8007000E : 0;
    if ( !v20 )
      goto LABEL_28;
    if ( v4 )
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v22, Filename, v21, L"REGISTRY", 1);
    else
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v22, Filename, v21, L"REGISTRY", 0);
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
  }
  v5 = Error;
LABEL_28:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012e20  push    rbp
0x180012e22  push    rbx
0x180012e23  push    rsi
0x180012e24  push    rdi
0x180012e25  push    r14
0x180012e27  lea     rbp, [rsp-9B0h]
0x180012e2f  sub     rsp, 0AB0h
0x180012e36  mov     rax, cs:__security_cookie
0x180012e3d  xor     rax, rsp
0x180012e40  mov     [rbp+9D0h+var_30], rax
0x180012e47  mov     esi, r8d
0x180012e4a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180012e51  mov     [rsp+0AD0h+var_AA0], rax
0x180012e56  xorps   xmm0, xmm0
0x180012e59  movdqu  [rsp+0AD0h+var_A98], xmm0
0x180012e5f  xor     r14d, r14d
0x180012e62  mov     [rsp+0AD0h+var_A88], r14d
0x180012e67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012e6e  mov     rax, [rcx]
0x180012e71  lea     rdx, [rsp+0AD0h+var_AA0]
0x180012e76  mov     rax, [rax+28h]
0x180012e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e7f  mov     ebx, eax
0x180012e81  test    eax, eax
0x180012e83  js      loc_180013043
0x180012e89  mov     rbx, cs:hModule
0x180012e90  mov     edi, 104h
0x180012e95  mov     r8d, edi; nSize
0x180012e98  lea     rdx, [rsp+0AD0h+Filename]; lpFilename
0x180012e9d  mov     rcx, rbx; hModule
0x180012ea0  call    cs:__imp_GetModuleFileNameW
0x180012ea6  test    eax, eax
0x180012ea8  jnz     short loc_180012EB6
0x180012eaa  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180012eaf  mov     ebx, eax
0x180012eb1  jmp     loc_180013043
0x180012eb6  cmp     eax, edi
0x180012eb8  jnz     short loc_180012EC4
0x180012eba  mov     ebx, 8007007Ah
0x180012ebf  jmp     loc_180013043
0x180012ec4  lea     rdx, [rsp+0AD0h+Filename]
0x180012ec9  mov     ecx, r14d
0x180012ecc  mov     r9d, 27h ; '''
0x180012ed2  movzx   r8d, word ptr [rdx]
0x180012ed6  test    r8w, r8w
0x180012eda  jz      short loc_180012F0C
0x180012edc  mov     [rbp+rcx*2+9D0h+Src], r8w
0x180012ee5  cmp     r8w, r9w
0x180012ee9  jnz     short loc_180012EFE
0x180012eeb  cmp     ecx, 206h
0x180012ef1  jnb     short loc_180012EFE
0x180012ef3  inc     ecx
0x180012ef5  mov     [rbp+rcx*2+9D0h+Src], r9w
0x180012efe  add     rdx, 2
0x180012f02  inc     ecx
0x180012f04  cmp     ecx, 207h
0x180012f0a  jb      short loc_180012ED2
0x180012f0c  mov     [rbp+rcx*2+9D0h+Src], r14w
0x180012f15  test    rbx, rbx
0x180012f18  jz      short loc_180012F33
0x180012f1a  xor     ecx, ecx; lpModuleName
0x180012f1c  call    cs:__imp_GetModuleHandleW
0x180012f22  cmp     rbx, rax
0x180012f25  jz      short loc_180012F33
0x180012f27  lea     r8, [rbp+9D0h+Src]
0x180012f2e  jmp     loc_180012FBE
0x180012f33  mov     edi, 22h ; '"'
0x180012f38  mov     [rbp+9D0h+var_450], di
0x180012f3f  lea     rcx, [rbp+9D0h+Src]
0x180012f46  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012f4a  mov     rax, rbx
0x180012f4d  inc     rax
0x180012f50  cmp     [rcx+rax*2], r14w
0x180012f55  jnz     short loc_180012F4D
0x180012f57  inc     eax
0x180012f59  movsxd  r8, eax
0x180012f5c  add     r8, r8; Size
0x180012f5f  jz      short loc_180012F7D
0x180012f61  cmp     r8, 414h
0x180012f68  ja      short loc_180012FE4
0x180012f6a  lea     rdx, [rbp+9D0h+Src]; Src
0x180012f71  lea     rcx, [rbp+9D0h+var_44E]; void *
0x180012f78  call    memcpy_0
0x180012f7d  lea     rax, [rbp+9D0h+var_450]
0x180012f84  inc     rbx
0x180012f87  cmp     [rax+rbx*2], r14w
0x180012f8c  jnz     short loc_180012F84
0x180012f8e  movsxd  rax, ebx
0x180012f91  mov     [rbp+rax*2+9D0h+var_450], di
0x180012f99  lea     rcx, ds:2[rax*2]
0x180012fa1  cmp     rcx, 418h
0x180012fa8  jnb     loc_18001307F
0x180012fae  mov     [rbp+rcx+9D0h+var_450], r14w
0x180012fb7  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x180012fbe  lea     rdx, aModule; "Module"
0x180012fc5  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180012fca  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180012fcf  neg     eax
0x180012fd1  sbb     ecx, ecx
0x180012fd3  mov     edi, 8007000Eh
0x180012fd8  not     ecx
0x180012fda  and     ecx, edi
0x180012fdc  test    ecx, ecx
0x180012fde  jns     short loc_18001301D
0x180012fe0  mov     ebx, ecx
0x180012fe2  jmp     short loc_180013043
0x180012fe4  call    cs:__imp__o__errno
0x180012fea  mov     [rax], edi
0x180012fec  call    _invalid_parameter_noinfo
0x180012ff1  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180012ff6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180012ffb  mov     eax, 80004005h
0x180013000  mov     rcx, [rbp+9D0h+var_30]
0x180013007  xor     rcx, rsp; StackCookie
0x18001300a  call    __security_check_cookie
0x18001300f  add     rsp, 0AB0h
0x180013016  pop     r14
0x180013018  pop     rdi
0x180013019  pop     rsi
0x18001301a  pop     rbx
0x18001301b  pop     rbp
0x18001301c  retn
0x18001301d  lea     r8, [rbp+9D0h+Src]; unsigned __int16 *
0x180013024  lea     rdx, aModuleRaw; "Module_Raw"
0x18001302b  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180013030  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180013035  mov     ecx, eax
0x180013037  neg     ecx
0x180013039  sbb     ebx, ebx
0x18001303b  not     ebx
0x18001303d  and     ebx, edi
0x18001303f  test    eax, eax
0x180013041  jnz     short loc_180013051
0x180013043  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180013048  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001304d  mov     eax, ebx
0x18001304f  jmp     short loc_180013000
0x180013051  lea     r9, aRegistry; "REGISTRY"
0x180013058  lea     rdx, [rsp+0AD0h+Filename]; unsigned __int16 *
0x18001305d  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180013062  test    esi, esi
0x180013064  jz      short loc_180013070
0x180013066  mov     [rsp+0AD0h+var_AB0], 1
0x18001306e  jmp     short loc_180013075
0x180013070  mov     [rsp+0AD0h+var_AB0], r14d; int
0x180013075  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001307a  jmp     loc_180012EAF
0x18001307f  call    __report_rangecheckfailure
```
