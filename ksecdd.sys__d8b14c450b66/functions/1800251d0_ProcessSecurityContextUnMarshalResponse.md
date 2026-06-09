# ProcessSecurityContextUnMarshalResponse

- ea: `0x1800251d0`
- end: `0x180025722`
- name: `ProcessSecurityContextUnMarshalResponse`
- size: `1362`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002140`
- `0x180002820`
- `0x180004050`
- `0x180004810`
- `0x180010920`
- `0x180010980`
- `0x1800251d0`
- `0x180025db0`

## pseudocode

```c
__int64 __fastcall ProcessSecurityContextUnMarshalResponse(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v5; // rdx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rcx
  _OWORD *v8; // rdx
  unsigned __int64 v9; // rax
  void *ForcePool; // rax
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  unsigned int v16; // r8d
  __int64 v17; // rax
  int v18; // r10d
  unsigned int v19; // r12d
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned __int64 v22; // rax
  unsigned int i; // r8d
  __int64 v24; // r9
  unsigned __int64 v25; // rax
  __int64 v26; // r8
  unsigned int v27; // ecx
  unsigned int j; // esi
  __int64 v29; // rax
  const void **v30; // r14
  __int64 v31; // r15
  unsigned __int64 *v32; // rbx
  unsigned __int64 v33; // r14
  int v34; // r15d
  unsigned __int64 v35; // rbp
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 (__fastcall *v38)(unsigned __int64, __int128 *, unsigned __int64 *); // rax
  int v39; // ebp
  __int64 v41; // r9
  unsigned int v42; // r9d
  __int64 v43; // rdx
  void *v44; // rax
  __int64 v45; // rax
  unsigned int v46; // ebx
  __int64 v47; // rsi
  void *v48; // rcx
  __int128 v49; // [rsp+20h] [rbp-48h] BYREF
  char v50; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v51; // [rsp+88h] [rbp+20h] BYREF

  if ( a3 < 0x50 )
    return 3221225507LL;
  v5 = *(_QWORD **)(a1 + 96);
  v6 = a3;
  *v5 = *(_QWORD *)(a2 + 48);
  v5[1] = *(_QWORD *)(a2 + 56);
  **(_DWORD **)(a1 + 112) = *(_DWORD *)(a2 + 64);
  v7 = *(_QWORD *)(a2 + 32);
  if ( a3 < v7 )
    return 3221225507LL;
  if ( v7 )
  {
    v7 += a2;
    *(_QWORD *)(a2 + 32) = v7;
  }
  v8 = (_OWORD *)v7;
  if ( v7 )
  {
    v9 = *(_QWORD *)(v7 + 8);
    if ( a3 < v9 )
      return 3221225507LL;
    if ( v9 )
    {
      *(_QWORD *)(v7 + 8) = a2 + v9;
      v8 = *(_OWORD **)(a2 + 32);
    }
    *(_OWORD *)(a1 + 184) = *v8;
    ForcePool = *(void **)(a1 + 192);
    if ( ForcePool )
    {
      ForcePool = (void *)SecAllocateForcePool(*(_DWORD *)(a1 + 184));
      *(_QWORD *)(a1 + 192) = ForcePool;
      if ( !ForcePool )
        return 3221225626LL;
    }
    memmove(ForcePool, *(const void **)(*(_QWORD *)(a2 + 32) + 8LL), **(unsigned int **)(a2 + 32));
  }
  v11 = *(_QWORD **)(a1 + 120);
  if ( v11 )
    *v11 = *(_QWORD *)(a2 + 72);
  v12 = *(_QWORD *)(a2 + 24);
  if ( v6 < v12 )
    return 3221225507LL;
  if ( v12 )
  {
    v12 += a2;
    *(_QWORD *)(a2 + 24) = v12;
  }
  v13 = v12;
  if ( !v12 )
    goto LABEL_27;
  v14 = *(_QWORD *)(a1 + 80);
  if ( !v14 )
  {
    v19 = 261;
    goto LABEL_28;
  }
  if ( *(_DWORD *)(v14 + 4) < *(_DWORD *)(v12 + 4) )
  {
    v19 = 261;
    goto LABEL_28;
  }
  v15 = *(_QWORD *)(v12 + 8);
  if ( v6 < v15 )
    return 3221225507LL;
  if ( v15 )
  {
    *(_QWORD *)(v12 + 8) = a2 + v15;
    v13 = *(_QWORD *)(a2 + 24);
  }
  if ( *(_DWORD *)(v13 + 4) )
  {
    v16 = 0;
    do
    {
      v17 = *(_QWORD *)(v13 + 8);
      v18 = *(_DWORD *)(v17 + 8LL * v16 + 4);
      if ( (unsigned int)(v18 - 4) <= 1 )
      {
        v41 = 2LL * v16;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL) + 8 * v41 + 4) = v18;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL) + 8 * v41) = *(_DWORD *)(v17 + 8LL * v16);
      }
      v13 = *(_QWORD *)(a2 + 24);
      ++v16;
    }
    while ( v16 < *(_DWORD *)(v13 + 4) );
  }
