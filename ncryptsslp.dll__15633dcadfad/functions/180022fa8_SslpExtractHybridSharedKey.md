# SslpExtractHybridSharedKey

- ea: `0x180022fa8`
- end: `0x18002322d`
- name: `SslpExtractHybridSharedKey`
- size: `645`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000dea0`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x180013f08`
- `0x180021efc`
- `0x180022fa8`
- `0x180023314`
- `0x180023a54`
- `0x180024fb0`

## string_xrefs

- `0x180023042`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023081`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x1800230c9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023192`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpExtractHybridSharedKey(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  _BYTE *v4; // r14
  size_t v5; // r15
  size_t v6; // r13
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int KemSharedKey; // eax
  unsigned int v16; // r12d
  char *v17; // rsi
  int HybridKeyConstituentKeyIndices; // eax
  __int64 v19; // rcx
  __int64 v20; // r9
  char *v21; // rcx
  void *v22; // rdx
  size_t v23; // r8
  __int64 v24; // rcx
  _BYTE *v25; // rax
  _BYTE *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  _BYTE *v29; // rax
  size_t Size; // [rsp+20h] [rbp-20h] BYREF
  void *v32; // [rsp+28h] [rbp-18h] BYREF
  void *Src; // [rsp+30h] [rbp-10h] BYREF
  __int64 v34; // [rsp+38h] [rbp-8h]

  v4 = 0;
  Src = 0;
  LODWORD(v5) = 0;
  v32 = 0;
  LODWORD(v6) = 0;
  Size = 0;
  v34 = ((__int64 (*)(void))SslpValidateHybridKeyHandle)();
  v7 = v34;
  v9 = SslpValidateHybridKeyHandle(v8);
  v12 = v9;
  if ( v34 && v9 && v10 && v11 )
  {
    v13 = SslpExtractEcdhSharedKey(*(_QWORD *)(v34 + 16), *(_QWORD *)(v9 + 16), &Src, &Size);
    v14 = v13;
    if ( v13 < 0 )
    {
      DebugTraceError(
        (unsigned int)v13,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
        1318);
      LODWORD(v5) = Size;
      goto LABEL_22;
    }
    KemSharedKey = SslpExtractKemSharedKey(
                     *(_QWORD *)(v7 + 32),
                     *(_QWORD *)(v12 + 32),
                     (__int64 *)&v32,
                     (unsigned int *)&Size + 1);
    v14 = KemSharedKey;
    if ( KemSharedKey < 0 )
    {
      DebugTraceError(
        (unsigned int)KemSharedKey,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
        1329);
      v4 = v32;
      LODWORD(v5) = Size;
      LODWORD(v6) = HIDWORD(Size);
      goto LABEL_22;
    }
    v6 = HIDWORD(Size);
    v5 = (unsigned int)Size;
    v16 = Size + HIDWORD(Size);
    v17 = (char *)SafeAllocaAllocateFromHeap((unsigned int)(Size + HIDWORD(Size)));
    if ( !v17 )
    {
      v14 = -2146893810;
      DebugTraceError(2148073486LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 1338);
      v4 = v32;
      goto LABEL_22;
    }
    Size = 0;
    HybridKeyConstituentKeyIndices = SslpGetHybridKeyConstituentKeyIndices(
                                       *(unsigned __int16 *)(v34 + 8),
                                       (char *)&Size + 4,
                                       &Size);
    v14 = HybridKeyConstituentKeyIndices;
    if ( HybridKeyConstituentKeyIndices >= 0 )
    {
      if ( Size == 1 )
      {
        memmove(v17, Src, v5);
        v4 = v32;
        v21 = &v17[v5];
        v22 = v32;
        v23 = v6;
      }
      else
      {
        v4 = v32;
        memmove(v17, v32, v6);
        v22 = Src;
        v21 = &v17[v6];
        v23 = v5;
      }
      memmove(v21, v22, v23);
      *a3 = v17;
      *a4 = v16;
      goto LABEL_22;
    }
    v4 = v32;
    v19 = (unsigned int)HybridKeyConstituentKeyIndices;
    v20 = 1350;
  }
  else
  {
    v17 = 0;
    v14 = -2146893785;
    v16 = 0;
    v19 = 2148073511LL;
    v20 = 1307;
  }
  DebugTraceError(v19, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v20);
  if ( v17 )
  {
    v24 = v16;
    v25 = v17;
    if ( v16 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    MSCryptFree(v17);
  }
LABEL_22:
  v26 = Src;
  if ( Src )
  {
    v27 = (unsigned int)v5;
    if ( (_DWORD)v5 )
    {
      do
      {
        *v26++ = 0;
        --v27;
      }
      while ( v27 );
    }
    MSCryptFree(Src);
  }
  if ( v4 )
  {
    v28 = (unsigned int)v6;
    v29 = v4;
    if ( (_DWORD)v6 )
    {
      do
      {
        *v29++ = 0;
        --v28;
      }
      while ( v28 );
    }
    MSCryptFree(v4);
  }
  return v14;
}

```

## disassembly

```asm
0x180022fa8  mov     [rsp-38h+arg_0], rbx
0x180022fad  mov     [rsp-38h+arg_18], r9
0x180022fb2  mov     [rsp-38h+arg_10], r8
0x180022fb7  push    rbp
0x180022fb8  push    rsi
0x180022fb9  push    rdi
0x180022fba  push    r12
0x180022fbc  push    r13
0x180022fbe  push    r14
0x180022fc0  push    r15
0x180022fc2  mov     rbp, rsp
0x180022fc5  sub     rsp, 40h
0x180022fc9  xor     r14d, r14d
0x180022fcc  mov     [rbp+Src], 0
0x180022fd4  xor     r15d, r15d
0x180022fd7  mov     [rbp+var_18], r14
0x180022fdb  xor     r13d, r13d
0x180022fde  mov     dword ptr [rbp+Size], r15d
0x180022fe2  mov     dword ptr [rbp+Size+4], r13d
0x180022fe6  call    SslpValidateHybridKeyHandle
0x180022feb  mov     rcx, rdx
0x180022fee  mov     [rbp+var_8], rax
0x180022ff2  mov     rsi, rax
0x180022ff5  call    SslpValidateHybridKeyHandle
0x180022ffa  mov     rbx, rax
0x180022ffd  test    rsi, rsi
0x180023000  jz      loc_18002317D
0x180023006  test    rax, rax
0x180023009  jz      loc_18002317D
0x18002300f  test    r8, r8
0x180023012  jz      loc_18002317D
0x180023018  test    r9, r9
0x18002301b  jz      loc_18002317D
0x180023021  mov     rdx, [rax+10h]
0x180023025  lea     r9, [rbp+Size]
0x180023029  mov     rcx, [rsi+10h]
0x18002302d  lea     r8, [rbp+Src]
0x180023031  call    SslpExtractEcdhSharedKey
0x180023036  mov     edi, eax
0x180023038  test    eax, eax
0x18002303a  jns     short loc_180023060
0x18002303c  mov     r9d, 526h
0x180023042  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023049  lea     rdx, aStatus_0; "status"
0x180023050  mov     ecx, eax
0x180023052  call    DebugTraceError
0x180023057  mov     r15d, dword ptr [rbp+Size]
0x18002305b  jmp     loc_1800231C9
0x180023060  mov     rdx, [rbx+20h]
0x180023064  lea     r9, [rbp+Size+4]
0x180023068  mov     rcx, [rsi+20h]
0x18002306c  lea     r8, [rbp+var_18]
0x180023070  call    SslpExtractKemSharedKey
0x180023075  mov     edi, eax
0x180023077  test    eax, eax
0x180023079  jns     short loc_1800230A7
0x18002307b  mov     r9d, 531h
0x180023081  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023088  lea     rdx, aStatus_0; "status"
0x18002308f  mov     ecx, eax
0x180023091  call    DebugTraceError
0x180023096  mov     r14, [rbp+var_18]
0x18002309a  mov     r15d, dword ptr [rbp+Size]
0x18002309e  mov     r13d, dword ptr [rbp+Size+4]
0x1800230a2  jmp     loc_1800231C9
0x1800230a7  mov     r13d, dword ptr [rbp+Size+4]
0x1800230ab  mov     r15d, dword ptr [rbp+Size]
0x1800230af  lea     r12d, [r15+r13]
0x1800230b3  mov     ecx, r12d
0x1800230b6  call    SafeAllocaAllocateFromHeap
0x1800230bb  mov     rsi, rax
0x1800230be  test    rax, rax
0x1800230c1  jnz     short loc_1800230EF
0x1800230c3  mov     r9d, 53Ah
0x1800230c9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800230d0  lea     rdx, aStatus_0; "status"
0x1800230d7  mov     ecx, 8009000Eh
0x1800230dc  mov     edi, 8009000Eh
0x1800230e1  call    DebugTraceError
0x1800230e6  mov     r14, [rbp+var_18]
0x1800230ea  jmp     loc_1800231C9
0x1800230ef  mov     rcx, [rbp+var_8]
0x1800230f3  lea     r8, [rbp+Size]
0x1800230f7  lea     rdx, [rbp+Size+4]
0x1800230fb  mov     dword ptr [rbp+Size+4], r14d
0x1800230ff  mov     dword ptr [rbp+Size], r14d
0x180023103  movzx   ecx, word ptr [rcx+8]
0x180023107  call    SslpGetHybridKeyConstituentKeyIndices
0x18002310c  mov     edi, eax
0x18002310e  test    eax, eax
0x180023110  jns     short loc_180023120
0x180023112  mov     r14, [rbp+var_18]
0x180023116  mov     ecx, eax
0x180023118  mov     r9d, 546h
0x18002311e  jmp     short loc_180023192
0x180023120  cmp     dword ptr [rbp+Size+4], r14d
0x180023124  jnz     short loc_18002314B
0x180023126  cmp     dword ptr [rbp+Size], 1
0x18002312a  jnz     short loc_18002314B
0x18002312c  mov     rdx, [rbp+Src]; Src
0x180023130  mov     r8, r15; Size
0x180023133  mov     rcx, rsi; void *
0x180023136  call    memmove
0x18002313b  mov     r14, [rbp+var_18]
0x18002313f  lea     rcx, [r15+rsi]
0x180023143  mov     rdx, r14
0x180023146  mov     r8, r13
0x180023149  jmp     short loc_180023168
0x18002314b  mov     r14, [rbp+var_18]
0x18002314f  mov     r8, r13; Size
0x180023152  mov     rdx, r14; Src
0x180023155  mov     rcx, rsi; void *
0x180023158  call    memmove
0x18002315d  mov     rdx, [rbp+Src]; Src
0x180023161  lea     rcx, [rsi+r13]; void *
0x180023165  mov     r8, r15; Size
0x180023168  call    memmove
0x18002316d  mov     rax, [rbp+arg_10]
0x180023171  mov     [rax], rsi
0x180023174  mov     rax, [rbp+arg_18]
0x180023178  mov     [rax], r12d
0x18002317b  jmp     short loc_1800231C9
0x18002317d  xor     esi, esi
0x18002317f  mov     edi, 80090027h
0x180023184  xor     r12d, r12d
0x180023187  mov     ecx, 80090027h
0x18002318c  mov     r9d, 51Bh
0x180023192  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023199  lea     rdx, aStatus_0; "status"
0x1800231a0  call    DebugTraceError
0x1800231a5  test    rsi, rsi
0x1800231a8  jz      short loc_1800231C9
0x1800231aa  mov     ecx, r12d
0x1800231ad  mov     rax, rsi
0x1800231b0  test    r12d, r12d
0x1800231b3  jz      short loc_1800231C1
0x1800231b5  mov     byte ptr [rax], 0
0x1800231b8  inc     rax
0x1800231bb  sub     rcx, 1
0x1800231bf  jnz     short loc_1800231B5
0x1800231c1  mov     rcx, rsi
0x1800231c4  call    MSCryptFree
0x1800231c9  mov     rax, [rbp+Src]
0x1800231cd  test    rax, rax
0x1800231d0  jz      short loc_1800231EF
0x1800231d2  mov     ecx, r15d
0x1800231d5  test    r15d, r15d
0x1800231d8  jz      short loc_1800231E6
0x1800231da  mov     byte ptr [rax], 0
0x1800231dd  inc     rax
0x1800231e0  sub     rcx, 1
0x1800231e4  jnz     short loc_1800231DA
0x1800231e6  mov     rcx, [rbp+Src]
0x1800231ea  call    MSCryptFree
0x1800231ef  test    r14, r14
0x1800231f2  jz      short loc_180023213
0x1800231f4  mov     ecx, r13d
0x1800231f7  mov     rax, r14
0x1800231fa  test    r13d, r13d
0x1800231fd  jz      short loc_18002320B
0x1800231ff  mov     byte ptr [rax], 0
0x180023202  inc     rax
0x180023205  sub     rcx, 1
0x180023209  jnz     short loc_1800231FF
0x18002320b  mov     rcx, r14
0x18002320e  call    MSCryptFree
0x180023213  mov     rbx, [rsp+40h+arg_0]
0x18002321b  mov     eax, edi
0x18002321d  add     rsp, 40h
0x180023221  pop     r15
0x180023223  pop     r14
0x180023225  pop     r13
0x180023227  pop     r12
0x180023229  pop     rdi
0x18002322a  pop     rsi
0x18002322b  pop     rbp
0x18002322c  retn
```
