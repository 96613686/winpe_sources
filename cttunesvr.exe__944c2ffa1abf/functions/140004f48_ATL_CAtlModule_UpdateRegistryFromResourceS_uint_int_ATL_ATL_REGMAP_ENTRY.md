# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140004f48`
- end: `0x1400051d8`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `656`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x140004f30`
- `0x140005ce4`

## callees

- `0x140001888`
- `0x140002174`
- `0x140002308`
- `0x140002bd8`
- `0x140004128`
- `0x140004f48`
- `0x1400065f0`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140005079`
- `KERNEL32!GetModuleHandleW` at `0x140005079`
- `KERNEL32!GetModuleFileNameW` at `0x140005004`
- `KERNEL32!GetModuleFileNameW` at `0x140005004`
- `msvcrt!memcpy_s` at `0x1400050c9`
- `msvcrt!memcpy_s` at `0x1400050c9`

## string_xrefs

- `0x140005179`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        const unsigned __int16 **a4)
{
  struct ATL::CAtlModule *v4; // rdi
  const unsigned __int16 **v6; // rbx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v9; // r8
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v22; // eax
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  unsigned __int16 Source[520]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v29; // [rsp+680h] [rbp+580h] BYREF
  _BYTE Destination[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = ATL::_pAtlModule;
  v24 = &ATL::CRegObject::`vftable';
  v26 = 0;
  v6 = a4;
  v25 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v6 )
    {
      v9 = v6[1];
      if ( v9 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, i, v9);
      v6 += 2;
    }
  }
  v10 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v4 + 40LL))(v4, &v24);
  if ( v10 < 0 )
    goto LABEL_31;
  v11 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v10 = Error;
LABEL_31:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
    return (unsigned int)v10;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_31;
  }
  v14 = Filename;
  v15 = 0;
  do
  {
    v16 = *v14;
    if ( !*v14 )
      break;
    Source[v15] = v16;
    if ( v16 == 39 && (unsigned int)v15 < 0x206 )
    {
      LODWORD(v15) = v15 + 1;
      Source[(unsigned int)v15] = 39;
    }
    ++v14;
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < 0x207 );
  Source[v15] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v17 = Source;
LABEL_28:
    if ( !-ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module", v17) )
    {
      v10 = -2147024882;
      goto LABEL_31;
    }
    v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module_Raw", Source);
    v10 = v22 == 0 ? 0x8007000E : 0;
    if ( !v22 )
      goto LABEL_31;
    Error = ATL::CRegObject::RegisterFromResource(
              (ATL::CRegObject *)&v24,
              Filename,
              (const unsigned __int16 *)a2,
              L"REGISTRY",
              a3 != 0);
    goto LABEL_10;
  }
  v18 = -1;
  v29 = 34;
  v19 = -1;
  do
    ++v19;
  while ( Source[v19] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v19 + 1)) )
  {
    do
      ++v18;
    while ( *(_WORD *)&Destination[2 * v18 - 2] );
    v20 = 2LL * (int)v18 + 2;
    *(_WORD *)&Destination[2 * (int)v18 - 2] = 34;
    if ( v20 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v20 - 2] = 0;
    v17 = &v29;
    goto LABEL_28;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
  return 2147500037LL;
}

```

## disassembly

```asm
0x140004f48  mov     [rsp-8+arg_0], rbx
0x140004f4d  push    rbp
0x140004f4e  push    rsi
0x140004f4f  push    rdi
0x140004f50  push    r14
0x140004f52  push    r15
0x140004f54  lea     rbp, [rsp-9B0h]
0x140004f5c  sub     rsp, 0AB0h
0x140004f63  mov     rax, cs:__security_cookie
0x140004f6a  xor     rax, rsp
0x140004f6d  mov     [rbp+9D0h+var_30], rax
0x140004f74  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004f7b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140004f82  xor     r15d, r15d
0x140004f85  mov     r14d, edx
0x140004f88  mov     [rsp+0AD0h+var_AA0], rax
0x140004f8d  xorps   xmm0, xmm0
0x140004f90  mov     [rsp+0AD0h+var_A88], r15d
0x140004f95  mov     rbx, r9
0x140004f98  mov     esi, r8d
0x140004f9b  movdqu  [rsp+0AD0h+var_A98], xmm0
0x140004fa1  test    r9, r9
0x140004fa4  jz      short loc_140004FCD
0x140004fa6  mov     rax, [r9]
0x140004fa9  jmp     short loc_140004FC8
0x140004fab  mov     r8, [rbx+8]; unsigned __int16 *
0x140004faf  test    r8, r8
0x140004fb2  jz      short loc_140004FC1
0x140004fb4  mov     rdx, rax; unsigned __int16 *
0x140004fb7  lea     rcx, [rsp+0AD0h+var_A98]; this
0x140004fbc  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140004fc1  add     rbx, 10h
0x140004fc5  mov     rax, [rbx]
0x140004fc8  test    rax, rax
0x140004fcb  jnz     short loc_140004FAB
0x140004fcd  mov     rax, [rdi]
0x140004fd0  lea     rdx, [rsp+0AD0h+var_AA0]
0x140004fd5  mov     rcx, rdi
0x140004fd8  mov     rax, [rax+28h]
0x140004fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fe1  mov     ebx, eax
0x140004fe3  test    eax, eax
0x140004fe5  js      loc_140005162
0x140004feb  mov     rbx, cs:hInstance
0x140004ff2  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x140004ff9  mov     edi, 104h
0x140004ffe  mov     rcx, rbx; hModule
0x140005001  mov     r8d, edi; nSize
0x140005004  call    cs:__imp_GetModuleFileNameW
0x14000500a  test    eax, eax
0x14000500c  jnz     short loc_14000501A
0x14000500e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140005013  mov     ebx, eax
0x140005015  jmp     loc_140005162
0x14000501a  cmp     eax, edi
0x14000501c  jnz     short loc_140005028
0x14000501e  mov     ebx, 8007007Ah
0x140005023  jmp     loc_140005162
0x140005028  lea     rdx, [rbp+9D0h+Filename]
0x14000502f  mov     ecx, r15d
0x140005032  mov     r9d, 27h ; '''
0x140005038  movzx   r8d, word ptr [rdx]
0x14000503c  test    r8w, r8w
0x140005040  jz      short loc_14000506C
0x140005042  mov     [rsp+rcx*2+0AD0h+Source], r8w
0x140005048  cmp     r8w, r9w
0x14000504c  jnz     short loc_14000505E
0x14000504e  cmp     ecx, 206h
0x140005054  jnb     short loc_14000505E
0x140005056  inc     ecx
0x140005058  mov     [rsp+rcx*2+0AD0h+Source], r9w
0x14000505e  add     rdx, 2
0x140005062  inc     ecx
0x140005064  cmp     ecx, 207h
0x14000506a  jb      short loc_140005038
0x14000506c  mov     [rsp+rcx*2+0AD0h+Source], r15w
0x140005072  test    rbx, rbx
0x140005075  jz      short loc_14000508E
0x140005077  xor     ecx, ecx; lpModuleName
0x140005079  call    cs:__imp_GetModuleHandleW
0x14000507f  cmp     rbx, rax
0x140005082  jz      short loc_14000508E
0x140005084  lea     r8, [rsp+0AD0h+Source]
0x140005089  jmp     loc_140005118
0x14000508e  mov     edi, 22h ; '"'
0x140005093  lea     rcx, [rsp+0AD0h+Source]
0x140005098  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000509c  mov     [rbp+9D0h+var_450], di
0x1400050a3  mov     rax, rbx
0x1400050a6  inc     rax
0x1400050a9  cmp     [rcx+rax*2], r15w
0x1400050ae  jnz     short loc_1400050A6
0x1400050b0  inc     eax
0x1400050b2  lea     r8, [rsp+0AD0h+Source]; Source
0x1400050b7  movsxd  r9, eax
0x1400050ba  lea     rcx, [rbp+9D0h+Destination]; Destination
0x1400050c1  add     r9, r9; SourceSize
0x1400050c4  mov     edx, 414h; DestinationSize
0x1400050c9  call    cs:__imp_memcpy_s
0x1400050cf  test    eax, eax
0x1400050d1  jnz     loc_14000519D
0x1400050d7  lea     rax, [rbp+9D0h+var_450]
0x1400050de  inc     rbx
0x1400050e1  cmp     [rax+rbx*2], r15w
0x1400050e6  jnz     short loc_1400050DE
0x1400050e8  movsxd  rax, ebx
0x1400050eb  lea     rcx, ds:2[rax*2]
0x1400050f3  mov     [rbp+rax*2+9D0h+var_450], di
0x1400050fb  cmp     rcx, 418h
0x140005102  jnb     loc_1400051D2
0x140005108  mov     [rbp+rcx+9D0h+var_450], r15w
0x140005111  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x140005118  lea     rdx, aModule; "Module"
0x14000511f  lea     rcx, [rsp+0AD0h+var_A98]; this
0x140005124  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005129  neg     eax
0x14000512b  mov     edi, 8007000Eh
0x140005130  sbb     ecx, ecx
0x140005132  not     ecx
0x140005134  and     ecx, edi
0x140005136  test    ecx, ecx
0x140005138  jns     short loc_14000513E
0x14000513a  mov     ebx, ecx
0x14000513c  jmp     short loc_140005162
0x14000513e  lea     r8, [rsp+0AD0h+Source]; unsigned __int16 *
0x140005143  lea     rdx, aModuleRaw; "Module_Raw"
0x14000514a  lea     rcx, [rsp+0AD0h+var_A98]; this
0x14000514f  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005154  mov     ecx, eax
0x140005156  neg     ecx
0x140005158  sbb     ebx, ebx
0x14000515a  not     ebx
0x14000515c  and     ebx, edi
0x14000515e  test    eax, eax
0x140005160  jnz     short loc_140005170
0x140005162  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x140005167  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000516c  mov     eax, ebx
0x14000516e  jmp     short loc_1400051AC
0x140005170  mov     eax, r15d
0x140005173  movzx   r8d, r14w; unsigned __int16 *
0x140005177  test    esi, esi
0x140005179  lea     r9, aRegistry; "REGISTRY"
0x140005180  lea     rdx, [rbp+9D0h+Filename]; unsigned __int16 *
0x140005187  setnz   al
0x14000518a  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x14000518f  mov     [rsp+0AD0h+var_AB0], eax; int
0x140005193  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x140005198  jmp     loc_140005013
0x14000519d  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x1400051a2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400051a7  mov     eax, 80004005h
0x1400051ac  mov     rcx, [rbp+9D0h+var_30]
0x1400051b3  xor     rcx, rsp; StackCookie
0x1400051b6  call    __security_check_cookie
0x1400051bb  mov     rbx, [rsp+0AD0h+arg_0]
0x1400051c3  add     rsp, 0AB0h
0x1400051ca  pop     r15
0x1400051cc  pop     r14
0x1400051ce  pop     rdi
0x1400051cf  pop     rsi
0x1400051d0  pop     rbp
0x1400051d1  retn
0x1400051d2  call    __report_rangecheckfailure
```