LABEL_27:
  v19 = 0;
LABEL_28:
  if ( *(int *)(a1 + 20) >= 0 )
    *(_BYTE *)(a1 + 176) = (*(_DWORD *)(a2 + 40) & 0x2000) != 0;
  v20 = *(_QWORD *)(a2 + 16);
  if ( v6 >= v20 )
  {
    if ( v20 )
    {
      v20 += a2;
      *(_QWORD *)(a2 + 16) = v20;
    }
    v21 = v20;
    if ( !v20 )
      goto LABEL_53;
    v22 = *(_QWORD *)(v20 + 8);
    if ( v6 >= v22 )
    {
      if ( v22 )
      {
        *(_QWORD *)(v20 + 8) = a2 + v22;
        v21 = *(_QWORD *)(a2 + 16);
      }
      if ( *(_QWORD *)(v21 + 8) )
      {
        for ( i = 0; i < *(_DWORD *)(v21 + 4); ++i )
        {
          v24 = *(_QWORD *)(v21 + 8) + 16LL * i;
          v25 = *(_QWORD *)(v24 + 8);
          if ( v6 < v25 )
            return 3221225507LL;
          if ( v25 )
          {
            *(_QWORD *)(v24 + 8) = a2 + v25;
            v21 = *(_QWORD *)(a2 + 16);
          }
        }
      }
      v26 = *(_QWORD *)(a1 + 104);
      v27 = *(_DWORD *)(v26 + 4);
      if ( v27 >= *(_DWORD *)(v21 + 4) )
      {
        if ( (*(_DWORD *)(a1 + 88) & 0x100) != 0 && v27 )
        {
          v42 = 0;
          do
          {
            v43 = v42++;
            v21 = 2 * v43;
            *(_QWORD *)(*(_QWORD *)(v26 + 8) + 8 * v21 + 8) = 0;
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL) + 8 * v21) = 0;
            v26 = *(_QWORD *)(a1 + 104);
          }
          while ( v42 < *(_DWORD *)(v26 + 4) );
        }
        for ( j = 0; ; ++j )
        {
          v29 = *(_QWORD *)(a2 + 16);
          if ( j >= *(_DWORD *)(v29 + 4) )
            break;
          v21 = 16LL * j;
          v30 = (const void **)(v21 + *(_QWORD *)(v29 + 8));
          v31 = v21 + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL);
          if ( v30[1] )
          {
            if ( (*(_DWORD *)(a1 + 88) & 0x100) != 0 )
            {
              v44 = MIDL_user_allocate(*(unsigned int *)v30);
              *(_QWORD *)(v31 + 8) = v44;
              if ( !v44 )
              {
                v45 = *(_QWORD *)(a1 + 104);
                if ( *(_DWORD *)(v45 + 4) )
                {
                  v46 = 0;
                  do
                  {
                    v47 = *(_QWORD *)(v45 + 8) + 16LL * v46;
                    v48 = *(void **)(v47 + 8);
                    if ( v48 )
                    {
                      SspiLocalFree(v48);
                      *(_QWORD *)(v47 + 8) = 0;
                      *(_DWORD *)v47 = 0;
                    }
                    v45 = *(_QWORD *)(a1 + 104);
                    ++v46;
                  }
                  while ( v46 < *(_DWORD *)(v45 + 4) );
                }
                return 3221225626LL;
              }
            }
            else if ( *(_DWORD *)v31 < *(_DWORD *)v30 )
            {
              return 3221225507LL;
            }
            memmove(*(void **)(v31 + 8), v30[1], *(unsigned int *)v30);
          }
          *(_DWORD *)(v31 + 4) = *((_DWORD *)v30 + 1);
          *(_DWORD *)v31 = *(_DWORD *)v30;
        }
      }
