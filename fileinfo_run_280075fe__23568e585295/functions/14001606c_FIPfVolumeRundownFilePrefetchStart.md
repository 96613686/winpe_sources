# FIPfVolumeRundownFilePrefetchStart

- ea: `0x14001606c`
- end: `0x140016453`
- name: `FIPfVolumeRundownFilePrefetchStart`
- size: `999`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x140015a48`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140003920`
- `0x140003a00`
- `0x140003a80`
- `0x140003d80`
- `0x14000d008`
- `0x14000ed40`
- `0x14000ef70`
- `0x140015950`
- `0x140015d3c`
- `0x14001606c`
- `0x14001645c`
- `0x140016788`
- `0x14001689c`
- `0x140017e44`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x14001626f`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x14001626f`

## pseudocode

```c
__int64 __fastcall FIPfVolumeRundownFilePrefetchStart(__m128i *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rsi
  char v5; // r15
  unsigned int v6; // eax
  __int16 v7; // bx
  __m128i *v8; // rsi
  __int8 *v9; // r14
  __m128i *v10; // r12
  __m128i *v11; // rdi
  __int16 v12; // ax
  unsigned int v13; // ebx
  unsigned int v14; // r12d
  unsigned __int16 v15; // r13
  __int8 *v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rdi
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  int v22; // edi
  unsigned __int64 v23; // rax
  _QWORD *v24; // rdx
  unsigned __int64 v25; // rbx
  unsigned __int16 v27; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-B0h]
  unsigned int v31; // [rsp+54h] [rbp-ACh]
  __int128 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  _QWORD v37[28]; // [rsp+90h] [rbp-70h] BYREF

  v3 = (int)a2;
  v36 = a3;
  memset(v37, 0, 0xD8u);
  _InterlockedAdd(&a1[28].m128i_i32[v3 + 2], 1u);
  _InterlockedAdd((volatile signed __int32 *)&FIGlobals + v3 + 326, 1u);
  v32 = 0;
  v35 = 0;
  v5 = 0;
  v29 = 0;
  v33 = MEMORY[0xFFFFF78000000320];
  v31 = MEMORY[0xFFFFF78000000004];
  FILockSharedAcquire(&a1[1].m128i_u64[1]);
  v27 = a1[5].m128i_u16[7];
  v34 = a1[6].m128i_i64[1];
  FILockExclusiveRelease(&a1[1].m128i_u64[1]);
  v6 = FIPfOpenAttemptsRundownStart(a1, v3, (__int64)&v29);
  v7 = v29;
  v8 = a1 + 9;
  v30 = v6;
  v9 = &a1[8].m128i_i8[8];
  v10 = 0;
  while ( 1 )
  {
    FILockExclusiveAcquire(&a1[8].m128i_u64[1]);
    v8 = (__m128i *)v8->m128i_i64[0];
    v11 = 0;
    if ( v8 != &a1[9] )
    {
      v11 = v8;
      FIPfFilePfLinkReference(v8, &a1[8].m128i_u64[1]);
    }
    FILockExclusiveRelease(&a1[8].m128i_u64[1]);
    if ( v10 )
      FIPfFilePfLinkDereference(v10);
    if ( !v11 )
      break;
    v10 = v11;
    FILockExclusiveAcquire(&v11[1].m128i_u64[1]);
    v12 = v11[3].m128i_i16[0];
    HIWORD(v29) += v12;
    v7 += v12;
    if ( v11[3].m128i_i32[0] )
    {
      _InterlockedAdd(&a1[25].m128i_i32[a2 + 1], 1u);
      _InterlockedAdd((volatile signed __int32 *)&FIGlobals + (int)a2 + 303, 1u);
      if ( (int)FIPfOpenListNotifyConflictStart(&v11[2], (int)a2, a2, &v32) < 0 )
        v5 = 1;
    }
    FILockExclusiveRelease(&v11[1].m128i_u64[1]);
  }
  LOWORD(v29) = v7;
  FILockExclusiveAcquire(&a1[8].m128i_u64[1]);
  v13 = v33;
  v14 = v30;
  if ( v5 && (int)((__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *))qword_140009A80)(0, 0, &v35) < 0 )
    v5 = 0;
  if ( a1[13].m128i_i32[0] )
  {
    if ( PsIsCurrentThreadPrefetching() )
    {
      FILockExclusiveRelease(&a1[8].m128i_u64[1]);
      _InterlockedAdd(&dword_1400098D4, 1u);
      v15 = v27;
      v14 = -1073610679;
    }
    else
    {
      v16 = &a1[13].m128i_i8[12];
      FIPfBlockedOpInsert(&a1[12], (char *)&a1[13].m128i_u64[1] + 4, v37);
      FILockExclusiveRelease(&a1[8].m128i_u64[1]);
      LODWORD(v37[14]) |= 4u;
      v17 = 49;
      v37[12] = a1;
      v15 = v27;
      LODWORD(v37[11]) = a2;
      if ( v27 < 0x31u )
        v17 = v27;
      v18 = 2 * v17;
      memmove((char *)&v37[14] + 4, (const void *)(v34 + 2LL * (v27 - (unsigned int)v17)), 2 * v17);
      *(_WORD *)((char *)&v37[14] + v18 + 4) = 0;
      v19 = FIPfBlockedOpBlock((__int64)v37, 1);
      if ( !v14 )
        v14 = v19;
      FILockExclusiveAcquire(v9);
      FIPfBlockedOpRemove(v20, v16, v37);
      FILockExclusiveRelease(v9);
    }
  }
  else
  {
    FILockExclusiveRelease(&a1[8].m128i_u64[1]);
    v15 = v27;
  }
  if ( (_WORD)v29 )
    FIPfConflictTelemetryAccumulate(
      v34,
      v15,
      1,
      a2,
      ((v31 * HIDWORD(v33)) << 8) + ((v31 * (unsigned __int64)v13) >> 24),
      (__int64)&v29,
      v36);
  if ( v5 )
    ((void (__fastcall *)(_QWORD, _QWORD))v35)(0, *((_QWORD *)&v35 + 1));
  v21 = v32;
  if ( (BYTE8(v32) & 1) != 0 )
  {
    if ( (_QWORD)v32 )
      v21 = (unsigned __int64)&v32 ^ v32;
    else
      v21 = 0;
  }
  v22 = BYTE8(v32) & 1;
  if ( v21 )
  {
    while ( 1 )
    {
      v23 = *(_QWORD *)v21;
      if ( *(_QWORD *)v21 )
        break;
      v24 = (_QWORD *)(v21 + 8);
      v23 = *(_QWORD *)(v21 + 8);
      if ( v23 )
      {
LABEL_35:
        if ( v22 )
          v21 ^= v23;
        else
          v21 = v23;
        *v24 = 0;
      }
      else
      {
        v25 = *(_QWORD *)(v21 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v22 && v25 )
          v25 ^= v21;
        FIPfNotifiedContextsDelete((PVOID)v21);
        if ( !v25 )
          return v14;
        v21 = v25;
      }
    }
    v24 = (_QWORD *)v21;
    goto LABEL_35;
  }
  return v14;
}

```

