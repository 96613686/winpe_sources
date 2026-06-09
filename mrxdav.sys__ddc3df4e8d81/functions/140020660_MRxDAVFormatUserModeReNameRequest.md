# MRxDAVFormatUserModeReNameRequest

- ea: `0x140020660`
- end: `0x140020e75`
- name: `MRxDAVFormatUserModeReNameRequest`
- size: `2069`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140001b64`
- `0x140002ac4`
- `0x140006900`
- `0x140006c00`
- `0x140020660`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400206d7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020713`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020772`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020800`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020874`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002094e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020a29`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020a71`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020b17`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020baa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020bf2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020ca6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020d0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020d6d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020db0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020de8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020e33`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400206d7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020713`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020772`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020800`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020874`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002094e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020a29`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020a71`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020b17`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020baa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020bf2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020ca6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020d0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020d6d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020db0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020de8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020e33`
- `ntoskrnl!wcschr` at `0x1400208d3`
- `ntoskrnl!wcschr` at `0x1400208d3`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeReNameRequest(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbp
  __int64 v7; // rax
  __int64 v8; // r13
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  unsigned __int8 *v13; // rax
  int v14; // ecx
  __int64 v15; // rdi
  int v16; // ebx
  HANDLE v17; // rax
  _DWORD *v18; // r15
  __int64 v19; // rbx
  ULONG_PTR v20; // r14
  PVOID SecondaryBuffer; // rax
  __int64 v22; // rdi
  unsigned int v23; // edi
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rbx
  unsigned int v27; // eax
  int v28; // r15d
  __int64 v29; // rax
  unsigned __int16 *v30; // r8
  unsigned int v31; // r12d
  wchar_t *v32; // rdi
  unsigned int v33; // edx
  unsigned int v34; // ecx
  size_t v35; // rbx
  char *v36; // rax
  char *v37; // r14
  __int64 v38; // rbx
  HANDLE v39; // rax
  __int64 v40; // rdx
  _WORD *v41; // r9
  _WORD *v42; // rax
  __int64 v43; // r8
  __int64 v44; // rdx
  _WORD *v45; // rcx
  __int64 v46; // rbx
  __int64 v47; // rdi
  unsigned int v48; // eax
  __int64 v49; // rbx
  unsigned int v50; // eax
  unsigned int v51; // ecx
  unsigned int v52; // eax
  size_t v53; // rbx
  char *v54; // rax
  char *v55; // rdi
  char *v56; // rcx
  __int64 v57; // rbx
  unsigned int v58; // eax
  __int64 v59; // rbx
  unsigned int v60; // eax
  __int64 v61; // rdi
  __int64 v62; // rcx
  __int64 v63; // rbx
  __int64 v64; // rax
  ULONG_PTR v65; // rbp
  PVOID v66; // rax
  _WORD *v67; // rdx
  __int64 v68; // rbx
  HANDLE v69; // rax
  __int64 v70; // rbx
  HANDLE v71; // rax
  __int64 v72; // rbx
  HANDLE v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rbx
  HANDLE v76; // rax
  unsigned __int64 v78; // [rsp+30h] [rbp-48h]
  __int64 v80; // [rsp+88h] [rbp+10h]
  wchar_t *Src; // [rsp+90h] [rbp+18h]

  v3 = *(_QWORD **)(a2 + 72);
  if ( v3 )
    v80 = v3[6];
  else
    v80 = 0;
  v7 = v3[4];
  v8 = 0;
  if ( v7 )
    v8 = *(_QWORD *)(v7 + 136);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 50, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqq(v11, 51, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v12, a1, a2);
    }
  }
  v13 = *(unsigned __int8 **)(a2 + 456);
  *(_DWORD *)(a3 + 48) = 9;
  v14 = *v13;
  *(_BYTE *)(a3 + 644) = v14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v16 = v14;
    v17 = PsGetCurrentThreadId();
    WPP_SF_qD(v15, 52, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v17, v16);
  }
  v18 = 0;
  v19 = *(_QWORD *)(*(_QWORD *)(v3[5] + 32LL) + 32LL);
  if ( v19 )
    v18 = *(_DWORD **)(v19 + 32);
  v20 = **(unsigned __int16 **)(v19 + 64) + 2LL;
  SecondaryBuffer = UMRxAllocateSecondaryBuffer(a1, v20);
  v22 = (__int64)SecondaryBuffer;
  if ( SecondaryBuffer )
  {
    memmove(SecondaryBuffer, *(const void **)(*(_QWORD *)(v19 + 64) + 8LL), **(unsigned __int16 **)(v19 + 64));
    *(_WORD *)(v22 + 2 * (v20 >> 1) - 2) = 0;
    *(_QWORD *)(a3 + 648) = v22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v27 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v26, 54, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v27, v22);
    }
    *(_DWORD *)(a3 + 640) = *v18;
    v28 = 2;
    v29 = *(_QWORD *)(v3[4] + 120LL);
    v30 = *(unsigned __int16 **)(v29 + 88);
    v31 = *v30 - **(unsigned __int16 **)(*(_QWORD *)(v29 + 32) + 64LL);
    v32 = wcschr((const wchar_t *)(*((_QWORD *)v30 + 1) + 2LL), 0x5Cu);
    Src = v32;
    v33 = *(unsigned __int16 *)v3[10];
    v34 = v31 + v33 + 2;
    if ( v34 <= v31 || v34 <= v33 )
    {
      v23 = -1073741811;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v23;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_85;
      v72 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v73 = PsGetCurrentThreadId();
      v74 = 55;
    }
    else
    {
      v35 = v34;
      v36 = (char *)UMRxAllocateSecondaryBuffer(a1, v34);
      v37 = v36;
      if ( !v36 )
      {
        v23 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v23;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          goto LABEL_85;
        v38 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v39 = PsGetCurrentThreadId();
        v40 = 56;
        goto LABEL_31;
      }
      memset(v36, 0, v35);
      memmove(v37, v32, v31);
      v78 = (unsigned __int64)v31 >> 1;
      memmove(&v37[2 * v78], *(const void **)(v3[10] + 8LL), *(unsigned __int16 *)v3[10]);
      v41 = (_WORD *)(v8 + 1188);
      v42 = (_WORD *)(a3 + 680);
      v43 = 2147483646;
      v44 = 520;
      *(_WORD *)&v37[2 * (v35 >> 1) - 2] = 0;
      *(_QWORD *)(a3 + 656) = v37;
      do
      {
        if ( !v43 )
          break;
        if ( !*v41 )
          break;
        *v42++ = *v41++;
        --v43;
        --v44;
      }
      while ( v44 );
      v45 = v42 - 1;
      if ( v44 )
        v45 = v42;
      *v45 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v46 = v3[10];
          v47 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v48 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qZ(v47, 57, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v48, v46);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v50 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qS(v49, 58, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v50, (__int64)v37);
        }
      }
      v51 = *(_DWORD *)(v8 + 664);
      if ( *(_WORD *)(v8 + 144) != 92 )
        v28 = 4;
      v52 = v51 + v31 + v28;
      if ( v52 > v31 && v52 > v51 )
      {
        v53 = v52;
        v54 = (char *)UMRxAllocateSecondaryBuffer(a1, v52);
        v55 = v54;
        if ( v54 )
        {
          memset(v54, 0, v53);
          memmove(v55, Src, v31);
          v56 = &v55[2 * v78];
          if ( *(_WORD *)(v8 + 144) != 92 )
          {
            *(_WORD *)v56 = 92;
            v56 += 2;
          }
          memmove(v56, (const void *)(v8 + 144), *(unsigned int *)(v8 + 664));
          *(_WORD *)&v55[2 * (v53 >> 1) - 2] = 0;
          *(_QWORD *)(a3 + 664) = v55;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v57 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v58 = (unsigned int)PsGetCurrentThreadId();
              WPP_SF_qS(v57, 61, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v58, v8 + 144);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v59 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v60 = (unsigned int)PsGetCurrentThreadId();
              WPP_SF_qS(v59, 62, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v60, (__int64)v55);
            }
          }
          v61 = *(_QWORD *)(v3[5] + 40LL);
          *(_DWORD *)(a3 + 632) = *(_DWORD *)(v61 + 80);
          *(_DWORD *)(a3 + 636) = *(_DWORD *)(v61 + 84);
          v62 = *(_QWORD *)(v80 + 48);
          if ( v62 )
          {
            v63 = -1;
            v64 = -1;
            do
              ++v64;
            while ( *(_WORD *)(v62 + 2 * v64) );
            v65 = (unsigned int)(2 * v64 + 2);
            v66 = UMRxAllocateSecondaryBuffer(a1, v65);
            *(_QWORD *)(a3 + 672) = v66;
            if ( !v66 )
            {
              v23 = -1073741670;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v23;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
                goto LABEL_85;
              v38 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v39 = PsGetCurrentThreadId();
              v40 = 63;
              goto LABEL_31;
            }
            memset(v66, 0, v65);
            v67 = *(_WORD **)(v80 + 48);
            do
              ++v63;
            while ( v67[v63] );
            memmove(*(void **)(a3 + 672), v67, 2 * v63);
          }
          if ( !*(_BYTE *)(v61 + 72)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v68 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v69 = PsGetCurrentThreadId();
            WPP_SF_q(v68, 64, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v69);
          }
          v23 = UMRxImpersonateClient((PSECURITY_CLIENT_CONTEXT)v61);
          if ( (v23 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v23;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v70 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v71 = PsGetCurrentThreadId();
              WPP_SF_qD(v70, 65, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v71, v23);
            }
          }
          goto LABEL_85;
        }
        v23 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v23;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          goto LABEL_85;
        v38 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v39 = PsGetCurrentThreadId();
        v40 = 60;
LABEL_31:
        WPP_SF_qD(v38, v40, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v39, -1073741670);
        goto LABEL_85;
      }
      v23 = -1073741811;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v23;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_85;
      v72 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v73 = PsGetCurrentThreadId();
      v74 = 59;
    }
    WPP_SF_qD(v72, v74, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v73, -1073741811);
    goto LABEL_85;
  }
  v23 = -1073741670;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v23;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v25 = PsGetCurrentThreadId();
    WPP_SF_qD(v24, 53, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v25, -1073741670);
  }
LABEL_85:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v75 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v76 = PsGetCurrentThreadId();
    WPP_SF_qD(v75, 66, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v76, v23);
  }
  return v23;
}

```

