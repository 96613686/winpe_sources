# TREE_HASH_TABLE::CalcHash(ushort const *,ulong *)

- ea: `0x180003190`
- end: `0x18000353c`
- name: `?CalcHash@TREE_HASH_TABLE@@QEAAJPEBGPEAK@Z`
- size: `940`
- prototype: `int(TREE_HASH_TABLE *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004250`

## callees

- `0x180003190`
- `0x180003550`
- `0x18002c476`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003500`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003527`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003500`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003527`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003358`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003358`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000334a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003519`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000334a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003519`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003447`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003447`
- `bcrypt!BCryptCreateHash` at `0x180003472`
- `bcrypt!BCryptCreateHash` at `0x180003472`
- `bcrypt!BCryptFinishHash` at `0x1800034ab`
- `bcrypt!BCryptFinishHash` at `0x1800034ab`
- `bcrypt!BCryptHashData` at `0x18000348c`
- `bcrypt!BCryptHashData` at `0x18000348c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800034bf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800034bf`
- `bcrypt!BCryptDestroyHash` at `0x1800034cf`
- `bcrypt!BCryptDestroyHash` at `0x1800034cf`

## pseudocode

```c
int __fastcall TREE_HASH_TABLE::CalcHash(TREE_HASH_TABLE *this, const unsigned __int16 *a2, unsigned int *a3)
{
  const unsigned __int16 *v4; // rdi
  int v5; // ebp
  unsigned __int16 v6; // ax
  int v7; // ebx
  int result; // eax
  char v9; // r14
  __int64 v10; // rax
  UCHAR *v11; // rsi
  __int64 v13; // rbp
  unsigned int v14; // ecx
  unsigned __int16 v15; // cx
  HANDLE ProcessHeap; // rax
  UCHAR *v17; // rax
  UCHAR *v18; // rdx
  UCHAR *v19; // rcx
  __int64 v20; // r8
  UCHAR *v21; // rax
  __int128 v22; // xmm0
  bool v23; // sf
  ULONG v24; // ebx
  unsigned __int64 v25; // rdx
  NTSTATUS v26; // ebp
  unsigned int v27; // r8d
  HANDLE v28; // rax
  HANDLE v29; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-288h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-280h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-278h] BYREF
  __int128 v33; // [rsp+60h] [rbp-268h]
  UCHAR pbInput[2]; // [rsp+70h] [rbp-258h] BYREF
  char v35[526]; // [rsp+72h] [rbp-256h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return -2147024809;
  v5 = 0;
  if ( !*((_DWORD *)this + 6) )
  {
    v15 = *a2;
    v7 = 0;
    if ( *a2 )
    {
      do
      {
        ++v4;
        v7 = (v15 & 0xFFDF) + 101 * v7;
        v15 = *v4;
      }
      while ( *v4 );
    }
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 7) )
  {
    v6 = *a2;
    v7 = 0;
    if ( *a2 )
    {
      do
      {
        ++v4;
        v7 = v6 + 101 * v7;
        v6 = *v4;
      }
      while ( *v4 );
    }
LABEL_7:
    *a3 = (69069 * v7 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v7 + 12345) >> 16);
    return v5;
  }
  memset_0(v35, 0, 0x206u);
  v9 = 0;
  *(_WORD *)pbInput = 0;
  v10 = -1;
  v11 = pbInput;
  while ( v4[++v10] != 0 )
    ;
  v13 = (unsigned int)(2 * v10);
  if ( (unsigned __int64)(v13 + 2) <= 0x208 )
    goto LABEL_13;
  if ( (unsigned __int64)(v13 + 128) > 0xFFFFFFFF )
    return -2147024362;
  if ( (unsigned int)(v13 + 128) <= 0x208 )
    goto LABEL_13;
  ProcessHeap = GetProcessHeap();
  v17 = (UCHAR *)HeapAlloc(ProcessHeap, 0, (unsigned int)(v13 + 128));
  v18 = v17;
  if ( v17 )
  {
    v19 = v17;
    v20 = 4;
    v21 = pbInput;
    do
    {
      v19 += 128;
      v22 = *(_OWORD *)v21;
      v21 += 128;
      *((_OWORD *)v19 - 8) = v22;
      *((_OWORD *)v19 - 7) = *((_OWORD *)v21 - 7);
      *((_OWORD *)v19 - 6) = *((_OWORD *)v21 - 6);
      *((_OWORD *)v19 - 5) = *((_OWORD *)v21 - 5);
      *((_OWORD *)v19 - 4) = *((_OWORD *)v21 - 4);
      *((_OWORD *)v19 - 3) = *((_OWORD *)v21 - 3);
      *((_OWORD *)v19 - 2) = *((_OWORD *)v21 - 2);
      *((_OWORD *)v19 - 1) = *((_OWORD *)v21 - 1);
      --v20;
    }
    while ( v20 );
    v11 = v18;
    *(_QWORD *)v19 = *(_QWORD *)v21;
    v9 = 1;
LABEL_13:
    memcpy_0(v11, v4, (unsigned int)v13);
    v14 = (unsigned int)v13 >> 1;
    *(_WORD *)&v11[2 * ((unsigned int)v13 >> 1)] = 0;
LABEL_28:
    phAlgorithm = 0;
    phHash = 0;
    *(_OWORD *)pbOutput = 0;
    v33 = 0;
    if ( v11 && (v24 = 2 * v14) != 0 )
    {
      v26 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
      if ( v26 >= 0 )
      {
        v26 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
        if ( v26 >= 0 )
        {
          v26 = BCryptHashData(phHash, v11, v24, 0);
          if ( v26 >= 0 )
            v26 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
        }
      }
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      if ( phHash )
        BCryptDestroyHash(phHash);
      v5 = v26 | 0x10000000;
      if ( v5 >= 0 )
      {
        v7 = HashBlob(pbOutput, v25, v27);
        if ( v9 )
        {
          v28 = GetProcessHeap();
          HeapFree(v28, 0, v11);
        }
        goto LABEL_7;
      }
    }
    else
    {
      v5 = -805306355;
    }
    if ( v9 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v11);
    }
    return v5;
  }
  SetLastError(8u);
  result = GetLastError();
  v23 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v23 = result < 0;
  }
  if ( !v23 )
  {
    v14 = 0;
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x180003190  mov     r11, rsp
0x180003193  push    rdi
0x180003194  push    r12
0x180003196  sub     rsp, 2B8h
0x18000319d  mov     rax, cs:__security_cookie
0x1800031a4  xor     rax, rsp
0x1800031a7  mov     [rsp+2C8h+var_48], rax
0x1800031af  mov     r12, r8
0x1800031b2  mov     rdi, rdx
0x1800031b5  test    rdx, rdx
0x1800031b8  jz      loc_180003532
0x1800031be  test    r8, r8
0x1800031c1  jz      loc_180003532
0x1800031c7  mov     [r11-18h], rbp
0x1800031cb  mov     [r11-28h], r13
0x1800031cf  xor     r13d, r13d
0x1800031d2  mov     ebp, r13d
0x1800031d5  mov     [r11+8], rbx
0x1800031d9  mov     [r11-20h], rsi
0x1800031dd  mov     [r11-30h], r14
0x1800031e1  mov     [r11-38h], r15
0x1800031e5  cmp     [rcx+18h], r13d
0x1800031e9  jz      loc_1800032F9
0x1800031ef  cmp     [rcx+1Ch], r13d
0x1800031f3  jnz     loc_180003293
0x1800031f9  movzx   eax, word ptr [rdx]
0x1800031fc  mov     ebx, r13d
0x1800031ff  test    ax, ax
0x180003202  jz      short loc_180003224
0x180003204  nop     dword ptr [rax+00h]
0x180003208  nop     dword ptr [rax+rax+00000000h]
0x180003210  imul    ebx, 65h ; 'e'
0x180003213  lea     rdi, [rdi+2]
0x180003217  movzx   eax, ax
0x18000321a  add     ebx, eax
0x18000321c  movzx   eax, word ptr [rdi]
0x18000321f  test    ax, ax
0x180003222  jnz     short loc_180003210
0x180003224  imul    ecx, ebx, 41C64E6Dh
0x18000322a  imul    eax, ebx, 10DCDh
0x180003230  add     ecx, 3039h
0x180003236  inc     eax
0x180003238  shr     ecx, 10h
0x18000323b  and     eax, 0FFFF0000h
0x180003240  or      ecx, eax
0x180003242  mov     [r12], ecx
0x180003246  mov     eax, ebp
0x180003248  mov     r14, [rsp+2C8h+var_30]
0x180003250  mov     rbx, [rsp+2C8h+arg_0]
0x180003258  mov     rsi, [rsp+2C8h+var_20]
0x180003260  mov     r15, [rsp+2C8h+var_38]
0x180003268  mov     rbp, [rsp+2C8h+var_18]
0x180003270  mov     r13, [rsp+2C8h+var_28]
0x180003278  mov     rcx, [rsp+2C8h+var_48]
0x180003280  xor     rcx, rsp; StackCookie
0x180003283  call    __security_check_cookie
0x180003288  add     rsp, 2B8h
0x18000328f  pop     r12
0x180003291  pop     rdi
0x180003292  retn
0x180003293  xor     edx, edx; Val
0x180003295  lea     rcx, [rsp+2C8h+var_256]; void *
0x18000329a  mov     r8d, 206h; Size
0x1800032a0  call    memset_0
0x1800032a5  xor     r14b, r14b
0x1800032a8  mov     word ptr [rsp+2C8h+pbInput], r13w
0x1800032ae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800032b5  lea     rsi, [rsp+2C8h+pbInput]
0x1800032ba  nop     word ptr [rax+rax+00h]
0x1800032c0  cmp     [rdi+rax*2+2], bp
0x1800032c5  lea     rax, [rax+1]
0x1800032c9  jnz     short loc_1800032C0
0x1800032cb  lea     ebp, [rax+rax]
0x1800032ce  lea     rax, [rbp+2]
0x1800032d2  mov     r15d, ebp
0x1800032d5  cmp     rax, 208h
0x1800032db  ja      short loc_18000332C
0x1800032dd  mov     r8, r15; Size
0x1800032e0  mov     rdx, rdi; Src
0x1800032e3  mov     rcx, rsi; void *
0x1800032e6  call    memcpy_0
0x1800032eb  shr     ebp, 1
0x1800032ed  mov     ecx, ebp
0x1800032ef  mov     [rsi+rbp*2], r13w
0x1800032f4  jmp     loc_18000340A
0x1800032f9  movzx   ecx, word ptr [rdx]
0x1800032fc  mov     ebx, r13d
0x1800032ff  test    cx, cx
0x180003302  jz      loc_180003224
0x180003308  nop     dword ptr [rax+rax+00000000h]
0x180003310  and     ecx, 0FFDFh
0x180003316  imul    ebx, 65h ; 'e'
0x180003319  lea     rdi, [rdi+2]
0x18000331d  add     ebx, ecx
0x18000331f  movzx   ecx, word ptr [rdi]
0x180003322  test    cx, cx
0x180003325  jnz     short loc_180003310
0x180003327  jmp     loc_180003224
0x18000332c  lea     rax, [rbp+80h]
0x180003333  mov     ecx, 0FFFFFFFFh
0x180003338  cmp     rax, rcx
0x18000333b  ja      loc_1800033D8
0x180003341  cmp     eax, 208h
0x180003346  jbe     short loc_1800032DD
0x180003348  mov     ebx, eax
0x18000334a  call    cs:__imp_GetProcessHeap
0x180003350  mov     r8d, ebx; dwBytes
0x180003353  xor     edx, edx; dwFlags
0x180003355  mov     rcx, rax; hHeap
0x180003358  call    cs:__imp_HeapAlloc
0x18000335e  mov     rdx, rax
0x180003361  test    rax, rax
0x180003364  jz      short loc_1800033E2
0x180003366  mov     rcx, rax
0x180003369  mov     r8d, 4
0x18000336f  lea     rax, [rsp+2C8h+pbInput]
0x180003374  lea     rcx, [rcx+80h]
0x18000337b  movups  xmm0, xmmword ptr [rax]
0x18000337e  lea     rax, [rax+80h]
0x180003385  movups  xmmword ptr [rcx-80h], xmm0
0x180003389  movups  xmm1, xmmword ptr [rax-70h]
0x18000338d  movups  xmmword ptr [rcx-70h], xmm1
0x180003391  movups  xmm0, xmmword ptr [rax-60h]
0x180003395  movups  xmmword ptr [rcx-60h], xmm0
0x180003399  movups  xmm1, xmmword ptr [rax-50h]
0x18000339d  movups  xmmword ptr [rcx-50h], xmm1
0x1800033a1  movups  xmm0, xmmword ptr [rax-40h]
0x1800033a5  movups  xmmword ptr [rcx-40h], xmm0
0x1800033a9  movups  xmm1, xmmword ptr [rax-30h]
0x1800033ad  movups  xmmword ptr [rcx-30h], xmm1
0x1800033b1  movups  xmm0, xmmword ptr [rax-20h]
0x1800033b5  movups  xmmword ptr [rcx-20h], xmm0
0x1800033b9  movups  xmm1, xmmword ptr [rax-10h]
0x1800033bd  movups  xmmword ptr [rcx-10h], xmm1
0x1800033c1  sub     r8, 1
0x1800033c5  jnz     short loc_180003374
0x1800033c7  mov     rax, [rax]
0x1800033ca  mov     rsi, rdx
0x1800033cd  mov     [rcx], rax
0x1800033d0  mov     r14b, 1
0x1800033d3  jmp     loc_1800032DD
0x1800033d8  mov     eax, 80070216h
0x1800033dd  jmp     loc_180003248
0x1800033e2  mov     ecx, 8; dwErrCode
0x1800033e7  call    cs:__imp_SetLastError
0x1800033ed  call    cs:__imp_GetLastError
0x1800033f3  test    eax, eax
0x1800033f5  jle     short loc_180003401
0x1800033f7  movzx   eax, ax
0x1800033fa  or      eax, 80070000h
0x1800033ff  test    eax, eax
0x180003401  js      loc_180003248
0x180003407  mov     ecx, r13d
0x18000340a  mov     [rsp+2C8h+phAlgorithm], r13
0x18000340f  xorps   xmm0, xmm0
0x180003412  mov     [rsp+2C8h+phHash], r13
0x180003417  movups  xmmword ptr [rsp+2C8h+pbOutput], xmm0
0x18000341c  movups  [rsp+2C8h+var_268], xmm0
0x180003421  test    rsi, rsi
0x180003424  jz      loc_18000350B
0x18000342a  lea     ebx, [rcx+rcx]
0x18000342d  test    ebx, ebx
0x18000342f  jz      loc_18000350B
0x180003435  xor     r9d, r9d; dwFlags
0x180003438  lea     rdx, pszAlgId; "SHA256"
0x18000343f  xor     r8d, r8d; pszImplementation
0x180003442  lea     rcx, [rsp+2C8h+phAlgorithm]; phAlgorithm
0x180003447  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000344d  mov     ebp, eax
0x18000344f  test    eax, eax
0x180003451  js      short loc_1800034B3
0x180003453  mov     rcx, [rsp+2C8h+phAlgorithm]; hAlgorithm
0x180003458  lea     rdx, [rsp+2C8h+phHash]; phHash
0x18000345d  mov     [rsp+2C8h+dwFlags], r13d; dwFlags
0x180003462  xor     r9d, r9d; cbHashObject
0x180003465  mov     [rsp+2C8h+cbSecret], r13d; cbSecret
0x18000346a  xor     r8d, r8d; pbHashObject
0x18000346d  mov     [rsp+2C8h+pbSecret], r13; pbSecret
0x180003472  call    cs:__imp_BCryptCreateHash
0x180003478  mov     ebp, eax
0x18000347a  test    eax, eax
0x18000347c  js      short loc_1800034B3
0x18000347e  mov     rcx, [rsp+2C8h+phHash]; hHash
0x180003483  xor     r9d, r9d; dwFlags
0x180003486  mov     r8d, ebx; cbInput
0x180003489  mov     rdx, rsi; pbInput
0x18000348c  call    cs:__imp_BCryptHashData
0x180003492  mov     ebp, eax
0x180003494  test    eax, eax
0x180003496  js      short loc_1800034B3
0x180003498  mov     rcx, [rsp+2C8h+phHash]; hHash
0x18000349d  lea     rdx, [rsp+2C8h+pbOutput]; pbOutput
0x1800034a2  xor     r9d, r9d; dwFlags
0x1800034a5  mov     r8d, 20h ; ' '; cbOutput
0x1800034ab  call    cs:__imp_BCryptFinishHash
0x1800034b1  mov     ebp, eax
0x1800034b3  mov     rcx, [rsp+2C8h+phAlgorithm]; hAlgorithm
0x1800034b8  test    rcx, rcx
0x1800034bb  jz      short loc_1800034C5
0x1800034bd  xor     edx, edx; dwFlags
0x1800034bf  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800034c5  mov     rcx, [rsp+2C8h+phHash]; hHash
0x1800034ca  test    rcx, rcx
0x1800034cd  jz      short loc_1800034D5
0x1800034cf  call    cs:__imp_BCryptDestroyHash
0x1800034d5  or      ebp, 10000000h
0x1800034db  jl      short loc_180003510
0x1800034dd  lea     rcx, [rsp+2C8h+pbOutput]; void *
0x1800034e2  call    ?HashBlob@@YAKPEBX_KK@Z; HashBlob(void const *,unsigned __int64,ulong)
0x1800034e7  mov     ebx, eax
0x1800034e9  test    r14b, r14b
0x1800034ec  jz      loc_180003224
0x1800034f2  call    cs:__imp_GetProcessHeap
0x1800034f8  mov     r8, rsi; lpMem
0x1800034fb  xor     edx, edx; dwFlags
0x1800034fd  mov     rcx, rax; hHeap
0x180003500  call    cs:__imp_HeapFree
0x180003506  jmp     loc_180003224
0x18000350b  mov     ebp, 0D000000Dh
0x180003510  test    r14b, r14b
0x180003513  jz      loc_180003246
0x180003519  call    cs:__imp_GetProcessHeap
0x18000351f  mov     r8, rsi; lpMem
0x180003522  xor     edx, edx; dwFlags
0x180003524  mov     rcx, rax; hHeap
0x180003527  call    cs:__imp_HeapFree
0x18000352d  jmp     loc_180003246
0x180003532  mov     eax, 80070057h
0x180003537  jmp     loc_180003278
```