LABEL_53:
      v49 = *(_OWORD *)(a1 + 184);
      if ( *(int *)(a1 + 20) < 0 )
        return v19;
      v32 = *(unsigned __int64 **)(a1 + 96);
      if ( !*(_BYTE *)(a1 + 176) )
      {
        if ( a1 != -56 && v32[1] == *(_QWORD *)(a1 + 136) )
          *(_OWORD *)v32 = *(_OWORD *)(a1 + 144);
        return v19;
      }
      v33 = v32[1];
      v34 = *(_DWORD *)(a1 + 200);
      if ( v33 && (v35 = *v32) != 0 )
      {
        v51 = 0;
        if ( v32 )
        {
          KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v50);
          if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v50) )
          {
            v36 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v50);
            if ( *(_QWORD *)(v36 + 456) )
            {
              if ( v35 < *(unsigned int *)(v36 + 464)
                && (_mm_lfence(), (v37 = *(_QWORD *)(*(_QWORD *)(v36 + 456) + 8 * v35)) != 0) )
              {
                v38 = *(__int64 (__fastcall **)(unsigned __int64, __int128 *, unsigned __int64 *))(v37 + 16);
                if ( v38 )
                {
                  v39 = v38(v33, &v49, &v51);
                  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v50);
                  if ( v39 < 0 )
                    goto LABEL_78;
                  v32[1] = v51;
                }
                else
                {
                  v39 = -2146893054;
                  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v50);
                }
              }
              else
              {
                v39 = -2146893055;
                KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v50);
              }
            }
            else
            {
              v39 = -1073741823;
              KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v50);
            }
          }
          else
          {
            v39 = -1073741058;
            KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v50);
          }
        }
        else
        {
          v39 = -1073741811;
        }
        if ( v39 >= 0 )
          return v19;
      }
      else
      {
        v39 = -2146893056;
      }
LABEL_78:
      if ( a1 == -56 || (v34 & 0x20) != 0 )
      {
        DeleteSecurityContextInternal(0, v21, v32);
        *(_OWORD *)v32 = *(_OWORD *)(a1 + 160);
      }
      *(_DWORD *)(a1 + 20) = v39;
      return v19;
    }
  }
  return 3221225507LL;
}

