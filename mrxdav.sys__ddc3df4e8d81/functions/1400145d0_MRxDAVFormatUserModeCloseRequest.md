# MRxDAVFormatUserModeCloseRequest

- ea: `0x1400145d0`
- end: `0x140014df5`
- name: `MRxDAVFormatUserModeCloseRequest`
- size: `2085`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140001b64`
- `0x140006900`
- `0x140006c00`
- `0x1400145d0`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140014633`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014676`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014829`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014928`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400149f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014a6c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014ae1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014b4c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014c54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014cbc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014d21`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014d6f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014dba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014633`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014676`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014829`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014928`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400149f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014a6c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014ae1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014b4c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014c54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014cbc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014d21`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014d6f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014dba`
- `ntoskrnl!wcschr` at `0x14001499f`
- `ntoskrnl!wcschr` at `0x14001499f`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeCloseRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v7; // r15
  __int64 v8; // rbp
  __int64 v9; // rdi
  __int64 v10; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  _DWORD *v14; // r12
  __int64 v15; // r14
  __int64 v16; // r8
  _WORD *v17; // r9
  __int64 v18; // rcx
  _WORD *v19; // rax
  __int64 v20; // rdx
  bool v21; // zf
  _WORD *v22; // rcx
  __int64 v23; // rdx
  _WORD *v24; // rax
  _WORD *v25; // rcx
  _WORD *v26; // rcx
  signed __int32 v27; // edx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rbx
  HANDLE v31; // rax
  ULONG_PTR v32; // rbp
  _WORD *SecondaryBuffer; // rax
  _WORD *v34; // rbx
  unsigned int v35; // edi
  __int64 v36; // rbx
  HANDLE v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  unsigned __int16 *v40; // r8
  unsigned int v41; // ebx
  wchar_t *v42; // r12
  unsigned int v43; // edx
  unsigned int v44; // ecx
  __int64 v45; // rbx
  HANDLE v46; // rax
  __int64 v47; // rdx
  unsigned int v48; // edx
  size_t v49; // rbp
  char *v50; // rax
  char *v51; // r14
  char *v52; // rcx
  __int64 v53; // rbx
  unsigned int v54; // eax
  __int64 v55; // rbx
  unsigned int v56; // eax
  __int64 v57; // rbp
  __int64 v58; // rcx
  __int64 v59; // rbx
  __int64 v60; // rax
  ULONG_PTR v61; // rdi
  PVOID v62; // rax
  _WORD *v63; // rdx
  __int64 v64; // rbx
  __int64 v65; // rdi
  unsigned int v66; // eax
  __int64 v67; // rbx
  HANDLE v68; // rax
  __int64 v69; // rbx
  HANDLE v70; // rax

  v3 = *(_QWORD *)(a2 + 72);
  v7 = 0;
  if ( v3 )
    v7 = *(_QWORD *)(v3 + 48);
  v8 = *(_QWORD *)(v3 + 32);
  v9 = 0;
  if ( v8 )
    v9 = *(_QWORD *)(v8 + 136);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v10, 102, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      WPP_SF_qqq(v12, 103, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v13, a1, a2);
    }
  }
  *(_DWORD *)(a3 + 48) = 3;
  v14 = 0;
  v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 32LL) + 32LL);
  if ( v15 )
    v14 = *(_DWORD **)(v15 + 32);
  v16 = 2147483646;
  v17 = (_WORD *)(v9 + 668);
  v18 = 2147483646;
  v19 = (_WORD *)(a3 + 752);
  v20 = 260;
  do
  {
    if ( !v18 )
      break;
    if ( !*v17 )
      break;
    *v19++ = *v17++;
    --v18;
    --v20;
  }
  while ( v20 );
  v21 = v20 == 0;
  v22 = v19 - 1;
  v23 = 520;
  if ( !v21 )
    v22 = v19;
  v24 = (_WORD *)(a3 + 1272);
  *v22 = 0;
  v25 = (_WORD *)(v9 + 1188);
  do
  {
    if ( !v16 )
      break;
    if ( !*v25 )
      break;
    *v24++ = *v25++;
    --v16;
    --v23;
  }
  while ( v23 );
  v26 = v24 - 1;
  if ( v23 )
    v26 = v24;
  *v26 = 0;
  v27 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 16), 0, 0);
  if ( v27 )
  {
    _InterlockedExchange((volatile __int32 *)(v9 + 16), 0);
    *(_DWORD *)(v9 + 20) = 1;
  }
  *(_DWORD *)(a3 + 688) = *(_DWORD *)(v9 + 12);
  *(_DWORD *)(a3 + 692) = v27;
  if ( !v27 || (v28 = 1, *(_DWORD *)(v9 + 12)) )
    v28 = 0;
  *(_DWORD *)(v7 + 40) = v28;
  if ( !*(_DWORD *)(a3 + 688) )
  {
    if ( v27 )
    {
      *(_BYTE *)(a3 + 708) = *(_QWORD *)(v8 + 200) != 0;
      *(_BYTE *)(a3 + 709) = *(_QWORD *)(v8 + 208) != 0;
      *(_BYTE *)(a3 + 710) = *(_QWORD *)(v8 + 216) != 0;
      if ( !*(_DWORD *)(v9 + 28) )
      {
        v29 = MEMORY[0xFFFFF78000000014];
        *(_QWORD *)(v8 + 208) = MEMORY[0xFFFFF78000000014];
        *(_QWORD *)(v8 + 216) = v29;
      }
      if ( *(_DWORD *)(v8 + 232) == 128 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v31 = PsGetCurrentThreadId();
          WPP_SF_q(v30, 104, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v31);
        }
        *(_DWORD *)(v8 + 232) = 32;
        *(_BYTE *)(v9 + 63) = 1;
      }
      if ( *(_DWORD *)(v8 + 232) || *(_BYTE *)(v9 + 63) )
        *(_BYTE *)(a3 + 711) = 1;
    }
    else
    {
      *(_BYTE *)(a3 + 708) = *(_BYTE *)(v9 + 60);
      *(_BYTE *)(a3 + 709) = *(_BYTE *)(v9 + 61);
      *(_BYTE *)(a3 + 710) = *(_BYTE *)(v9 + 62);
      *(_BYTE *)(a3 + 711) = *(_BYTE *)(v9 + 63);
    }
  }
  *(_QWORD *)(a3 + 712) = *(_QWORD *)(v8 + 200);
  *(_QWORD *)(a3 + 720) = *(_QWORD *)(v8 + 208);
  *(_QWORD *)(a3 + 728) = *(_QWORD *)(v8 + 216);
  *(_DWORD *)(a3 + 744) = *(_DWORD *)(v8 + 232);
  *(_DWORD *)(a3 + 748) = *(_DWORD *)(v8 + 32);
  v32 = **(unsigned __int16 **)(v15 + 64) + 2LL;
  SecondaryBuffer = UMRxAllocateSecondaryBuffer(a1, v32);
  v34 = SecondaryBuffer;
  if ( SecondaryBuffer )
  {
    memmove(SecondaryBuffer, *(const void **)(*(_QWORD *)(v15 + 64) + 8LL), **(unsigned __int16 **)(v15 + 64));
    v34[(v32 >> 1) - 1] = 0;
    *(_QWORD *)(a3 + 656) = v34;
    *(_DWORD *)(a3 + 664) = *v14;
    v39 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 120LL);
    v40 = *(unsigned __int16 **)(v39 + 88);
    v41 = *v40 - **(unsigned __int16 **)(*(_QWORD *)(v39 + 32) + 64LL);
    v42 = wcschr((const wchar_t *)(*((_QWORD *)v40 + 1) + 2LL), 0x5Cu);
    if ( *(_DWORD *)(v9 + 64) )
    {
      v43 = *(_DWORD *)(v9 + 664);
      v44 = v43 + v41 + 2;
      if ( v44 <= v41 || v44 <= v43 )
      {
        v35 = -1073741811;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v35;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          goto LABEL_93;
        v45 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v46 = PsGetCurrentThreadId();
        v47 = 106;
LABEL_92:
        WPP_SF_qD(v45, v47, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v46, -1073741811);
        goto LABEL_93;
      }
    }
    else
    {
      v48 = **(unsigned __int16 **)(v3 + 80);
      v44 = v41 + v48 + 2;
      if ( v44 <= v41 || v44 <= v48 )
      {
        v35 = -1073741811;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v35;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          goto LABEL_93;
        v45 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v46 = PsGetCurrentThreadId();
        v47 = 107;
        goto LABEL_92;
      }
    }
    v49 = v44;
    v50 = (char *)UMRxAllocateSecondaryBuffer(a1, v44);
    v51 = v50;
    if ( v50 )
    {
      memset(v50, 0, v49);
      memmove(v51, v42, v41);
      v52 = &v51[2 * ((unsigned __int64)v41 >> 1)];
      if ( *(_DWORD *)(v9 + 64) )
      {
        memmove(v52, (const void *)(v9 + 144), *(unsigned int *)(v9 + 664));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v53 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v54 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qS(v53, 109, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v54, (__int64)v51);
        }
      }
      else
      {
        memmove(v52, *(const void **)(*(_QWORD *)(v3 + 80) + 8LL), **(unsigned __int16 **)(v3 + 80));
      }
      *(_WORD *)&v51[2 * (v49 >> 1) - 2] = 0;
      *(_QWORD *)(a3 + 672) = v51;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v55 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v56 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qS(v55, 110, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v56, (__int64)v51);
      }
      v57 = *(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL);
      *(_DWORD *)(a3 + 648) = *(_DWORD *)(v57 + 80);
      *(_DWORD *)(a3 + 652) = *(_DWORD *)(v57 + 84);
      if ( *(_DWORD *)v9 )
      {
        *(_DWORD *)(a3 + 704) = 1;
      }
      else
      {
        *(_DWORD *)(a3 + 704) = 0;
        if ( *(_DWORD *)(v7 + 44) )
        {
          *(_QWORD *)(a3 + 632) = 0;
          *(_QWORD *)(a3 + 640) = 0;
          *(_DWORD *)(a3 + 700) = *(_DWORD *)(v7 + 44);
        }
        else
        {
          *(_QWORD *)(a3 + 632) = *(_QWORD *)v7;
          *(_QWORD *)(a3 + 640) = *(_QWORD *)(v7 + 8);
        }
      }
      *(_DWORD *)(a3 + 696) = *(_DWORD *)(v7 + 16);
      v58 = *(_QWORD *)(v7 + 48);
      if ( v58 )
      {
        v59 = -1;
        v60 = -1;
        do
          ++v60;
        while ( *(_WORD *)(v58 + 2 * v60) );
        v61 = (unsigned int)(2 * v60 + 2);
        v62 = UMRxAllocateSecondaryBuffer(a1, v61);
        *(_QWORD *)(a3 + 680) = v62;
        if ( !v62 )
        {
          v35 = -1073741670;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v35;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
            goto LABEL_93;
          v36 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v37 = PsGetCurrentThreadId();
          v38 = 111;
          goto LABEL_47;
        }
        memset(v62, 0, v61);
        v63 = *(_WORD **)(v7 + 48);
        do
          ++v59;
        while ( v63[v59] );
        memmove(*(void **)(a3 + 680), v63, 2 * v59);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v64 = *(_QWORD *)(a3 + 680);
          v65 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v66 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qS(v65, 112, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v66, v64);
        }
      }
      v35 = UMRxImpersonateClient((PSECURITY_CLIENT_CONTEXT)v57);
      if ( (v35 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v35;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v67 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v68 = PsGetCurrentThreadId();
          WPP_SF_qD(v67, 113, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v68, v35);
        }
      }
      goto LABEL_93;
    }
    v35 = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v35;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_93;
    v36 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v37 = PsGetCurrentThreadId();
    v38 = 108;
