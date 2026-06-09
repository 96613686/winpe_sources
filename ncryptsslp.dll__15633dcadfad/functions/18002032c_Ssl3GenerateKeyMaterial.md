# Ssl3GenerateKeyMaterial

- ea: `0x18002032c`
- end: `0x18002070f`
- name: `Ssl3GenerateKeyMaterial`
- size: `995`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006b60`
- `0x180020248`

## callees

- `0x180009160`
- `0x18000b654`
- `0x180018ac0`
- `0x18002032c`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18002050c`
- `bcrypt!BCryptHashData` at `0x18002052a`
- `bcrypt!BCryptHashData` at `0x180020549`
- `bcrypt!BCryptHashData` at `0x1800205d2`
- `bcrypt!BCryptHashData` at `0x1800205ed`
- `bcrypt!BCryptHashData` at `0x18002050c`
- `bcrypt!BCryptHashData` at `0x18002052a`
- `bcrypt!BCryptHashData` at `0x180020549`
- `bcrypt!BCryptHashData` at `0x1800205d2`
- `bcrypt!BCryptHashData` at `0x1800205ed`
- `bcrypt!BCryptCreateHash` at `0x1800204e7`
- `bcrypt!BCryptCreateHash` at `0x1800205b4`
- `bcrypt!BCryptCreateHash` at `0x1800204e7`
- `bcrypt!BCryptCreateHash` at `0x1800205b4`
- `bcrypt!BCryptFinishHash` at `0x180020568`
- `bcrypt!BCryptFinishHash` at `0x18002060d`
- `bcrypt!BCryptFinishHash` at `0x180020568`
- `bcrypt!BCryptFinishHash` at `0x18002060d`
- `bcrypt!BCryptDestroyHash` at `0x18002057c`
- `bcrypt!BCryptDestroyHash` at `0x18002061d`
- `bcrypt!BCryptDestroyHash` at `0x1800206c7`
- `bcrypt!BCryptDestroyHash` at `0x18002057c`
- `bcrypt!BCryptDestroyHash` at `0x18002061d`
- `bcrypt!BCryptDestroyHash` at `0x1800206c7`

## string_xrefs

