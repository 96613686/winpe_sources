# MRxDAVFormatUserModeCreateRequest

- ea: `0x140014e00`
- end: `0x1400158f1`
- name: `MRxDAVFormatUserModeCreateRequest`
- size: `2801`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001044`
- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140001b64`
- `0x1400025cc`
- `0x140002ac4`
- `0x140006900`
- `0x14000f008`
- `0x14000f06c`
- `0x140014e00`
- `0x14002609c`
- `0x140027a20`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140014e81`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014ec9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014f71`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014fb8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001500a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400150e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001512e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015233`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400152b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015379`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400153b3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001545a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400154f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015583`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400155f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015641`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400156cd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015899`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014e81`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014ec9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014f71`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014fb8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001500a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400150e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001512e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015233`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400152b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015379`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400153b3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001545a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400154f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015583`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400155f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015641`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400156cd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015899`
- `ntoskrnl!ExAllocatePool2` at `0x140015548`
- `ntoskrnl!ExAllocatePool2` at `0x140015548`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015183`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015183`
- `rdbss!RxFindEa` at `0x140015320`
- `rdbss!RxFindEa` at `0x1400153e7`
- `rdbss!RxFindEa` at `0x140015418`
- `rdbss!RxFindEa` at `0x14001548e`
- `rdbss!RxFindEa` at `0x140015320`
- `rdbss!RxFindEa` at `0x1400153e7`
- `rdbss!RxFindEa` at `0x140015418`
- `rdbss!RxFindEa` at `0x14001548e`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeCreateRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // r14
  struct _SECURITY_CLIENT_CONTEXT *v6; // rdi
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  struct _SECURITY_CLIENT_CONTEXT *v13; // rax
  int v14; // ebx
  __int64 v15; // rdi
  HANDLE v16; // rax
  int v17; // ebx
  __int64 v18; // rdi
  HANDLE v19; // rax
  signed int v20; // edi
  __int64 v21; // rbx
  HANDLE v22; // rax
  char *v23; // r13
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned __int16 v26; // cx
  unsigned __int16 v27; // dx
  __int64 v28; // rbx
  char *SecondaryBuffer; // rax
  __int64 v30; // rbx
  HANDLE v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rbx
  HANDLE v34; // rax
  void *v35; // rcx
  __int64 v37; // rbx
  unsigned int v38; // eax
  unsigned int v39; // eax
  PVOID v40; // rcx
  int v41; // r8d
  __int64 v42; // rdx
  __int64 Ea; // rax
  __int64 v44; // rbx
  HANDLE v45; // rax
  __int64 v46; // rbx
  HANDLE v47; // rax
  __int64 v48; // rax
  __int64 v49; // rbx
  HANDLE v50; // rax
  __int64 v51; // rax
  __int64 v52; // rbx
  unsigned int v53; // eax
  PVOID v54; // rax
  void *Pool2; // rax
  __int64 v56; // rbx
  unsigned int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rbx
  HANDLE v60; // rax
  __int64 *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  int v65; // [rsp+40h] [rbp-78h]
  char *v66; // [rsp+48h] [rbp-70h]
  _QWORD *v67; // [rsp+50h] [rbp-68h]
  size_t Size; // [rsp+58h] [rbp-60h]
  __int64 v69; // [rsp+60h] [rbp-58h]
  void *Src; // [rsp+70h] [rbp-48h]
  void *v71; // [rsp+78h] [rbp-40h]
  struct _SECURITY_CLIENT_CONTEXT *ClientContext; // [rsp+D0h] [rbp+18h]
  unsigned __int16 ClientContexta; // [rsp+D0h] [rbp+18h]
  int ClientContextb; // [rsp+D0h] [rbp+18h]

  v67 = *(_QWORD **)(a2 + 72);
  v4 = v67[4];
  if ( v4 )
    v69 = *(_QWORD *)(v4 + 136);
  else
    v69 = 0;
  v5 = a3 + 632;
  v6 = 0;
  ClientContext = 0;
  v65 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v7, 15, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qqq(v9, 16, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v10, a1, a2);
  }
  v11 = *(_QWORD *)(a2 + 72);
  if ( v11 )
  {
    v12 = *(_QWORD *)(v11 + 40);
    if ( v12 )
    {
      v13 = *(struct _SECURITY_CLIENT_CONTEXT **)(v12 + 40);
      if ( v13 )
        v6 = v13;
      ClientContext = v6;
    }
  }
  *(_DWORD *)(v5 + 12) = *(_DWORD *)&v6[1].SecurityQos.ContextTrackingMode;
  *(_DWORD *)(v5 + 16) = *((_DWORD *)&v6[1].SecurityQos + 3);
  *(_QWORD *)(v5 + 24) = *(_QWORD *)(a1 + 104);
  *(_QWORD *)(v5 + 32) = *(_QWORD *)(a1 + 112);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v14 = *(_DWORD *)&v6[1].SecurityQos.ContextTrackingMode;
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v16 = PsGetCurrentThreadId();
    WPP_SF_qD(v15, 17, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v16, v14);
    v6 = ClientContext;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v17 = *((_DWORD *)&v6[1].SecurityQos + 3);
    v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v19 = PsGetCurrentThreadId();
    WPP_SF_qD(v18, 18, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v19, v17);
  }
  v20 = UMRxImpersonateClient(ClientContext);
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v22 = PsGetCurrentThreadId();
      WPP_SF_qD(v21, 19, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v22, v20);
    }
    goto LABEL_25;
  }
  v24 = *(_QWORD *)(*(_QWORD *)(v67[5] + 32LL) + 88LL);
  v25 = v67[10];
  v26 = *(_WORD *)v25 + *(_WORD *)v24;
  if ( v26 < *(_WORD *)v24 )
  {
    v20 = -1073741675;
  }
  else
  {
    if ( (unsigned __int16)(v26 + 2) < v26 )
      v27 = -1;
    else
      v27 = v26 + 2;
    ClientContexta = v27;
    v20 = (unsigned __int16)(v26 + 2) < v26 ? 0xC0000095 : 0;
    if ( (unsigned __int16)(v26 + 2) >= v26 )
    {
      Src = *(void **)(v24 + 8);
      v71 = *(void **)(v25 + 8);
      Size = v27;
      v28 = a1;
      SecondaryBuffer = (char *)UMRxAllocateSecondaryBuffer(a1, v27);
      v66 = SecondaryBuffer;
      if ( SecondaryBuffer )
      {
        RtlSetUserMemory(SecondaryBuffer);
        RtlCopyToUser(v66, Src, **(unsigned __int16 **)(*(_QWORD *)(v67[5] + 32LL) + 88LL));
        RtlCopyToUser(
          &v66[**(unsigned __int16 **)(*(_QWORD *)(v67[5] + 32LL) + 88LL)],
          v71,
          *(unsigned __int16 *)v67[10]);
        *(_QWORD *)v5 = v66;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v37 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v38 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qS(v37, 23, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v38, (__int64)v66);
          v28 = a1;
        }
        v39 = *(_DWORD *)(a2 + 712);
        *(_DWORD *)(v5 + 96) = v39;
        v40 = UMRxAllocateSecondaryBuffer(v28, v39);
        *(_QWORD *)(v5 + 88) = v40;
        if ( v40 )
        {
          memmove(v40, *(const void **)(a2 + 696), *(unsigned int *)(v5 + 96));
          *(_QWORD *)(a3 + 7080) = 0;
          *(_QWORD *)(a3 + 7088) = 0;
          *(_QWORD *)(a3 + 7104) = 0;
          *(_DWORD *)(a3 + 7112) = 0;
          *(_QWORD *)(a3 + 9168) = 0;
          v42 = *(unsigned int *)(v5 + 96);
          if ( (_DWORD)v42 )
          {
            Ea = RxFindEa(*(_QWORD *)(v5 + 88), v42, "Client-Cert", 11);
            if ( Ea )
            {
              *(_DWORD *)(a3 + 7088) = *(unsigned __int16 *)(Ea + 6);
              if ( *(_WORD *)(Ea + 6) )
              {
                *(_QWORD *)(a3 + 7080) = *(unsigned __int8 *)(Ea + 5) + Ea + 9;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
                {
                  v44 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                  v45 = PsGetCurrentThreadId();
                  WPP_SF_q(v44, 25, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v45);
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
              {
                v46 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v47 = PsGetCurrentThreadId();
                WPP_SF_q(v46, 26, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v47);
              }
              if ( RxFindEa(*(_QWORD *)(v5 + 88), *(unsigned int *)(v5 + 96), "NoClient-Cert", 15) )
                *(_DWORD *)(a3 + 7092) = 1;
            }
            v48 = RxFindEa(*(_QWORD *)(v5 + 88), *(unsigned int *)(v5 + 96), "Pin", 3);
            if ( v48 )
            {
              if ( *(_WORD *)(v48 + 6) )
              {
                *(_QWORD *)(a3 + 9168) = *(unsigned __int8 *)(v48 + 5) + v48 + 9;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
                {
                  v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                  v50 = PsGetCurrentThreadId();
                  WPP_SF_q(v49, 27, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v50);
                }
              }
            }
            v51 = RxFindEa(*(_QWORD *)(v5 + 88), *(unsigned int *)(v5 + 96), "Cookie:", 7);
            v52 = v51;
            if ( v51 )
            {
              *(_DWORD *)(a3 + 7112) = *(unsigned __int16 *)(v51 + 6);
              v53 = *(unsigned __int16 *)(v51 + 6);
              if ( (_WORD)v53 )
              {
                v54 = UMRxAllocateSecondaryBuffer(a1, v53);
                if ( !v54 )
                {
                  v20 = -1073741670;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
                  {
                    goto LABEL_36;
                  }
                  v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                  v31 = PsGetCurrentThreadId();
                  v32 = 28;
                  goto LABEL_35;
                }
                *(_QWORD *)(a3 + 7104) = v54;
                memmove(v54, (const void *)(v52 + *(unsigned __int8 *)(v52 + 5) + 9LL), *(unsigned __int16 *)(v52 + 6));
              }
            }
          }
          if ( *(_DWORD *)(v69 + 56) != 1 )
          {
            Pool2 = (void *)ExAllocatePool2(256, Size, 1766217284);
            *(_QWORD *)(v69 + 48) = Pool2;
            if ( !Pool2 )
            {
              v20 = -1073741670;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
              {
                goto LABEL_36;
              }
              v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v31 = PsGetCurrentThreadId();
              v32 = 29;
              goto LABEL_35;
            }
            v65 = 1;
            RtlCopyFromUser(Pool2, *(void **)v5, Size);
            *(_WORD *)(v69 + 40) = ClientContexta - 2;
            *(_WORD *)(v69 + 42) = ClientContexta;
            *(_DWORD *)(v69 + 56) = 1;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v56 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v57 = (unsigned int)PsGetCurrentThreadId();
              WPP_SF_qZ(v56, 31, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v57, v69 + 40);
            }
          }
          *(_DWORD *)(a3 + 48) = 0;
          v58 = a2;
          ClientContextb = **(_DWORD **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 72) + 40LL) + 32LL) + 32LL)
                                       + 32LL);
          *(_DWORD *)(v5 + 8) = ClientContextb;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v59 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v60 = PsGetCurrentThreadId();
            WPP_SF_qD(v59, 32, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v60, ClientContextb);
            v58 = a2;
          }
          *(_QWORD *)(v5 + 64) = *(_QWORD *)(v58 + 520);
          *(_DWORD *)(v5 + 72) = *(_DWORD *)(v58 + 528);
          *(_DWORD *)(v5 + 76) = *(_DWORD *)(v58 + 532);
          *(_DWORD *)(v5 + 80) = *(_DWORD *)(v58 + 536);
          *(_DWORD *)(v5 + 48) = *(_DWORD *)(v58 + 716);
          *(_DWORD *)(v5 + 52) = *(_DWORD *)(v58 + 552);
          *(_DWORD *)(v5 + 56) = 0;
          v61 = *(__int64 **)(v58 + 544);
          if ( v61 )
          {
            v62 = *v61;
            if ( v62 )
            {
              v41 = 0;
              if ( *(_BYTE *)(v62 + 8) == 1 )
              {
                *(_DWORD *)(v5 + 56) = 1;
                v41 = 1;
              }
              if ( *(_BYTE *)(**(_QWORD **)(v58 + 544) + 9LL) )
              {
                v41 |= 2u;
                *(_DWORD *)(v5 + 56) = v41;
              }
            }
          }
          *(_DWORD *)(v5 + 60) = *(_DWORD *)(v58 + 512);
          *(_DWORD *)(v5 + 84) = *(_DWORD *)(v58 + 540);
          if ( *(_BYTE *)(a1 + 210) )
          {
            *(_BYTE *)(v5 + 100) = 1;
            v63 = *(_QWORD *)(a1 + 752);
            *(_OWORD *)(a3 + 5472) = *(_OWORD *)v63;
            *(_OWORD *)(a3 + 5488) = *(_OWORD *)(v63 + 16);
            *(_QWORD *)(a3 + 5504) = *(_QWORD *)(v63 + 32);
            v64 = *(_QWORD *)(a1 + 752);
            *(_OWORD *)(a3 + 5512) = *(_OWORD *)(v64 + 40);
            *(_QWORD *)(a3 + 5528) = *(_QWORD *)(v64 + 56);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              WPP_SF_DDDDS(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v58,
                v41,
                *(_DWORD *)(a3 + 5504),
                *(_DWORD *)(a3 + 5476),
                *(_DWORD *)(a3 + 5472),
                *(_DWORD *)(a3 + 5520),
                *(_QWORD *)v5);
            }
          }
          *(_BYTE *)(v5 + 102) = *(_BYTE *)(a1 + 212);
          *(_BYTE *)(v5 + 103) = *(_BYTE *)(a1 + 213);
          if ( *(_BYTE *)(a1 + 211) )
            *(_BYTE *)(v5 + 101) = 1;
          goto LABEL_36;
        }
        v20 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          goto LABEL_36;
        }
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v31 = PsGetCurrentThreadId();
        v32 = 24;
      }
      else
      {
        v20 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          v23 = 0;
          goto LABEL_37;
        }
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v31 = PsGetCurrentThreadId();
        v32 = 21;
      }
