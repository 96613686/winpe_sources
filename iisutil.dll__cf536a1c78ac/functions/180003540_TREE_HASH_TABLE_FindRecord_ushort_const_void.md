# TREE_HASH_TABLE::FindRecord(ushort const *,void * *)

- ea: `0x180003540`
- end: `0x180003b2b`
- name: `?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z`
- size: `1515`
- prototype: `void(TREE_HASH_TABLE *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800034f0`
- `0x180003540`
- `0x180003b40`
- `0x180003fb0`
- `0x18002e516`
- `0x18002e52e`
- `0x18002e560`
- `0x18002f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003710`
- `msvcrt!_wcsicmp` at `0x180003710`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003627`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800037b9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800037b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003922`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000390e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000390e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003a31`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003a31`
- `bcrypt!BCryptCreateHash` at `0x180003a62`
- `bcrypt!BCryptCreateHash` at `0x180003a62`
- `bcrypt!BCryptFinishHash` at `0x180003aa6`
- `bcrypt!BCryptFinishHash` at `0x180003aa6`
- `bcrypt!BCryptHashData` at `0x180003a82`
- `bcrypt!BCryptHashData` at `0x180003a82`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180003ac0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180003ac0`
- `bcrypt!BCryptDestroyHash` at `0x180003ad6`
- `bcrypt!BCryptDestroyHash` at `0x180003ad6`

## pseudocode

```c
void __fastcall TREE_HASH_TABLE::FindRecord(TREE_HASH_TABLE *this, unsigned __int16 *a2, void **a3)
{
  void **v3; // r12
  const wchar_t *v4; // r13
  TREE_HASH_TABLE *v5; // r15
  unsigned __int16 v6; // ax
  int i; // ebx
  unsigned __int16 *v8; // rcx
  signed __int32 v9; // edx
  unsigned int v10; // r14d
  DWORD v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // rsi
  unsigned __int16 v14; // r8
  int v15; // ebx
  int v16; // edx
  signed __int32 v17; // r8d
  __int64 *j; // rbx
  const wchar_t *v19; // rcx
  signed __int64 v20; // r8
  int v21; // edx
  int v22; // eax
  signed __int32 v23; // edx
  __int64 v24; // rsi
  char v25; // r14
  UCHAR *v26; // rdi
  __int64 v27; // rax
  __int64 v29; // r15
  UCHAR *v30; // rbx
  __int16 v31; // cx
  unsigned int v32; // r12d
  HANDLE ProcessHeap; // rax
  UCHAR *v34; // rax
  UCHAR *v35; // rcx
  __int64 v36; // rdx
  UCHAR *v37; // rax
  __int128 v38; // xmm0
  signed int LastError; // eax
  bool v40; // sf
  ULONG v41; // esi
  unsigned __int64 v42; // rdx
  NTSTATUS v43; // ebx
  unsigned int v44; // r8d
  void *Src; // [rsp+48h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-B8h] BYREF
  void **v47; // [rsp+58h] [rbp-B0h]
  TREE_HASH_TABLE *v48; // [rsp+60h] [rbp-A8h]
  _BYTE v49[32]; // [rsp+68h] [rbp-A0h] BYREF
  UCHAR *v50; // [rsp+88h] [rbp-80h]
  int v51; // [rsp+90h] [rbp-78h]
  __int16 v52; // [rsp+94h] [rbp-74h]
  unsigned int v53; // [rsp+98h] [rbp-70h]
  UCHAR pbOutput[16]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v55; // [rsp+B0h] [rbp-58h]
  UCHAR pbInput[2]; // [rsp+C8h] [rbp-40h] BYREF
  char v57[526]; // [rsp+CAh] [rbp-3Eh] BYREF

  v47 = a3;
  v3 = a3;
  Src = a2;
  v4 = a2;
  v48 = this;
  v5 = this;
  *a3 = 0;
  if ( !a2 )
    return;
  if ( !*((_DWORD *)this + 6) )
  {
    v31 = *a2;
    for ( i = 0; *a2; v31 = *a2 )
    {
      ++a2;
      i = (v31 & 0xFFDF) + 101 * i;
    }
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 7) )
  {
    v6 = *a2;
    i = 0;
    if ( *a2 )
    {
      v8 = a2;
      do
      {
        ++v8;
        i = v6 + 101 * i;
        v6 = *v8;
      }
      while ( *v8 );
    }
    goto LABEL_7;
  }
  memset_0(v57, 0, 0x206u);
  LODWORD(v24) = 0;
  v51 = 520;
  v25 = 0;
  v52 = 256;
  v53 = 0;
  v26 = pbInput;
  *(_WORD *)pbInput = 0;
  v27 = -1;
  v50 = pbInput;
  while ( v4[++v27] != 0 )
    ;
  v29 = (unsigned int)(2 * v27);
  if ( (unsigned __int64)(v29 + 2) <= 0x208 )
    goto LABEL_47;
  v32 = v29 + 128;
  if ( (unsigned __int64)(v29 + 128) > 0xFFFFFFFF )
  {
LABEL_33:
    BUFFER::~BUFFER((BUFFER *)v49);
    return;
  }
  if ( v32 > 0x208 )
  {
    ProcessHeap = GetProcessHeap();
    v34 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v32);
    v30 = v34;
    if ( v34 )
    {
      v35 = v34;
      v36 = 4;
      v37 = pbInput;
      do
      {
        v35 += 128;
        v38 = *(_OWORD *)v37;
        v37 += 128;
        *((_OWORD *)v35 - 8) = v38;
        *((_OWORD *)v35 - 7) = *((_OWORD *)v37 - 7);
        *((_OWORD *)v35 - 6) = *((_OWORD *)v37 - 6);
        *((_OWORD *)v35 - 5) = *((_OWORD *)v37 - 5);
        *((_OWORD *)v35 - 4) = *((_OWORD *)v37 - 4);
        *((_OWORD *)v35 - 3) = *((_OWORD *)v37 - 3);
        *((_OWORD *)v35 - 2) = *((_OWORD *)v37 - 2);
        *((_OWORD *)v35 - 1) = *((_OWORD *)v37 - 1);
        --v36;
      }
      while ( v36 );
      v25 = 1;
      *(_QWORD *)v35 = *(_QWORD *)v37;
      v26 = v30;
      LOBYTE(v52) = 1;
      v50 = v30;
      v51 = v29 + 128;
      goto LABEL_48;
    }
    SetLastError(8u);
    LastError = GetLastError();
    v40 = LastError < 0;
    if ( LastError > 0 )
      v40 = 1;
    if ( !v40 )
    {
      v4 = (const wchar_t *)Src;
      goto LABEL_65;
    }
    goto LABEL_33;
  }