```

## disassembly

```asm
0x1800251d0  push    rbx
0x1800251d2  push    rsi
0x1800251d3  push    rdi
0x1800251d4  push    r12
0x1800251d6  push    r13
0x1800251d8  sub     rsp, 40h
0x1800251dc  mov     rbx, rdx
0x1800251df  mov     rdi, rcx
0x1800251e2  cmp     r8d, 50h ; 'P'
0x1800251e6  jb      loc_1800255E7
0x1800251ec  mov     rdx, [rcx+60h]
0x1800251f0  mov     rax, [rbx+30h]
0x1800251f4  mov     esi, r8d
0x1800251f7  mov     [rdx], rax
0x1800251fa  mov     rax, [rbx+38h]
0x1800251fe  mov     [rdx+8], rax
0x180025202  mov     rdx, [rcx+70h]
0x180025206  mov     eax, [rbx+40h]
0x180025209  mov     [rdx], eax
0x18002520b  mov     rcx, [rbx+20h]
0x18002520f  cmp     rsi, rcx
0x180025212  jb      loc_1800255E7
0x180025218  test    rcx, rcx
0x18002521b  jz      short loc_180025224
0x18002521d  add     rcx, rbx
0x180025220  mov     [rbx+20h], rcx
0x180025224  mov     rdx, rcx
0x180025227  test    rcx, rcx
0x18002522a  jz      short loc_180025276
0x18002522c  mov     rax, [rcx+8]
0x180025230  cmp     rsi, rax
0x180025233  jb      loc_1800255E7
0x180025239  test    rax, rax
0x18002523c  jz      short loc_180025249
0x18002523e  add     rax, rbx
0x180025241  mov     [rcx+8], rax
0x180025245  mov     rdx, [rbx+20h]
0x180025249  movups  xmm0, xmmword ptr [rdx]
0x18002524c  movups  xmmword ptr [rdi+0B8h], xmm0
0x180025253  mov     rax, [rdi+0C0h]
0x18002525a  test    rax, rax
0x18002525d  jnz     loc_180025505
0x180025263  mov     rdx, [rbx+20h]
0x180025267  mov     rcx, rax; void *
0x18002526a  mov     r8d, [rdx]; Size
0x18002526d  mov     rdx, [rdx+8]; Src
0x180025271  call    memmove
0x180025276  mov     rcx, [rdi+78h]
0x18002527a  test    rcx, rcx
0x18002527d  jnz     loc_18002565E
0x180025283  mov     rcx, [rbx+18h]
0x180025287  cmp     rsi, rcx
0x18002528a  jb      loc_1800255E7
0x180025290  test    rcx, rcx
0x180025293  jnz     loc_1800255F9
0x180025299  xor     r13d, r13d
0x18002529c  mov     rdx, rcx
0x18002529f  test    rcx, rcx
0x1800252a2  jz      short loc_18002530E
0x1800252a4  mov     r8, [rdi+50h]
0x1800252a8  test    r8, r8
0x1800252ab  jz      loc_18002566A
0x1800252b1  mov     eax, [rcx+4]
0x1800252b4  cmp     [r8+4], eax
0x1800252b8  jb      loc_180025675
0x1800252be  mov     rax, [rcx+8]
0x1800252c2  cmp     rsi, rax
0x1800252c5  jb      loc_1800255E7
0x1800252cb  test    rax, rax
0x1800252ce  jz      short loc_1800252DB
0x1800252d0  add     rax, rbx
0x1800252d3  mov     [rcx+8], rax
0x1800252d7  mov     rdx, [rbx+18h]
0x1800252db  cmp     [rdx+4], r13d
0x1800252df  jbe     short loc_18002530E
0x1800252e1  mov     r8d, r13d
0x1800252e4  mov     rax, [rdx+8]
0x1800252e8  mov     r9d, r8d
0x1800252eb  mov     r10d, [rax+r9*8+4]
0x1800252f0  lea     rdx, [rax+r9*8]
0x1800252f4  lea     eax, [r10-4]
0x1800252f8  cmp     eax, 1
0x1800252fb  jbe     loc_1800255C4
0x180025301  mov     rdx, [rbx+18h]
0x180025305  inc     r8d
0x180025308  cmp     r8d, [rdx+4]
0x18002530c  jb      short loc_1800252E4
0x18002530e  mov     r12d, r13d
0x180025311  cmp     [rdi+14h], r13d
0x180025315  jl      short loc_180025325
0x180025317  mov     eax, [rbx+28h]
0x18002531a  shr     eax, 0Dh
0x18002531d  and     al, 1
0x18002531f  mov     [rdi+0B0h], al
0x180025325  mov     rcx, [rbx+10h]
0x180025329  mov     [rsp+68h+var_30], r14
0x18002532e  mov     [rsp+68h+var_38], r15
0x180025333  cmp     rsi, rcx
0x180025336  jb      loc_1800255AC
0x18002533c  test    rcx, rcx
0x18002533f  jz      short loc_180025348
0x180025341  add     rcx, rbx
0x180025344  mov     [rbx+10h], rcx
0x180025348  mov     rdx, rcx
0x18002534b  test    rcx, rcx
0x18002534e  jz      loc_18002542E
0x180025354  mov     rax, [rcx+8]
0x180025358  cmp     rsi, rax
0x18002535b  jb      loc_1800255AC
0x180025361  test    rax, rax
0x180025364  jz      short loc_180025371
0x180025366  add     rax, rbx
0x180025369  mov     [rcx+8], rax
0x18002536d  mov     rdx, [rbx+10h]
0x180025371  cmp     [rdx+8], r13
0x180025375  jz      short loc_1800253AD
0x180025377  mov     r8d, r13d
0x18002537a  cmp     r8d, [rdx+4]
0x18002537e  jnb     short loc_1800253AD
0x180025380  mov     r9d, r8d
0x180025383  shl     r9, 4
0x180025387  add     r9, [rdx+8]
0x18002538b  mov     rax, [r9+8]
0x18002538f  cmp     rsi, rax
0x180025392  jb      loc_1800255AC
0x180025398  test    rax, rax
0x18002539b  jz      short loc_1800253A8
0x18002539d  add     rax, rbx
0x1800253a0  mov     [r9+8], rax
0x1800253a4  mov     rdx, [rbx+10h]
0x1800253a8  inc     r8d
0x1800253ab  jmp     short loc_18002537A
0x1800253ad  mov     r8, [rdi+68h]
0x1800253b1  mov     ecx, [r8+4]
0x1800253b5  cmp     ecx, [rdx+4]
0x1800253b8  jb      short loc_18002542E
0x1800253ba  test    dword ptr [rdi+58h], 100h
0x1800253c1  jnz     loc_180025680
0x1800253c7  mov     esi, r13d
0x1800253ca  mov     rax, [rbx+10h]
0x1800253ce  cmp     esi, [rax+4]
0x1800253d1  jnb     short loc_18002542E
0x1800253d3  mov     r14, [rax+8]
0x1800253d7  mov     rax, [rdi+68h]
0x1800253db  mov     edx, esi
0x1800253dd  shl     rdx, 4
0x1800253e1  add     r14, rdx
0x1800253e4  mov     r15, [rax+8]
0x1800253e8  add     r15, rdx
0x1800253eb  cmp     [r14+8], r13
0x1800253ef  jnz     short loc_180025403
0x1800253f1  mov     eax, [r14+4]
0x1800253f5  inc     esi
0x1800253f7  mov     [r15+4], eax
0x1800253fb  mov     eax, [r14]
0x1800253fe  mov     [r15], eax
0x180025401  jmp     short loc_1800253CA
0x180025403  test    dword ptr [rdi+58h], 100h
0x18002540a  jnz     loc_1800256B8
0x180025410  mov     eax, [r14]
0x180025413  cmp     [r15], eax
0x180025416  jb      loc_1800255AC
0x18002541c  mov     r8d, [r14]; Size
0x18002541f  mov     rdx, [r14+8]; Src
0x180025423  mov     rcx, [r15+8]; void *
0x180025427  call    memmove
0x18002542c  jmp     short loc_1800253F1
0x18002542e  movups  xmm0, xmmword ptr [rdi+0B8h]
0x180025435  mov     [rsp+68h+arg_8], rbp
0x18002543a  movaps  [rsp+68h+var_48], xmm0
0x18002543f  cmp     [rdi+14h], r13d
0x180025443  jl      loc_18002556F
0x180025449  lea     rsi, [rdi+38h]
0x18002544d  mov     rbx, [rdi+60h]
0x180025451  cmp     [rdi+0B0h], r13b
0x180025458  jz      loc_18002558E
0x18002545e  mov     r14, [rbx+8]
0x180025462  mov     r15d, [rdi+0C8h]
0x180025469  test    r14, r14
0x18002546c  jz      loc_180025614
0x180025472  mov     rbp, [rbx]
0x180025475  test    rbp, rbp
0x180025478  jz      loc_180025614
0x18002547e  mov     [rsp+68h+arg_18], r13
0x180025486  test    rbx, rbx
0x180025489  jz      loc_180025640
0x18002548f  lea     rcx, [rsp+68h+arg_0]; this
0x180025494  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180025499  lea     rcx, [rsp+68h+arg_0]; this
0x18002549e  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800254a3  lea     rcx, [rsp+68h+arg_0]; this
0x1800254a8  test    al, al
0x1800254aa  jz      loc_180025605
0x1800254b0  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800254b5  mov     rcx, rax
0x1800254b8  cmp     [rax+1C8h], r13
0x1800254bf  jz      loc_1800255B3
0x1800254c5  mov     eax, [rax+1D0h]
0x1800254cb  cmp     rbp, rax
0x1800254ce  jnb     loc_18002564A
0x1800254d4  lfence
0x1800254d7  mov     rax, [rcx+1C8h]
0x1800254de  mov     rcx, [rax+rbp*8]
0x1800254e2  test    rcx, rcx
0x1800254e5  jz      loc_18002570E
0x1800254eb  mov     rax, [rcx+10h]
0x1800254ef  test    rax, rax
0x1800254f2  jnz     short loc_180025532
0x1800254f4  lea     rcx, [rsp+68h+arg_0]; this
0x1800254f9  mov     ebp, 80090302h
0x1800254fe  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180025503  jmp     short loc_180025567
0x180025505  mov     ecx, [rdi+0B8h]; unsigned int
0x18002550b  call    SecAllocateForcePool
0x180025510  mov     [rdi+0C0h], rax
0x180025517  test    rax, rax
0x18002551a  jnz     loc_180025263
0x180025520  mov     eax, 0C000009Ah
0x180025525  add     rsp, 40h
0x180025529  pop     r13
0x18002552b  pop     r12
0x18002552d  pop     rdi
0x18002552e  pop     rsi
0x18002552f  pop     rbx
0x180025530  retn
0x180025532  lea     r8, [rsp+68h+arg_18]
0x18002553a  mov     rcx, r14
0x18002553d  lea     rdx, [rsp+68h+var_48]
0x180025542  call    _guard_dispatch_icall
0x180025547  lea     rcx, [rsp+68h+arg_0]; this
0x18002554c  mov     ebp, eax
0x18002554e  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180025553  test    ebp, ebp
0x180025555  js      loc_180025619
0x18002555b  mov     rax, [rsp+68h+arg_18]
0x180025563  mov     [rbx+8], rax
0x180025567  test    ebp, ebp
0x180025569  js      loc_180025619
0x18002556f  mov     rbp, [rsp+68h+arg_8]
0x180025574  mov     eax, r12d
0x180025577  mov     r14, [rsp+68h+var_30]
0x18002557c  mov     r15, [rsp+68h+var_38]
0x180025581  add     rsp, 40h
0x180025585  pop     r13
0x180025587  pop     r12
0x180025589  pop     rdi
0x18002558a  pop     rsi
0x18002558b  pop     rbx
0x18002558c  retn
0x18002558e  test    rsi, rsi
0x180025591  jz      short loc_18002556F
0x180025593  mov     rcx, [rdi+88h]
0x18002559a  cmp     [rbx+8], rcx
0x18002559e  jnz     short loc_18002556F
0x1800255a0  movups  xmm0, xmmword ptr [rdi+90h]
0x1800255a7  movups  xmmword ptr [rbx], xmm0
0x1800255aa  jmp     short loc_18002556F
0x1800255ac  mov     eax, 0C0000023h
0x1800255b1  jmp     short loc_180025577
0x1800255b3  lea     rcx, [rsp+68h+arg_0]; this
0x1800255b8  mov     ebp, 0C0000001h
0x1800255bd  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800255c2  jmp     short loc_180025567
0x1800255c4  mov     rax, [rdi+50h]
0x1800255c8  add     r9, r9
0x1800255cb  mov     rcx, [rax+8]
0x1800255cf  mov     [rcx+r9*8+4], r10d
0x1800255d4  mov     rax, [rdi+50h]
0x1800255d8  mov     rcx, [rax+8]
0x1800255dc  mov     eax, [rdx]
0x1800255de  mov     [rcx+r9*8], eax
0x1800255e2  jmp     loc_180025301
0x1800255e7  mov     eax, 0C0000023h
0x1800255ec  add     rsp, 40h
0x1800255f0  pop     r13
0x1800255f2  pop     r12
0x1800255f4  pop     rdi
0x1800255f5  pop     rsi
0x1800255f6  pop     rbx
0x1800255f7  retn
0x1800255f9  add     rcx, rbx
0x1800255fc  mov     [rbx+18h], rcx
0x180025600  jmp     loc_180025299
0x180025605  mov     ebp, 0C00002FEh
0x18002560a  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002560f  jmp     loc_180025567
0x180025614  mov     ebp, 80090300h
0x180025619  test    rsi, rsi
0x18002561c  jz      short loc_180025624
0x18002561e  test    r15b, 20h
0x180025622  jz      short loc_180025638
0x180025624  mov     r8, rbx
0x180025627  xor     ecx, ecx
0x180025629  call    DeleteSecurityContextInternal
0x18002562e  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180025635  movups  xmmword ptr [rbx], xmm0
0x180025638  mov     [rdi+14h], ebp
0x18002563b  jmp     loc_18002556F
0x180025640  mov     ebp, 0C000000Dh
0x180025645  jmp     loc_180025567
  ... truncated ...
```
