# TREE_HASH_TABLE::DeletePath(ushort const *)

- ea: `0x180002680`
- end: `0x180002a88`
- name: `?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z`
- size: `1032`
- prototype: `void __fastcall(TREE_HASH_TABLE *__hidden this, const unsigned __int16 *Src)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002470`
- `0x180002680`
- `0x180002a90`
- `0x180002b60`
- `0x180003550`
- `0x180007180`
- `0x18002c476`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800027d3`
- `msvcrt!_wcsicmp` at `0x1800027d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002865`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800029c0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800029c0`
- `bcrypt!BCryptCreateHash` at `0x1800029eb`
- `bcrypt!BCryptCreateHash` at `0x1800029eb`
- `bcrypt!BCryptFinishHash` at `0x180002a23`
- `bcrypt!BCryptFinishHash` at `0x180002a23`
- `bcrypt!BCryptHashData` at `0x180002a05`
- `bcrypt!BCryptHashData` at `0x180002a05`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002a37`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002a37`
- `bcrypt!BCryptDestroyHash` at `0x180002a47`
- `bcrypt!BCryptDestroyHash` at `0x180002a47`

## pseudocode

```c
void __fastcall TREE_HASH_TABLE::DeletePath(TREE_HASH_TABLE *this, const unsigned __int16 *Src)
{
  const unsigned __int16 *v2; // r12
  unsigned __int16 v4; // ax
  int i; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // esi
  signed __int32 v8; // edx
  __int64 v9; // rdx
  __int64 v10; // rax
  struct TREE_HASH_NODE *v11; // rbx
  struct TREE_HASH_NODE **v12; // rdi
  const wchar_t *v13; // rcx
  signed __int64 v14; // r8
  int v15; // edx
  int v16; // eax
  signed __int32 v17; // edx
  UCHAR *v18; // rdi
  __int64 v19; // rax
  __int64 v21; // rbx
  unsigned int v22; // eax
  unsigned __int16 v23; // cx
  signed int LastError; // eax
  bool v25; // sf
  ULONG v26; // esi
  unsigned __int64 v27; // rdx
  NTSTATUS v28; // ebx
  unsigned int v29; // r8d
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v32[24]; // [rsp+58h] [rbp-B0h] BYREF
  UCHAR *v33; // [rsp+78h] [rbp-90h]
  int v34; // [rsp+80h] [rbp-88h]
  __int16 v35; // [rsp+84h] [rbp-84h]
  unsigned int v36; // [rsp+88h] [rbp-80h]
  UCHAR pbOutput[16]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-68h]
  UCHAR pbInput[2]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v40[526]; // [rsp+BAh] [rbp-4Eh] BYREF

  if ( !Src )
    return;
  v2 = Src;
  if ( *((_DWORD *)this + 6) )
  {
    if ( !*((_DWORD *)this + 7) )
    {
      v4 = *Src;
      i = 0;
      if ( *Src )
      {
        v6 = Src;
        do
        {
          ++v6;
          i = v4 + 101 * i;
          v4 = *v6;
        }
        while ( *v6 );
      }
      goto LABEL_7;
    }
    memset_0(v40, 0, 0x206u);
    v34 = 520;
    v18 = pbInput;
    v36 = 0;
    *(_WORD *)pbInput = 0;
    v19 = -1;
    v33 = pbInput;
    v35 = 256;
    while ( v2[++v19] != 0 )
      ;
    v21 = (unsigned int)(2 * v19);
    if ( (unsigned __int64)(v21 + 2) > 0x208 )
    {
      if ( (unsigned __int64)(v21 + 128) > 0xFFFFFFFF )
        goto LABEL_58;
      if ( !BUFFER::Resize((BUFFER *)v32, v21 + 128) )
      {
        LastError = GetLastError();
        v25 = LastError < 0;
        if ( LastError > 0 )
          v25 = 1;
        if ( v25 )
          goto LABEL_58;
        v22 = v36;
        v18 = v33;
        goto LABEL_46;
      }
      v18 = v33;
    }
    memcpy_0(v18, v2, (unsigned int)v21);
    v22 = (unsigned int)v21 >> 1;
    v36 = v22;
    *(_WORD *)&v18[2 * v22] = 0;
LABEL_46:
    phAlgorithm = 0;
    phHash = 0;
    *(_OWORD *)pbOutput = 0;
    v38 = 0;
    if ( v18 )
    {
      v26 = 2 * v22;
      if ( 2 * v22 )
      {
        v28 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
        if ( v28 >= 0 )
        {
          v28 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
          if ( v28 >= 0 )
          {
            v28 = BCryptHashData(phHash, v18, v26, 0);
            if ( v28 >= 0 )
              v28 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
          }
        }
        if ( phAlgorithm )
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        if ( phHash )
          BCryptDestroyHash(phHash);
        if ( v28 >= 0 )
        {
          i = HashBlob(pbOutput, v27, v29);
          BUFFER::~BUFFER((BUFFER *)v32);
          goto LABEL_7;
        }
      }
    }
LABEL_58:
    BUFFER::~BUFFER((BUFFER *)v32);
    return;
  }
  v23 = *Src;
  for ( i = 0; *Src; v23 = *Src )
  {
    ++Src;
    i = (v23 & 0xFFDF) + 101 * i;
  }
LABEL_7:
  v7 = (69069 * i + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * i + 12345) >> 16);
  if ( *((_DWORD *)this + 9)
    || (v8 = *((_DWORD *)this + 8), (_WORD)v8)
    || v8 != _InterlockedCompareExchange((volatile signed __int32 *)this + 8, (v8 + 0x10000) | 0xFFFF, v8) )
  {
    if ( (*((_DWORD *)this + 9) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)this + 9);
    else
      CReaderWriterLock3::_WriteLockSpin((TREE_HASH_TABLE *)((char *)this + 32));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 9, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  v9 = v7 % *((_DWORD *)this + 4);
  v10 = *((_QWORD *)this + 1);
  v11 = *(struct TREE_HASH_NODE **)(v10 + 8 * v9);
  v12 = (struct TREE_HASH_NODE **)(v10 + 8LL * (unsigned int)v9);
  while ( v11 )
  {
    if ( *((_DWORD *)v11 + 12) == v7 )
    {
      v13 = (const wchar_t *)*((_QWORD *)v11 + 5);
      if ( *((_DWORD *)this + 6) )
      {
        v14 = (char *)v2 - (char *)v13;
        do
        {
          v15 = *(const wchar_t *)((char *)v13 + v14);
          v16 = *v13 - v15;
          if ( v16 )
            break;
          ++v13;
        }
        while ( v15 );
        if ( !v16 )
        {
LABEL_22:
          TREE_HASH_TABLE::DeleteNodeInternal(this, v12, v11);
          break;
        }
      }
      else if ( !_wcsicmp(v13, v2) )
      {
        goto LABEL_22;
      }
    }
    else if ( *((_DWORD *)v11 + 12) > v7 )
    {
      break;
    }
    v12 = (struct TREE_HASH_NODE **)v11;
    v11 = *(struct TREE_HASH_NODE **)v11;
  }
  if ( ((*((_BYTE *)this + 36) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)this + 9, *((_DWORD *)this + 9) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 9, 0);
    while ( 1 )
    {
      v17 = *((_DWORD *)this + 8);
      if ( v17 == _InterlockedCompareExchange((volatile signed __int32 *)this + 8, (v17 - 0x10000) & 0xFFFF0000, v17) )
        break;
      _mm_pause();
    }
  }
}

```

