# UpdateDhcpContextWithOptions

- ea: `0x180026278`
- end: `0x18002684f`
- name: `UpdateDhcpContextWithOptions`
- size: `1495`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180014590`
- `0x180020d50`
- `0x180021150`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18000e6e4`
- `0x180018864`
- `0x180026278`
- `0x18003098c`
- `0x1800337d0`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180026410`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180026410`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800262db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800262db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800267da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800267da`
- `WS2_32!__imp_htonl` at `0x180026402`
- `WS2_32!__imp_htonl` at `0x180026402`

## pseudocode

```c
void __fastcall UpdateDhcpContextWithOptions(__int64 a1, __int64 a2)
{
  RTL_SRWLOCK *v4; // r13
  _QWORD *v5; // rdx
  int v6; // r8d
  unsigned int v7; // r12d
  void *v8; // rax
  _BYTE *v9; // rax
  int v10; // eax
  _QWORD *v11; // r13
  __int64 v12; // r15
  _QWORD *v13; // rsi
  unsigned int v14; // r14d
  __int64 v15; // rcx
  void *v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // r10
  unsigned int v19; // r9d
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  unsigned int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // r14d
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // r14
  _QWORD *v32; // r15
  _QWORD *v33; // rsi
  __int64 v34; // rcx
  void *v35; // rax
  unsigned int v36; // ecx
  __int128 v37; // [rsp+20h] [rbp-68h] BYREF
  __int64 v38; // [rsp+90h] [rbp+8h]

  v37 = 0;
  if ( !a1 || !a2 )
  {
    v7 = 87;
LABEL_84:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 58, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v7);
    return;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 55, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
  v4 = (RTL_SRWLOCK *)(a1 + 608);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 608));
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 56, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
  *((_QWORD *)&v37 + 1) = &v37;
  *(_QWORD *)&v37 = &v37;
  Dhcpv6GetExpiredOptions((time_t *)(a1 + 632), (__int64)&v37);
  v7 = Dhcpv6DestroyOptionsList(&v37, v5, v6);
  if ( *(_QWORD *)(a2 + 120) )
  {
    *(_DWORD *)(a1 + 556) = 1;
    *(_OWORD *)(a1 + 140) = *(_OWORD *)*(_QWORD *)(a2 + 120);
  }
  if ( *(_DWORD *)(a2 + 40) )
  {
    if ( *(_DWORD *)(a1 + 488) )
      DhcpFree(a1 + 480);
    v8 = (void *)DhcpAlloc(*(unsigned int *)(a2 + 40));
    *(_QWORD *)(a1 + 480) = v8;
    if ( !v8 )
    {
      v7 = 8;
      goto LABEL_79;
    }
    memcpy_0(v8, *(const void **)(a2 + 32), *(unsigned int *)(a2 + 40));
    *(_DWORD *)(a1 + 488) = *(_DWORD *)(a2 + 40);
  }
  v9 = *(_BYTE **)(a2 + 112);
  v38 = 0;
  if ( v9 )
    *(_BYTE *)(a1 + 554) = *v9;
  v10 = g_fVelocityDhcpv6ContextBitfieldUpdate;
  if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    *(_DWORD *)(a1 + 8868) = 1;
  else
    *(_DWORD *)(a1 + 8860) |= 2u;
  if ( v10 )
    *(_DWORD *)(a1 + 8884) = 0;
  else
    *(_DWORD *)(a1 + 8860) &= ~0x40u;
  htonl(0xE10u);
  _time64(0);
  if ( *(_DWORD *)(a2 + 48) )
  {
    v11 = (_QWORD *)(a1 + 104);
    v12 = 0;
    do
    {
      v13 = (_QWORD *)*v11;
      if ( (_QWORD *)*v11 != v11 )
      {
        while ( *((_DWORD *)v13 + 8) != *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 32LL) )
        {
          v13 = (_QWORD *)*v13;
          if ( v13 == v11 )
            goto LABEL_61;
        }
        v14 = 0;
        *((_DWORD *)v13 + 8) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 32LL);
        *((_DWORD *)v13 + 12) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 48LL);
        if ( *((_DWORD *)v13 + 13) && v13[5] )
        {
          DhcpFree(v13 + 5);
          *((_DWORD *)v13 + 13) = 0;
        }
        v15 = *(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12);
        if ( *(_DWORD *)(v15 + 52) )
        {
          if ( *(_QWORD *)(v15 + 40) )
          {
            v16 = (void *)DhcpAlloc(*(unsigned int *)(v15 + 52));
            v13[5] = v16;
            if ( v16 )
            {
              v17 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 52LL);
              *((_DWORD *)v13 + 13) = v17;
              memcpy_0(v16, *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 40LL), v17);
            }
          }
        }
        v13[2] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 16LL);
        v13[3] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 24LL);
        *((_DWORD *)v13 + 9) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 36LL);
        v18 = *(_QWORD *)(a2 + 80);
        if ( *(_DWORD *)(*(_QWORD *)(v18 + 8 * v12) + 36LL) )
        {
          v19 = 0;
          do
          {
            if ( v19 >= 2 )
              break;
            v20 = v19++;
            v21 = 7 * v20;
            *(_OWORD *)&v13[v21 + 7] = *(_OWORD *)(*(_QWORD *)(v18 + 8 * v12) + 56 * v20 + 56);
            LODWORD(v13[v21 + 13]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 56 * v20 + 104);
            LODWORD(v13[v21 + 9]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 56 * v20 + 72);
            HIDWORD(v13[v21 + 9]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 56 * v20 + 76);
            v13[v21 + 11] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 56 * v20 + 88);
            v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8 * v12) + 56 * v20 + 80);
            v13[v21 + 10] = v22;
            *(_QWORD *)(a1 + 536) = v22;
            v23 = HIDWORD(v13[v21 + 9]);
            v18 = *(_QWORD *)(a2 + 80);
            v24 = *(_QWORD *)(v18 + 8 * v12);
            v25 = *(_QWORD *)(v24 + v21 * 8 + 88);
            if ( v38 >= v25 )
              v25 = v38;
            v38 = v25;
            if ( v14 <= v23 )
              v23 = v14;
            v14 = v23;
          }
          while ( v19 < *(_DWORD *)(v24 + 36) );
        }
        if ( !v13[3] )
        {
          if ( v14 == -1 )
            v26 = -1;
          else
            v26 = (int)(float)((float)(int)v14 * 0.875);
          v27 = v13[2];
          v13[3] = v26;
          if ( v26 <= v27 )
            v13[3] = (v27 + v14) / 2;
          if ( !v27 )
          {
            if ( v14 == -1 )
              v28 = -1;
            else
              v28 = v14 >> 1;
            v13[2] = v28;
          }
        }
        v29 = *(_DWORD *)(a1 + 536);
        if ( (unsigned int)(*((_DWORD *)v13 + 4) + v29) < *((_DWORD *)v13 + 4) )
          v30 = 0x7FFFFFFFFFFFFFFFLL;
        else
          v30 = v13[2] + *(_QWORD *)(a1 + 536);
        *(_QWORD *)(a1 + 520) = v30;
        if ( (unsigned int)(*((_DWORD *)v13 + 6) + v29) < *((_DWORD *)v13 + 6) )
          *(_QWORD *)(a1 + 528) = 0x7FFFFFFFFFFFFFFFLL;
        else
          *(_QWORD *)(a1 + 528) = *(_QWORD *)(a1 + 536) + v13[3];
      }
