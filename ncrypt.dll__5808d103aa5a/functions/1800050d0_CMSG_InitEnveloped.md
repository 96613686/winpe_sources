# CMSG_InitEnveloped

- ea: `0x1800050d0`
- end: `0x18000537c`
- name: `CMSG_InitEnveloped`
- size: `684`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003a68`
- `0x180006090`

## callees

- `0x180003ce4`
- `0x180004310`
- `0x180004454`
- `0x1800050d0`
- `0x180006be4`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000525e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180005329`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180005349`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`

## pseudocode

```c
__int64 __fastcall CMSG_InitEnveloped(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rsi
  __int64 v5; // r12
  __int64 v8; // rax
  unsigned int v9; // edx
  int v10; // ecx
  _QWORD *v11; // r14
  __int64 v12; // r10
  _DWORD *v13; // r15
  __int64 *v14; // r10
  int v15; // edx
  unsigned int BCryptOidInfo; // edi
  int v17; // r8d
  __int64 v18; // rax
  unsigned int CEKBCryptKeyAndAlgorithmInfo; // eax
  unsigned int v20; // eax
  int v21; // edx
  int v22; // r8d
  int v24; // eax
  int v25; // [rsp+90h] [rbp+8h] BYREF
  __int64 v26; // [rsp+98h] [rbp+10h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+18h]
  unsigned int v28; // [rsp+A8h] [rbp+20h]

  v28 = a4;
  v27 = a3;
  v4 = 0;
  v5 = a1 + 88;
  v26 = 0;
  v25 = 0;
  *(_QWORD *)(a1 + 88) = a1 + 16;
  v8 = *(_QWORD *)(a2 + 8);
  v9 = 11;
  if ( v8 )
  {
    *(_QWORD *)(a1 + 288) = *(_QWORD *)(v8 + 8);
    v10 = **(_DWORD **)(a2 + 8);
  }
  else
  {
    *(_QWORD *)(a1 + 288) = qword_1800224B0;
    v10 = 11;
  }
  *(_DWORD *)(a1 + 280) = v10;
  v11 = (_QWORD *)(a1 + 144);
  v12 = *(_QWORD *)(a2 + 16);
  v13 = (_DWORD *)(a1 + 136);
  if ( v12 )
  {
    v14 = *(__int64 **)(v12 + 8);
    *(_QWORD *)(a1 + 304) = v14;
    v9 = **(_DWORD **)(a2 + 16);
    *(_DWORD *)(a1 + 296) = v9;
    *v11 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL);
    *v13 = *(_DWORD *)(*(_QWORD *)(a2 + 16) + 16LL);
  }
  else
  {
    v14 = qword_180022508;
    *(_DWORD *)(a1 + 296) = 11;
    *(_QWORD *)(a1 + 304) = qword_180022508;
  }
  BCryptOidInfo = CNG_FindBCryptOidInfo(v14, v9, 1u, (_QWORD *)(a1 + 112));
  if ( !BCryptOidInfo )
  {
    v18 = *(_QWORD *)(a2 + 24);
    if ( v18 )
    {
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(v18 + 8);
      *(_DWORD *)(a1 + 120) = **(_DWORD **)(a2 + 24);
    }
    CEKBCryptKeyAndAlgorithmInfo = CNG_CreateCEKBCryptKeyAndAlgorithmInfo(
                                     (unsigned int *)(*(_QWORD *)(a1 + 112) + 40LL),
                                     a1 + 16,
                                     v5);
    BCryptOidInfo = CEKBCryptKeyAndAlgorithmInfo;
    if ( CEKBCryptKeyAndAlgorithmInfo )
    {
      DebugTraceError(
        CEKBCryptKeyAndAlgorithmInfo,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
        763);
      goto LABEL_15;
    }
    *(_QWORD *)(a1 + 320) = *v11;
    *(_DWORD *)(a1 + 312) = *v13;
    if ( v27 )
    {
      v20 = CNG_EncryptAndAllocate(v5, v27, v28, &v26, &v25);
      BCryptOidInfo = v20;
      if ( v20 )
      {
        DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c", 781);
        v4 = v26;
        goto LABEL_15;
      }
      v4 = v26;
      BCryptOidInfo = CMSG_AddBuffer(a1, v26);
      if ( BCryptOidInfo )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            v22,
            (unsigned int)"Status",
            BCryptOidInfo,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
            27);
        goto LABEL_15;
      }
      v24 = v25;
      *(_QWORD *)(a1 + 344) = v4;
      v4 = 0;
      *(_DWORD *)(a1 + 336) = v24;
    }
    BCryptOidInfo = 0;
    *(_DWORD *)(a1 + 352) = *(_DWORD *)(a2 + 32);
    *(_QWORD *)(a1 + 360) = *(_QWORD *)(a2 + 40);
    *(_DWORD *)(a1 + 224) = 2;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v17,
      (unsigned int)"Status",
      BCryptOidInfo,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
      234);
LABEL_15:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(a1 + 32))(v4);
  return BCryptOidInfo;
}

```

