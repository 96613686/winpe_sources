# CPackage::_IconCreateFromFile(ushort const *)

- ea: `0x18000baa0`
- end: `0x18000bbb7`
- name: `?_IconCreateFromFile@CPackage@@IEAAPEAU_IC@@PEBG@Z`
- size: `279`
- prototype: `struct _IC *__fastcall(CPackage *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800073b8`
- `0x180007b28`

## callees

- `0x18000ae20`
- `0x18000afb4`
- `0x18000b7a0`
- `0x18000b94c`
- `0x18000baa0`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bad1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bad1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000bb88`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000bb88`
- `USER32!DestroyIcon` at `0x18000bb7f`
- `USER32!DestroyIcon` at `0x18000bb7f`

## pseudocode

```c
struct _IC *__fastcall CPackage::_IconCreateFromFile(CPackage *this, const unsigned __int16 *a2)
{
  char *v4; // rax
  char *v5; // rbx
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // r8
  _WORD *v9; // rax
  _WORD *v10; // rcx
  CPackage *v11; // rcx
  unsigned __int16 v13[264]; // [rsp+20h] [rbp-238h] BYREF

  v4 = (char *)GlobalAlloc(0x40u, 0x430u);
  v5 = v4;
  if ( v4 )
  {
    v6 = 2147483646;
    v7 = a2;
    v8 = 260;
    v9 = v4 + 8;
    do
    {
      if ( !v6 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v6;
      --v8;
    }
    while ( v8 );
    v10 = v9 - 1;
    if ( v8 )
      v10 = v9;
    *v10 = 0;
    *((_DWORD *)v5 + 262) = 0;
    if ( *((_WORD *)v5 + 4) )
      CPackage::_GetCurrentIcon(this, (HICON *)v5);
    GetDisplayName((unsigned __int16 *)v5 + 264, a2);
    CPackage::_CreateSaferIconTitle(this, (CPackage *)v13, (const WCHAR *)v5, 0);
    if ( !(unsigned int)CPackage::_IconCalcSize(v11, (struct tagRECT *)(v5 + 1052), v13) )
    {
      if ( *(_QWORD *)v5 )
        DestroyIcon(*(HICON *)v5);
      GlobalFree(v5);
      return 0;
    }
  }
  return (struct _IC *)v5;
}

```

## disassembly

```asm
0x18000baa0  mov     [rsp+arg_10], rbx
0x18000baa5  push    rbp
0x18000baa6  push    rsi
0x18000baa7  push    rdi
0x18000baa8  sub     rsp, 240h
0x18000baaf  mov     rax, cs:__security_cookie
0x18000bab6  xor     rax, rsp
0x18000bab9  mov     [rsp+258h+var_28], rax
0x18000bac1  mov     rsi, rdx
0x18000bac4  mov     rdi, rcx
0x18000bac7  mov     edx, 430h; dwBytes
0x18000bacc  mov     ecx, 40h ; '@'; uFlags
0x18000bad1  call    cs:__imp_GlobalAlloc
0x18000bad7  xor     ebp, ebp
0x18000bad9  mov     rbx, rax
0x18000badc  test    rax, rax
0x18000badf  jz      loc_18000BB91
0x18000bae5  mov     ecx, 7FFFFFFEh
0x18000baea  mov     rdx, rsi
0x18000baed  mov     r8d, 104h
0x18000baf3  add     rax, 8
0x18000baf7  test    rcx, rcx
0x18000bafa  jz      short loc_18000BB1B
0x18000bafc  movzx   r9d, word ptr [rdx]
0x18000bb00  test    r9w, r9w
0x18000bb04  jz      short loc_18000BB1B
0x18000bb06  mov     [rax], r9w
0x18000bb0a  add     rdx, 2
0x18000bb0e  add     rax, 2
0x18000bb12  dec     rcx
0x18000bb15  sub     r8, 1
0x18000bb19  jnz     short loc_18000BAF7
0x18000bb1b  test    r8, r8
0x18000bb1e  lea     rcx, [rax-2]
0x18000bb22  cmovnz  rcx, rax
0x18000bb26  mov     [rcx], bp
0x18000bb29  mov     [rbx+418h], ebp
0x18000bb2f  cmp     [rbx+8], bp
0x18000bb33  jz      short loc_18000BB40
0x18000bb35  mov     rdx, rbx; struct _IC *
0x18000bb38  mov     rcx, rdi; this
0x18000bb3b  call    ?_GetCurrentIcon@CPackage@@IEAAXPEAU_IC@@@Z; CPackage::_GetCurrentIcon(_IC *)
0x18000bb40  lea     rcx, [rbx+210h]; unsigned __int16 *
0x18000bb47  mov     rdx, rsi; unsigned __int16 *
0x18000bb4a  call    ?GetDisplayName@@YAXPEAGPEBG@Z; GetDisplayName(ushort *,ushort const *)
0x18000bb4f  xor     r9d, r9d; struct tagRECT *
0x18000bb52  lea     rdx, [rsp+258h+var_238]; unsigned __int16 *
0x18000bb57  mov     r8, rbx; struct _IC *
0x18000bb5a  mov     rcx, rdi; this
0x18000bb5d  call    ?_CreateSaferIconTitle@CPackage@@IEAAXPEAGPEAU_IC@@PEBUtagRECT@@@Z; CPackage::_CreateSaferIconTitle(ushort *,_IC *,tagRECT const *)
0x18000bb62  lea     rdx, [rbx+41Ch]; struct tagRECT *
0x18000bb69  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x18000bb6e  call    ?_IconCalcSize@CPackage@@IEAAHPEAUtagRECT@@PEBG@Z; CPackage::_IconCalcSize(tagRECT *,ushort const *)
0x18000bb73  test    eax, eax
0x18000bb75  jnz     short loc_18000BB91
0x18000bb77  mov     rcx, [rbx]; hIcon
0x18000bb7a  test    rcx, rcx
0x18000bb7d  jz      short loc_18000BB85
0x18000bb7f  call    cs:__imp_DestroyIcon
0x18000bb85  mov     rcx, rbx; hMem
0x18000bb88  call    cs:__imp_GlobalFree
0x18000bb8e  mov     rbx, rbp
0x18000bb91  mov     rax, rbx
0x18000bb94  mov     rcx, [rsp+258h+var_28]
0x18000bb9c  xor     rcx, rsp; StackCookie
0x18000bb9f  call    __security_check_cookie
0x18000bba4  mov     rbx, [rsp+258h+arg_10]
0x18000bbac  add     rsp, 240h
0x18000bbb3  pop     rdi
0x18000bbb4  pop     rsi
0x18000bbb5  pop     rbp
0x18000bbb6  retn
```