LABEL_47:
    WPP_SF_qD(v36, v38, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v37, -1073741670);
    goto LABEL_93;
  }
  v35 = -1073741670;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v35;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v36 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v37 = PsGetCurrentThreadId();
    v38 = 105;
    goto LABEL_47;
  }
LABEL_93:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v69 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v70 = PsGetCurrentThreadId();
    WPP_SF_qD(v69, 115, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v70, v35);
  }
  return v35;
}

```

## disassembly

```asm
0x1400145d0  mov     [rsp+arg_0], rcx
0x1400145d5  push    rbx
0x1400145d6  push    rbp
0x1400145d7  push    rsi
0x1400145d8  push    rdi
0x1400145d9  push    r12
0x1400145db  push    r13
0x1400145dd  push    r14
0x1400145df  push    r15
0x1400145e1  sub     rsp, 38h
0x1400145e5  mov     r13, [rdx+48h]
0x1400145e9  xor     eax, eax
0x1400145eb  mov     rsi, r8
0x1400145ee  mov     r14, rdx
0x1400145f1  mov     r12, rcx
0x1400145f4  mov     r15d, eax
0x1400145f7  test    r13, r13
0x1400145fa  jz      short loc_140014600
0x1400145fc  mov     r15, [r13+30h]
0x140014600  mov     rbp, [r13+20h]
0x140014604  mov     rdi, rax
0x140014607  test    rbp, rbp
0x14001460a  jz      short loc_140014613
0x14001460c  mov     rdi, [rbp+88h]
0x140014613  mov     rbx, cs:WPP_GLOBAL_Control
0x14001461a  lea     rax, WPP_GLOBAL_Control
0x140014621  cmp     rbx, rax
0x140014624  jz      short loc_1400146A3
0x140014626  test    dword ptr [rbx+2Ch], 4000h
0x14001462d  jz      short loc_140014656
0x14001462f  mov     rbx, [rbx+18h]
0x140014633  call    cs:__imp_PsGetCurrentThreadId
0x14001463a  nop     dword ptr [rax+rax+00h]
0x14001463f  mov     edx, 66h ; 'f'
0x140014644  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x14001464b  mov     r9, rax
0x14001464e  mov     rcx, rbx
0x140014651  call    WPP_SF_q
0x140014656  mov     rbx, cs:WPP_GLOBAL_Control
0x14001465d  lea     rax, WPP_GLOBAL_Control
0x140014664  cmp     rbx, rax
0x140014667  jz      short loc_1400146A3
0x140014669  test    dword ptr [rbx+2Ch], 2000h
0x140014670  jz      short loc_1400146A3
0x140014672  mov     rbx, [rbx+18h]
0x140014676  call    cs:__imp_PsGetCurrentThreadId
0x14001467d  nop     dword ptr [rax+rax+00h]
0x140014682  mov     edx, 67h ; 'g'
0x140014687  mov     [rsp+78h+var_50], r14
0x14001468c  mov     r9, rax
0x14001468f  mov     [rsp+78h+var_58], r12
0x140014694  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x14001469b  mov     rcx, rbx
0x14001469e  call    WPP_SF_qqq
0x1400146a3  mov     dword ptr [rsi+30h], 3
0x1400146aa  xor     r11d, r11d
0x1400146ad  mov     rax, [r13+28h]
0x1400146b1  mov     r12d, r11d
0x1400146b4  mov     rcx, [rax+20h]
0x1400146b8  mov     r14, [rcx+20h]
0x1400146bc  test    r14, r14
0x1400146bf  jz      short loc_1400146C5
0x1400146c1  mov     r12, [r14+20h]
0x1400146c5  mov     r8d, 7FFFFFFEh
0x1400146cb  lea     r9, [rdi+29Ch]
0x1400146d2  mov     ecx, r8d
0x1400146d5  lea     rax, [rsi+2F0h]
0x1400146dc  mov     edx, 104h
0x1400146e1  test    rcx, rcx
0x1400146e4  jz      short loc_140014705
0x1400146e6  movzx   r10d, word ptr [r9]
0x1400146ea  test    r10w, r10w
0x1400146ee  jz      short loc_140014705
0x1400146f0  mov     [rax], r10w
0x1400146f4  add     r9, 2
0x1400146f8  add     rax, 2
0x1400146fc  dec     rcx
0x1400146ff  sub     rdx, 1
0x140014703  jnz     short loc_1400146E1
0x140014705  test    rdx, rdx
0x140014708  lea     rcx, [rax-2]
0x14001470c  mov     edx, 208h
0x140014711  cmovnz  rcx, rax
0x140014715  lea     rax, [rsi+4F8h]
0x14001471c  mov     [rcx], r11w
0x140014720  lea     rcx, [rdi+4A4h]
0x140014727  test    r8, r8
0x14001472a  jz      short loc_14001474B
0x14001472c  movzx   r9d, word ptr [rcx]
0x140014730  test    r9w, r9w
0x140014734  jz      short loc_14001474B
0x140014736  mov     [rax], r9w
0x14001473a  add     rcx, 2
0x14001473e  add     rax, 2
0x140014742  dec     r8
0x140014745  sub     rdx, 1
0x140014749  jnz     short loc_140014727
0x14001474b  test    rdx, rdx
0x14001474e  lea     rcx, [rax-2]
0x140014752  cmovnz  rcx, rax
0x140014756  xor     eax, eax
0x140014758  mov     [rcx], r11w
0x14001475c  mov     ecx, r11d
0x14001475f  lock cmpxchg [rdi+10h], ecx
0x140014764  mov     edx, eax
0x140014766  jz      short loc_140014772
0x140014768  xchg    ecx, [rdi+10h]
0x14001476b  mov     dword ptr [rdi+14h], 1
0x140014772  mov     ecx, [rdi+0Ch]
0x140014775  mov     [rsi+2B0h], ecx
0x14001477b  mov     [rsi+2B4h], edx
0x140014781  test    edx, edx
0x140014783  jz      short loc_140014790
0x140014785  mov     eax, 1
0x14001478a  cmp     [rdi+0Ch], r11d
0x14001478e  jz      short loc_140014793
0x140014790  mov     eax, r11d
0x140014793  mov     [r15+28h], eax
0x140014797  cmp     [rsi+2B0h], r11d
0x14001479e  jnz     loc_140014899
0x1400147a4  test    edx, edx
0x1400147a6  jz      loc_140014875
0x1400147ac  cmp     [rbp+0C8h], r11
0x1400147b3  setnz   al
0x1400147b6  mov     [rsi+2C4h], al
0x1400147bc  cmp     [rbp+0D0h], r11
0x1400147c3  setnz   al
0x1400147c6  mov     [rsi+2C5h], al
0x1400147cc  cmp     [rbp+0D8h], r11
0x1400147d3  setnz   al
0x1400147d6  mov     [rsi+2C6h], al
0x1400147dc  cmp     [rdi+1Ch], r11d
0x1400147e0  jnz     short loc_1400147FD
0x1400147e2  mov     rax, 0FFFFF78000000014h
0x1400147ec  mov     rax, [rax]
0x1400147ef  mov     [rbp+0D0h], rax
0x1400147f6  mov     [rbp+0D8h], rax
0x1400147fd  cmp     dword ptr [rbp+0E8h], 80h
0x140014807  jnz     short loc_14001485D
0x140014809  mov     rbx, cs:WPP_GLOBAL_Control
0x140014810  lea     rax, WPP_GLOBAL_Control
0x140014817  cmp     rbx, rax
0x14001481a  jz      short loc_14001484F
0x14001481c  test    dword ptr [rbx+2Ch], 4000h
0x140014823  jz      short loc_14001484F
0x140014825  mov     rbx, [rbx+18h]
0x140014829  call    cs:__imp_PsGetCurrentThreadId
0x140014830  nop     dword ptr [rax+rax+00h]
0x140014835  mov     edx, 68h ; 'h'
0x14001483a  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140014841  mov     r9, rax
0x140014844  mov     rcx, rbx
0x140014847  call    WPP_SF_q
0x14001484c  xor     r11d, r11d
0x14001484f  mov     dword ptr [rbp+0E8h], 20h ; ' '
0x140014859  mov     byte ptr [rdi+3Fh], 1
0x14001485d  cmp     [rbp+0E8h], r11d
0x140014864  jnz     short loc_14001486C
0x140014866  cmp     [rdi+3Fh], r11b
0x14001486a  jz      short loc_140014899
0x14001486c  mov     byte ptr [rsi+2C7h], 1
0x140014873  jmp     short loc_140014899
0x140014875  mov     al, [rdi+3Ch]
0x140014878  mov     [rsi+2C4h], al
0x14001487e  mov     al, [rdi+3Dh]
0x140014881  mov     [rsi+2C5h], al
0x140014887  mov     al, [rdi+3Eh]
0x14001488a  mov     [rsi+2C6h], al
0x140014890  mov     al, [rdi+3Fh]
0x140014893  mov     [rsi+2C7h], al
0x140014899  mov     rax, [rbp+0C8h]
0x1400148a0  mov     rcx, [rsp+78h+arg_0]
0x1400148a8  mov     [rsi+2C8h], rax
0x1400148af  mov     rax, [rbp+0D0h]
0x1400148b6  mov     [rsi+2D0h], rax
0x1400148bd  mov     rax, [rbp+0D8h]
0x1400148c4  mov     [rsi+2D8h], rax
0x1400148cb  mov     eax, [rbp+0E8h]
0x1400148d1  mov     [rsi+2E8h], eax
0x1400148d7  mov     eax, [rbp+20h]
0x1400148da  mov     [rsi+2ECh], eax
0x1400148e0  mov     rax, [r14+40h]
0x1400148e4  movzx   ebp, word ptr [rax]
0x1400148e7  add     rbp, 2
0x1400148eb  mov     rdx, rbp
0x1400148ee  call    UMRxAllocateSecondaryBuffer
0x1400148f3  mov     rbx, rax
0x1400148f6  test    rax, rax
0x1400148f9  jnz     short loc_140014946
0x1400148fb  mov     edi, 0C000009Ah
0x140014900  mov     rbx, cs:WPP_GLOBAL_Control
0x140014907  lea     rax, WPP_GLOBAL_Control
0x14001490e  cmp     rbx, rax
0x140014911  jz      loc_140014DE1
0x140014917  test    dword ptr [rbx+2Ch], 2000h
0x14001491e  jz      loc_140014D9A
0x140014924  mov     rbx, [rbx+18h]
0x140014928  call    cs:__imp_PsGetCurrentThreadId
0x14001492f  nop     dword ptr [rax+rax+00h]
0x140014934  mov     edx, 69h ; 'i'
0x140014939  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140014941  jmp     loc_140014D88
0x140014946  mov     rdx, [r14+40h]
0x14001494a  mov     rcx, rbx; void *
0x14001494d  movzx   r8d, word ptr [rdx]; Size
0x140014951  mov     rdx, [rdx+8]; Src
0x140014955  call    memmove
0x14001495a  xor     eax, eax
0x14001495c  shr     rbp, 1
0x14001495f  mov     edx, 5Ch ; '\'; Ch
0x140014964  mov     [rbx+rbp*2-2], ax
0x140014969  mov     [rsi+290h], rbx
0x140014970  mov     eax, [r12]
0x140014974  mov     [rsi+298h], eax
0x14001497a  mov     rax, [r13+20h]
0x14001497e  mov     rax, [rax+78h]
0x140014982  mov     r8, [rax+58h]
0x140014986  mov     rax, [rax+20h]
0x14001498a  movzx   ebx, word ptr [r8]
0x14001498e  mov     rcx, [rax+40h]
0x140014992  movzx   eax, word ptr [rcx]
0x140014995  mov     rcx, [r8+8]
0x140014999  sub     ebx, eax
0x14001499b  add     rcx, 2; Str
0x14001499f  call    cs:__imp_wcschr
0x1400149a6  nop     dword ptr [rax+rax+00h]
0x1400149ab  cmp     dword ptr [rdi+40h], 0
0x1400149af  mov     r12, rax
0x1400149b2  jz      short loc_140014A0A
0x1400149b4  mov     edx, [rdi+298h]
0x1400149ba  lea     ecx, [rbx+2]
0x1400149bd  add     ecx, edx
0x1400149bf  cmp     ecx, ebx
0x1400149c1  jbe     short loc_1400149C7
0x1400149c3  cmp     ecx, edx
0x1400149c5  ja      short loc_140014A26
0x1400149c7  mov     edi, 0C000000Dh
0x1400149cc  mov     rbx, cs:WPP_GLOBAL_Control
0x1400149d3  lea     rax, WPP_GLOBAL_Control
0x1400149da  cmp     rbx, rax
0x1400149dd  jz      loc_140014DE1
0x1400149e3  test    dword ptr [rbx+2Ch], 2000h
0x1400149ea  jz      loc_140014D9A
0x1400149f0  mov     rbx, [rbx+18h]
0x1400149f4  call    cs:__imp_PsGetCurrentThreadId
0x1400149fb  nop     dword ptr [rax+rax+00h]
0x140014a00  mov     edx, 6Ah ; 'j'
0x140014a05  jmp     loc_140014D80
0x140014a0a  mov     rax, [r13+50h]
0x140014a0e  movzx   edx, word ptr [rax]
0x140014a11  lea     ecx, [rdx+2]
0x140014a14  add     ecx, ebx
0x140014a16  cmp     ecx, ebx
0x140014a18  jbe     loc_140014D4A
0x140014a1e  cmp     ecx, edx
0x140014a20  jbe     loc_140014D4A
0x140014a26  mov     ebp, ecx
0x140014a28  mov     edx, ecx
0x140014a2a  mov     rcx, [rsp+78h+arg_0]
0x140014a32  call    UMRxAllocateSecondaryBuffer
0x140014a37  mov     r14, rax
0x140014a3a  test    rax, rax
0x140014a3d  jnz     short loc_140014A81
0x140014a3f  mov     edi, 0C000009Ah
0x140014a44  mov     rbx, cs:WPP_GLOBAL_Control
0x140014a4b  lea     rax, WPP_GLOBAL_Control
0x140014a52  cmp     rbx, rax
0x140014a55  jz      loc_140014DE1
0x140014a5b  test    dword ptr [rbx+2Ch], 2000h
0x140014a62  jz      loc_140014D9A
0x140014a68  mov     rbx, [rbx+18h]
0x140014a6c  call    cs:__imp_PsGetCurrentThreadId
0x140014a73  nop     dword ptr [rax+rax+00h]
0x140014a78  lea     edx, [r14+6Ch]
0x140014a7c  jmp     loc_140014939
0x140014a81  mov     r8, rbp; Size
0x140014a84  xor     edx, edx; Val
0x140014a86  mov     rcx, r14; void *
0x140014a89  call    memset
0x140014a8e  mov     r8d, ebx; Size
0x140014a91  mov     rdx, r12; Src
0x140014a94  mov     rcx, r14; void *
0x140014a97  call    memmove
0x140014a9c  mov     eax, ebx
0x140014a9e  xor     r12d, r12d
0x140014aa1  shr     rax, 1
0x140014aa4  lea     rcx, [r14+rax*2]; void *
0x140014aa8  cmp     [rdi+40h], r12d
0x140014aac  jz      short loc_140014B0B
0x140014aae  mov     r8d, [rdi+298h]; Size
0x140014ab5  lea     rdx, [rdi+90h]; Src
0x140014abc  call    memmove
0x140014ac1  mov     rbx, cs:WPP_GLOBAL_Control
0x140014ac8  lea     rax, WPP_GLOBAL_Control
0x140014acf  cmp     rbx, rax
0x140014ad2  jz      short loc_140014B1C
0x140014ad4  test    dword ptr [rbx+2Ch], 4000h
0x140014adb  jz      short loc_140014B1C
0x140014add  mov     rbx, [rbx+18h]
0x140014ae1  call    cs:__imp_PsGetCurrentThreadId
  ... truncated ...
```
