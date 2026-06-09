# MRxDAVFormatUserModeSetFileInformationRequest

- ea: `0x140020e80`
- end: `0x140021460`
- name: `MRxDAVFormatUserModeSetFileInformationRequest`
- size: `1504`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140001b64`
- `0x140006900`
- `0x140006c00`
- `0x140020e80`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140020efd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020f39`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020fd3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021048`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002110c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002118c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400211f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021248`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400213bd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002141e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020efd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020f39`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020fd3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021048`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002110c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002118c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400211f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021248`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400213bd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002141e`
- `ntoskrnl!wcschr` at `0x1400210a5`
- `ntoskrnl!wcschr` at `0x1400210a5`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeSetFileInformationRequest(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v7; // rbp
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  _DWORD *v13; // r13
  ULONG_PTR v14; // r12
  PVOID SecondaryBuffer; // rax
  __int64 v16; // r15
  unsigned int v17; // esi
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned __int16 *v24; // r8
  unsigned int v25; // r12d
  ULONG_PTR v26; // rbx
  char *v27; // rax
  char *v28; // r15
  __int64 v29; // rbx
  unsigned int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // rbx
  HANDLE v35; // rax
  __int64 v36; // rax
  char v37; // dl
  char v38; // al
  char v39; // cl
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rax
  ULONG_PTR v44; // rbp
  PVOID v45; // rax
  _WORD *v46; // rdx
  __int64 v47; // rbx
  HANDLE v48; // rax
  wchar_t *Src; // [rsp+30h] [rbp-48h]
  _QWORD *v52; // [rsp+88h] [rbp+10h]
  __int64 v53; // [rsp+90h] [rbp+18h]

  v3 = a2[9];
  if ( v3 )
    v53 = *(_QWORD *)(v3 + 48);
  else
    v53 = 0;
  v7 = *(_QWORD *)(v3 + 32);
  v52 = (_QWORD *)a2[7];
  if ( v7 )
    v7 = *(_QWORD *)(v7 + 136);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 76, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 77, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v11, a1, a2);
    }
  }
  *(_DWORD *)(a3 + 48) = 10;
  v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 32LL) + 32LL);
  if ( v12 )
    v13 = *(_DWORD **)(v12 + 32);
  else
    v13 = 0;
  v14 = **(unsigned __int16 **)(v12 + 64) + 2LL;
  SecondaryBuffer = UMRxAllocateSecondaryBuffer(a1, v14);
  v16 = (__int64)SecondaryBuffer;
  if ( SecondaryBuffer )
  {
    memmove(SecondaryBuffer, *(const void **)(*(_QWORD *)(v12 + 64) + 8LL), **(unsigned __int16 **)(v12 + 64));
    *(_WORD *)(v16 + 2 * (v14 >> 1) - 2) = 0;
    *(_QWORD *)(a3 + 648) = v16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v22 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v21, 79, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v22, v16);
    }
    *(_DWORD *)(a3 + 640) = *v13;
    v23 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 120LL);
    v24 = *(unsigned __int16 **)(v23 + 88);
    v25 = *v24 - **(unsigned __int16 **)(*(_QWORD *)(v23 + 32) + 64LL);
    Src = wcschr((const wchar_t *)(*((_QWORD *)v24 + 1) + 2LL), 0x5Cu);
    v26 = v25 + **(unsigned __int16 **)(v3 + 80) + 2;
    v27 = (char *)UMRxAllocateSecondaryBuffer(a1, v26);
    v28 = v27;
    if ( !v27 )
    {
      v17 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v17;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_63;
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      v20 = 80;
      goto LABEL_19;
    }
    memset(v27, 0, v26);
    memmove(v28, Src, v25);
    memmove(
      &v28[2 * ((unsigned __int64)v25 >> 1)],
      *(const void **)(*(_QWORD *)(v3 + 80) + 8LL),
      **(unsigned __int16 **)(v3 + 80));
    *(_WORD *)&v28[2 * (v26 >> 1) - 2] = 0;
    *(_QWORD *)(a3 + 656) = v28;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v29 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v30 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v29, 81, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v30, (__int64)v28);
    }
    v31 = *(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL);
    *(_DWORD *)(a3 + 632) = *(_DWORD *)(v31 + 80);
    *(_DWORD *)(a3 + 636) = *(_DWORD *)(v31 + 84);
    if ( !*(_BYTE *)(v31 + 72)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v33 = PsGetCurrentThreadId();
      WPP_SF_q(v32, 82, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v33);
    }
    v17 = UMRxImpersonateClient((PSECURITY_CLIENT_CONTEXT)v31);
    if ( (v17 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v34 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v35 = PsGetCurrentThreadId();
      WPP_SF_qD(v34, 83, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v35, v17);
    }
    v36 = a2[57];
    *(_OWORD *)(a3 + 680) = *(_OWORD *)v36;
    *(_OWORD *)(a3 + 696) = *(_OWORD *)(v36 + 16);
    *(_QWORD *)(a3 + 712) = *(_QWORD *)(v36 + 32);
    if ( (*(_DWORD *)(a2[7] + 232LL) & 0x4000) != 0 )
      *(_DWORD *)(a3 + 712) |= 0x4000u;
    v37 = *(_BYTE *)(v7 + 60);
    *(_BYTE *)(a3 + 672) = v37;
    if ( v37 && !*(_QWORD *)(a3 + 680) )
      *(_QWORD *)(a3 + 680) = v52[25];
    v38 = *(_BYTE *)(v7 + 61);
    *(_BYTE *)(a3 + 673) = v38;
    if ( v38 && !*(_QWORD *)(a3 + 688) )
      *(_QWORD *)(a3 + 688) = v52[26];
    v39 = *(_BYTE *)(v7 + 62);
    *(_BYTE *)(a3 + 674) = v39;
    if ( v39 && !*(_QWORD *)(a3 + 696) )
      *(_QWORD *)(a3 + 696) = v52[27];
    if ( v37 )
    {
      if ( v39 )
      {
        v40 = *(_QWORD *)(a3 + 696);
        if ( *(_QWORD *)(a3 + 680) > v40 )
          *(_QWORD *)(a3 + 680) = v40;
      }
    }
    *(_BYTE *)(a3 + 675) = *(_BYTE *)(v7 + 63);
    v41 = *(_QWORD *)(v53 + 48);
    if ( !v41 )
      goto LABEL_63;
    v42 = -1;
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)(v41 + 2 * v43) );
    v44 = (unsigned int)(2 * v43 + 2);
    v45 = UMRxAllocateSecondaryBuffer(a1, v44);
    *(_QWORD *)(a3 + 664) = v45;
    if ( !v45 )
    {
      v17 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v17;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_63;
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      v20 = 84;
      goto LABEL_19;
    }
    memset(v45, 0, v44);
    v46 = *(_WORD **)(v53 + 48);
    do
      ++v42;
    while ( v46[v42] );
    memmove(*(void **)(a3 + 664), v46, 2 * v42);
  }
  else
  {
    v17 = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v17;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      v20 = 78;
LABEL_19:
      WPP_SF_qD(v18, v20, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v19, -1073741670);
    }
  }
