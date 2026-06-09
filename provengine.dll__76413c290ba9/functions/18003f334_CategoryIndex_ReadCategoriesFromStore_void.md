# CategoryIndex::ReadCategoriesFromStore(void)

- ea: `0x18003f334`
- end: `0x18003f4ef`
- name: `?ReadCategoriesFromStore@CategoryIndex@@AEAAXXZ`
- size: `443`
- prototype: `void __fastcall(CategoryIndex *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18003ec58`

## callees

- `0x1800021b4`
- `0x18000b030`
- `0x180021cf4`
- `0x180021f40`
- `0x18002d6b0`
- `0x18003836c`
- `0x18003e488`
- `0x18003ea28`
- `0x18003f334`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18003f3e6`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18003f3e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f49b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f49b`

## string_xrefs

- `0x18003f398`: `categories.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CategoryIndex::ReadCategoriesFromStore(CategoryIndex *this)
{
  char *v2; // rdx
  unsigned __int64 v3; // r8
  __int64 *v4; // rdx
  _QWORD *v5; // rax
  int v6; // eax
  void *v7; // rcx
  int v8; // [rsp+20h] [rbp-19h] BYREF
  void *ppvObject; // [rsp+28h] [rbp-11h] BYREF
  __int128 v10; // [rsp+30h] [rbp-9h] BYREF
  __int64 v11; // [rsp+40h] [rbp+7h]
  __int64 v12; // [rsp+48h] [rbp+Fh]
  __int64 v13; // [rsp+50h] [rbp+17h]
  const void *Src[3]; // [rsp+60h] [rbp+27h] BYREF
  unsigned __int64 v15; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v2 = *(char **)ProvisioningPaths::GetWindowsProvisioningFolderPath();
  v15 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  if ( *(_WORD *)v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&v2[2 * v3] );
  }
  else
  {
    v3 = 0;
  }
  std::wstring::assign(Src, v2, v3);
  std::wstring::append(Src, (char *)L"categories.xml");
  v4 = (__int64 *)Src;
  if ( v15 >= 8 )
    v4 = (__int64 *)Src[0];
  CreateCategoryReader(&ppvObject, v4);
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v5 = operator new(0x10u);
  if ( !v5 )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  *(_QWORD *)&v10 = v5;
  *v5 = 0;
  v5[1] = 0;
  *(_QWORD *)v10 = &v10;
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v8);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v6,
        v8);
    if ( v6 )
      break;
    if ( v8 == 1 )
    {
      CategoryIndex::AddNode((__int64)this, &ppvObject, (__int64)&v10);
    }
    else if ( v8 == 15 && v13 && !--v13 )
    {
      v12 = 0;
    }
  }
  if ( v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)0x8000FFFFLL,
      v8);
  std::deque<_CategoryNode *>::~deque<_CategoryNode *>(&v10);
  v7 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( v15 >= 8 )
    operator delete((void *)Src[0]);
}

```

## disassembly

