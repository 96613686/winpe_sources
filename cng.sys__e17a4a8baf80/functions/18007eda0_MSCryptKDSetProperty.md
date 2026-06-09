# MSCryptKDSetProperty

- ea: `0x18007eda0`
- end: `0x18007f0c1`
- name: `MSCryptKDSetProperty`
- size: `801`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000e090`
- `0x18000ff30`
- `0x180010590`
- `0x18001155c`
- `0x180043fb0`
- `0x1800467e0`
- `0x18006e898`
- `0x18007eda0`
- `0x1800a4232`
- `0x1800a4260`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x18007ef93`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18007f084`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
  void *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  unsigned __int64 v21; // r14
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v27; // [rsp+40h] [rbp-41h] BYREF
  _QWORD Src[8]; // [rsp+50h] [rbp-31h] BYREF

  v5 = a4;
  v27 = 0;
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
  v12 = ValidateKeyDerivationKey(a1, &v27);
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
    v14 = v27;
    if ( *(_DWORD *)(v27 + 48) == 1 )
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
    v18 = (void *)MSCryptAlloc(v5, v17);
    *(_QWORD *)(v14 + 56) = v18;
    if ( !v18 )
    {
      v9 = -1073741801;
      v10 = 1179;
      v11 = 3221225495LL;
      goto LABEL_45;
    }
    memmove(v18, a3, v5);
    *(_DWORD *)(v14 + 64) = v5;
  }
  else if ( !wcscmp_0(a2, L"HkdfSaltAndFinalize") )
  {
    v19 = v27;
    if ( *(_DWORD *)(v27 + 48) == 1 || (v20 = *(_QWORD *)(v27 + 72)) == 0 )
    {
      v10 = 1205;
      goto LABEL_44;
    }
    v21 = *(_QWORD *)(v20 + 48);
    if ( (unsigned int)SymCryptHkdfExtractPrk(
                         v20,
                         *(_QWORD *)(v27 + 24),
                         *(_DWORD *)(v27 + 16),
                         (_DWORD)a3,
                         v5,
                         (__int64)Src,
                         v21) )
      return v9;
    v13 = 1;
    if ( !(unsigned int)SymCryptHkdfPrkExpandKey(v19 + 80, *(_QWORD *)(v19 + 72), Src, v21) )
    {
      if ( *(unsigned int *)(v19 + 16) < v21 )
      {
        MSCryptFree(*(PVOID *)(v19 + 24));
        v23 = MSCryptAlloc(v21, v22);
        *(_QWORD *)(v19 + 24) = v23;
        if ( !v23 )
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
      memmove(*(void **)(v19 + 24), Src, v21);
      *(_DWORD *)(v19 + 16) = v21;
      *(_DWORD *)(v19 + 48) = 1;
    }
  }
  else
  {
    if ( wcscmp_0(a2, L"HkdfPrkAndFinalize") )
    {
      v10 = 1302;
      goto LABEL_17;
    }
    v24 = v27;
    if ( *(_DWORD *)(v27 + 48) == 1 || (v25 = *(_QWORD *)(v27 + 72)) == 0 || a3 || (_DWORD)v5 )
    {
      v10 = 1275;
      goto LABEL_44;
    }
    if ( (unsigned int)SymCryptHkdfPrkExpandKey(v27 + 80, v25, *(_QWORD *)(v27 + 24), *(unsigned int *)(v27 + 16)) )
    {
      v9 = -1073741823;
      v10 = 1290;
      v11 = 3221225473LL;
      goto LABEL_45;
    }
    *(_DWORD *)(v24 + 48) = 1;
  }
  v9 = 0;
  if ( v13 )
    goto LABEL_40;
  return v9;
}

```

## disassembly

