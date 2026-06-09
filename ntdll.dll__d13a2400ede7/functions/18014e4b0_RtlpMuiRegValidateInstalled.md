# _RtlpMuiRegValidateInstalled

- ea: `0x18014e4b0`
- end: `0x18014e878`
- name: `_RtlpMuiRegValidateInstalled`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801210e0`

## callees

- `0x18000908c`
- `0x18000a360`
- `0x18000c6b0`
- `0x18001861c`
- `0x1800bcb1c`
- `0x1800bccd0`
- `0x1800bce00`
- `0x1800cc700`
- `0x18014d598`
- `0x18014e4b0`
- `0x18014e880`
- `0x18014eab0`
- `0x18014ebcc`
- `0x180160c30`
- `0x180161650`
- `0x180162810`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpMuiRegValidateInstalled(__int64 a1)
{
  __int16 v2; // si
  int IsUILanguageComitted; // eax
  __int64 v4; // rdx
  int v5; // r13d
  __int64 result; // rax
  int v7; // r14d
  int InstalledLanguageIndexByLangId; // eax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // eax
  __int16 v14; // cx
  int v15; // edi
  __int64 v16; // rcx
  int v17; // esi
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int16 v20; // cx
  int v21; // edx
  __int64 v22; // r9
  __int16 v23; // cx
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v26; // edi
  _WORD v27[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v28[2]; // [rsp+24h] [rbp-DCh] BYREF
  int v29; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v30; // [rsp+2Ch] [rbp-D4h]
  __int16 v31; // [rsp+2Eh] [rbp-D2h]
  __int16 v32; // [rsp+30h] [rbp-D0h]
  __int128 v33; // [rsp+32h] [rbp-CEh]
  __int16 v34; // [rsp+42h] [rbp-BEh]
  __int64 v35; // [rsp+48h] [rbp-B8h]
  __int128 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[176]; // [rsp+70h] [rbp-90h] BYREF

  v27[0] = 0;
  v2 = -1;
  v34 = 0;
  v28[0] = -1;
  v37 = 0;
  v33 = 0;
  v36 = 0;
  memset_thunk_772440563353939046(v38, 0, 0xAAu);
  IsUILanguageComitted = NtIsUILanguageComitted();
  v4 = *(unsigned __int16 *)(a1 + 4);
  v5 = IsUILanguageComitted;
  if ( (_WORD)v4 )
  {
    v27[0] = *(_WORD *)(a1 + 4);
  }
  else
  {
    result = NtQueryInstallUILanguage(v27);
    if ( (int)result < 0 )
      return result;
    v4 = v27[0];
  }
  v7 = -1;
  InstalledLanguageIndexByLangId = RtlpMuiRegGetInstalledLanguageIndexByLangId(a1, v4, 0, v28);
  if ( InstalledLanguageIndexByLangId == -1073741772 || InstalledLanguageIndexByLangId == -1073741637 )
  {
    v28[0] = -1;
    v11 = MuiRegAllocArray(v9, 85);
    v35 = v11;
    v10 = v11;
    if ( !v11 )
      return 3221225495LL;
    if ( (unsigned __int8)RtlpInitAndCallLcidToCultureName(&v37, v11, v27[0]) )
    {
      LOBYTE(v12) = 1;
      v13 = RtlpMuiRegGetOrAddString(a1, *((_QWORD *)&v37 + 1), v12, v28);
      v14 = -1;
      if ( v13 >= 0 )
        v14 = v28[0];
      v30 = v27[0];
      v31 = v14;
      *(_QWORD *)((char *)&v33 + 2) = 0;
      *(_DWORD *)((char *)&v33 + 10) = 0;
      HIWORD(v33) = 0;
      v34 = 0;
      v29 = 49;
      v32 = 0;
      RtlpMuiRegAddNeutralLanguage(a1, &v29, *((_QWORD *)&v37 + 1));
      if ( (int)RtlpMuiRegGetOrAddLangInfo(a1 + 24, &v29, 0) >= 0 )
        v7 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 6LL) - 1;
    }
  }
  else
  {
    v35 = 0;
    v10 = 0;
    if ( InstalledLanguageIndexByLangId >= 0 )
      v7 = v28[0];
  }
  v15 = 0;
  if ( v7 != -1 )
  {
    *((_QWORD *)&v36 + 1) = v38;
    WORD1(v36) = 170;
    if ( (int)RtlpGetNameFromLangInfoNode(a1, 28LL * v7 + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL), &v36) >= 0 )
    {
      if ( (int)RtlpIsALicensedRegularLanguage(a1, *((_QWORD *)&v36 + 1)) >= 0 )
      {
        v15 = 1;
      }
      else
      {
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v7) &= ~0x20u;
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v7) |= 0x8000u;
      }
    }
  }
  if ( !v5 )
    v2 = v7;
  RtlpRemovePendingDeleteLanguages(a1, v2);
  v16 = *(_QWORD *)(a1 + 24);
  if ( *(_WORD *)(v16 + 6) )
  {
    v17 = 0;
    do
    {
      if ( (*(_BYTE *)(28LL * v17 + *(_QWORD *)(v16 + 16)) & 0x22) == 0x22 )
      {
        RtlpMuiRegValidatePartialLanguage(a1, (unsigned int)v17);
        v18 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
        v19 = v15 + 1;
        v20 = *(_WORD *)(v18 + 28LL * v17);
        if ( (v20 & 0x1000) != 0 )
          v19 = v15;
        v15 = v19;
        if ( !v5 && v17 != v7 && v19 > *(_DWORD *)(a1 + 120) )
        {
          *(_WORD *)(v18 + 28LL * v17) = v20 & 0xFFDF;
          *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v17) |= 0x8000u;
        }
      }
      v16 = *(_QWORD *)(a1 + 24);
      ++v17;
    }
    while ( v17 < *(unsigned __int16 *)(v16 + 6) );
    v10 = v35;
  }
  if ( !v5 && *(_WORD *)(v16 + 6) )
  {
    v21 = 0;
    do
    {
      v22 = *(_QWORD *)(v16 + 16);
      v23 = *(_WORD *)(v22 + 28LL * v21);
      if ( (v23 & 0x21) == 0x21 )
      {
        v24 = v15 + 1;
        if ( (v23 & 0x1000) != 0 )
          v24 = v15;
        v15 = v24;
        if ( v21 != v7 && v24 > *(_DWORD *)(a1 + 120) )
        {
          *(_WORD *)(v22 + 28LL * v21) = v23 & 0xFFDF;
          *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v21) |= 0x8000u;
        }
      }
      v16 = *(_QWORD *)(a1 + 24);
      ++v21;
    }
    while ( v21 < *(unsigned __int16 *)(v16 + 6) );
    v10 = v35;
  }
  v25 = *(_QWORD *)(a1 + 24);
  if ( *(_WORD *)(v25 + 6) )
  {
    v26 = 0;
    do
    {
      if ( (*(_BYTE *)(28LL * v26 + *(_QWORD *)(v25 + 16)) & 4) != 0 )
        RtlpMuiRegValidateLIPLanguage(a1, (unsigned int)v26);
      v25 = *(_QWORD *)(a1 + 24);
      ++v26;
    }
    while ( v26 < *(unsigned __int16 *)(v25 + 6) );
  }
  if ( v10 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v10);
  return 0;
}

```