LABEL_61:
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < *(_DWORD *)(a2 + 48) );
    v4 = (RTL_SRWLOCK *)(a1 + 608);
  }
  if ( *(_DWORD *)(a2 + 52) )
  {
    v31 = 0;
    v32 = (_QWORD *)(a1 + 120);
    do
    {
      v33 = (_QWORD *)*v32;
      if ( (_QWORD *)*v32 != v32 )
      {
        while ( *((_DWORD *)v33 + 22) != *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 88LL) )
        {
          v33 = (_QWORD *)*v33;
          if ( v33 == v32 )
            goto LABEL_77;
        }
        *((_DWORD *)v33 + 22) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 88LL);
        *((_DWORD *)v33 + 20) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 80LL);
        if ( *((_DWORD *)v33 + 21) && v33[9] )
        {
          *((_DWORD *)v33 + 21) = 0;
          DhcpFree(v33 + 9);
        }
        v34 = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31);
        if ( *(_DWORD *)(v34 + 84) )
        {
          if ( *(_QWORD *)(v34 + 72) )
          {
            v35 = (void *)DhcpAlloc(*(unsigned int *)(v34 + 84));
            v33[9] = v35;
            if ( v35 )
            {
              v36 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 84LL);
              *((_DWORD *)v33 + 21) = v36;
              memcpy_0(v35, *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 72LL), v36);
            }
          }
        }
        *((_OWORD *)v33 + 1) = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 16LL);
        *((_DWORD *)v33 + 8) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 32LL);
        *((_DWORD *)v33 + 9) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 36LL);
        v33[6] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 48LL);
        v33[5] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v31) + 40LL);
      }