## disassembly

```asm
0x180002680  test    rdx, rdx
0x180002683  jz      locret_18000283C
0x180002689  mov     r11, rsp
0x18000268c  push    rbp
0x18000268d  push    r12
0x18000268f  push    r15
0x180002691  lea     rbp, [r11-208h]
0x180002698  sub     rsp, 2F0h
0x18000269f  mov     rax, cs:__security_cookie
0x1800026a6  xor     rax, rsp
0x1800026a9  mov     [rbp+200h+var_40], rax
0x1800026b0  cmp     dword ptr [rcx+18h], 0
0x1800026b4  mov     r12, rdx
0x1800026b7  mov     [r11+18h], rbx
0x1800026bb  mov     r15, rcx
0x1800026be  mov     [r11-20h], rsi
0x1800026c2  mov     [r11-28h], rdi
0x1800026c6  mov     [r11-30h], r13
0x1800026ca  jz      loc_180002906
0x1800026d0  cmp     dword ptr [rcx+1Ch], 0
0x1800026d4  jnz     loc_18000287A
0x1800026da  movzx   eax, word ptr [rdx]
0x1800026dd  xor     r13d, r13d
0x1800026e0  mov     ebx, r13d
0x1800026e3  test    ax, ax
0x1800026e6  jz      short loc_180002704
0x1800026e8  mov     rcx, rdx
0x1800026eb  nop     dword ptr [rax+rax+00h]
0x1800026f0  imul    ebx, 65h ; 'e'
0x1800026f3  lea     rcx, [rcx+2]
0x1800026f7  movzx   eax, ax
0x1800026fa  add     ebx, eax
0x1800026fc  movzx   eax, word ptr [rcx]
0x1800026ff  test    ax, ax
0x180002702  jnz     short loc_1800026F0
0x180002704  imul    esi, ebx, 41C64E6Dh
0x18000270a  imul    eax, ebx, 10DCDh
0x180002710  mov     [rsp+300h+var_30], r14
0x180002718  add     esi, 3039h
0x18000271e  inc     eax
0x180002720  shr     esi, 10h
0x180002723  and     eax, 0FFFF0000h
0x180002728  or      esi, eax
0x18000272a  mov     eax, [r15+24h]
0x18000272e  test    eax, eax
0x180002730  jnz     short loc_180002757
0x180002732  mov     edx, [r15+20h]
0x180002736  test    dx, dx
0x180002739  jnz     short loc_180002757
0x18000273b  lea     ecx, [rdx+10000h]
0x180002741  mov     eax, edx
0x180002743  or      ecx, 0FFFFh
0x180002749  lock cmpxchg [r15+20h], ecx
0x18000274f  cmp     edx, eax
0x180002751  jz      loc_180002865
0x180002757  call    cs:__imp_GetCurrentThreadId
0x18000275d  mov     ecx, [r15+24h]
0x180002761  and     eax, 0FFFFFFFCh
0x180002764  and     ecx, 0FFFFFFFCh
0x180002767  cmp     ecx, eax
0x180002769  jz      loc_1800028FC
0x18000276f  lea     rcx, [r15+20h]; this
0x180002773  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180002778  xor     edx, edx
0x18000277a  mov     eax, esi
0x18000277c  div     dword ptr [r15+10h]
0x180002780  mov     rax, [r15+8]
0x180002784  mov     rbx, [rax+rdx*8]
0x180002788  lea     rdi, [rax+rdx*8]
0x18000278c  nop     dword ptr [rax+00h]
0x180002790  test    rbx, rbx
0x180002793  jz      short loc_1800027EB
0x180002795  cmp     [rbx+30h], esi
0x180002798  jnz     loc_18000283D
0x18000279e  cmp     dword ptr [r15+18h], 0
0x1800027a3  mov     rcx, [rbx+28h]; String1
0x1800027a7  jz      short loc_1800027D0
0x1800027a9  mov     r8, r12
0x1800027ac  sub     r8, rcx
0x1800027af  nop
0x1800027b0  movzx   eax, word ptr [rcx]
0x1800027b3  movzx   edx, word ptr [rcx+r8]
0x1800027b8  sub     eax, edx
0x1800027ba  jnz     short loc_1800027C4
0x1800027bc  add     rcx, 2
0x1800027c0  test    edx, edx
0x1800027c2  jnz     short loc_1800027B0
0x1800027c4  test    eax, eax
0x1800027c6  jz      short loc_1800027DD
0x1800027c8  mov     rdi, rbx
0x1800027cb  mov     rbx, [rbx]
0x1800027ce  jmp     short loc_180002790
0x1800027d0  mov     rdx, r12; String2
0x1800027d3  call    cs:__imp__wcsicmp
0x1800027d9  test    eax, eax
0x1800027db  jnz     short loc_1800027C8
0x1800027dd  mov     r8, rbx; struct TREE_HASH_NODE *
0x1800027e0  mov     rdx, rdi; struct TREE_HASH_NODE **
0x1800027e3  mov     rcx, r15; this
0x1800027e6  call    ?DeleteNodeInternal@TREE_HASH_TABLE@@AEAAXPEAPEAUTREE_HASH_NODE@@PEAU2@@Z; TREE_HASH_TABLE::DeleteNodeInternal(TREE_HASH_NODE * *,TREE_HASH_NODE *)
0x1800027eb  mov     eax, [r15+24h]
0x1800027ef  dec     eax
0x1800027f1  test    al, 3
0x1800027f3  jz      short loc_180002841
0x1800027f5  xchg    eax, [r15+24h]
0x1800027f9  mov     r14, [rsp+300h+var_30]
0x180002801  mov     rdi, [rsp+300h+var_20]
0x180002809  mov     rsi, [rsp+2E8h]
0x180002811  mov     rbx, [rsp+300h+arg_10]
0x180002819  mov     r13, [rsp+300h+var_28]
0x180002821  mov     rcx, [rbp+200h+var_40]
0x180002828  xor     rcx, rsp; StackCookie
0x18000282b  call    __security_check_cookie
0x180002830  add     rsp, 2F0h
0x180002837  pop     r15
0x180002839  pop     r12
0x18000283b  pop     rbp
0x18000283c  retn
0x18000283d  jbe     short loc_1800027C8
0x18000283f  jmp     short loc_1800027EB
0x180002841  xchg    r13d, [r15+24h]
0x180002845  mov     edx, [r15+20h]
0x180002849  mov     eax, edx
0x18000284b  lea     ecx, [rdx-10000h]
0x180002851  and     ecx, 0FFFF0000h
0x180002857  lock cmpxchg [r15+20h], ecx
0x18000285d  cmp     edx, eax
0x18000285f  jz      short loc_1800027F9
0x180002861  pause
0x180002863  jmp     short loc_180002845
0x180002865  call    cs:__imp_GetCurrentThreadId
0x18000286b  and     eax, 0FFFFFFFCh
0x18000286e  or      eax, 1
0x180002871  xchg    eax, [r15+24h]
0x180002875  jmp     loc_180002778
0x18000287a  xor     edx, edx; Val
0x18000287c  lea     rcx, [rbp+200h+var_24E]; void *
0x180002880  mov     r8d, 206h; Size
0x180002886  call    memset_0
0x18000288b  xor     r13d, r13d
0x18000288e  mov     [rsp+300h+var_288], 208h
0x180002896  lea     rdi, [rbp+200h+pbInput]
0x18000289a  mov     [rbp+200h+var_280], r13d
0x18000289e  mov     word ptr [rbp+200h+pbInput], r13w
0x1800028a3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800028aa  mov     qword ptr [rsp+300h+var_290], rdi
0x1800028af  mov     [rsp+300h+var_284], 100h
0x1800028b6  nop     word ptr [rax+rax+00000000h]
0x1800028c0  cmp     [r12+rax*2+2], r13w
0x1800028c6  lea     rax, [rax+1]
0x1800028ca  jnz     short loc_1800028C0
0x1800028cc  lea     ebx, [rax+rax]
0x1800028cf  lea     rax, [rbx+2]
0x1800028d3  mov     esi, ebx
0x1800028d5  cmp     rax, 208h
0x1800028db  ja      short loc_18000293C
0x1800028dd  mov     r8, rsi; Size
0x1800028e0  mov     rdx, r12; Src
0x1800028e3  mov     rcx, rdi; void *
0x1800028e6  call    memcpy_0
0x1800028eb  shr     ebx, 1
0x1800028ed  mov     eax, ebx
0x1800028ef  mov     [rbp+200h+var_280], eax
0x1800028f2  mov     [rdi+rbx*2], r13w
0x1800028f7  jmp     loc_180002985
0x1800028fc  lock inc dword ptr [r15+24h]
0x180002901  jmp     loc_180002778
0x180002906  movzx   ecx, word ptr [rdx]
0x180002909  xor     r13d, r13d
0x18000290c  mov     ebx, r13d
0x18000290f  test    cx, cx
0x180002912  jz      loc_180002704
0x180002918  nop     dword ptr [rax+rax+00000000h]
0x180002920  and     ecx, 0FFDFh
0x180002926  imul    ebx, 65h ; 'e'
0x180002929  lea     rdx, [rdx+2]
0x18000292d  add     ebx, ecx
0x18000292f  movzx   ecx, word ptr [rdx]
0x180002932  test    cx, cx
0x180002935  jnz     short loc_180002920
0x180002937  jmp     loc_180002704
0x18000293c  lea     rdx, [rbx+80h]; unsigned int
0x180002943  mov     eax, 0FFFFFFFFh
0x180002948  cmp     rdx, rax
0x18000294b  ja      loc_180002A6F
0x180002951  lea     rcx, [rsp+300h+var_2B0]; this
0x180002956  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000295b  test    al, al
0x18000295d  jnz     loc_180002A7E
0x180002963  call    cs:__imp_GetLastError
0x180002969  test    eax, eax
0x18000296b  jle     short loc_180002977
0x18000296d  movzx   eax, ax
0x180002970  or      eax, 80070000h
0x180002975  test    eax, eax
0x180002977  js      loc_180002A6F
0x18000297d  mov     eax, [rbp+200h+var_280]
0x180002980  mov     rdi, qword ptr [rsp+300h+var_290]
0x180002985  mov     [rsp+300h+phAlgorithm], r13
0x18000298a  xorps   xmm0, xmm0
0x18000298d  mov     [rsp+300h+phHash], r13
0x180002992  movups  xmmword ptr [rbp+200h+pbOutput], xmm0
0x180002996  movups  [rbp+200h+var_268], xmm0
0x18000299a  test    rdi, rdi
0x18000299d  jz      loc_180002A6F
0x1800029a3  lea     esi, [rax+rax]
0x1800029a6  test    esi, esi
0x1800029a8  jz      loc_180002A6F
0x1800029ae  xor     r9d, r9d; dwFlags
0x1800029b1  lea     rdx, pszAlgId; "SHA256"
0x1800029b8  xor     r8d, r8d; pszImplementation
0x1800029bb  lea     rcx, [rsp+300h+phAlgorithm]; phAlgorithm
0x1800029c0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800029c6  mov     ebx, eax
0x1800029c8  test    eax, eax
0x1800029ca  js      short loc_180002A2B
0x1800029cc  mov     rcx, [rsp+300h+phAlgorithm]; hAlgorithm
0x1800029d1  lea     rdx, [rsp+300h+phHash]; phHash
0x1800029d6  mov     [rsp+30h], r13d; dwFlags
0x1800029db  xor     r9d, r9d; cbHashObject
0x1800029de  mov     [rsp+300h+cbSecret], r13d; cbSecret
0x1800029e3  xor     r8d, r8d; pbHashObject
0x1800029e6  mov     [rsp+300h+pbSecret], r13; pbSecret
0x1800029eb  call    cs:__imp_BCryptCreateHash
0x1800029f1  mov     ebx, eax
0x1800029f3  test    eax, eax
0x1800029f5  js      short loc_180002A2B
0x1800029f7  mov     rcx, [rsp+300h+phHash]; hHash
0x1800029fc  xor     r9d, r9d; dwFlags
0x1800029ff  mov     r8d, esi; cbInput
0x180002a02  mov     rdx, rdi; pbInput
0x180002a05  call    cs:__imp_BCryptHashData
0x180002a0b  mov     ebx, eax
0x180002a0d  test    eax, eax
0x180002a0f  js      short loc_180002A2B
0x180002a11  mov     rcx, [rsp+300h+phHash]; hHash
0x180002a16  lea     rdx, [rbp+200h+pbOutput]; pbOutput
0x180002a1a  xor     r9d, r9d; dwFlags
0x180002a1d  mov     r8d, 20h ; ' '; cbOutput
0x180002a23  call    cs:__imp_BCryptFinishHash
0x180002a29  mov     ebx, eax
0x180002a2b  mov     rcx, [rsp+300h+phAlgorithm]; hAlgorithm
0x180002a30  test    rcx, rcx
0x180002a33  jz      short loc_180002A3D
0x180002a35  xor     edx, edx; dwFlags
0x180002a37  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002a3d  mov     rcx, [rsp+300h+phHash]; hHash
0x180002a42  test    rcx, rcx
0x180002a45  jz      short loc_180002A4D
0x180002a47  call    cs:__imp_BCryptDestroyHash
0x180002a4d  or      ebx, 10000000h
0x180002a53  jl      short loc_180002A6F
0x180002a55  lea     rcx, [rbp+200h+pbOutput]; void *
0x180002a59  call    ?HashBlob@@YAKPEBX_KK@Z; HashBlob(void const *,unsigned __int64,ulong)
0x180002a5e  lea     rcx, [rsp+300h+var_2B0]; this
0x180002a63  mov     ebx, eax
0x180002a65  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002a6a  jmp     loc_180002704
0x180002a6f  lea     rcx, [rsp+300h+var_2B0]; this
0x180002a74  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002a79  jmp     loc_180002801
0x180002a7e  mov     rdi, qword ptr [rsp+300h+var_290]
0x180002a83  jmp     loc_1800028DD
```