## disassembly

```asm
0x18014e4b0  push    rbp
0x18014e4b2  push    rbx
0x18014e4b3  push    rsi
0x18014e4b4  push    rdi
0x18014e4b5  push    r12
0x18014e4b7  push    r13
0x18014e4b9  push    r14
0x18014e4bb  push    r15
0x18014e4bd  lea     rbp, [rsp-38h]
0x18014e4c2  sub     rsp, 138h
0x18014e4c9  mov     rax, cs:__security_cookie
0x18014e4d0  xor     rax, rsp
0x18014e4d3  mov     [rbp+70h+var_50], rax
0x18014e4d7  xorps   xmm0, xmm0
0x18014e4da  mov     rbx, rcx
0x18014e4dd  xor     r15d, r15d
0x18014e4e0  lea     rcx, [rsp+170h+var_100]; void *
0x18014e4e5  xorps   xmm1, xmm1
0x18014e4e8  mov     [rsp+170h+var_150], r15w
0x18014e4ee  or      esi, 0FFFFFFFFh
0x18014e4f1  mov     [rsp+170h+var_12E], r15w
0x18014e4f7  xor     edx, edx; Val
0x18014e4f9  mov     [rsp+170h+var_14C], si
0x18014e4fe  mov     r8d, 0AAh; Size
0x18014e504  movups  [rsp+170h+var_110], xmm0
0x18014e509  movdqu  [rsp+170h+var_13E], xmm1
0x18014e50f  movups  [rsp+170h+var_120], xmm0
0x18014e514  call    memset$thunk$772440563353939046
0x18014e519  call    NtIsUILanguageComitted
0x18014e51e  movzx   edx, word ptr [rbx+4]
0x18014e522  mov     r13d, eax
0x18014e525  test    dx, dx
0x18014e528  jz      short loc_18014E531
0x18014e52a  mov     [rsp+170h+var_150], dx
0x18014e52f  jmp     short loc_18014E548
0x18014e531  lea     rcx, [rsp+170h+var_150]
0x18014e536  call    NtQueryInstallUILanguage
0x18014e53b  test    eax, eax
0x18014e53d  js      loc_18014E857
0x18014e543  movzx   edx, [rsp+170h+var_150]
0x18014e548  lea     r9, [rsp+170h+var_14C]
0x18014e54d  xor     r8d, r8d
0x18014e550  mov     rcx, rbx
0x18014e553  mov     r14d, esi
0x18014e556  call    RtlpMuiRegGetInstalledLanguageIndexByLangId
0x18014e55b  cmp     eax, 0C0000034h
0x18014e560  jz      short loc_18014E584
0x18014e562  cmp     eax, 0C00000BBh
0x18014e567  jz      short loc_18014E584
0x18014e569  mov     [rsp+170h+var_128], r15
0x18014e56e  mov     r12, r15
0x18014e571  test    eax, eax
0x18014e573  js      loc_18014E661
0x18014e579  movsx   r14d, [rsp+170h+var_14C]
0x18014e57f  jmp     loc_18014E661
0x18014e584  mov     edx, 55h ; 'U'
0x18014e589  mov     [rsp+170h+var_14C], si
0x18014e58e  call    _MuiRegAllocArray
0x18014e593  mov     [rsp+170h+var_128], rax
0x18014e598  mov     r12, rax
0x18014e59b  test    rax, rax
0x18014e59e  jnz     short loc_18014E5AA
0x18014e5a0  mov     eax, 0C0000017h
0x18014e5a5  jmp     loc_18014E857
0x18014e5aa  movzx   r8d, [rsp+170h+var_150]
0x18014e5b0  lea     rcx, [rsp+170h+var_110]
0x18014e5b5  mov     rdx, rax
0x18014e5b8  call    RtlpInitAndCallLcidToCultureName
0x18014e5bd  test    al, al
0x18014e5bf  jz      loc_18014E661
0x18014e5c5  mov     rdx, qword ptr [rsp+170h+var_110+8]
0x18014e5ca  lea     r9, [rsp+170h+var_14C]
0x18014e5cf  mov     r8b, 1
0x18014e5d2  mov     rcx, rbx
0x18014e5d5  call    RtlpMuiRegGetOrAddString
0x18014e5da  movzx   ecx, si
0x18014e5dd  test    eax, eax
0x18014e5df  js      short loc_18014E5E6
0x18014e5e1  movzx   ecx, [rsp+170h+var_14C]
0x18014e5e6  movzx   eax, [rsp+170h+var_150]
0x18014e5eb  lea     rdx, [rsp+170h+var_148]
0x18014e5f0  mov     r8, qword ptr [rsp+170h+var_110+8]
0x18014e5f5  mov     [rsp+170h+var_144], ax
0x18014e5fa  mov     eax, r15d
0x18014e5fd  mov     [rsp+170h+var_142], cx
0x18014e602  mov     rcx, rbx
0x18014e605  mov     word ptr [rsp+170h+var_13E+2], ax
0x18014e60a  mov     word ptr [rsp+170h+var_13E+4], ax
0x18014e60f  mov     word ptr [rsp+170h+var_13E+6], ax
0x18014e614  mov     word ptr [rsp+170h+var_13E+8], ax
0x18014e619  mov     word ptr [rsp+170h+var_13E+0Ah], ax
0x18014e61e  mov     word ptr [rsp+170h+var_13E+0Ch], ax
0x18014e623  mov     word ptr [rsp+170h+var_13E+0Eh], ax
0x18014e628  mov     [rsp+170h+var_12E], ax
0x18014e62d  mov     [rsp+170h+var_148], 31h ; '1'
0x18014e635  mov     [rsp+170h+var_140], r15w
0x18014e63b  call    _RtlpMuiRegAddNeutralLanguage
0x18014e640  xor     r8d, r8d
0x18014e643  lea     rdx, [rsp+170h+var_148]
0x18014e648  lea     rcx, [rbx+18h]
0x18014e64c  call    RtlpMuiRegGetOrAddLangInfo
0x18014e651  test    eax, eax
0x18014e653  js      short loc_18014E661
0x18014e655  mov     rax, [rbx+18h]
0x18014e659  movzx   r14d, word ptr [rax+6]
0x18014e65e  dec     r14d
0x18014e661  mov     edi, r15d
0x18014e664  cmp     r14d, esi
0x18014e667  jz      short loc_18014E6DF
0x18014e669  lea     rax, [rsp+170h+var_100]
0x18014e66e  mov     rcx, rbx
0x18014e671  mov     qword ptr [rsp+170h+var_120+8], rax
0x18014e676  lea     r8, [rsp+170h+var_120]
0x18014e67b  mov     eax, 0AAh
0x18014e680  mov     word ptr [rsp+170h+var_120+2], ax
0x18014e685  movsxd  rax, r14d
0x18014e688  imul    r15, rax, 1Ch
0x18014e68c  mov     rax, [rbx+18h]
0x18014e690  mov     rdx, [rax+10h]
0x18014e694  add     rdx, r15
0x18014e697  call    RtlpGetNameFromLangInfoNode
0x18014e69c  test    eax, eax
0x18014e69e  js      short loc_18014E6DC
0x18014e6a0  mov     rdx, qword ptr [rsp+170h+var_120+8]
0x18014e6a5  mov     rcx, rbx
0x18014e6a8  call    RtlpIsALicensedRegularLanguage
0x18014e6ad  test    eax, eax
0x18014e6af  jns     short loc_18014E6D7
0x18014e6b1  mov     rax, [rbx+18h]
0x18014e6b5  mov     rcx, [rax+10h]
0x18014e6b9  mov     eax, 0FFDFh
0x18014e6be  and     [rcx+r15], ax
0x18014e6c3  mov     rax, [rbx+18h]
0x18014e6c7  mov     rcx, [rax+10h]
0x18014e6cb  mov     eax, 8000h
0x18014e6d0  or      [rcx+r15], ax
0x18014e6d5  jmp     short loc_18014E6DC
0x18014e6d7  mov     edi, 1
0x18014e6dc  xor     r15d, r15d
0x18014e6df  test    r13d, r13d
0x18014e6e2  jnz     short loc_18014E6E8
0x18014e6e4  movzx   esi, r14w
0x18014e6e8  movzx   edx, si
0x18014e6eb  mov     rcx, rbx
0x18014e6ee  call    _RtlpRemovePendingDeleteLanguages
0x18014e6f3  mov     rcx, [rbx+18h]
0x18014e6f7  mov     r10d, 1000h
0x18014e6fd  cmp     r15w, [rcx+6]
0x18014e702  jnb     loc_18014E791
0x18014e708  mov     esi, r15d
0x18014e70b  mov     r12d, 0FFDFh
0x18014e711  movsxd  rax, esi
0x18014e714  imul    r15, rax, 1Ch
0x18014e718  mov     rax, [rcx+10h]
0x18014e71c  mov     cl, [r15+rax]
0x18014e720  and     cl, 22h
0x18014e723  cmp     cl, 22h ; '"'
0x18014e726  jnz     short loc_18014E77B
0x18014e728  mov     edx, esi
0x18014e72a  mov     rcx, rbx
0x18014e72d  call    _RtlpMuiRegValidatePartialLanguage
0x18014e732  mov     rax, [rbx+18h]
0x18014e736  mov     r10d, 1000h
0x18014e73c  mov     rdx, [rax+10h]
0x18014e740  lea     eax, [rdi+1]
0x18014e743  movzx   ecx, word ptr [rdx+r15]
0x18014e748  test    r10w, cx
0x18014e74c  cmovnz  eax, edi
0x18014e74f  mov     edi, eax
0x18014e751  test    r13d, r13d
0x18014e754  jnz     short loc_18014E77B
0x18014e756  cmp     esi, r14d
0x18014e759  jz      short loc_18014E77B
0x18014e75b  cmp     eax, [rbx+78h]
0x18014e75e  jbe     short loc_18014E77B
0x18014e760  and     cx, r12w
0x18014e764  mov     [rdx+r15], cx
0x18014e769  mov     rax, [rbx+18h]
0x18014e76d  mov     rcx, [rax+10h]
0x18014e771  mov     eax, 8000h
0x18014e776  or      [rcx+r15], ax
0x18014e77b  mov     rcx, [rbx+18h]
0x18014e77f  inc     esi
0x18014e781  movzx   eax, word ptr [rcx+6]
0x18014e785  cmp     esi, eax
0x18014e787  jl      short loc_18014E711
0x18014e789  mov     r12, [rsp+170h+var_128]
0x18014e78e  xor     r15d, r15d
0x18014e791  test    r13d, r13d
0x18014e794  jnz     short loc_18014E802
0x18014e796  cmp     r15w, [rcx+6]
0x18014e79b  jnb     short loc_18014E802
0x18014e79d  mov     edx, r15d
0x18014e7a0  mov     r12d, 0FFDFh
0x18014e7a6  mov     r9, [rcx+10h]
0x18014e7aa  movsxd  rax, edx
0x18014e7ad  imul    r8, rax, 1Ch
0x18014e7b1  movzx   ecx, word ptr [r9+r8]
0x18014e7b6  mov     al, cl
0x18014e7b8  and     al, 21h
0x18014e7ba  cmp     al, 21h ; '!'
0x18014e7bc  jnz     short loc_18014E7EF
0x18014e7be  test    r10w, cx
0x18014e7c2  lea     eax, [rdi+1]
0x18014e7c5  cmovnz  eax, edi
0x18014e7c8  mov     edi, eax
0x18014e7ca  cmp     edx, r14d
0x18014e7cd  jz      short loc_18014E7EF
0x18014e7cf  cmp     eax, [rbx+78h]
0x18014e7d2  jbe     short loc_18014E7EF
0x18014e7d4  and     cx, r12w
0x18014e7d8  mov     [r9+r8], cx
0x18014e7dd  mov     rax, [rbx+18h]
0x18014e7e1  mov     rcx, [rax+10h]
0x18014e7e5  mov     eax, 8000h
0x18014e7ea  or      [rcx+r8], ax
0x18014e7ef  mov     rcx, [rbx+18h]
0x18014e7f3  inc     edx
0x18014e7f5  movzx   eax, word ptr [rcx+6]
0x18014e7f9  cmp     edx, eax
0x18014e7fb  jl      short loc_18014E7A6
0x18014e7fd  mov     r12, [rsp+170h+var_128]
0x18014e802  mov     rdx, [rbx+18h]
0x18014e806  cmp     r15w, [rdx+6]
0x18014e80b  jnb     short loc_18014E839
0x18014e80d  mov     edi, r15d
0x18014e810  movsxd  rax, edi
0x18014e813  imul    rcx, rax, 1Ch
0x18014e817  mov     rax, [rdx+10h]
0x18014e81b  test    byte ptr [rcx+rax], 4
0x18014e81f  jz      short loc_18014E82B
0x18014e821  mov     edx, edi
0x18014e823  mov     rcx, rbx
0x18014e826  call    _RtlpMuiRegValidateLIPLanguage
0x18014e82b  mov     rdx, [rbx+18h]
0x18014e82f  inc     edi
0x18014e831  movzx   eax, word ptr [rdx+6]
0x18014e835  cmp     edi, eax
0x18014e837  jl      short loc_18014E810
0x18014e839  test    r12, r12
0x18014e83c  jz      short loc_18014E855
0x18014e83e  mov     rcx, gs:60h
0x18014e847  mov     r8, r12
0x18014e84a  xor     edx, edx
0x18014e84c  mov     rcx, [rcx+30h]
0x18014e850  call    RtlFreeHeap_0
0x18014e855  xor     eax, eax
0x18014e857  mov     rcx, [rbp+70h+var_50]
0x18014e85b  xor     rcx, rsp; StackCookie
0x18014e85e  call    __security_check_cookie
0x18014e863  add     rsp, 138h
0x18014e86a  pop     r15
0x18014e86c  pop     r14
0x18014e86e  pop     r13
0x18014e870  pop     r12
0x18014e872  pop     rdi
0x18014e873  pop     rsi
0x18014e874  pop     rbx
0x18014e875  pop     rbp
0x18014e876  retn
```