```asm
0x18003f334  mov     [rsp-8+arg_8], rbx
0x18003f339  mov     [rsp-8+arg_10], rdi
0x18003f33e  push    rbp
0x18003f33f  lea     rbp, [rsp-57h]
0x18003f344  sub     rsp, 90h
0x18003f34b  mov     rax, cs:__security_cookie
0x18003f352  xor     rax, rsp
0x18003f355  mov     [rbp+57h+var_10], rax
0x18003f359  mov     rbx, rcx
0x18003f35c  call    ?GetWindowsProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetWindowsProvisioningFolderPath(void)
0x18003f361  mov     rdx, [rax]; Src
0x18003f364  mov     [rbp+57h+var_18], 7
0x18003f36c  xor     edi, edi
0x18003f36e  mov     [rbp+57h+var_20], rdi
0x18003f372  mov     word ptr [rbp+57h+Src], di
0x18003f376  cmp     [rdx], di
0x18003f379  jnz     short loc_18003F380
0x18003f37b  mov     r8d, edi
0x18003f37e  jmp     short loc_18003F38E
0x18003f380  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f384  inc     r8
0x18003f387  cmp     [rdx+r8*2], di
0x18003f38c  jnz     short loc_18003F384
0x18003f38e  lea     rcx, [rbp+57h+Src]; void *
0x18003f392  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003f397  nop
0x18003f398  lea     rdx, aCategoriesXml; "categories.xml"
0x18003f39f  lea     rcx, [rbp+57h+Src]; Src
0x18003f3a3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18003f3a8  lea     rdx, [rbp+57h+Src]
0x18003f3ac  cmp     [rbp+57h+var_18], 8
0x18003f3b1  cmovnb  rdx, [rbp+57h+Src]; pszFile
0x18003f3b6  lea     rcx, [rbp+57h+ppvObject]; ppvObject
0x18003f3ba  call    CreateCategoryReader
0x18003f3bf  nop
0x18003f3c0  mov     [rbp+57h+var_70], edi
0x18003f3c3  xorps   xmm0, xmm0
0x18003f3c6  movdqu  [rbp+57h+var_60], xmm0
0x18003f3cb  mov     [rbp+57h+var_50], rdi
0x18003f3cf  mov     [rbp+57h+var_48], rdi
0x18003f3d3  mov     [rbp+57h+var_40], rdi
0x18003f3d7  mov     ecx, 10h; Size
0x18003f3dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f3e1  test    rax, rax
0x18003f3e4  jnz     short loc_18003F3ED
0x18003f3e6  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18003f3ec  int     3; Trap to Debugger
0x18003f3ed  mov     qword ptr [rbp+57h+var_60], rax
0x18003f3f1  mov     [rax], rdi
0x18003f3f4  mov     [rax+8], rdi
0x18003f3f8  lea     rcx, [rbp+57h+var_60]
0x18003f3fc  mov     rax, qword ptr [rbp+57h+var_60]
0x18003f400  mov     [rax], rcx
0x18003f403  mov     rcx, [rbp+57h+ppvObject]
0x18003f407  mov     rax, [rcx]
0x18003f40a  lea     rdx, [rbp+57h+var_70]
0x18003f40e  mov     rax, [rax+30h]
0x18003f412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f417  mov     rcx, [rbp+5Fh]; this
0x18003f41b  test    eax, eax
0x18003f41d  js      loc_18003F4DA
0x18003f423  jnz     short loc_18003F45D
0x18003f425  mov     ecx, [rbp+57h+var_70]
0x18003f428  sub     ecx, 1
0x18003f42b  jz      short loc_18003F44B
0x18003f42d  cmp     ecx, 0Eh
0x18003f430  jnz     short loc_18003F403
0x18003f432  mov     rax, [rbp+57h+var_40]
0x18003f436  test    rax, rax
0x18003f439  jz      short loc_18003F403
0x18003f43b  sub     rax, 1
0x18003f43f  mov     [rbp+57h+var_40], rax
0x18003f443  jnz     short loc_18003F403
0x18003f445  mov     [rbp+57h+var_48], rdi
0x18003f449  jmp     short loc_18003F403
0x18003f44b  lea     r8, [rbp+57h+var_60]
0x18003f44f  lea     rdx, [rbp+57h+ppvObject]
0x18003f453  mov     rcx, rbx
0x18003f456  call    ?AddNode@CategoryIndex@@AEAAXAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@AEAV?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@@Z; CategoryIndex::AddNode(Microsoft::WRL::ComPtr<IXmlReader> &,std::deque<_CategoryNode *> &)
0x18003f45b  jmp     short loc_18003F403
0x18003f45d  cmp     [rbp+57h+var_40], rdi
0x18003f461  setnz   al
0x18003f464  mov     rcx, [rbp+5Fh]; this
0x18003f468  test    al, al
0x18003f46a  jnz     short loc_18003F4C2
0x18003f46c  lea     rcx, [rbp+57h+var_60]
0x18003f470  call    ??1?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@QEAA@XZ; std::deque<_CategoryNode *>::~deque<_CategoryNode *>(void)
0x18003f475  nop
0x18003f476  mov     rcx, [rbp+57h+ppvObject]
0x18003f47a  test    rcx, rcx
0x18003f47d  jz      short loc_18003F490
0x18003f47f  mov     [rbp+57h+ppvObject], rdi
0x18003f483  mov     rax, [rcx]
0x18003f486  mov     rax, [rax+10h]
0x18003f48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f48f  nop
0x18003f490  cmp     [rbp+57h+var_18], 8
0x18003f495  jb      short loc_18003F4A1
0x18003f497  mov     rcx, [rbp+57h+Src]
0x18003f49b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003f4a1  mov     rcx, [rbp+57h+var_10]
0x18003f4a5  xor     rcx, rsp; StackCookie
0x18003f4a8  call    __security_check_cookie
0x18003f4ad  lea     r11, [rsp+90h+var_s0]
0x18003f4b5  mov     rbx, [r11+18h]
0x18003f4b9  mov     rdi, [r11+20h]
0x18003f4bd  mov     rsp, r11
0x18003f4c0  pop     rbp
0x18003f4c1  retn
0x18003f4c2  mov     r9d, 8000FFFFh; char *
0x18003f4c8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003f4cf  mov     edx, 0DCh; void *
0x18003f4d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f4da  mov     r9d, eax; char *
0x18003f4dd  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003f4e4  mov     edx, 0CFh; void *
0x18003f4e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
