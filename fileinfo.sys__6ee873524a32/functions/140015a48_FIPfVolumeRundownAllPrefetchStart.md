# FIPfVolumeRundownAllPrefetchStart

- ea: `0x140015a48`
- end: `0x140015d35`
- name: `FIPfVolumeRundownAllPrefetchStart`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140010cd0`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140003920`
- `0x140003a00`
- `0x140003a80`
- `0x140003d80`
- `0x14000ed40`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`
- `0x14001645c`
- `0x140016788`
- `0x14001689c`
- `0x140017e44`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140015c56`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140015c56`

## pseudocode

```c
__int64 __fastcall FIPfVolumeRundownAllPrefetchStart(__m128i *a1, int a2, _WORD *a3)
{
  __int64 v3; // r14
  unsigned int v6; // r12d
  unsigned int v7; // eax
  __int8 *v8; // r13
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  int v11; // edi
  unsigned __int64 v13; // rax
  _QWORD *v14; // rdx
  unsigned __int64 v15; // rbx
  bool v16; // r15
  __int8 *v17; // r14
  unsigned int v18; // ebx
  __int8 *v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rbx
  unsigned int v24; // eax
  __int64 v25; // rcx
  PVOID P[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v28; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v29[28]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = a2;
  memset(v29, 0, 0xD8u);
  _InterlockedAdd(&a1[29].m128i_i32[v3 + 3], 1u);
  _InterlockedAdd((volatile signed __int32 *)&FIGlobals + v3 + 331, 1u);
  *(_OWORD *)P = 0;
  v28 = 0;
  v6 = FIPfVolumeRundownFilePrefetchStart(a1, v3, (__int64)a3);
  v7 = FIPfOpenAttemptsRundownStart((__m128i *)2, v3, (__int64)a3);
  v8 = &a1[8].m128i_i8[8];
  if ( v7 )
    v6 = v7;
  FILockExclusiveAcquire(&a1[8].m128i_u64[1]);
  if ( a1[13].m128i_i32[1] )
  {
    v16 = 0;
    a3[2] += a1[13].m128i_i16[2];
    *a3 += a1[13].m128i_i16[2];
    _InterlockedAdd(&a1[26].m128i_i32[v3 + 1], 1u);
    _InterlockedAdd((volatile signed __int32 *)&FIGlobals + v3 + 307, 1u);
    if ( (int)FIPfOpenListNotifyConflictStart(&a1[10], v9, (unsigned int)v3, P) < 0 )
      v16 = (int)((__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *))qword_140009A80)(0, 0, &v28) >= 0;
    if ( PsIsCurrentThreadPrefetching() )
    {
      FILockExclusiveRelease(&a1[8].m128i_u64[1]);
      _InterlockedAdd(&dword_1400098D8, 1u);
      v6 = -1073610679;
    }
    else
    {
      v17 = &a1[13].m128i_i8[8];
      FIPfBlockedOpInsert(&a1[11], &a1[13].m128i_u64[1], v29);
      FILockExclusiveRelease(&a1[8].m128i_u64[1]);
      LODWORD(v29[14]) |= 2u;
      LODWORD(v29[11]) = a2;
      v29[12] = a1;
      FILockSharedAcquire(&a1[1].m128i_u64[1]);
      v18 = a1[5].m128i_u16[7];
      v19 = &a1[1].m128i_i8[8];
      v20 = a1[6].m128i_i64[1];
      FILockExclusiveRelease(v19);
      v21 = 49;
      v22 = v18;
      if ( v18 < 0x31 )
        v21 = v18;
      v23 = 2 * v21;
      memmove((char *)&v29[14] + 4, (const void *)(v20 + 2LL * (v22 - (unsigned int)v21)), 2 * v21);
      *(_WORD *)((char *)&v29[14] + v23 + 4) = 0;
      v24 = FIPfBlockedOpBlock((__int64)v29, 1);
      if ( !v6 )
        v6 = v24;
      FILockExclusiveAcquire(v8);
      FIPfBlockedOpRemove(v25, v17, v29);
      FILockExclusiveRelease(v8);
    }
    if ( v16 )
      ((void (__fastcall *)(_QWORD, _QWORD))v28)(0, *((_QWORD *)&v28 + 1));
  }
  else
  {
    FILockExclusiveRelease(&a1[8].m128i_u64[1]);
  }
  v10 = (unsigned __int64)P[0];
  if ( ((__int64)P[1] & 1) != 0 && P[0] )
    v10 = (unsigned __int64)P ^ (unsigned __int64)P[0];
  v11 = (__int64)P[1] & 1;
  if ( v10 )
  {
    while ( 1 )
    {
      v13 = *(_QWORD *)v10;
      if ( *(_QWORD *)v10 )
      {
        v14 = (_QWORD *)v10;
LABEL_10:
        if ( v11 )
          v10 ^= v13;
        else
          v10 = v13;
        *v14 = 0;
      }
      else
      {
        v14 = (_QWORD *)(v10 + 8);
        v13 = *(_QWORD *)(v10 + 8);
        if ( v13 )
          goto LABEL_10;
        v15 = *(_QWORD *)(v10 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v11 && v15 )
          v15 ^= v10;
        FIPfNotifiedContextsDelete((PVOID)v10);
        if ( !v15 )
          return v6;
        v10 = v15;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140015a48  mov     [rsp-8+arg_18], rbx
0x140015a4d  push    rbp
0x140015a4e  push    rsi
0x140015a4f  push    rdi
0x140015a50  push    r12
0x140015a52  push    r13
0x140015a54  push    r14
0x140015a56  push    r15
0x140015a58  lea     rbp, [rsp-40h]
0x140015a5d  sub     rsp, 140h
0x140015a64  mov     rax, cs:__security_cookie
0x140015a6b  xor     rax, rsp
0x140015a6e  mov     [rbp+70h+var_40], rax
0x140015a72  movsxd  r14, edx
0x140015a75  mov     rdi, r8
0x140015a78  mov     rsi, rcx
0x140015a7b  mov     [rsp+170h+var_150], r14d
0x140015a80  xor     edx, edx; Val
0x140015a82  lea     rcx, [rsp+170h+var_120]; void *
0x140015a87  mov     r8d, 0D8h; Size
0x140015a8d  call    memset
0x140015a92  xorps   xmm0, xmm0
0x140015a95  xorps   xmm1, xmm1
0x140015a98  movups  xmmword ptr [rsp+170h+P], xmm0
0x140015a9d  mov     eax, 1
0x140015aa2  movups  [rsp+170h+var_138], xmm1
0x140015aa7  lock add [rsi+r14*4+1DCh], eax
0x140015ab0  lea     rcx, FIGlobals
0x140015ab7  lock add [rcx+r14*4+52Ch], eax
0x140015ac0  mov     r8, rdi
0x140015ac3  mov     edx, r14d
0x140015ac6  mov     rcx, rsi
0x140015ac9  movdqu  xmmword ptr [rsp+170h+P], xmm0
0x140015acf  movups  [rsp+170h+var_138], xmm0
0x140015ad4  call    FIPfVolumeRundownFilePrefetchStart
0x140015ad9  mov     r8, rdi
0x140015adc  mov     edx, r14d
0x140015adf  mov     ecx, 2
0x140015ae4  mov     r12d, eax
0x140015ae7  call    FIPfOpenAttemptsRundownStart
0x140015aec  test    eax, eax
0x140015aee  lea     r13, [rsi+88h]
0x140015af5  mov     rcx, r13
0x140015af8  cmovnz  r12d, eax
0x140015afc  call    FILockExclusiveAcquire
0x140015b01  cmp     dword ptr [rsi+0D4h], 0
0x140015b08  jnz     loc_140015BE8
0x140015b0e  mov     rcx, r13
0x140015b11  call    FILockExclusiveRelease
0x140015b16  test    byte ptr [rsp+170h+P+8], 1
0x140015b1b  mov     rcx, [rsp+170h+P]; P
0x140015b20  jnz     loc_140015BB2
0x140015b26  movzx   edi, byte ptr [rsp+170h+P+8]
0x140015b2b  and     edi, 1
0x140015b2e  test    rcx, rcx
0x140015b31  jnz     short loc_140015B5E
0x140015b33  mov     eax, r12d
0x140015b36  mov     rcx, [rbp+70h+var_40]
0x140015b3a  xor     rcx, rsp; StackCookie
0x140015b3d  call    __security_check_cookie
0x140015b42  mov     rbx, [rsp+170h+arg_18]
0x140015b4a  add     rsp, 140h
0x140015b51  pop     r15
0x140015b53  pop     r14
0x140015b55  pop     r13
0x140015b57  pop     r12
0x140015b59  pop     rdi
0x140015b5a  pop     rsi
0x140015b5b  pop     rbp
0x140015b5c  retn
0x140015b5e  mov     rax, [rcx]
0x140015b61  test    rax, rax
0x140015b64  jnz     short loc_140015BA8
0x140015b66  lea     rdx, [rcx+8]
0x140015b6a  mov     rax, [rdx]
0x140015b6d  test    rax, rax
0x140015b70  jz      short loc_140015B82
0x140015b72  test    edi, edi
0x140015b74  jz      short loc_140015BAD
0x140015b76  xor     rcx, rax
0x140015b79  mov     qword ptr [rdx], 0
0x140015b80  jmp     short loc_140015B5E
0x140015b82  mov     rbx, [rcx+10h]
0x140015b86  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140015b8a  test    edi, edi
0x140015b8c  jz      short loc_140015B97
0x140015b8e  test    rbx, rbx
0x140015b91  jnz     loc_140015D2D
0x140015b97  xor     edx, edx
0x140015b99  call    FIPfNotifiedContextsDelete
0x140015b9e  test    rbx, rbx
0x140015ba1  jz      short loc_140015B33
0x140015ba3  mov     rcx, rbx
0x140015ba6  jmp     short loc_140015B5E
0x140015ba8  mov     rdx, rcx
0x140015bab  jmp     short loc_140015B72
0x140015bad  mov     rcx, rax
0x140015bb0  jmp     short loc_140015B79
0x140015bb2  test    rcx, rcx
0x140015bb5  jz      short loc_140015BC4
0x140015bb7  lea     rax, [rsp+170h+P]
0x140015bbc  xor     rcx, rax
0x140015bbf  jmp     loc_140015B26
0x140015bc4  jmp     loc_140015B26
0x140015bc9  test    r15b, r15b
0x140015bcc  jz      loc_140015B16
0x140015bd2  mov     rdx, qword ptr [rsp+170h+var_138+8]
0x140015bd7  xor     ecx, ecx
0x140015bd9  mov     rax, qword ptr [rsp+170h+var_138]
0x140015bde  call    _guard_dispatch_icall
0x140015be3  jmp     loc_140015B16
0x140015be8  movzx   eax, word ptr [rsi+0D4h]
0x140015bef  xor     r15b, r15b
0x140015bf2  add     [rdi+4], ax
0x140015bf6  movzx   eax, word ptr [rsi+0D4h]
0x140015bfd  add     [rdi], ax
0x140015c00  mov     edi, 1
0x140015c05  lock add [rsi+r14*4+1A4h], edi
0x140015c0e  lea     rax, FIGlobals
0x140015c15  lock add [rax+r14*4+4CCh], edi
0x140015c1e  lea     rcx, [rsi+0A0h]
0x140015c25  mov     r8d, r14d
0x140015c28  lea     r9, [rsp+170h+P]
0x140015c2d  call    FIPfOpenListNotifyConflictStart
0x140015c32  test    eax, eax
0x140015c34  jns     short loc_140015C56
0x140015c36  mov     rax, cs:qword_140009A80
0x140015c3d  lea     r8, [rsp+170h+var_138]
0x140015c42  xor     edx, edx
0x140015c44  xor     ecx, ecx
0x140015c46  call    _guard_dispatch_icall
0x140015c4b  xor     edx, edx
0x140015c4d  mov     r15d, edi
0x140015c50  test    eax, eax
0x140015c52  cmovs   r15d, edx
0x140015c56  call    cs:__imp_PsIsCurrentThreadPrefetching
0x140015c5d  nop     dword ptr [rax+rax+00h]
0x140015c62  test    al, al
0x140015c64  jz      short loc_140015C80
0x140015c66  mov     rcx, r13
0x140015c69  call    FILockExclusiveRelease
0x140015c6e  lock add cs:dword_1400098D8, edi
0x140015c75  mov     r12d, 0C0020049h
0x140015c7b  jmp     loc_140015BC9
0x140015c80  lea     r14, [rsi+0D8h]
0x140015c87  mov     rdx, r14
0x140015c8a  lea     rcx, [rsi+0B0h]
0x140015c91  lea     r8, [rsp+170h+var_120]
0x140015c96  call    FIPfBlockedOpInsert
0x140015c9b  mov     rcx, r13
0x140015c9e  call    FILockExclusiveRelease
0x140015ca3  mov     eax, [rsp+170h+var_150]
0x140015ca7  lea     rdi, [rsi+18h]
0x140015cab  or      [rbp+70h+var_B0], 2
0x140015caf  mov     rcx, rdi
0x140015cb2  mov     [rbp+70h+var_C8], eax
0x140015cb5  mov     [rbp+70h+var_C0], rsi
0x140015cb9  call    FILockSharedAcquire
0x140015cbe  movzx   ebx, word ptr [rsi+5Eh]
0x140015cc2  mov     rcx, rdi
0x140015cc5  mov     rsi, [rsi+68h]
0x140015cc9  call    FILockExclusiveRelease
0x140015cce  mov     ecx, 31h ; '1'
0x140015cd3  mov     edx, ebx
0x140015cd5  cmp     ebx, ecx
0x140015cd7  cmovb   ecx, ebx
0x140015cda  sub     edx, ecx
0x140015cdc  lea     rbx, [rcx+rcx]
0x140015ce0  lea     rdx, [rsi+rdx*2]; Src
0x140015ce4  mov     r8, rbx; Size
0x140015ce7  lea     rcx, [rbp+70h+var_AC]; void *
0x140015ceb  call    memmove
0x140015cf0  xor     eax, eax
0x140015cf2  lea     rcx, [rsp+170h+var_120]
0x140015cf7  mov     [rbp+rbx+70h+var_AC], ax
0x140015cfc  lea     edx, [rax+1]
0x140015cff  call    FIPfBlockedOpBlock
0x140015d04  test    r12d, r12d
0x140015d07  mov     rcx, r13
0x140015d0a  cmovz   r12d, eax
0x140015d0e  call    FILockExclusiveAcquire
0x140015d13  lea     r8, [rsp+170h+var_120]
0x140015d18  mov     rdx, r14
0x140015d1b  call    FIPfBlockedOpRemove
0x140015d20  mov     rcx, r13
0x140015d23  call    FILockExclusiveRelease
0x140015d28  jmp     loc_140015BC9
0x140015d2d  xor     rbx, rcx
0x140015d30  jmp     loc_140015B97
```
