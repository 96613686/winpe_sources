# TlsExpandLabel

- ea: `0x180083ed4`
- end: `0x1800840c4`
- name: `TlsExpandLabel`
- size: `496`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180083c48`
- `0x1800840cc`
- `0x1800843c0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800361d0`
- `0x180083ed4`
- `0x18009f780`

## import_xrefs

- `ntoskrnl!strnlen` at `0x180083f30`
- `ntoskrnl!strnlen` at `0x180083f30`

## string_xrefs

- `0x180083f8e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008408b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExpandLabel(__int64 a1, const char *a2, void *a3, __int64 a4, __int64 a5, unsigned __int16 a6)
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
  v8 = (unsigned __int8)a4;
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
  v15 = MSCryptAlloc((unsigned __int16)(v8 + 4 + (unsigned __int8)(v9 + 6)), a2, a3, a4);
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
0x180083ed4  mov     [rsp-38h+arg_18], rbx
0x180083ed9  mov     [rsp-38h+Src], r8
0x180083ede  mov     [rsp-38h+arg_0], rcx
0x180083ee3  push    rbp
0x180083ee4  push    rsi
0x180083ee5  push    rdi
0x180083ee6  push    r12
0x180083ee8  push    r13
0x180083eea  push    r14
0x180083eec  push    r15
0x180083eee  mov     rbp, rsp
0x180083ef1  sub     rsp, 60h
0x180083ef5  mov     eax, dword ptr cs:aTls13; "tls13 "
0x180083efb  xor     esi, esi
0x180083efd  mov     [rbp+var_28], eax
0x180083f00  mov     r13, rdx
0x180083f03  movzx   eax, word ptr cs:aTls13+4; "3 "
0x180083f0a  mov     rbx, rcx
0x180083f0d  mov     [rbp+arg_8], ax
0x180083f11  mov     al, byte ptr cs:aTls13+6; ""
0x180083f17  mov     [rbp+var_2A], al
0x180083f1a  movzx   r14d, r9b
0x180083f1e  test    rdx, rdx
0x180083f21  jnz     short loc_180083F28
0x180083f23  mov     r15d, esi
0x180083f26  jmp     short loc_180083F43
0x180083f28  mov     edx, 0F9h; MaxCount
0x180083f2d  mov     rcx, r13; Str
0x180083f30  call    cs:__imp_strnlen
0x180083f37  nop     dword ptr [rax+rax+00h]
0x180083f3c  mov     r8, [rbp+Src]
0x180083f40  mov     r15, rax
0x180083f43  mov     [rbp+var_20], esi
0x180083f46  lea     rax, [rbp+var_20]
0x180083f4a  mov     [rbp+var_8], rax
0x180083f4e  mov     [rbp+var_1C], 14h
0x180083f55  mov     [rbp+var_18], rsi
0x180083f59  mov     [rbp+var_10], esi
0x180083f5c  mov     [rbp+var_C], 1
0x180083f63  mov     [rbp+var_30], esi
0x180083f66  test    rbx, rbx
0x180083f69  jz      short loc_180083F7E
0x180083f6b  lea     ebx, [r15+6]
0x180083f6f  cmp     bl, 0FFh
0x180083f72  jnb     short loc_180083F7E
0x180083f74  test    r8, r8
0x180083f77  jnz     short loc_180083FBC
0x180083f79  test    r14b, r14b
0x180083f7c  jz      short loc_180083FC1
0x180083f7e  mov     ebx, 0C000000Dh
0x180083f83  mov     r9d, 0F96h
0x180083f89  mov     ecx, 0C000000Dh
0x180083f8e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083f95  lea     rdx, aStatus; "Status"
0x180083f9c  call    DebugTraceError
0x180083fa1  mov     eax, ebx
0x180083fa3  mov     rbx, [rsp+60h+arg_18]
0x180083fab  add     rsp, 60h
0x180083faf  pop     r15
0x180083fb1  pop     r14
0x180083fb3  pop     r13
0x180083fb5  pop     r12
0x180083fb7  pop     rdi
0x180083fb8  pop     rsi
0x180083fb9  pop     rbp
0x180083fba  retn
0x180083fbc  test    r14b, r14b
0x180083fbf  jz      short loc_180083F7E
0x180083fc1  cmp     [rbp+arg_20], rsi
0x180083fc5  jz      short loc_180083F7E
0x180083fc7  movzx   edi, [rbp+arg_28]
0x180083fcb  test    di, di
0x180083fce  jz      short loc_180083F7E
0x180083fd0  movzx   ecx, bl
0x180083fd3  lea     eax, [r14+4]
0x180083fd7  add     cx, ax
0x180083fda  movzx   r12d, cx
0x180083fde  mov     ecx, r12d
0x180083fe1  call    MSCryptAlloc
0x180083fe6  mov     rsi, rax
0x180083fe9  test    rax, rax
0x180083fec  jnz     short loc_180084000
0x180083fee  mov     ebx, 0C0000017h
0x180083ff3  mov     r9d, 0FA9h
0x180083ff9  mov     ecx, 0C0000017h
0x180083ffe  jmp     short loc_180083F8E
0x180084000  mov     [rsi+2], bl
0x180084003  lea     rcx, [rsi+9]; void *
0x180084007  movzx   eax, di
0x18008400a  mov     [rsi+1], dil
0x18008400e  shr     ax, 8
0x180084012  mov     rdx, r13; Src
0x180084015  mov     [rsi], al
0x180084017  mov     eax, [rbp+var_28]
0x18008401a  mov     [rsi+3], eax
0x18008401d  movzx   eax, [rbp+arg_8]
0x180084021  movzx   ebx, r15b
0x180084025  mov     r8d, ebx; Size
0x180084028  mov     [rsi+7], ax
0x18008402c  call    memmove
0x180084031  mov     rdx, [rbp+Src]; Src
0x180084035  lea     rcx, [rsi+0Ah]
0x180084039  add     rcx, rbx; void *
0x18008403c  mov     [rbx+rsi+9], r14b
0x180084041  mov     r8, r14; Size
0x180084044  call    memmove
0x180084049  movzx   edi, [rbp+arg_28]
0x18008404d  lea     rax, [rbp+var_30]
0x180084051  mov     r8, [rbp+arg_20]
0x180084055  lea     rdx, [rbp+var_10]
0x180084059  mov     rcx, [rbp+arg_0]
0x18008405d  mov     r9d, edi
0x180084060  mov     [rsp+60h+var_38], 0
0x180084068  mov     [rsp+60h+var_40], rax
0x18008406d  mov     [rbp+var_20], r12d
0x180084071  mov     [rbp+var_18], rsi
0x180084075  call    BCryptKeyDerivation
0x18008407a  mov     ebx, eax
0x18008407c  test    eax, eax
0x18008407e  jnz     short loc_180084085
0x180084080  cmp     [rbp+var_30], edi
0x180084083  jz      short loc_1800840A0
0x180084085  mov     r9d, 0FC3h
0x18008408b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180084092  lea     rdx, aStatus; "Status"
0x180084099  mov     ecx, eax
0x18008409b  call    DebugTraceError
0x1800840a0  mov     rcx, r12
0x1800840a3  mov     rax, rsi
0x1800840a6  test    r12, r12
0x1800840a9  jz      short loc_1800840B7
0x1800840ab  mov     byte ptr [rax], 0
0x1800840ae  inc     rax
0x1800840b1  sub     rcx, 1
0x1800840b5  jnz     short loc_1800840AB
0x1800840b7  mov     rcx, rsi; P
0x1800840ba  call    MSCryptFree
0x1800840bf  jmp     loc_180083FA1
```
