# SslpExportHybridConstituentKeys

- ea: `0x180014024`
- end: `0x1800142b0`
- name: `SslpExportHybridConstituentKeys`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180022e04`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x180013c6c`
- `0x180014024`
- `0x180021da8`
- `0x1800233d0`
- `0x1800237a0`

## string_xrefs

- `0x180014235`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180014283`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpExportHybridConstituentKeys(
        __int64 a1,
        char a2,
        unsigned int a3,
        BYTE **a4,
        BYTE **a5,
        unsigned int *a6,
        DWORD a7)
{
  BYTE **v9; // r13
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  DWORD v14; // ebx
  BYTE *v15; // rsi
  BYTE *v16; // r14
  int HybridPublicKeySizes; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  DWORD v20; // ebx
  const WCHAR *v21; // r15
  const wchar_t *v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // edx
  unsigned int v25; // ecx
  BYTE **v26; // rax
  _DWORD *v28; // [rsp+30h] [rbp-10h] BYREF
  DWORD v29; // [rsp+38h] [rbp-8h] BYREF
  DWORD v30; // [rsp+3Ch] [rbp-4h] BYREF
  __int64 v31; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v32; // [rsp+90h] [rbp+50h]
  BYTE **v33; // [rsp+98h] [rbp+58h]

  v33 = a4;
  v32 = a3;
  if ( !a1 || !a4 || (v9 = a5) == 0 || !a6 )
  {
    v11 = -2146893785;
    v12 = 499;
    v13 = 2148073511LL;
    goto LABEL_42;
  }
  v31 = 0;
  v28 = 0;
  v10 = SslpValidateConstituentKeys(a1, &v31, (__int64 *)&v28);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 511;
    v13 = (unsigned int)v10;
LABEL_42:
    DebugTraceError(v13, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v12);
    return v11;
  }
  v14 = *(_DWORD *)(a1 + 24);
  v15 = 0;
  if ( !a2 )
  {
    if ( v14 )
    {
      v15 = (BYTE *)SafeAllocaAllocateFromHeap(v14);
      if ( !v15 )
      {
        v11 = -2146893810;
        v12 = 522;
        v13 = 2148073486LL;
        goto LABEL_42;
      }
    }
  }
  v16 = 0;
  v29 = 0;
  HybridPublicKeySizes = SslpExportEphemeralKey(v31, L"ECCPUBLICBLOB", v15, v14, &v29, a7);
  v11 = HybridPublicKeySizes;
  if ( HybridPublicKeySizes < 0 )
  {
    v18 = 539;
LABEL_13:
    v19 = (unsigned int)HybridPublicKeySizes;
LABEL_35:
    DebugTraceError(v19, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v18);
    goto LABEL_36;
  }
  v20 = *(_DWORD *)(a1 + 40);
  if ( !a2 )
  {
    if ( v20 )
    {
      v16 = (BYTE *)SafeAllocaAllocateFromHeap(v20);
      if ( !v16 )
      {
        v11 = -2146893810;
        v18 = 550;
        v19 = 2148073486LL;
        goto LABEL_35;
      }
    }
  }
  v21 = L"MLKEMPUBLICBLOB";
  v30 = 0;
  if ( *((_QWORD *)v28 + 4) )
  {
    v22 = L"TLS_KEM_CIPHERTEXT";
    if ( !v28[10] )
      v22 = L"MLKEMPUBLICBLOB";
    v21 = v22;
  }
  HybridPublicKeySizes = SslpExportKemKey(v28, v21, v16, v20, &v30, a7);
  v11 = HybridPublicKeySizes;
  if ( HybridPublicKeySizes < 0 )
  {
    v18 = 573;
    goto LABEL_13;
  }
  v23 = *(unsigned __int16 *)(a1 + 8);
  LODWORD(v31) = 0;
  LODWORD(v28) = 0;
  HybridPublicKeySizes = SslpGetHybridPublicKeySizes(v23, v21, &v31, &v28);
  v11 = HybridPublicKeySizes;
  if ( HybridPublicKeySizes < 0 )
  {
    v18 = 586;
    goto LABEL_13;
  }
  v24 = v31 + 32;
  if ( (unsigned int)v31 >= 0xFFFFFFE0 )
  {
    v18 = 602;
LABEL_28:
    v11 = -1073741675;
    v19 = 3221225621LL;
    goto LABEL_35;
  }
  v25 = v24 + (_DWORD)v28;
  if ( v24 + (unsigned int)v28 < v24 )
  {
    v18 = 609;
    goto LABEL_28;
  }
  if ( v32 >= v25 )
  {
    v26 = v33;
    v11 = 0;
    *v9 = v16;
    *v26 = v15;
    return v11;
  }
  *a6 = v25;
  *(_DWORD *)(a1 + 24) = v29;
  *(_DWORD *)(a1 + 40) = v30;
  if ( !a2 )
  {
    v11 = -2146893784;
    v18 = 626;
    v19 = 2148073512LL;
    goto LABEL_35;
  }
  v11 = 0;
LABEL_36:
  if ( v15 )
    MSCryptFree(v15);
  if ( v16 )
    MSCryptFree(v16);
  return v11;
}

```

