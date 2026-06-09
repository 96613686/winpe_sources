# TlsExpandLabel

- ea: `0x180082ee4`
- end: `0x1800830d4`
- name: `TlsExpandLabel`
- size: `496`
- prototype: `__int64 __fastcall(__int64, const char *, void *, unsigned __int8, __int64, unsigned __int16)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180082c58`
- `0x1800830dc`
- `0x1800833d0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800356d0`
- `0x180082ee4`
- `0x18009da40`

## import_xrefs

- `ntoskrnl!strnlen` at `0x180082f40`
- `ntoskrnl!strnlen` at `0x180082f40`

## string_xrefs

- `0x180082f9e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008309b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  int v27; // [rsp+A0h] [rbp+40h]
  void *Src; // [rsp+B0h] [rbp+50h]

  Src = a3;
  v27 = a1;
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
  v17 = BCryptKeyDerivation(v27, (unsigned int)v25, a5, a6, (__int64)&v20, 0);
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
0x180082ee4  mov     [rsp-38h+arg_18], rbx
0x180082ee9  mov     [rsp-38h+Src], r8
0x180082eee  mov     [rsp-38h+arg_0], rcx
0x180082ef3  push    rbp
0x180082ef4  push    rsi
0x180082ef5  push    rdi
0x180082ef6  push    r12
0x180082ef8  push    r13
0x180082efa  push    r14
0x180082efc  push    r15
0x180082efe  mov     rbp, rsp
0x180082f01  sub     rsp, 60h
0x180082f05  mov     eax, dword ptr cs:aTls13; "tls13 "
0x180082f0b  xor     esi, esi
0x180082f0d  mov     [rbp+var_28], eax
0x180082f10  mov     r13, rdx
0x180082f13  movzx   eax, word ptr cs:aTls13+4; "3 "
0x180082f1a  mov     rbx, rcx
0x180082f1d  mov     [rbp+arg_8], ax
0x180082f21  mov     al, byte ptr cs:aTls13+6; ""
0x180082f27  mov     [rbp+var_2A], al
0x180082f2a  movzx   r14d, r9b
0x180082f2e  test    rdx, rdx
0x180082f31  jnz     short loc_180082F38
0x180082f33  mov     r15d, esi
0x180082f36  jmp     short loc_180082F53
0x180082f38  mov     edx, 0F9h; MaxCount
0x180082f3d  mov     rcx, r13; Str
0x180082f40  call    cs:__imp_strnlen
0x180082f47  nop     dword ptr [rax+rax+00h]
0x180082f4c  mov     r8, [rbp+Src]
0x180082f50  mov     r15, rax
0x180082f53  mov     [rbp+var_20], esi
0x180082f56  lea     rax, [rbp+var_20]
0x180082f5a  mov     [rbp+var_8], rax
0x180082f5e  mov     [rbp+var_1C], 14h
0x180082f65  mov     [rbp+var_18], rsi
0x180082f69  mov     [rbp+var_10], esi
0x180082f6c  mov     [rbp+var_C], 1
0x180082f73  mov     [rbp+var_30], esi
0x180082f76  test    rbx, rbx
0x180082f79  jz      short loc_180082F8E
0x180082f7b  lea     ebx, [r15+6]
0x180082f7f  cmp     bl, 0FFh
0x180082f82  jnb     short loc_180082F8E
0x180082f84  test    r8, r8
0x180082f87  jnz     short loc_180082FCC
0x180082f89  test    r14b, r14b
0x180082f8c  jz      short loc_180082FD1
0x180082f8e  mov     ebx, 0C000000Dh
0x180082f93  mov     r9d, 0F96h
0x180082f99  mov     ecx, 0C000000Dh
0x180082f9e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082fa5  lea     rdx, aStatus; "Status"
0x180082fac  call    DebugTraceError
0x180082fb1  mov     eax, ebx
0x180082fb3  mov     rbx, [rsp+60h+arg_18]
0x180082fbb  add     rsp, 60h
0x180082fbf  pop     r15
0x180082fc1  pop     r14
0x180082fc3  pop     r13
0x180082fc5  pop     r12
0x180082fc7  pop     rdi
0x180082fc8  pop     rsi
0x180082fc9  pop     rbp
0x180082fca  retn
0x180082fcc  test    r14b, r14b
0x180082fcf  jz      short loc_180082F8E
0x180082fd1  cmp     [rbp+arg_20], rsi
0x180082fd5  jz      short loc_180082F8E
0x180082fd7  movzx   edi, [rbp+arg_28]
0x180082fdb  test    di, di
0x180082fde  jz      short loc_180082F8E
0x180082fe0  movzx   ecx, bl
0x180082fe3  lea     eax, [r14+4]
0x180082fe7  add     cx, ax
0x180082fea  movzx   r12d, cx
0x180082fee  mov     ecx, r12d
0x180082ff1  call    MSCryptAlloc
0x180082ff6  mov     rsi, rax
0x180082ff9  test    rax, rax
0x180082ffc  jnz     short loc_180083010
0x180082ffe  mov     ebx, 0C0000017h
0x180083003  mov     r9d, 0FA9h
0x180083009  mov     ecx, 0C0000017h
0x18008300e  jmp     short loc_180082F9E
0x180083010  mov     [rsi+2], bl
0x180083013  lea     rcx, [rsi+9]; void *
0x180083017  movzx   eax, di
0x18008301a  mov     [rsi+1], dil
0x18008301e  shr     ax, 8
0x180083022  mov     rdx, r13; Src
0x180083025  mov     [rsi], al
0x180083027  mov     eax, [rbp+var_28]
0x18008302a  mov     [rsi+3], eax
0x18008302d  movzx   eax, [rbp+arg_8]
0x180083031  movzx   ebx, r15b
0x180083035  mov     r8d, ebx; Size
0x180083038  mov     [rsi+7], ax
0x18008303c  call    memmove
0x180083041  mov     rdx, [rbp+Src]; Src
0x180083045  lea     rcx, [rsi+0Ah]
0x180083049  add     rcx, rbx; void *
0x18008304c  mov     [rbx+rsi+9], r14b
0x180083051  mov     r8, r14; Size
0x180083054  call    memmove
0x180083059  movzx   edi, [rbp+arg_28]
0x18008305d  lea     rax, [rbp+var_30]
0x180083061  mov     r8, [rbp+arg_20]
0x180083065  lea     rdx, [rbp+var_10]
0x180083069  mov     rcx, [rbp+arg_0]
0x18008306d  mov     r9d, edi
0x180083070  mov     [rsp+60h+var_38], 0
0x180083078  mov     [rsp+60h+var_40], rax
0x18008307d  mov     [rbp+var_20], r12d
0x180083081  mov     [rbp+var_18], rsi
0x180083085  call    BCryptKeyDerivation
0x18008308a  mov     ebx, eax
0x18008308c  test    eax, eax
0x18008308e  jnz     short loc_180083095
0x180083090  cmp     [rbp+var_30], edi
0x180083093  jz      short loc_1800830B0
0x180083095  mov     r9d, 0FC3h
0x18008309b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800830a2  lea     rdx, aStatus; "Status"
0x1800830a9  mov     ecx, eax
0x1800830ab  call    DebugTraceError
0x1800830b0  mov     rcx, r12
0x1800830b3  mov     rax, rsi
0x1800830b6  test    r12, r12
0x1800830b9  jz      short loc_1800830C7
0x1800830bb  mov     byte ptr [rax], 0
0x1800830be  inc     rax
0x1800830c1  sub     rcx, 1
0x1800830c5  jnz     short loc_1800830BB
0x1800830c7  mov     rcx, rsi; P
0x1800830ca  call    MSCryptFree
0x1800830cf  jmp     loc_180082FB1
```
