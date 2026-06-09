# MRxDAVFormatUserModeQueryDirectoryRequest

- ea: `0x14001dec0`
- end: `0x14001e699`
- name: `MRxDAVFormatUserModeQueryDirectoryRequest`
- size: `2009`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x1400019bc`
- `0x140001a4c`
- `0x140001b64`
- `0x140003064`
- `0x140006900`
- `0x140006c00`
- `0x14001dec0`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001df13`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001df56`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001dfe0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e03f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e092`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e141`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e1b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e2a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e3cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e498`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e4e7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e52c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e570`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e5d7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e614`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e657`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001df13`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001df56`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001dfe0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e03f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e092`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e141`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e1b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e2a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e3cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e498`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e4e7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e52c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e570`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e5d7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e614`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e657`
- `ntoskrnl!wcschr` at `0x14001e215`
- `ntoskrnl!wcschr` at `0x14001e215`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeQueryDirectoryRequest(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // r15
  __int64 v5; // rbp
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  _QWORD *v12; // r12
  _QWORD *v13; // rcx
  __int64 v14; // r13
  __int64 v15; // rsi
  __int16 *v16; // rdi
  __int16 v17; // bx
  unsigned int v18; // eax
  __int16 *v19; // rdi
  __int64 v20; // rsi
  __int16 v21; // bx
  unsigned int v22; // eax
  __int16 *v23; // rdi
  __int64 v24; // rsi
  __int16 v25; // bx
  unsigned int v26; // eax
  _DWORD *v27; // r12
  __int64 v28; // rbx
  ULONG_PTR v29; // rsi
  PVOID SecondaryBuffer; // rax
  __int64 v31; // rdi
  unsigned int v32; // edi
  __int64 v33; // rbx
  HANDLE v34; // rax
  __int64 v35; // rbx
  unsigned int v36; // eax
  unsigned __int16 *v37; // r8
  size_t v38; // rbx
  unsigned __int16 *v39; // r12
  int v40; // ecx
  ULONG_PTR v41; // rdx
  size_t v42; // rsi
  char *v43; // rax
  char *v44; // rdi
  __int64 v45; // rbx
  HANDLE v46; // rax
  __int64 v47; // rdx
  unsigned __int16 *v48; // rdx
  size_t v49; // rax
  _WORD *v50; // rdx
  char *v51; // rcx
  unsigned __int16 *v52; // rdx
  size_t v53; // r8
  unsigned __int64 v54; // rdx
  bool v55; // zf
  int v56; // ecx
  __int64 v57; // r12
  int v58; // r8d
  unsigned int v59; // ecx
  size_t v60; // rsi
  char *v61; // rax
  __int64 v62; // rbx
  unsigned int v63; // eax
  int v64; // edx
  int v65; // r8d
  __int64 v66; // rbx
  HANDLE v67; // rax
  int v68; // ebx
  __int64 v69; // rdi
  HANDLE v70; // rax
  int v71; // ebx
  __int64 v72; // rdi
  HANDLE v73; // rax
  __int64 v74; // rbx
  HANDLE v75; // rax
  __int64 v76; // rbx
  HANDLE v77; // rax
  __int64 v78; // rbx
  HANDLE v79; // rax
  int v83; // [rsp+78h] [rbp+10h]
  _QWORD *Src; // [rsp+80h] [rbp+18h]
  wchar_t *Srca; // [rsp+80h] [rbp+18h]

  v3 = *(_QWORD **)(a2 + 72);
  v5 = *(_QWORD *)(a2 + 64);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 27, WPP_609949de13fe38daba556366630c430b_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 28, WPP_609949de13fe38daba556366630c430b_Traceguids, v11, a1, a2);
    }
  }
  *(_DWORD *)(a3 + 48) = 2;
  v12 = 0;
  if ( v5 )
    v12 = *(_QWORD **)(v5 + 56);
  v13 = *(_QWORD **)(v3[4] + 120LL);
  Src = v13;
  v14 = *(_QWORD *)(v3[5] + 40LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = *(__int16 **)(v13[4] + 64LL);
      v17 = *v16;
      v18 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qZd(v15, 29, (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids, v18, (__int64)v16, v17);
      v13 = Src;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v19 = (__int16 *)v13[11];
        v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v21 = *v19;
        v22 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZd(v20, 30, (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids, v22, (__int64)v19, v21);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v23 = (__int16 *)v3[10];
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v25 = *v23;
        v26 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZd(v24, 31, (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids, v26, (__int64)v23, v25);
      }
    }
  }
  if ( *v12 )
  {
    *(_DWORD *)(a3 + 632) = 1;
    goto LABEL_73;
  }
  v27 = 0;
  *(_DWORD *)(a3 + 632) = 0;
  v28 = *(_QWORD *)(*(_QWORD *)(v3[5] + 32LL) + 32LL);
  if ( v28 )
    v27 = *(_DWORD **)(v28 + 32);
  v29 = **(unsigned __int16 **)(v28 + 64) + 2LL;
  SecondaryBuffer = UMRxAllocateSecondaryBuffer(a1, v29);
  v31 = (__int64)SecondaryBuffer;
  if ( SecondaryBuffer )
  {
    memmove(SecondaryBuffer, *(const void **)(*(_QWORD *)(v28 + 64) + 8LL), **(unsigned __int16 **)(v28 + 64));
    *(_WORD *)(v31 + 2 * (v29 >> 1) - 2) = 0;
    *(_QWORD *)(a3 + 648) = v31;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v35 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v36 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v35, 33, (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids, v36, v31);
    }
    *(_DWORD *)(a3 + 656) = *v27;
    v37 = (unsigned __int16 *)Src[11];
    v38 = *v37 - (unsigned int)**(unsigned __int16 **)(Src[4] + 64LL);
    Srca = wcschr((const wchar_t *)(*((_QWORD *)v37 + 1) + 2LL), 0x5Cu);
    *(_DWORD *)(a3 + 636) = *(unsigned __int8 *)(a2 + 520);
    v39 = (unsigned __int16 *)v3[10];
    v40 = *v39;
    if ( *(_BYTE *)(a2 + 520) )
    {
      v41 = (unsigned int)(v38 + 2);
      if ( (_WORD)v40 )
        v41 = (unsigned int)(v40 + v38 + 4);
      v42 = (unsigned int)v41;
      v43 = (char *)UMRxAllocateSecondaryBuffer(a1, v41);
      v44 = v43;
      if ( !v43 )
      {
        v32 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v32;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          goto LABEL_81;
        v45 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v46 = PsGetCurrentThreadId();
        v47 = 34;
LABEL_37:
        WPP_SF_qD(v45, v47, WPP_609949de13fe38daba556366630c430b_Traceguids, v46, -1073741670);
        goto LABEL_81;
      }
      *(_QWORD *)(a3 + 664) = v43;
      memset(v43, 0, v42);
      memmove(v44, Srca, v38);
      v48 = (unsigned __int16 *)v3[10];
      v49 = *v48;
      if ( !(_WORD)v49 )
      {
LABEL_61:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v62 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v63 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qs(v62, v64, v65, v63, (__int64)v44);
        }
        *(_DWORD *)(a3 + 640) = *(_DWORD *)(v14 + 80);
        *(_DWORD *)(a3 + 644) = *(_DWORD *)(v14 + 84);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v66 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v67 = PsGetCurrentThreadId();
            WPP_SF_qq(v66, 37, WPP_609949de13fe38daba556366630c430b_Traceguids, v67, v14);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v68 = *(_DWORD *)(v14 + 80);
              v69 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v70 = PsGetCurrentThreadId();
              WPP_SF_qD(v69, 38, WPP_609949de13fe38daba556366630c430b_Traceguids, v70, v68);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v71 = *(_DWORD *)(v14 + 84);
              v72 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v73 = PsGetCurrentThreadId();
              WPP_SF_qD(v72, 39, WPP_609949de13fe38daba556366630c430b_Traceguids, v73, v71);
            }
          }
        }
LABEL_73:
        if ( v14 )
        {
          v32 = UMRxImpersonateClient((PSECURITY_CLIENT_CONTEXT)v14);
          if ( (v32 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v32;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v74 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v75 = PsGetCurrentThreadId();
              WPP_SF_qD(v74, 40, WPP_609949de13fe38daba556366630c430b_Traceguids, v75, v32);
            }
          }
        }
        else
        {
          v32 = -1073741811;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v32;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v76 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v77 = PsGetCurrentThreadId();
            WPP_SF_q(v76, 41, WPP_609949de13fe38daba556366630c430b_Traceguids, v77);
          }
        }
        goto LABEL_81;
      }
      v50 = (_WORD *)*((_QWORD *)v48 + 1);
      v51 = &v44[v38];
      if ( *v50 == 92 )
      {
        v53 = v49;
      }
      else
      {
        *(_WORD *)v51 = 92;
        v51 += 2;
        v52 = (unsigned __int16 *)v3[10];
        v53 = *v52;
        v50 = (_WORD *)*((_QWORD *)v52 + 1);
      }
    }
    else
    {
      v54 = *v39;
      v55 = v40 == 0;
      v56 = 0;
      if ( v55 )
      {
        v57 = 0;
      }
      else
      {
        v57 = *((_QWORD *)v39 + 1);
        LOBYTE(v56) = *(_WORD *)(v57 + 2 * (v54 >> 1) - 2) == 92;
      }
      v58 = *(unsigned __int16 *)(v5 + 80);
      v83 = v56;
      if ( v56 )
      {
        v59 = v58 + v54 + v38 + 4;
      }
      else
      {
        v59 = v38 + v58 + 4;
        if ( v57 )
          v59 += v54 + 2;
      }
      v60 = v59;
      v61 = (char *)UMRxAllocateSecondaryBuffer(a1, v59);
      v44 = v61;
      if ( !v61 )
      {
        v32 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v32;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          goto LABEL_81;
        v45 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v46 = PsGetCurrentThreadId();
        v47 = 35;
        goto LABEL_37;
      }
      *(_QWORD *)(a3 + 664) = v61;
      memset(v61, 0, v60);
      memmove(v44, Srca, (unsigned int)v38);
      if ( v57 )
      {
        if ( **(_WORD **)(v3[10] + 8LL) != 92 )
        {
          *(_WORD *)&v44[v38] = 92;
          LODWORD(v38) = v38 + 2;
        }
        memmove(&v44[(unsigned int)v38], *(const void **)(v3[10] + 8LL), *(unsigned __int16 *)v3[10]);
        v51 = &v44[(unsigned int)v38 + *(unsigned __int16 *)v3[10]];
        if ( !v83 )
        {
          *(_WORD *)v51 = 92;
          v51 += 2;
        }
      }
      else
      {
        *(_WORD *)&v44[v38] = 92;
        v51 = &v44[v38 + 2];
      }
      v53 = *(unsigned __int16 *)(v5 + 80);
      v50 = *(_WORD **)(v5 + 88);
    }
    memmove(v51, v50, v53);
    goto LABEL_61;
  }
  v32 = -1073741670;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v32;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v34 = PsGetCurrentThreadId();
    WPP_SF_qD(v33, 32, WPP_609949de13fe38daba556366630c430b_Traceguids, v34, -1073741670);
  }
LABEL_81:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v78 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v79 = PsGetCurrentThreadId();
    WPP_SF_qD(v78, 42, WPP_609949de13fe38daba556366630c430b_Traceguids, v79, v32);
  }
  return v32;
}

```

