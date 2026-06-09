# UL_RESPONSE_CACHE_ENTRY::ContainsInvalidationUrlOnTheExtraList(ushort const *)

- ea: `0x180002820`
- end: `0x180002898`
- name: `?ContainsInvalidationUrlOnTheExtraList@UL_RESPONSE_CACHE_ENTRY@@AEAAHPEBG@Z`
- size: `120`
- prototype: `__int64 __fastcall(UL_RESPONSE_CACHE_ENTRY *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002670`

## callees

- `0x180002820`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002849`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002849`

## pseudocode

```c
__int64 __fastcall UL_RESPONSE_CACHE_ENTRY::ContainsInvalidationUrlOnTheExtraList(
        UL_RESPONSE_CACHE_ENTRY *this,
        char *a2)
{
  char *v2; // rdi
  char *i; // rbx
  signed __int64 v5; // rax
  char *v6; // rcx
  int v7; // edx
  int v8; // r8d

  v2 = (char *)this + 768;
  for ( i = (char *)*((_QWORD *)this + 96); i != v2; i = *(char **)i )
  {
    v5 = (char *)STRU::QueryStr((STRU *)(i + 16)) - a2;
    v6 = a2;
    do
    {
      v7 = *(unsigned __int16 *)&v6[v5];
      v8 = *(unsigned __int16 *)v6 - v7;
      if ( v8 )
        break;
      v6 += 2;
    }
    while ( v7 );
    if ( !v8 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002820  mov     [rsp+arg_0], rbx
0x180002825  mov     [rsp+arg_8], rsi
0x18000282a  push    rdi
0x18000282b  sub     rsp, 20h
0x18000282f  lea     rdi, [rcx+300h]
0x180002836  mov     rsi, rdx
0x180002839  mov     rbx, [rdi]
0x18000283c  nop     dword ptr [rax+00h]
0x180002840  cmp     rbx, rdi
0x180002843  jz      short loc_180002894
0x180002845  lea     rcx, [rbx+10h]
0x180002849  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000284f  sub     rax, rsi
0x180002852  mov     rcx, rsi
0x180002855  nop     word ptr [rax+rax+00000000h]
0x180002860  movzx   r8d, word ptr [rcx]
0x180002864  movzx   edx, word ptr [rcx+rax]
0x180002868  sub     r8d, edx
0x18000286b  jnz     short loc_180002875
0x18000286d  add     rcx, 2
0x180002871  test    edx, edx
0x180002873  jnz     short loc_180002860
0x180002875  test    r8d, r8d
0x180002878  jz      short loc_18000287F
0x18000287a  mov     rbx, [rbx]
0x18000287d  jmp     short loc_180002840
0x18000287f  mov     eax, 1
0x180002884  mov     rbx, [rsp+28h+arg_0]
0x180002889  mov     rsi, [rsp+28h+arg_8]
0x18000288e  add     rsp, 20h
0x180002892  pop     rdi
0x180002893  retn
0x180002894  xor     eax, eax
0x180002896  jmp     short loc_180002884
```