- `0x1800206ab`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3GenerateKeyMaterial(
        __int64 a1,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  unsigned int v9; // eax
  __int64 v10; // rbx
  UCHAR *p_phHash; // rdi
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  UCHAR *v17; // rax
  NTSTATUS v18; // ebx
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned int i; // esi
  NTSTATUS v22; // eax
  __int64 v24; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  ULONG cbInput; // [rsp+48h] [rbp+8h] BYREF
  PUCHAR v27; // [rsp+50h] [rbp+10h]
  __int64 v28; // [rsp+58h] [rbp+18h]
  PUCHAR pbInput[9]; // [rsp+60h] [rbp+20h]
  UCHAR pbOutput[24]; // [rsp+A8h] [rbp+68h] BYREF

  v28 = a6;
  pbInput[0] = (PUCHAR)"A";
  pbInput[1] = (PUCHAR)"BB";
  pbInput[2] = (PUCHAR)"CCC";
  pbInput[3] = (PUCHAR)"DDDD";
  pbInput[4] = (PUCHAR)"EEEEE";
  pbInput[5] = (PUCHAR)"FFFFFF";
  pbInput[6] = (PUCHAR)"GGGGGGG";
  pbInput[7] = (PUCHAR)"HHHHHHHH";
  v27 = a4;
  cbInput = a3;
  phHash = 0;
  if ( (a7 & 0xF) != 0 || a7 > 0x80 )
  {
    p_phHash = 0;
    v18 = -2146893779;
    v19 = 201;
    v20 = 2148073517LL;
LABEL_46:
    DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v19);
  }
  else
  {
    v9 = *(_DWORD *)(a1 + 352);
    v10 = *(unsigned int *)(a1 + 320);
    if ( (unsigned int)v10 <= v9 )
      v10 = v9;
    p_phHash = 0;
    if ( !(_DWORD)v10 )
      goto LABEL_55;
    if ( (unsigned int)v10 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_55;
    v12 = (unsigned int)v10 + g_ulAdditionalProbeSize + 8;
    if ( v12 < (unsigned int)v10 || !(unsigned int)VerifyStackAvailable(v12) )
      goto LABEL_55;
    v13 = v10 + 23;
    if ( v10 + 23 <= (unsigned __int64)(v10 + 8) )
      v13 = 0xFFFFFFFFFFFFFF0LL;
    v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
    v15 = alloca(v14);
    v16 = alloca(v14);
    p_phHash = (UCHAR *)&phHash;
    if ( &v24 == (__int64 *)-64LL || (LODWORD(phHash) = 1801679955, (p_phHash = (UCHAR *)&cbInput) == 0) )
    {
LABEL_55:
      if ( v10 + 8 >= (unsigned __int64)(unsigned int)v10 )
      {
        v17 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_phHash = v17;
        if ( v17 )
        {
          *(_DWORD *)v17 = 1885431112;
          p_phHash = v17 + 8;
        }
      }
    }
    if ( !p_phHash )
    {
      v18 = -2146893810;
      v19 = 213;
      v20 = 2148073486LL;
      goto LABEL_46;
    }
    for ( i = 0; i < a7 >> 4; ++i )
    {
      v22 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(a1 + 336), &phHash, p_phHash, *(_DWORD *)(a1 + 352), 0, 0, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 233;
        goto LABEL_33;
      }
      v22 = BCryptHashData(phHash, pbInput[i], i + 1, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 244;
        goto LABEL_33;
      }
      v22 = BCryptHashData(phHash, a2, cbInput, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 255;
        goto LABEL_33;
      }
      v22 = BCryptHashData(phHash, v27, 0x40u, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 266;
        goto LABEL_33;
      }
      v22 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 277;
        goto LABEL_33;
      }
      v18 = BCryptDestroyHash(phHash);
      phHash = 0;
      if ( v18 < 0 )
      {
        v19 = 285;
        v20 = (unsigned int)v18;
        goto LABEL_46;
      }
      v22 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(a1 + 304), &phHash, p_phHash, *(_DWORD *)(a1 + 320), 0, 0, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 303;
        goto LABEL_33;
      }
      v22 = BCryptHashData(phHash, a2, cbInput, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 314;
        goto LABEL_33;
      }
      v22 = BCryptHashData(phHash, pbOutput, 0x14u, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 325;
        goto LABEL_33;
      }
      v22 = BCryptFinishHash(phHash, (PUCHAR)(v28 + 16 * i), 0x10u, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 336;
        goto LABEL_33;
      }
      v22 = BCryptDestroyHash(phHash);
      phHash = 0;
      v18 = v22;
      if ( v22 < 0 )
      {
        v19 = 344;
LABEL_33:
        v20 = (unsigned int)v22;
        goto LABEL_46;
      }
    }
    v18 = 0;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18002032c  push    rbp
