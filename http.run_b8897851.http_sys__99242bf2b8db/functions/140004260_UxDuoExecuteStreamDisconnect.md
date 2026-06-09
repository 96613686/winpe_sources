# UxDuoExecuteStreamDisconnect

- ea: `0x140004260`
- end: `0x140004c31`
- name: `UxDuoExecuteStreamDisconnect`
- size: `2513`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400029a0`
- `0x140003ac0`
- `0x1400040d0`
- `0x140004260`
- `0x140005410`
- `0x140005d10`
- `0x1400068a8`
- `0x1400079b0`
- `0x14000a350`
- `0x140049d28`
- `0x14005dff0`
- `0x14006e50c`
- `0x1400d9280`
- `0x1400dc510`
- `0x1400dc72c`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3fb0`
- `0x1401c4510`
- `0x1401c4974`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004676`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004861`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004676`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140004861`
- `ntoskrnl!IoFreeMdl` at `0x140004733`
- `ntoskrnl!IoFreeMdl` at `0x140004733`
- `ntoskrnl!IofCompleteRequest` at `0x140004b94`
- `ntoskrnl!IofCompleteRequest` at `0x140004b94`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400048ff`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400048ff`
- `ntoskrnl!ExAllocatePool3` at `0x14000431d`
- `ntoskrnl!ExAllocatePool3` at `0x14000431d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000476c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000476c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a44`

## pseudocode