## disassembly

```asm
0x140020660  mov     [rsp+arg_18], rbx
0x140020665  mov     [rsp+arg_0], rcx
0x14002066a  push    rbp
0x14002066b  push    rsi
0x14002066c  push    rdi
0x14002066d  push    r12
0x14002066f  push    r13
0x140020671  push    r14
0x140020673  push    r15
0x140020675  sub     rsp, 40h
0x140020679  mov     rbp, [rdx+48h]
0x14002067d  xor     r14d, r14d
0x140020680  mov     rsi, r8
0x140020683  mov     rdi, rdx
0x140020686  mov     r12, rcx
0x140020689  test    rbp, rbp
0x14002068c  jnz     short loc_140020698
0x14002068e  mov     [rsp+78h+arg_8], r14
0x140020696  jmp     short loc_1400206A4
0x140020698  mov     rax, [rbp+30h]
0x14002069c  mov     [rsp+78h+arg_8], rax
0x1400206a4  mov     rax, [rbp+20h]
0x1400206a8  mov     r13, r14
0x1400206ab  test    rax, rax
0x1400206ae  jz      short loc_1400206B7
0x1400206b0  mov     r13, [rax+88h]
0x1400206b7  mov     rbx, cs:WPP_GLOBAL_Control
0x1400206be  lea     r15, WPP_GLOBAL_Control
0x1400206c5  cmp     rbx, r15
0x1400206c8  jz      short loc_140020740
0x1400206ca  test    dword ptr [rbx+2Ch], 4000h
0x1400206d1  jz      short loc_1400206FA
0x1400206d3  mov     rbx, [rbx+18h]
0x1400206d7  call    cs:__imp_PsGetCurrentThreadId
0x1400206de  nop     dword ptr [rax+rax+00h]
0x1400206e3  mov     edx, 32h ; '2'
0x1400206e8  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400206ef  mov     r9, rax
0x1400206f2  mov     rcx, rbx
0x1400206f5  call    WPP_SF_q
0x1400206fa  mov     rbx, cs:WPP_GLOBAL_Control
0x140020701  cmp     rbx, r15
0x140020704  jz      short loc_140020740
0x140020706  test    dword ptr [rbx+2Ch], 2000h
0x14002070d  jz      short loc_140020740
0x14002070f  mov     rbx, [rbx+18h]
0x140020713  call    cs:__imp_PsGetCurrentThreadId
0x14002071a  nop     dword ptr [rax+rax+00h]
0x14002071f  mov     edx, 33h ; '3'
0x140020724  mov     [rsp+78h+var_50], rdi
0x140020729  mov     r9, rax
0x14002072c  mov     [rsp+78h+var_58], r12
0x140020731  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020738  mov     rcx, rbx
0x14002073b  call    WPP_SF_qqq
0x140020740  mov     rax, [rdi+1C8h]
0x140020747  mov     dword ptr [rsi+30h], 9
0x14002074e  movzx   ecx, byte ptr [rax]
0x140020751  mov     [rsi+284h], cl
0x140020757  mov     rdi, cs:WPP_GLOBAL_Control
0x14002075e  cmp     rdi, r15
0x140020761  jz      short loc_140020799
0x140020763  test    dword ptr [rdi+2Ch], 4000h
0x14002076a  jz      short loc_140020799
0x14002076c  mov     rdi, [rdi+18h]
0x140020770  mov     ebx, ecx
0x140020772  call    cs:__imp_PsGetCurrentThreadId
0x140020779  nop     dword ptr [rax+rax+00h]
0x14002077e  mov     edx, 34h ; '4'
0x140020783  mov     dword ptr [rsp+78h+var_58], ebx
0x140020787  mov     r9, rax
0x14002078a  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020791  mov     rcx, rdi
0x140020794  call    WPP_SF_qD
0x140020799  mov     rax, [rbp+28h]
0x14002079d  mov     r15, r14
0x1400207a0  mov     rcx, [rax+20h]
0x1400207a4  mov     rbx, [rcx+20h]
0x1400207a8  test    rbx, rbx
0x1400207ab  jz      short loc_1400207B1
0x1400207ad  mov     r15, [rbx+20h]
0x1400207b1  mov     rax, [rbx+40h]
0x1400207b5  mov     rcx, r12
0x1400207b8  movzx   r14d, word ptr [rax]
0x1400207bc  add     r14, 2
0x1400207c0  mov     rdx, r14
0x1400207c3  call    UMRxAllocateSecondaryBuffer
0x1400207c8  xor     r12d, r12d
0x1400207cb  mov     rdi, rax
0x1400207ce  test    rax, rax
0x1400207d1  jnz     short loc_140020830
0x1400207d3  mov     edi, 0C000009Ah
0x1400207d8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400207df  lea     r14, WPP_GLOBAL_Control
0x1400207e6  cmp     rbx, r14
0x1400207e9  jz      loc_140020E5A
0x1400207ef  test    dword ptr [rbx+2Ch], 2000h
0x1400207f6  jz      loc_140020E1A
0x1400207fc  mov     rbx, [rbx+18h]
0x140020800  call    cs:__imp_PsGetCurrentThreadId
0x140020807  nop     dword ptr [rax+rax+00h]
0x14002080c  lea     edx, [r12+35h]
0x140020811  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140020819  mov     r9, rax
0x14002081c  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020823  mov     rcx, rbx
0x140020826  call    WPP_SF_qD
0x14002082b  jmp     loc_140020E1A
0x140020830  mov     rdx, [rbx+40h]
0x140020834  mov     rcx, rdi; void *
0x140020837  movzx   r8d, word ptr [rdx]; Size
0x14002083b  mov     rdx, [rdx+8]; Src
0x14002083f  call    memmove
0x140020844  shr     r14, 1
0x140020847  mov     [rdi+r14*2-2], r12w
0x14002084d  mov     [rsi+288h], rdi
0x140020854  mov     rbx, cs:WPP_GLOBAL_Control
0x14002085b  lea     r14, WPP_GLOBAL_Control
0x140020862  cmp     rbx, r14
0x140020865  jz      short loc_14002089C
0x140020867  test    dword ptr [rbx+2Ch], 4000h
0x14002086e  jz      short loc_14002089C
0x140020870  mov     rbx, [rbx+18h]
0x140020874  call    cs:__imp_PsGetCurrentThreadId
0x14002087b  nop     dword ptr [rax+rax+00h]
0x140020880  mov     edx, 36h ; '6'
0x140020885  mov     [rsp+78h+var_58], rdi
0x14002088a  mov     r9, rax
0x14002088d  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020894  mov     rcx, rbx
0x140020897  call    WPP_SF_qS
0x14002089c  mov     eax, [r15]
0x14002089f  mov     edx, 5Ch ; '\'; Ch
0x1400208a4  mov     [rsi+280h], eax
0x1400208aa  mov     rax, [rbp+20h]
0x1400208ae  lea     r15d, [rdx-5Ah]
0x1400208b2  mov     rax, [rax+78h]
0x1400208b6  mov     r8, [rax+58h]
0x1400208ba  mov     rax, [rax+20h]
0x1400208be  movzx   r12d, word ptr [r8]
0x1400208c2  mov     rcx, [rax+40h]
0x1400208c6  movzx   eax, word ptr [rcx]
0x1400208c9  mov     rcx, [r8+8]
0x1400208cd  sub     r12d, eax
0x1400208d0  add     rcx, r15; Str
0x1400208d3  call    cs:__imp_wcschr
0x1400208da  nop     dword ptr [rax+rax+00h]
0x1400208df  mov     rcx, [rbp+50h]
0x1400208e3  mov     rdi, rax
0x1400208e6  mov     [rsp+78h+Src], rax
0x1400208ee  movzx   edx, word ptr [rcx]
0x1400208f1  lea     ecx, [rdx+2]
0x1400208f4  add     ecx, r12d
0x1400208f7  cmp     ecx, r12d
0x1400208fa  jbe     loc_140020DC3
0x140020900  cmp     ecx, edx
0x140020902  jbe     loc_140020DC3
0x140020908  mov     ebx, ecx
0x14002090a  mov     edx, ecx
0x14002090c  mov     rcx, [rsp+78h+arg_0]
0x140020914  call    UMRxAllocateSecondaryBuffer
0x140020919  mov     r14, rax
0x14002091c  test    rax, rax
0x14002091f  jnz     short loc_14002096B
0x140020921  mov     edi, 0C000009Ah
0x140020926  mov     rbx, cs:WPP_GLOBAL_Control
0x14002092d  lea     rax, WPP_GLOBAL_Control
0x140020934  cmp     rbx, rax
0x140020937  jz      loc_140020E5A
0x14002093d  test    dword ptr [rbx+2Ch], 2000h
0x140020944  jz      loc_140020E13
0x14002094a  mov     rbx, [rbx+18h]
0x14002094e  call    cs:__imp_PsGetCurrentThreadId
0x140020955  nop     dword ptr [rax+rax+00h]
0x14002095a  lea     edx, [r15+36h]
0x14002095e  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140020966  jmp     loc_140020E01
0x14002096b  mov     r8, rbx; Size
0x14002096e  xor     edx, edx; Val
0x140020970  mov     rcx, r14; void *
0x140020973  call    memset
0x140020978  mov     r8d, r12d; Size
0x14002097b  mov     rdx, rdi; Src
0x14002097e  mov     rcx, r14; void *
0x140020981  call    memmove
0x140020986  mov     rdx, [rbp+50h]
0x14002098a  mov     eax, r12d
0x14002098d  shr     rax, 1
0x140020990  mov     [rsp+78h+var_48], rax
0x140020995  movzx   r8d, word ptr [rdx]; Size
0x140020999  mov     rdx, [rdx+8]; Src
0x14002099d  lea     rcx, [r14+rax*2]; void *
0x1400209a1  call    memmove
0x1400209a6  shr     rbx, 1
0x1400209a9  lea     r9, [r13+4A4h]
0x1400209b0  xor     r10d, r10d
0x1400209b3  lea     rax, [rsi+2A8h]
0x1400209ba  mov     r8d, 7FFFFFFEh
0x1400209c0  mov     edx, 208h
0x1400209c5  mov     [r14+rbx*2-2], r10w
0x1400209cb  mov     [rsi+290h], r14
0x1400209d2  test    r8, r8
0x1400209d5  jz      short loc_1400209F2
0x1400209d7  movzx   ecx, word ptr [r9]
0x1400209db  test    cx, cx
0x1400209de  jz      short loc_1400209F2
0x1400209e0  mov     [rax], cx
0x1400209e3  add     r9, r15
0x1400209e6  add     rax, r15
0x1400209e9  dec     r8
0x1400209ec  sub     rdx, 1
0x1400209f0  jnz     short loc_1400209D2
0x1400209f2  test    rdx, rdx
0x1400209f5  lea     rcx, [rax-2]
0x1400209f9  cmovnz  rcx, rax
0x1400209fd  mov     [rcx], r10w
0x140020a01  mov     rdi, cs:WPP_GLOBAL_Control
0x140020a08  lea     rax, WPP_GLOBAL_Control
0x140020a0f  cmp     rdi, rax
0x140020a12  jz      loc_140020A99
0x140020a18  test    dword ptr [rdi+2Ch], 4000h
0x140020a1f  jz      short loc_140020A51
0x140020a21  mov     rbx, [rbp+50h]
0x140020a25  mov     rdi, [rdi+18h]
0x140020a29  call    cs:__imp_PsGetCurrentThreadId
0x140020a30  nop     dword ptr [rax+rax+00h]
0x140020a35  mov     edx, 39h ; '9'
0x140020a3a  mov     [rsp+78h+var_58], rbx
0x140020a3f  mov     r9, rax
0x140020a42  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020a49  mov     rcx, rdi
0x140020a4c  call    WPP_SF_qZ
0x140020a51  mov     rbx, cs:WPP_GLOBAL_Control
0x140020a58  lea     rax, WPP_GLOBAL_Control
0x140020a5f  cmp     rbx, rax
0x140020a62  jz      short loc_140020A99
0x140020a64  test    dword ptr [rbx+2Ch], 4000h
0x140020a6b  jz      short loc_140020A99
0x140020a6d  mov     rbx, [rbx+18h]
0x140020a71  call    cs:__imp_PsGetCurrentThreadId
0x140020a78  nop     dword ptr [rax+rax+00h]
0x140020a7d  mov     edx, 3Ah ; ':'
0x140020a82  mov     [rsp+78h+var_58], r14
0x140020a87  mov     r9, rax
0x140020a8a  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020a91  mov     rcx, rbx
0x140020a94  call    WPP_SF_qS
0x140020a99  mov     ecx, [r13+298h]
0x140020aa0  lea     r14, [r13+90h]
0x140020aa7  mov     eax, 4
0x140020aac  lea     edx, [rax+58h]
0x140020aaf  cmp     [r14], dx
0x140020ab3  cmovnz  r15d, eax
0x140020ab7  lea     eax, [r12+r15]
0x140020abb  add     eax, ecx
0x140020abd  cmp     eax, r12d
0x140020ac0  jbe     loc_140020D87
0x140020ac6  cmp     eax, ecx
0x140020ac8  jbe     loc_140020D87
0x140020ace  mov     r15, [rsp+78h+arg_0]
0x140020ad6  mov     rcx, r15
0x140020ad9  mov     edx, eax
0x140020adb  mov     ebx, eax
0x140020add  call    UMRxAllocateSecondaryBuffer
0x140020ae2  mov     rdi, rax
0x140020ae5  test    rax, rax
0x140020ae8  jnz     short loc_140020B2D
0x140020aea  mov     edi, 0C000009Ah
0x140020aef  mov     rbx, cs:WPP_GLOBAL_Control
0x140020af6  lea     rax, WPP_GLOBAL_Control
0x140020afd  cmp     rbx, rax
0x140020b00  jz      loc_140020E5A
0x140020b06  test    dword ptr [rbx+2Ch], 2000h
0x140020b0d  jz      loc_140020E13
0x140020b13  mov     rbx, [rbx+18h]
0x140020b17  call    cs:__imp_PsGetCurrentThreadId
0x140020b1e  nop     dword ptr [rax+rax+00h]
0x140020b23  mov     edx, 3Ch ; '<'
0x140020b28  jmp     loc_14002095E
0x140020b2d  mov     r8, rbx; Size
0x140020b30  xor     edx, edx; Val
0x140020b32  mov     rcx, rdi; void *
0x140020b35  call    memset
0x140020b3a  mov     rdx, [rsp+78h+Src]; Src
0x140020b42  mov     rcx, rdi; void *
0x140020b45  mov     r8d, r12d; Size
0x140020b48  call    memmove
0x140020b4d  mov     rax, [rsp+78h+var_48]
0x140020b52  mov     rdx, r14; Src
0x140020b55  lea     rcx, [rdi+rax*2]
0x140020b59  mov     eax, 5Ch ; '\'
0x140020b5e  cmp     [r14], ax
0x140020b62  jz      short loc_140020B6B
0x140020b64  mov     [rcx], ax
0x140020b67  add     rcx, 2; void *
0x140020b6b  mov     r8d, [r13+298h]; Size
0x140020b72  call    memmove
0x140020b77  shr     rbx, 1
0x140020b7a  xor     r12d, r12d
0x140020b7d  mov     [rdi+rbx*2-2], r12w
  ... truncated ...
```