0x18002032e  push    rbx
0x18002032f  push    rsi
0x180020330  push    rdi
0x180020331  push    r12
0x180020333  push    r13
0x180020335  push    r14
0x180020337  push    r15
0x180020339  sub     rsp, 0D8h
0x180020340  lea     rbp, [rsp+40h]
0x180020345  mov     rax, cs:__security_cookie
0x18002034c  xor     rax, rbp
0x18002034f  mov     [rbp+0D0h+var_50], rax
0x180020356  mov     rax, [rbp+0D0h+arg_28]
0x18002035d  mov     r12, rdx
0x180020360  mov     r14d, [rbp+0D0h+arg_30]
0x180020367  mov     r13, rcx
0x18002036a  mov     [rbp+0D0h+var_B8], rax
0x18002036e  lea     rax, aA; "A"
0x180020375  mov     [rbp+0D0h+pbInput], rax
0x180020379  lea     rax, aBb; "BB"
0x180020380  mov     [rbp+0D0h+var_A8], rax
0x180020384  lea     rax, aCcc; "CCC"
0x18002038b  mov     [rbp+0D0h+var_A0], rax
0x18002038f  lea     rax, aDddd; "DDDD"
0x180020396  mov     [rbp+0D0h+var_98], rax
0x18002039a  lea     rax, aEeeee; "EEEEE"
0x1800203a1  mov     [rbp+0D0h+var_90], rax
0x1800203a5  lea     rax, aFfffff; "FFFFFF"
0x1800203ac  mov     [rbp+0D0h+var_88], rax
0x1800203b0  lea     rax, aGgggggg; "GGGGGGG"
0x1800203b7  mov     [rbp+0D0h+var_80], rax
0x1800203bb  lea     rax, aHhhhhhhh; "HHHHHHHH"
0x1800203c2  mov     [rbp+0D0h+var_78], rax
0x1800203c6  mov     [rbp+0D0h+var_C0], r9
0x1800203ca  mov     [rbp+0D0h+cbInput], r8d
0x1800203ce  mov     [rbp+0D0h+phHash], 0
0x1800203d6  test    r14b, 0Fh
0x1800203da  jnz     loc_180020699
0x1800203e0  cmp     r14d, 80h
0x1800203e7  ja      loc_180020699
0x1800203ed  mov     eax, [rcx+160h]
0x1800203f3  mov     ebx, [rcx+140h]
0x1800203f9  cmp     ebx, eax
0x1800203fb  cmovbe  ebx, eax
0x1800203fe  xor     edi, edi
0x180020400  test    ebx, ebx
0x180020402  jz      short loc_180020467
0x180020404  mov     esi, ebx
0x180020406  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18002040d  ja      short loc_180020467
0x18002040f  mov     rcx, cs:g_ulAdditionalProbeSize
0x180020416  add     rcx, 8
0x18002041a  add     rcx, rsi
0x18002041d  cmp     rcx, rsi
0x180020420  jb      short loc_180020467
0x180020422  call    VerifyStackAvailable
0x180020427  test    eax, eax
0x180020429  jz      short loc_180020467
0x18002042b  lea     rax, [rbx+8]
0x18002042f  lea     rcx, [rax+0Fh]
0x180020433  cmp     rcx, rax
0x180020436  ja      short loc_180020442
0x180020438  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180020442  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180020446  mov     rax, rcx
0x180020449  call    _alloca_probe
0x18002044e  sub     rsp, rcx
0x180020451  lea     rdi, [rsp+110h+phHash]
0x180020456  test    rdi, rdi
0x180020459  jz      short loc_180020467
0x18002045b  mov     dword ptr [rdi], 6B637453h
0x180020461  add     rdi, 8
0x180020465  jnz     short loc_180020490
0x180020467  mov     eax, ebx
0x180020469  lea     rcx, [rbx+8]
0x18002046d  cmp     rcx, rax
0x180020470  jb      short loc_180020490
0x180020472  mov     rax, cs:g_pfnAllocate
0x180020479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002047e  mov     rdi, rax
0x180020481  test    rax, rax
0x180020484  jz      short loc_180020490
0x180020486  mov     dword ptr [rax], 70616548h
0x18002048c  add     rdi, 8
0x180020490  test    rdi, rdi
0x180020493  jnz     short loc_1800204AA
0x180020495  mov     ebx, 8009000Eh
0x18002049a  mov     r9d, 0D5h
0x1800204a0  mov     ecx, 8009000Eh
0x1800204a5  jmp     loc_1800206AB
0x1800204aa  xor     esi, esi
0x1800204ac  shr     r14d, 4
0x1800204b0  cmp     esi, r14d
0x1800204b3  jnb     loc_180020695
0x1800204b9  mov     r9d, [r13+160h]; cbHashObject
0x1800204c0  lea     rdx, [rbp+0D0h+phHash]; phHash
0x1800204c4  mov     rcx, [r13+150h]; hAlgorithm
0x1800204cb  mov     r8, rdi; pbHashObject
0x1800204ce  mov     [rsp+110h+dwFlags], 0; dwFlags
0x1800204d6  mov     [rsp+110h+cbSecret], 0; cbSecret
0x1800204de  mov     [rsp+110h+pbSecret], 0; pbSecret
0x1800204e7  call    cs:__imp_BCryptCreateHash
0x1800204ed  mov     ebx, eax
0x1800204ef  test    eax, eax
0x1800204f1  js      loc_18002068D
0x1800204f7  mov     rcx, [rbp+0D0h+phHash]; hHash
0x1800204fb  lea     r15d, [rsi+1]
0x1800204ff  mov     edx, esi
0x180020501  xor     r9d, r9d; dwFlags
0x180020504  mov     r8d, r15d; cbInput
0x180020507  mov     rdx, [rbp+rdx*8+0D0h+pbInput]; pbInput
0x18002050c  call    cs:__imp_BCryptHashData
0x180020512  mov     ebx, eax
0x180020514  test    eax, eax
0x180020516  js      loc_180020685
0x18002051c  mov     r8d, [rbp+0D0h+cbInput]; cbInput
0x180020520  xor     r9d, r9d; dwFlags
0x180020523  mov     rcx, [rbp+0D0h+phHash]; hHash
0x180020527  mov     rdx, r12; pbInput
0x18002052a  call    cs:__imp_BCryptHashData
0x180020530  mov     ebx, eax
0x180020532  test    eax, eax
0x180020534  js      loc_18002067D
0x18002053a  mov     rdx, [rbp+0D0h+var_C0]; pbInput
0x18002053e  xor     r9d, r9d; dwFlags
0x180020541  mov     rcx, [rbp+0D0h+phHash]; hHash
0x180020545  lea     r8d, [r9+40h]; cbInput
0x180020549  call    cs:__imp_BCryptHashData
0x18002054f  mov     ebx, eax
0x180020551  test    eax, eax
0x180020553  js      loc_180020675
0x180020559  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18002055d  lea     rdx, [rbp+0D0h+pbOutput]; pbOutput
0x180020561  xor     r9d, r9d; dwFlags
0x180020564  lea     r8d, [r9+14h]; cbOutput
0x180020568  call    cs:__imp_BCryptFinishHash
0x18002056e  mov     ebx, eax
0x180020570  test    eax, eax
0x180020572  js      loc_18002066D
0x180020578  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18002057c  call    cs:__imp_BCryptDestroyHash
0x180020582  mov     ebx, eax
0x180020584  xor     eax, eax
0x180020586  mov     [rbp+0D0h+phHash], rax
0x18002058a  test    ebx, ebx
0x18002058c  js      loc_180020663
0x180020592  mov     r9d, [r13+140h]; cbHashObject
0x180020599  lea     rdx, [rbp+0D0h+phHash]; phHash
0x18002059d  mov     rcx, [r13+130h]; hAlgorithm
0x1800205a4  mov     r8, rdi; pbHashObject
0x1800205a7  mov     [rsp+110h+dwFlags], eax; dwFlags
0x1800205ab  mov     [rsp+110h+cbSecret], eax; cbSecret
0x1800205af  mov     [rsp+110h+pbSecret], rax; pbSecret
0x1800205b4  call    cs:__imp_BCryptCreateHash
0x1800205ba  mov     ebx, eax
0x1800205bc  test    eax, eax
0x1800205be  js      loc_18002065B
0x1800205c4  mov     r8d, [rbp+0D0h+cbInput]; cbInput
0x1800205c8  xor     r9d, r9d; dwFlags
0x1800205cb  mov     rcx, [rbp+0D0h+phHash]; hHash
0x1800205cf  mov     rdx, r12; pbInput
0x1800205d2  call    cs:__imp_BCryptHashData
0x1800205d8  mov     ebx, eax
0x1800205da  test    eax, eax
0x1800205dc  js      short loc_180020653
0x1800205de  mov     rcx, [rbp+0D0h+phHash]; hHash
0x1800205e2  lea     rdx, [rbp+0D0h+pbOutput]; pbInput
0x1800205e6  xor     r9d, r9d; dwFlags
0x1800205e9  lea     r8d, [r9+14h]; cbInput
0x1800205ed  call    cs:__imp_BCryptHashData
0x1800205f3  mov     ebx, eax
0x1800205f5  test    eax, eax
0x1800205f7  js      short loc_18002064B
0x1800205f9  mov     rcx, [rbp+0D0h+phHash]; hHash
0x1800205fd  xor     r9d, r9d; dwFlags
0x180020600  shl     esi, 4
0x180020603  mov     edx, esi
0x180020605  add     rdx, [rbp+0D0h+var_B8]; pbOutput
0x180020609  lea     r8d, [r9+10h]; cbOutput
0x18002060d  call    cs:__imp_BCryptFinishHash
0x180020613  mov     ebx, eax
0x180020615  test    eax, eax
0x180020617  js      short loc_180020643
0x180020619  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18002061d  call    cs:__imp_BCryptDestroyHash
0x180020623  mov     [rbp+0D0h+phHash], 0
0x18002062b  mov     ebx, eax
0x18002062d  test    eax, eax
0x18002062f  js      short loc_180020639
0x180020631  mov     esi, r15d
0x180020634  jmp     loc_1800204B0
0x180020639  mov     r9d, 158h
0x18002063f  mov     ecx, eax
0x180020641  jmp     short loc_1800206AB
0x180020643  mov     r9d, 150h
0x180020649  jmp     short loc_18002063F
0x18002064b  mov     r9d, 145h
0x180020651  jmp     short loc_18002063F
0x180020653  mov     r9d, 13Ah
0x180020659  jmp     short loc_18002063F
0x18002065b  mov     r9d, 12Fh
0x180020661  jmp     short loc_18002063F
0x180020663  mov     r9d, 11Dh
0x180020669  mov     ecx, ebx
0x18002066b  jmp     short loc_1800206AB
0x18002066d  mov     r9d, 115h
0x180020673  jmp     short loc_18002063F
0x180020675  mov     r9d, 10Ah
0x18002067b  jmp     short loc_18002063F
0x18002067d  mov     r9d, 0FFh
0x180020683  jmp     short loc_18002063F
0x180020685  mov     r9d, 0F4h
0x18002068b  jmp     short loc_18002063F
0x18002068d  mov     r9d, 0E9h
0x180020693  jmp     short loc_18002063F
0x180020695  xor     ebx, ebx
0x180020697  jmp     short loc_1800206BE
0x180020699  xor     edi, edi
0x18002069b  mov     ebx, 8009002Dh
0x1800206a0  mov     r9d, 0C9h
0x1800206a6  mov     ecx, 8009002Dh
0x1800206ab  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800206b2  lea     rdx, aStatus; "Status"
0x1800206b9  call    DebugTraceError
0x1800206be  mov     rcx, [rbp+0D0h+phHash]; hHash
0x1800206c2  test    rcx, rcx
0x1800206c5  jz      short loc_1800206CD
0x1800206c7  call    cs:__imp_BCryptDestroyHash
0x1800206cd  test    rdi, rdi
0x1800206d0  jz      short loc_1800206EA
0x1800206d2  lea     rcx, [rdi-8]
0x1800206d6  cmp     dword ptr [rcx], 70616548h
0x1800206dc  jnz     short loc_1800206EA
0x1800206de  mov     rax, cs:g_pfnFree
0x1800206e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206ea  mov     eax, ebx
0x1800206ec  mov     rcx, [rbp+0D0h+var_50]
0x1800206f3  xor     rcx, rbp; StackCookie
0x1800206f6  call    __security_check_cookie
0x1800206fb  lea     rsp, [rbp+98h]
0x180020702  pop     r15
0x180020704  pop     r14
0x180020706  pop     r13
0x180020708  pop     r12
0x18002070a  pop     rdi
0x18002070b  pop     rsi
0x18002070c  pop     rbx
0x18002070d  pop     rbp
0x18002070e  retn
```
