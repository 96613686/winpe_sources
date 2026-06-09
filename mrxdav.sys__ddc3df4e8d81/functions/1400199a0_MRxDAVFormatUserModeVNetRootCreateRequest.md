# MRxDAVFormatUserModeVNetRootCreateRequest

- ea: `0x1400199a0`
- end: `0x14001a47a`
- name: `MRxDAVFormatUserModeVNetRootCreateRequest`
- size: `2778`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x1400019bc`
- `0x140001b64`
- `0x140003310`
- `0x140006900`
- `0x14000f008`
- `0x14000f0cc`
- `0x1400199a0`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400199e2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019a2d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019a94`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019b1c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019b5f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019bd0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019c43`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019cc2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019e15`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019e6d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019ec8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a077`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a0c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a0f3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a15a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a1ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a234`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a2d1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a32a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a38a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a3f2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a448`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400199e2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019a2d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019a94`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019b1c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019b5f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019bd0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019c43`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019cc2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019e15`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019e6d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019ec8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a077`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a0c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a0f3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a15a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a1ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a234`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a2d1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a32a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a38a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a3f2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a448`
- `rdbss!RxFindEa` at `0x14001a00d`
- `rdbss!RxFindEa` at `0x14001a126`
- `rdbss!RxFindEa` at `0x14001a18d`
- `rdbss!RxFindEa` at `0x14001a267`
- `rdbss!RxFindEa` at `0x14001a00d`
- `rdbss!RxFindEa` at `0x14001a126`
- `rdbss!RxFindEa` at `0x14001a18d`
- `rdbss!RxFindEa` at `0x14001a267`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeVNetRootCreateRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rbx
  HANDLE v12; // rax
  PSECURITY_CLIENT_CONTEXT v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  __int64 v16; // rdi
  HANDLE v17; // rax
  int v18; // ebx
  __int64 v19; // rdi
  HANDLE v20; // rax
  ULONG_PTR v21; // rbx
  char *SecondaryBuffer; // rdi
  int v23; // esi
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rbx
  unsigned int v28; // eax
  int HighPart_low; // eax
  PVOID v30; // rax
  __int64 v31; // rbx
  HANDLE v32; // rax
  unsigned int v33; // ebx
  __int64 v34; // rdx
  unsigned int v35; // ecx
  unsigned __int16 *v36; // r9
  unsigned int v37; // edx
  unsigned int v38; // r10d
  void *v39; // rbx
  __int64 v40; // r9
  unsigned int v41; // edx
  unsigned int i; // r8d
  unsigned __int64 v43; // rdi
  PVOID v44; // rax
  __int64 v45; // rsi
  __int64 v46; // rbx
  unsigned int v47; // eax
  __int64 v48; // rbx
  HANDLE v49; // rax
  unsigned int v50; // r8d
  unsigned __int16 *v51; // rdx
  __int64 v52; // rcx
  const void **v53; // rdx
  unsigned __int64 v54; // rax
  unsigned __int16 *v55; // rdx
  __int64 v56; // rdx
  __int64 Ea; // rax
  __int64 v58; // rbx
  unsigned int v59; // eax
  PVOID v60; // rax
  __int64 v61; // rbx
  HANDLE v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rbx
  HANDLE v65; // rax
  __int64 v66; // rax
  __int64 v67; // rbx
  unsigned int v68; // eax
  PVOID v69; // rax
  __int64 v70; // rbx
  HANDLE v71; // rax
  __int64 v72; // rax
  __int64 v73; // rbx
  unsigned int v74; // eax
  PVOID v75; // rax
  int v76; // ebx
  __int64 v77; // rdi
  HANDLE v78; // rax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v82; // [rsp+30h] [rbp-68h]
  _DWORD *v84; // [rsp+40h] [rbp-58h]
  __int64 v85; // [rsp+48h] [rbp-50h]
  _QWORD *v86; // [rsp+50h] [rbp-48h]
  __int64 v87; // [rsp+58h] [rbp-40h]
  __int64 v89; // [rsp+A8h] [rbp+10h]
  PSECURITY_CLIENT_CONTEXT ClientContext; // [rsp+B0h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v6, 31, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v9 = PsGetCurrentThreadId();
    WPP_SF_qqq(v8, 32, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v9, a1, a2);
  }
  *(_DWORD *)(a3 + 48) = 1;
  v10 = *(_QWORD **)(a2 + 216);
  v87 = *(_QWORD *)(a2 + 232);
  v86 = (_QWORD *)v10[13];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qq(v11, 33, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v12, v10);
  }
  v13 = (PSECURITY_CLIENT_CONTEXT)v10[5];
  ClientContext = v13;
  v85 = v10[4];
  v14 = *(_QWORD *)(v85 + 32);
  v89 = v14;
  if ( v14 )
    v84 = *(_DWORD **)(v14 + 32);
  else
    v84 = 0;
  *(_DWORD *)(a3 + 648) = *(_DWORD *)&v13[1].SecurityQos.ContextTrackingMode;
  *(_DWORD *)(a3 + 652) = *((_DWORD *)&v13[1].SecurityQos + 3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v15 = *(_DWORD *)&v13[1].SecurityQos.ContextTrackingMode;
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v17 = PsGetCurrentThreadId();
    WPP_SF_qD(v16, 34, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v17, v15);
    v13 = ClientContext;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v18 = *((_DWORD *)&v13[1].SecurityQos + 3);
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v20 = PsGetCurrentThreadId();
    WPP_SF_qD(v19, 35, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v20, v18);
  }
  v21 = **(unsigned __int16 **)(v89 + 64) + 2LL;
  SecondaryBuffer = (char *)UMRxAllocateSecondaryBuffer(a1, v21);
  if ( !SecondaryBuffer )
  {
    v23 = -1073741670;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      v26 = 36;
LABEL_23:
      WPP_SF_qD(v24, v26, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v25, -1073741670);
      goto LABEL_108;
    }
    goto LABEL_108;
  }
  RtlCopyToUser(SecondaryBuffer, *(void **)(*(_QWORD *)(v89 + 64) + 8LL), **(unsigned __int16 **)(v89 + 64));
  RtlWriteUShortToUser(&SecondaryBuffer[2 * (v21 >> 1) - 2], 0);
  *(_QWORD *)(a3 + 632) = SecondaryBuffer;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v28 = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qS(v27, 37, (unsigned int)WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v28, (__int64)SecondaryBuffer);
  }
  HighPart_low = LOWORD(ClientContext[1].ClientTokenControl.AuthenticationId.HighPart);
  if ( (_WORD)HighPart_low )
  {
    LODWORD(v82) = HighPart_low + 2;
    v30 = UMRxAllocateSecondaryBuffer(a1, (unsigned int)(HighPart_low + 2));
    *(_QWORD *)(a3 + 664) = v30;
    if ( !v30 )
    {
      v23 = -1073741670;
      HIDWORD(v82) = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v31 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v32 = PsGetCurrentThreadId();
        WPP_SF_qD(v31, 38, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v32, -1073741670);
      }
      goto LABEL_108;
    }
    v33 = 0;
    LODWORD(v82) = 0;
    while ( v33 < LOWORD(ClientContext[1].ClientTokenControl.AuthenticationId.HighPart) >> 1 )
    {
      v34 = *(unsigned __int16 *)(*(_QWORD *)&ClientContext[1].ClientTokenControl.ModifiedId.HighPart + 2LL * v33);
      if ( (_WORD)v34 == 92 )
        v34 = 47;
      RtlWriteUShortToUser(*(_QWORD *)(a3 + 664) + 2LL * v33++, v34);
      LODWORD(v82) = v33;
    }
    RtlWriteUShortToUser(*(_QWORD *)(a3 + 664) + 2LL * v33, 0);
  }
  else
  {
    *(_QWORD *)(a3 + 664) = 0;
  }
  *(_DWORD *)(a3 + 656) = *v84;
  v35 = **(unsigned __int16 **)(v89 + 64);
  v36 = *(unsigned __int16 **)(v85 + 88);
  v37 = *v36;
  if ( v37 < v35 || (v38 = v37 - v35 + 2, v38 < v37 - v35) )
  {
    v23 = -1073741675;
    goto LABEL_108;
  }
  v39 = 0;
  v40 = *((_QWORD *)v36 + 1) + 2LL;
  v41 = (v37 >> 1) - 1;
  for ( i = 0; i < v41; ++i )
  {
    if ( *(_WORD *)(v40 + 2LL * i) == 92 )
      v39 = (void *)(v40 + 2LL * i);
  }
  if ( !v39 )
  {
    v23 = -1073741634;
    goto LABEL_108;
  }
  v43 = v38;
  v44 = UMRxAllocateSecondaryBuffer(a1, v38);
  v45 = (__int64)v44;
  if ( !v44 )
  {
    v23 = -1073741670;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      v26 = 40;
      goto LABEL_23;
    }
    goto LABEL_108;
  }
  RtlCopyToUser(v44, v39, v43 - 2);
  RtlWriteUShortToUser(v45 + 2 * ((v43 >> 1) - 1), 0);
  *(_QWORD *)(a3 + 640) = v45;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v46 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v47 = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qS(v46, 42, (unsigned int)WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v47, v45);
  }
  v23 = UMRxImpersonateClient(ClientContext);
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v48 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v49 = PsGetCurrentThreadId();
      WPP_SF_qD(v48, 43, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v49, v23);
    }
    goto LABEL_108;
  }
  if ( v86 )
  {
    v50 = 0;
    v51 = (unsigned __int16 *)v86[4];
    if ( v51 && *v51 && (*v51 & 0xFFFEu) < 0x400 )
    {
      memmove((void *)(a3 + 5536), *((const void **)v51 + 1), *v51);
      v52 = *(unsigned __int16 *)v86[4] >> 1;
      *(_WORD *)(a3 + 2 * v52 + 5536) = 92;
      v50 = v52 + 1;
    }
    v53 = (const void **)v86[2];
    if ( v53 )
    {
      v54 = *(unsigned __int16 *)v53;
      if ( (_WORD)v54 )
      {
        if ( v50 + (v54 >> 1) < 0x201 )
          memmove((void *)(a3 + 2 * (v50 + 2768LL)), v53[1], *(unsigned __int16 *)v53);
      }
    }
    v55 = (unsigned __int16 *)v86[3];
    if ( v55 && *v55 && (*v55 & 0xFFFEu) < 0x200 )
      memmove((void *)(a3 + 6562), *((const void **)v55 + 1), *v55);
  }
  *(_QWORD *)(a3 + 7080) = 0;
  *(_QWORD *)(a3 + 7088) = 0;
  *(_QWORD *)(a3 + 7104) = 0;
  *(_DWORD *)(a3 + 7112) = 0;
  *(_QWORD *)(a3 + 9168) = 0;
  v56 = *(unsigned int *)(v87 + 72);
  if ( (_DWORD)v56 )
  {
    Ea = RxFindEa(*(_QWORD *)(v87 + 64), v56, "Client-Cert", 11);
    v58 = Ea;
    if ( Ea )
    {
      *(_DWORD *)(a3 + 7088) = *(unsigned __int16 *)(Ea + 6);
      v59 = *(unsigned __int16 *)(Ea + 6);
      if ( (_WORD)v59 )
      {
        v60 = UMRxAllocateSecondaryBuffer(a1, v59);
        if ( !v60 )
        {
          v23 = -1073741670;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v25 = PsGetCurrentThreadId();
            v26 = 45;
            goto LABEL_23;
          }
          goto LABEL_108;
        }
        *(_QWORD *)(a3 + 7080) = v60;
        memmove(v60, (const void *)(v58 + 9 + *(unsigned __int8 *)(v58 + 5)), *(unsigned __int16 *)(v58 + 6));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v61 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v62 = PsGetCurrentThreadId();
          v63 = 46;
LABEL_90:
          WPP_SF_q(v61, v63, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v62);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v64 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v65 = PsGetCurrentThreadId();
        WPP_SF_q(v64, 47, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v65);
      }
      if ( RxFindEa(*(_QWORD *)(v87 + 64), *(unsigned int *)(v87 + 72), "NoClient-Cert", 15) )
      {
        *(_DWORD *)(a3 + 7092) = 1;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v61 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v62 = PsGetCurrentThreadId();
        v63 = 48;
        goto LABEL_90;
      }
    }
    v66 = RxFindEa(*(_QWORD *)(v87 + 64), *(unsigned int *)(v87 + 72), "Pin", 3);
    v67 = v66;
    if ( v66 )
    {
      v68 = *(unsigned __int16 *)(v66 + 6);
      if ( (_WORD)v68 )
      {
        v69 = UMRxAllocateSecondaryBuffer(a1, v68);
        if ( !v69 )
        {
          v23 = -1073741670;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v25 = PsGetCurrentThreadId();
            v26 = 49;
            goto LABEL_23;
          }
          goto LABEL_108;
        }
        *(_QWORD *)(a3 + 9168) = v69;
        memmove(v69, (const void *)(v67 + 9 + *(unsigned __int8 *)(v67 + 5)), *(unsigned __int16 *)(v67 + 6));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v70 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v71 = PsGetCurrentThreadId();
          WPP_SF_q(v70, 50, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v71);
        }
      }
    }
    v72 = RxFindEa(*(_QWORD *)(v87 + 64), *(unsigned int *)(v87 + 72), "Cookie:", 7);
    v73 = v72;
    if ( v72 )
    {
      *(_DWORD *)(a3 + 7112) = *(unsigned __int16 *)(v72 + 6);
      v74 = *(unsigned __int16 *)(v72 + 6);
      if ( (_WORD)v74 )
      {
        v75 = UMRxAllocateSecondaryBuffer(a1, v74);
        if ( v75 )
        {
          *(_QWORD *)(a3 + 7104) = v75;
          RtlCopyToUser(v75, (void *)(v73 + *(unsigned __int8 *)(v73 + 5) + 9LL), *(unsigned __int16 *)(v73 + 6));
          goto LABEL_108;
        }
        v23 = -1073741670;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v25 = PsGetCurrentThreadId();
          v26 = 51;
          goto LABEL_23;
        }
      }
    }
  }
LABEL_108:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v76 = *(_DWORD *)(a3 + 7088);
    v77 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v78 = PsGetCurrentThreadId();
    WPP_SF_qdL(v77, v79, v80, v78, v76, v23, v82, a3);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1400199a0  mov     [rsp+arg_0], rcx
0x1400199a5  push    rbx
0x1400199a6  push    rsi
0x1400199a7  push    rdi
0x1400199a8  push    r12
0x1400199aa  push    r13
0x1400199ac  push    r14
0x1400199ae  push    r15
0x1400199b0  sub     rsp, 60h
0x1400199b4  mov     r14, r8
0x1400199b7  mov     rsi, rdx
0x1400199ba  mov     rdi, rcx
0x1400199bd  mov     [rsp+98h+var_60], r8
0x1400199c2  lea     r15, WPP_GLOBAL_Control
0x1400199c9  mov     rbx, cs:WPP_GLOBAL_Control
0x1400199d0  cmp     rbx, r15
0x1400199d3  jz      short loc_140019A0A
0x1400199d5  test    dword ptr [rbx+2Ch], 4000h
0x1400199dc  jz      short loc_140019A0A
0x1400199de  mov     rbx, [rbx+18h]
0x1400199e2  call    cs:__imp_PsGetCurrentThreadId
0x1400199e9  nop     dword ptr [rax+rax+00h]
0x1400199ee  mov     r9, rax
0x1400199f1  mov     edx, 1Fh
0x1400199f6  lea     r13, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x1400199fd  mov     r8, r13
0x140019a00  mov     rcx, rbx
0x140019a03  call    WPP_SF_q
0x140019a08  jmp     short loc_140019A11
0x140019a0a  lea     r13, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140019a11  mov     rbx, cs:WPP_GLOBAL_Control
0x140019a18  mov     r12d, 2000h
0x140019a1e  cmp     rbx, r15
0x140019a21  jz      short loc_140019A56
0x140019a23  test    [rbx+2Ch], r12d
0x140019a27  jz      short loc_140019A56
0x140019a29  mov     rbx, [rbx+18h]
0x140019a2d  call    cs:__imp_PsGetCurrentThreadId
0x140019a34  nop     dword ptr [rax+rax+00h]
0x140019a39  mov     r9, rax
0x140019a3c  mov     edx, 20h ; ' '
0x140019a41  mov     [rsp+98h+var_70], rsi
0x140019a46  mov     [rsp+98h+var_78], rdi
0x140019a4b  mov     r8, r13
0x140019a4e  mov     rcx, rbx
0x140019a51  call    WPP_SF_qqq
0x140019a56  mov     dword ptr [r14+30h], 1
0x140019a5e  mov     rdi, [rsi+0D8h]
0x140019a65  mov     rax, [rsi+0E8h]
0x140019a6c  mov     [rsp+98h+var_40], rax
0x140019a71  mov     rax, [rdi+68h]
0x140019a75  mov     [rsp+98h+var_48], rax
0x140019a7a  mov     rbx, cs:WPP_GLOBAL_Control
0x140019a81  mov     esi, 4000h
0x140019a86  cmp     rbx, r15
0x140019a89  jz      short loc_140019AB8
0x140019a8b  test    [rbx+2Ch], esi
0x140019a8e  jz      short loc_140019AB8
0x140019a90  mov     rbx, [rbx+18h]
0x140019a94  call    cs:__imp_PsGetCurrentThreadId
0x140019a9b  nop     dword ptr [rax+rax+00h]
0x140019aa0  mov     r9, rax
0x140019aa3  mov     edx, 21h ; '!'
0x140019aa8  mov     [rsp+98h+var_78], rdi
0x140019aad  mov     r8, r13
0x140019ab0  mov     rcx, rbx
0x140019ab3  call    WPP_SF_qq
0x140019ab8  mov     rcx, [rdi+28h]
0x140019abc  mov     [rsp+98h+ClientContext], rcx
0x140019ac4  mov     rax, [rdi+20h]
0x140019ac8  mov     [rsp+98h+var_50], rax
0x140019acd  mov     rax, [rax+20h]
0x140019ad1  mov     [rsp+98h+arg_8], rax
0x140019ad9  xor     edx, edx
0x140019adb  test    rax, rax
0x140019ade  jnz     short loc_140019AE7
0x140019ae0  mov     [rsp+98h+var_58], rdx
0x140019ae5  jmp     short loc_140019AF0
0x140019ae7  mov     rax, [rax+20h]
0x140019aeb  mov     [rsp+98h+var_58], rax
0x140019af0  mov     eax, [rcx+50h]
0x140019af3  mov     [r14+288h], eax
0x140019afa  mov     eax, [rcx+54h]
0x140019afd  mov     [r14+28Ch], eax
0x140019b04  mov     rdi, cs:WPP_GLOBAL_Control
0x140019b0b  cmp     rdi, r15
0x140019b0e  jz      short loc_140019B47
0x140019b10  test    [rdi+2Ch], esi
0x140019b13  jz      short loc_140019B47
0x140019b15  mov     ebx, [rcx+50h]
0x140019b18  mov     rdi, [rdi+18h]
0x140019b1c  call    cs:__imp_PsGetCurrentThreadId
0x140019b23  nop     dword ptr [rax+rax+00h]
0x140019b28  mov     r9, rax
0x140019b2b  mov     edx, 22h ; '"'
0x140019b30  mov     dword ptr [rsp+98h+var_78], ebx
0x140019b34  mov     r8, r13
0x140019b37  mov     rcx, rdi
0x140019b3a  call    WPP_SF_qD
0x140019b3f  mov     rcx, [rsp+98h+ClientContext]
0x140019b47  mov     rdi, cs:WPP_GLOBAL_Control
0x140019b4e  cmp     rdi, r15
0x140019b51  jz      short loc_140019B82
0x140019b53  test    [rdi+2Ch], esi
0x140019b56  jz      short loc_140019B82
0x140019b58  mov     ebx, [rcx+54h]
0x140019b5b  mov     rdi, [rdi+18h]
0x140019b5f  call    cs:__imp_PsGetCurrentThreadId
0x140019b66  nop     dword ptr [rax+rax+00h]
0x140019b6b  mov     r9, rax
0x140019b6e  mov     edx, 23h ; '#'
0x140019b73  mov     dword ptr [rsp+98h+var_78], ebx
0x140019b77  mov     r8, r13
0x140019b7a  mov     rcx, rdi
0x140019b7d  call    WPP_SF_qD
0x140019b82  mov     rax, [rsp+98h+arg_8]
0x140019b8a  mov     rax, [rax+40h]
0x140019b8e  movzx   ebx, word ptr [rax]
0x140019b91  add     rbx, 2
0x140019b95  mov     rdx, rbx
0x140019b98  mov     rcx, [rsp+98h+arg_0]
0x140019ba0  call    UMRxAllocateSecondaryBuffer
0x140019ba5  mov     rdi, rax
0x140019ba8  test    rax, rax
0x140019bab  jnz     short loc_140019BFA
0x140019bad  mov     esi, 0C000009Ah
0x140019bb2  mov     rbx, cs:WPP_GLOBAL_Control
0x140019bb9  cmp     rbx, r15
0x140019bbc  jz      loc_14001A42B
0x140019bc2  test    [rbx+2Ch], r12d
0x140019bc6  jz      loc_14001A42B
0x140019bcc  mov     rbx, [rbx+18h]
0x140019bd0  call    cs:__imp_PsGetCurrentThreadId
0x140019bd7  nop     dword ptr [rax+rax+00h]
0x140019bdc  lea     edx, [rdi+24h]
0x140019bdf  mov     dword ptr [rsp+98h+var_78], 0C000009Ah
0x140019be7  mov     r9, rax
0x140019bea  mov     r8, r13
0x140019bed  mov     rcx, rbx
0x140019bf0  call    WPP_SF_qD
0x140019bf5  jmp     loc_14001A42B
0x140019bfa  mov     rax, [rsp+98h+arg_8]
0x140019c02  mov     rdx, [rax+40h]
0x140019c06  movzx   r8d, word ptr [rdx]; Size
0x140019c0a  mov     rdx, [rdx+8]; Src
0x140019c0e  mov     rcx, rdi; void *
0x140019c11  call    RtlCopyToUser
0x140019c16  xor     edx, edx
0x140019c18  shr     rbx, 1
0x140019c1b  dec     rbx
0x140019c1e  lea     rcx, [rdi+rbx*2]
0x140019c22  call    RtlWriteUShortToUser
0x140019c27  mov     [r14+278h], rdi
0x140019c2e  mov     rbx, cs:WPP_GLOBAL_Control
0x140019c35  cmp     rbx, r15
0x140019c38  jz      short loc_140019C67
0x140019c3a  test    [rbx+2Ch], esi
0x140019c3d  jz      short loc_140019C67
0x140019c3f  mov     rbx, [rbx+18h]
0x140019c43  call    cs:__imp_PsGetCurrentThreadId
0x140019c4a  nop     dword ptr [rax+rax+00h]
0x140019c4f  mov     r9, rax
0x140019c52  mov     edx, 25h ; '%'
0x140019c57  mov     [rsp+98h+var_78], rdi
0x140019c5c  mov     r8, r13
0x140019c5f  mov     rcx, rbx
0x140019c62  call    WPP_SF_qS
0x140019c67  mov     rdi, [rsp+98h+ClientContext]
0x140019c6f  movzx   eax, word ptr [rdi+70h]
0x140019c73  xor     r11d, r11d
0x140019c76  test    ax, ax
0x140019c79  jz      loc_140019D4E
0x140019c7f  add     eax, 2
0x140019c82  mov     [rsp+98h+var_68], eax
0x140019c86  mov     edx, eax
0x140019c88  mov     rcx, [rsp+98h+arg_0]
0x140019c90  call    UMRxAllocateSecondaryBuffer
0x140019c95  mov     [r14+298h], rax
0x140019c9c  xor     ecx, ecx
0x140019c9e  test    rax, rax
0x140019ca1  jnz     short loc_140019CEE
0x140019ca3  mov     esi, 0C000009Ah
0x140019ca8  mov     [rsp+98h+var_64], esi
0x140019cac  mov     rbx, cs:WPP_GLOBAL_Control
0x140019cb3  cmp     rbx, r15
0x140019cb6  jz      short loc_140019CE9
0x140019cb8  test    [rbx+2Ch], r12d
0x140019cbc  jz      short loc_140019CE9
0x140019cbe  mov     rbx, [rbx+18h]
0x140019cc2  call    cs:__imp_PsGetCurrentThreadId
0x140019cc9  nop     dword ptr [rax+rax+00h]
0x140019cce  mov     r9, rax
0x140019cd1  mov     edx, 26h ; '&'
0x140019cd6  mov     dword ptr [rsp+98h+var_78], 0C000009Ah
0x140019cde  mov     r8, r13
0x140019ce1  mov     rcx, rbx
0x140019ce4  call    WPP_SF_qD
0x140019ce9  jmp     loc_14001A42B
0x140019cee  mov     ebx, ecx
0x140019cf0  mov     [rsp+98h+var_68], ecx
0x140019cf4  mov     esi, 5Ch ; '\'
0x140019cf9  mov     r9d, 2Fh ; '/'
0x140019cff  mov     r8d, ebx
0x140019d02  movzx   eax, word ptr [rdi+70h]
0x140019d06  shr     eax, 1
0x140019d08  cmp     ebx, eax
0x140019d0a  jnb     short loc_140019D37
0x140019d0c  mov     ecx, ebx
0x140019d0e  mov     rax, [rdi+78h]
0x140019d12  movzx   edx, word ptr [rax+rcx*2]
0x140019d16  cmp     dx, si
0x140019d19  jnz     short loc_140019D1F
0x140019d1b  movzx   edx, r9w
0x140019d1f  mov     rax, [r14+298h]
0x140019d26  lea     rcx, [rax+r8*2]
0x140019d2a  call    RtlWriteUShortToUser
0x140019d2f  inc     ebx
0x140019d31  mov     [rsp+98h+var_68], ebx
0x140019d35  jmp     short loc_140019CF9
0x140019d37  xor     edx, edx
0x140019d39  mov     rax, [r14+298h]
0x140019d40  lea     rcx, [rax+r8*2]
0x140019d44  call    RtlWriteUShortToUser
0x140019d49  xor     r11d, r11d
0x140019d4c  jmp     short loc_140019D5A
0x140019d4e  mov     [r14+298h], r11
0x140019d55  mov     esi, 5Ch ; '\'
0x140019d5a  mov     rax, [rsp+98h+var_58]
0x140019d5f  mov     eax, [rax]
0x140019d61  mov     [r14+290h], eax
0x140019d68  mov     rax, [rsp+98h+arg_8]
0x140019d70  mov     rax, [rax+40h]
0x140019d74  movzx   ecx, word ptr [rax]
0x140019d77  mov     r9, [rsp+98h+var_50]
0x140019d7c  mov     r9, [r9+58h]
0x140019d80  movzx   edx, word ptr [r9]
0x140019d84  cmp     edx, ecx
0x140019d86  jb      loc_14001A3C5
0x140019d8c  mov     eax, edx
0x140019d8e  sub     eax, ecx
0x140019d90  lea     r10d, [rax+2]
0x140019d94  cmp     r10d, eax
0x140019d97  jb      loc_14001A3C5
0x140019d9d  mov     rbx, r11
0x140019da0  mov     r9, [r9+8]
0x140019da4  add     r9, 2
0x140019da8  shr     edx, 1
0x140019daa  sub     edx, 1
0x140019dad  mov     r8d, r11d
0x140019db0  jz      short loc_140019DC8
0x140019db2  mov     eax, r8d
0x140019db5  lea     rcx, [r9+rax*2]
0x140019db9  cmp     [rcx], si
0x140019dbc  cmovz   rbx, rcx
0x140019dc0  inc     r8d
0x140019dc3  cmp     r8d, edx
0x140019dc6  jb      short loc_140019DB2
0x140019dc8  test    rbx, rbx
0x140019dcb  jnz     short loc_140019DD7
0x140019dcd  mov     esi, 0C00000BEh
0x140019dd2  jmp     loc_14001A42B
0x140019dd7  mov     edi, r10d
0x140019dda  mov     edx, r10d
0x140019ddd  mov     rcx, [rsp+98h+arg_0]
0x140019de5  call    UMRxAllocateSecondaryBuffer
0x140019dea  mov     rsi, rax
0x140019ded  test    rax, rax
0x140019df0  jnz     short loc_140019E2B
0x140019df2  mov     esi, 0C000009Ah
0x140019df7  mov     rbx, cs:WPP_GLOBAL_Control
0x140019dfe  cmp     rbx, r15
0x140019e01  jz      loc_14001A42B
0x140019e07  test    [rbx+2Ch], r12d
0x140019e0b  jz      loc_14001A42B
0x140019e11  mov     rbx, [rbx+18h]
0x140019e15  call    cs:__imp_PsGetCurrentThreadId
0x140019e1c  nop     dword ptr [rax+rax+00h]
0x140019e21  mov     edx, 28h ; '('
0x140019e26  jmp     loc_140019BDF
0x140019e2b  lea     r8, [rdi-2]; Size
0x140019e2f  mov     rdx, rbx; Src
0x140019e32  mov     rcx, rsi; void *
0x140019e35  call    RtlCopyToUser
0x140019e3a  xor     edx, edx
0x140019e3c  shr     rdi, 1
0x140019e3f  lea     rcx, [rdi-1]
0x140019e43  lea     rcx, [rsi+rcx*2]
0x140019e47  call    RtlWriteUShortToUser
0x140019e4c  nop
0x140019e4d  mov     [r14+280h], rsi
0x140019e54  mov     rbx, cs:WPP_GLOBAL_Control
0x140019e5b  cmp     rbx, r15
0x140019e5e  jz      short loc_140019E91
0x140019e60  test    dword ptr [rbx+2Ch], 4000h
0x140019e67  jz      short loc_140019E91
0x140019e69  mov     rbx, [rbx+18h]
0x140019e6d  call    cs:__imp_PsGetCurrentThreadId
0x140019e74  nop     dword ptr [rax+rax+00h]
0x140019e79  mov     r9, rax
0x140019e7c  mov     edx, 2Ah ; '*'
  ... truncated ...
```
