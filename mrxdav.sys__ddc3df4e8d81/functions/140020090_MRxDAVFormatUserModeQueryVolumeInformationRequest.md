# MRxDAVFormatUserModeQueryVolumeInformationRequest

- ea: `0x140020090`
- end: `0x140020651`
- name: `MRxDAVFormatUserModeQueryVolumeInformationRequest`
- size: `1473`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x1400019bc`
- `0x140001a4c`
- `0x140001b64`
- `0x140006900`
- `0x140006c00`
- `0x140020090`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400200ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002010a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002017e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400201d5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020228`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400202b5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020300`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020380`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020426`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002047f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400204df`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002052e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020578`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400205c5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020625`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400200ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002010a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002017e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400201d5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020228`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400202b5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020300`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020380`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020426`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002047f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400204df`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002052e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020578`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400205c5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020625`
- `ntoskrnl!wcschr` at `0x1400203d1`
- `ntoskrnl!wcschr` at `0x1400203d1`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeQueryVolumeInformationRequest(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // r15
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // r13
  __int64 v12; // rbp
  __int64 v13; // rsi
  __int16 *v14; // rdi
  __int16 v15; // bx
  unsigned int v16; // eax
  __int16 *v17; // rdi
  __int64 v18; // rsi
  __int16 v19; // bx
  unsigned int v20; // eax
  __int16 *v21; // rdi
  __int64 v22; // rsi
  __int16 v23; // bx
  unsigned int v24; // eax
  __int64 v25; // rbx
  _DWORD *v26; // r15
  ULONG_PTR v27; // rsi
  PVOID SecondaryBuffer; // rax
  __int64 v29; // rdi
  unsigned int v30; // edi
  __int64 v31; // rbx
  HANDLE v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rbx
  HANDLE v35; // rax
  __int64 v37; // rbx
  unsigned int v38; // eax
  unsigned __int16 *v39; // rcx
  unsigned int v40; // ebx
  wchar_t *v41; // r15
  PVOID v42; // rax
  void *v43; // rdi
  __int64 v44; // rbx
  unsigned int v45; // eax
  __int64 v46; // rbx
  HANDLE v47; // rax
  int v48; // ebx
  __int64 v49; // rdi
  HANDLE v50; // rax
  int v51; // ebx
  __int64 v52; // rdi
  HANDLE v53; // rax
  __int64 v54; // rbx
  HANDLE v55; // rax
  __int64 v56; // rbx
  HANDLE v57; // rax

  v3 = *(_QWORD **)(a2 + 72);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v7, 94, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_qqq(v9, 95, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v10, a1, a2);
    }
  }
  *(_DWORD *)(a3 + 48) = 11;
  v11 = *(_QWORD *)(v3[4] + 120LL);
  v12 = *(_QWORD *)(v3[5] + 40LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v14 = *(__int16 **)(*(_QWORD *)(v11 + 32) + 64LL);
      v15 = *v14;
      v16 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qZd(v13, 96, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v16, (__int64)v14, v15);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v17 = *(__int16 **)(v11 + 88);
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = *v17;
        v20 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZd(v18, 97, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v20, (__int64)v17, v19);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v21 = (__int16 *)v3[10];
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v23 = *v21;
        v24 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZd(v22, 98, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v24, (__int64)v21, v23);
      }
    }
  }
  v25 = *(_QWORD *)(*(_QWORD *)(v3[5] + 32LL) + 32LL);
  if ( v25 )
    v26 = *(_DWORD **)(v25 + 32);
  else
    v26 = 0;
  v27 = **(unsigned __int16 **)(v25 + 64) + 2LL;
  SecondaryBuffer = UMRxAllocateSecondaryBuffer(a1, v27);
  v29 = (__int64)SecondaryBuffer;
  if ( SecondaryBuffer )
  {
    memmove(SecondaryBuffer, *(const void **)(*(_QWORD *)(v25 + 64) + 8LL), **(unsigned __int16 **)(v25 + 64));
    *(_WORD *)(v29 + 2 * (v27 >> 1) - 2) = 0;
    *(_QWORD *)(a3 + 632) = v29;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v37 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v38 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v37, 100, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v38, v29);
    }
    *(_DWORD *)(a3 + 656) = *v26;
    v39 = *(unsigned __int16 **)(v11 + 88);
    v40 = *v39 - **(unsigned __int16 **)(*(_QWORD *)(v11 + 32) + 64LL);
    v41 = wcschr((const wchar_t *)(*((_QWORD *)v39 + 1) + 2LL), 0x5Cu);
    v42 = UMRxAllocateSecondaryBuffer(a1, v40 + 2LL);
    v43 = v42;
    if ( v42 )
    {
      *(_QWORD *)(a3 + 640) = v42;
      memset(v42, 0, v40 + 2LL);
      memmove(v43, v41, v40);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v44 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v45 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qS(v44, 102, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v45, (__int64)v43);
      }
      *(_DWORD *)(a3 + 648) = *(_DWORD *)(v12 + 80);
      *(_DWORD *)(a3 + 652) = *(_DWORD *)(v12 + 84);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v46 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v47 = PsGetCurrentThreadId();
          WPP_SF_qq(v46, 103, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v47, v12);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v48 = *(_DWORD *)(v12 + 80);
            v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v50 = PsGetCurrentThreadId();
            WPP_SF_qD(v49, 104, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v50, v48);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v51 = *(_DWORD *)(v12 + 84);
            v52 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v53 = PsGetCurrentThreadId();
            WPP_SF_qD(v52, 105, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v53, v51);
          }
        }
      }
      if ( !*(_BYTE *)(v12 + 72)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v54 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v55 = PsGetCurrentThreadId();
        WPP_SF_q(v54, 106, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v55);
      }
      v30 = UMRxImpersonateClient((PSECURITY_CLIENT_CONTEXT)v12);
      if ( (v30 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v30;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v56 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v57 = PsGetCurrentThreadId();
          WPP_SF_qD(v56, 107, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v57, v30);
        }
      }
      goto LABEL_24;
    }
    v30 = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v30;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_24;
    v31 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v32 = PsGetCurrentThreadId();
    v33 = 101;
    goto LABEL_23;
  }
  v30 = -1073741670;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v30;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v31 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v32 = PsGetCurrentThreadId();
    v33 = 99;
LABEL_23:
    WPP_SF_qD(v31, v33, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v32, -1073741670);
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v34 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v35 = PsGetCurrentThreadId();
    WPP_SF_qD(v34, 108, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v35, v30);
  }
  return v30;
}

```