## disassembly

```asm
0x14001dec0  mov     [rsp+arg_18], rbx
0x14001dec5  mov     [rsp+arg_8], rdx
0x14001deca  mov     [rsp+arg_0], rcx
0x14001decf  push    rbp
0x14001ded0  push    rsi
0x14001ded1  push    rdi
0x14001ded2  push    r12
0x14001ded4  push    r13
0x14001ded6  push    r14
0x14001ded8  push    r15
0x14001deda  sub     rsp, 30h
0x14001dede  mov     r15, [rdx+48h]
0x14001dee2  mov     r14, r8
0x14001dee5  mov     rbp, [rdx+40h]
0x14001dee9  mov     rdi, rdx
0x14001deec  mov     rsi, rcx
0x14001deef  mov     rbx, cs:WPP_GLOBAL_Control
0x14001def6  lea     rdx, WPP_GLOBAL_Control
0x14001defd  cmp     rbx, rdx
0x14001df00  jz      loc_14001DF8A
0x14001df06  test    dword ptr [rbx+2Ch], 4000h
0x14001df0d  jz      short loc_14001DF3D
0x14001df0f  mov     rbx, [rbx+18h]
0x14001df13  call    cs:__imp_PsGetCurrentThreadId
0x14001df1a  nop     dword ptr [rax+rax+00h]
0x14001df1f  mov     edx, 1Bh
0x14001df24  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001df2b  mov     r9, rax
0x14001df2e  mov     rcx, rbx
0x14001df31  call    WPP_SF_q
0x14001df36  lea     rdx, WPP_GLOBAL_Control
0x14001df3d  mov     rbx, cs:WPP_GLOBAL_Control
0x14001df44  cmp     rbx, rdx
0x14001df47  jz      short loc_14001DF8A
0x14001df49  test    dword ptr [rbx+2Ch], 2000h
0x14001df50  jz      short loc_14001DF8A
0x14001df52  mov     rbx, [rbx+18h]
0x14001df56  call    cs:__imp_PsGetCurrentThreadId
0x14001df5d  nop     dword ptr [rax+rax+00h]
0x14001df62  mov     edx, 1Ch
0x14001df67  mov     [rsp+68h+var_40], rdi
0x14001df6c  mov     r9, rax
0x14001df6f  mov     [rsp+68h+var_48], rsi
0x14001df74  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001df7b  mov     rcx, rbx
0x14001df7e  call    WPP_SF_qqq
0x14001df83  lea     rdx, WPP_GLOBAL_Control
0x14001df8a  xor     eax, eax
0x14001df8c  mov     dword ptr [r14+30h], 2
0x14001df94  mov     r12d, eax
0x14001df97  test    rbp, rbp
0x14001df9a  jz      short loc_14001DFA0
0x14001df9c  mov     r12, [rbp+38h]
0x14001dfa0  mov     rax, [r15+20h]
0x14001dfa4  mov     rcx, [rax+78h]
0x14001dfa8  mov     rax, [r15+28h]
0x14001dfac  mov     [rsp+68h+Src], rcx
0x14001dfb4  mov     r13, [rax+28h]
0x14001dfb8  mov     rsi, cs:WPP_GLOBAL_Control
0x14001dfbf  cmp     rsi, rdx
0x14001dfc2  jz      loc_14001E0BE
0x14001dfc8  test    dword ptr [rsi+2Ch], 4000h
0x14001dfcf  jz      short loc_14001E01B
0x14001dfd1  mov     rax, [rcx+20h]
0x14001dfd5  mov     rsi, [rsi+18h]
0x14001dfd9  mov     rdi, [rax+40h]
0x14001dfdd  movzx   ebx, word ptr [rdi]
0x14001dfe0  call    cs:__imp_PsGetCurrentThreadId
0x14001dfe7  nop     dword ptr [rax+rax+00h]
0x14001dfec  mov     edx, 1Dh
0x14001dff1  mov     dword ptr [rsp+68h+var_40], ebx
0x14001dff5  mov     r9, rax
0x14001dff8  mov     [rsp+68h+var_48], rdi
0x14001dffd  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e004  mov     rcx, rsi
0x14001e007  call    WPP_SF_qZd
0x14001e00c  mov     rcx, [rsp+68h+Src]
0x14001e014  lea     rdx, WPP_GLOBAL_Control
0x14001e01b  mov     rsi, cs:WPP_GLOBAL_Control
0x14001e022  cmp     rsi, rdx
0x14001e025  jz      loc_14001E0BE
0x14001e02b  test    dword ptr [rsi+2Ch], 4000h
0x14001e032  jz      short loc_14001E072
0x14001e034  mov     rdi, [rcx+58h]
0x14001e038  mov     rsi, [rsi+18h]
0x14001e03c  movzx   ebx, word ptr [rdi]
0x14001e03f  call    cs:__imp_PsGetCurrentThreadId
0x14001e046  nop     dword ptr [rax+rax+00h]
0x14001e04b  mov     edx, 1Eh
0x14001e050  mov     dword ptr [rsp+68h+var_40], ebx
0x14001e054  mov     r9, rax
0x14001e057  mov     [rsp+68h+var_48], rdi
0x14001e05c  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e063  mov     rcx, rsi
0x14001e066  call    WPP_SF_qZd
0x14001e06b  lea     rdx, WPP_GLOBAL_Control
0x14001e072  mov     rsi, cs:WPP_GLOBAL_Control
0x14001e079  cmp     rsi, rdx
0x14001e07c  jz      short loc_14001E0BE
0x14001e07e  test    dword ptr [rsi+2Ch], 4000h
0x14001e085  jz      short loc_14001E0BE
0x14001e087  mov     rdi, [r15+50h]
0x14001e08b  mov     rsi, [rsi+18h]
0x14001e08f  movzx   ebx, word ptr [rdi]
0x14001e092  call    cs:__imp_PsGetCurrentThreadId
0x14001e099  nop     dword ptr [rax+rax+00h]
0x14001e09e  mov     edx, 1Fh
0x14001e0a3  mov     dword ptr [rsp+68h+var_40], ebx
0x14001e0a7  mov     r9, rax
0x14001e0aa  mov     [rsp+68h+var_48], rdi
0x14001e0af  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e0b6  mov     rcx, rsi
0x14001e0b9  call    WPP_SF_qZd
0x14001e0be  cmp     qword ptr [r12], 0
0x14001e0c3  jz      short loc_14001E0D5
0x14001e0c5  mov     dword ptr [r14+278h], 1
0x14001e0d0  jmp     loc_14001E597
0x14001e0d5  xor     r12d, r12d
0x14001e0d8  mov     [r14+278h], r12d
0x14001e0df  mov     rax, [r15+28h]
0x14001e0e3  mov     rcx, [rax+20h]
0x14001e0e7  mov     rbx, [rcx+20h]
0x14001e0eb  test    rbx, rbx
0x14001e0ee  jz      short loc_14001E0F4
0x14001e0f0  mov     r12, [rbx+20h]
0x14001e0f4  mov     rax, [rbx+40h]
0x14001e0f8  mov     rcx, [rsp+68h+arg_0]
0x14001e0fd  movzx   esi, word ptr [rax]
0x14001e100  add     rsi, 2
0x14001e104  mov     rdx, rsi
0x14001e107  call    UMRxAllocateSecondaryBuffer
0x14001e10c  mov     rdi, rax
0x14001e10f  test    rax, rax
0x14001e112  jnz     short loc_14001E171
0x14001e114  mov     edi, 0C000009Ah
0x14001e119  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e120  lea     rsi, WPP_GLOBAL_Control
0x14001e127  cmp     rbx, rsi
0x14001e12a  jz      loc_14001E67E
0x14001e130  test    dword ptr [rbx+2Ch], 2000h
0x14001e137  jz      loc_14001E63E
0x14001e13d  mov     rbx, [rbx+18h]
0x14001e141  call    cs:__imp_PsGetCurrentThreadId
0x14001e148  nop     dword ptr [rax+rax+00h]
0x14001e14d  mov     edx, 20h ; ' '
0x14001e152  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x14001e15a  mov     r9, rax
0x14001e15d  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e164  mov     rcx, rbx
0x14001e167  call    WPP_SF_qD
0x14001e16c  jmp     loc_14001E63E
0x14001e171  mov     rdx, [rbx+40h]
0x14001e175  mov     rcx, rdi; void *
0x14001e178  movzx   r8d, word ptr [rdx]; Size
0x14001e17c  mov     rdx, [rdx+8]; Src
0x14001e180  call    memmove
0x14001e185  shr     rsi, 1
0x14001e188  xor     eax, eax
0x14001e18a  mov     [rdi+rsi*2-2], ax
0x14001e18f  mov     [r14+288h], rdi
0x14001e196  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e19d  lea     rsi, WPP_GLOBAL_Control
0x14001e1a4  cmp     rbx, rsi
0x14001e1a7  jz      short loc_14001E1DE
0x14001e1a9  test    dword ptr [rbx+2Ch], 4000h
0x14001e1b0  jz      short loc_14001E1DE
0x14001e1b2  mov     rbx, [rbx+18h]
0x14001e1b6  call    cs:__imp_PsGetCurrentThreadId
0x14001e1bd  nop     dword ptr [rax+rax+00h]
0x14001e1c2  mov     edx, 21h ; '!'
0x14001e1c7  mov     [rsp+68h+var_48], rdi
0x14001e1cc  mov     r9, rax
0x14001e1cf  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e1d6  mov     rcx, rbx
0x14001e1d9  call    WPP_SF_qS
0x14001e1de  mov     eax, [r12]
0x14001e1e2  mov     edi, 5Ch ; '\'
0x14001e1e7  mov     [r14+290h], eax
0x14001e1ee  mov     edx, edi; Ch
0x14001e1f0  mov     rax, [rsp+68h+Src]
0x14001e1f8  mov     r8, [rax+58h]
0x14001e1fc  mov     rax, [rax+20h]
0x14001e200  movzx   ebx, word ptr [r8]
0x14001e204  mov     rcx, [rax+40h]
0x14001e208  movzx   eax, word ptr [rcx]
0x14001e20b  mov     rcx, [r8+8]
0x14001e20f  sub     ebx, eax
0x14001e211  add     rcx, 2; Str
0x14001e215  call    cs:__imp_wcschr
0x14001e21c  nop     dword ptr [rax+rax+00h]
0x14001e221  mov     rdx, [rsp+68h+arg_8]
0x14001e226  xor     r9d, r9d
0x14001e229  mov     [rsp+68h+Src], rax
0x14001e231  movzx   ecx, byte ptr [rdx+208h]
0x14001e238  mov     [r14+27Ch], ecx
0x14001e23f  mov     r12, [r15+50h]
0x14001e243  movzx   ecx, word ptr [r12]
0x14001e248  cmp     [rdx+208h], r9b
0x14001e24f  jz      loc_14001E33F
0x14001e255  lea     edx, [rbx+2]
0x14001e258  test    cx, cx
0x14001e25b  jz      short loc_14001E262
0x14001e25d  add     edx, 2
0x14001e260  add     edx, ecx
0x14001e262  mov     rcx, [rsp+68h+arg_0]
0x14001e267  mov     esi, edx
0x14001e269  call    UMRxAllocateSecondaryBuffer
0x14001e26e  xor     ebp, ebp
0x14001e270  mov     rdi, rax
0x14001e273  test    rax, rax
0x14001e276  jnz     short loc_14001E2D3
0x14001e278  mov     edi, 0C000009Ah
0x14001e27d  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e284  lea     rax, WPP_GLOBAL_Control
0x14001e28b  cmp     rbx, rax
0x14001e28e  jz      loc_14001E67E
0x14001e294  test    dword ptr [rbx+2Ch], 2000h
0x14001e29b  jz      loc_14001E637
0x14001e2a1  mov     rbx, [rbx+18h]
0x14001e2a5  call    cs:__imp_PsGetCurrentThreadId
0x14001e2ac  nop     dword ptr [rax+rax+00h]
0x14001e2b1  lea     edx, [rbp+22h]
0x14001e2b4  mov     r9, rax
0x14001e2b7  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x14001e2bf  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e2c6  mov     rcx, rbx
0x14001e2c9  call    WPP_SF_qD
0x14001e2ce  jmp     loc_14001E637
0x14001e2d3  mov     r8, rsi; Size
0x14001e2d6  mov     [r14+298h], rdi
0x14001e2dd  xor     edx, edx; Val
0x14001e2df  mov     rcx, rdi; void *
0x14001e2e2  call    memset
0x14001e2e7  mov     rdx, [rsp+68h+Src]; Src
0x14001e2ef  mov     r8, rbx; Size
0x14001e2f2  mov     rcx, rdi; void *
0x14001e2f5  call    memmove
0x14001e2fa  mov     rdx, [r15+50h]
0x14001e2fe  movzx   eax, word ptr [rdx]
0x14001e301  test    ax, ax
0x14001e304  jz      loc_14001E478
0x14001e30a  mov     rdx, [rdx+8]
0x14001e30e  lea     rcx, [rbx+rdi]
0x14001e312  mov     r12d, 5Ch ; '\'
0x14001e318  cmp     [rdx], r12w
0x14001e31c  jz      short loc_14001E337
0x14001e31e  mov     [rcx], r12w
0x14001e322  add     rcx, 2
0x14001e326  mov     rdx, [r15+50h]
0x14001e32a  movzx   r8d, word ptr [rdx]
0x14001e32e  mov     rdx, [rdx+8]
0x14001e332  jmp     loc_14001E473
0x14001e337  mov     r8, rax
0x14001e33a  jmp     loc_14001E473
0x14001e33f  mov     rdx, rcx
0x14001e342  test    ecx, ecx
0x14001e344  mov     ecx, r9d
0x14001e347  jz      short loc_14001E35F
0x14001e349  mov     r12, [r12+8]
0x14001e34e  mov     rax, rdx
0x14001e351  shr     rax, 1
0x14001e354  cmp     [r12+rax*2-2], di
0x14001e35a  setz    cl
0x14001e35d  jmp     short loc_14001E362
0x14001e35f  mov     r12, r9
0x14001e362  movzx   r8d, word ptr [rbp+50h]
0x14001e367  mov     dword ptr [rsp+68h+arg_8], ecx
0x14001e36b  test    ecx, ecx
0x14001e36d  jz      short loc_14001E379
0x14001e36f  lea     ecx, [rbx+4]
0x14001e372  add     ecx, edx
0x14001e374  add     ecx, r8d
0x14001e377  jmp     short loc_14001E389
0x14001e379  lea     ecx, [r8+4]
0x14001e37d  add     ecx, ebx
0x14001e37f  test    r12, r12
0x14001e382  jz      short loc_14001E389
0x14001e384  add     ecx, 2
0x14001e387  add     ecx, edx
0x14001e389  mov     esi, ecx
0x14001e38b  mov     edx, ecx
0x14001e38d  mov     rcx, [rsp+68h+arg_0]
0x14001e392  call    UMRxAllocateSecondaryBuffer
0x14001e397  mov     rdi, rax
0x14001e39a  test    rax, rax
0x14001e39d  jnz     short loc_14001E3E2
0x14001e39f  mov     edi, 0C000009Ah
0x14001e3a4  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e3ab  lea     rax, WPP_GLOBAL_Control
0x14001e3b2  cmp     rbx, rax
0x14001e3b5  jz      loc_14001E67E
0x14001e3bb  test    dword ptr [rbx+2Ch], 2000h
0x14001e3c2  jz      loc_14001E637
0x14001e3c8  mov     rbx, [rbx+18h]
0x14001e3cc  call    cs:__imp_PsGetCurrentThreadId
0x14001e3d3  nop     dword ptr [rax+rax+00h]
0x14001e3d8  mov     edx, 23h ; '#'
0x14001e3dd  jmp     loc_14001E2B4
0x14001e3e2  mov     r8, rsi; Size
0x14001e3e5  mov     [r14+298h], rdi
  ... truncated ...
```
