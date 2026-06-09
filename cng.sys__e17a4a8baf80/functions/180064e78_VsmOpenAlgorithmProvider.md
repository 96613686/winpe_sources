# VsmOpenAlgorithmProvider

- ea: `0x180064e78`
- end: `0x180065239`
- name: `VsmOpenAlgorithmProvider`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004eaa0`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180064acc`
- `0x180064e78`
- `0x18007362c`
- `0x1800a4300`
- `0x1800a4380`
- `0x1800a4890`

## import_xrefs

- `ntoskrnl!wcsncpy_s` at `0x180064fb2`
- `ntoskrnl!wcsncpy_s` at `0x180064fb2`

## string_xrefs

- `0x18006519d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180065208`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall VsmOpenAlgorithmProvider(_QWORD *a1, const wchar_t *a2, const void *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned int i; // ecx
  __int64 v10; // r15
  wchar_t *v11; // rax
  signed __int64 v12; // r9
  int v13; // r8d
  __int64 v14; // rdx
  int v15; // esi
  char *v16; // rax
  char *v17; // rdi
  _OWORD *v18; // r14
  int Interface; // eax
  __int64 v20; // r9
  __int64 v21; // rax
  _OWORD *v22; // rcx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  _QWORD *v30; // r14
  __int64 v31; // rcx
  wchar_t *v32; // rdx
  __int64 (__fastcall *v34)(char *, const wchar_t *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v36)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall *v37)(_QWORD, wchar_t *, __int64 *, _QWORD, _DWORD); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[448]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+250h] [rbp+150h] BYREF

  v41 = 4;
  v34 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  if ( !a3 || !memcmp(a3, L"Microsoft Primitive Provider", 0x3Au) )
  {
    for ( i = 0; i < 0x35; ++i )
    {
      v10 = 4LL * i;
      v11 = (&AlgorithmClassPropertyTable)[v10];
      v12 = (char *)a2 - (char *)v11;
      do
      {
        v13 = *(wchar_t *)((char *)v11 + v12);
        v14 = (unsigned int)*v11 - v13;
        if ( (_DWORD)v14 )
          break;
        ++v11;
      }
      while ( v13 );
      if ( !(_DWORD)v14 )
      {
        v15 = *((_DWORD *)&AlgorithmClassPropertyTable + 2 * v10 + 2);
        if ( (unsigned int)(v15 - 1) > 7 )
        {
          v7 = 1677;
          goto LABEL_41;
        }
        v16 = (char *)MSCryptAlloc(968, v14);
        v17 = v16;
        if ( !v16 )
        {
          v6 = -1073741801;
          v7 = 1691;
          v8 = 3221225495LL;
          goto LABEL_42;
        }
        memset(v16, 0, 0x3C8u);
        *(_DWORD *)v17 = 968;
        *((_DWORD *)v17 + 1) = 1431655761;
        *((_DWORD *)v17 + 4) = 1;
        *((_DWORD *)v17 + 9) = v15;
        wcsncpy_s((wchar_t *)v17 + 222, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
        v18 = v17 + 48;
        *((_DWORD *)v17 + 8) = a4 & 1;
        Interface = VsmLoadInterface(*((unsigned int *)v17 + 9), a2, a4, v17 + 48);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1722;
          goto LABEL_35;
        }
        v21 = 3;
        v22 = v39;
        do
        {
          v23 = v18[1];
          *v22 = *v18;
          v24 = v18[2];
          v22[1] = v23;
          v25 = v18[3];
          v22[2] = v24;
          v26 = v18[4];
          v22[3] = v25;
          v27 = v18[5];
          v22[4] = v26;
          v28 = v18[6];
          v22[5] = v27;
          v29 = v18[7];
          v18 += 8;
          v22[6] = v28;
          v22[7] = v29;
          v22 += 8;
          --v21;
        }
        while ( v21 );
        *(_QWORD *)v22 = *(_QWORD *)v18;
        Interface = ValidateFunctionTable(
                      v15,
                      (unsigned int)v39,
                      (unsigned int)&v34,
                      (unsigned int)&v38,
                      (__int64)&v37,
                      (__int64)&v36);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1731;
          goto LABEL_35;
        }
        v30 = v17 + 24;
        v6 = v34(v17 + 24, a2, a4);
        if ( v6 == -1073700863 )
        {
          if ( v15 == 2 )
          {
            if ( (a4 & 0x28) == 8 )
            {
              v34(v17 + 24, a2, a4 & 0xFFFFFFF7);
              *((_DWORD *)v17 + 2) |= 8u;
            }
LABEL_26:
            if ( !v36 )
            {
              v6 = -1073741595;
              v31 = 3221225701LL;
              v20 = 1769;
LABEL_36:
              DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
              MSCryptFree(v17);
              return v6;
            }
            Interface = v36(*v30, L"HashBlockLength", v17 + 12, 4, &v35, 0);
            v6 = Interface;
            if ( Interface < 0 )
            {
              v20 = 1781;
LABEL_35:
              v31 = (unsigned int)Interface;
              goto LABEL_36;
            }
LABEL_37:
            v32 = (&AlgorithmClassPropertyTable)[v10 + 1];
            if ( v32 )
              v37(*v30, v32, &qword_1800AEFB8[v10], *((unsigned int *)&AlgorithmClassPropertyTable + 2 * v10 + 7), 0);
            *a1 = v17;
            return v6;
          }
        }
        else if ( v15 == 2 )
        {
          goto LABEL_26;
        }
        if ( v15 == 3 )
        {
          if ( !v36 )
          {
            v6 = -1073741595;
            v31 = 3221225701LL;
            v20 = 1790;
            goto LABEL_36;
          }
          Interface = v36(*v30, L"PaddingSchemes", v17 + 440, v41, (int *)&v41, 0);
          v6 = Interface;
          if ( Interface < 0 )
          {
            v20 = 1802;
            goto LABEL_35;
          }
        }
        goto LABEL_37;
      }
    }
    v7 = 1668;