```c
void __fastcall UxDuoExecuteStreamDisconnect(char *Entry, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  ULONG_PTR v5; // rbx
  int v7; // r15d
  __int64 v8; // r13
  __int64 Pool3; // rax
  _QWORD *v10; // rcx
  __int128 v11; // xmm0
  int v12; // eax
  __int64 v13; // r13
  __int64 v14; // rax
  __int64 v15; // rdx
  bool v16; // zf
  int v17; // r9d
  int Parcel; // r14d
  int v19; // eax
  bool v20; // al
  int v21; // eax
  __int64 v22; // r10
  __int64 v23; // rax
  char v24; // r13
  void (__fastcall *v25)(_QWORD, _QWORD, _QWORD); // rax
  int v26; // eax
  __int64 v27; // rcx
  ULONG_PTR v28; // rdx
  int v29; // eax
  volatile signed __int32 *v30; // rcx
  int v31; // ebp
  unsigned __int64 v32; // rbx
  struct _MDL *v33; // rcx
  struct _MDL *Next; // rdi
  __int64 v35; // rcx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rcx
  int v38; // eax
  unsigned __int64 v39; // rdi
  __int64 v40; // rbx
  USHORT CurrentNodeNumber; // ax
  __int64 v42; // rcx
  void (__fastcall *v43)(_QWORD, __int64, __int64); // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rcx
  ULONG_PTR v47; // rdx
  int v48; // eax
  __int64 v49; // rcx
  int v50; // eax
  int StreamEndParcel; // eax
  IRP *v52; // rcx
  volatile signed __int32 *v53; // rcx
  __int64 v54; // [rsp+40h] [rbp-E8h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-E0h]
  __int64 v56; // [rsp+50h] [rbp-D8h]
  __int64 v57; // [rsp+58h] [rbp-D0h]
  __int64 v58; // [rsp+60h] [rbp-C8h]
  _DWORD v59[24]; // [rsp+70h] [rbp-B8h] BYREF

  v4 = *((_QWORD *)Entry + 6);
  v5 = 0;
  if ( *(_BYTE *)(v4 + 96) )
  {
    Parcel = -1073741436;
    goto LABEL_33;
  }
  v7 = *((_DWORD *)Entry + 35) & 2;
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_DDPd(
      Entry,
      a2,
      a3,
      *(unsigned int *)(*(_QWORD *)(v4 + 48) + 17232LL),
      *(_DWORD *)(v4 + 88),
      *((_QWORD *)Entry + 16),
      v7 != 0);
  if ( *(_BYTE *)(v4 + 404) )
  {
    if ( *((_QWORD *)Entry + 15)
      || *((_DWORD *)Entry + 34)
      || *((_QWORD *)Entry + 16)
      || (Parcel = 0, v24 = 1, *((_QWORD *)Entry + 14)) )
    {
      if ( (byte_1401A2C8B & 8) != 0 )
        WPP_SF_Dd(
          283,
          38,
          WPP_309922b680ce3405e88e422e035050e4_Traceguids,
          *(unsigned int *)(*(_QWORD *)(v4 + 48) + 17232LL),
          *(_DWORD *)(v4 + 88));
      Parcel = -1073741436;
      UxDuoSetFault(*(_QWORD *)(v4 + 48), v4, 14, 3221225860LL);
      goto LABEL_33;
    }
    goto LABEL_29;
  }
  *(_BYTE *)(v4 + 404) = 1;
  v8 = *((_QWORD *)Entry + 16);
  v55 = *((_DWORD *)Entry + 34);
  v58 = *((_QWORD *)Entry + 15);
  LODWORD(v54) = *((_DWORD *)Entry + 35);
  v57 = *((_QWORD *)Entry + 12);
  v56 = *((_QWORD *)Entry + 11);
  Pool3 = ExAllocatePool3(256, 136, 1129936981, UxLowPriorityPool, 1);
  v5 = Pool3;
  if ( !Pool3 )
  {
    Parcel = -1073741670;
    v5 = 0;
    UxDuoSetFault(*(_QWORD *)(v4 + 48), v4, 1000, 3221225626LL);
    v49 = *(_QWORD *)(v4 + 48);
    if ( !*(_DWORD *)(v49 + 17032) && !*(_DWORD *)(v4 + 232) )
      UxDuoSetFault(v49, 0, 1045, 3221225626LL);
    goto LABEL_33;
  }
  *(_DWORD *)Pool3 = 1;
  v10 = (_QWORD *)(Pool3 + 112);
  *(_QWORD *)(Pool3 + 16) = v56;
  *(_QWORD *)(Pool3 + 24) = v57;
  *(_DWORD *)(Pool3 + 128) = v54;
  *(_QWORD *)(Pool3 + 88) = v58;
  *(_DWORD *)(Pool3 + 104) = v55;
  *(_QWORD *)(Pool3 + 40) = v8;
  *(_BYTE *)(Pool3 + 80) = 1;
  *(_QWORD *)(Pool3 + 96) = v8;
  v11 = *(_OWORD *)(Entry + 72);
  *(_QWORD *)(Pool3 + 8) = v4;
  *(_OWORD *)(Pool3 + 112) = v11;
  v12 = _InterlockedIncrement((volatile signed __int32 *)(v4 + 20));
  if ( UxDebugCheckRefcount && v12 <= -1 )
    UlBugCheckEx(3u, v4 + 20, 0x2Bu, v12);
  v54 = 0;
  *(_OWORD *)(v5 + 48) = 0;
  *(_OWORD *)(v5 + 64) = 0;
  v13 = *((_QWORD *)Entry + 13);
  v14 = *((_QWORD *)Entry + 14);
  v15 = *((_QWORD *)Entry + 16);
  v56 = v14;
  v57 = v15;
  if ( v13 )
    goto LABEL_8;
  if ( v15 || v14 )
  {
    Parcel = 0;
    if ( !v15 )
    {
LABEL_26:
      if ( !v14 )
        goto LABEL_27;
      StreamEndParcel = UxDuoAllocateCatalogParcel(v10, v5, v14, &v54);
      goto LABEL_139;
    }
LABEL_8:
    v16 = *(_BYTE *)(v5 + 80) == 0;
    v55 = *((_DWORD *)Entry + 34);
    v58 = *((_QWORD *)Entry + 15);
    if ( v16 )
      v17 = *(_DWORD *)(v5 + 128);
    else
      v17 = 0;
    Parcel = UxDuoAllocateParcel(0, v4, *(_QWORD *)(v4 + 48), v17, v5 + 112, (__int64)&v54);
    if ( Parcel < 0 )
      goto LABEL_27;
    a3 = v54;
    *(_QWORD *)(v54 + 264) = v5;
    v19 = _InterlockedIncrement((volatile signed __int32 *)v5);
    if ( UxDebugCheckRefcount && v19 <= -1 )
      UlBugCheckEx(3u, v5, 0x24u, v19);
    *(_QWORD *)(a3 + 272) = v58;
    *(_QWORD *)(a3 + 288) = v55;
    *(_QWORD *)(a3 + 280) = v57;
    *(_QWORD *)(a3 + 240) = v13;
    v20 = *(_BYTE *)(v5 + 80) && !v56;
    *(_BYTE *)(a3 + 304) = v20;
    v21 = *(_DWORD *)(a3 + 232);
    v22 = *(_QWORD *)(a3 + 88);
    a4 = *(_QWORD *)(a3 + 80);
    *(_BYTE *)(a3 + 208) = 1;
    *(_DWORD *)(a3 + 180) = 1;
    if ( v21 == 10 )
    {
LABEL_16:
      v23 = a4 + 280;
      v10 = *(_QWORD **)(a4 + 288);
      if ( *v10 != a4 + 280 )
        goto LABEL_17;
    }
    else
    {
      if ( v21 != 9 )
      {
        switch ( v21 )
        {
          case 0:
          case 2:
            goto LABEL_16;
          case 1:
          case 3:
          case 4:
          case 5:
          case 6:
          case 7:
          case 8:
            break;
          default:
            goto LABEL_22;
        }
      }
      v23 = v22 + 16984;
      v10 = *(_QWORD **)(v22 + 16992);
      if ( *v10 != v22 + 16984 )
LABEL_17:
        __fastfail(3u);
    }
    *(_QWORD *)a3 = v23;
    *(_QWORD *)(a3 + 8) = v10;
    *v10 = a3;
    *(_QWORD *)(v23 + 8) = a3;
LABEL_22:
    if ( a4 )
    {
      if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_DDDL(
          1307,
          20,
          WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids,
          *(unsigned int *)(v22 + 17232),
          *(_DWORD *)(a4 + 88),
          *(_DWORD *)(a3 + 176),
          *(_DWORD *)(a3 + 232));
    }
    else if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
    {
      WPP_SF_LLL(
        1307,
        21,
        WPP_fc5e4f38a5b73b16c7731f2fb336856e_Traceguids,
        *(unsigned int *)(v22 + 17232),
        *(_DWORD *)(a3 + 176),
        *(_DWORD *)(a3 + 232));
    }
    v14 = v56;
    v54 = 0;
    goto LABEL_26;
  }
  StreamEndParcel = UxDuoAllocateStreamEndParcel(v5);
LABEL_139:
  Parcel = StreamEndParcel;
  if ( StreamEndParcel >= 0 )
  {
    UxDuoSubmitParcel(v54);
    v24 = 0;
    goto LABEL_28;
  }
LABEL_27:
  v24 = 0;
  if ( Parcel < 0 )
  {
    v42 = *(_QWORD *)(v4 + 48);
    if ( !*(_DWORD *)(v42 + 17032) && !*(_DWORD *)(v4 + 232) )
      UxDuoSetFault(v42, 0, 1045, (unsigned int)Parcel);
    goto LABEL_36;
  }
LABEL_28:
  Parcel = UxDuoDispatchConnectionSends(*(_QWORD *)(v4 + 48));
  if ( Parcel >= 0 )
  {
LABEL_29:
    if ( v7 && !*(_BYTE *)(v4 + 398) )
    {
      *(_BYTE *)(v4 + 398) = 1;
      Parcel = UxDuoRunStreamReceivePump(v4, a2, a3, a4);
    }
    if ( !v24 )
    {
LABEL_35:
      if ( !v5 )
        goto LABEL_41;
      goto LABEL_36;
    }
LABEL_33:
    v25 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))*((_QWORD *)Entry + 11);
    if ( v25 )
      v25(*((_QWORD *)Entry + 12), (unsigned int)Parcel, 0);
    goto LABEL_35;
  }
LABEL_36:
  if ( *(int *)(v5 + 32) >= 0 && Parcel < 0 )
    *(_DWORD *)(v5 + 32) = Parcel;
  v26 = _InterlockedDecrement((volatile signed __int32 *)v5);
  if ( UxDebugCheckRefcount && v26 <= -1 )
    UlBugCheckEx(3u, v5, 1u, v26);
  if ( !v26 )
  {
    v33 = *(struct _MDL **)(v5 + 48);
    if ( v33 )
    {
      do
      {
        Next = v33->Next;
        IoFreeMdl(v33);
        v33 = Next;
      }
      while ( Next );
    }
    *(_QWORD *)(v5 + 48) = 0;
    *(_QWORD *)(v5 + 56) = 0;
    while ( 1 )
    {
      v35 = *(_QWORD *)(v5 + 72);
      if ( !v35 )
        break;
      *(_QWORD *)(v5 + 72) = *(_QWORD *)v35;
      ExFreePoolWithTag(*(PVOID *)(v35 + 8), 0);
    }
    v43 = *(void (__fastcall **)(_QWORD, __int64, __int64))(v5 + 16);
    if ( v43 )
    {
      v44 = *(unsigned int *)(v5 + 32);
      if ( (int)v44 < 0 )
        v45 = 0;
      else
        v45 = *(_QWORD *)(v5 + 40);
      v43(*(_QWORD *)(v5 + 24), v44, v45);
    }
    v46 = *(_QWORD *)(v5 + 8);
    if ( v46 )
    {
      v47 = v46 + 20;
      v48 = _InterlockedDecrement((volatile signed __int32 *)(v46 + 20));
      if ( UxDebugCheckRefcount && v48 <= -1 )
        UlBugCheckEx(3u, v47, 0x2Bu, v48);
      if ( !v48 )
        UxDuoFreeStream(v46, v47, a3, a4);
      *(_QWORD *)(v5 + 8) = 0;
    }
    ExFreePoolWithTag((PVOID)v5, 0);
  }
LABEL_41:
  switch ( *((_DWORD *)Entry + 16) )
  {
    case 9:
      v36 = (volatile signed __int32 *)*((_QWORD *)Entry + 9);
      if ( !v36 )
        break;
      v37 = *((_QWORD *)Entry + 7);
      v38 = _InterlockedDecrement(v36 + 5);
      if ( UxDebugCheckRefcount && v38 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v36 + 5), 1u, v38);
      if ( v38 )
        goto LABEL_84;
      if ( *((_QWORD *)v36 + 3) )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(v37 + 16) + 128LL))(*(_QWORD *)(v37 + 8));
        *((_QWORD *)v36 + 3) = 0;
      }
      v16 = UxDebugDisableLookaside == 0;
      *((_DWORD *)v36 + 4) = 2021218421;
      if ( !v16 )
      {
        memset(v59, 0, sizeof(v59));
        v59[10] = dword_1401A07D8;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A07E8)(v36, v59);
        goto LABEL_84;
      }
      if ( !UxCompactMode )
      {
        v39 = qword_1401A07C0 + ((unsigned __int64)(unsigned int)(*v36 + 1) << 7);
        if ( !*(_BYTE *)(v39 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A07C0, v39 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v39 + 64), (PVOID)v36);
        goto LABEL_84;
      }
      PnlFreeToLookasideList(qword_1401A07C0, v36);
      *((_QWORD *)Entry + 9) = 0;
      break;
    case 0xA:
      v53 = (volatile signed __int32 *)*((_QWORD *)Entry + 9);
      if ( v53 )
      {
        v50 = _InterlockedDecrement(v53);
        if ( UxDebugCheckRefcount && v50 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v53, 0x3Au, v50);
        if ( !v50 )
          UxDuoFreeDeclarePushParameters((PVOID)v53);
        *((_QWORD *)Entry + 10) = 0;
        *((_QWORD *)Entry + 9) = 0;
      }
      break;
    case 0x11:
      v52 = (IRP *)*((_QWORD *)Entry + 9);
      if ( v52 )
      {
        IofCompleteRequest(v52, 0);
LABEL_84:
        *((_QWORD *)Entry + 9) = 0;
      }
      break;
  }
  v27 = *((_QWORD *)Entry + 6);
  if ( v27 )
  {
    v28 = v27 + 20;
    v29 = _InterlockedDecrement((volatile signed __int32 *)(v27 + 20));
    if ( UxDebugCheckRefcount && v29 <= -1 )
      UlBugCheckEx(3u, v28, 0x2Cu, v29);
    if ( !v29 )
      UxDuoFreeStream(v27, v28, a3, a4);
    *((_QWORD *)Entry + 6) = 0;
  }
  v30 = (volatile signed __int32 *)*((_QWORD *)Entry + 7);
  if ( v30 )
  {
    v31 = _InterlockedDecrement(v30 + 1);
    if ( UxDebugCheckRefcount && v31 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v30 + 1), 0x2Cu, v31);
    if ( !v31 )
      UxDuoFreeConnection((PVOID)v30);
    *((_QWORD *)Entry + 7) = 0;
  }
  v16 = UxDebugDisableLookaside == 0;
  *((_DWORD *)Entry + 4) = 1769560181;
  if ( v16 )
  {
    if ( UxCompactMode )
    {
      v40 = qword_1401A0790;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v40, Entry, CurrentNodeNumber);
    }
    else
    {
      v32 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(*(_DWORD *)Entry + 1) << 7);
      if ( !*(_BYTE *)(v32 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0790, v32 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v32 + 64), Entry);
    }
  }
  else
  {
    memset(v59, 0, sizeof(v59));
    v59[10] = dword_1401A07A8;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A07B8)(Entry, v59);
  }
}

```

