# AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)

- ea: `0x180004250`
- end: `0x1800044d9`
- name: `?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z`
- size: `649`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, const struct _GUID *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004c80`
- `0x180009a34`

## callees

- `0x1800040c0`
- `0x180004250`
- `0x1800044e0`
- `0x18000a3e4`
- `0x180022830`

## string_xrefs

- `0x1800042f5`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004368`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000446f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800044bb`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::IsFolderPresent(
        char *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        int *a4)
{
  char *v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // r11
  char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // r10
  _WORD *v13; // rcx
  _WORD *v14; // rdx
  unsigned int v15; // ebx
  __int64 v17; // rdx
  _WORD *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  _WORD *v21; // r9
  const unsigned __int16 *v22; // r8
  _WORD *v23; // rcx
  _WORD *v24; // rax
  unsigned int v25; // ebx
  const unsigned __int16 *v26; // rcx
  _WORD *v27; // rdx
  _WORD *v28; // rcx
  unsigned int IsFileOrFolderPresent; // eax
  _BYTE v30[520]; // [rsp+40h] [rbp-258h] BYREF
  _BYTE v31[8]; // [rsp+248h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v7 = a1;
  if ( a2 )
  {
    v8 = 2147483646;
    v9 = 260;
    v10 = a1;
    v11 = 2147483646;
    v12 = 260;
    v13 = v30;
    do
    {
      if ( !v11 )
        break;
      if ( !*(_WORD *)v10 )
        break;
      *v13 = *(_WORD *)v10;
      v10 += 2;
      ++v13;
      --v11;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v15 = -2147024774;
    if ( v12 )
    {
      v14 = v13;
      v15 = 0;
    }
    *v14 = 0;
    if ( !v12 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x401,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v15,
        (int)"Root %ls",
        v7);
      return v15;
    }
    v17 = 260;
    v18 = v30;
    while ( *v18 )
    {
      ++v18;
      if ( !--v17 )
      {
        v19 = -2147024809;
LABEL_14:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x404,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v19,
          (int)"Root %ls",
          v7);
        return v19;
      }
    }
    v20 = 2147483646;
    v21 = &v31[-2 * v17];
    v22 = L"\\";
    do
    {
      if ( !v20 )
        break;
      if ( !*v22 )
        break;
      *v21++ = *v22++;
      --v20;
      --v17;
    }
    while ( v17 );
    v23 = v21 - 1;
    v19 = -2147024774;
    if ( v17 )
    {
      v23 = v21;
      v19 = 0;
    }
    *v23 = 0;
    if ( !v17 )
      goto LABEL_14;
    v24 = v30;
    while ( *v24 )
    {
      ++v24;
      if ( !--v9 )
      {
        v25 = -2147024809;
LABEL_33:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x407,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v25,
          (int)"Root %ls append %ls",
          v7,
          a2);
        return v25;
      }
    }
    v26 = a2;
    v27 = &v31[-2 * v9];
    do
    {
      if ( !v8 )
        break;
      if ( !*v26 )
        break;
      *v27++ = *v26++;
      --v8;
      --v9;
    }
    while ( v9 );
    v28 = v27 - 1;
    v25 = -2147024774;
    if ( v9 )
    {
      v28 = v27;
      v25 = 0;
    }
    *v28 = 0;
    if ( !v9 )
      goto LABEL_33;
    v7 = v30;
  }
  IsFileOrFolderPresent = AppContainerRegistrationHelper::IsFileOrFolderPresent((WCHAR *)v7, a3, a4);
  return wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0x40B,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
           (const char *)IsFileOrFolderPresent,
           (__int64)"Root %ls",
           v7);
}

```

## disassembly

