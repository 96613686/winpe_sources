# Csl::GetSystemDrivePath(Csl::Path &)

- ea: `0x14000c064`
- end: `0x14000c186`
- name: `?GetSystemDrivePath@Csl@@YAJAEAVPath@1@@Z`
- size: `290`
- prototype: `__int64 __fastcall(Csl *__hidden this, struct Path *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140018d5c`

## callees

- `0x1400020b0`
- `0x140002344`
- `0x140006fe4`
- `0x14000aa58`
- `0x14000bebc`
- `0x14000c064`

## pseudocode

```c
__int64 __fastcall Csl::GetSystemDrivePath(Csl *this, struct Path *a2)
{
  int SystemDirectoryPath; // eax
  unsigned int v4; // ebx
  void *v5; // rcx
  bool v6; // zf
  _WORD *v8; // r8
  int i; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  void *v12[2]; // [rsp+20h] [rbp-48h] BYREF
  _WORD v13[8]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-28h] BYREF
  _WORD v15[4]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v12[0] = v13;
  v12[1] = v13;
  v13[0] = 0;
  SystemDirectoryPath = Csl::GetSystemDirectoryPath((Csl *)v12, a2);
  v4 = SystemDirectoryPath;
  if ( SystemDirectoryPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)(unsigned int)SystemDirectoryPath,
      (int)v12[0]);
    v5 = v12[0];
    v6 = v12[0] == v13;
LABEL_3:
    if ( !v6 )
      operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    return v4;
  }
  v8 = v12[0];
  for ( i = 0; i < 2; ++i )
  {
    v10 = (unsigned int)i;
    v15[v10] = v8[v10];
  }
  v15[2] = 0;
  v14[0] = v15;
  v11 = -1;
  do
    ++v11;
  while ( v15[v11] );
  v14[1] = v11;
  if ( !Csl::Path::Assign(this, v14) )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x555,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      (int)v12[0]);
    v5 = v12[0];
    v6 = v12[0] == v13;
    goto LABEL_3;
  }
  if ( v12[0] != v13 )
    operator delete(v12[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x14000c064  push    rbp
0x14000c066  push    rbx
0x14000c067  push    rsi
0x14000c068  push    rdi
0x14000c069  mov     rbp, rsp
0x14000c06c  sub     rsp, 68h
0x14000c070  mov     rax, cs:__security_cookie
0x14000c077  xor     rax, rsp
0x14000c07a  mov     [rbp+var_10], rax
0x14000c07e  lea     rax, [rbp+var_38]
0x14000c082  mov     rdi, rcx
0x14000c085  mov     [rbp+var_48], rax
0x14000c089  lea     rcx, [rbp+var_48]; this
0x14000c08d  lea     rax, [rbp+var_38]
0x14000c091  xor     esi, esi
0x14000c093  mov     [rbp+var_40], rax
0x14000c097  mov     [rbp+var_38], si
0x14000c09b  call    ?GetSystemDirectoryPath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDirectoryPath(Csl::Path &)
0x14000c0a0  mov     ebx, eax
0x14000c0a2  test    eax, eax
0x14000c0a4  jns     short loc_14000C0DE
0x14000c0a6  mov     rcx, [rbp+20h]; this
0x14000c0aa  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c0b1  mov     r9d, eax; char *
0x14000c0b4  mov     edx, 54Eh; void *
0x14000c0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c0be  mov     rcx, [rbp+var_48]; void *
0x14000c0c2  lea     rax, [rbp+var_38]
0x14000c0c6  cmp     rcx, rax
0x14000c0c9  jz      short loc_14000C0D7
0x14000c0cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c0d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c0d7  mov     eax, ebx
0x14000c0d9  jmp     loc_14000C170
0x14000c0de  mov     r8, [rbp+var_48]
0x14000c0e2  mov     edx, esi
0x14000c0e4  mov     ecx, edx
0x14000c0e6  inc     edx
0x14000c0e8  movzx   eax, word ptr [r8+rcx*2]
0x14000c0ed  mov     [rbp+rcx*2+var_18], ax
0x14000c0f2  cmp     edx, 2
0x14000c0f5  jl      short loc_14000C0E4
0x14000c0f7  lea     rax, [rbp+var_18]
0x14000c0fb  mov     [rbp+var_14], si
0x14000c0ff  mov     [rbp+var_28], rax
0x14000c103  lea     rcx, [rbp+var_18]
0x14000c107  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c10b  inc     rax
0x14000c10e  cmp     [rcx+rax*2], si
0x14000c112  jnz     short loc_14000C10B
0x14000c114  lea     rdx, [rbp+var_28]
0x14000c118  mov     [rbp+var_20], rax
0x14000c11c  mov     rcx, rdi; this
0x14000c11f  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000c124  test    al, al
0x14000c126  jnz     short loc_14000C155
0x14000c128  mov     rcx, [rbp+20h]; this
0x14000c12c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c133  mov     ebx, 8007000Eh
0x14000c138  mov     edx, 555h; void *
0x14000c13d  mov     r9d, ebx; char *
0x14000c140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c145  mov     rcx, [rbp+var_48]
0x14000c149  lea     rdx, [rbp+var_38]
0x14000c14d  cmp     rcx, rdx
0x14000c150  jmp     loc_14000C0C9
0x14000c155  mov     rcx, [rbp+var_48]; void *
0x14000c159  lea     rax, [rbp+var_38]
0x14000c15d  cmp     rcx, rax
0x14000c160  jz      short loc_14000C16E
0x14000c162  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c169  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c16e  xor     eax, eax
0x14000c170  mov     rcx, [rbp+var_10]
0x14000c174  xor     rcx, rsp; StackCookie
0x14000c177  call    __security_check_cookie
0x14000c17c  add     rsp, 68h
0x14000c180  pop     rdi
0x14000c181  pop     rsi
0x14000c182  pop     rbx
0x14000c183  pop     rbp
0x14000c184  retn
```
