# TlsExpandLabel

- ea: `0x18008d0d4`
- end: `0x18008d2c4`
- name: `TlsExpandLabel`
- size: `496`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008ce48`
- `0x18008d2cc`
- `0x18008d5c0`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18003f740`
- `0x18008d0d4`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!strnlen` at `0x18008d130`
- `ntoskrnl!strnlen` at `0x18008d130`

## string_xrefs

- `0x18008d18e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008d28b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExpandLabel(
        __int64 a1,
        const char *a2,
        void *a3,
        unsigned __int8 a4,
        __int64 a5,
        unsigned __int16 a6)
{
  size_t v8; // r14
  unsigned __int8 v9; // r15
  unsigned __int8 v10; // al
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v15; // rax
  _BYTE *v16; // rsi
  unsigned int v17; // eax
  __int64 v18; // rcx
  _BYTE *v19; // rax
  int v20; // [rsp+30h] [rbp-30h] BYREF
  char v21; // [rsp+36h] [rbp-2Ah]
  int v22; // [rsp+38h] [rbp-28h]
  _DWORD v23[2]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE *v24; // [rsp+48h] [rbp-18h]
  _DWORD v25[2]; // [rsp+50h] [rbp-10h] BYREF
  _DWORD *v26; // [rsp+58h] [rbp-8h]
  void *Src; // [rsp+B0h] [rbp+50h]

  Src = a3;
  v22 = *(_DWORD *)"tls13 ";
  v21 = aTls13[6];
  v8 = a4;
  if ( a2 )
  {
    v10 = strnlen(a2, 0xF9u);
    a3 = Src;
    v9 = v10;
  }
  else
  {
    v9 = 0;
  }
  v23[0] = 0;
  v26 = v23;
  v23[1] = 20;
  v24 = 0;
  v25[0] = 0;
  v25[1] = 1;
  v20 = 0;
  if ( !a1 || v9 == 0xF9 )
    goto LABEL_8;
  if ( a3 )
  {
    if ( !(_BYTE)v8 )
      goto LABEL_8;
  }
  else if ( (_BYTE)v8 )
  {
LABEL_8:
    v11 = -1073741811;
    v12 = 3990;
    v13 = 3221225485LL;
LABEL_9:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v12);
    return v11;
  }
  if ( !a5 || !a6 )
    goto LABEL_8;
  v15 = MSCryptAlloc((unsigned __int16)(v8 + 4 + (unsigned __int8)(v9 + 6)), a2);
  v16 = (_BYTE *)v15;
  if ( !v15 )
  {
    v11 = -1073741801;
    v12 = 4009;
    v13 = 3221225495LL;
    goto LABEL_9;
  }
  *(_BYTE *)(v15 + 2) = v9 + 6;
  *(_BYTE *)(v15 + 1) = a6;
  *(_BYTE *)v15 = HIBYTE(a6);
  *(_DWORD *)(v15 + 3) = v22;
  *(_WORD *)(v15 + 7) = *(_WORD *)"3 ";
  memmove((void *)(v15 + 9), a2, v9);
  v16[v9 + 9] = v8;
  memmove(&v16[v9 + 10], Src, v8);
  v23[0] = (unsigned __int16)(v8 + 4 + (unsigned __int8)(v9 + 6));
  v24 = v16;
  v17 = BCryptKeyDerivation(a1, (__int64)v25, a5, a6, (__int64)&v20, 0);
  v11 = v17;
  if ( v17 || v20 != a6 )
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4035);
  v18 = (unsigned __int16)(v8 + 4 + (unsigned __int8)(v9 + 6));
  v19 = v16;
  if ( (_WORD)v8 + 4 + (unsigned __int8)(v9 + 6) )
  {
    do
    {
      *v19++ = 0;
      --v18;
    }
    while ( v18 );
  }
  MSCryptFree(v16);
  return v11;
}

