# MSCryptKDSetProperty

- ea: `0x180075610`
- end: `0x180075931`
- name: `MSCryptKDSetProperty`
- size: `801`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180005e10`
- `0x180006470`
- `0x18000743c`
- `0x18003aa20`
- `0x18003d320`
- `0x180065078`
- `0x180075610`
- `0x18009f616`
- `0x18009f650`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x180075803`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800758f4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDSetProperty(__int64 a1, const wchar_t *a2, wchar_t *a3, unsigned int a4, int a5)
{
  size_t v5; // rsi
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  int v13; // r12d
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 SymCryptMacAlgorithm; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  void *v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rcx
  unsigned __int64 v23; // r14
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v31; // [rsp+40h] [rbp-41h] BYREF
  _QWORD Src[8]; // [rsp+50h] [rbp-31h] BYREF

  v5 = a4;
  v31 = 0;
  memset(Src, 0, sizeof(Src));
  if ( !a1 )
  {
    v9 = -1073741816;
    v10 = 1122;
    v11 = 3221225480LL;
LABEL_45:
    DebugTraceError(
      v11,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v10);
    return v9;
  }
  if ( a5 || !a2 )
  {
    v10 = 1130;
    goto LABEL_44;
  }
  v12 = ValidateKeyDerivationKey(a1, &v31);
  v9 = v12;
  if ( v12 < 0 )
  {
    v10 = 1138;
    v11 = (unsigned int)v12;
    goto LABEL_45;
  }
  v13 = 0;
  if ( !wcscmp_0(a2, L"HkdfHashAlgorithm") )
  {
    v14 = v31;
    if ( *(_DWORD *)(v31 + 48) == 1 )
    {
      v10 = 1150;
LABEL_44:
      v9 = -1073741811;
      v11 = 3221225485LL;
      goto LABEL_45;
    }
    if ( (unsigned int)v5 < 2 )
    {
LABEL_14:
      v10 = 1159;
      goto LABEL_44;
    }
    LODWORD(v15) = (unsigned int)v5 >> 1;
    while ( 1 )
    {
      v15 = (unsigned int)(v15 - 1);
      if ( !a3[v15] )
        break;
      if ( !(_DWORD)v15 )
        goto LABEL_14;
    }
    SymCryptMacAlgorithm = GetSymCryptMacAlgorithm(a3);
    *(_QWORD *)(v14 + 72) = SymCryptMacAlgorithm;
    if ( !SymCryptMacAlgorithm )
    {
      v10 = 1171;
LABEL_17:
      v9 = -1073741637;
      v11 = 3221225659LL;
      goto LABEL_45;
    }
    v20 = (void *)MSCryptAlloc(v5, v17, v18, v19);
    *(_QWORD *)(v14 + 56) = v20;
    if ( !v20 )
    {
      v9 = -1073741801;
      v10 = 1179;
      v11 = 3221225495LL;
      goto LABEL_45;
    }
    memmove(v20, a3, v5);
    *(_DWORD *)(v14 + 64) = v5;
  }
  else if ( !wcscmp_0(a2, L"HkdfSaltAndFinalize") )
  {
    v21 = v31;
    if ( *(_DWORD *)(v31 + 48) == 1 || (v22 = *(_QWORD *)(v31 + 72)) == 0 )
    {
      v10 = 1205;
      goto LABEL_44;
    }
    v23 = *(_QWORD *)(v22 + 48);
    if ( (unsigned int)SymCryptHkdfExtractPrk(
                         v22,
                         *(_QWORD *)(v31 + 24),
                         *(_DWORD *)(v31 + 16),
                         (_DWORD)a3,
                         v5,
                         (__int64)Src,
                         v23) )
      return v9;
    v13 = 1;
    if ( !(unsigned int)SymCryptHkdfPrkExpandKey(v21 + 80, *(_QWORD *)(v21 + 72), Src, v23) )
    {
      if ( *(unsigned int *)(v21 + 16) < v23 )
      {
        MSCryptFree(*(PVOID *)(v21 + 24));
        v27 = MSCryptAlloc(v23, v24, v25, v26);
        *(_QWORD *)(v21 + 24) = v27;
        if ( !v27 )
        {
          v9 = -1073741801;
          DebugTraceError(
            3221225495LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            1241);
LABEL_40:
          memset(Src, 0, sizeof(Src));
          return v9;
        }
      }
      memmove(*(void **)(v21 + 24), Src, v23);
      *(_DWORD *)(v21 + 16) = v23;
      *(_DWORD *)(v21 + 48) = 1;
    }
  }
  else
  {
    if ( wcscmp_0(a2, L"HkdfPrkAndFinalize") )
    {
      v10 = 1302;
      goto LABEL_17;
    }
    v28 = v31;
    if ( *(_DWORD *)(v31 + 48) == 1 || (v29 = *(_QWORD *)(v31 + 72)) == 0 || a3 || (_DWORD)v5 )
    {
      v10 = 1275;
      goto LABEL_44;
    }
    if ( (unsigned int)SymCryptHkdfPrkExpandKey(v31 + 80, v29, *(_QWORD *)(v31 + 24), *(unsigned int *)(v31 + 16)) )
    {
      v9 = -1073741823;
      v10 = 1290;
      v11 = 3221225473LL;
      goto LABEL_45;
    }
    *(_DWORD *)(v28 + 48) = 1;
  }
  v9 = 0;
  if ( v13 )
    goto LABEL_40;
  return v9;
}

