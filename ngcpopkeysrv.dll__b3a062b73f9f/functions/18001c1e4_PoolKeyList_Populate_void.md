# PoolKeyList::Populate(void)

- ea: `0x18001c1e4`
- end: `0x18001c260`
- name: `?Populate@PoolKeyList@@QEAAJXZ`
- size: `124`
- prototype: `__int64 __fastcall(PoolKeyList *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b7fc`

## callees

- `0x18000b0fc`
- `0x18001069c`
- `0x18001c1e4`
- `0x18001ca98`

## string_xrefs

- `0x18001c212`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c23d`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall PoolKeyList::Populate(PoolKeyList *this)
{
  int v1; // ebx
  __int64 i; // rdi
  int v4; // eax
  int v5; // esi
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = 0;
  for ( i = 0; i != 6; ++i )
  {
    v4 = PoolKeyList::p_Populate(this, (const unsigned __int16 **)(&s_params)[i]);
    v5 = v4;
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x711,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v4,
        v7);
    if ( !v1 )
      v1 = v5;
  }
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x71C,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)(unsigned int)v1,
    v7);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001c1e4  push    rbx
0x18001c1e6  push    rbp
0x18001c1e7  push    rsi
0x18001c1e8  push    rdi
0x18001c1e9  sub     rsp, 28h
0x18001c1ed  xor     ebx, ebx
0x18001c1ef  mov     rbp, rcx
0x18001c1f2  xor     edi, edi
0x18001c1f4  lea     rdx, ?s_params@@3PAPEAU_PregenParms@@A; _PregenParms * near * s_params
0x18001c1fb  mov     rcx, rbp; this
0x18001c1fe  mov     rdx, [rdx+rdi*8]; struct _PregenParms *
0x18001c202  call    ?p_Populate@PoolKeyList@@AEAAJPEBU_PregenParms@@@Z; PoolKeyList::p_Populate(_PregenParms const *)
0x18001c207  mov     esi, eax
0x18001c209  test    eax, eax
0x18001c20b  jns     short loc_18001C226
0x18001c20d  mov     rcx, [rsp+48h]; this
0x18001c212  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c219  mov     r9d, eax; char *
0x18001c21c  mov     edx, 711h; void *
0x18001c221  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c226  test    ebx, ebx
0x18001c228  cmovz   ebx, esi
0x18001c22b  inc     rdi
0x18001c22e  cmp     rdi, 6
0x18001c232  jnz     short loc_18001C1F4
0x18001c234  test    ebx, ebx
0x18001c236  jns     short loc_18001C255
0x18001c238  mov     rcx, [rsp+48h]; this
0x18001c23d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c244  mov     r9d, ebx; char *
0x18001c247  mov     edx, 71Ch; void *
0x18001c24c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c251  mov     eax, ebx
0x18001c253  jmp     short loc_18001C257
0x18001c255  xor     eax, eax
0x18001c257  add     rsp, 28h
0x18001c25b  pop     rdi
0x18001c25c  pop     rsi
0x18001c25d  pop     rbp
0x18001c25e  pop     rbx
0x18001c25f  retn
```
