# QueryAlwaysAllowedQueryString(REQUEST_FILTER_CONFIG *,ushort const *,ushort const *)

- ea: `0x180005320`
- end: `0x180005458`
- name: `?QueryAlwaysAllowedQueryString@@YAHPEAVREQUEST_FILTER_CONFIG@@PEBG1@Z`
- size: `312`
- prototype: `__int64 __fastcall(struct REQUEST_FILTER_CONFIG *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800010c0`

## callees

- `0x180005320`

## import_xrefs

- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005350`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800053ad`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180005350`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800053ad`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180005392`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800053e2`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180005392`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800053e2`
- `iisutil!PuDbgPrint` at `0x180005448`
- `iisutil!PuDbgPrint` at `0x180005448`

## string_xrefs

- `0x180005441`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\requestfiltering.cxx`

## pseudocode

```c
__int64 __fastcall QueryAlwaysAllowedQueryString(
        struct REQUEST_FILTER_CONFIG *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  MULTISZ *v5; // rbx
  __int64 result; // rax
  const unsigned __int16 *v7; // r9
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  int v11; // edx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // rcx
  signed __int64 v15; // r8
  int v16; // eax
  int v17; // edx

  if ( !*a2 )
    return 1;
  v5 = (struct REQUEST_FILTER_CONFIG *)((char *)a1 + 336);
  if ( *a3 )
  {
    for ( i = MULTISZ::First((struct REQUEST_FILTER_CONFIG *)((char *)a1 + 336)); ; i = MULTISZ::Next(v5, v13) )
    {
      v13 = i;
      if ( !i )
        break;
      v14 = a3;
      v15 = (char *)i - (char *)a3;
      do
      {
        v16 = *(const unsigned __int16 *)((char *)v14 + v15);
        v17 = *v14 - v16;
        if ( v17 )
          break;
        ++v14;
      }
      while ( v16 );
      if ( !v17 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\requestfiltering.cxx",
            1632,
            "QueryAlwaysAllowedQueryString",
            "QueryString '%S' is always allowed.\r\n",
            a3);
        return 1;
      }
    }
  }
  for ( result = (__int64)MULTISZ::First(v5); ; result = (__int64)MULTISZ::Next(v5, v7) )
  {
    v7 = (const unsigned __int16 *)result;
    if ( !result )
      break;
    v8 = a2;
    v9 = result - (_QWORD)a2;
    do
    {
      v10 = *(const unsigned __int16 *)((char *)v8 + v9);
      v11 = *v8 - v10;
      if ( v11 )
        break;
      ++v8;
    }
    while ( v10 );
    if ( !v11 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\requestfiltering.cxx",
          1653,
          "QueryAlwaysAllowedQueryString",
          "QueryString '%S' is always allowed.\r\n",
          a3);
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005320  mov     [rsp+arg_0], rbx
0x180005325  mov     [rsp+arg_8], rsi
0x18000532a  push    rdi
0x18000532b  sub     rsp, 30h
0x18000532f  cmp     word ptr [rdx], 0
0x180005333  mov     rdi, r8
0x180005336  mov     rsi, rdx
0x180005339  jz      loc_18000544E
0x18000533f  cmp     word ptr [r8], 0
0x180005344  lea     rbx, [rcx+150h]
0x18000534b  jnz     short loc_1800053AA
0x18000534d  mov     rcx, rbx
0x180005350  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180005356  mov     r9, rax
0x180005359  test    rax, rax
0x18000535c  jz      short loc_18000539A
0x18000535e  mov     r8, rax
0x180005361  mov     rcx, rsi
0x180005364  sub     r8, rsi
0x180005367  nop     word ptr [rax+rax+00000000h]
0x180005370  movzx   edx, word ptr [rcx]
0x180005373  movzx   eax, word ptr [rcx+r8]
0x180005378  sub     edx, eax
0x18000537a  jnz     short loc_180005384
0x18000537c  add     rcx, 2
0x180005380  test    eax, eax
0x180005382  jnz     short loc_180005370
0x180005384  test    edx, edx
0x180005386  jz      loc_180005413
0x18000538c  mov     rdx, r9
0x18000538f  mov     rcx, rbx
0x180005392  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x180005398  jmp     short loc_180005356
0x18000539a  mov     rbx, [rsp+38h+arg_0]
0x18000539f  mov     rsi, [rsp+38h+arg_8]
0x1800053a4  add     rsp, 30h
0x1800053a8  pop     rdi
0x1800053a9  retn
0x1800053aa  mov     rcx, rbx
0x1800053ad  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x1800053b3  mov     r9, rax
0x1800053b6  test    rax, rax
0x1800053b9  jz      short loc_18000534D
0x1800053bb  mov     r8, rax
0x1800053be  mov     rcx, rdi
0x1800053c1  sub     r8, rdi
0x1800053c4  movzx   edx, word ptr [rcx]
0x1800053c7  movzx   eax, word ptr [rcx+r8]
0x1800053cc  sub     edx, eax
0x1800053ce  jnz     short loc_1800053D8
0x1800053d0  add     rcx, 2
0x1800053d4  test    eax, eax
0x1800053d6  jnz     short loc_1800053C4
0x1800053d8  test    edx, edx
0x1800053da  jz      short loc_1800053EA
0x1800053dc  mov     rdx, r9
0x1800053df  mov     rcx, rbx
0x1800053e2  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800053e8  jmp     short loc_1800053B3
0x1800053ea  test    byte ptr cs:g_dwDebugFlags, 3
0x1800053f1  jz      short loc_18000544E
0x1800053f3  lea     rax, aQuerystringSIs; "QueryString '%S' is always allowed.\r\n"
0x1800053fa  mov     [rsp+38h+var_10], rdi
0x1800053ff  mov     [rsp+38h+var_18], rax
0x180005404  lea     r9, aQueryalwaysall_0; "QueryAlwaysAllowedQueryString"
0x18000540b  mov     r8d, 660h
0x180005411  jmp     short loc_18000543A
0x180005413  test    byte ptr cs:g_dwDebugFlags, 3
0x18000541a  jz      short loc_18000544E
0x18000541c  lea     rax, aQuerystringSIs; "QueryString '%S' is always allowed.\r\n"
0x180005423  mov     [rsp+38h+var_10], rdi
0x180005428  mov     [rsp+38h+var_18], rax
0x18000542d  lea     r9, aQueryalwaysall_0; "QueryAlwaysAllowedQueryString"
0x180005434  mov     r8d, 675h
0x18000543a  mov     rcx, cs:g_pDebug
0x180005441  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005448  call    cs:__imp_PuDbgPrint
0x18000544e  mov     eax, 1
0x180005453  jmp     loc_18000539A
```
