# ProcessSecurityContextUnMarshalResponse

- ea: `0x180025220`
- end: `0x180025772`
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
- `0x180010980`
- `0x180010a00`
- `0x180025220`
- `0x180025e00`

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
0x180025220  push    rbx
0x180025222  push    rsi
0x180025223  push    rdi
0x180025224  push    r12
0x180025226  push    r13
0x180025228  sub     rsp, 40h
0x18002522c  mov     rbx, rdx
0x18002522f  mov     rdi, rcx
0x180025232  cmp     r8d, 50h ; 'P'
0x180025236  jb      loc_180025637
0x18002523c  mov     rdx, [rcx+60h]
0x180025240  mov     rax, [rbx+30h]
0x180025244  mov     esi, r8d
0x180025247  mov     [rdx], rax
0x18002524a  mov     rax, [rbx+38h]
0x18002524e  mov     [rdx+8], rax
0x180025252  mov     rdx, [rcx+70h]
0x180025256  mov     eax, [rbx+40h]
0x180025259  mov     [rdx], eax
0x18002525b  mov     rcx, [rbx+20h]
0x18002525f  cmp     rsi, rcx
0x180025262  jb      loc_180025637
0x180025268  test    rcx, rcx
0x18002526b  jz      short loc_180025274
0x18002526d  add     rcx, rbx
0x180025270  mov     [rbx+20h], rcx
0x180025274  mov     rdx, rcx
0x180025277  test    rcx, rcx
0x18002527a  jz      short loc_1800252C6
0x18002527c  mov     rax, [rcx+8]
0x180025280  cmp     rsi, rax
0x180025283  jb      loc_180025637
0x180025289  test    rax, rax
0x18002528c  jz      short loc_180025299
0x18002528e  add     rax, rbx
0x180025291  mov     [rcx+8], rax
0x180025295  mov     rdx, [rbx+20h]
0x180025299  movups  xmm0, xmmword ptr [rdx]
0x18002529c  movups  xmmword ptr [rdi+0B8h], xmm0
0x1800252a3  mov     rax, [rdi+0C0h]
0x1800252aa  test    rax, rax
0x1800252ad  jnz     loc_180025555
0x1800252b3  mov     rdx, [rbx+20h]
0x1800252b7  mov     rcx, rax; void *
0x1800252ba  mov     r8d, [rdx]; Size
0x1800252bd  mov     rdx, [rdx+8]; Src
0x1800252c1  call    memmove
0x1800252c6  mov     rcx, [rdi+78h]
0x1800252ca  test    rcx, rcx
0x1800252cd  jnz     loc_1800256AE
0x1800252d3  mov     rcx, [rbx+18h]
0x1800252d7  cmp     rsi, rcx
0x1800252da  jb      loc_180025637
0x1800252e0  test    rcx, rcx
0x1800252e3  jnz     loc_180025649
0x1800252e9  xor     r13d, r13d
0x1800252ec  mov     rdx, rcx
0x1800252ef  test    rcx, rcx
0x1800252f2  jz      short loc_18002535E
0x1800252f4  mov     r8, [rdi+50h]
0x1800252f8  test    r8, r8
0x1800252fb  jz      loc_1800256BA
0x180025301  mov     eax, [rcx+4]
0x180025304  cmp     [r8+4], eax
0x180025308  jb      loc_1800256C5
0x18002530e  mov     rax, [rcx+8]
0x180025312  cmp     rsi, rax
0x180025315  jb      loc_180025637
0x18002531b  test    rax, rax
0x18002531e  jz      short loc_18002532B
0x180025320  add     rax, rbx
0x180025323  mov     [rcx+8], rax
0x180025327  mov     rdx, [rbx+18h]
0x18002532b  cmp     [rdx+4], r13d
0x18002532f  jbe     short loc_18002535E
0x180025331  mov     r8d, r13d
0x180025334  mov     rax, [rdx+8]
0x180025338  mov     r9d, r8d
0x18002533b  mov     r10d, [rax+r9*8+4]
0x180025340  lea     rdx, [rax+r9*8]
0x180025344  lea     eax, [r10-4]
0x180025348  cmp     eax, 1
0x18002534b  jbe     loc_180025614
0x180025351  mov     rdx, [rbx+18h]
0x180025355  inc     r8d
0x180025358  cmp     r8d, [rdx+4]
0x18002535c  jb      short loc_180025334
0x18002535e  mov     r12d, r13d
0x180025361  cmp     [rdi+14h], r13d
0x180025365  jl      short loc_180025375
0x180025367  mov     eax, [rbx+28h]
0x18002536a  shr     eax, 0Dh
0x18002536d  and     al, 1
0x18002536f  mov     [rdi+0B0h], al
0x180025375  mov     rcx, [rbx+10h]
0x180025379  mov     [rsp+68h+var_30], r14
0x18002537e  mov     [rsp+68h+var_38], r15
0x180025383  cmp     rsi, rcx
0x180025386  jb      loc_1800255FC
0x18002538c  test    rcx, rcx
0x18002538f  jz      short loc_180025398
0x180025391  add     rcx, rbx
0x180025394  mov     [rbx+10h], rcx
0x180025398  mov     rdx, rcx
0x18002539b  test    rcx, rcx
0x18002539e  jz      loc_18002547E
0x1800253a4  mov     rax, [rcx+8]
0x1800253a8  cmp     rsi, rax
0x1800253ab  jb      loc_1800255FC
0x1800253b1  test    rax, rax
0x1800253b4  jz      short loc_1800253C1
0x1800253b6  add     rax, rbx
0x1800253b9  mov     [rcx+8], rax
0x1800253bd  mov     rdx, [rbx+10h]
0x1800253c1  cmp     [rdx+8], r13
0x1800253c5  jz      short loc_1800253FD
0x1800253c7  mov     r8d, r13d
0x1800253ca  cmp     r8d, [rdx+4]
0x1800253ce  jnb     short loc_1800253FD
0x1800253d0  mov     r9d, r8d
0x1800253d3  shl     r9, 4
0x1800253d7  add     r9, [rdx+8]
0x1800253db  mov     rax, [r9+8]
0x1800253df  cmp     rsi, rax
0x1800253e2  jb      loc_1800255FC
0x1800253e8  test    rax, rax
0x1800253eb  jz      short loc_1800253F8
0x1800253ed  add     rax, rbx
0x1800253f0  mov     [r9+8], rax
0x1800253f4  mov     rdx, [rbx+10h]
0x1800253f8  inc     r8d
0x1800253fb  jmp     short loc_1800253CA
0x1800253fd  mov     r8, [rdi+68h]
0x180025401  mov     ecx, [r8+4]
0x180025405  cmp     ecx, [rdx+4]
0x180025408  jb      short loc_18002547E
0x18002540a  test    dword ptr [rdi+58h], 100h
0x180025411  jnz     loc_1800256D0
0x180025417  mov     esi, r13d
0x18002541a  mov     rax, [rbx+10h]
0x18002541e  cmp     esi, [rax+4]
0x180025421  jnb     short loc_18002547E
0x180025423  mov     r14, [rax+8]
0x180025427  mov     rax, [rdi+68h]
0x18002542b  mov     edx, esi
0x18002542d  shl     rdx, 4
0x180025431  add     r14, rdx
0x180025434  mov     r15, [rax+8]
0x180025438  add     r15, rdx
0x18002543b  cmp     [r14+8], r13
0x18002543f  jnz     short loc_180025453
0x180025441  mov     eax, [r14+4]
0x180025445  inc     esi
0x180025447  mov     [r15+4], eax
0x18002544b  mov     eax, [r14]
0x18002544e  mov     [r15], eax
0x180025451  jmp     short loc_18002541A
0x180025453  test    dword ptr [rdi+58h], 100h
0x18002545a  jnz     loc_180025708
0x180025460  mov     eax, [r14]
0x180025463  cmp     [r15], eax
0x180025466  jb      loc_1800255FC
0x18002546c  mov     r8d, [r14]; Size
0x18002546f  mov     rdx, [r14+8]; Src
0x180025473  mov     rcx, [r15+8]; void *
0x180025477  call    memmove
0x18002547c  jmp     short loc_180025441
0x18002547e  movups  xmm0, xmmword ptr [rdi+0B8h]
0x180025485  mov     [rsp+68h+arg_8], rbp
0x18002548a  movaps  [rsp+68h+var_48], xmm0
0x18002548f  cmp     [rdi+14h], r13d
0x180025493  jl      loc_1800255BF
0x180025499  lea     rsi, [rdi+38h]
0x18002549d  mov     rbx, [rdi+60h]
0x1800254a1  cmp     [rdi+0B0h], r13b
0x1800254a8  jz      loc_1800255DE
0x1800254ae  mov     r14, [rbx+8]
0x1800254b2  mov     r15d, [rdi+0C8h]
0x1800254b9  test    r14, r14
0x1800254bc  jz      loc_180025664
0x1800254c2  mov     rbp, [rbx]
0x1800254c5  test    rbp, rbp
0x1800254c8  jz      loc_180025664
0x1800254ce  mov     [rsp+68h+arg_18], r13
0x1800254d6  test    rbx, rbx
0x1800254d9  jz      loc_180025690
0x1800254df  lea     rcx, [rsp+68h+arg_0]; this
0x1800254e4  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800254e9  lea     rcx, [rsp+68h+arg_0]; this
0x1800254ee  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800254f3  lea     rcx, [rsp+68h+arg_0]; this
0x1800254f8  test    al, al
0x1800254fa  jz      loc_180025655
0x180025500  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180025505  mov     rcx, rax
0x180025508  cmp     [rax+1C8h], r13
0x18002550f  jz      loc_180025603
0x180025515  mov     eax, [rax+1D0h]
0x18002551b  cmp     rbp, rax
0x18002551e  jnb     loc_18002569A
0x180025524  lfence
0x180025527  mov     rax, [rcx+1C8h]
0x18002552e  mov     rcx, [rax+rbp*8]
0x180025532  test    rcx, rcx
0x180025535  jz      loc_18002575E
0x18002553b  mov     rax, [rcx+10h]
0x18002553f  test    rax, rax
0x180025542  jnz     short loc_180025582
0x180025544  lea     rcx, [rsp+68h+arg_0]; this
0x180025549  mov     ebp, 80090302h
0x18002554e  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180025553  jmp     short loc_1800255B7
0x180025555  mov     ecx, [rdi+0B8h]; unsigned int
0x18002555b  call    SecAllocateForcePool
0x180025560  mov     [rdi+0C0h], rax
0x180025567  test    rax, rax
0x18002556a  jnz     loc_1800252B3
0x180025570  mov     eax, 0C000009Ah
0x180025575  add     rsp, 40h
0x180025579  pop     r13
0x18002557b  pop     r12
0x18002557d  pop     rdi
0x18002557e  pop     rsi
0x18002557f  pop     rbx
0x180025580  retn
0x180025582  lea     r8, [rsp+68h+arg_18]
0x18002558a  mov     rcx, r14
0x18002558d  lea     rdx, [rsp+68h+var_48]
0x180025592  call    _guard_dispatch_icall
0x180025597  lea     rcx, [rsp+68h+arg_0]; this
0x18002559c  mov     ebp, eax
0x18002559e  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800255a3  test    ebp, ebp
0x1800255a5  js      loc_180025669
0x1800255ab  mov     rax, [rsp+68h+arg_18]
0x1800255b3  mov     [rbx+8], rax
0x1800255b7  test    ebp, ebp
0x1800255b9  js      loc_180025669
0x1800255bf  mov     rbp, [rsp+68h+arg_8]
0x1800255c4  mov     eax, r12d
0x1800255c7  mov     r14, [rsp+68h+var_30]
0x1800255cc  mov     r15, [rsp+68h+var_38]
0x1800255d1  add     rsp, 40h
0x1800255d5  pop     r13
0x1800255d7  pop     r12
0x1800255d9  pop     rdi
0x1800255da  pop     rsi
0x1800255db  pop     rbx
0x1800255dc  retn
0x1800255de  test    rsi, rsi
0x1800255e1  jz      short loc_1800255BF
0x1800255e3  mov     rcx, [rdi+88h]
0x1800255ea  cmp     [rbx+8], rcx
0x1800255ee  jnz     short loc_1800255BF
0x1800255f0  movups  xmm0, xmmword ptr [rdi+90h]
0x1800255f7  movups  xmmword ptr [rbx], xmm0
0x1800255fa  jmp     short loc_1800255BF
0x1800255fc  mov     eax, 0C0000023h
0x180025601  jmp     short loc_1800255C7
0x180025603  lea     rcx, [rsp+68h+arg_0]; this
0x180025608  mov     ebp, 0C0000001h
0x18002560d  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180025612  jmp     short loc_1800255B7
0x180025614  mov     rax, [rdi+50h]
0x180025618  add     r9, r9
0x18002561b  mov     rcx, [rax+8]
0x18002561f  mov     [rcx+r9*8+4], r10d
0x180025624  mov     rax, [rdi+50h]
0x180025628  mov     rcx, [rax+8]
0x18002562c  mov     eax, [rdx]
0x18002562e  mov     [rcx+r9*8], eax
0x180025632  jmp     loc_180025351
0x180025637  mov     eax, 0C0000023h
0x18002563c  add     rsp, 40h
0x180025640  pop     r13
0x180025642  pop     r12
0x180025644  pop     rdi
0x180025645  pop     rsi
0x180025646  pop     rbx
0x180025647  retn
0x180025649  add     rcx, rbx
0x18002564c  mov     [rbx+18h], rcx
0x180025650  jmp     loc_1800252E9
0x180025655  mov     ebp, 0C00002FEh
0x18002565a  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002565f  jmp     loc_1800255B7
0x180025664  mov     ebp, 80090300h
0x180025669  test    rsi, rsi
0x18002566c  jz      short loc_180025674
0x18002566e  test    r15b, 20h
0x180025672  jz      short loc_180025688
0x180025674  mov     r8, rbx
0x180025677  xor     ecx, ecx
0x180025679  call    DeleteSecurityContextInternal
0x18002567e  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180025685  movups  xmmword ptr [rbx], xmm0
0x180025688  mov     [rdi+14h], ebp
0x18002568b  jmp     loc_1800255BF
0x180025690  mov     ebp, 0C000000Dh
0x180025695  jmp     loc_1800255B7
  ... truncated ...
```