LABEL_63:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v47 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v48 = PsGetCurrentThreadId();
    WPP_SF_qD(v47, 85, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v48, v17);
  }
  return v17;
}

```

## disassembly

```asm
0x140020e80  mov     [rsp+arg_18], rbx
0x140020e85  mov     [rsp+arg_0], rcx
0x140020e8a  push    rbp
0x140020e8b  push    rsi
0x140020e8c  push    rdi
0x140020e8d  push    r12
0x140020e8f  push    r13
0x140020e91  push    r14
0x140020e93  push    r15
0x140020e95  sub     rsp, 40h
0x140020e99  mov     rsi, [rdx+48h]
0x140020e9d  mov     rdi, r8
0x140020ea0  mov     r14, rdx
0x140020ea3  mov     r15, rcx
0x140020ea6  test    rsi, rsi
0x140020ea9  jnz     short loc_140020EB5
0x140020eab  mov     [rsp+78h+arg_10], rsi
0x140020eb3  jmp     short loc_140020EC1
0x140020eb5  mov     rax, [rsi+30h]
0x140020eb9  mov     [rsp+78h+arg_10], rax
0x140020ec1  mov     rbp, [rsi+20h]
0x140020ec5  mov     rax, [rdx+38h]
0x140020ec9  mov     [rsp+78h+arg_8], rax
0x140020ed1  test    rbp, rbp
0x140020ed4  jz      short loc_140020EDD
0x140020ed6  mov     rbp, [rbp+88h]
0x140020edd  mov     rbx, cs:WPP_GLOBAL_Control
0x140020ee4  lea     r12, WPP_GLOBAL_Control
0x140020eeb  cmp     rbx, r12
0x140020eee  jz      short loc_140020F66
0x140020ef0  test    dword ptr [rbx+2Ch], 4000h
0x140020ef7  jz      short loc_140020F20
0x140020ef9  mov     rbx, [rbx+18h]
0x140020efd  call    cs:__imp_PsGetCurrentThreadId
0x140020f04  nop     dword ptr [rax+rax+00h]
0x140020f09  mov     edx, 4Ch ; 'L'
0x140020f0e  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020f15  mov     r9, rax
0x140020f18  mov     rcx, rbx
0x140020f1b  call    WPP_SF_q
0x140020f20  mov     rbx, cs:WPP_GLOBAL_Control
0x140020f27  cmp     rbx, r12
0x140020f2a  jz      short loc_140020F66
0x140020f2c  test    dword ptr [rbx+2Ch], 2000h
0x140020f33  jz      short loc_140020F66
0x140020f35  mov     rbx, [rbx+18h]
0x140020f39  call    cs:__imp_PsGetCurrentThreadId
0x140020f40  nop     dword ptr [rax+rax+00h]
0x140020f45  mov     edx, 4Dh ; 'M'
0x140020f4a  mov     [rsp+78h+var_50], r14
0x140020f4f  mov     r9, rax
0x140020f52  mov     [rsp+78h+var_58], r15
0x140020f57  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020f5e  mov     rcx, rbx
0x140020f61  call    WPP_SF_qqq
0x140020f66  mov     dword ptr [rdi+30h], 0Ah
0x140020f6d  mov     rax, [rsi+28h]
0x140020f71  mov     rcx, [rax+20h]
0x140020f75  mov     rbx, [rcx+20h]
0x140020f79  test    rbx, rbx
0x140020f7c  jnz     short loc_140020F83
0x140020f7e  xor     r13d, r13d
0x140020f81  jmp     short loc_140020F87
0x140020f83  mov     r13, [rbx+20h]
0x140020f87  mov     rax, [rbx+40h]
0x140020f8b  mov     rcx, r15
0x140020f8e  movzx   r12d, word ptr [rax]
0x140020f92  add     r12, 2
0x140020f96  mov     rdx, r12
0x140020f99  call    UMRxAllocateSecondaryBuffer
0x140020f9e  mov     r15, rax
0x140020fa1  test    rax, rax
0x140020fa4  jnz     short loc_140021002
0x140020fa6  mov     esi, 0C000009Ah
0x140020fab  mov     rbx, cs:WPP_GLOBAL_Control
0x140020fb2  lea     rax, WPP_GLOBAL_Control
0x140020fb9  cmp     rbx, rax
0x140020fbc  jz      loc_140021445
0x140020fc2  test    dword ptr [rbx+2Ch], 2000h
0x140020fc9  jz      loc_1400213FE
0x140020fcf  mov     rbx, [rbx+18h]
0x140020fd3  call    cs:__imp_PsGetCurrentThreadId
0x140020fda  nop     dword ptr [rax+rax+00h]
0x140020fdf  lea     edx, [r15+4Eh]
0x140020fe3  mov     r9, rax
0x140020fe6  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140020fee  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020ff5  mov     rcx, rbx
0x140020ff8  call    WPP_SF_qD
0x140020ffd  jmp     loc_1400213FE
0x140021002  mov     rdx, [rbx+40h]
0x140021006  mov     rcx, r15; void *
0x140021009  movzx   r8d, word ptr [rdx]; Size
0x14002100d  mov     rdx, [rdx+8]; Src
0x140021011  call    memmove
0x140021016  shr     r12, 1
0x140021019  xor     eax, eax
0x14002101b  mov     [r15+r12*2-2], ax
0x140021021  mov     [rdi+288h], r15
0x140021028  mov     rbx, cs:WPP_GLOBAL_Control
0x14002102f  lea     rax, WPP_GLOBAL_Control
0x140021036  cmp     rbx, rax
0x140021039  jz      short loc_140021070
0x14002103b  test    dword ptr [rbx+2Ch], 4000h
0x140021042  jz      short loc_140021070
0x140021044  mov     rbx, [rbx+18h]
0x140021048  call    cs:__imp_PsGetCurrentThreadId
0x14002104f  nop     dword ptr [rax+rax+00h]
0x140021054  mov     edx, 4Fh ; 'O'
0x140021059  mov     [rsp+78h+var_58], r15
0x14002105e  mov     r9, rax
0x140021061  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021068  mov     rcx, rbx
0x14002106b  call    WPP_SF_qS
0x140021070  mov     eax, [r13+0]
0x140021074  mov     edx, 5Ch ; '\'; Ch
0x140021079  mov     [rdi+280h], eax
0x14002107f  mov     rax, [rsi+20h]
0x140021083  mov     rax, [rax+78h]
0x140021087  mov     r8, [rax+58h]
0x14002108b  mov     rax, [rax+20h]
0x14002108f  movzx   r12d, word ptr [r8]
0x140021093  mov     rcx, [rax+40h]
0x140021097  movzx   eax, word ptr [rcx]
0x14002109a  mov     rcx, [r8+8]
0x14002109e  sub     r12d, eax
0x1400210a1  add     rcx, 2; Str
0x1400210a5  call    cs:__imp_wcschr
0x1400210ac  nop     dword ptr [rax+rax+00h]
0x1400210b1  mov     rcx, [rsi+50h]
0x1400210b5  mov     r13, [rsp+78h+arg_0]
0x1400210bd  mov     [rsp+78h+Src], rax
0x1400210c2  movzx   ecx, word ptr [rcx]
0x1400210c5  add     ecx, 2
0x1400210c8  add     ecx, r12d
0x1400210cb  mov     ebx, ecx
0x1400210cd  mov     edx, ecx
0x1400210cf  mov     rcx, r13
0x1400210d2  call    UMRxAllocateSecondaryBuffer
0x1400210d7  mov     r15, rax
0x1400210da  test    rax, rax
0x1400210dd  jnz     short loc_140021121
0x1400210df  mov     esi, 0C000009Ah
0x1400210e4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400210eb  lea     rax, WPP_GLOBAL_Control
0x1400210f2  cmp     rbx, rax
0x1400210f5  jz      loc_140021445
0x1400210fb  test    dword ptr [rbx+2Ch], 2000h
0x140021102  jz      loc_1400213FE
0x140021108  mov     rbx, [rbx+18h]
0x14002110c  call    cs:__imp_PsGetCurrentThreadId
0x140021113  nop     dword ptr [rax+rax+00h]
0x140021118  lea     edx, [r15+50h]
0x14002111c  jmp     loc_140020FE3
0x140021121  mov     r8, rbx; Size
0x140021124  xor     edx, edx; Val
0x140021126  mov     rcx, r15; void *
0x140021129  call    memset
0x14002112e  mov     rdx, [rsp+78h+Src]; Src
0x140021133  mov     rcx, r15; void *
0x140021136  mov     r8d, r12d; Size
0x140021139  call    memmove
0x14002113e  mov     rdx, [rsi+50h]
0x140021142  mov     eax, r12d
0x140021145  shr     rax, 1
0x140021148  movzx   r8d, word ptr [rdx]; Size
0x14002114c  mov     rdx, [rdx+8]; Src
0x140021150  lea     rcx, [r15+rax*2]; void *
0x140021154  call    memmove
0x140021159  shr     rbx, 1
0x14002115c  xor     r12d, r12d
0x14002115f  mov     [r15+rbx*2-2], r12w
0x140021165  mov     [rdi+290h], r15
0x14002116c  mov     rbx, cs:WPP_GLOBAL_Control
0x140021173  lea     rcx, WPP_GLOBAL_Control
0x14002117a  cmp     rbx, rcx
0x14002117d  jz      short loc_1400211BB
0x14002117f  test    dword ptr [rbx+2Ch], 4000h
0x140021186  jz      short loc_1400211BB
0x140021188  mov     rbx, [rbx+18h]
0x14002118c  call    cs:__imp_PsGetCurrentThreadId
0x140021193  nop     dword ptr [rax+rax+00h]
0x140021198  lea     edx, [r12+51h]
0x14002119d  mov     [rsp+78h+var_58], r15
0x1400211a2  mov     r9, rax
0x1400211a5  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400211ac  mov     rcx, rbx
0x1400211af  call    WPP_SF_qS
0x1400211b4  lea     rcx, WPP_GLOBAL_Control
0x1400211bb  mov     rax, [rsi+28h]
0x1400211bf  mov     rsi, [rax+28h]
0x1400211c3  mov     eax, [rsi+50h]
0x1400211c6  mov     [rdi+278h], eax
0x1400211cc  mov     eax, [rsi+54h]
0x1400211cf  mov     [rdi+27Ch], eax
0x1400211d5  cmp     [rsi+48h], r12b
0x1400211d9  jnz     short loc_140021217
0x1400211db  mov     rbx, cs:WPP_GLOBAL_Control
0x1400211e2  cmp     rbx, rcx
0x1400211e5  jz      short loc_140021217
0x1400211e7  test    dword ptr [rbx+2Ch], 2000h
0x1400211ee  jz      short loc_140021217
0x1400211f0  mov     rbx, [rbx+18h]
0x1400211f4  call    cs:__imp_PsGetCurrentThreadId
0x1400211fb  nop     dword ptr [rax+rax+00h]
0x140021200  mov     edx, 52h ; 'R'
0x140021205  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002120c  mov     r9, rax
0x14002120f  mov     rcx, rbx
0x140021212  call    WPP_SF_q
0x140021217  mov     rdx, rdi
0x14002121a  mov     rcx, rsi; ClientContext
0x14002121d  call    UMRxImpersonateClient
0x140021222  mov     esi, eax
0x140021224  test    eax, eax
0x140021226  jns     short loc_140021271
0x140021228  mov     rbx, cs:WPP_GLOBAL_Control
0x14002122f  lea     r15, WPP_GLOBAL_Control
0x140021236  cmp     rbx, r15
0x140021239  jz      short loc_140021278
0x14002123b  test    dword ptr [rbx+2Ch], 2000h
0x140021242  jz      short loc_140021278
0x140021244  mov     rbx, [rbx+18h]
0x140021248  call    cs:__imp_PsGetCurrentThreadId
0x14002124f  nop     dword ptr [rax+rax+00h]
0x140021254  mov     edx, 53h ; 'S'
0x140021259  mov     dword ptr [rsp+78h+var_58], esi
0x14002125d  mov     r9, rax
0x140021260  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021267  mov     rcx, rbx
0x14002126a  call    WPP_SF_qD
0x14002126f  jmp     short loc_140021278
0x140021271  lea     r15, WPP_GLOBAL_Control
0x140021278  mov     rax, [r14+1C8h]
0x14002127f  movups  xmm0, xmmword ptr [rax]
0x140021282  movups  xmmword ptr [rdi+2A8h], xmm0
0x140021289  movups  xmm1, xmmword ptr [rax+10h]
0x14002128d  movups  xmmword ptr [rdi+2B8h], xmm1
0x140021294  movsd   xmm0, qword ptr [rax+20h]
0x140021299  movsd   qword ptr [rdi+2C8h], xmm0
0x1400212a1  mov     rax, [r14+38h]
0x1400212a5  mov     ecx, [rax+0E8h]
0x1400212ab  mov     eax, 4000h
0x1400212b0  test    eax, ecx
0x1400212b2  jz      short loc_1400212BA
0x1400212b4  or      [rdi+2C8h], eax
0x1400212ba  mov     dl, [rbp+3Ch]
0x1400212bd  mov     r8, [rsp+78h+arg_8]
0x1400212c5  mov     [rdi+2A0h], dl
0x1400212cb  test    dl, dl
0x1400212cd  jz      short loc_1400212E6
0x1400212cf  cmp     [rdi+2A8h], r12
0x1400212d6  jnz     short loc_1400212E6
0x1400212d8  mov     rax, [r8+0C8h]
0x1400212df  mov     [rdi+2A8h], rax
0x1400212e6  mov     al, [rbp+3Dh]
0x1400212e9  mov     [rdi+2A1h], al
0x1400212ef  test    al, al
0x1400212f1  jz      short loc_14002130A
0x1400212f3  cmp     [rdi+2B0h], r12
0x1400212fa  jnz     short loc_14002130A
0x1400212fc  mov     rax, [r8+0D0h]
0x140021303  mov     [rdi+2B0h], rax
0x14002130a  mov     cl, [rbp+3Eh]
0x14002130d  mov     [rdi+2A2h], cl
0x140021313  test    cl, cl
0x140021315  jz      short loc_14002132E
0x140021317  cmp     [rdi+2B8h], r12
0x14002131e  jnz     short loc_14002132E
0x140021320  mov     rax, [r8+0D8h]
0x140021327  mov     [rdi+2B8h], rax
0x14002132e  test    dl, dl
0x140021330  jz      short loc_14002134D
0x140021332  test    cl, cl
0x140021334  jz      short loc_14002134D
0x140021336  mov     rax, [rdi+2B8h]
0x14002133d  cmp     [rdi+2A8h], rax
0x140021344  jle     short loc_14002134D
0x140021346  mov     [rdi+2A8h], rax
0x14002134d  mov     r14, [rsp+78h+arg_10]
0x140021355  mov     al, [rbp+3Fh]
0x140021358  mov     [rdi+2A3h], al
0x14002135e  mov     rcx, [r14+30h]
0x140021362  test    rcx, rcx
0x140021365  jz      loc_1400213FE
0x14002136b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002136f  mov     rax, rbx
0x140021372  inc     rax
0x140021375  cmp     [rcx+rax*2], r12w
0x14002137a  jnz     short loc_140021372
0x14002137c  lea     eax, ds:2[rax*2]
0x140021383  mov     rcx, r13
0x140021386  mov     edx, eax
0x140021388  mov     ebp, eax
0x14002138a  call    UMRxAllocateSecondaryBuffer
0x14002138f  mov     [rdi+298h], rax
0x140021396  test    rax, rax
0x140021399  jnz     short loc_1400213D3
0x14002139b  mov     esi, 0C000009Ah
0x1400213a0  mov     rbx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