```asm
0x18007eda0  mov     [rsp-8+arg_0], rbx
0x18007eda5  push    rbp
0x18007eda6  push    rsi
0x18007eda7  push    rdi
0x18007eda8  push    r12
0x18007edaa  push    r13
0x18007edac  push    r14
0x18007edae  push    r15
0x18007edb0  lea     rbp, [rsp-1Fh]
0x18007edb5  sub     rsp, 0A0h
0x18007edbc  mov     rax, cs:__security_cookie
0x18007edc3  xor     rax, rsp
0x18007edc6  mov     [rbp+4Fh+var_40], rax
0x18007edca  xor     r13d, r13d
0x18007edcd  mov     esi, r9d
0x18007edd0  mov     r15, r8
0x18007edd3  mov     [rbp+4Fh+var_90], r13
0x18007edd7  mov     rdi, rdx
0x18007edda  mov     rbx, rcx
0x18007eddd  xor     edx, edx; Val
0x18007eddf  lea     rcx, [rbp+4Fh+Src]; void *
0x18007ede3  lea     r8d, [r13+40h]; Size
0x18007ede7  call    memset
0x18007edec  test    rbx, rbx
0x18007edef  jnz     short loc_18007EE06
0x18007edf1  mov     ebx, 0C0000008h
0x18007edf6  mov     r9d, 462h
0x18007edfc  mov     ecx, 0C0000008h
0x18007ee01  jmp     loc_18007F084
0x18007ee06  cmp     [rbp+4Fh+arg_20], r13d
0x18007ee0a  jnz     loc_18007F074
0x18007ee10  test    rdi, rdi
0x18007ee13  jz      loc_18007F074
0x18007ee19  lea     rdx, [rbp+4Fh+var_90]
0x18007ee1d  mov     rcx, rbx
0x18007ee20  call    ValidateKeyDerivationKey
0x18007ee25  mov     ebx, eax
0x18007ee27  test    eax, eax
0x18007ee29  jns     short loc_18007EE38
0x18007ee2b  mov     r9d, 472h
0x18007ee31  mov     ecx, eax
0x18007ee33  jmp     loc_18007F084
0x18007ee38  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x18007ee3f  mov     rcx, rdi; Str1
0x18007ee42  mov     r12d, r13d
0x18007ee45  call    wcscmp_0
0x18007ee4a  test    eax, eax
0x18007ee4c  jnz     loc_18007EEEA
0x18007ee52  mov     rbx, [rbp+4Fh+var_90]
0x18007ee56  cmp     dword ptr [rbx+30h], 1
0x18007ee5a  jnz     short loc_18007EE67
0x18007ee5c  mov     r9d, 47Eh
0x18007ee62  jmp     loc_18007F07A
0x18007ee67  cmp     esi, 2
0x18007ee6a  jb      short loc_18007EE7D
0x18007ee6c  mov     ecx, esi
0x18007ee6e  shr     ecx, 1
0x18007ee70  dec     ecx
0x18007ee72  cmp     [r15+rcx*2], r13w
0x18007ee77  jz      short loc_18007EE88
0x18007ee79  test    ecx, ecx
0x18007ee7b  jnz     short loc_18007EE70
0x18007ee7d  mov     r9d, 487h
0x18007ee83  jmp     loc_18007F07A
0x18007ee88  mov     rcx, r15; Str1
0x18007ee8b  call    GetSymCryptMacAlgorithm
0x18007ee90  mov     [rbx+48h], rax
0x18007ee94  test    rax, rax
0x18007ee97  jnz     short loc_18007EEAE
0x18007ee99  mov     r9d, 493h
0x18007ee9f  mov     ebx, 0C00000BBh
0x18007eea4  mov     ecx, 0C00000BBh
0x18007eea9  jmp     loc_18007F084
0x18007eeae  mov     rcx, rsi
0x18007eeb1  call    MSCryptAlloc
0x18007eeb6  mov     [rbx+38h], rax
0x18007eeba  test    rax, rax
0x18007eebd  jnz     short loc_18007EED4
0x18007eebf  mov     ebx, 0C0000017h
0x18007eec4  mov     r9d, 49Bh
0x18007eeca  mov     ecx, 0C0000017h
0x18007eecf  jmp     loc_18007F084
0x18007eed4  mov     r8, rsi; Size
0x18007eed7  mov     rdx, r15; Src
0x18007eeda  mov     rcx, rax; void *
0x18007eedd  call    memmove
0x18007eee2  mov     [rbx+40h], esi
0x18007eee5  jmp     loc_18007F037
0x18007eeea  lea     rdx, aHkdfsaltandfin; "HkdfSaltAndFinalize"
0x18007eef1  mov     rcx, rdi; Str1
0x18007eef4  call    wcscmp_0
0x18007eef9  test    eax, eax
0x18007eefb  jnz     loc_18007EFDA
0x18007ef01  mov     rdi, [rbp+4Fh+var_90]
0x18007ef05  cmp     dword ptr [rdi+30h], 1
0x18007ef09  jz      loc_18007EFCF
0x18007ef0f  mov     rcx, [rdi+48h]
0x18007ef13  test    rcx, rcx
0x18007ef16  jz      loc_18007EFCF
0x18007ef1c  mov     r14, [rcx+30h]
0x18007ef20  lea     rdx, [rbp+4Fh+Src]
0x18007ef24  mov     r8d, [rdi+10h]
0x18007ef28  mov     r9, r15
0x18007ef2b  mov     [rsp+0D0h+var_A0], r14
0x18007ef30  mov     [rsp+0D0h+var_A8], rdx
0x18007ef35  mov     rdx, [rdi+18h]
0x18007ef39  mov     [rsp+0D0h+var_B0], rsi
0x18007ef3e  call    SymCryptHkdfExtractPrk
0x18007ef43  test    eax, eax
0x18007ef45  jnz     loc_18007F097
0x18007ef4b  mov     rdx, [rdi+48h]
0x18007ef4f  lea     rcx, [rdi+50h]
0x18007ef53  mov     r9, r14
0x18007ef56  lea     r8, [rbp+4Fh+Src]
0x18007ef5a  lea     r12d, [rax+1]
0x18007ef5e  call    SymCryptHkdfPrkExpandKey
0x18007ef63  test    eax, eax
0x18007ef65  jnz     loc_18007F037
0x18007ef6b  mov     eax, [rdi+10h]
0x18007ef6e  cmp     rax, r14
0x18007ef71  jnb     short loc_18007EFB5
0x18007ef73  mov     rcx, [rdi+18h]; P
0x18007ef77  call    MSCryptFree
0x18007ef7c  mov     rcx, r14
0x18007ef7f  call    MSCryptAlloc
0x18007ef84  mov     [rdi+18h], rax
0x18007ef88  test    rax, rax
0x18007ef8b  jnz     short loc_18007EFB5
0x18007ef8d  mov     r9d, 4D9h
0x18007ef93  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ef9a  lea     rdx, aStatus; "Status"
0x18007efa1  mov     ecx, 0C0000017h
0x18007efa6  mov     ebx, 0C0000017h
0x18007efab  call    DebugTraceError
0x18007efb0  jmp     loc_18007F03F
0x18007efb5  mov     rcx, [rdi+18h]; void *
0x18007efb9  lea     rdx, [rbp+4Fh+Src]; Src
0x18007efbd  mov     r8, r14; Size
0x18007efc0  call    memmove
0x18007efc5  mov     [rdi+10h], r14d
0x18007efc9  mov     [rdi+30h], r12d
0x18007efcd  jmp     short loc_18007F037
0x18007efcf  mov     r9d, 4B5h
0x18007efd5  jmp     loc_18007F07A
0x18007efda  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x18007efe1  mov     rcx, rdi; Str1
0x18007efe4  call    wcscmp_0
0x18007efe9  test    eax, eax
0x18007efeb  jnz     short loc_18007F069
0x18007efed  mov     rbx, [rbp+4Fh+var_90]
0x18007eff1  cmp     dword ptr [rbx+30h], 1
0x18007eff5  jz      short loc_18007F061
0x18007eff7  mov     rdx, [rbx+48h]
0x18007effb  test    rdx, rdx
0x18007effe  jz      short loc_18007F061
0x18007f000  test    r15, r15
0x18007f003  jnz     short loc_18007F061
0x18007f005  test    esi, esi
0x18007f007  jnz     short loc_18007F061
0x18007f009  mov     r9d, [rbx+10h]
0x18007f00d  lea     rcx, [rbx+50h]
0x18007f011  mov     r8, [rbx+18h]
0x18007f015  call    SymCryptHkdfPrkExpandKey
0x18007f01a  test    eax, eax
0x18007f01c  jz      short loc_18007F030
0x18007f01e  mov     ebx, 0C0000001h
0x18007f023  mov     r9d, 50Ah
0x18007f029  mov     ecx, 0C0000001h
0x18007f02e  jmp     short loc_18007F084
0x18007f030  mov     dword ptr [rbx+30h], 1
0x18007f037  mov     ebx, r13d
0x18007f03a  test    r12d, r12d
0x18007f03d  jz      short loc_18007F097
0x18007f03f  mov     [rbp+4Fh+Src], r13
0x18007f043  mov     [rbp+4Fh+var_78], r13
0x18007f047  mov     [rbp+4Fh+var_70], r13
0x18007f04b  mov     [rbp+4Fh+var_68], r13
0x18007f04f  mov     [rbp+4Fh+var_60], r13
0x18007f053  mov     [rbp+4Fh+var_58], r13
0x18007f057  mov     [rbp+4Fh+var_50], r13
0x18007f05b  mov     [rbp+4Fh+var_48], r13
0x18007f05f  jmp     short loc_18007F097
0x18007f061  mov     r9d, 4FBh
0x18007f067  jmp     short loc_18007F07A
0x18007f069  mov     r9d, 516h
0x18007f06f  jmp     loc_18007EE9F
0x18007f074  mov     r9d, 46Ah
0x18007f07a  mov     ebx, 0C000000Dh
0x18007f07f  mov     ecx, 0C000000Dh
0x18007f084  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f08b  lea     rdx, aStatus; "Status"
0x18007f092  call    DebugTraceError
0x18007f097  mov     eax, ebx
0x18007f099  mov     rcx, [rbp+4Fh+var_40]
0x18007f09d  xor     rcx, rsp; StackCookie
0x18007f0a0  call    __security_check_cookie
0x18007f0a5  mov     rbx, [rsp+0D0h+arg_0]
0x18007f0ad  add     rsp, 0A0h
0x18007f0b4  pop     r15
0x18007f0b6  pop     r14
0x18007f0b8  pop     r13
0x18007f0ba  pop     r12
0x18007f0bc  pop     rdi
0x18007f0bd  pop     rsi
0x18007f0be  pop     rbp
0x18007f0bf  retn
```
