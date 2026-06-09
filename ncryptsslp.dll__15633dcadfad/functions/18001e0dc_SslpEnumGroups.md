# SslpEnumGroups

- ea: `0x18001e0dc`
- end: `0x18001e479`
- name: `SslpEnumGroups`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ec10`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x18001e014`
- `0x18001e0dc`
- `0x180024fb0`
- `0x180025660`

## string_xrefs

- `0x18001e13f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x18001e436`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`

## pseudocode

```c
__int64 __fastcall SslpEnumGroups(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned __int64 v3; // rbx
  int v6; // eax
  unsigned int v7; // esi
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r14
  size_t v11; // rbx
  char *v12; // rax
  char *v13; // rdi
  unsigned int v14; // ebp
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // r8
  _OWORD *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r11
  char *v20; // r10
  char *v21; // rax
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  unsigned int v24; // ebp
  unsigned int v26; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v27; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v27 = 0;
  if ( a1 && a2 && a3 )
  {
    v26 = 0;
    v6 = SslpEnumEccCurves(a1, &v26, &v27);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 2222;
      v9 = (unsigned int)v6;
LABEL_6:
      DebugTraceError(v9, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", v8);
      v3 = v27;
      goto LABEL_15;
    }
    v10 = v26;
    v11 = 1432LL * (v26 + 6);
    v12 = (char *)SafeAllocaAllocateFromHeap(v11);
    v13 = v12;
    if ( !v12 )
    {
      v7 = -2146893810;
      v8 = 2232;
      v9 = 2148073486LL;
      goto LABEL_6;
    }
    memset(v12, 0, v11);
    v3 = v27;
    v14 = 0;
    v15 = v27;
    v16 = v27 + 780 * v10;
    if ( v27 < v16 )
    {
      do
      {
        v17 = (_OWORD *)v15;
        v18 = 1432LL * v14;
        v19 = 3;
        v20 = &v13[v18];
        v21 = &v13[v18];
        do
        {
          *(_OWORD *)v21 = *v17;
          *((_OWORD *)v21 + 1) = v17[1];
          *((_OWORD *)v21 + 2) = v17[2];
          *((_OWORD *)v21 + 3) = v17[3];
          *((_OWORD *)v21 + 4) = v17[4];
          *((_OWORD *)v21 + 5) = v17[5];
          *((_OWORD *)v21 + 6) = v17[6];
          v22 = v17[7];
          v17 += 8;
          *((_OWORD *)v21 + 7) = v22;
          v21 += 128;
          --v19;
        }
        while ( v19 );
        ++v14;
        *(_OWORD *)v21 = *v17;
        *((_OWORD *)v21 + 1) = v17[1];
        *((_OWORD *)v21 + 2) = v17[2];
        *((_OWORD *)v21 + 3) = v17[3];
        *((_OWORD *)v21 + 4) = v17[4];
        *((_OWORD *)v21 + 5) = v17[5];
        *((_OWORD *)v21 + 6) = v17[6];
        *(_OWORD *)(v21 + 110) = *(_OWORD *)((char *)v17 + 110);
        wcscpy((wchar_t *)&v13[v18 + 510], L"ECDH");
        *((_WORD *)v20 + 319) = *(_WORD *)(v15 + 772);
        *((_DWORD *)v20 + 160) = 1;
        *((_DWORD *)v20 + 161) = *(_DWORD *)(v15 + 768);
        *((_DWORD *)v20 + 162) = *(_DWORD *)(v15 + 768);
        *((_DWORD *)v20 + 163) = *(_DWORD *)(v15 + 768);
        *(_OWORD *)&v13[v18 + 656] = *(_OWORD *)(v15 + 510);
        *(_OWORD *)&v13[v18 + 672] = *(_OWORD *)(v15 + 526);
        *(_OWORD *)&v13[v18 + 688] = *(_OWORD *)(v15 + 542);
        *(_OWORD *)&v13[v18 + 704] = *(_OWORD *)(v15 + 558);
        *(_OWORD *)&v13[v18 + 720] = *(_OWORD *)(v15 + 574);
        *(_OWORD *)&v13[v18 + 736] = *(_OWORD *)(v15 + 590);
        *(_OWORD *)&v13[v18 + 752] = *(_OWORD *)(v15 + 606);
        *(_OWORD *)&v13[v18 + 768] = *(_OWORD *)(v15 + 622);
        *(_OWORD *)&v13[v18 + 784] = *(_OWORD *)(v15 + 638);
        *(_OWORD *)&v13[v18 + 800] = *(_OWORD *)(v15 + 654);
        *(_OWORD *)&v13[v18 + 816] = *(_OWORD *)(v15 + 670);
        *(_OWORD *)&v13[v18 + 832] = *(_OWORD *)(v15 + 686);
        *(_OWORD *)&v13[v18 + 848] = *(_OWORD *)(v15 + 702);
        *(_OWORD *)&v13[v18 + 864] = *(_OWORD *)(v15 + 718);
        *(_OWORD *)&v13[v18 + 880] = *(_OWORD *)(v15 + 734);
        v23 = *(_OWORD *)(v15 + 749);
        v15 += 780LL;
        *(_DWORD *)(v20 + 1422) = 0;
        *((_DWORD *)v20 + 357) = 0;
        *(_OWORD *)&v13[v18 + 895] = v23;
        *((_WORD *)v20 + 456) = 0;
      }
      while ( v15 < v16 );
    }
    memmove(&v13[1432 * v14], aMlkem512, 0x10C8u);
    v24 = v14 + 3;
    memmove(&v13[1432 * v24], aSecp256r1Mlkem, 0x10C8u);
    *a2 = v13;
    *a3 = v24 + 3;
  }
  else
  {
    v7 = -2146893785;
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", 2211);
  }
LABEL_15:
  if ( v3 )
    MSCryptFree(v3);
  return v7;
}

