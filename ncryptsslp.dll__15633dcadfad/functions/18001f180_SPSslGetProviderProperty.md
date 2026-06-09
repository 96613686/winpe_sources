# SPSslGetProviderProperty

- ea: `0x18001f180`
- end: `0x18001f220`
- name: `SPSslGetProviderProperty`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001f180`

## string_xrefs

- `0x18001f205`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGetProviderProperty(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned __int64 v12; // rax

  if ( !SslpValidateProvHandle(a1) )
  {
    v9 = -2146893786;
    v10 = 3341;
    v11 = 2148073510LL;
LABEL_16:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v10);
    return v9;
  }
  if ( !v6 )
  {
    v10 = 3348;
LABEL_15:
    v9 = -2146893785;
    v11 = 2148073511LL;
    goto LABEL_16;
  }
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v6 + 2 * v12) );
  if ( v12 > 0x40 )
  {
    v10 = 3354;
    goto LABEL_15;
  }
  if ( !v7 || !v8 )
  {
    v10 = 3361;
    goto LABEL_15;
  }
  if ( a6 )
  {
    v9 = -2146893815;
    v10 = 3368;
    v11 = 2148073481LL;
    goto LABEL_16;
  }
  return (unsigned int)-2146893783;
}

```

## disassembly

```asm
0x18001f180  push    rbx
0x18001f182  sub     rsp, 20h
0x18001f186  call    SslpValidateProvHandle
0x18001f18b  xor     ecx, ecx
0x18001f18d  test    rax, rax
0x18001f190  jnz     short loc_18001F1A4
0x18001f192  mov     ebx, 80090026h
0x18001f197  mov     r9d, 0D0Dh
0x18001f19d  mov     ecx, 80090026h
0x18001f1a2  jmp     short loc_18001F205
0x18001f1a4  test    rdx, rdx
0x18001f1a7  jnz     short loc_18001F1B1
0x18001f1a9  mov     r9d, 0D14h
0x18001f1af  jmp     short loc_18001F1FB
0x18001f1b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f1b5  inc     rax
0x18001f1b8  cmp     [rdx+rax*2], cx
0x18001f1bc  jnz     short loc_18001F1B5
0x18001f1be  cmp     rax, 40h ; '@'
0x18001f1c2  jbe     short loc_18001F1CC
0x18001f1c4  mov     r9d, 0D1Ah
0x18001f1ca  jmp     short loc_18001F1FB
0x18001f1cc  test    r8, r8
0x18001f1cf  jz      short loc_18001F1F5
0x18001f1d1  test    r9, r9
0x18001f1d4  jz      short loc_18001F1F5
0x18001f1d6  cmp     [rsp+28h+arg_28], ecx
0x18001f1da  jz      short loc_18001F1EE
0x18001f1dc  mov     ebx, 80090009h
0x18001f1e1  mov     r9d, 0D28h
0x18001f1e7  mov     ecx, 80090009h
0x18001f1ec  jmp     short loc_18001F205
0x18001f1ee  mov     ebx, 80090029h
0x18001f1f3  jmp     short loc_18001F218
0x18001f1f5  mov     r9d, 0D21h
0x18001f1fb  mov     ebx, 80090027h
0x18001f200  mov     ecx, 80090027h
0x18001f205  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f20c  lea     rdx, aStatus; "Status"
0x18001f213  call    DebugTraceError
0x18001f218  mov     eax, ebx
0x18001f21a  add     rsp, 20h
0x18001f21e  pop     rbx
0x18001f21f  retn
```