LABEL_41:
    v8 = 3221225480LL;
    v6 = -1073741816;
  }
  else
  {
    v6 = -1073741811;
    v7 = 1660;
    v8 = 3221225485LL;
  }
LABEL_42:
  DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v7);
  return v6;
}

```

## disassembly

```asm
0x180064e78  mov     [rsp-8+arg_8], rbx
0x180064e7d  mov     [rsp-8+arg_0], rcx
0x180064e82  push    rbp
0x180064e83  push    rsi
0x180064e84  push    rdi
0x180064e85  push    r12
0x180064e87  push    r13
0x180064e89  push    r14
0x180064e8b  push    r15
0x180064e8d  lea     rbp, [rsp-100h]
0x180064e95  sub     rsp, 200h
0x180064e9c  xor     ebx, ebx
0x180064e9e  mov     [rbp+130h+arg_10], 4
0x180064ea8  mov     [rsp+230h+var_1F0], rbx
0x180064ead  mov     r12d, r9d
0x180064eb0  mov     [rsp+230h+var_1D0], rbx
0x180064eb5  mov     rax, r8
0x180064eb8  mov     [rsp+230h+var_1D8], rbx
0x180064ebd  mov     r13, rdx
0x180064ec0  mov     [rsp+230h+var_1E0], rbx
0x180064ec5  mov     [rsp+230h+var_1E8], ebx
0x180064ec9  test    r8, r8
0x180064ecc  jz      short loc_180064EFA
0x180064ece  lea     r8d, [rbx+3Ah]; Size
0x180064ed2  mov     rcx, rax; Buf1
0x180064ed5  lea     rdx, pszProvider; "Microsoft Primitive Provider"
0x180064edc  call    memcmp
0x180064ee1  test    eax, eax
0x180064ee3  jz      short loc_180064EFA
0x180064ee5  mov     ebx, 0C000000Dh
0x180064eea  mov     r9d, 67Ch
0x180064ef0  mov     ecx, 0C000000Dh
0x180064ef5  jmp     loc_180065208
0x180064efa  mov     ecx, ebx
0x180064efc  lea     r10, AlgorithmClassPropertyTable
0x180064f03  cmp     ecx, 35h ; '5'
0x180064f06  jnb     loc_1800651F8
0x180064f0c  mov     r15d, ecx
0x180064f0f  mov     r9, r13
0x180064f12  shl     r15, 5
0x180064f16  mov     rax, [r15+r10]
0x180064f1a  sub     r9, rax
0x180064f1d  movzx   edx, word ptr [rax]
0x180064f20  movzx   r8d, word ptr [rax+r9]
0x180064f25  sub     edx, r8d
0x180064f28  jnz     short loc_180064F33
0x180064f2a  add     rax, 2
0x180064f2e  test    r8d, r8d
0x180064f31  jnz     short loc_180064F1D
0x180064f33  test    edx, edx
0x180064f35  jz      short loc_180064F3B
0x180064f37  inc     ecx
0x180064f39  jmp     short loc_180064F03
0x180064f3b  mov     esi, [r15+r10+8]
0x180064f40  lea     eax, [rsi-1]
0x180064f43  cmp     eax, 7
0x180064f46  jbe     short loc_180064F53
0x180064f48  mov     r9d, 68Dh
0x180064f4e  jmp     loc_1800651FE
0x180064f53  mov     r14d, 3C8h
0x180064f59  mov     ecx, r14d
0x180064f5c  call    MSCryptAlloc
0x180064f61  mov     rdi, rax
0x180064f64  test    rax, rax
0x180064f67  jnz     short loc_180064F7E
0x180064f69  mov     ebx, 0C0000017h
0x180064f6e  mov     r9d, 69Bh
0x180064f74  mov     ecx, 0C0000017h
0x180064f79  jmp     loc_180065208
0x180064f7e  mov     r8, r14; Size
0x180064f81  xor     edx, edx; Val
0x180064f83  mov     rcx, rdi; void *
0x180064f86  call    memset
0x180064f8b  lea     rcx, [rdi+1BCh]; Dst
0x180064f92  mov     [rdi], r14d
0x180064f95  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180064f99  mov     dword ptr [rdi+4], 55555551h
0x180064fa0  mov     r8, r13; Src
0x180064fa3  mov     dword ptr [rdi+10h], 1
0x180064faa  mov     edx, 104h; SizeInWords
0x180064faf  mov     [rdi+24h], esi
0x180064fb2  call    cs:__imp_wcsncpy_s
0x180064fb9  nop     dword ptr [rax+rax+00h]
0x180064fbe  mov     eax, r12d
0x180064fc1  lea     r14, [rdi+30h]
0x180064fc5  and     eax, 1
0x180064fc8  mov     r9, r14
0x180064fcb  mov     [rdi+20h], eax
0x180064fce  mov     r8d, r12d
0x180064fd1  mov     ecx, [rdi+24h]
0x180064fd4  mov     rdx, r13
0x180064fd7  call    VsmLoadInterface
0x180064fdc  mov     ebx, eax
0x180064fde  test    eax, eax
0x180064fe0  jns     short loc_180064FED
0x180064fe2  mov     r9d, 6BAh
0x180064fe8  jmp     loc_18006519B
0x180064fed  mov     eax, 3
0x180064ff2  lea     rcx, [rsp+230h+var_1C0]
0x180064ff7  lea     edx, [rax+7Dh]
0x180064ffa  movups  xmm0, xmmword ptr [r14]
0x180064ffe  movups  xmm1, xmmword ptr [r14+10h]
0x180065003  movups  xmmword ptr [rcx], xmm0
0x180065006  movups  xmm0, xmmword ptr [r14+20h]
0x18006500b  movups  xmmword ptr [rcx+10h], xmm1
0x18006500f  movups  xmm1, xmmword ptr [r14+30h]
0x180065014  movups  xmmword ptr [rcx+20h], xmm0
0x180065018  movups  xmm0, xmmword ptr [r14+40h]
0x18006501d  movups  xmmword ptr [rcx+30h], xmm1
0x180065021  movups  xmm1, xmmword ptr [r14+50h]
0x180065026  movups  xmmword ptr [rcx+40h], xmm0
0x18006502a  movups  xmm0, xmmword ptr [r14+60h]
0x18006502f  movups  xmmword ptr [rcx+50h], xmm1
0x180065033  movups  xmm1, xmmword ptr [r14+70h]
0x180065038  add     r14, rdx
0x18006503b  movups  xmmword ptr [rcx+60h], xmm0
0x18006503f  movups  xmmword ptr [rcx+70h], xmm1
0x180065043  add     rcx, rdx
0x180065046  sub     rax, 1
0x18006504a  jnz     short loc_180064FFA
0x18006504c  mov     rax, [r14]
0x18006504f  lea     r9, [rsp+230h+var_1D0]
0x180065054  mov     [rcx], rax
0x180065057  lea     r8, [rsp+230h+var_1F0]
0x18006505c  lea     rax, [rsp+230h+var_1E0]
0x180065061  mov     ecx, esi
0x180065063  mov     [rsp+230h+var_208], rax
0x180065068  lea     rdx, [rsp+230h+var_1C0]
0x18006506d  lea     rax, [rsp+230h+var_1D8]
0x180065072  mov     [rsp+230h+var_210], rax
0x180065077  call    ValidateFunctionTable
0x18006507c  mov     ebx, eax
0x18006507e  test    eax, eax
0x180065080  jns     short loc_18006508D
0x180065082  mov     r9d, 6C3h
0x180065088  jmp     loc_18006519B
0x18006508d  mov     rax, [rsp+230h+var_1F0]
0x180065092  lea     r14, [rdi+18h]
0x180065096  mov     rcx, r14
0x180065099  mov     r8d, r12d
0x18006509c  mov     rdx, r13
0x18006509f  call    _guard_dispatch_icall
0x1800650a4  mov     ebx, eax
0x1800650a6  cmp     eax, 0C000A001h
0x1800650ab  jnz     short loc_1800650DC
0x1800650ad  cmp     esi, 2
0x1800650b0  jnz     loc_18006513D
0x1800650b6  mov     eax, r12d
0x1800650b9  and     al, 28h
0x1800650bb  cmp     al, 8
0x1800650bd  jnz     short loc_1800650E1
0x1800650bf  mov     rax, [rsp+230h+var_1F0]
0x1800650c4  and     r12d, 0FFFFFFF7h
0x1800650c8  mov     r8d, r12d
0x1800650cb  mov     rdx, r13
0x1800650ce  mov     rcx, r14
0x1800650d1  call    _guard_dispatch_icall
0x1800650d6  or      dword ptr [rdi+8], 8
0x1800650da  jmp     short loc_1800650E1
0x1800650dc  cmp     esi, 2
0x1800650df  jnz     short loc_18006513D
0x1800650e1  mov     rax, [rsp+230h+var_1E0]
0x1800650e6  test    rax, rax
0x1800650e9  jnz     short loc_180065100
0x1800650eb  mov     ebx, 0C00000E5h
0x1800650f0  mov     ecx, 0C00000E5h
0x1800650f5  mov     r9d, 6E9h
0x1800650fb  jmp     loc_18006519D
0x180065100  lea     rcx, [rsp+230h+var_1E8]
0x180065105  mov     dword ptr [rsp+230h+var_208], 0
0x18006510d  mov     [rsp+230h+var_210], rcx
0x180065112  lea     r8, [rdi+0Ch]
0x180065116  mov     rcx, [r14]
0x180065119  lea     rdx, aHashblocklengt; "HashBlockLength"
0x180065120  mov     r9d, 4
0x180065126  call    _guard_dispatch_icall
0x18006512b  mov     ebx, eax
0x18006512d  test    eax, eax
0x18006512f  jns     loc_1800651BA
0x180065135  mov     r9d, 6F5h
0x18006513b  jmp     short loc_18006519B
0x18006513d  cmp     esi, 3
0x180065140  jnz     short loc_1800651BA
0x180065142  mov     rax, [rsp+230h+var_1E0]
0x180065147  test    rax, rax
0x18006514a  jnz     short loc_18006515E
0x18006514c  mov     ebx, 0C00000E5h
0x180065151  mov     ecx, 0C00000E5h
0x180065156  mov     r9d, 6FEh
0x18006515c  jmp     short loc_18006519D
0x18006515e  mov     r9d, [rbp+130h+arg_10]
0x180065165  lea     rcx, [rbp+130h+arg_10]
0x18006516c  mov     dword ptr [rsp+230h+var_208], 0
0x180065174  lea     r8, [rdi+1B8h]
0x18006517b  mov     [rsp+230h+var_210], rcx
0x180065180  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x180065187  mov     rcx, [r14]
0x18006518a  call    _guard_dispatch_icall
0x18006518f  mov     ebx, eax
0x180065191  test    eax, eax
0x180065193  jns     short loc_1800651BA
0x180065195  mov     r9d, 70Ah
0x18006519b  mov     ecx, eax
0x18006519d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800651a4  lea     rdx, aStatus; "Status"
0x1800651ab  call    DebugTraceError
0x1800651b0  mov     rcx, rdi; P
0x1800651b3  call    MSCryptFree
0x1800651b8  jmp     short loc_18006521B
0x1800651ba  lea     r9, AlgorithmClassPropertyTable
0x1800651c1  mov     rdx, [r15+r9+10h]
0x1800651c6  test    rdx, rdx
0x1800651c9  jz      short loc_1800651EC
0x1800651cb  mov     rcx, [r14]
0x1800651ce  lea     r8, [r9+18h]
0x1800651d2  mov     r9d, [r15+r9+1Ch]
0x1800651d7  add     r8, r15
0x1800651da  mov     rax, [rsp+230h+var_1D8]
0x1800651df  mov     dword ptr [rsp+230h+var_210], 0
0x1800651e7  call    _guard_dispatch_icall
0x1800651ec  mov     rax, [rbp+130h+arg_0]
0x1800651f3  mov     [rax], rdi
0x1800651f6  jmp     short loc_18006521B
0x1800651f8  mov     r9d, 684h
0x1800651fe  mov     ecx, 0C0000008h
0x180065203  mov     ebx, 0C0000008h
0x180065208  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006520f  lea     rdx, aStatus; "Status"
0x180065216  call    DebugTraceError
0x18006521b  mov     eax, ebx
0x18006521d  mov     rbx, [rsp+230h+arg_8]
0x180065225  add     rsp, 200h
0x18006522c  pop     r15
0x18006522e  pop     r14
0x180065230  pop     r13
0x180065232  pop     r12
0x180065234  pop     rdi
0x180065235  pop     rsi
0x180065236  pop     rbp
0x180065237  retn
```