## disassembly

```asm
0x14001606c  mov     [rsp-8+arg_18], rbx
0x140016071  push    rbp
0x140016072  push    rsi
0x140016073  push    rdi
0x140016074  push    r12
0x140016076  push    r13
0x140016078  push    r14
0x14001607a  push    r15
0x14001607c  lea     rbp, [rsp-80h]
0x140016081  sub     rsp, 180h
0x140016088  mov     rax, cs:__security_cookie
0x14001608f  xor     rax, rsp
0x140016092  mov     [rbp+0B0h+var_40], rax
0x140016096  movsxd  rsi, edx
0x140016099  mov     r13, rcx
0x14001609c  mov     [rbp+0B0h+var_128], r8
0x1400160a0  lea     rcx, [rbp+0B0h+var_120]; void *
0x1400160a4  xor     edx, edx; Val
0x1400160a6  mov     [rsp+1B0h+var_16C], esi
0x1400160aa  mov     r8d, 0D8h; Size
0x1400160b0  call    memset
0x1400160b5  xorps   xmm0, xmm0
0x1400160b8  xorps   xmm1, xmm1
0x1400160bb  movups  [rsp+1B0h+var_158], xmm0
0x1400160c0  mov     ecx, 1
0x1400160c5  movups  [rsp+1B0h+var_138], xmm1
0x1400160ca  lock add [r13+rsi*4+1C8h], ecx
0x1400160d3  lea     rdx, FIGlobals
0x1400160da  lock add [rdx+rsi*4+518h], ecx
0x1400160e2  movdqu  [rsp+1B0h+var_158], xmm0
0x1400160e8  mov     rbx, 0FFFFF78000000320h
0x1400160f2  lea     rcx, [r13+18h]
0x1400160f6  movups  [rsp+1B0h+var_138], xmm0
0x1400160fb  xor     r15b, r15b
0x1400160fe  mov     [rsp+1B0h+var_168], 0
0x140016107  mov     rbx, [rbx]
0x14001610a  mov     eax, ds:0FFFFF78000000004h
0x140016113  mov     [rsp+1B0h+var_148], rbx
0x140016118  mov     [rsp+1B0h+var_15C], eax
0x14001611c  call    FILockSharedAcquire
0x140016121  movzx   eax, word ptr [r13+5Eh]
0x140016126  lea     rcx, [r13+18h]
0x14001612a  mov     [rsp+1B0h+var_170], ax
0x14001612f  mov     rax, [r13+68h]
0x140016133  mov     [rsp+1B0h+var_140], rax
0x140016138  call    FILockExclusiveRelease
0x14001613d  lea     r8, [rsp+1B0h+var_168]
0x140016142  mov     edx, esi
0x140016144  mov     rcx, r13
0x140016147  call    FIPfOpenAttemptsRundownStart
0x14001614c  movzx   ebx, word ptr [rsp+1B0h+var_168]
0x140016151  lea     rsi, [r13+90h]
0x140016158  mov     [rsp+1B0h+var_160], eax
0x14001615c  lea     r14, [r13+88h]
0x140016163  xor     r12d, r12d
0x140016166  mov     rcx, r14
0x140016169  call    FILockExclusiveAcquire
0x14001616e  mov     rsi, [rsi]
0x140016171  lea     rax, [r13+90h]
0x140016178  xor     edi, edi
0x14001617a  cmp     rsi, rax
0x14001617d  jz      short loc_14001618D
0x14001617f  mov     rdx, r14
0x140016182  mov     rcx, rsi
0x140016185  mov     rdi, rsi
0x140016188  call    FIPfFilePfLinkReference
0x14001618d  mov     rcx, r14
0x140016190  call    FILockExclusiveRelease
0x140016195  test    r12, r12
0x140016198  jz      short loc_1400161A2
0x14001619a  mov     rcx, r12
0x14001619d  call    FIPfFilePfLinkDereference
0x1400161a2  test    rdi, rdi
0x1400161a5  jz      short loc_140016216
0x1400161a7  lea     rcx, [rdi+18h]
0x1400161ab  mov     r12, rdi
0x1400161ae  call    FILockExclusiveAcquire
0x1400161b3  movzx   eax, word ptr [rdi+30h]
0x1400161b7  add     word ptr [rsp+1B0h+var_168+6], ax
0x1400161bc  add     bx, ax
0x1400161bf  cmp     dword ptr [rdi+30h], 0
0x1400161c3  jz      short loc_140016208
0x1400161c5  movsxd  rdx, [rsp+1B0h+var_16C]
0x1400161ca  mov     ecx, 1
0x1400161cf  lock add [r13+rdx*4+194h], ecx
0x1400161d8  lea     r8, FIGlobals
0x1400161df  lock add [r8+rdx*4+4BCh], ecx
0x1400161e8  lea     rcx, [rdi+20h]
0x1400161ec  mov     r8d, edx
0x1400161ef  lea     r9, [rsp+1B0h+var_158]
0x1400161f4  call    FIPfOpenListNotifyConflictStart
0x1400161f9  test    eax, eax
0x1400161fb  movzx   r15d, r15b
0x1400161ff  mov     eax, 1
0x140016204  cmovs   r15d, eax
0x140016208  lea     rcx, [rdi+18h]
0x14001620c  call    FILockExclusiveRelease
0x140016211  jmp     loc_140016166
0x140016216  mov     rcx, r14
0x140016219  mov     word ptr [rsp+1B0h+var_168], bx
0x14001621e  call    FILockExclusiveAcquire
0x140016223  mov     rbx, [rsp+1B0h+var_148]
0x140016228  xor     esi, esi
0x14001622a  mov     r12d, [rsp+1B0h+var_160]
0x14001622f  test    r15b, r15b
0x140016232  jz      short loc_140016253
0x140016234  mov     rax, cs:qword_140009A80
0x14001623b  lea     r8, [rsp+1B0h+var_138]
0x140016240  xor     edx, edx
0x140016242  xor     ecx, ecx
0x140016244  call    _guard_dispatch_icall
0x140016249  test    eax, eax
0x14001624b  movzx   r15d, r15b
0x14001624f  cmovs   r15d, esi
0x140016253  cmp     [r13+0D0h], esi
0x14001625a  jnz     short loc_14001626F
0x14001625c  mov     rcx, r14
0x14001625f  call    FILockExclusiveRelease
0x140016264  movzx   r13d, [rsp+1B0h+var_170]
0x14001626a  jmp     loc_14001633F
0x14001626f  call    cs:__imp_PsIsCurrentThreadPrefetching
0x140016276  nop     dword ptr [rax+rax+00h]
0x14001627b  test    al, al
0x14001627d  jz      short loc_1400162A6
0x14001627f  mov     rcx, r14
0x140016282  call    FILockExclusiveRelease
0x140016287  mov     r14d, 1
0x14001628d  lock add cs:dword_1400098D4, r14d
0x140016295  movzx   r13d, [rsp+1B0h+var_170]
0x14001629b  mov     r12d, 0C0020049h
0x1400162a1  jmp     loc_140016345
0x1400162a6  lea     rsi, [r13+0DCh]
0x1400162ad  mov     rdx, rsi
0x1400162b0  lea     rcx, [r13+0C0h]
0x1400162b7  lea     r8, [rbp+0B0h+var_120]
0x1400162bb  call    FIPfBlockedOpInsert
0x1400162c0  mov     rcx, r14
0x1400162c3  call    FILockExclusiveRelease
0x1400162c8  or      [rbp+0B0h+var_B0], 4
0x1400162cc  mov     ecx, 31h ; '1'
0x1400162d1  mov     eax, [rsp+1B0h+var_16C]
0x1400162d5  mov     [rbp+0B0h+var_C0], r13
0x1400162d9  movzx   r13d, [rsp+1B0h+var_170]
0x1400162df  cmp     r13d, ecx
0x1400162e2  mov     [rbp+0B0h+var_C8], eax
0x1400162e5  mov     edx, r13d
0x1400162e8  cmovb   ecx, r13d
0x1400162ec  sub     edx, ecx
0x1400162ee  lea     rdi, [rcx+rcx]
0x1400162f2  mov     rcx, [rsp+1B0h+var_140]
0x1400162f7  mov     r8, rdi; Size
0x1400162fa  lea     rdx, [rcx+rdx*2]; Src
0x1400162fe  lea     rcx, [rbp+0B0h+var_AC]; void *
0x140016302  call    memmove
0x140016307  xor     eax, eax
0x140016309  lea     rcx, [rbp+0B0h+var_120]
0x14001630d  mov     [rbp+rdi+0B0h+var_AC], ax
0x140016312  lea     edx, [rax+1]
0x140016315  call    FIPfBlockedOpBlock
0x14001631a  test    r12d, r12d
0x14001631d  mov     rcx, r14
0x140016320  cmovz   r12d, eax
0x140016324  call    FILockExclusiveAcquire
0x140016329  lea     r8, [rbp+0B0h+var_120]
0x14001632d  mov     rdx, rsi
0x140016330  call    FIPfBlockedOpRemove
0x140016335  mov     rcx, r14
0x140016338  call    FILockExclusiveRelease
0x14001633d  xor     esi, esi
0x14001633f  mov     r14d, 1
0x140016345  cmp     word ptr [rsp+1B0h+var_168], si
0x14001634a  jbe     short loc_140016399
0x14001634c  mov     r8d, [rsp+1B0h+var_15C]
0x140016351  movzx   edx, r13w
0x140016355  mov     eax, dword ptr [rsp+1B0h+var_148+4]
0x140016359  mov     r9d, [rsp+1B0h+var_16C]
0x14001635e  mov     rcx, [rsp+1B0h+var_140]
0x140016363  imul    rax, r8
0x140016367  mov     r10d, ebx
0x14001636a  imul    r10, r8
0x14001636e  shl     rax, 8
0x140016372  mov     r8d, r14d
0x140016375  shr     r10, 18h
0x140016379  add     r10, rax
0x14001637c  mov     rax, [rbp+0B0h+var_128]
0x140016380  mov     [rsp+1B0h+var_180], rax
0x140016385  lea     rax, [rsp+1B0h+var_168]
0x14001638a  mov     [rsp+1B0h+var_188], rax
0x14001638f  mov     [rsp+1B0h+var_190], r10
0x140016394  call    FIPfConflictTelemetryAccumulate
0x140016399  test    r15b, r15b
0x14001639c  jz      short loc_1400163AE
0x14001639e  mov     rdx, qword ptr [rbp+0B0h+var_138+8]
0x1400163a2  xor     ecx, ecx
0x1400163a4  mov     rax, qword ptr [rsp+1B0h+var_138]
0x1400163a9  call    _guard_dispatch_icall
0x1400163ae  mov     rcx, qword ptr [rsp+1B0h+var_158]
0x1400163b3  test    byte ptr [rsp+1B0h+var_158+8], r14b
0x1400163b8  jz      short loc_1400163CC
0x1400163ba  test    rcx, rcx
0x1400163bd  jz      short loc_1400163C9
0x1400163bf  lea     rax, [rsp+1B0h+var_158]
0x1400163c4  xor     rcx, rax
0x1400163c7  jmp     short loc_1400163CC
0x1400163c9  mov     rcx, rsi; P
0x1400163cc  movzx   edi, byte ptr [rsp+1B0h+var_158+8]
0x1400163d1  and     edi, r14d
0x1400163d4  test    rcx, rcx
0x1400163d7  jz      short loc_140016428
0x1400163d9  mov     rax, [rcx]
0x1400163dc  test    rax, rax
0x1400163df  jz      short loc_1400163E6
0x1400163e1  mov     rdx, rcx
0x1400163e4  jmp     short loc_1400163F2
0x1400163e6  lea     rdx, [rcx+8]
0x1400163ea  mov     rax, [rdx]
0x1400163ed  test    rax, rax
0x1400163f0  jz      short loc_140016403
0x1400163f2  test    edi, edi
0x1400163f4  jz      short loc_1400163FB
0x1400163f6  xor     rcx, rax
0x1400163f9  jmp     short loc_1400163FE
0x1400163fb  mov     rcx, rax
0x1400163fe  mov     [rdx], rsi
0x140016401  jmp     short loc_1400163D9
0x140016403  mov     rbx, [rcx+10h]
0x140016407  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14001640b  test    edi, edi
0x14001640d  jz      short loc_140016417
0x14001640f  test    rbx, rbx
0x140016412  jz      short loc_140016417
0x140016414  xor     rbx, rcx
0x140016417  xor     edx, edx
0x140016419  call    FIPfNotifiedContextsDelete
0x14001641e  test    rbx, rbx
0x140016421  jz      short loc_140016428
0x140016423  mov     rcx, rbx
0x140016426  jmp     short loc_1400163D9
0x140016428  mov     eax, r12d
0x14001642b  mov     rcx, [rbp+0B0h+var_40]
0x14001642f  xor     rcx, rsp; StackCookie
0x140016432  call    __security_check_cookie
0x140016437  mov     rbx, [rsp+1B0h+arg_18]
0x14001643f  add     rsp, 180h
0x140016446  pop     r15
0x140016448  pop     r14
0x14001644a  pop     r13
0x14001644c  pop     r12
0x14001644e  pop     rdi
0x14001644f  pop     rsi
0x140016450  pop     rbp
0x140016451  retn
```