LABEL_47:
  v30 = pbInput;
LABEL_48:
  v4 = (const wchar_t *)Src;
  memcpy_0(v30, Src, (unsigned int)v29);
  v24 = (unsigned int)v29 >> 1;
  v53 = (unsigned int)v29 >> 1;
  *(_WORD *)&v30[2 * v24] = 0;
LABEL_65:
  Src = 0;
  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v55 = 0;
  if ( !v26 )
    goto LABEL_79;
  v41 = 2 * v24;
  if ( !v41 )
    goto LABEL_79;
  v43 = BCryptOpenAlgorithmProvider(&Src, L"SHA256", 0, 0);
  if ( v43 >= 0 )
  {
    v43 = BCryptCreateHash(Src, &phHash, 0, 0, 0, 0, 0);
    if ( v43 >= 0 )
    {
      v43 = BCryptHashData(phHash, v26, v41, 0);
      if ( v43 >= 0 )
        v43 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
    }
  }
  if ( Src )
    BCryptCloseAlgorithmProvider(Src, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v43 < 0 )
  {
LABEL_79:
    if ( v25 )
      BUFFER::FreeMemoryInternal((BUFFER *)v49);
    return;
  }
  i = HashBlob(pbOutput, v42, v44);
  if ( v25 )
    BUFFER::FreeMemoryInternal((BUFFER *)v49);
  v3 = v47;
  v5 = v48;