```asm
0x180004250  push    rbx
0x180004252  push    rbp
0x180004253  push    rsi
0x180004254  push    rdi
0x180004255  push    r14
0x180004257  push    r15
0x180004259  sub     rsp, 268h
0x180004260  mov     rax, cs:__security_cookie
0x180004267  xor     rax, rsp
0x18000426a  mov     [rsp+298h+var_48], rax
0x180004272  mov     r15, r9
0x180004275  mov     r14, r8
0x180004278  mov     rbp, rdx
0x18000427b  mov     rsi, rcx
0x18000427e  test    rdx, rdx
0x180004281  jz      loc_180004499
0x180004287  mov     edi, 7FFFFFFEh
0x18000428c  mov     r11d, 104h
0x180004292  mov     r9, rcx
0x180004295  mov     r8d, edi
0x180004298  mov     r10d, r11d
0x18000429b  lea     rcx, [rsp+298h+var_258]
0x1800042a0  test    r8, r8
0x1800042a3  jz      short loc_1800042C2
0x1800042a5  movzx   eax, word ptr [r9]
0x1800042a9  test    ax, ax
0x1800042ac  jz      short loc_1800042C2
0x1800042ae  mov     [rcx], ax
0x1800042b1  add     r9, 2
0x1800042b5  add     rcx, 2
0x1800042b9  dec     r8
0x1800042bc  sub     r10, 1
0x1800042c0  jnz     short loc_1800042A0
0x1800042c2  xor     eax, eax
0x1800042c4  lea     rdx, [rcx-2]
0x1800042c8  test    r10, r10
0x1800042cb  mov     ebx, 8007007Ah
0x1800042d0  cmovnz  rdx, rcx
0x1800042d4  cmovnz  ebx, eax
0x1800042d7  xor     ecx, ecx
0x1800042d9  mov     [rdx], cx
0x1800042dc  test    r10, r10
0x1800042df  jnz     short loc_180004331
0x1800042e1  mov     rcx, [rsp+298h]; this
0x1800042e9  lea     rdx, aRootLs; "Root %ls"
0x1800042f0  mov     [rsp+298h+var_270], rsi; char *
0x1800042f5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800042fc  mov     [rsp+298h+var_278], rdx; int
0x180004301  mov     r9d, ebx; char *
0x180004304  mov     edx, 401h; void *
0x180004309  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000430e  mov     eax, ebx
0x180004310  mov     rcx, [rsp+298h+var_48]
0x180004318  xor     rcx, rsp; StackCookie
0x18000431b  call    __security_check_cookie
0x180004320  add     rsp, 268h
0x180004327  pop     r15
0x180004329  pop     r14
0x18000432b  pop     rdi
0x18000432c  pop     rsi
0x18000432d  pop     rbp
0x18000432e  pop     rbx
0x18000432f  retn
0x180004331  mov     rdx, r11
0x180004334  lea     rax, [rsp+298h+var_258]
0x180004339  nop     dword ptr [rax+00000000h]
0x180004340  cmp     [rax], cx
0x180004343  jz      short loc_180004385
0x180004345  add     rax, 2
0x180004349  sub     rdx, 1
0x18000434d  jnz     short loc_180004340
0x18000434f  mov     ebx, 80070057h
0x180004354  mov     rcx, [rsp+298h]; this
0x18000435c  lea     rdx, aRootLs; "Root %ls"
0x180004363  mov     [rsp+298h+var_270], rsi; char *
0x180004368  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000436f  mov     [rsp+298h+var_278], rdx; int
0x180004374  mov     r9d, ebx; char *
0x180004377  mov     edx, 404h; void *
0x18000437c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004381  mov     eax, ebx
0x180004383  jmp     short loc_180004310
0x180004385  lea     rax, [rdx+rdx]
0x180004389  mov     rcx, rdi
0x18000438c  lea     r9, [rsp+298h+var_50]
0x180004394  sub     r9, rax
0x180004397  lea     r8, asc_180026BFC; "\\"
0x18000439e  test    rdx, rdx
0x1800043a1  jz      short loc_1800043C6
0x1800043a3  test    rcx, rcx
0x1800043a6  jz      short loc_1800043C6
0x1800043a8  movzx   eax, word ptr [r8]
0x1800043ac  test    ax, ax
0x1800043af  jz      short loc_1800043C6
0x1800043b1  mov     [r9], ax
0x1800043b5  add     r8, 2
0x1800043b9  add     r9, 2
0x1800043bd  dec     rcx
0x1800043c0  sub     rdx, 1
0x1800043c4  jnz     short loc_1800043A3
0x1800043c6  xor     eax, eax
0x1800043c8  lea     rcx, [r9-2]
0x1800043cc  test    rdx, rdx
0x1800043cf  mov     ebx, 8007007Ah
0x1800043d4  cmovnz  rcx, r9
0x1800043d8  cmovnz  ebx, eax
0x1800043db  mov     [rcx], ax
0x1800043de  jz      loc_180004354
0x1800043e4  lea     rax, [rsp+298h+var_258]
0x1800043e9  nop     dword ptr [rax+00000000h]
0x1800043f0  cmp     word ptr [rax], 0
0x1800043f4  jz      short loc_180004407
0x1800043f6  add     rax, 2
0x1800043fa  sub     r11, 1
0x1800043fe  jnz     short loc_1800043F0
0x180004400  mov     ebx, 80070057h
0x180004405  jmp     short loc_18000445B
0x180004407  lea     rax, [r11+r11]
0x18000440b  mov     rcx, rbp
0x18000440e  lea     rdx, [rsp+298h+var_50]
0x180004416  sub     rdx, rax
0x180004419  test    r11, r11
0x18000441c  jz      short loc_180004441
0x18000441e  xchg    ax, ax
0x180004420  test    rdi, rdi
0x180004423  jz      short loc_180004441
0x180004425  movzx   eax, word ptr [rcx]
0x180004428  test    ax, ax
0x18000442b  jz      short loc_180004441
0x18000442d  mov     [rdx], ax
0x180004430  add     rcx, 2
0x180004434  add     rdx, 2
0x180004438  dec     rdi
0x18000443b  sub     r11, 1
0x18000443f  jnz     short loc_180004420
0x180004441  xor     eax, eax
0x180004443  lea     rcx, [rdx-2]
0x180004447  test    r11, r11
0x18000444a  mov     ebx, 8007007Ah
0x18000444f  cmovnz  rcx, rdx
0x180004453  cmovnz  ebx, eax
0x180004456  mov     [rcx], ax
0x180004459  jnz     short loc_180004494
0x18000445b  mov     rcx, [rsp+298h]; this
0x180004463  lea     rax, aRootLsAppendLs; "Root %ls append %ls"
0x18000446a  mov     [rsp+298h+var_268], rbp
0x18000446f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004476  mov     [rsp+298h+var_270], rsi; char *
0x18000447b  mov     r9d, ebx; char *
0x18000447e  mov     edx, 407h; void *
0x180004483  mov     [rsp+298h+var_278], rax; int
0x180004488  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000448d  mov     eax, ebx
0x18000448f  jmp     loc_180004310
0x180004494  lea     rsi, [rsp+298h+var_258]
0x180004499  mov     r8, r15; int *
0x18000449c  mov     rdx, r14; struct _GUID *
0x18000449f  mov     rcx, rsi; char *
0x1800044a2  call    ?IsFileOrFolderPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFileOrFolderPresent(ushort const *,_GUID const *,int *)
0x1800044a7  mov     rcx, [rsp+298h]; this
0x1800044af  lea     rdx, aRootLs; "Root %ls"
0x1800044b6  mov     [rsp+298h+var_270], rsi; char *
0x1800044bb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800044c2  mov     [rsp+298h+var_278], rdx; __int64
0x1800044c7  mov     r9d, eax; char *
0x1800044ca  mov     edx, 40Bh; void *
0x1800044cf  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800044d4  jmp     loc_180004310
```