## disassembly

```asm
0x1800050d0  mov     rax, rsp
0x1800050d3  mov     [rax+20h], r9d
0x1800050d7  mov     [rax+18h], r8
0x1800050db  push    rbx
0x1800050dc  push    rbp
0x1800050dd  push    rsi
0x1800050de  push    rdi
0x1800050df  push    r12
0x1800050e1  push    r13
0x1800050e3  push    r14
0x1800050e5  push    r15
0x1800050e7  sub     rsp, 48h
0x1800050eb  xor     esi, esi
0x1800050ed  lea     r12, [rcx+58h]
0x1800050f1  mov     [rax+10h], rsi
0x1800050f5  mov     rbp, rdx
0x1800050f8  mov     [rax+8], esi
0x1800050fb  mov     rbx, rcx
0x1800050fe  lea     rax, [rcx+10h]
0x180005102  mov     [r12], rax
0x180005106  mov     rax, [rdx+8]
0x18000510a  lea     edx, [rsi+0Bh]
0x18000510d  test    rax, rax
0x180005110  jnz     loc_18000530D
0x180005116  lea     rax, qword_1800224B0
0x18000511d  mov     [rcx+120h], rax
0x180005124  mov     ecx, edx
0x180005126  mov     [rbx+118h], ecx
0x18000512c  lea     r14, [rbx+90h]
0x180005133  mov     r10, [rbp+10h]
0x180005137  lea     r15, [rbx+88h]
0x18000513e  test    r10, r10
0x180005141  jz      loc_1800052F4
0x180005147  mov     r10, [r10+8]
0x18000514b  mov     [rbx+130h], r10
0x180005152  mov     rax, [rbp+10h]
0x180005156  mov     edx, [rax]
0x180005158  mov     [rbx+128h], edx
0x18000515e  mov     rax, [rbp+10h]
0x180005162  mov     rcx, [rax+18h]
0x180005166  mov     [r14], rcx
0x180005169  mov     rax, [rbp+10h]
0x18000516d  mov     ecx, [rax+10h]
0x180005170  mov     [r15], ecx
0x180005173  lea     r9, [rbx+70h]
0x180005177  mov     r8d, 1
0x18000517d  mov     rcx, r10
0x180005180  call    CNG_FindBCryptOidInfo
0x180005185  mov     edi, eax
0x180005187  test    eax, eax
0x180005189  jnz     loc_1800052CE
0x18000518f  mov     rax, [rbp+18h]
0x180005193  test    rax, rax
0x180005196  jz      short loc_1800051AC
0x180005198  mov     rax, [rax+8]
0x18000519c  mov     [rbx+80h], rax
0x1800051a3  mov     rax, [rbp+18h]
0x1800051a7  mov     ecx, [rax]
0x1800051a9  mov     [rbx+78h], ecx
0x1800051ac  mov     rcx, [rbx+70h]
0x1800051b0  lea     rdx, [rbx+10h]
0x1800051b4  add     rcx, 28h ; '('
0x1800051b8  mov     r8, r12
0x1800051bb  call    CNG_CreateCEKBCryptKeyAndAlgorithmInfo
0x1800051c0  mov     edi, eax
0x1800051c2  test    eax, eax
0x1800051c4  jnz     loc_180005323
0x1800051ca  mov     rax, [r14]
0x1800051cd  mov     [rbx+140h], rax
0x1800051d4  mov     eax, [r15]
0x1800051d7  mov     [rbx+138h], eax
0x1800051dd  mov     rax, [rsp+88h+arg_10]
0x1800051e5  test    rax, rax
0x1800051e8  jz      loc_1800052AC
0x1800051ee  mov     r8d, [rsp+88h+arg_18]
0x1800051f6  lea     rcx, [rsp+88h+arg_0]
0x1800051fe  mov     [rsp+88h+var_68], rcx
0x180005203  lea     r9, [rsp+88h+arg_8]
0x18000520b  mov     rcx, r12
0x18000520e  mov     rdx, rax
0x180005211  call    CNG_EncryptAndAllocate
0x180005216  mov     edi, eax
0x180005218  test    eax, eax
0x18000521a  jnz     loc_180005343
0x180005220  mov     rsi, [rsp+88h+arg_8]
0x180005228  mov     rcx, rbx
0x18000522b  mov     rdx, rsi
0x18000522e  call    CMSG_AddBuffer
0x180005233  mov     edi, eax
0x180005235  test    eax, eax
0x180005237  jz      short loc_180005296
0x180005239  mov     rcx, cs:WPP_GLOBAL_Control
0x180005240  lea     rax, WPP_GLOBAL_Control
0x180005247  cmp     rcx, rax
0x18000524a  jz      short loc_18000527A
0x18000524c  test    byte ptr [rcx+1Ch], 1
0x180005250  jz      short loc_18000527A
0x180005252  mov     [rsp+88h+var_58], 31Bh
0x18000525a  mov     rcx, [rcx+10h]
0x18000525e  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005265  mov     [rsp+88h+var_60], rax
0x18000526a  lea     r9, aStatus; "Status"
0x180005271  mov     dword ptr [rsp+88h+var_68], edi
0x180005275  call    WPP_SF_sDsd
0x18000527a  test    rsi, rsi
0x18000527d  jnz     loc_18000536B
0x180005283  mov     eax, edi
0x180005285  add     rsp, 48h
0x180005289  pop     r15
0x18000528b  pop     r14
0x18000528d  pop     r13
0x18000528f  pop     r12
0x180005291  pop     rdi
0x180005292  pop     rsi
0x180005293  pop     rbp
0x180005294  pop     rbx
0x180005295  retn
0x180005296  mov     eax, [rsp+88h+arg_0]
0x18000529d  mov     [rbx+158h], rsi
0x1800052a4  xor     esi, esi
0x1800052a6  mov     [rbx+150h], eax
0x1800052ac  mov     eax, [rbp+20h]
0x1800052af  xor     edi, edi
0x1800052b1  mov     [rbx+160h], eax
0x1800052b7  mov     rax, [rbp+28h]
0x1800052bb  mov     [rbx+168h], rax
0x1800052c2  mov     dword ptr [rbx+0E0h], 2
0x1800052cc  jmp     short loc_18000527A
0x1800052ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052d5  lea     rax, WPP_GLOBAL_Control
0x1800052dc  cmp     rcx, rax
0x1800052df  jz      short loc_18000527A
0x1800052e1  test    byte ptr [rcx+1Ch], 1
0x1800052e5  jz      short loc_18000527A
0x1800052e7  mov     [rsp+88h+var_58], 2EAh
0x1800052ef  jmp     loc_18000525A
0x1800052f4  lea     r10, qword_180022508
0x1800052fb  mov     [rbx+128h], edx
0x180005301  mov     [rbx+130h], r10
0x180005308  jmp     loc_180005173
0x18000530d  mov     rax, [rax+8]
0x180005311  mov     [rcx+120h], rax
0x180005318  mov     rax, [rbp+8]
0x18000531c  mov     ecx, [rax]
0x18000531e  jmp     loc_180005126
0x180005323  mov     r9d, 2FBh
0x180005329  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005330  lea     rdx, aStatus; "Status"
0x180005337  mov     ecx, eax
0x180005339  call    DebugTraceError
0x18000533e  jmp     loc_18000527A
0x180005343  mov     r9d, 30Dh
0x180005349  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005350  lea     rdx, aStatus; "Status"
0x180005357  mov     ecx, eax
0x180005359  call    DebugTraceError
0x18000535e  mov     rsi, [rsp+88h+arg_8]
0x180005366  jmp     loc_18000527A
0x18000536b  mov     rax, [rbx+20h]
0x18000536f  mov     rcx, rsi
0x180005372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005377  jmp     loc_180005283
```
