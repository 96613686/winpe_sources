# bCopyColorPointer

- ea: `0x140014670`
- end: `0x1400148d7`
- name: `bCopyColorPointer`
- size: `615`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014338`

## callees

- `0x140014670`
- `0x1400334c4`
- `0x1400371f0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400147be`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400147be`
- `watchdog!WdLogSingleEntry0` at `0x1400147a7`
- `watchdog!WdLogSingleEntry0` at `0x1400147a7`
- `WIN32K!EngCopyBits` at `0x14001477e`
- `WIN32K!EngCopyBits` at `0x14001477e`

## pseudocode

```c
__int64 __fastcall bCopyColorPointer(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  unsigned int v4; // r15d
  unsigned int v9; // esi
  _DWORD *v10; // rcx
  unsigned int v11; // edx
  int v12; // r9d
  __int64 v13; // rdx
  int v14; // ecx
  unsigned int *v15; // rdi
  SURFOBJ *v16; // rcx
  int v17; // ebp
  __int64 v18; // rdi
  _QWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r12
  int v22; // ecx
  unsigned int i; // r11d
  __int64 j; // r9
  __int64 v25; // r10
  __int64 v26; // rdx
  unsigned int k; // r8d
  __int64 m; // rcx
  POINTL pptlSrc; // [rsp+30h] [rbp-48h] BYREF
  RECTL prclDest; // [rsp+38h] [rbp-40h] BYREF

  v4 = *(_DWORD *)(a3 + 32);
  if ( v4 > *(_DWORD *)(a1 + 80) )
    return 0;
  v9 = *(_DWORD *)(a3 + 36);
  if ( v9 > *(_DWORD *)(a1 + 84) )
    return 0;
  v10 = *(_DWORD **)(a1 + 40);
  v11 = 0;
  if ( a2 )
  {
    if ( *(_DWORD *)(a1 + 24) * *(_DWORD *)(a1 + 20) )
    {
      do
      {
        *v10 = -16777216;
        ++v11;
        ++v10;
      }
      while ( v11 < *(_DWORD *)(a1 + 20) * *(_DWORD *)(a1 + 24) );
    }
  }
  else
  {
    memset(v10, 0, (unsigned int)(*(_DWORD *)(a1 + 24) * *(_DWORD *)(a1 + 28)));
  }
  if ( *(_DWORD *)(a3 + 72) == 4 )
  {
    v12 = *(_DWORD *)(a3 + 64);
    v13 = *(_QWORD *)(a3 + 48);
    v14 = -v12;
    if ( v12 > 0 )
      v14 = *(_DWORD *)(a3 + 64);
    if ( (*(_BYTE *)(a3 + 78) & 1) == 0 )
      LODWORD(v13) = (v9 - 1) * v14 + v13;
    v15 = (unsigned int *)(a1 + 28);
    Copy16TO32(*(_QWORD *)(a1 + 40), v13, *(_DWORD *)(a1 + 28), v12, v4, v9);
  }
  else
  {
    v16 = *(SURFOBJ **)(a1 + 56);
    prclDest.right = *(_DWORD *)(a3 + 32);
    prclDest.bottom = *(_DWORD *)(a3 + 36);
    pptlSrc = 0;
    *(_QWORD *)&prclDest.left = 0;
    EngCopyBits(v16, (SURFOBJ *)a3, 0, 0, &prclDest, &pptlSrc);
    v15 = (unsigned int *)(a1 + 28);
  }
  v17 = a4 & 0x10;
  if ( a2 )
  {
    v18 = *(_QWORD *)(a2 + 48);
    if ( v17 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 681;
      v19 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v19[3] = gCddImageInfo;
      v19[4] = (unsigned int)dword_14003E570;
      v19[5] = 215857758;
      WdLogGlobalForLineNumber = 681;
    }
    v20 = *(int *)(a2 + 64);
    v21 = *(_QWORD *)(a1 + 40);
    v22 = -*(_DWORD *)(a2 + 64);
    if ( *(int *)(a2 + 64) > 0 )
      v22 = *(_DWORD *)(a2 + 64);
    if ( (*(_BYTE *)(a2 + 78) & 1) == 0 )
      v18 += (v9 - 1) * v22;
    for ( i = 0; i < v9; ++i )
    {
      for ( j = 0; (unsigned int)j < v4; j = (unsigned int)(j + 1) )
      {
        v25 = v21 + 4 * j;
        if ( ((unsigned __int8)(1 << (7 - (j & 7))) & *(_BYTE *)(((unsigned __int64)(unsigned int)j >> 3) + v18)) != 0 )
          *(_DWORD *)v25 |= 0xFF000000;
        else
          *(_BYTE *)(v25 + 3) = 0;
      }
      v18 += v20;
      v21 += *(unsigned int *)(a1 + 28);
    }
  }
  else if ( !v17 )
  {
    v26 = *(_QWORD *)(a1 + 40);
    for ( k = 0; k < v9; v26 += *v15 )
    {
      for ( m = 0; (unsigned int)m < v4; m = (unsigned int)(m + 1) )
        *(_DWORD *)(v26 + 4 * m) |= 0xFF000000;
      ++k;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140014670  mov     [rsp+arg_8], rbx
0x140014675  mov     [rsp+arg_18], rbp
0x14001467a  push    rsi
0x14001467b  push    rdi
0x14001467c  push    r12
0x14001467e  push    r14
0x140014680  push    r15
0x140014682  sub     rsp, 50h
0x140014686  mov     rax, cs:__security_cookie
0x14001468d  xor     rax, rsp
0x140014690  mov     [rsp+78h+var_30], rax
0x140014695  mov     r15d, [r8+20h]
0x140014699  mov     ebp, r9d
0x14001469c  mov     rdi, r8
0x14001469f  mov     r14, rdx
0x1400146a2  mov     rbx, rcx
0x1400146a5  cmp     r15d, [rcx+50h]
0x1400146a9  ja      loc_1400148AE
0x1400146af  mov     esi, [r8+24h]
0x1400146b3  cmp     esi, [rcx+54h]
0x1400146b6  ja      loc_1400148AE
0x1400146bc  mov     rcx, [rcx+28h]; void *
0x1400146c0  xor     edx, edx; Val
0x1400146c2  mov     r12d, 0FF000000h
0x1400146c8  test    r14, r14
0x1400146cb  jnz     short loc_1400146DD
0x1400146cd  mov     r8d, [rbx+1Ch]
0x1400146d1  imul    r8d, [rbx+18h]; Size
0x1400146d6  call    memset
0x1400146db  jmp     short loc_1400146FC
0x1400146dd  mov     eax, [rbx+14h]
0x1400146e0  imul    eax, [rbx+18h]
0x1400146e4  test    eax, eax
0x1400146e6  jz      short loc_1400146FC
0x1400146e8  mov     [rcx], r12d
0x1400146eb  inc     edx
0x1400146ed  mov     eax, [rbx+18h]
0x1400146f0  lea     rcx, [rcx+4]
0x1400146f4  imul    eax, [rbx+14h]
0x1400146f8  cmp     edx, eax
0x1400146fa  jb      short loc_1400146E8
0x1400146fc  cmp     dword ptr [rdi+48h], 4
0x140014700  jnz     short loc_14001473D
0x140014702  mov     r9d, [rdi+40h]
0x140014706  mov     ecx, r9d
0x140014709  mov     rdx, [rdi+30h]
0x14001470d  neg     ecx
0x14001470f  cmovs   ecx, r9d
0x140014713  test    byte ptr [rdi+4Eh], 1
0x140014717  jnz     short loc_140014722
0x140014719  lea     eax, [rsi-1]
0x14001471c  imul    ecx, eax
0x14001471f  add     rdx, rcx
0x140014722  mov     rcx, [rbx+28h]
0x140014726  lea     rdi, [rbx+1Ch]
0x14001472a  mov     r8d, [rdi]
0x14001472d  mov     dword ptr [rsp+78h+pptlSrc], esi
0x140014731  mov     dword ptr [rsp+78h+prclDest], r15d
0x140014736  call    Copy16TO32
0x14001473b  jmp     short loc_14001478E
0x14001473d  mov     eax, [rdi+20h]
0x140014740  xor     r9d, r9d; pxlo
0x140014743  mov     rcx, [rbx+38h]; psoDest
0x140014747  xor     r8d, r8d; pco
0x14001474a  mov     [rsp+78h+var_40.right], eax
0x14001474e  mov     rdx, rdi; psoSrc
0x140014751  mov     eax, [rdi+24h]
0x140014754  mov     [rsp+78h+var_40.bottom], eax
0x140014758  lea     rax, [rsp+78h+var_48]
0x14001475d  mov     [rsp+78h+pptlSrc], rax; pptlSrc
0x140014762  lea     rax, [rsp+78h+var_40]
0x140014767  mov     [rsp+78h+prclDest], rax; prclDest
0x14001476c  mov     qword ptr [rsp+78h+var_48.x], 0
0x140014775  mov     qword ptr [rsp+78h+var_40.left], 0
0x14001477e  call    cs:__imp_EngCopyBits
0x140014785  nop     dword ptr [rax+rax+00h]
0x14001478a  lea     rdi, [rbx+1Ch]
0x14001478e  and     ebp, 10h
0x140014791  test    r14, r14
0x140014794  jz      loc_140014879
0x14001479a  mov     rdi, [r14+30h]
0x14001479e  test    ebp, ebp
0x1400147a0  jz      short loc_1400147F0
0x1400147a2  mov     ecx, 1
0x1400147a7  call    cs:__imp_WdLogSingleEntry0
0x1400147ae  nop     dword ptr [rax+rax+00h]
0x1400147b3  mov     ebp, 2A9h
0x1400147b8  mov     cs:WdLogGlobalForLineNumber, ebp
0x1400147be  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400147c5  nop     dword ptr [rax+rax+00h]
0x1400147ca  mov     rcx, rax
0x1400147cd  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400147d4  mov     [rcx+18h], rax
0x1400147d8  mov     eax, cs:dword_14003E570
0x1400147de  mov     [rcx+20h], rax
0x1400147e2  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x1400147ea  mov     cs:WdLogGlobalForLineNumber, ebp
0x1400147f0  movsxd  rdx, dword ptr [r14+40h]
0x1400147f4  mov     al, [r14+4Eh]
0x1400147f8  mov     ecx, edx
0x1400147fa  mov     r12, [rbx+28h]
0x1400147fe  neg     ecx
0x140014800  mov     r14d, 1
0x140014806  cmovs   ecx, edx
0x140014809  test    r14b, al
0x14001480c  jnz     short loc_140014817
0x14001480e  lea     eax, [rsi-1]
0x140014811  imul    ecx, eax
0x140014814  add     rdi, rcx
0x140014817  xor     r11d, r11d
0x14001481a  test    esi, esi
0x14001481c  jz      loc_1400148A7
0x140014822  mov     rbp, rdx
0x140014825  xor     r9d, r9d
0x140014828  test    r15d, r15d
0x14001482b  jz      short loc_140014866
0x14001482d  mov     eax, r9d
0x140014830  mov     r8d, r9d
0x140014833  and     eax, 7
0x140014836  shr     r8, 3
0x14001483a  mov     ecx, 7
0x14001483f  lea     r10, [r12+r9*4]
0x140014843  sub     ecx, eax
0x140014845  mov     edx, r14d
0x140014848  shl     edx, cl
0x14001484a  test    [r8+rdi], dl
0x14001484e  jz      short loc_140014859
0x140014850  or      dword ptr [r10], 0FF000000h
0x140014857  jmp     short loc_14001485E
0x140014859  mov     byte ptr [r10+3], 0
0x14001485e  add     r9d, r14d
0x140014861  cmp     r9d, r15d
0x140014864  jb      short loc_14001482D
0x140014866  mov     eax, [rbx+1Ch]
0x140014869  add     rdi, rbp
0x14001486c  add     r12, rax
0x14001486f  add     r11d, r14d
0x140014872  cmp     r11d, esi
0x140014875  jb      short loc_140014825
0x140014877  jmp     short loc_1400148A7
0x140014879  test    ebp, ebp
0x14001487b  jnz     short loc_1400148A7
0x14001487d  mov     rdx, [rbx+28h]
0x140014881  xor     r8d, r8d
0x140014884  test    esi, esi
0x140014886  jz      short loc_1400148A7
0x140014888  xor     ecx, ecx
0x14001488a  test    r15d, r15d
0x14001488d  jz      short loc_14001489A
0x14001488f  or      [rdx+rcx*4], r12d
0x140014893  inc     ecx
0x140014895  cmp     ecx, r15d
0x140014898  jb      short loc_14001488F
0x14001489a  mov     ecx, [rdi]
0x14001489c  inc     r8d
0x14001489f  add     rdx, rcx
0x1400148a2  cmp     r8d, esi
0x1400148a5  jb      short loc_140014888
0x1400148a7  mov     eax, 1
0x1400148ac  jmp     short loc_1400148B0
0x1400148ae  xor     eax, eax
0x1400148b0  mov     rcx, [rsp+78h+var_30]
0x1400148b5  xor     rcx, rsp; StackCookie
0x1400148b8  call    __security_check_cookie
0x1400148bd  lea     r11, [rsp+78h+var_28]
0x1400148c2  mov     rbx, [r11+38h]
0x1400148c6  mov     rbp, [r11+48h]
0x1400148ca  mov     rsp, r11
0x1400148cd  pop     r15
0x1400148cf  pop     r14
0x1400148d1  pop     r12
0x1400148d3  pop     rdi
0x1400148d4  pop     rsi
0x1400148d5  retn
```
