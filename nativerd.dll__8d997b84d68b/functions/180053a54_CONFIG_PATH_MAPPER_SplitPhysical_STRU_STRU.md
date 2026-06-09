# CONFIG_PATH_MAPPER::SplitPhysical(STRU *,STRU *)

- ea: `0x180053a54`
- end: `0x180053acb`
- name: `?SplitPhysical@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@0@Z`
- size: `119`
- prototype: `__int64 __fastcall(struct STRU *, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180008d00`
- `0x18000a240`

## callees

- `0x180053a54`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053a7a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053a7a`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180053a6f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180053a6f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053aa1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053aa1`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180053ab3`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180053ab3`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::SplitPhysical(struct STRU *a1, struct STRU *a2)
{
  __int64 CCH; // rbx
  unsigned __int16 *Str; // rax
  int v7; // edi

  if ( !a1 )
    return 2147942487LL;
  CCH = STRU::QueryCCH(a1);
  Str = STRU::QueryStr(a1);
  do
  {
    if ( !CCH )
      return (unsigned int)-2147024883;
    --CCH;
  }
  while ( Str[CCH] != 92 );
  v7 = 0;
  if ( !a2 || (v7 = STRU::Copy(a2, &Str[CCH + 1]), v7 >= 0) )
    STRU::SetLen(a1, CCH + 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180053a54  push    rbx
0x180053a56  push    rbp
0x180053a57  push    rsi
0x180053a58  push    rdi
0x180053a59  sub     rsp, 28h
0x180053a5d  mov     rbp, rdx
0x180053a60  mov     rsi, rcx
0x180053a63  test    rcx, rcx
0x180053a66  jnz     short loc_180053A6F
0x180053a68  mov     eax, 80070057h
0x180053a6d  jmp     short loc_180053AC2
0x180053a6f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180053a75  mov     rcx, rsi
0x180053a78  mov     ebx, eax
0x180053a7a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180053a80  test    rbx, rbx
0x180053a83  jz      short loc_180053ABB
0x180053a85  dec     rbx
0x180053a88  cmp     word ptr [rax+rbx*2], 5Ch ; '\'
0x180053a8d  jnz     short loc_180053A80
0x180053a8f  xor     edi, edi
0x180053a91  test    rbp, rbp
0x180053a94  jz      short loc_180053AAD
0x180053a96  lea     rdx, [rax+2]
0x180053a9a  mov     rcx, rbp
0x180053a9d  lea     rdx, [rdx+rbx*2]
0x180053aa1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180053aa7  mov     edi, eax
0x180053aa9  test    eax, eax
0x180053aab  js      short loc_180053AC0
0x180053aad  lea     edx, [rbx+1]
0x180053ab0  mov     rcx, rsi
0x180053ab3  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180053ab9  jmp     short loc_180053AC0
0x180053abb  mov     edi, 8007000Dh
0x180053ac0  mov     eax, edi
0x180053ac2  add     rsp, 28h
0x180053ac6  pop     rdi
0x180053ac7  pop     rsi
0x180053ac8  pop     rbp
0x180053ac9  pop     rbx
0x180053aca  retn
```