## disassembly

```asm
0x180014024  mov     [rsp-38h+arg_8], rbx
0x180014029  mov     [rsp-38h+arg_18], r9
0x18001402e  mov     [rsp-38h+arg_10], r8d
0x180014033  push    rbp
0x180014034  push    rsi
0x180014035  push    rdi
0x180014036  push    r12
0x180014038  push    r13
0x18001403a  push    r14
0x18001403c  push    r15
0x18001403e  mov     rbp, rsp
0x180014041  sub     rsp, 40h
0x180014045  mov     rax, r9
0x180014048  mov     r12b, dl
0x18001404b  mov     rdi, rcx
0x18001404e  test    rcx, rcx
0x180014051  jz      loc_180014273
0x180014057  test    rax, rax
0x18001405a  jz      loc_180014273
0x180014060  mov     r13, [rbp+arg_20]
0x180014064  test    r13, r13
0x180014067  jz      loc_180014273
0x18001406d  cmp     [rbp+arg_28], 0
0x180014072  jz      loc_180014273
0x180014078  lea     r8, [rbp+var_10]
0x18001407c  mov     [rbp+arg_0], 0
0x180014084  lea     rdx, [rbp+arg_0]
0x180014088  mov     [rbp+var_10], 0
0x180014090  call    SslpValidateConstituentKeys
0x180014095  mov     ebx, eax
0x180014097  test    eax, eax
0x180014099  jns     short loc_1800140A8
0x18001409b  mov     r9d, 1FFh
0x1800140a1  mov     ecx, eax
0x1800140a3  jmp     loc_180014283
0x1800140a8  mov     ebx, [rdi+18h]
0x1800140ab  xor     esi, esi
0x1800140ad  test    r12b, r12b
0x1800140b0  jnz     short loc_1800140DA
0x1800140b2  test    ebx, ebx
0x1800140b4  jz      short loc_1800140DA
0x1800140b6  mov     ecx, ebx
0x1800140b8  call    SafeAllocaAllocateFromHeap
0x1800140bd  mov     rsi, rax
0x1800140c0  test    rax, rax
0x1800140c3  jnz     short loc_1800140DA
0x1800140c5  mov     ebx, 8009000Eh
0x1800140ca  mov     r9d, 20Ah
0x1800140d0  mov     ecx, 8009000Eh
0x1800140d5  jmp     loc_180014283
0x1800140da  mov     eax, [rbp+arg_30]
0x1800140dd  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x1800140e4  mov     rcx, [rbp+arg_0]
0x1800140e8  xor     r14d, r14d
0x1800140eb  mov     [rsp+40h+var_18], eax
0x1800140ef  mov     r9d, ebx
0x1800140f2  lea     rax, [rbp+var_8]
0x1800140f6  mov     [rbp+var_8], r14d
0x1800140fa  mov     r8, rsi
0x1800140fd  mov     [rsp+40h+var_20], rax
0x180014102  call    SslpExportEphemeralKey
0x180014107  mov     ebx, eax
0x180014109  test    eax, eax
0x18001410b  jns     short loc_18001411A
0x18001410d  mov     r9d, 21Bh
0x180014113  mov     ecx, eax
0x180014115  jmp     loc_180014235
0x18001411a  mov     ebx, [rdi+28h]
0x18001411d  test    r12b, r12b
0x180014120  jnz     short loc_18001414A
0x180014122  test    ebx, ebx
0x180014124  jz      short loc_18001414A
0x180014126  mov     ecx, ebx
0x180014128  call    SafeAllocaAllocateFromHeap
0x18001412d  mov     r14, rax
0x180014130  test    rax, rax
0x180014133  jnz     short loc_18001414A
0x180014135  mov     ebx, 8009000Eh
0x18001413a  mov     r9d, 226h
0x180014140  mov     ecx, 8009000Eh
0x180014145  jmp     loc_180014235
0x18001414a  mov     rcx, [rbp+var_10]
0x18001414e  lea     r15, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180014155  mov     [rbp+var_4], 0
0x18001415c  cmp     qword ptr [rcx+20h], 0
0x180014161  jz      short loc_180014175
0x180014163  cmp     dword ptr [rcx+28h], 0
0x180014167  lea     rax, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x18001416e  cmovz   rax, r15
0x180014172  mov     r15, rax
0x180014175  mov     eax, [rbp+arg_30]
0x180014178  mov     r9d, ebx
0x18001417b  mov     [rsp+40h+var_18], eax
0x18001417f  mov     r8, r14
0x180014182  lea     rax, [rbp+var_4]
0x180014186  mov     rdx, r15
0x180014189  mov     [rsp+40h+var_20], rax
0x18001418e  call    SslpExportKemKey
0x180014193  mov     ebx, eax
0x180014195  test    eax, eax
0x180014197  jns     short loc_1800141A4
0x180014199  mov     r9d, 23Dh
0x18001419f  jmp     loc_180014113
0x1800141a4  movzx   ecx, word ptr [rdi+8]
0x1800141a8  lea     r9, [rbp+var_10]
0x1800141ac  lea     r8, [rbp+arg_0]
0x1800141b0  mov     dword ptr [rbp+arg_0], 0
0x1800141b7  mov     rdx, r15
0x1800141ba  mov     dword ptr [rbp+var_10], 0
0x1800141c1  call    SslpGetHybridPublicKeySizes
0x1800141c6  mov     ebx, eax
0x1800141c8  test    eax, eax
0x1800141ca  jns     short loc_1800141D7
0x1800141cc  mov     r9d, 24Ah
0x1800141d2  jmp     loc_180014113
0x1800141d7  mov     edx, dword ptr [rbp+arg_0]
0x1800141da  add     edx, 20h ; ' '
0x1800141dd  cmp     edx, 20h ; ' '
0x1800141e0  jnb     short loc_1800141F4
0x1800141e2  mov     r9d, 25Ah
0x1800141e8  mov     ebx, 0C0000095h
0x1800141ed  mov     ecx, 0C0000095h
0x1800141f2  jmp     short loc_180014235
0x1800141f4  mov     ecx, dword ptr [rbp+var_10]
0x1800141f7  add     ecx, edx
0x1800141f9  cmp     ecx, edx
0x1800141fb  jnb     short loc_180014205
0x1800141fd  mov     r9d, 261h
0x180014203  jmp     short loc_1800141E8
0x180014205  cmp     [rbp+arg_10], ecx
0x180014208  jnb     short loc_180014264
0x18001420a  mov     rax, [rbp+arg_28]
0x18001420e  mov     [rax], ecx
0x180014210  mov     eax, [rbp+var_8]
0x180014213  mov     [rdi+18h], eax
0x180014216  mov     eax, [rbp+var_4]
0x180014219  mov     [rdi+28h], eax
0x18001421c  test    r12b, r12b
0x18001421f  jz      short loc_180014225
0x180014221  xor     ebx, ebx
0x180014223  jmp     short loc_180014248
0x180014225  mov     ebx, 80090028h
0x18001422a  mov     r9d, 272h
0x180014230  mov     ecx, 80090028h
0x180014235  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001423c  lea     rdx, aStatus_0; "status"
0x180014243  call    DebugTraceError
0x180014248  test    rsi, rsi
0x18001424b  jz      short loc_180014255
0x18001424d  mov     rcx, rsi
0x180014250  call    MSCryptFree
0x180014255  test    r14, r14
0x180014258  jz      short loc_180014296
0x18001425a  mov     rcx, r14
0x18001425d  call    MSCryptFree
0x180014262  jmp     short loc_180014296
0x180014264  mov     rax, [rbp+arg_18]
0x180014268  xor     ebx, ebx
0x18001426a  mov     [r13+0], r14
0x18001426e  mov     [rax], rsi
0x180014271  jmp     short loc_180014296
0x180014273  mov     ebx, 80090027h
0x180014278  mov     r9d, 1F3h
0x18001427e  mov     ecx, 80090027h
0x180014283  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001428a  lea     rdx, aStatus_0; "status"
0x180014291  call    DebugTraceError
0x180014296  mov     eax, ebx
0x180014298  mov     rbx, [rsp+40h+arg_8]
0x1800142a0  add     rsp, 40h
0x1800142a4  pop     r15
0x1800142a6  pop     r14
0x1800142a8  pop     r13
0x1800142aa  pop     r12
0x1800142ac  pop     rdi
0x1800142ad  pop     rsi
0x1800142ae  pop     rbp
0x1800142af  retn
```