LABEL_35:
      WPP_SF_qD(v30, v32, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v31, -1073741670);
LABEL_36:
      v23 = v66;
      goto LABEL_37;
    }
  }
LABEL_25:
  v23 = 0;
LABEL_37:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v34 = PsGetCurrentThreadId();
    WPP_SF_qD(v33, 34, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v34, v20);
  }
  if ( v20 )
  {
    if ( v23 )
    {
      UMRxFreeSecondaryBuffer(a1);
      *(_QWORD *)v5 = 0;
    }
    v35 = *(void **)(v69 + 48);
    if ( v35 && v65 )
    {
      ExFreePoolWithTag(v35, 0);
      *(_QWORD *)(v69 + 48) = 0;
      *(_DWORD *)(v69 + 40) = 0;
      *(_DWORD *)(v69 + 56) = 0;
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140014e00  mov     [rsp+arg_8], rdx
0x140014e05  mov     [rsp+arg_0], rcx
0x140014e0a  push    rbx
0x140014e0b  push    rsi
0x140014e0c  push    rdi
0x140014e0d  push    r12
0x140014e0f  push    r13
0x140014e11  push    r14
0x140014e13  push    r15
0x140014e15  sub     rsp, 80h
0x140014e1c  mov     r13, r8
0x140014e1f  mov     rax, [rdx+48h]
0x140014e23  mov     [rsp+0B8h+var_68], rax
0x140014e28  mov     rax, [rax+20h]
0x140014e2c  xor     esi, esi
0x140014e2e  test    rax, rax
0x140014e31  jnz     short loc_140014E3A
0x140014e33  mov     [rsp+0B8h+var_58], rsi
0x140014e38  jmp     short loc_140014E46
0x140014e3a  mov     rax, [rax+88h]
0x140014e41  mov     [rsp+0B8h+var_58], rax
0x140014e46  lea     r14, [r8+278h]
0x140014e4d  mov     [rsp+0B8h+var_50], r14
0x140014e52  mov     rdi, rsi
0x140014e55  mov     [rsp+0B8h+ClientContext], rsi
0x140014e5d  mov     [rsp+0B8h+var_78], esi
0x140014e61  lea     r15, WPP_GLOBAL_Control
0x140014e68  mov     rbx, cs:WPP_GLOBAL_Control
0x140014e6f  cmp     rbx, r15
0x140014e72  jz      short loc_140014EA9
0x140014e74  test    dword ptr [rbx+2Ch], 4000h
0x140014e7b  jz      short loc_140014EA9
0x140014e7d  mov     rbx, [rbx+18h]
0x140014e81  call    cs:__imp_PsGetCurrentThreadId
0x140014e88  nop     dword ptr [rax+rax+00h]
0x140014e8d  mov     r9, rax
0x140014e90  mov     edx, 0Fh
0x140014e95  lea     r12, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140014e9c  mov     r8, r12
0x140014e9f  mov     rcx, rbx
0x140014ea2  call    WPP_SF_q
0x140014ea7  jmp     short loc_140014EB0
0x140014ea9  lea     r12, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140014eb0  mov     rbx, cs:WPP_GLOBAL_Control
0x140014eb7  cmp     rbx, r15
0x140014eba  jz      short loc_140014F02
0x140014ebc  test    dword ptr [rbx+2Ch], 2000h
0x140014ec3  jz      short loc_140014F02
0x140014ec5  mov     rbx, [rbx+18h]
0x140014ec9  call    cs:__imp_PsGetCurrentThreadId
0x140014ed0  nop     dword ptr [rax+rax+00h]
0x140014ed5  mov     r9, rax
0x140014ed8  mov     edx, 10h
0x140014edd  mov     rax, [rsp+0B8h+arg_8]
0x140014ee5  mov     [rsp+0B8h+var_90], rax
0x140014eea  mov     rcx, [rsp+0B8h+arg_0]
0x140014ef2  mov     [rsp+0B8h+var_98], rcx
0x140014ef7  mov     r8, r12
0x140014efa  mov     rcx, rbx
0x140014efd  call    WPP_SF_qqq
0x140014f02  mov     rax, [rsp+0B8h+arg_8]
0x140014f0a  mov     rcx, [rax+48h]
0x140014f0e  test    rcx, rcx
0x140014f11  jz      short loc_140014F2F
0x140014f13  mov     rax, [rcx+28h]
0x140014f17  test    rax, rax
0x140014f1a  jz      short loc_140014F2F
0x140014f1c  mov     rax, [rax+28h]
0x140014f20  test    rax, rax
0x140014f23  cmovnz  rdi, rax
0x140014f27  mov     [rsp+0B8h+ClientContext], rdi
0x140014f2f  mov     eax, [rdi+50h]
0x140014f32  mov     [r14+0Ch], eax
0x140014f36  mov     eax, [rdi+54h]
0x140014f39  mov     [r14+10h], eax
0x140014f3d  mov     rcx, [rsp+0B8h+arg_0]
0x140014f45  mov     rax, [rcx+68h]
0x140014f49  mov     [r14+18h], rax
0x140014f4d  mov     rax, [rcx+70h]
0x140014f51  mov     [r14+20h], rax
0x140014f55  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f5c  cmp     rcx, r15
0x140014f5f  jz      short loc_140014F9C
0x140014f61  test    dword ptr [rcx+2Ch], 4000h
0x140014f68  jz      short loc_140014F9C
0x140014f6a  mov     ebx, [rdi+50h]
0x140014f6d  mov     rdi, [rcx+18h]
0x140014f71  call    cs:__imp_PsGetCurrentThreadId
0x140014f78  nop     dword ptr [rax+rax+00h]
0x140014f7d  mov     r9, rax
0x140014f80  mov     edx, 11h
0x140014f85  mov     dword ptr [rsp+0B8h+var_98], ebx
0x140014f89  mov     r8, r12
0x140014f8c  mov     rcx, rdi
0x140014f8f  call    WPP_SF_qD
0x140014f94  mov     rdi, [rsp+0B8h+ClientContext]
0x140014f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014fa3  cmp     rcx, r15
0x140014fa6  jz      short loc_140014FDB
0x140014fa8  test    dword ptr [rcx+2Ch], 4000h
0x140014faf  jz      short loc_140014FDB
0x140014fb1  mov     ebx, [rdi+54h]
0x140014fb4  mov     rdi, [rcx+18h]
0x140014fb8  call    cs:__imp_PsGetCurrentThreadId
0x140014fbf  nop     dword ptr [rax+rax+00h]
0x140014fc4  mov     r9, rax
0x140014fc7  mov     edx, 12h
0x140014fcc  mov     dword ptr [rsp+0B8h+var_98], ebx
0x140014fd0  mov     r8, r12
0x140014fd3  mov     rcx, rdi
0x140014fd6  call    WPP_SF_qD
0x140014fdb  mov     rdx, r13
0x140014fde  mov     rcx, [rsp+0B8h+ClientContext]; ClientContext
0x140014fe6  call    UMRxImpersonateClient
0x140014feb  mov     edi, eax
0x140014fed  test    eax, eax
0x140014fef  jns     short loc_140015035
0x140014ff1  mov     rbx, cs:WPP_GLOBAL_Control
0x140014ff8  cmp     rbx, r15
0x140014ffb  jz      short loc_14001502D
0x140014ffd  test    dword ptr [rbx+2Ch], 2000h
0x140015004  jz      short loc_14001502D
0x140015006  mov     rbx, [rbx+18h]
0x14001500a  call    cs:__imp_PsGetCurrentThreadId
0x140015011  nop     dword ptr [rax+rax+00h]
0x140015016  mov     r9, rax
0x140015019  mov     edx, 13h
0x14001501e  mov     dword ptr [rsp+0B8h+var_98], edi
0x140015022  mov     r8, r12
0x140015025  mov     rcx, rbx
0x140015028  call    WPP_SF_qD
0x14001502d  mov     r13, rsi
0x140015030  jmp     loc_140015115
0x140015035  mov     rdx, [rsp+0B8h+var_68]
0x14001503a  mov     rax, [rdx+28h]
0x14001503e  mov     rcx, [rax+20h]
0x140015042  mov     r8, [rcx+58h]
0x140015046  mov     r9, [rdx+50h]
0x14001504a  movzx   eax, word ptr [r8]
0x14001504e  movzx   ecx, ax
0x140015051  add     cx, [r9]
0x140015055  cmp     cx, ax
0x140015058  jb      loc_1400158DF
0x14001505e  mov     edx, 2
0x140015063  lea     eax, [rdx+rcx]
0x140015066  cmp     ax, cx
0x140015069  jb      short loc_140015070
0x14001506b  movzx   edx, ax
0x14001506e  jmp     short loc_140015075
0x140015070  mov     edx, 0FFFFh
0x140015075  mov     dword ptr [rsp+0B8h+ClientContext], edx
0x14001507c  sbb     edi, edi
0x14001507e  and     edi, 0C0000095h
0x140015084  cmp     ax, cx
0x140015087  jb      short loc_14001502D
0x140015089  mov     rax, [r8+8]
0x14001508d  mov     [rsp+0B8h+Src], rax
0x140015092  mov     rax, [r9+8]
0x140015096  mov     [rsp+0B8h+var_40], rax
0x14001509b  movzx   eax, dx
0x14001509e  mov     [rsp+0B8h+Size], rax
0x1400150a3  mov     edx, eax
0x1400150a5  mov     rbx, [rsp+0B8h+arg_0]
0x1400150ad  mov     rcx, rbx
0x1400150b0  call    UMRxAllocateSecondaryBuffer
0x1400150b5  mov     [rsp+0B8h+var_70], rax
0x1400150ba  test    rax, rax
0x1400150bd  jnz     loc_1400151B3
0x1400150c3  mov     edi, 0C000009Ah
0x1400150c8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400150cf  cmp     rbx, r15
0x1400150d2  jz      loc_1400158E9
0x1400150d8  test    dword ptr [rbx+2Ch], 2000h
0x1400150df  jz      loc_1400158E9
0x1400150e5  mov     rbx, [rbx+18h]
0x1400150e9  call    cs:__imp_PsGetCurrentThreadId
0x1400150f0  nop     dword ptr [rax+rax+00h]
0x1400150f5  mov     edx, 15h
0x1400150fa  mov     r9, rax
0x1400150fd  mov     dword ptr [rsp+0B8h+var_98], 0C000009Ah
0x140015105  mov     r8, r12
0x140015108  mov     rcx, rbx
0x14001510b  call    WPP_SF_qD
0x140015110  mov     r13, [rsp+0B8h+var_70]
0x140015115  mov     rbx, cs:WPP_GLOBAL_Control
0x14001511c  cmp     rbx, r15
0x14001511f  jz      short loc_140015151
0x140015121  test    dword ptr [rbx+2Ch], 4000h
0x140015128  jz      short loc_140015151
0x14001512a  mov     rbx, [rbx+18h]
0x14001512e  call    cs:__imp_PsGetCurrentThreadId
0x140015135  nop     dword ptr [rax+rax+00h]
0x14001513a  mov     r9, rax
0x14001513d  mov     edx, 22h ; '"'
0x140015142  mov     dword ptr [rsp+0B8h+var_98], edi
0x140015146  mov     r8, r12
0x140015149  mov     rcx, rbx
0x14001514c  call    WPP_SF_qD
0x140015151  test    edi, edi
0x140015153  jz      short loc_14001519D
0x140015155  test    r13, r13
0x140015158  jz      short loc_14001516D
0x14001515a  mov     rdx, r13
0x14001515d  mov     rcx, [rsp+0B8h+arg_0]
0x140015165  call    UMRxFreeSecondaryBuffer
0x14001516a  mov     [r14], rsi
0x14001516d  mov     rbx, [rsp+0B8h+var_58]
0x140015172  mov     rcx, [rbx+30h]; P
0x140015176  test    rcx, rcx
0x140015179  jz      short loc_14001519D
0x14001517b  cmp     [rsp+0B8h+var_78], esi
0x14001517f  jz      short loc_14001519D
0x140015181  xor     edx, edx; Tag
0x140015183  call    cs:__imp_ExFreePoolWithTag
0x14001518a  nop     dword ptr [rax+rax+00h]
0x14001518f  mov     [rbx+30h], rsi
0x140015193  mov     dword ptr [rbx+28h], 0
0x14001519a  mov     [rbx+38h], esi
0x14001519d  mov     eax, edi
0x14001519f  add     rsp, 80h
0x1400151a6  pop     r15
0x1400151a8  pop     r14
0x1400151aa  pop     r13
0x1400151ac  pop     r12
0x1400151ae  pop     rdi
0x1400151af  pop     rsi
0x1400151b0  pop     rbx
0x1400151b1  retn
0x1400151b3  mov     r8, [rsp+0B8h+Size]
0x1400151b8  xor     edx, edx
0x1400151ba  mov     rcx, rax; void *
0x1400151bd  call    RtlSetUserMemory
0x1400151c2  mov     rcx, [rsp+0B8h+var_68]
0x1400151c7  mov     rax, [rcx+28h]
0x1400151cb  mov     rcx, [rax+20h]
0x1400151cf  mov     rax, [rcx+58h]
0x1400151d3  movzx   r8d, word ptr [rax]; Size
0x1400151d7  mov     rdx, [rsp+0B8h+Src]; Src
0x1400151dc  mov     rcx, [rsp+0B8h+var_70]; void *
0x1400151e1  call    RtlCopyToUser
0x1400151e6  mov     rcx, [rsp+0B8h+var_68]
0x1400151eb  mov     rax, [rcx+50h]
0x1400151ef  movzx   r8d, word ptr [rax]; Size
0x1400151f3  mov     rax, [rcx+28h]
0x1400151f7  mov     rcx, [rax+20h]
0x1400151fb  mov     rax, [rcx+58h]
0x1400151ff  movzx   ecx, word ptr [rax]
0x140015202  add     rcx, [rsp+0B8h+var_70]; void *
0x140015207  mov     rdx, [rsp+0B8h+var_40]; Src
0x14001520c  call    RtlCopyToUser
0x140015211  nop
0x140015212  mov     rax, [rsp+0B8h+var_70]
0x140015217  mov     [r14], rax
0x14001521a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015221  cmp     rcx, r15
0x140015224  jz      short loc_140015264
0x140015226  test    dword ptr [rcx+2Ch], 4000h
0x14001522d  jz      short loc_140015264
0x14001522f  mov     rbx, [rcx+18h]
0x140015233  call    cs:__imp_PsGetCurrentThreadId
0x14001523a  nop     dword ptr [rax+rax+00h]
0x14001523f  mov     r9, rax
0x140015242  mov     edx, 17h
0x140015247  mov     rax, [rsp+0B8h+var_70]
0x14001524c  mov     [rsp+0B8h+var_98], rax
0x140015251  mov     r8, r12
0x140015254  mov     rcx, rbx
0x140015257  call    WPP_SF_qS
0x14001525c  mov     rbx, [rsp+0B8h+arg_0]
0x140015264  mov     rax, [rsp+0B8h+arg_8]
0x14001526c  mov     eax, [rax+2C8h]
0x140015272  mov     [r14+60h], eax
0x140015276  mov     edx, eax
0x140015278  mov     rcx, rbx
0x14001527b  call    UMRxAllocateSecondaryBuffer
0x140015280  mov     rcx, rax; void *
0x140015283  mov     [r14+58h], rax
0x140015287  test    rax, rax
0x14001528a  jnz     short loc_1400152C8
0x14001528c  mov     edi, 0C000009Ah
0x140015291  mov     rbx, cs:WPP_GLOBAL_Control
0x140015298  cmp     rbx, r15
0x14001529b  jz      loc_140015110
0x1400152a1  test    dword ptr [rbx+2Ch], 2000h
0x1400152a8  jz      loc_140015110
0x1400152ae  mov     rbx, [rbx+18h]
0x1400152b2  call    cs:__imp_PsGetCurrentThreadId
0x1400152b9  nop     dword ptr [rax+rax+00h]
0x1400152be  mov     edx, 18h
0x1400152c3  jmp     loc_1400150FA
0x1400152c8  mov     r8d, [r14+60h]; Size
0x1400152cc  mov     rax, [rsp+0B8h+arg_8]
0x1400152d4  mov     rdx, [rax+2B8h]; Src
0x1400152db  call    memmove
0x1400152e0  mov     [r13+1BA8h], rsi
0x1400152e7  mov     [r13+1BB0h], rsi
0x1400152ee  mov     [r13+1BC0h], rsi
0x1400152f5  mov     [r13+1BC8h], esi
0x1400152fc  mov     [r13+23D0h], rsi
0x140015303  mov     edx, [r14+60h]
  ... truncated ...
```