LABEL_77:
      v31 = (unsigned int)(v31 + 1);
    }
    while ( (unsigned int)v31 < *(_DWORD *)(a2 + 52) );
  }
  *(_QWORD *)(a1 + 512) = v38;
LABEL_79:
  ReleaseSRWLockExclusive(v4);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 57, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
  if ( v7 )
    goto LABEL_84;
}

```

## disassembly

```asm
0x180026278  push    rbx
0x18002627a  push    rbp
0x18002627b  push    rsi
0x18002627c  push    rdi
0x18002627d  push    r12
0x18002627f  push    r13
0x180026281  push    r14
0x180026283  push    r15
0x180026285  sub     rsp, 48h
0x180026289  movaps  [rsp+88h+var_58], xmm6
0x18002628e  xorps   xmm0, xmm0
0x180026291  mov     rbx, rdx
0x180026294  mov     rdi, rcx
0x180026297  movups  [rsp+88h+var_68], xmm0
0x18002629c  test    rcx, rcx
0x18002629f  jz      loc_180026810
0x1800262a5  test    rdx, rdx
0x1800262a8  jz      loc_180026810
0x1800262ae  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800262b5  jz      short loc_1800262D1
0x1800262b7  mov     r9, [rdi+38h]
0x1800262bb  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800262c2  mov     edx, 37h ; '7'
0x1800262c7  mov     ecx, 404h
0x1800262cc  call    WPP_SF_S
0x1800262d1  lea     r13, [rdi+260h]
0x1800262d8  mov     rcx, r13; SRWLock
0x1800262db  call    cs:__imp_AcquireSRWLockExclusive
0x1800262e2  nop     dword ptr [rax+rax+00h]
0x1800262e7  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800262ee  jz      short loc_18002630A
0x1800262f0  mov     r9, [rdi+38h]
0x1800262f4  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800262fb  mov     edx, 38h ; '8'
0x180026300  mov     ecx, 404h
0x180026305  call    WPP_SF_S
0x18002630a  lea     rax, [rsp+88h+var_68]
0x18002630f  mov     qword ptr [rsp+88h+var_68+8], rax
0x180026314  lea     rcx, [rdi+278h]
0x18002631b  lea     rax, [rsp+88h+var_68]
0x180026320  lea     rdx, [rsp+88h+var_68]
0x180026325  mov     qword ptr [rsp+88h+var_68], rax
0x18002632a  call    Dhcpv6GetExpiredOptions
0x18002632f  lea     rcx, [rsp+88h+var_68]
0x180026334  call    Dhcpv6DestroyOptionsList
0x180026339  cmp     qword ptr [rbx+78h], 0
0x18002633e  mov     r12d, eax
0x180026341  jz      short loc_18002635C
0x180026343  mov     dword ptr [rdi+22Ch], 1
0x18002634d  mov     rax, [rbx+78h]
0x180026351  movups  xmm0, xmmword ptr [rax]
0x180026354  movdqu  xmmword ptr [rdi+8Ch], xmm0
0x18002635c  cmp     dword ptr [rbx+28h], 0
0x180026360  jz      short loc_1800263AC
0x180026362  cmp     dword ptr [rdi+1E8h], 0
0x180026369  lea     rsi, [rdi+1E0h]
0x180026370  jz      short loc_18002637A
0x180026372  mov     rcx, rsi
0x180026375  call    DhcpFree
0x18002637a  mov     ecx, [rbx+28h]
0x18002637d  call    DhcpAlloc
0x180026382  mov     [rsi], rax
0x180026385  test    rax, rax
0x180026388  jnz     short loc_180026393
0x18002638a  lea     r12d, [rax+8]
0x18002638e  jmp     loc_1800267D7
0x180026393  mov     r8d, [rbx+28h]; Size
0x180026397  mov     rcx, rax; void *
0x18002639a  mov     rdx, [rbx+20h]; Src
0x18002639e  call    memcpy_0
0x1800263a3  mov     eax, [rbx+28h]
0x1800263a6  mov     [rdi+1E8h], eax
0x1800263ac  mov     rax, [rbx+70h]
0x1800263b0  mov     [rsp+88h+arg_0], 0
0x1800263bc  test    rax, rax
0x1800263bf  jz      short loc_1800263C9
0x1800263c1  mov     al, [rax]
0x1800263c3  mov     [rdi+22Ah], al
0x1800263c9  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800263cf  test    eax, eax
0x1800263d1  jz      short loc_1800263DF
0x1800263d3  mov     dword ptr [rdi+22A4h], 1
0x1800263dd  jmp     short loc_1800263E6
0x1800263df  or      dword ptr [rdi+229Ch], 2
0x1800263e6  test    eax, eax
0x1800263e8  jz      short loc_1800263F6
0x1800263ea  mov     dword ptr [rdi+22B4h], 0
0x1800263f4  jmp     short loc_1800263FD
0x1800263f6  and     dword ptr [rdi+229Ch], 0FFFFFFBFh
0x1800263fd  mov     ecx, 0E10h; hostlong
0x180026402  call    cs:__imp_htonl
0x180026409  nop     dword ptr [rax+rax+00h]
0x18002640e  xor     ecx, ecx; Time
0x180026410  call    cs:__imp__time64
0x180026417  nop     dword ptr [rax+rax+00h]
0x18002641c  cmp     dword ptr [rbx+30h], 0
0x180026420  jbe     loc_1800266B5
0x180026426  movss   xmm6, cs:__real@3f600000
0x18002642e  lea     r13, [rdi+68h]
0x180026432  xor     r15d, r15d
0x180026435  mov     rsi, [r13+0]
0x180026439  cmp     rsi, r13
0x18002643c  jz      loc_1800266A1
0x180026442  mov     rax, [rbx+50h]
0x180026446  mov     rcx, [rax+r15*8]
0x18002644a  mov     eax, [rcx+20h]
0x18002644d  cmp     [rsi+20h], eax
0x180026450  jz      short loc_18002645F
0x180026452  mov     rsi, [rsi]
0x180026455  cmp     rsi, r13
0x180026458  jnz     short loc_18002644D
0x18002645a  jmp     loc_1800266A1
0x18002645f  mov     rax, [rbx+50h]
0x180026463  xor     r14d, r14d
0x180026466  mov     rcx, [rax+r15*8]
0x18002646a  mov     eax, [rcx+20h]
0x18002646d  mov     [rsi+20h], eax
0x180026470  mov     rax, [rbx+50h]
0x180026474  mov     rcx, [rax+r15*8]
0x180026478  mov     eax, [rcx+30h]
0x18002647b  mov     [rsi+30h], eax
0x18002647e  cmp     [rsi+34h], r14d
0x180026482  jz      short loc_180026496
0x180026484  lea     rcx, [rsi+28h]
0x180026488  cmp     [rcx], r14
0x18002648b  jz      short loc_180026496
0x18002648d  call    DhcpFree
0x180026492  mov     [rsi+34h], r14d
0x180026496  mov     rax, [rbx+50h]
0x18002649a  mov     rcx, [rax+r15*8]
0x18002649e  cmp     [rcx+34h], r14d
0x1800264a2  jz      short loc_1800264E0
0x1800264a4  cmp     [rcx+28h], r14
0x1800264a8  jz      short loc_1800264E0
0x1800264aa  mov     ecx, [rcx+34h]
0x1800264ad  call    DhcpAlloc
0x1800264b2  mov     [rsi+28h], rax
0x1800264b6  test    rax, rax
0x1800264b9  jz      short loc_1800264E0
0x1800264bb  mov     rcx, [rbx+50h]
0x1800264bf  mov     rdx, [rcx+r15*8]
0x1800264c3  mov     ecx, [rdx+34h]
0x1800264c6  mov     [rsi+34h], ecx
0x1800264c9  mov     r8d, ecx; Size
0x1800264cc  mov     rcx, [rbx+50h]
0x1800264d0  mov     rdx, [rcx+r15*8]
0x1800264d4  mov     rcx, rax; void *
0x1800264d7  mov     rdx, [rdx+28h]; Src
0x1800264db  call    memcpy_0
0x1800264e0  mov     rax, [rbx+50h]
0x1800264e4  mov     rcx, [rax+r15*8]
0x1800264e8  mov     rax, [rcx+10h]
0x1800264ec  mov     [rsi+10h], rax
0x1800264f0  mov     rax, [rbx+50h]
0x1800264f4  mov     rcx, [rax+r15*8]
0x1800264f8  mov     rax, [rcx+18h]
0x1800264fc  mov     [rsi+18h], rax
0x180026500  mov     rax, [rbx+50h]
0x180026504  mov     rcx, [rax+r15*8]
0x180026508  mov     eax, [rcx+24h]
0x18002650b  mov     [rsi+24h], eax
0x18002650e  mov     r10, [rbx+50h]
0x180026512  mov     rax, [r10+r15*8]
0x180026516  cmp     [rax+24h], r14d
0x18002651a  jbe     loc_1800265E8
0x180026520  xor     r9d, r9d
0x180026523  cmp     r9d, 2
0x180026527  jnb     loc_1800265E8
0x18002652d  mov     eax, r9d
0x180026530  inc     r9d
0x180026533  imul    r8, rax, 38h ; '8'
0x180026537  mov     rax, [r10+r15*8]
0x18002653b  movups  xmm0, xmmword ptr [rax+r8+38h]
0x180026541  movdqu  xmmword ptr [r8+rsi+38h], xmm0
0x180026548  mov     rax, [rbx+50h]
0x18002654c  mov     rcx, [rax+r15*8]
0x180026550  mov     eax, [rcx+r8+68h]
0x180026555  mov     [r8+rsi+68h], eax
0x18002655a  mov     rax, [rbx+50h]
0x18002655e  mov     rcx, [rax+r15*8]
0x180026562  mov     eax, [rcx+r8+48h]
0x180026567  mov     [r8+rsi+48h], eax
0x18002656c  mov     rax, [rbx+50h]
0x180026570  mov     rcx, [rax+r15*8]
0x180026574  mov     eax, [rcx+r8+4Ch]
0x180026579  mov     [r8+rsi+4Ch], eax
0x18002657e  mov     rax, [rbx+50h]
0x180026582  mov     rcx, [rax+r15*8]
0x180026586  mov     rax, [rcx+r8+58h]
0x18002658b  mov     [r8+rsi+58h], rax
0x180026590  mov     rax, [rbx+50h]
0x180026594  mov     rcx, [rax+r15*8]
0x180026598  mov     rax, [rcx+r8+50h]
0x18002659d  mov     [r8+rsi+50h], rax
0x1800265a2  mov     [rdi+218h], rax
0x1800265a9  mov     ecx, [r8+rsi+4Ch]
0x1800265ae  mov     r10, [rbx+50h]
0x1800265b2  mov     rdx, [r10+r15*8]
0x1800265b6  mov     rax, [rdx+r8+58h]
0x1800265bb  cmp     [rsp+88h+arg_0], rax
0x1800265c3  cmovge  rax, [rsp+88h+arg_0]
0x1800265cc  cmp     r14d, ecx
0x1800265cf  mov     [rsp+88h+arg_0], rax
0x1800265d7  cmovbe  ecx, r14d
0x1800265db  mov     r14d, ecx
0x1800265de  cmp     r9d, [rdx+24h]
0x1800265e2  jb      loc_180026523
0x1800265e8  cmp     qword ptr [rsi+18h], 0
0x1800265ed  jnz     short loc_18002664B
0x1800265ef  or      r8d, 0FFFFFFFFh
0x1800265f3  cmp     r14d, r8d
0x1800265f6  jnz     short loc_1800265FD
0x1800265f8  mov     eax, r8d
0x1800265fb  jmp     short loc_180026611
0x1800265fd  mov     eax, r14d
0x180026600  xorps   xmm0, xmm0
0x180026603  cvtsi2ss xmm0, rax
0x180026608  mulss   xmm0, xmm6
0x18002660c  cvttss2si rax, xmm0
0x180026611  mov     rcx, [rsi+10h]
0x180026615  mov     eax, eax
0x180026617  mov     [rsi+18h], rax
0x18002661b  cmp     rax, rcx
0x18002661e  jg      short loc_180026632
0x180026620  mov     eax, r14d
0x180026623  add     rax, rcx
0x180026626  cqo
0x180026628  sub     rax, rdx
0x18002662b  sar     rax, 1
0x18002662e  mov     [rsi+18h], rax
0x180026632  test    rcx, rcx
0x180026635  jnz     short loc_18002664B
0x180026637  cmp     r14d, r8d
0x18002663a  jnz     short loc_180026641
0x18002663c  mov     r14d, r8d
0x18002663f  jmp     short loc_180026644
0x180026641  shr     r14d, 1
0x180026644  mov     eax, r14d
0x180026647  mov     [rsi+10h], rax
0x18002664b  mov     ecx, [rsi+10h]
0x18002664e  mov     r8, 7FFFFFFFFFFFFFFFh
0x180026658  mov     edx, [rdi+218h]
0x18002665e  lea     eax, [rcx+rdx]
0x180026661  cmp     eax, ecx
0x180026663  jb      short loc_180026672
0x180026665  mov     rax, [rdi+218h]
0x18002666c  add     rax, [rsi+10h]
0x180026670  jmp     short loc_180026675
0x180026672  mov     rax, r8
0x180026675  mov     [rdi+208h], rax
0x18002667c  mov     ecx, [rsi+18h]
0x18002667f  lea     eax, [rcx+rdx]
0x180026682  cmp     eax, ecx
0x180026684  jb      short loc_18002669A
0x180026686  mov     rax, [rsi+18h]
0x18002668a  add     rax, [rdi+218h]
0x180026691  mov     [rdi+210h], rax
0x180026698  jmp     short loc_1800266A1
0x18002669a  mov     [rdi+210h], r8
0x1800266a1  inc     r15d
0x1800266a4  cmp     r15d, [rbx+30h]
0x1800266a8  jb      loc_180026435
0x1800266ae  lea     r13, [rdi+260h]
0x1800266b5  cmp     dword ptr [rbx+34h], 0
0x1800266b9  jbe     loc_1800267C8
0x1800266bf  xor     r14d, r14d
0x1800266c2  lea     r15, [rdi+78h]
0x1800266c6  mov     rsi, [r15]
0x1800266c9  cmp     rsi, r15
0x1800266cc  jz      loc_1800267BB
0x1800266d2  mov     rax, [rbx+58h]
0x1800266d6  mov     rcx, [rax+r14*8]
0x1800266da  mov     eax, [rcx+58h]
0x1800266dd  cmp     [rsi+58h], eax
0x1800266e0  jz      short loc_1800266EF
0x1800266e2  mov     rsi, [rsi]
0x1800266e5  cmp     rsi, r15
0x1800266e8  jnz     short loc_1800266DD
0x1800266ea  jmp     loc_1800267BB
0x1800266ef  mov     rax, [rbx+58h]
0x1800266f3  xor     edx, edx
0x1800266f5  mov     rcx, [rax+r14*8]
0x1800266f9  mov     eax, [rcx+58h]
0x1800266fc  mov     [rsi+58h], eax
0x1800266ff  mov     rax, [rbx+58h]
0x180026703  mov     rcx, [rax+r14*8]
0x180026707  mov     eax, [rcx+50h]
0x18002670a  mov     [rsi+50h], eax
0x18002670d  cmp     [rsi+54h], edx
0x180026710  jz      short loc_180026725
0x180026712  lea     rcx, [rsi+48h]
0x180026716  cmp     [rcx], rdx
0x180026719  jz      short loc_180026725
0x18002671b  mov     [rsi+54h], edx
0x18002671e  call    DhcpFree
0x180026723  xor     edx, edx
0x180026725  mov     rax, [rbx+58h]
0x180026729  mov     rcx, [rax+r14*8]
0x18002672d  cmp     [rcx+54h], edx
0x180026730  jz      short loc_18002676E
  ... truncated ...
```
