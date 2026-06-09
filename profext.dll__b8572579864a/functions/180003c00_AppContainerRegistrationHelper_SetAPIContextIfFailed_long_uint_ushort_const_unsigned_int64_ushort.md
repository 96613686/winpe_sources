# AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)

- ea: `0x180003c00`
- end: `0x180003d26`
- name: `?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z`
- size: `294`
- prototype: `static int(int, unsigned int, const unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002a80`
- `0x180009504`
- `0x18000d980`
- `0x18000ea1c`
- `0x1800153b8`

## callees

- `0x180003c00`
- `0x180004030`
- `0x18001b914`

## string_xrefs

- `0x180003c23`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003d06`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::SetAPIContextIfFailed(
        unsigned int a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned __int16 *a5)
{
  int v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rdx
  unsigned __int64 i; // rdi
  unsigned __int16 *v16; // rax
  __int64 v18; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (a1 & 0x80000000) == 0 )
    return a1;
  v8 = StringCchPrintfW(a5, a4, L"%ls Line:%d ", L"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp");
  if ( v8 < 0 )
  {
    v12 = (unsigned int)v8;
    v18 = 3304;
    goto LABEL_20;
  }
  if ( !a3 )
    return a1;
  v9 = 2147483646;
  if ( a4 - 1 > 0x7FFFFFFE )
  {
    v12 = 2147942487LL;
LABEL_19:
    v18 = 3310;
LABEL_20:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v12,
      a2);
    return a1;
  }
  v10 = a4;
  v11 = a5;
  while ( *v11 )
  {
    ++v11;
    if ( !--v10 )
    {
      v12 = 2147942487LL;
      v13 = 0;
      goto LABEL_10;
    }
  }
  v13 = a4 - v10;
  v12 = 0;
LABEL_10:
  if ( (int)v12 < 0 )
    goto LABEL_19;
  v14 = &a5[v13];
  for ( i = a4 - v13; i; --i )
  {
    if ( !v9 )
      break;
    if ( !*a3 )
      break;
    *v14++ = *a3++;
    --v9;
  }
  v16 = v14 - 1;
  v12 = 2147942522LL;
  if ( i )
  {
    v16 = v14;
    v12 = 0;
  }
  *v16 = 0;
  if ( !i )
    goto LABEL_19;
  return a1;
}

```

## disassembly

```asm
0x180003c00  mov     [rsp+arg_8], rbx
0x180003c05  mov     [rsp+arg_10], rbp
0x180003c0a  push    rdi
0x180003c0b  sub     rsp, 30h
0x180003c0f  mov     rdi, r9
0x180003c12  mov     rbx, r8
0x180003c15  mov     ebp, ecx
0x180003c17  test    ecx, ecx
0x180003c19  jns     loc_180003CE9
0x180003c1f  mov     [rsp+38h+var_18], edx; int
0x180003c23  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003c2a  mov     [rsp+38h+arg_0], rsi
0x180003c2f  lea     r8, aLsLineD; "%ls Line:%d "
0x180003c36  mov     rsi, [rsp+38h+arg_20]
0x180003c3b  mov     rdx, rdi; unsigned __int64
0x180003c3e  mov     rcx, rsi; unsigned __int16 *
0x180003c41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c46  test    eax, eax
0x180003c48  js      loc_180003D14
0x180003c4e  test    rbx, rbx
0x180003c51  jz      loc_180003CE4
0x180003c57  lea     rax, [rdi-1]
0x180003c5b  mov     ecx, 7FFFFFFEh
0x180003c60  cmp     rax, rcx
0x180003c63  ja      loc_180003D1E
0x180003c69  mov     rdx, rdi
0x180003c6c  mov     rax, rsi
0x180003c6f  nop
0x180003c70  cmp     word ptr [rax], 0
0x180003c74  jz      short loc_180003C8E
0x180003c76  add     rax, 2
0x180003c7a  sub     rdx, 1
0x180003c7e  jnz     short loc_180003C70
0x180003c80  xor     r8d, r8d
0x180003c83  mov     r9d, 80070057h
0x180003c89  mov     eax, r8d
0x180003c8c  jmp     short loc_180003C9A
0x180003c8e  mov     rax, rdi
0x180003c91  sub     rax, rdx
0x180003c94  xor     r8d, r8d
0x180003c97  mov     r9d, r8d; char *
0x180003c9a  test    r9d, r9d
0x180003c9d  js      short loc_180003CFC
0x180003c9f  lea     rdx, [rsi+rax*2]
0x180003ca3  sub     rdi, rax
0x180003ca6  jz      short loc_180003CC9
0x180003ca8  test    rcx, rcx
0x180003cab  jz      short loc_180003CC9
0x180003cad  movzx   eax, word ptr [rbx]
0x180003cb0  test    ax, ax
0x180003cb3  jz      short loc_180003CC9
0x180003cb5  mov     [rdx], ax
0x180003cb8  add     rbx, 2
0x180003cbc  add     rdx, 2
0x180003cc0  dec     rcx
0x180003cc3  sub     rdi, 1
0x180003cc7  jnz     short loc_180003CA8
0x180003cc9  test    rdi, rdi
0x180003ccc  lea     rax, [rdx-2]
0x180003cd0  mov     r9d, 8007007Ah
0x180003cd6  cmovnz  rax, rdx
0x180003cda  cmovnz  r9d, r8d
0x180003cde  mov     [rax], r8w
0x180003ce2  jz      short loc_180003CFC
0x180003ce4  mov     rsi, [rsp+38h+arg_0]
0x180003ce9  mov     rbx, [rsp+38h+arg_8]
0x180003cee  mov     eax, ebp
0x180003cf0  mov     rbp, [rsp+38h+arg_10]
0x180003cf5  add     rsp, 30h
0x180003cf9  pop     rdi
0x180003cfa  retn
0x180003cfc  mov     edx, 0CEEh; void *
0x180003d01  mov     rcx, [rsp+38h]; this
0x180003d06  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003d0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003d12  jmp     short loc_180003CE4
0x180003d14  mov     r9d, eax
0x180003d17  mov     edx, 0CE8h
0x180003d1c  jmp     short loc_180003D01
0x180003d1e  mov     r9d, 80070057h
0x180003d24  jmp     short loc_180003CFC
```
