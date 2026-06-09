# _anonymous_namespace_::DfspCreateDeletedLinkDn

- ea: `0x140040fa8`
- end: `0x14004105b`
- name: `_anonymous_namespace_::DfspCreateDeletedLinkDn`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003fa40`

## callees

- `0x1400011d0`
- `0x14000aed8`
- `0x140040fa8`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x140040fcb`
- `RPCRT4!UuidToStringW` at `0x140040fcb`

## string_xrefs

- `0x14004102b`: `CN=deletedlink-%s,%s`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::DfspCreateDeletedLinkDn(const UUID *a1, __int64 a2, unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rbp
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdi
  RPC_WSTR v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v12 = 0;
  if ( UuidToStringW(a1, &v12) )
    return 8;
  v6 = -1;
  do
    ++v6;
  while ( v12[v6] );
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  v8 = v6 + v7 + 17;
  v9 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
  v10 = v9;
  if ( !v9 )
  {
    return 8;
  }
  else
  {
    StringCchPrintfW(v9, v8, L"CN=deletedlink-%s,%s", v12, a2);
    *a3 = v10;
  }
  return v4;
}

```

## disassembly

```asm
0x140040fa8  mov     rax, rsp
0x140040fab  mov     [rax+8], rbx
0x140040faf  mov     [rax+10h], rbp
0x140040fb3  push    rsi
0x140040fb4  push    rdi
0x140040fb5  push    r14
0x140040fb7  sub     rsp, 30h
0x140040fbb  mov     rsi, rdx
0x140040fbe  xor     ebx, ebx
0x140040fc0  lea     rdx, [rax+20h]; StringUuid
0x140040fc4  mov     [rax+20h], rbx
0x140040fc8  mov     r14, r8
0x140040fcb  call    cs:__imp_UuidToStringW
0x140040fd2  nop     dword ptr [rax+rax+00h]
0x140040fd7  test    eax, eax
0x140040fd9  jz      short loc_140040FE2
0x140040fdb  mov     ebx, 8
0x140040fe0  jmp     short loc_140041045
0x140040fe2  mov     rcx, [rsp+48h+arg_18]
0x140040fe7  or      r8, 0FFFFFFFFFFFFFFFFh
0x140040feb  mov     rax, r8
0x140040fee  inc     rax
0x140040ff1  cmp     [rcx+rax*2], bx
0x140040ff5  jnz     short loc_140040FEE
0x140040ff7  mov     rcx, r8
0x140040ffa  inc     rcx
0x140040ffd  cmp     [rsi+rcx*2], bx
0x140041001  jnz     short loc_140040FFA
0x140041003  lea     rbp, [rcx+11h]
0x140041007  add     rbp, rax
0x14004100a  mov     eax, 2
0x14004100f  mul     rbp
0x140041012  cmovo   rax, r8
0x140041016  mov     rcx, rax; Size
0x140041019  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004101e  mov     rdi, rax
0x140041021  test    rax, rax
0x140041024  jz      short loc_140040FDB
0x140041026  mov     r9, [rsp+48h+arg_18]
0x14004102b  lea     r8, aCnDeletedlinkS; "CN=deletedlink-%s,%s"
0x140041032  mov     rdx, rbp; unsigned __int64
0x140041035  mov     [rsp+48h+var_28], rsi
0x14004103a  mov     rcx, rax; unsigned __int16 *
0x14004103d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140041042  mov     [r14], rdi
0x140041045  mov     rbp, [rsp+48h+arg_8]
0x14004104a  mov     eax, ebx
0x14004104c  mov     rbx, [rsp+48h+arg_0]
0x140041051  add     rsp, 30h
0x140041055  pop     r14
0x140041057  pop     rdi
0x140041058  pop     rsi
0x140041059  retn
```