## disassembly

```asm
0x140020090  push    rbx
0x140020092  push    rbp
0x140020093  push    rsi
0x140020094  push    rdi
0x140020095  push    r12
0x140020097  push    r13
0x140020099  push    r14
0x14002009b  push    r15
0x14002009d  sub     rsp, 38h
0x1400200a1  mov     r15, [rdx+48h]
0x1400200a5  mov     r14, r8
0x1400200a8  mov     rdi, rdx
0x1400200ab  mov     r12, rcx
0x1400200ae  mov     rbx, cs:WPP_GLOBAL_Control
0x1400200b5  lea     rsi, WPP_GLOBAL_Control
0x1400200bc  cmp     rbx, rsi
0x1400200bf  jz      short loc_140020137
0x1400200c1  test    dword ptr [rbx+2Ch], 4000h
0x1400200c8  jz      short loc_1400200F1
0x1400200ca  mov     rbx, [rbx+18h]
0x1400200ce  call    cs:__imp_PsGetCurrentThreadId
0x1400200d5  nop     dword ptr [rax+rax+00h]
0x1400200da  mov     edx, 5Eh ; '^'
0x1400200df  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400200e6  mov     r9, rax
0x1400200e9  mov     rcx, rbx
0x1400200ec  call    WPP_SF_q
0x1400200f1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400200f8  cmp     rbx, rsi
0x1400200fb  jz      short loc_140020137
0x1400200fd  test    dword ptr [rbx+2Ch], 2000h
0x140020104  jz      short loc_140020137
0x140020106  mov     rbx, [rbx+18h]
0x14002010a  call    cs:__imp_PsGetCurrentThreadId
0x140020111  nop     dword ptr [rax+rax+00h]
0x140020116  mov     edx, 5Fh ; '_'
0x14002011b  mov     [rsp+78h+var_50], rdi
0x140020120  mov     r9, rax
0x140020123  mov     [rsp+78h+var_58], r12
0x140020128  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002012f  mov     rcx, rbx
0x140020132  call    WPP_SF_qqq
0x140020137  mov     dword ptr [r14+30h], 0Bh
0x14002013f  mov     rax, [r15+20h]
0x140020143  mov     r13, [rax+78h]
0x140020147  mov     rax, [r15+28h]
0x14002014b  mov     rbp, [rax+28h]
0x14002014f  mov     rsi, cs:WPP_GLOBAL_Control
0x140020156  lea     rax, WPP_GLOBAL_Control
0x14002015d  cmp     rsi, rax
0x140020160  jz      loc_140020254
0x140020166  test    dword ptr [rsi+2Ch], 4000h
0x14002016d  jz      short loc_1400201AA
0x14002016f  mov     rax, [r13+20h]
0x140020173  mov     rsi, [rsi+18h]
0x140020177  mov     rdi, [rax+40h]
0x14002017b  movzx   ebx, word ptr [rdi]
0x14002017e  call    cs:__imp_PsGetCurrentThreadId
0x140020185  nop     dword ptr [rax+rax+00h]
0x14002018a  mov     edx, 60h ; '`'
0x14002018f  mov     dword ptr [rsp+78h+var_50], ebx
0x140020193  mov     r9, rax
0x140020196  mov     [rsp+78h+var_58], rdi
0x14002019b  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400201a2  mov     rcx, rsi
0x1400201a5  call    WPP_SF_qZd
0x1400201aa  mov     rsi, cs:WPP_GLOBAL_Control
0x1400201b1  lea     rax, WPP_GLOBAL_Control
0x1400201b8  cmp     rsi, rax
0x1400201bb  jz      loc_140020254
0x1400201c1  test    dword ptr [rsi+2Ch], 4000h
0x1400201c8  jz      short loc_140020201
0x1400201ca  mov     rdi, [r13+58h]
0x1400201ce  mov     rsi, [rsi+18h]
0x1400201d2  movzx   ebx, word ptr [rdi]
0x1400201d5  call    cs:__imp_PsGetCurrentThreadId
0x1400201dc  nop     dword ptr [rax+rax+00h]
0x1400201e1  mov     edx, 61h ; 'a'
0x1400201e6  mov     dword ptr [rsp+78h+var_50], ebx
0x1400201ea  mov     r9, rax
0x1400201ed  mov     [rsp+78h+var_58], rdi
0x1400201f2  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400201f9  mov     rcx, rsi
0x1400201fc  call    WPP_SF_qZd
0x140020201  mov     rsi, cs:WPP_GLOBAL_Control
0x140020208  lea     rax, WPP_GLOBAL_Control
0x14002020f  cmp     rsi, rax
0x140020212  jz      short loc_140020254
0x140020214  test    dword ptr [rsi+2Ch], 4000h
0x14002021b  jz      short loc_140020254
0x14002021d  mov     rdi, [r15+50h]
0x140020221  mov     rsi, [rsi+18h]
0x140020225  movzx   ebx, word ptr [rdi]
0x140020228  call    cs:__imp_PsGetCurrentThreadId
0x14002022f  nop     dword ptr [rax+rax+00h]
0x140020234  mov     edx, 62h ; 'b'
0x140020239  mov     dword ptr [rsp+78h+var_50], ebx
0x14002023d  mov     r9, rax
0x140020240  mov     [rsp+78h+var_58], rdi
0x140020245  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002024c  mov     rcx, rsi
0x14002024f  call    WPP_SF_qZd
0x140020254  mov     rax, [r15+28h]
0x140020258  mov     rcx, [rax+20h]
0x14002025c  mov     rbx, [rcx+20h]
0x140020260  test    rbx, rbx
0x140020263  jnz     short loc_14002026A
0x140020265  xor     r15d, r15d
0x140020268  jmp     short loc_14002026E
0x14002026a  mov     r15, [rbx+20h]
0x14002026e  mov     rax, [rbx+40h]
0x140020272  mov     rcx, r12
0x140020275  movzx   esi, word ptr [rax]
0x140020278  add     rsi, 2
0x14002027c  mov     rdx, rsi
0x14002027f  call    UMRxAllocateSecondaryBuffer
0x140020284  mov     rdi, rax
0x140020287  test    rax, rax
0x14002028a  jnz     loc_14002033B
0x140020290  mov     edi, 0C000009Ah
0x140020295  mov     rbx, cs:WPP_GLOBAL_Control
0x14002029c  lea     rax, WPP_GLOBAL_Control
0x1400202a3  cmp     rbx, rax
0x1400202a6  jz      short loc_140020327
0x1400202a8  test    dword ptr [rbx+2Ch], 2000h
0x1400202af  jz      short loc_1400202E0
0x1400202b1  mov     rbx, [rbx+18h]
0x1400202b5  call    cs:__imp_PsGetCurrentThreadId
0x1400202bc  nop     dword ptr [rax+rax+00h]
0x1400202c1  mov     edx, 63h ; 'c'
0x1400202c6  mov     r9, rax
0x1400202c9  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x1400202d1  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400202d8  mov     rcx, rbx
0x1400202db  call    WPP_SF_qD
0x1400202e0  lea     rsi, WPP_GLOBAL_Control
0x1400202e7  mov     rbx, cs:WPP_GLOBAL_Control
0x1400202ee  cmp     rbx, rsi
0x1400202f1  jz      short loc_140020327
0x1400202f3  test    dword ptr [rbx+2Ch], 2000h
0x1400202fa  jz      short loc_140020327
0x1400202fc  mov     rbx, [rbx+18h]
0x140020300  call    cs:__imp_PsGetCurrentThreadId
0x140020307  nop     dword ptr [rax+rax+00h]
0x14002030c  mov     edx, 6Ch ; 'l'
0x140020311  mov     dword ptr [rsp+78h+var_58], edi
0x140020315  mov     r9, rax
0x140020318  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002031f  mov     rcx, rbx
0x140020322  call    WPP_SF_qD
0x140020327  mov     eax, edi
0x140020329  add     rsp, 38h
0x14002032d  pop     r15
0x14002032f  pop     r14
0x140020331  pop     r13
0x140020333  pop     r12
0x140020335  pop     rdi
0x140020336  pop     rsi
0x140020337  pop     rbp
0x140020338  pop     rbx
0x140020339  retn
0x14002033b  mov     rdx, [rbx+40h]
0x14002033f  mov     rcx, rdi; void *
0x140020342  movzx   r8d, word ptr [rdx]; Size
0x140020346  mov     rdx, [rdx+8]; Src
0x14002034a  call    memmove
0x14002034f  shr     rsi, 1
0x140020352  xor     eax, eax
0x140020354  mov     [rdi+rsi*2-2], ax
0x140020359  mov     [r14+278h], rdi
0x140020360  mov     rbx, cs:WPP_GLOBAL_Control
0x140020367  lea     rax, WPP_GLOBAL_Control
0x14002036e  cmp     rbx, rax
0x140020371  jz      short loc_1400203A8
0x140020373  test    dword ptr [rbx+2Ch], 4000h
0x14002037a  jz      short loc_1400203A8
0x14002037c  mov     rbx, [rbx+18h]
0x140020380  call    cs:__imp_PsGetCurrentThreadId
0x140020387  nop     dword ptr [rax+rax+00h]
0x14002038c  mov     edx, 64h ; 'd'
0x140020391  mov     [rsp+78h+var_58], rdi
0x140020396  mov     r9, rax
0x140020399  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400203a0  mov     rcx, rbx
0x1400203a3  call    WPP_SF_qS
0x1400203a8  mov     eax, [r15]
0x1400203ab  mov     edx, 5Ch ; '\'; Ch
0x1400203b0  mov     [r14+290h], eax
0x1400203b7  mov     rax, [r13+20h]
0x1400203bb  mov     rcx, [rax+40h]
0x1400203bf  movzx   edi, word ptr [rcx]
0x1400203c2  mov     rcx, [r13+58h]
0x1400203c6  movzx   ebx, word ptr [rcx]
0x1400203c9  mov     rcx, [rcx+8]
0x1400203cd  add     rcx, 2; Str
0x1400203d1  call    cs:__imp_wcschr
0x1400203d8  nop     dword ptr [rax+rax+00h]
0x1400203dd  sub     rbx, rdi
0x1400203e0  mov     rcx, r12
0x1400203e3  mov     ebx, ebx
0x1400203e5  mov     r15, rax
0x1400203e8  lea     rdx, [rbx+2]
0x1400203ec  call    UMRxAllocateSecondaryBuffer
0x1400203f1  mov     rdi, rax
0x1400203f4  test    rax, rax
0x1400203f7  jnz     short loc_14002043C
0x1400203f9  mov     edi, 0C000009Ah
0x1400203fe  mov     rbx, cs:WPP_GLOBAL_Control
0x140020405  lea     rax, WPP_GLOBAL_Control
0x14002040c  cmp     rbx, rax
0x14002040f  jz      loc_140020327
0x140020415  test    dword ptr [rbx+2Ch], 2000h
0x14002041c  jz      loc_1400202E0
0x140020422  mov     rbx, [rbx+18h]
0x140020426  call    cs:__imp_PsGetCurrentThreadId
0x14002042d  nop     dword ptr [rax+rax+00h]
0x140020432  mov     edx, 65h ; 'e'
0x140020437  jmp     loc_1400202C6
0x14002043c  lea     r8, [rbx+2]; Size
0x140020440  mov     [r14+280h], rdi
0x140020447  xor     edx, edx; Val
0x140020449  mov     rcx, rdi; void *
0x14002044c  call    memset
0x140020451  mov     r8, rbx; Size
0x140020454  mov     rdx, r15; Src
0x140020457  mov     rcx, rdi; void *
0x14002045a  call    memmove
0x14002045f  mov     rbx, cs:WPP_GLOBAL_Control
0x140020466  lea     rax, WPP_GLOBAL_Control
0x14002046d  cmp     rbx, rax
0x140020470  jz      short loc_1400204A7
0x140020472  test    dword ptr [rbx+2Ch], 4000h
0x140020479  jz      short loc_1400204A7
0x14002047b  mov     rbx, [rbx+18h]
0x14002047f  call    cs:__imp_PsGetCurrentThreadId
0x140020486  nop     dword ptr [rax+rax+00h]
0x14002048b  mov     edx, 66h ; 'f'
0x140020490  mov     [rsp+78h+var_58], rdi
0x140020495  mov     r9, rax
0x140020498  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002049f  mov     rcx, rbx
0x1400204a2  call    WPP_SF_qS
0x1400204a7  mov     eax, [rbp+50h]
0x1400204aa  mov     [r14+288h], eax
0x1400204b1  mov     eax, [rbp+54h]
0x1400204b4  mov     [r14+28Ch], eax
0x1400204bb  mov     rbx, cs:WPP_GLOBAL_Control
0x1400204c2  lea     rax, WPP_GLOBAL_Control
0x1400204c9  cmp     rbx, rax
0x1400204cc  jz      loc_1400205A6
0x1400204d2  test    dword ptr [rbx+2Ch], 4000h
0x1400204d9  jz      short loc_140020507
0x1400204db  mov     rbx, [rbx+18h]
0x1400204df  call    cs:__imp_PsGetCurrentThreadId
0x1400204e6  nop     dword ptr [rax+rax+00h]
0x1400204eb  mov     edx, 67h ; 'g'
0x1400204f0  mov     [rsp+78h+var_58], rbp
0x1400204f5  mov     r9, rax
0x1400204f8  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400204ff  mov     rcx, rbx
0x140020502  call    WPP_SF_qq
0x140020507  mov     rdi, cs:WPP_GLOBAL_Control
0x14002050e  lea     rax, WPP_GLOBAL_Control
0x140020515  cmp     rdi, rax
0x140020518  jz      loc_1400205A6
0x14002051e  test    dword ptr [rdi+2Ch], 4000h
0x140020525  jz      short loc_140020555
0x140020527  mov     ebx, [rbp+50h]
0x14002052a  mov     rdi, [rdi+18h]
0x14002052e  call    cs:__imp_PsGetCurrentThreadId
0x140020535  nop     dword ptr [rax+rax+00h]
0x14002053a  mov     edx, 68h ; 'h'
0x14002053f  mov     dword ptr [rsp+78h+var_58], ebx
0x140020543  mov     r9, rax
0x140020546  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002054d  mov     rcx, rdi
0x140020550  call    WPP_SF_qD
0x140020555  mov     rdi, cs:WPP_GLOBAL_Control
0x14002055c  lea     rax, WPP_GLOBAL_Control
0x140020563  cmp     rdi, rax
0x140020566  jz      short loc_1400205A6
0x140020568  test    dword ptr [rdi+2Ch], 4000h
0x14002056f  jz      short loc_14002059F
0x140020571  mov     ebx, [rbp+54h]
0x140020574  mov     rdi, [rdi+18h]
0x140020578  call    cs:__imp_PsGetCurrentThreadId
0x14002057f  nop     dword ptr [rax+rax+00h]
0x140020584  mov     edx, 69h ; 'i'
0x140020589  mov     dword ptr [rsp+78h+var_58], ebx
0x14002058d  mov     r9, rax
0x140020590  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140020597  mov     rcx, rdi
0x14002059a  call    WPP_SF_qD
0x14002059f  lea     rax, WPP_GLOBAL_Control
0x1400205a6  cmp     byte ptr [rbp+48h], 0
0x1400205aa  jnz     short loc_1400205E8
0x1400205ac  mov     rbx, cs:WPP_GLOBAL_Control
0x1400205b3  cmp     rbx, rax
0x1400205b6  jz      short loc_1400205E8
0x1400205b8  test    dword ptr [rbx+2Ch], 2000h
  ... truncated ...
```