## disassembly

```asm
0x140004260  push    rbx
0x140004262  push    rbp
0x140004263  push    rsi
0x140004264  push    rdi
0x140004265  push    r12
0x140004267  push    r13
0x140004269  push    r14
0x14000426b  push    r15
0x14000426d  sub     rsp, 0E8h
0x140004274  mov     rax, cs:__security_cookie
0x14000427b  xor     rax, rsp
0x14000427e  mov     [rsp+128h+var_58], rax
0x140004286  mov     rdi, [rcx+30h]
0x14000428a  xor     ebx, ebx
0x14000428c  mov     rsi, rcx
0x14000428f  mov     ebp, 0FFFFFFFFh
0x140004294  cmp     [rdi+60h], bl
0x140004297  jnz     loc_140004895
0x14000429d  mov     r15d, [rcx+8Ch]
0x1400042a4  and     r15d, 2
0x1400042a8  test    byte ptr cs:xmmword_1401A2CA0+3, 8
0x1400042af  jnz     loc_1400049A4
0x1400042b5  cmp     [rdi+194h], bl
0x1400042bb  jnz     loc_1400046C3
0x1400042c1  mov     byte ptr [rdi+194h], 1
0x1400042c8  lea     r9, UxLowPriorityPool
0x1400042cf  mov     eax, [rsi+88h]
0x1400042d5  mov     edx, 88h
0x1400042da  mov     r13, [rsi+80h]
0x1400042e1  mov     ecx, 100h
0x1400042e6  mov     [rsp+128h+var_E0], eax
0x1400042ea  mov     r8d, 43597855h
0x1400042f0  mov     rax, [rsi+78h]
0x1400042f4  mov     [rsp+128h+var_C8], rax
0x1400042f9  mov     eax, [rsi+8Ch]
0x1400042ff  mov     dword ptr [rsp+128h+var_E8], eax
0x140004303  mov     rax, [rsi+60h]
0x140004307  mov     [rsp+128h+var_D0], rax
0x14000430c  mov     rax, [rsi+58h]
0x140004310  mov     [rsp+128h+var_D8], rax
0x140004315  mov     dword ptr [rsp+128h+var_108], 1
0x14000431d  call    cs:__imp_ExAllocatePool3
0x140004324  nop     dword ptr [rax+rax+00h]
0x140004329  mov     rbx, rax
0x14000432c  test    rax, rax
0x14000432f  jz      loc_140004A72
0x140004335  mov     dword ptr [rax], 1
0x14000433b  lea     rcx, [rbx+70h]
0x14000433f  mov     rax, [rsp+128h+var_D8]
0x140004344  lea     rdx, [rdi+14h]; BugCheckParameter2
0x140004348  mov     [rbx+10h], rax
0x14000434c  mov     rax, [rsp+128h+var_D0]
0x140004351  mov     [rbx+18h], rax
0x140004355  mov     eax, dword ptr [rsp+128h+var_E8]
0x140004359  mov     [rbx+80h], eax
0x14000435f  mov     rax, [rsp+128h+var_C8]
0x140004364  mov     [rbx+58h], rax
0x140004368  mov     eax, [rsp+128h+var_E0]
0x14000436c  mov     [rbx+68h], eax
0x14000436f  mov     eax, 1
0x140004374  mov     [rbx+28h], r13
0x140004378  mov     byte ptr [rbx+50h], 1
0x14000437c  mov     [rbx+60h], r13
0x140004380  movups  xmm0, xmmword ptr [rsi+48h]
0x140004384  mov     [rbx+8], rdi
0x140004388  movups  xmmword ptr [rcx], xmm0
0x14000438b  lock xadd [rdx], eax
0x14000438f  inc     eax
0x140004391  cmp     cs:UxDebugCheckRefcount, 0
0x140004398  jnz     loc_1400046A7
0x14000439e  xorps   xmm0, xmm0
0x1400043a1  mov     [rsp+128h+var_E8], 0
0x1400043aa  movups  xmmword ptr [rbx+30h], xmm0
0x1400043ae  movups  xmmword ptr [rbx+40h], xmm0
0x1400043b2  mov     r13, [rsi+68h]
0x1400043b6  mov     rax, [rsi+70h]
0x1400043ba  mov     rdx, [rsi+80h]
0x1400043c1  mov     [rsp+128h+var_D8], rax
0x1400043c6  mov     [rsp+128h+var_D0], rdx
0x1400043cb  test    r13, r13
0x1400043ce  jz      loc_140004AC0
0x1400043d4  cmp     byte ptr [rbx+50h], 0
0x1400043d8  mov     eax, [rsi+88h]
0x1400043de  mov     [rsp+128h+var_E0], eax
0x1400043e2  mov     rax, [rsi+78h]
0x1400043e6  mov     [rsp+128h+var_C8], rax
0x1400043eb  jz      loc_1400044C7
0x1400043f1  xor     r9d, r9d
0x1400043f4  mov     r8, [rdi+30h]
0x1400043f8  lea     rax, [rsp+128h+var_E8]
0x1400043fd  mov     [rsp+128h+var_100], rax
0x140004402  mov     rdx, rdi
0x140004405  mov     [rsp+128h+var_108], rcx
0x14000440a  xor     ecx, ecx
0x14000440c  call    UxDuoAllocateParcel
0x140004411  mov     r14d, eax
0x140004414  test    eax, eax
0x140004416  js      loc_140004527
0x14000441c  mov     r8, [rsp+128h+var_E8]
0x140004421  mov     eax, 1
0x140004426  mov     [r8+108h], rbx
0x14000442d  lock xadd [rbx], eax
0x140004431  inc     eax
0x140004433  cmp     cs:UxDebugCheckRefcount, 0
0x14000443a  jnz     loc_140004876
0x140004440  mov     rax, [rsp+128h+var_C8]
0x140004445  mov     [r8+110h], rax
0x14000444c  mov     eax, [rsp+128h+var_E0]
0x140004450  mov     [r8+120h], rax
0x140004457  mov     rax, [rsp+128h+var_D0]
0x14000445c  mov     [r8+118h], rax
0x140004463  mov     [r8+0F0h], r13
0x14000446a  cmp     byte ptr [rbx+50h], 0
0x14000446e  jz      loc_14000498F
0x140004474  cmp     [rsp+128h+var_D8], 0
0x14000447a  jnz     loc_14000498F
0x140004480  mov     al, 1
0x140004482  mov     [r8+130h], al
0x140004489  movsxd  rax, dword ptr [r8+0E8h]
0x140004490  mov     r10, [r8+58h]
0x140004494  mov     r9, [r8+50h]
0x140004498  mov     byte ptr [r8+0D0h], 1
0x1400044a0  mov     dword ptr [r8+0B4h], 1
0x1400044ab  cmp     eax, 0Ah
0x1400044ae  jnz     short loc_1400044D3
0x1400044b0  lea     rax, [r9+118h]; jumptable 000000014016FD8E cases 0,2
0x1400044b7  mov     rcx, [rax+8]
0x1400044bb  cmp     [rcx], rax
0x1400044be  jz      short loc_1400044EC
0x1400044c0  mov     ecx, 3
0x1400044c5  int     29h; Win8: RtlFailFast(ecx)
0x1400044c7  mov     r9d, [rbx+80h]
0x1400044ce  jmp     loc_1400043F4
0x1400044d3  cmp     eax, 9
0x1400044d6  jnz     loc_140004996
0x1400044dc  lea     rax, [r10+4258h]; jumptable 000000014016FD8E cases 1,3-8
0x1400044e3  mov     rcx, [rax+8]
0x1400044e7  cmp     [rcx], rax
0x1400044ea  jnz     short loc_1400044C0
0x1400044ec  mov     [r8], rax
0x1400044ef  mov     [r8+8], rcx
0x1400044f3  mov     [rcx], r8
0x1400044f6  mov     [rax+8], r8
0x1400044fa  test    r9, r9; jumptable 000000014016FD8E default case
0x1400044fd  jz      loc_140004784
0x140004503  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x14000450a  jnz     loc_140004B2F
0x140004510  mov     rax, [rsp+128h+var_D8]
0x140004515  mov     [rsp+128h+var_E8], 0
0x14000451e  test    rax, rax
0x140004521  jnz     loc_140004B6F
0x140004527  xor     r13b, r13b
0x14000452a  test    r14d, r14d
0x14000452d  js      loc_14000495C
0x140004533  mov     rcx, [rdi+30h]
0x140004537  call    UxDuoDispatchConnectionSends
0x14000453c  mov     r14d, eax
0x14000453f  test    eax, eax
0x140004541  js      short loc_140004585
0x140004543  test    r15d, r15d
0x140004546  jz      short loc_140004563
0x140004548  cmp     byte ptr [rdi+18Eh], 0
0x14000454f  jnz     short loc_140004563
0x140004551  mov     rcx, rdi
0x140004554  mov     byte ptr [rdi+18Eh], 1
0x14000455b  call    UxDuoRunStreamReceivePump
0x140004560  mov     r14d, eax
0x140004563  test    r13b, r13b
0x140004566  jz      short loc_140004580
0x140004568  mov     rax, [rsi+58h]
0x14000456c  test    rax, rax
0x14000456f  jz      short loc_140004580
0x140004571  mov     rcx, [rsi+60h]
0x140004575  xor     r8d, r8d
0x140004578  mov     edx, r14d
0x14000457b  call    _guard_dispatch_icall
0x140004580  test    rbx, rbx
0x140004583  jz      short loc_1400045B1
0x140004585  cmp     dword ptr [rbx+20h], 0
0x140004589  jl      short loc_140004594
0x14000458b  test    r14d, r14d
0x14000458e  js      loc_14000493B
0x140004594  mov     eax, ebp
0x140004596  lock xadd [rbx], eax
0x14000459a  dec     eax
0x14000459c  cmp     cs:UxDebugCheckRefcount, 0
0x1400045a3  jnz     loc_1400048A0
0x1400045a9  test    eax, eax
0x1400045ab  jz      loc_140004725
0x1400045b1  xor     r14d, r14d
0x1400045b4  mov     ecx, [rsi+40h]
0x1400045b7  sub     ecx, 9
0x1400045ba  jz      loc_1400047C9
0x1400045c0  sub     ecx, 1
0x1400045c3  jz      loc_140004BA5
0x1400045c9  cmp     ecx, 7
0x1400045cc  jz      loc_140004B85
0x1400045d2  mov     rcx, [rsi+30h]
0x1400045d6  test    rcx, rcx
0x1400045d9  jz      short loc_140004601
0x1400045db  lea     rdx, [rcx+14h]; BugCheckParameter2
0x1400045df  mov     eax, ebp
0x1400045e1  lock xadd [rdx], eax
0x1400045e5  dec     eax
0x1400045e7  cmp     cs:UxDebugCheckRefcount, 0
0x1400045ee  jnz     loc_1400048DC
0x1400045f4  test    eax, eax
0x1400045f6  jnz     short loc_1400045FD
0x1400045f8  call    UxDuoFreeStream
0x1400045fd  mov     [rsi+30h], r14
0x140004601  mov     rcx, [rsi+38h]; P
0x140004605  test    rcx, rcx
0x140004608  jz      short loc_14000462D
0x14000460a  lea     rdx, [rcx+4]; BugCheckParameter2
0x14000460e  lock xadd [rdx], ebp
0x140004612  dec     ebp
0x140004614  cmp     cs:UxDebugCheckRefcount, 0
0x14000461b  jnz     loc_1400048BF
0x140004621  test    ebp, ebp
0x140004623  jz      loc_14000477A
0x140004629  mov     [rsi+38h], r14
0x14000462d  cmp     cs:UxDebugDisableLookaside, 0
0x140004634  mov     dword ptr [rsi+10h], 69795875h
0x14000463b  jnz     loc_140004BF9
0x140004641  cmp     cs:UxCompactMode, 0
0x140004648  jnz     loc_1400048F8
0x14000464e  mov     ebx, [rsi]
0x140004650  mov     rcx, cs:qword_1401A0790
0x140004657  inc     ebx
0x140004659  shl     rbx, 7
0x14000465d  add     rbx, rcx
0x140004660  movzx   eax, byte ptr [rbx+0B0h]
0x140004667  test    al, al
0x140004669  jz      loc_1400049E9
0x14000466f  mov     rdx, rsi; Entry
0x140004672  lea     rcx, [rbx+40h]; Lookaside
0x140004676  call    cs:__imp_ExFreeToLookasideListEx
0x14000467d  nop     dword ptr [rax+rax+00h]
0x140004682  mov     rcx, [rsp+128h+var_58]
0x14000468a  xor     rcx, rsp; StackCookie
0x14000468d  call    __security_check_cookie
0x140004692  add     rsp, 0E8h
0x140004699  pop     r15
0x14000469b  pop     r14
0x14000469d  pop     r13
0x14000469f  pop     r12
0x1400046a1  pop     rdi
0x1400046a2  pop     rsi
0x1400046a3  pop     rbp
0x1400046a4  pop     rbx
0x1400046a5  retn
0x1400046a7  cmp     eax, ebp
0x1400046a9  jg      loc_14000439E
0x1400046af  movsxd  r9, eax; BugCheckParameter4
0x1400046b2  mov     ecx, 3; BugCheckParameter1
0x1400046b7  mov     r8d, 2Bh ; '+'; BugCheckParameter3
0x1400046bd  call    UlBugCheckEx
0x1400046c3  cmp     [rsi+78h], rbx
0x1400046c7  jnz     short loc_1400046EA
0x1400046c9  cmp     [rsi+88h], ebx
0x1400046cf  jnz     short loc_1400046EA
0x1400046d1  cmp     [rsi+80h], rbx
0x1400046d8  jnz     short loc_1400046EA
0x1400046da  xor     r14d, r14d
0x1400046dd  mov     r13b, 1
0x1400046e0  cmp     [rsi+70h], rbx
0x1400046e4  jz      loc_140004543
0x1400046ea  test    cs:byte_1401A2C8B, 8
0x1400046f1  jz      loc_14016FD5C
0x1400046f7  mov     r9, [rdi+30h]
0x1400046fb  lea     r8, WPP_309922b680ce3405e88e422e035050e4_Traceguids
0x140004702  mov     eax, [rdi+58h]
0x140004705  mov     edx, 26h ; '&'
0x14000470a  mov     ecx, 11Bh
0x14000470f  mov     dword ptr [rsp+128h+var_108], eax
0x140004713  mov     r9d, [r9+4350h]
0x14000471a  call    WPP_SF_Dd
0x14000471f  nop
0x140004720  jmp     loc_14016FD5C
0x140004725  mov     rcx, [rbx+30h]; Mdl
0x140004729  test    rcx, rcx
0x14000472c  jz      short loc_140004747
0x14000472e  xchg    ax, ax
0x140004730  mov     rdi, [rcx]
0x140004733  call    cs:__imp_IoFreeMdl
0x14000473a  nop     dword ptr [rax+rax+00h]
0x14000473f  mov     rcx, rdi
0x140004742  test    rdi, rdi
0x140004745  jnz     short loc_140004730
0x140004747  xor     r14d, r14d
0x14000474a  mov     [rbx+30h], r14
0x14000474e  mov     [rbx+38h], r14
0x140004752  mov     rcx, [rbx+48h]
0x140004756  test    rcx, rcx
0x140004759  jz      loc_1400049F7
0x14000475f  mov     rax, [rcx]
0x140004762  xor     edx, edx; Tag
0x140004764  mov     [rbx+48h], rax
0x140004768  mov     rcx, [rcx+8]; P
0x14000476c  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
