# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140018254`
- end: `0x140018505`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `689`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1400137ac`

## callees

- `0x140001fc8`
- `0x14000c2c0`
- `0x14000cfb8`
- `0x14000e4f8`
- `0x1400159d4`
- `0x140018254`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14001830d`
- `KERNEL32!GetModuleFileNameW` at `0x14001830d`
- `KERNEL32!GetModuleHandleW` at `0x14001838f`
- `KERNEL32!GetModuleHandleW` at `0x14001838f`
- `msvcrt!memcpy_s` at `0x1400183eb`
- `msvcrt!memcpy_s` at `0x1400183eb`

## string_xrefs

- `0x14001849a`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  struct ATL::CAtlModule *v6; // rdi
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v8; // r8
  signed int v9; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v15; // r8
  unsigned __int16 *v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  int v21; // eax
  const unsigned __int16 *v22; // r8
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Source[520]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v29; // [rsp+680h] [rbp+580h] BYREF
  _BYTE Destination[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = a4;
  v24 = &ATL::CRegObject::`vftable';
  v25 = 0;
  v26 = 0;
  v6 = ATL::_pAtlModule;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      v8 = v4[1];
      if ( v8 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, i, v8);
      v4 += 2;
    }
  }
  v9 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v6 + 40LL))(v6, &v24);
  if ( v9 < 0 )
    goto LABEL_31;
  v10 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v9 = Error;
LABEL_31:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
    return (unsigned int)v9;
  }
  if ( ModuleFileNameW == 260 )
  {
    v9 = -2147024774;
    goto LABEL_31;
  }
  v13 = Filename;
  v14 = 0;
  do
  {
    v15 = *v13;
    if ( !*v13 )
      break;
    Source[v14] = v15;
    if ( v15 == 39 && (unsigned int)v14 < 0x206 )
    {
      LODWORD(v14) = v14 + 1;
      Source[(unsigned int)v14] = 39;
    }
    ++v13;
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < 0x207 );
  Source[v14] = 0;
  if ( v10 && v10 != GetModuleHandleW(0) )
  {
    v16 = Source;
LABEL_28:
    if ( !-ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module", v16) )
    {
      v9 = -2147024882;
      goto LABEL_31;
    }
    v21 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module_Raw", Source);
    v9 = v21 == 0 ? 0x8007000E : 0;
    if ( !v21 )
      goto LABEL_31;
    if ( a3 )
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v24, Filename, v22, L"REGISTRY", 1);
    else
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v24, Filename, v22, L"REGISTRY", 0);
    goto LABEL_10;
  }
  v29 = 34;
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( Source[v18] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v18 + 1)) )
  {
    do
      ++v17;
    while ( *(_WORD *)&Destination[2 * v17 - 2] );
    *(_WORD *)&Destination[2 * (int)v17 - 2] = 34;
    v19 = 2LL * (int)v17 + 2;
    if ( v19 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v19 - 2] = 0;
    v16 = &v29;
    goto LABEL_28;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
  return 2147500037LL;
}

```

## disassembly

```asm
0x140018254  mov     [rsp-8+arg_0], rbx
0x140018259  mov     [rsp-8+arg_8], rsi
0x14001825e  push    rbp
0x14001825f  push    rdi
0x140018260  push    r14
0x140018262  lea     rbp, [rsp-9B0h]
0x14001826a  sub     rsp, 0AB0h
0x140018271  mov     rax, cs:__security_cookie
0x140018278  xor     rax, rsp
0x14001827b  mov     [rbp+9C0h+var_20], rax
0x140018282  mov     rbx, r9
0x140018285  mov     esi, r8d
0x140018288  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14001828f  mov     [rsp+0AC0h+var_A90], rax
0x140018294  xorps   xmm0, xmm0
0x140018297  movdqu  [rsp+0AC0h+var_A88], xmm0
0x14001829d  xor     r14d, r14d
0x1400182a0  mov     [rsp+0AC0h+var_A78], r14d
0x1400182a5  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400182ac  test    r9, r9
0x1400182af  jz      short loc_1400182D8
0x1400182b1  mov     rax, [r9]
0x1400182b4  jmp     short loc_1400182D3
0x1400182b6  mov     r8, [rbx+8]; unsigned __int16 *
0x1400182ba  test    r8, r8
0x1400182bd  jz      short loc_1400182CC
0x1400182bf  mov     rdx, rax; unsigned __int16 *
0x1400182c2  lea     rcx, [rsp+0AC0h+var_A88]; this
0x1400182c7  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400182cc  add     rbx, 10h
0x1400182d0  mov     rax, [rbx]
0x1400182d3  test    rax, rax
0x1400182d6  jnz     short loc_1400182B6
0x1400182d8  mov     rax, [rdi]
0x1400182db  lea     rdx, [rsp+0AC0h+var_A90]
0x1400182e0  mov     rcx, rdi
0x1400182e3  mov     rax, [rax+28h]
0x1400182e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400182ec  mov     ebx, eax
0x1400182ee  test    eax, eax
0x1400182f0  js      loc_14001848C
0x1400182f6  mov     rbx, cs:hInstance
0x1400182fd  mov     edi, 104h
0x140018302  mov     r8d, edi; nSize
0x140018305  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x14001830a  mov     rcx, rbx; hModule
0x14001830d  call    cs:__imp_GetModuleFileNameW
0x140018314  nop     dword ptr [rax+rax+00h]
0x140018319  test    eax, eax
0x14001831b  jnz     short loc_140018329
0x14001831d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140018322  mov     ebx, eax
0x140018324  jmp     loc_14001848C
0x140018329  cmp     eax, edi
0x14001832b  jnz     short loc_140018337
0x14001832d  mov     ebx, 8007007Ah
0x140018332  jmp     loc_14001848C
0x140018337  lea     rdx, [rsp+0AC0h+Filename]
0x14001833c  mov     ecx, r14d
0x14001833f  mov     r9d, 27h ; '''
0x140018345  movzx   r8d, word ptr [rdx]
0x140018349  test    r8w, r8w
0x14001834d  jz      short loc_14001837F
0x14001834f  mov     [rbp+rcx*2+9C0h+Source], r8w
0x140018358  cmp     r8w, r9w
0x14001835c  jnz     short loc_140018371
0x14001835e  cmp     ecx, 206h
0x140018364  jnb     short loc_140018371
0x140018366  inc     ecx
0x140018368  mov     [rbp+rcx*2+9C0h+Source], r9w
0x140018371  add     rdx, 2
0x140018375  inc     ecx
0x140018377  cmp     ecx, 207h
0x14001837d  jb      short loc_140018345
0x14001837f  mov     [rbp+rcx*2+9C0h+Source], r14w
0x140018388  test    rbx, rbx
0x14001838b  jz      short loc_1400183AC
0x14001838d  xor     ecx, ecx; lpModuleName
0x14001838f  call    cs:__imp_GetModuleHandleW
0x140018396  nop     dword ptr [rax+rax+00h]
0x14001839b  cmp     rbx, rax
0x14001839e  jz      short loc_1400183AC
0x1400183a0  lea     r8, [rbp+9C0h+Source]
0x1400183a7  jmp     loc_140018440
0x1400183ac  mov     edi, 22h ; '"'
0x1400183b1  mov     [rbp+9C0h+var_440], di
0x1400183b8  lea     rcx, [rbp+9C0h+Source]
0x1400183bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400183c3  mov     rax, rbx
0x1400183c6  inc     rax
0x1400183c9  cmp     [rcx+rax*2], r14w
0x1400183ce  jnz     short loc_1400183C6
0x1400183d0  inc     eax
0x1400183d2  movsxd  r9, eax
0x1400183d5  add     r9, r9; SourceSize
0x1400183d8  lea     r8, [rbp+9C0h+Source]; Source
0x1400183df  mov     edx, 414h; DestinationSize
0x1400183e4  lea     rcx, [rbp+9C0h+Destination]; Destination
0x1400183eb  call    cs:__imp_memcpy_s
0x1400183f2  nop     dword ptr [rax+rax+00h]
0x1400183f7  test    eax, eax
0x1400183f9  jnz     loc_1400184C8
0x1400183ff  lea     rax, [rbp+9C0h+var_440]
0x140018406  inc     rbx
0x140018409  cmp     [rax+rbx*2], r14w
0x14001840e  jnz     short loc_140018406
0x140018410  movsxd  rax, ebx
0x140018413  mov     [rbp+rax*2+9C0h+var_440], di
0x14001841b  lea     rcx, ds:2[rax*2]
0x140018423  cmp     rcx, 418h
0x14001842a  jnb     loc_1400184FF
0x140018430  mov     [rbp+rcx+9C0h+var_440], r14w
0x140018439  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x140018440  lea     rdx, aModule; "Module"
0x140018447  lea     rcx, [rsp+0AC0h+var_A88]; this
0x14001844c  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140018451  neg     eax
0x140018453  sbb     ecx, ecx
0x140018455  mov     edi, 8007000Eh
0x14001845a  not     ecx
0x14001845c  and     ecx, edi
0x14001845e  test    ecx, ecx
0x140018460  jns     short loc_140018466
0x140018462  mov     ebx, ecx
0x140018464  jmp     short loc_14001848C
0x140018466  lea     r8, [rbp+9C0h+Source]; unsigned __int16 *
0x14001846d  lea     rdx, aModuleRaw; "Module_Raw"
0x140018474  lea     rcx, [rsp+0AC0h+var_A88]; this
0x140018479  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14001847e  mov     ecx, eax
0x140018480  neg     ecx
0x140018482  sbb     ebx, ebx
0x140018484  not     ebx
0x140018486  and     ebx, edi
0x140018488  test    eax, eax
0x14001848a  jnz     short loc_14001849A
0x14001848c  lea     rcx, [rsp+0AC0h+var_A90]; this
0x140018491  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140018496  mov     eax, ebx
0x140018498  jmp     short loc_1400184D7
0x14001849a  lea     r9, aRegistry; "REGISTRY"
0x1400184a1  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x1400184a6  lea     rcx, [rsp+0AC0h+var_A90]; this
0x1400184ab  test    esi, esi
0x1400184ad  jz      short loc_1400184B9
0x1400184af  mov     [rsp+0AC0h+var_AA0], 1
0x1400184b7  jmp     short loc_1400184BE
0x1400184b9  mov     [rsp+0AC0h+var_AA0], r14d; int
0x1400184be  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1400184c3  jmp     loc_140018322
0x1400184c8  lea     rcx, [rsp+0AC0h+var_A90]; this
0x1400184cd  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400184d2  mov     eax, 80004005h
0x1400184d7  mov     rcx, [rbp+9C0h+var_20]
0x1400184de  xor     rcx, rsp; StackCookie
0x1400184e1  call    __security_check_cookie
0x1400184e6  lea     r11, [rsp+0AC0h+var_10]
0x1400184ee  mov     rbx, [r11+20h]
0x1400184f2  mov     rsi, [r11+28h]
0x1400184f6  mov     rsp, r11
0x1400184f9  pop     r14
0x1400184fb  pop     rdi
0x1400184fc  pop     rbp
0x1400184fd  retn
0x1400184ff  call    __report_rangecheckfailure
```