LABEL_7:
  v9 = *((_DWORD *)v5 + 8);
  v10 = (69069 * i + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * i + 12345) >> 16);
  if ( (v9 & 0xFFFF8000) != 0 || v9 != _InterlockedCompareExchange((volatile signed __int32 *)v5 + 8, v9 + 1, v9) )
  {
    v11 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v13 = 0;
    v14 = CReaderWriterLock3::sm_wDefaultSpinCount;
    v15 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
LABEL_10:
    v16 = v15;
    if ( g_cProcessors < 2 || !v14 )
      v16 = 1;
    while ( 1 )
    {
      if ( --v16 < 0 )
      {
        if ( v11 || !g_pfnSwitchToThread() )
          Sleep(v11);
        if ( (unsigned int)v13 < 4 )
          v11 = dword_180032D40[v13];
        else
          v11 = 100;
        v15 = (int)((double)v15 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
        if ( v15 > 10000 )
        {
          v14 = CReaderWriterLock3::sm_wDefaultSpinCount;
          v15 = 10000;
          v13 = (unsigned int)(v13 + 1);
        }
        else
        {
          if ( v15 <= 100 )
            v15 = 100;
          v14 = CReaderWriterLock3::sm_wDefaultSpinCount;
          v13 = (unsigned int)(v13 + 1);
        }
        goto LABEL_10;
      }
      v17 = *((_DWORD *)v5 + 8);
      if ( (v17 & 0xFFFF8000) == 0
        && v17 == _InterlockedCompareExchange((volatile signed __int32 *)v5 + 8, v17 + 1, v17) )
      {
        break;
      }
      _mm_pause();
    }
    v3 = v47;
  }
  for ( j = *(__int64 **)(*((_QWORD *)v5 + 1) + 8LL * (v10 % *((_DWORD *)v5 + 4))); j; j = (__int64 *)*j )
  {
    if ( *((_DWORD *)j + 12) == v10 )
    {
      v19 = (const wchar_t *)j[5];
      if ( *((_DWORD *)v5 + 6) )
      {
        v20 = (char *)v4 - (char *)v19;
        do
        {
          v21 = *(const wchar_t *)((char *)v19 + v20);
          v22 = *v19 - v21;
          if ( v22 )
            break;
          ++v19;
        }
        while ( v21 );
        if ( !v22 )
        {
LABEL_27:
          if ( j[4] )
          {
            (**(void (__fastcall ***)(TREE_HASH_TABLE *))v5)(v5);
            *v3 = (void *)j[4];
          }
          break;
        }
      }
      else if ( !_wcsicmp(v19, v4) )
      {
        goto LABEL_27;
      }
    }
    else if ( *((_DWORD *)j + 12) > v10 )
    {
      break;
    }
  }
  while ( 1 )
  {
    v23 = *((_DWORD *)v5 + 8);
    if ( v23 == _InterlockedCompareExchange((volatile signed __int32 *)v5 + 8, v23 - 1, v23) )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180003540  mov     r11, rsp
0x180003543  push    rbp
0x180003544  push    r12
0x180003546  push    r13
0x180003548  push    r15
0x18000354a  lea     rbp, [r11-218h]
0x180003551  sub     rsp, 2F8h
0x180003558  mov     rax, cs:__security_cookie
0x18000355f  xor     rax, rsp
0x180003562  mov     [rbp+210h+var_40], rax
0x180003569  mov     [rsp+310h+var_2C0], r8
0x18000356e  mov     r12, r8
0x180003571  mov     [rsp+310h+Src], rdx
0x180003576  mov     r13, rdx
0x180003579  mov     [rsp+310h+var_2B8], rcx
0x18000357e  mov     r15, rcx
0x180003581  mov     qword ptr [r8], 0
0x180003588  test    rdx, rdx
0x18000358b  jz      loc_180003784
0x180003591  cmp     dword ptr [rcx+18h], 0
0x180003595  mov     [r11+20h], rbx
0x180003599  mov     [r11-28h], rsi
0x18000359d  mov     [r11-30h], rdi
0x1800035a1  mov     [r11-38h], r14
0x1800035a5  jz      loc_1800038BD
0x1800035ab  cmp     dword ptr [rcx+1Ch], 0
0x1800035af  jnz     loc_18000380C
0x1800035b5  movzx   eax, word ptr [rdx]
0x1800035b8  xor     ebx, ebx
0x1800035ba  test    ax, ax
0x1800035bd  jz      short loc_1800035E4
0x1800035bf  mov     rcx, rdx
0x1800035c2  nop     dword ptr [rax+00h]
0x1800035c6  nop     word ptr [rax+rax+00000000h]
0x1800035d0  imul    ebx, 65h ; 'e'
0x1800035d3  lea     rcx, [rcx+2]
0x1800035d7  movzx   eax, ax
0x1800035da  add     ebx, eax
0x1800035dc  movzx   eax, word ptr [rcx]
0x1800035df  test    ax, ax
0x1800035e2  jnz     short loc_1800035D0
0x1800035e4  mov     edx, [r15+20h]
0x1800035e8  imul    r14d, ebx, 41C64E6Dh
0x1800035ef  imul    eax, ebx, 10DCDh
0x1800035f5  add     r14d, 3039h
0x1800035fc  inc     eax
0x1800035fe  shr     r14d, 10h
0x180003602  and     eax, 0FFFF0000h
0x180003607  or      r14d, eax
0x18000360a  test    edx, 0FFFF8000h
0x180003610  jnz     short loc_180003625
0x180003612  lea     ecx, [rdx+1]
0x180003615  mov     eax, edx
0x180003617  lock cmpxchg [r15+20h], ecx
0x18000361d  cmp     edx, eax
0x18000361f  jz      loc_1800036C2
0x180003625  xor     edi, edi
0x180003627  call    cs:__imp_GetCurrentThreadId
0x18000362e  nop     dword ptr [rax+rax+00h]
0x180003633  mov     r8d, eax
0x180003636  lea     r12, __ImageBase
0x18000363d  mov     eax, 4EC4EC4Fh
0x180003642  mul     r8d
0x180003645  shr     edx, 2
0x180003648  imul    ecx, edx, 0Dh
0x18000364b  lea     rdx, __ImageBase
0x180003652  sub     r8d, ecx
0x180003655  mov     ecx, r8d
0x180003658  xor     esi, esi
0x18000365a  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180003662  movd    xmm0, r8d
0x180003667  cvtdq2pd xmm0, xmm0
0x18000366b  mulsd   xmm0, ds:rva qword_180032E80[rdx+rcx*8]
0x180003674  cvttsd2si ebx, xmm0
0x180003678  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18000367f  mov     edx, ebx
0x180003681  jb      loc_1800039B6
0x180003687  test    r8w, r8w
0x18000368b  jz      loc_1800039B6
0x180003691  sub     edx, 1
0x180003694  js      loc_1800037A3
0x18000369a  mov     r8d, [r15+20h]
0x18000369e  test    r8d, 0FFFF8000h
0x1800036a5  jnz     short loc_1800036B9
0x1800036a7  lea     ecx, [r8+1]
0x1800036ab  mov     eax, r8d
0x1800036ae  lock cmpxchg [r15+20h], ecx
0x1800036b4  cmp     r8d, eax
0x1800036b7  jz      short loc_1800036BD
0x1800036b9  pause
0x1800036bb  jmp     short loc_180003691
0x1800036bd  mov     r12, [rsp+310h+var_2C0]
0x1800036c2  xor     edx, edx
0x1800036c4  mov     eax, r14d
0x1800036c7  div     dword ptr [r15+10h]
0x1800036cb  mov     rax, [r15+8]
0x1800036cf  mov     rbx, [rax+rdx*8]
0x1800036d3  test    rbx, rbx
0x1800036d6  jz      short loc_18000373F
0x1800036d8  cmp     [rbx+30h], r14d
0x1800036dc  jnz     short loc_180003756
0x1800036de  cmp     dword ptr [r15+18h], 0
0x1800036e3  mov     rcx, [rbx+28h]; String1
0x1800036e7  jz      short loc_18000370D
0x1800036e9  mov     r8, r13
0x1800036ec  sub     r8, rcx
0x1800036ef  nop
0x1800036f0  movzx   eax, word ptr [rcx]
0x1800036f3  movzx   edx, word ptr [rcx+r8]
0x1800036f8  sub     eax, edx
0x1800036fa  jnz     short loc_180003704
0x1800036fc  add     rcx, 2
0x180003700  test    edx, edx
0x180003702  jnz     short loc_1800036F0
0x180003704  test    eax, eax
0x180003706  jz      short loc_180003720
0x180003708  mov     rbx, [rbx]
0x18000370b  jmp     short loc_1800036D3
0x18000370d  mov     rdx, r13; String2
0x180003710  call    cs:__imp__wcsicmp
0x180003717  nop     dword ptr [rax+rax+00h]
0x18000371c  test    eax, eax
0x18000371e  jnz     short loc_180003708
0x180003720  mov     rdx, [rbx+20h]
0x180003724  test    rdx, rdx
0x180003727  jz      short loc_18000373F
0x180003729  mov     rax, [r15]
0x18000372c  mov     rcx, r15
0x18000372f  mov     rax, [rax]
0x180003732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003737  mov     rax, [rbx+20h]
0x18000373b  mov     [r12], rax
0x18000373f  mov     edx, [r15+20h]
0x180003743  mov     eax, edx
0x180003745  lea     ecx, [rdx-1]
0x180003748  lock cmpxchg [r15+20h], ecx
0x18000374e  cmp     edx, eax
0x180003750  jz      short loc_180003764
0x180003752  pause
0x180003754  jmp     short loc_18000373F
0x180003756  jbe     short loc_180003708
0x180003758  jmp     short loc_18000373F
0x18000375a  lea     rcx, [rsp+310h+var_2B0]; this
0x18000375f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003764  mov     rdi, [rsp+310h+var_28]
0x18000376c  mov     rsi, [rsp+2F0h]
0x180003774  mov     rbx, [rsp+310h+arg_18]
0x18000377c  mov     r14, [rsp+310h+var_30]
0x180003784  mov     rcx, [rbp+210h+var_40]
0x18000378b  xor     rcx, rsp; StackCookie
0x18000378e  call    __security_check_cookie
0x180003793  add     rsp, 2F8h
0x18000379a  pop     r15
0x18000379c  pop     r13
0x18000379e  pop     r12
0x1800037a0  pop     rbp
0x1800037a1  retn
0x1800037a3  test    edi, edi
0x1800037a5  jnz     short loc_1800037B7
0x1800037a7  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x1800037ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b3  test    eax, eax
0x1800037b5  jnz     short loc_1800037C5
0x1800037b7  mov     ecx, edi; dwMilliseconds
0x1800037b9  call    cs:__imp_Sleep
0x1800037c0  nop     dword ptr [rax+rax+00h]
0x1800037c5  cmp     esi, 4
0x1800037c8  jb      loc_1800038B0
0x1800037ce  mov     edi, 64h ; 'd'
0x1800037d3  movd    xmm0, ebx
0x1800037d7  cvtdq2pd xmm0, xmm0
0x1800037db  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x1800037e3  cvttsd2si ebx, xmm0
0x1800037e7  cmp     ebx, 2710h
0x1800037ed  jg      loc_18000389C
0x1800037f3  cmp     ebx, 64h ; 'd'
0x1800037f6  jg      short loc_1800037FD
0x1800037f8  mov     ebx, 64h ; 'd'
0x1800037fd  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180003805  inc     esi
0x180003807  jmp     loc_180003678
0x18000380c  xor     edx, edx; Val
0x18000380e  lea     rcx, [rbp+210h+var_24E]; void *
0x180003812  mov     r8d, 206h; Size
0x180003818  call    memset_0
0x18000381d  xor     esi, esi
0x18000381f  mov     [rbp+210h+var_288], 208h
0x180003826  xor     r14b, r14b
0x180003829  mov     [rbp+210h+var_284], 100h
0x18000382f  xor     eax, eax
0x180003831  mov     [rbp+210h+var_280], esi
0x180003834  lea     rdi, [rbp+210h+pbInput]
0x180003838  mov     word ptr [rbp+210h+pbInput], ax
0x18000383c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003843  mov     [rbp+210h+var_290], rdi
0x180003847  nop     word ptr [rax+rax+00000000h]
0x180003850  cmp     [r13+rax*2+2], si
0x180003856  lea     rax, [rax+1]
0x18000385a  jnz     short loc_180003850
0x18000385c  lea     r15d, [rax+rax]
0x180003860  lea     rax, [r15+2]
0x180003864  mov     r13d, r15d
0x180003867  cmp     rax, 208h
0x18000386d  ja      short loc_1800038EC
0x18000386f  lea     rbx, [rbp+210h+pbInput]
0x180003873  mov     r8, r13; Size
0x180003876  mov     rcx, rbx; void *
0x180003879  mov     r13, [rsp+310h+Src]
0x18000387e  mov     rdx, r13; Src
0x180003881  call    memcpy_0
0x180003886  shr     r15d, 1
0x180003889  mov     esi, r15d
0x18000388c  xor     r15d, r15d
0x18000388f  mov     [rbp+210h+var_280], esi
0x180003892  mov     [rbx+rsi*2], r15w
0x180003897  jmp     loc_1800039F9
0x18000389c  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x1800038a4  mov     ebx, 2710h
0x1800038a9  inc     esi
0x1800038ab  jmp     loc_180003678
0x1800038b0  mov     edi, ds:rva dword_180032D40[r12+rsi*4]
0x1800038b8  jmp     loc_1800037D3
0x1800038bd  movzx   ecx, word ptr [rdx]
0x1800038c0  xor     ebx, ebx
0x1800038c2  test    cx, cx
0x1800038c5  jz      loc_1800035E4
0x1800038cb  nop     dword ptr [rax+rax+00h]
0x1800038d0  and     ecx, 0FFDFh
0x1800038d6  imul    ebx, 65h ; 'e'
0x1800038d9  lea     rdx, [rdx+2]
0x1800038dd  add     ebx, ecx
0x1800038df  movzx   ecx, word ptr [rdx]
0x1800038e2  test    cx, cx
0x1800038e5  jnz     short loc_1800038D0
0x1800038e7  jmp     loc_1800035E4
0x1800038ec  lea     r12, [r15+80h]
0x1800038f3  mov     eax, 0FFFFFFFFh
0x1800038f8  cmp     r12, rax
0x1800038fb  ja      loc_18000375A
0x180003901  cmp     r12d, 208h
0x180003908  jbe     loc_18000386F
0x18000390e  call    cs:__imp_GetProcessHeap
0x180003915  nop     dword ptr [rax+rax+00h]
0x18000391a  mov     r8d, r12d; dwBytes
0x18000391d  xor     edx, edx; dwFlags
0x18000391f  mov     rcx, rax; hHeap
0x180003922  call    cs:__imp_HeapAlloc
0x180003929  nop     dword ptr [rax+rax+00h]
0x18000392e  mov     rbx, rax
0x180003931  test    rax, rax
0x180003934  jz      loc_1800039C0
0x18000393a  mov     rcx, rax
0x18000393d  mov     edx, 4
0x180003942  lea     rax, [rbp+210h+pbInput]
0x180003946  lea     rcx, [rcx+80h]
0x18000394d  movups  xmm0, xmmword ptr [rax]
0x180003950  lea     rax, [rax+80h]
0x180003957  movups  xmmword ptr [rcx-80h], xmm0
0x18000395b  movups  xmm1, xmmword ptr [rax-70h]
0x18000395f  movups  xmmword ptr [rcx-70h], xmm1
0x180003963  movups  xmm0, xmmword ptr [rax-60h]
0x180003967  movups  xmmword ptr [rcx-60h], xmm0
0x18000396b  movups  xmm1, xmmword ptr [rax-50h]
0x18000396f  movups  xmmword ptr [rcx-50h], xmm1
0x180003973  movups  xmm0, xmmword ptr [rax-40h]
0x180003977  movups  xmmword ptr [rcx-40h], xmm0
0x18000397b  movups  xmm1, xmmword ptr [rax-30h]
0x18000397f  movups  xmmword ptr [rcx-30h], xmm1
0x180003983  movups  xmm0, xmmword ptr [rax-20h]
0x180003987  movups  xmmword ptr [rcx-20h], xmm0
0x18000398b  movups  xmm1, xmmword ptr [rax-10h]
0x18000398f  movups  xmmword ptr [rcx-10h], xmm1
0x180003993  sub     rdx, 1
0x180003997  jnz     short loc_180003946
0x180003999  mov     rax, [rax]
0x18000399c  mov     r14b, 1
0x18000399f  mov     [rcx], rax
0x1800039a2  mov     rdi, rbx
0x1800039a5  mov     byte ptr [rbp+210h+var_284], r14b
0x1800039a9  mov     [rbp+210h+var_290], rbx
0x1800039ad  mov     [rbp+210h+var_288], r12d
0x1800039b1  jmp     loc_180003873
0x1800039b6  mov     edx, 1
0x1800039bb  jmp     loc_180003691
0x1800039c0  mov     ecx, 8; dwErrCode
0x1800039c5  call    cs:__imp_SetLastError
0x1800039cc  nop     dword ptr [rax+rax+00h]
0x1800039d1  call    cs:__imp_GetLastError
0x1800039d8  nop     dword ptr [rax+rax+00h]
0x1800039dd  test    eax, eax
0x1800039df  jle     short loc_1800039EB
0x1800039e1  movzx   eax, ax
0x1800039e4  or      eax, 80070000h
0x1800039e9  test    eax, eax
0x1800039eb  js      loc_18000375A
0x1800039f1  mov     r13, [rsp+310h+Src]
0x1800039f6  xor     r15d, r15d
0x1800039f9  mov     [rsp+310h+Src], r15
0x1800039fe  xorps   xmm0, xmm0
0x180003a01  mov     [rsp+310h+phHash], r15
  ... truncated ...
```