```

## disassembly

```asm
0x18001e0dc  mov     rax, rsp
0x18001e0df  mov     [rax+10h], rbx
0x18001e0e3  mov     [rax+18h], rbp
0x18001e0e7  push    rsi
0x18001e0e8  push    rdi
0x18001e0e9  push    r12
0x18001e0eb  push    r14
0x18001e0ed  push    r15
0x18001e0ef  sub     rsp, 20h
0x18001e0f3  xor     ebx, ebx
0x18001e0f5  mov     r15, r8
0x18001e0f8  mov     [rax+20h], rbx
0x18001e0fc  mov     r12, rdx
0x18001e0ff  test    rcx, rcx
0x18001e102  jz      loc_18001E430
0x18001e108  test    rdx, rdx
0x18001e10b  jz      loc_18001E430
0x18001e111  test    r8, r8
0x18001e114  jz      loc_18001E430
0x18001e11a  lea     r8, [rax+20h]
0x18001e11e  mov     [rax+8], ebx
0x18001e121  lea     rdx, [rax+8]
0x18001e125  call    SslpEnumEccCurves
0x18001e12a  mov     esi, eax
0x18001e12c  test    eax, eax
0x18001e12e  jns     short loc_18001E155
0x18001e130  mov     r9d, 8AEh
0x18001e136  mov     ecx, eax
0x18001e138  lea     rdx, aStatus_0; "status"
0x18001e13f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e146  call    DebugTraceError
0x18001e14b  mov     rbx, [rsp+48h+arg_18]
0x18001e150  jmp     loc_18001E453
0x18001e155  mov     r14d, [rsp+48h+arg_0]
0x18001e15a  lea     ecx, [r14+6]
0x18001e15e  imul    rbx, rcx, 598h
0x18001e165  mov     rcx, rbx
0x18001e168  call    SafeAllocaAllocateFromHeap
0x18001e16d  mov     rdi, rax
0x18001e170  test    rax, rax
0x18001e173  jnz     short loc_18001E187
0x18001e175  mov     esi, 8009000Eh
0x18001e17a  mov     r9d, 8B8h
0x18001e180  mov     ecx, 8009000Eh
0x18001e185  jmp     short loc_18001E138
0x18001e187  mov     r8, rbx; Size
0x18001e18a  xor     edx, edx; Val
0x18001e18c  mov     rcx, rdi; void *
0x18001e18f  call    memset
0x18001e194  mov     rbx, [rsp+48h+arg_18]
0x18001e199  xor     ebp, ebp
0x18001e19b  imul    r8, r14, 30Ch
0x18001e1a2  mov     rdx, rbx
0x18001e1a5  add     r8, rbx
0x18001e1a8  cmp     rbx, r8
0x18001e1ab  jnb     loc_18001E3E5
0x18001e1b1  mov     r14d, 80h
0x18001e1b7  mov     eax, ebp
0x18001e1b9  mov     rcx, rdx
0x18001e1bc  imul    r9, rax, 598h
0x18001e1c3  mov     r11d, 3
0x18001e1c9  lea     r10, [r9+rdi]
0x18001e1cd  mov     rax, r10
0x18001e1d0  movups  xmm0, xmmword ptr [rcx]
0x18001e1d3  movups  xmmword ptr [rax], xmm0
0x18001e1d6  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e1da  movups  xmmword ptr [rax+10h], xmm1
0x18001e1de  movups  xmm0, xmmword ptr [rcx+20h]
0x18001e1e2  movups  xmmword ptr [rax+20h], xmm0
0x18001e1e6  movups  xmm1, xmmword ptr [rcx+30h]
0x18001e1ea  movups  xmmword ptr [rax+30h], xmm1
0x18001e1ee  movups  xmm0, xmmword ptr [rcx+40h]
0x18001e1f2  movups  xmmword ptr [rax+40h], xmm0
0x18001e1f6  movups  xmm1, xmmword ptr [rcx+50h]
0x18001e1fa  movups  xmmword ptr [rax+50h], xmm1
0x18001e1fe  movups  xmm0, xmmword ptr [rcx+60h]
0x18001e202  movups  xmmword ptr [rax+60h], xmm0
0x18001e206  movups  xmm1, xmmword ptr [rcx+70h]
0x18001e20a  add     rcx, r14
0x18001e20d  movups  xmmword ptr [rax+70h], xmm1
0x18001e211  add     rax, r14
0x18001e214  sub     r11, 1
0x18001e218  jnz     short loc_18001E1D0
0x18001e21a  movups  xmm0, xmmword ptr [rcx]
0x18001e21d  inc     ebp
0x18001e21f  movups  xmmword ptr [rax], xmm0
0x18001e222  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e226  movups  xmmword ptr [rax+10h], xmm1
0x18001e22a  movups  xmm0, xmmword ptr [rcx+20h]
0x18001e22e  movups  xmmword ptr [rax+20h], xmm0
0x18001e232  movups  xmm1, xmmword ptr [rcx+30h]
0x18001e236  movups  xmmword ptr [rax+30h], xmm1
0x18001e23a  movups  xmm0, xmmword ptr [rcx+40h]
0x18001e23e  movups  xmmword ptr [rax+40h], xmm0
0x18001e242  movups  xmm1, xmmword ptr [rcx+50h]
0x18001e246  movups  xmmword ptr [rax+50h], xmm1
0x18001e24a  movups  xmm0, xmmword ptr [rcx+60h]
0x18001e24e  movups  xmmword ptr [rax+60h], xmm0
0x18001e252  movups  xmm1, xmmword ptr [rcx+6Eh]
0x18001e256  movups  xmmword ptr [rax+6Eh], xmm1
0x18001e25a  movsd   xmm0, qword ptr cs:aEcdh; "ECDH"
0x18001e262  movsd   qword ptr [r9+rdi+1FEh], xmm0
0x18001e26c  movzx   eax, word ptr cs:aEcdh+8; ""
0x18001e273  mov     [r9+rdi+206h], ax
0x18001e27c  movzx   eax, word ptr [rdx+304h]
0x18001e283  mov     [r10+27Eh], ax
0x18001e28b  mov     dword ptr [r10+280h], 1
0x18001e296  mov     eax, [rdx+300h]
0x18001e29c  mov     [r10+284h], eax
0x18001e2a3  mov     eax, [rdx+300h]
0x18001e2a9  mov     [r10+288h], eax
0x18001e2b0  mov     eax, [rdx+300h]
0x18001e2b6  mov     [r10+28Ch], eax
0x18001e2bd  xor     eax, eax
0x18001e2bf  movups  xmm0, xmmword ptr [rdx+1FEh]
0x18001e2c6  movups  xmmword ptr [r9+rdi+290h], xmm0
0x18001e2cf  movups  xmm1, xmmword ptr [rdx+20Eh]
0x18001e2d6  movups  xmmword ptr [r9+rdi+2A0h], xmm1
0x18001e2df  movups  xmm0, xmmword ptr [rdx+21Eh]
0x18001e2e6  movups  xmmword ptr [r9+rdi+2B0h], xmm0
0x18001e2ef  movups  xmm1, xmmword ptr [rdx+22Eh]
0x18001e2f6  movups  xmmword ptr [r9+rdi+2C0h], xmm1
0x18001e2ff  movups  xmm0, xmmword ptr [rdx+23Eh]
0x18001e306  movups  xmmword ptr [r9+rdi+2D0h], xmm0
0x18001e30f  movups  xmm1, xmmword ptr [rdx+24Eh]
0x18001e316  movups  xmmword ptr [r9+rdi+2E0h], xmm1
0x18001e31f  movups  xmm0, xmmword ptr [rdx+25Eh]
0x18001e326  movups  xmmword ptr [r9+rdi+2F0h], xmm0
0x18001e32f  movups  xmm1, xmmword ptr [rdx+26Eh]
0x18001e336  movups  xmmword ptr [r9+rdi+300h], xmm1
0x18001e33f  movups  xmm0, xmmword ptr [rdx+27Eh]
0x18001e346  movups  xmmword ptr [r9+rdi+310h], xmm0
0x18001e34f  movups  xmm1, xmmword ptr [rdx+28Eh]
0x18001e356  movups  xmmword ptr [r9+rdi+320h], xmm1
0x18001e35f  movups  xmm0, xmmword ptr [rdx+29Eh]
0x18001e366  movups  xmmword ptr [r9+rdi+330h], xmm0
0x18001e36f  movups  xmm1, xmmword ptr [rdx+2AEh]
0x18001e376  movups  xmmword ptr [r9+rdi+340h], xmm1
0x18001e37f  movups  xmm0, xmmword ptr [rdx+2BEh]
0x18001e386  movups  xmmword ptr [r9+rdi+350h], xmm0
0x18001e38f  movups  xmm1, xmmword ptr [rdx+2CEh]
0x18001e396  movups  xmmword ptr [r9+rdi+360h], xmm1
0x18001e39f  movups  xmm0, xmmword ptr [rdx+2DEh]
0x18001e3a6  movups  xmmword ptr [r9+rdi+370h], xmm0
0x18001e3af  movups  xmm1, xmmword ptr [rdx+2EDh]
0x18001e3b6  add     rdx, 30Ch
0x18001e3bd  mov     [r10+58Eh], eax
0x18001e3c4  mov     [r10+594h], eax
0x18001e3cb  movups  xmmword ptr [r9+rdi+37Fh], xmm1
0x18001e3d4  mov     [r10+390h], ax
0x18001e3dc  cmp     rdx, r8
0x18001e3df  jb      loc_18001E1B7
0x18001e3e5  mov     eax, ebp
0x18001e3e7  lea     rdx, aMlkem512; "MLKEM512"
0x18001e3ee  imul    rcx, rax, 598h
0x18001e3f5  mov     r14d, 10C8h
0x18001e3fb  add     rcx, rdi; void *
0x18001e3fe  mov     r8d, r14d; Size
0x18001e401  call    memmove
0x18001e406  add     ebp, 3
0x18001e409  lea     rdx, aSecp256r1Mlkem; "SECP256R1_MLKEM768"
0x18001e410  mov     eax, ebp
0x18001e412  mov     r8d, r14d; Size
0x18001e415  imul    rcx, rax, 598h
0x18001e41c  add     rcx, rdi; void *
0x18001e41f  call    memmove
0x18001e424  lea     eax, [rbp+3]
0x18001e427  mov     [r12], rdi
0x18001e42b  mov     [r15], eax
0x18001e42e  jmp     short loc_18001E453
0x18001e430  mov     r9d, 8A3h
0x18001e436  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e43d  lea     rdx, aStatus_0; "status"
0x18001e444  mov     ecx, 80090027h
0x18001e449  mov     esi, 80090027h
0x18001e44e  call    DebugTraceError
0x18001e453  test    rbx, rbx
0x18001e456  jz      short loc_18001E460
0x18001e458  mov     rcx, rbx
0x18001e45b  call    MSCryptFree
0x18001e460  mov     rbx, [rsp+48h+arg_8]
0x18001e465  mov     eax, esi
0x18001e467  mov     rbp, [rsp+48h+arg_10]
0x18001e46c  add     rsp, 20h
0x18001e470  pop     r15
0x18001e472  pop     r14
0x18001e474  pop     r12
0x18001e476  pop     rdi
0x18001e477  pop     rsi
0x18001e478  retn
```