```

## disassembly

```asm
0x18008d0d4  mov     [rsp-38h+arg_18], rbx
0x18008d0d9  mov     [rsp-38h+Src], r8
0x18008d0de  mov     [rsp-38h+arg_0], rcx
0x18008d0e3  push    rbp
0x18008d0e4  push    rsi
0x18008d0e5  push    rdi
0x18008d0e6  push    r12
0x18008d0e8  push    r13
0x18008d0ea  push    r14
0x18008d0ec  push    r15
0x18008d0ee  mov     rbp, rsp
0x18008d0f1  sub     rsp, 60h
0x18008d0f5  mov     eax, dword ptr cs:aTls13; "tls13 "
0x18008d0fb  xor     esi, esi
0x18008d0fd  mov     [rbp+var_28], eax
0x18008d100  mov     r13, rdx
0x18008d103  movzx   eax, word ptr cs:aTls13+4; "3 "
0x18008d10a  mov     rbx, rcx
0x18008d10d  mov     [rbp+arg_8], ax
0x18008d111  mov     al, byte ptr cs:aTls13+6; ""
0x18008d117  mov     [rbp+var_2A], al
0x18008d11a  movzx   r14d, r9b
0x18008d11e  test    rdx, rdx
0x18008d121  jnz     short loc_18008D128
0x18008d123  mov     r15d, esi
0x18008d126  jmp     short loc_18008D143
0x18008d128  mov     edx, 0F9h; MaxCount
0x18008d12d  mov     rcx, r13; Str
0x18008d130  call    cs:__imp_strnlen
0x18008d137  nop     dword ptr [rax+rax+00h]
0x18008d13c  mov     r8, [rbp+Src]
0x18008d140  mov     r15, rax
0x18008d143  mov     [rbp+var_20], esi
0x18008d146  lea     rax, [rbp+var_20]
0x18008d14a  mov     [rbp+var_8], rax
0x18008d14e  mov     [rbp+var_1C], 14h
0x18008d155  mov     [rbp+var_18], rsi
0x18008d159  mov     [rbp+var_10], esi
0x18008d15c  mov     [rbp+var_C], 1
0x18008d163  mov     [rbp+var_30], esi
0x18008d166  test    rbx, rbx
0x18008d169  jz      short loc_18008D17E
0x18008d16b  lea     ebx, [r15+6]
0x18008d16f  cmp     bl, 0FFh
0x18008d172  jnb     short loc_18008D17E
0x18008d174  test    r8, r8
0x18008d177  jnz     short loc_18008D1BC
0x18008d179  test    r14b, r14b
0x18008d17c  jz      short loc_18008D1C1
0x18008d17e  mov     ebx, 0C000000Dh
0x18008d183  mov     r9d, 0F96h
0x18008d189  mov     ecx, 0C000000Dh
0x18008d18e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d195  lea     rdx, aStatus; "Status"
0x18008d19c  call    DebugTraceError
0x18008d1a1  mov     eax, ebx
0x18008d1a3  mov     rbx, [rsp+60h+arg_18]
0x18008d1ab  add     rsp, 60h
0x18008d1af  pop     r15
0x18008d1b1  pop     r14
0x18008d1b3  pop     r13
0x18008d1b5  pop     r12
0x18008d1b7  pop     rdi
0x18008d1b8  pop     rsi
0x18008d1b9  pop     rbp
0x18008d1ba  retn
0x18008d1bc  test    r14b, r14b
0x18008d1bf  jz      short loc_18008D17E
0x18008d1c1  cmp     [rbp+arg_20], rsi
0x18008d1c5  jz      short loc_18008D17E
0x18008d1c7  movzx   edi, [rbp+arg_28]
0x18008d1cb  test    di, di
0x18008d1ce  jz      short loc_18008D17E
0x18008d1d0  movzx   ecx, bl
0x18008d1d3  lea     eax, [r14+4]
0x18008d1d7  add     cx, ax
0x18008d1da  movzx   r12d, cx
0x18008d1de  mov     ecx, r12d
0x18008d1e1  call    MSCryptAlloc
0x18008d1e6  mov     rsi, rax
0x18008d1e9  test    rax, rax
0x18008d1ec  jnz     short loc_18008D200
0x18008d1ee  mov     ebx, 0C0000017h
0x18008d1f3  mov     r9d, 0FA9h
0x18008d1f9  mov     ecx, 0C0000017h
0x18008d1fe  jmp     short loc_18008D18E
0x18008d200  mov     [rsi+2], bl
0x18008d203  lea     rcx, [rsi+9]; void *
0x18008d207  movzx   eax, di
0x18008d20a  mov     [rsi+1], dil
0x18008d20e  shr     ax, 8
0x18008d212  mov     rdx, r13; Src
0x18008d215  mov     [rsi], al
0x18008d217  mov     eax, [rbp+var_28]
0x18008d21a  mov     [rsi+3], eax
0x18008d21d  movzx   eax, [rbp+arg_8]
0x18008d221  movzx   ebx, r15b
0x18008d225  mov     r8d, ebx; Size
0x18008d228  mov     [rsi+7], ax
0x18008d22c  call    memmove
0x18008d231  mov     rdx, [rbp+Src]; Src
0x18008d235  lea     rcx, [rsi+0Ah]
0x18008d239  add     rcx, rbx; void *
0x18008d23c  mov     [rbx+rsi+9], r14b
0x18008d241  mov     r8, r14; Size
0x18008d244  call    memmove
0x18008d249  movzx   edi, [rbp+arg_28]
0x18008d24d  lea     rax, [rbp+var_30]
0x18008d251  mov     r8, [rbp+arg_20]
0x18008d255  lea     rdx, [rbp+var_10]
0x18008d259  mov     rcx, [rbp+arg_0]
0x18008d25d  mov     r9d, edi
0x18008d260  mov     [rsp+60h+var_38], 0
0x18008d268  mov     [rsp+60h+var_40], rax
0x18008d26d  mov     [rbp+var_20], r12d
0x18008d271  mov     [rbp+var_18], rsi
0x18008d275  call    BCryptKeyDerivation
0x18008d27a  mov     ebx, eax
0x18008d27c  test    eax, eax
0x18008d27e  jnz     short loc_18008D285
0x18008d280  cmp     [rbp+var_30], edi
0x18008d283  jz      short loc_18008D2A0
0x18008d285  mov     r9d, 0FC3h
0x18008d28b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d292  lea     rdx, aStatus; "Status"
0x18008d299  mov     ecx, eax
0x18008d29b  call    DebugTraceError
0x18008d2a0  mov     rcx, r12
0x18008d2a3  mov     rax, rsi
0x18008d2a6  test    r12, r12
0x18008d2a9  jz      short loc_18008D2B7
0x18008d2ab  mov     byte ptr [rax], 0
0x18008d2ae  inc     rax
0x18008d2b1  sub     rcx, 1
0x18008d2b5  jnz     short loc_18008D2AB
0x18008d2b7  mov     rcx, rsi; P
0x18008d2ba  call    MSCryptFree
0x18008d2bf  jmp     loc_18008D1A1
```