```

## disassembly

```asm
0x180075610  mov     [rsp-8+arg_0], rbx
0x180075615  push    rbp
0x180075616  push    rsi
0x180075617  push    rdi
0x180075618  push    r12
0x18007561a  push    r13
0x18007561c  push    r14
0x18007561e  push    r15
0x180075620  lea     rbp, [rsp-1Fh]
0x180075625  sub     rsp, 0A0h
0x18007562c  mov     rax, cs:__security_cookie
0x180075633  xor     rax, rsp
0x180075636  mov     [rbp+4Fh+var_40], rax
0x18007563a  xor     r13d, r13d
0x18007563d  mov     esi, r9d
0x180075640  mov     r15, r8
0x180075643  mov     [rbp+4Fh+var_90], r13
0x180075647  mov     rdi, rdx
0x18007564a  mov     rbx, rcx
0x18007564d  xor     edx, edx; Val
0x18007564f  lea     rcx, [rbp+4Fh+Src]; void *
0x180075653  lea     r8d, [r13+40h]; Size
0x180075657  call    memset
0x18007565c  test    rbx, rbx
0x18007565f  jnz     short loc_180075676
0x180075661  mov     ebx, 0C0000008h
0x180075666  mov     r9d, 462h
0x18007566c  mov     ecx, 0C0000008h
0x180075671  jmp     loc_1800758F4
0x180075676  cmp     [rbp+4Fh+arg_20], r13d
0x18007567a  jnz     loc_1800758E4
0x180075680  test    rdi, rdi
0x180075683  jz      loc_1800758E4
0x180075689  lea     rdx, [rbp+4Fh+var_90]
0x18007568d  mov     rcx, rbx
0x180075690  call    ValidateKeyDerivationKey
0x180075695  mov     ebx, eax
0x180075697  test    eax, eax
0x180075699  jns     short loc_1800756A8
0x18007569b  mov     r9d, 472h
0x1800756a1  mov     ecx, eax
0x1800756a3  jmp     loc_1800758F4
0x1800756a8  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x1800756af  mov     rcx, rdi; Str1
0x1800756b2  mov     r12d, r13d
0x1800756b5  call    wcscmp_0
0x1800756ba  test    eax, eax
0x1800756bc  jnz     loc_18007575A
0x1800756c2  mov     rbx, [rbp+4Fh+var_90]
0x1800756c6  cmp     dword ptr [rbx+30h], 1
0x1800756ca  jnz     short loc_1800756D7
0x1800756cc  mov     r9d, 47Eh
0x1800756d2  jmp     loc_1800758EA
0x1800756d7  cmp     esi, 2
0x1800756da  jb      short loc_1800756ED
0x1800756dc  mov     ecx, esi
0x1800756de  shr     ecx, 1
0x1800756e0  dec     ecx
0x1800756e2  cmp     [r15+rcx*2], r13w
0x1800756e7  jz      short loc_1800756F8
0x1800756e9  test    ecx, ecx
0x1800756eb  jnz     short loc_1800756E0
0x1800756ed  mov     r9d, 487h
0x1800756f3  jmp     loc_1800758EA
0x1800756f8  mov     rcx, r15; Str1
0x1800756fb  call    GetSymCryptMacAlgorithm
0x180075700  mov     [rbx+48h], rax
0x180075704  test    rax, rax
0x180075707  jnz     short loc_18007571E
0x180075709  mov     r9d, 493h
0x18007570f  mov     ebx, 0C00000BBh
0x180075714  mov     ecx, 0C00000BBh
0x180075719  jmp     loc_1800758F4
0x18007571e  mov     rcx, rsi
0x180075721  call    MSCryptAlloc
0x180075726  mov     [rbx+38h], rax
0x18007572a  test    rax, rax
0x18007572d  jnz     short loc_180075744
0x18007572f  mov     ebx, 0C0000017h
0x180075734  mov     r9d, 49Bh
0x18007573a  mov     ecx, 0C0000017h
0x18007573f  jmp     loc_1800758F4
0x180075744  mov     r8, rsi; Size
0x180075747  mov     rdx, r15; Src
0x18007574a  mov     rcx, rax; void *
0x18007574d  call    memmove
0x180075752  mov     [rbx+40h], esi
0x180075755  jmp     loc_1800758A7
0x18007575a  lea     rdx, aHkdfsaltandfin; "HkdfSaltAndFinalize"
0x180075761  mov     rcx, rdi; Str1
0x180075764  call    wcscmp_0
0x180075769  test    eax, eax
0x18007576b  jnz     loc_18007584A
0x180075771  mov     rdi, [rbp+4Fh+var_90]
0x180075775  cmp     dword ptr [rdi+30h], 1
0x180075779  jz      loc_18007583F
0x18007577f  mov     rcx, [rdi+48h]
0x180075783  test    rcx, rcx
0x180075786  jz      loc_18007583F
0x18007578c  mov     r14, [rcx+30h]
0x180075790  lea     rdx, [rbp+4Fh+Src]
0x180075794  mov     r8d, [rdi+10h]
0x180075798  mov     r9, r15
0x18007579b  mov     [rsp+0D0h+var_A0], r14
0x1800757a0  mov     [rsp+0D0h+var_A8], rdx
0x1800757a5  mov     rdx, [rdi+18h]
0x1800757a9  mov     [rsp+0D0h+var_B0], rsi
0x1800757ae  call    SymCryptHkdfExtractPrk
0x1800757b3  test    eax, eax
0x1800757b5  jnz     loc_180075907
0x1800757bb  mov     rdx, [rdi+48h]
0x1800757bf  lea     rcx, [rdi+50h]
0x1800757c3  mov     r9, r14
0x1800757c6  lea     r8, [rbp+4Fh+Src]
0x1800757ca  lea     r12d, [rax+1]
0x1800757ce  call    SymCryptHkdfPrkExpandKey
0x1800757d3  test    eax, eax
0x1800757d5  jnz     loc_1800758A7
0x1800757db  mov     eax, [rdi+10h]
0x1800757de  cmp     rax, r14
0x1800757e1  jnb     short loc_180075825
0x1800757e3  mov     rcx, [rdi+18h]; P
0x1800757e7  call    MSCryptFree
0x1800757ec  mov     rcx, r14
0x1800757ef  call    MSCryptAlloc
0x1800757f4  mov     [rdi+18h], rax
0x1800757f8  test    rax, rax
0x1800757fb  jnz     short loc_180075825
0x1800757fd  mov     r9d, 4D9h
0x180075803  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007580a  lea     rdx, aStatus; "Status"
0x180075811  mov     ecx, 0C0000017h
0x180075816  mov     ebx, 0C0000017h
0x18007581b  call    DebugTraceError
0x180075820  jmp     loc_1800758AF
0x180075825  mov     rcx, [rdi+18h]; void *
0x180075829  lea     rdx, [rbp+4Fh+Src]; Src
0x18007582d  mov     r8, r14; Size
0x180075830  call    memmove
0x180075835  mov     [rdi+10h], r14d
0x180075839  mov     [rdi+30h], r12d
0x18007583d  jmp     short loc_1800758A7
0x18007583f  mov     r9d, 4B5h
0x180075845  jmp     loc_1800758EA
0x18007584a  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x180075851  mov     rcx, rdi; Str1
0x180075854  call    wcscmp_0
0x180075859  test    eax, eax
0x18007585b  jnz     short loc_1800758D9
0x18007585d  mov     rbx, [rbp+4Fh+var_90]
0x180075861  cmp     dword ptr [rbx+30h], 1
0x180075865  jz      short loc_1800758D1
0x180075867  mov     rdx, [rbx+48h]
0x18007586b  test    rdx, rdx
0x18007586e  jz      short loc_1800758D1
0x180075870  test    r15, r15
0x180075873  jnz     short loc_1800758D1
0x180075875  test    esi, esi
0x180075877  jnz     short loc_1800758D1
0x180075879  mov     r9d, [rbx+10h]
0x18007587d  lea     rcx, [rbx+50h]
0x180075881  mov     r8, [rbx+18h]
0x180075885  call    SymCryptHkdfPrkExpandKey
0x18007588a  test    eax, eax
0x18007588c  jz      short loc_1800758A0
0x18007588e  mov     ebx, 0C0000001h
0x180075893  mov     r9d, 50Ah
0x180075899  mov     ecx, 0C0000001h
0x18007589e  jmp     short loc_1800758F4
0x1800758a0  mov     dword ptr [rbx+30h], 1
0x1800758a7  mov     ebx, r13d
0x1800758aa  test    r12d, r12d
0x1800758ad  jz      short loc_180075907
0x1800758af  mov     [rbp+4Fh+Src], r13
0x1800758b3  mov     [rbp+4Fh+var_78], r13
0x1800758b7  mov     [rbp+4Fh+var_70], r13
0x1800758bb  mov     [rbp+4Fh+var_68], r13
0x1800758bf  mov     [rbp+4Fh+var_60], r13
0x1800758c3  mov     [rbp+4Fh+var_58], r13
0x1800758c7  mov     [rbp+4Fh+var_50], r13
0x1800758cb  mov     [rbp+4Fh+var_48], r13
0x1800758cf  jmp     short loc_180075907
0x1800758d1  mov     r9d, 4FBh
0x1800758d7  jmp     short loc_1800758EA
0x1800758d9  mov     r9d, 516h
0x1800758df  jmp     loc_18007570F
0x1800758e4  mov     r9d, 46Ah
0x1800758ea  mov     ebx, 0C000000Dh
0x1800758ef  mov     ecx, 0C000000Dh
0x1800758f4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800758fb  lea     rdx, aStatus; "Status"
0x180075902  call    DebugTraceError
0x180075907  mov     eax, ebx
0x180075909  mov     rcx, [rbp+4Fh+var_40]
0x18007590d  xor     rcx, rsp; StackCookie
0x180075910  call    __security_check_cookie
0x180075915  mov     rbx, [rsp+0D0h+arg_0]
0x18007591d  add     rsp, 0A0h
0x180075924  pop     r15
0x180075926  pop     r14
0x180075928  pop     r13
0x18007592a  pop     r12
0x18007592c  pop     rdi
0x18007592d  pop     rsi
0x18007592e  pop     rbp
0x18007592f  retn
```
