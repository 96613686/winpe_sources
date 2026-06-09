# CscCollapseOpen

- ea: `0x14007fc40`
- end: `0x1400801ae`
- name: `CscCollapseOpen`
- size: `1390`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x140003a00`
- `0x1400084f0`
- `0x14000e100`
- `0x140012118`
- `0x140018fd0`
- `0x1400190ec`
- `0x14001c6c4`
- `0x14002f010`
- `0x14002f0f0`
- `0x1400498f0`
- `0x14007fc40`
- `0x140088890`

## import_xrefs

- `rdbss!RxCreateNetFobx` at `0x1400800a5`
- `rdbss!RxCreateNetFobx` at `0x1400800a5`

## pseudocode

```c
__int64 __fastcall CscCollapseOpen(PRX_CONTEXT RxContext)
{
  int v1; // edi
  int Blink; // r12d
  PMRX_FOBX pFobx; // r14
  bool v5; // si
  char v6; // r13
  int v7; // r9d
  int v8; // ecx
  int v9; // r10d
  int v10; // r11d
  __int64 v11; // rdx
  char v12; // al
  bool v13; // r15
  struct _MRX_SRV_OPEN_ *v14; // rsi
  int v15; // eax
  int v16; // esi
  PMRX_SRV_OPEN v17; // r8
  __int64 v18; // rax
  PUNICODE_STRING pAlreadyPrefixedName; // rcx
  _DWORD *v20; // r8
  __int64 v21; // r9
  void (__fastcall *v22)(PRX_CONTEXT); // rax
  unsigned int v24; // eax
  PMRX_FOBX NetFobx; // rax
  int v26; // ecx
  int v27; // r9d
  char v28; // [rsp+50h] [rbp-49h]
  PMRX_SRV_OPEN MrxSrvOpen; // [rsp+58h] [rbp-41h]
  PMRX_FCB pFcb; // [rsp+60h] [rbp-39h]
  __int128 v31; // [rsp+68h] [rbp-31h] BYREF
  __int128 v32; // [rsp+78h] [rbp-21h]
  __int64 v33; // [rsp+88h] [rbp-11h]
  __int128 v34; // [rsp+90h] [rbp-9h] BYREF

  v1 = 0;
  Blink = (int)RxContext->WorkQueueItem.List.Blink;
  pFobx = 0;
  pFcb = RxContext->pFcb;
  v5 = RxContext->NonPagedFcb != (PNON_PAGED_FCB)CscDeviceObject;
  MrxSrvOpen = RxContext->pRelevantSrvOpen;
  v28 = 0;
  v33 = 0;
  v6 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  CscGetContexts(RxContext, &v31);
  LOBYTE(v7) = 1;
  CscUpdateAndCaptureConnectionStateEx(v10, v9, v8, v7, (__int64)&v34, 0);
  if ( (BYTE1(v34) & 0x10) != 0
    || (v11 = *((_QWORD *)&v32 + 1), (Blink & 0x2000) != 0) && (*(_DWORD *)(*((_QWORD *)&v32 + 1) + 4LL) & 0x20) != 0
    || (Blink & 0x8000) != 0 && (*(_DWORD *)(*((_QWORD *)&v32 + 1) + 4LL) & 1) != 0 )
  {
    v12 = 16;
  }
  else
  {
    v12 = 0;
  }
  BYTE1(v34) = v12 | BYTE1(v34) & 0xEF;
  v13 = v5 && (v34 & 0x10) == 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (v11 = *(_DWORD *)(v32 + 24) & 2, (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0) )
  {
    v14 = MrxSrvOpen;
    WPP_SF_cDccqqq(WPP_GLOBAL_Control->AttachedDevice);
  }
  else
  {
    v14 = MrxSrvOpen;
  }
  if ( v13 )
  {
    if ( RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[5].Flink )
    {
      if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) == 0 )
      {
        *(_OWORD *)&RxContext->MRxContext[2] = 0;
        *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
        RxContext->ResumeRoutine = 0;
        v15 = ((__int64 (__fastcall *)(PRX_CONTEXT, __int64))RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[5].Flink)(
                RxContext,
                v11);
        pFobx = RxContext->pFobx;
        v1 = v15;
        if ( v15 >= 0 )
        {
          v6 = 1;
          goto LABEL_16;
        }
LABEL_45:
        CscCheckRdrStatusTransitionIfNetErr(v1, &v34, (__int64)pFcb);
        goto LABEL_16;
      }
      v1 = -1073741536;
    }
    else
    {
      v1 = -1073741822;
    }
    pFobx = RxContext->pFobx;
    goto LABEL_45;
  }
LABEL_16:
  if ( (v34 & 0x10) == 0 || pFobx )
  {
    v16 = 0;
    if ( !pFobx )
    {
      if ( v1 >= 0 )
        goto LABEL_49;
      goto LABEL_38;
    }
  }
  else
  {
    NetFobx = RxCreateNetFobx(RxContext, v14);
    pFobx = NetFobx;
    if ( !NetFobx )
    {
      v1 = -1073741670;
      v16 = 9469;
      goto LABEL_38;
    }
    LODWORD(NetFobx[1].Context) = 1;
    v16 = 0;
    RxContext->pFobx = NetFobx;
    v28 = 1;
  }
  v1 = CscCreateAndInitializeFobxContext(pFobx, &v31, 0, 0);
  if ( v1 < 0 )
  {
    v16 = 9487;
LABEL_38:
    if ( v6 )
    {
      v22 = *(void (__fastcall **)(PRX_CONTEXT))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&pFcb->UncleanCount
                                                                                   + 32LL)
                                                                       + 48LL)
                                                           + 352LL)
                                               + 104LL);
      if ( v22 )
        v22(RxContext);
    }
    goto LABEL_49;
  }
  if ( (Blink & 0x20000) != 0 )
    *(_DWORD *)(v31 + 4) |= 0x200u;
  if ( (_QWORD)v32 )
  {
    if ( (Blink & 0x2000) != 0 && (*(_DWORD *)(*((_QWORD *)&v32 + 1) + 4LL) & 0x20) != 0
      || (Blink & 0x8000) != 0 && (*(_DWORD *)(*((_QWORD *)&v32 + 1) + 4LL) & 1) != 0 )
    {
      ++*(_DWORD *)(*((_QWORD *)&v31 + 1) + 76LL);
      if ( (*(_DWORD *)(v32 + 24) & 0x809) == 0 && ((v34 & 1) == 0 || (BYTE1(v34) & 4) != 0) )
      {
        v26 = *(_DWORD *)(*((_QWORD *)&v31 + 1) + 4LL);
        if ( (v26 & 0x1166F) != 0
          && ((v26 & 0x200) != 0 || (v26 & 0x80000) != 0 || DWORD2(v34) > *(_DWORD *)(*((_QWORD *)&v31 + 1) + 40LL))
          && (v26 & 0x60) == 0 )
        {
          v24 = CscBackPatchObject((__int64)RxContext, (char *)&v34, (__int64)&v31);
          if ( v24 == -1073741225 )
          {
            v1 = -1073741225;
            v16 = 9526;
            --*(_DWORD *)(*((_QWORD *)&v31 + 1) + 76LL);
            goto LABEL_38;
          }
          CscUpdateFcbContextOnBackpatch(*((_QWORD *)&v31 + 1), &v34, v24);
          LOBYTE(v27) = 1;
          CscUpdateAndCaptureConnectionStateEx(
            (_DWORD)pFcb,
            (_DWORD)MrxSrvOpen,
            (_DWORD)RxContext,
            v27,
            (__int64)&v34,
            1);
        }
      }
      *(_DWORD *)(v31 + 4) |= 0x40u;
    }
    v17 = MrxSrvOpen;
    if ( (*(_DWORD *)&MrxSrvOpen[1].NodeTypeCode & 0xFFEFFF7F) != 0 )
    {
      ++*(_DWORD *)(*((_QWORD *)&v31 + 1) + 16LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v17 = MrxSrvOpen;
      }
    }
  }
  else
  {
    v17 = MrxSrvOpen;
  }
  if ( v13 && !v28 )
  {
    *(_DWORD *)(v31 + 4) |= 2u;
    *(_QWORD *)(v31 + 64) = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[9].Flink;
  }
  if ( v6 )
  {
    *(_DWORD *)(v31 + 4) |= 1u;
    v18 = *((_QWORD *)&v31 + 1);
    pAlreadyPrefixedName = v17->pAlreadyPrefixedName;
    ++*(_DWORD *)(*((_QWORD *)&v31 + 1) + 8LL);
    v20 = (_DWORD *)(v18 + 12);
    v21 = *(unsigned int *)(v18 + 8);
    if ( ((__int64)pAlreadyPrefixedName[1].Buffer & 0x10000) != 0 )
      ++*v20;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v21, *v20);
  }
LABEL_49:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      168,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)v1,
      v16);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14007fc40  push    rbp
0x14007fc42  push    rbx
0x14007fc43  push    rsi
0x14007fc44  push    rdi
0x14007fc45  push    r12
0x14007fc47  push    r13
0x14007fc49  push    r14
0x14007fc4b  push    r15
0x14007fc4d  lea     rbp, [rsp-1Fh]
0x14007fc52  sub     rsp, 0B8h
0x14007fc59  mov     rax, cs:__security_cookie
0x14007fc60  xor     rax, rsp
0x14007fc63  mov     [rbp+57h+var_50], rax
0x14007fc67  mov     rax, cs:CscDeviceObject
0x14007fc6e  lea     rdx, [rbp+57h+var_88]
0x14007fc72  mov     r11, [rcx+38h]
0x14007fc76  xorps   xmm0, xmm0
0x14007fc79  mov     r10, [rcx+48h]
0x14007fc7d  xor     edi, edi
0x14007fc7f  mov     r12d, [rcx+100h]
0x14007fc86  xor     r14d, r14d
0x14007fc89  cmp     [rcx+50h], rax
0x14007fc8d  mov     rbx, rcx
0x14007fc90  mov     [rbp+57h+var_90], r11
0x14007fc94  setnz   sil
0x14007fc98  mov     [rbp+57h+MrxSrvOpen], r10
0x14007fc9c  xor     eax, eax
0x14007fc9e  mov     [rbp+57h+var_A0], dil
0x14007fca2  mov     [rbp+57h+var_68], rax
0x14007fca6  xor     r13b, r13b
0x14007fca9  movups  [rbp+57h+var_88], xmm0
0x14007fcad  movups  [rbp+57h+var_78], xmm0
0x14007fcb1  movups  [rbp+57h+var_60], xmm0
0x14007fcb5  call    CscGetContexts
0x14007fcba  lea     rax, [rbp+57h+var_60]
0x14007fcbe  mov     byte ptr [rsp+0F0h+var_C8], dil
0x14007fcc3  mov     r8, rcx
0x14007fcc6  mov     [rsp+0F0h+var_D0], rax
0x14007fccb  mov     rcx, r11
0x14007fcce  mov     r9b, 1
0x14007fcd1  mov     rdx, r10
0x14007fcd4  call    CscUpdateAndCaptureConnectionStateEx
0x14007fcd9  movzx   ecx, byte ptr [rbp+57h+var_60+1]
0x14007fcdd  test    cl, 10h
0x14007fce0  jnz     loc_14007FF21
0x14007fce6  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x14007fcea  bt      r12d, 0Dh
0x14007fcef  jb      loc_140080018
0x14007fcf5  bt      r12d, 0Fh
0x14007fcfa  jb      loc_140080028
0x14007fd00  xor     al, al
0x14007fd02  and     cl, 0EFh
0x14007fd05  or      cl, al
0x14007fd07  mov     byte ptr [rbp+57h+var_60+1], cl
0x14007fd0a  test    sil, sil
0x14007fd0d  jz      loc_14007FF19
0x14007fd13  test    byte ptr [rbp+57h+var_60], 10h
0x14007fd17  jnz     loc_14007FF19
0x14007fd1d  mov     r15b, 1
0x14007fd20  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fd27  lea     rax, WPP_GLOBAL_Control
0x14007fd2e  cmp     rcx, rax
0x14007fd31  jz      short loc_14007FD48
0x14007fd33  mov     rax, qword ptr [rbp+57h+var_78]
0x14007fd37  mov     edx, [rax+18h]
0x14007fd3a  mov     eax, [rcx+2Ch]
0x14007fd3d  and     edx, 2
0x14007fd40  test    al, 20h
0x14007fd42  jnz     loc_140080038
0x14007fd48  mov     rsi, [rbp+57h+MrxSrvOpen]
0x14007fd4c  test    r15b, r15b
0x14007fd4f  jz      short loc_14007FDB6
0x14007fd51  mov     rax, [rbx+50h]
0x14007fd55  mov     rcx, [rax+160h]
0x14007fd5c  cmp     [rcx+50h], rdi
0x14007fd60  jz      loc_14007FF28
0x14007fd66  mov     eax, [rbx+80h]
0x14007fd6c  test    al, 2
0x14007fd6e  jnz     loc_14007FFBC
0x14007fd74  xor     eax, eax
0x14007fd76  xorps   xmm0, xmm0
0x14007fd79  movups  xmmword ptr [rbx+0D0h], xmm0
0x14007fd80  movups  xmmword ptr [rbx+0E0h], xmm0
0x14007fd87  mov     [rbx+0F0h], rax
0x14007fd8e  mov     rax, [rbx+50h]
0x14007fd92  mov     rcx, [rax+160h]
0x14007fd99  mov     rax, [rcx+50h]
0x14007fd9d  mov     rcx, rbx
0x14007fda0  call    _guard_dispatch_icall
0x14007fda5  mov     r14, [rbx+40h]
0x14007fda9  mov     edi, eax
0x14007fdab  test    eax, eax
0x14007fdad  js      loc_14007FF31
0x14007fdb3  mov     r13b, 1
0x14007fdb6  test    byte ptr [rbp+57h+var_60], 10h
0x14007fdba  jnz     loc_140080096
0x14007fdc0  xor     esi, esi
0x14007fdc2  test    r14, r14
0x14007fdc5  jz      loc_14007FF55
0x14007fdcb  xor     r9d, r9d
0x14007fdce  lea     rdx, [rbp+57h+var_88]
0x14007fdd2  xor     r8d, r8d
0x14007fdd5  mov     rcx, r14
0x14007fdd8  call    CscCreateAndInitializeFobxContext
0x14007fddd  mov     edi, eax
0x14007fddf  test    eax, eax
0x14007fde1  js      loc_14007FEE5
0x14007fde7  bt      r12d, 11h
0x14007fdec  jb      loc_1400800DE
0x14007fdf2  cmp     qword ptr [rbp+57h+var_78], 0
0x14007fdf7  jz      loc_14007FF45
0x14007fdfd  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x14007fe01  bt      r12d, 0Dh
0x14007fe06  jb      loc_1400800EE
0x14007fe0c  bt      r12d, 0Fh
0x14007fe11  jb      loc_1400800FA
0x14007fe17  mov     r8, [rbp+57h+MrxSrvOpen]
0x14007fe1b  test    dword ptr [r8+78h], 0FFEFFF7Fh
0x14007fe23  jz      loc_14007FF49
0x14007fe29  mov     rax, qword ptr [rbp+57h+var_88+8]
0x14007fe2d  inc     dword ptr [rax+10h]
0x14007fe30  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fe37  lea     r14, WPP_GLOBAL_Control
0x14007fe3e  cmp     rcx, r14
0x14007fe41  jz      short loc_14007FE4E
0x14007fe43  mov     eax, [rcx+2Ch]
0x14007fe46  test    al, 40h
0x14007fe48  jnz     loc_140080177
0x14007fe4e  test    r15b, r15b
0x14007fe51  jz      short loc_14007FE7B
0x14007fe53  cmp     [rbp+57h+var_A0], 0
0x14007fe57  jnz     short loc_14007FE7B
0x14007fe59  mov     rax, qword ptr [rbp+57h+var_88]
0x14007fe5d  or      dword ptr [rax+4], 2
0x14007fe61  mov     rax, [rbx+50h]
0x14007fe65  mov     rcx, [rax+160h]
0x14007fe6c  mov     rax, qword ptr [rbp+57h+var_88]
0x14007fe70  mov     rdx, [rcx+90h]
0x14007fe77  mov     [rax+40h], rdx
0x14007fe7b  test    r13b, r13b
0x14007fe7e  jz      loc_14007FF60
0x14007fe84  mov     rax, qword ptr [rbp+57h+var_88]
0x14007fe88  or      dword ptr [rax+4], 1
0x14007fe8c  mov     rax, qword ptr [rbp+57h+var_88+8]
0x14007fe90  mov     rcx, [r8+38h]
0x14007fe94  inc     dword ptr [rax+8]
0x14007fe97  lea     r8, [rax+0Ch]
0x14007fe9b  test    dword ptr [rcx+18h], 10000h
0x14007fea2  mov     r9d, [rax+8]
0x14007fea6  jnz     loc_14007FFB4
0x14007feac  mov     rcx, cs:WPP_GLOBAL_Control
0x14007feb3  cmp     rcx, r14
0x14007feb6  jz      loc_14007FF60
0x14007febc  mov     eax, [rcx+2Ch]
0x14007febf  test    al, 40h
0x14007fec1  jz      loc_14007FF60
0x14007fec7  mov     eax, [r8]
0x14007feca  mov     edx, 0Dh
0x14007fecf  mov     rcx, [rcx+18h]
0x14007fed3  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14007feda  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14007fede  call    WPP_SF_Dd
0x14007fee3  jmp     short loc_14007FF60
0x14007fee5  mov     esi, 250Fh
0x14007feea  test    r13b, r13b
0x14007feed  jz      short loc_14007FF59
0x14007feef  mov     rax, [rbp+57h+var_90]
0x14007fef3  mov     rax, [rax+78h]
0x14007fef7  mov     rcx, [rax+20h]
0x14007fefb  mov     rax, [rcx+30h]
0x14007feff  mov     rcx, [rax+160h]
0x14007ff06  mov     rax, [rcx+68h]
0x14007ff0a  test    rax, rax
0x14007ff0d  jz      short loc_14007FF59
0x14007ff0f  mov     rcx, rbx
0x14007ff12  call    _guard_dispatch_icall
0x14007ff17  jmp     short loc_14007FF59
0x14007ff19  xor     r15b, r15b
0x14007ff1c  jmp     loc_14007FD20
0x14007ff21  mov     al, 10h
0x14007ff23  jmp     loc_14007FD02
0x14007ff28  mov     edi, 0C0000002h
0x14007ff2d  mov     r14, [rbx+40h]
0x14007ff31  mov     r8, [rbp+57h+var_90]
0x14007ff35  lea     rdx, [rbp+57h+var_60]
0x14007ff39  mov     ecx, edi
0x14007ff3b  call    CscCheckRdrStatusTransitionIfNetErr
0x14007ff40  jmp     loc_14007FDB6
0x14007ff45  mov     r8, [rbp+57h+MrxSrvOpen]
0x14007ff49  lea     r14, WPP_GLOBAL_Control
0x14007ff50  jmp     loc_14007FE4E
0x14007ff55  test    edi, edi
0x14007ff57  js      short loc_14007FEEA
0x14007ff59  lea     r14, WPP_GLOBAL_Control
0x14007ff60  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ff67  cmp     rcx, r14
0x14007ff6a  jnz     short loc_14007FF8F
0x14007ff6c  mov     eax, edi
0x14007ff6e  mov     rcx, [rbp+57h+var_50]
0x14007ff72  xor     rcx, rsp; StackCookie
0x14007ff75  call    __security_check_cookie
0x14007ff7a  add     rsp, 0B8h
0x14007ff81  pop     r15
0x14007ff83  pop     r14
0x14007ff85  pop     r13
0x14007ff87  pop     r12
0x14007ff89  pop     rdi
0x14007ff8a  pop     rsi
0x14007ff8b  pop     rbx
0x14007ff8c  pop     rbp
0x14007ff8d  retn
0x14007ff8f  mov     eax, [rcx+2Ch]
0x14007ff92  test    al, 20h
0x14007ff94  jz      short loc_14007FF6C
0x14007ff96  mov     rcx, [rcx+18h]
0x14007ff9a  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14007ffa1  mov     edx, 0A8h
0x14007ffa6  mov     dword ptr [rsp+0F0h+var_D0], esi
0x14007ffaa  mov     r9d, edi
0x14007ffad  call    WPP_SF_Dd
0x14007ffb2  jmp     short loc_14007FF6C
0x14007ffb4  inc     dword ptr [r8]
0x14007ffb7  jmp     loc_14007FEAC
0x14007ffbc  mov     edi, 0C0000120h
0x14007ffc1  jmp     loc_14007FF2D
0x14007ffc6  bt      ecx, 9
0x14007ffca  jb      short loc_14007FFDE
0x14007ffcc  bt      ecx, 13h
0x14007ffd0  jb      short loc_14007FFDE
0x14007ffd2  mov     eax, [rax+28h]
0x14007ffd5  cmp     dword ptr [rbp+57h+var_60+8], eax
0x14007ffd8  jbe     loc_14008016A
0x14007ffde  test    cl, 60h
0x14007ffe1  jnz     loc_14008016A
0x14007ffe7  lea     r8, [rbp+57h+var_88]
0x14007ffeb  mov     rcx, rbx
0x14007ffee  lea     rdx, [rbp+57h+var_60]
0x14007fff2  call    CscBackPatchObject
0x14007fff7  cmp     eax, 0C0000257h
0x14007fffc  jnz     loc_140080139
0x140080002  mov     rax, qword ptr [rbp+57h+var_88+8]
0x140080006  mov     edi, 0C0000257h
0x14008000b  mov     esi, 2536h
0x140080010  dec     dword ptr [rax+4Ch]
0x140080013  jmp     loc_14007FEEA
0x140080018  mov     eax, [rdx+4]
0x14008001b  test    al, 20h
0x14008001d  jnz     loc_14007FF21
0x140080023  jmp     loc_14007FCF5
0x140080028  mov     eax, [rdx+4]
0x14008002b  test    al, 1
0x14008002d  jnz     loc_14007FF21
0x140080033  jmp     loc_14007FD00
0x140080038  mov     r10, [rbp+57h+var_90]
0x14008003c  test    edx, edx
0x14008003e  mov     rcx, [rcx+18h]
0x140080042  mov     r9d, 59h ; 'Y'
0x140080048  mov     eax, 4Eh ; 'N'
0x14008004d  mov     r8d, r9d
0x140080050  cmovz   r8d, eax
0x140080054  mov     edx, r9d
0x140080057  test    r15b, r15b
0x14008005a  cmovz   edx, eax
0x14008005d  test    sil, sil
0x140080060  mov     rsi, [rbp+57h+MrxSrvOpen]
0x140080064  mov     [rsp+0F0h+var_A8], rsi
0x140080069  cmovz   r9d, eax
0x14008006d  mov     rax, [r10+80h]
0x140080074  mov     [rsp+0F0h+var_B0], rax
0x140080079  mov     [rsp+0F0h+var_B8], r10
0x14008007e  mov     [rsp+0F0h+var_C0], r8b
0x140080083  mov     byte ptr [rsp+0F0h+var_C8], dl
0x140080087  mov     dword ptr [rsp+0F0h+var_D0], r12d
0x14008008c  call    WPP_SF_cDccqqq
0x140080091  jmp     loc_14007FD4C
0x140080096  test    r14, r14
0x140080099  jnz     loc_14007FDC0
0x14008009f  mov     rdx, rsi; MrxSrvOpen
0x1400800a2  mov     rcx, rbx; RxContext
0x1400800a5  call    cs:__imp_RxCreateNetFobx
0x1400800ac  nop     dword ptr [rax+rax+00h]
0x1400800b1  mov     r14, rax
0x1400800b4  test    rax, rax
0x1400800b7  jnz     short loc_1400800C8
0x1400800b9  mov     edi, 0C000009Ah
0x1400800be  mov     esi, 24FDh
0x1400800c3  jmp     loc_14007FEEA
0x1400800c8  mov     dword ptr [rax+60h], 1
0x1400800cf  xor     esi, esi
0x1400800d1  mov     [rbx+40h], rax
0x1400800d5  mov     [rbp+57h+var_A0], 1
0x1400800d9  jmp     loc_14007FDCB
0x1400800de  mov     rax, qword ptr [rbp+57h+var_88]
0x1400800e2  or      dword ptr [rax+4], 200h
0x1400800e9  jmp     loc_14007FDF2
0x1400800ee  mov     eax, [rcx+4]
0x1400800f1  test    al, 20h
0x1400800f3  jnz     short loc_140080105
0x1400800f5  jmp     loc_14007FE0C
0x1400800fa  mov     eax, [rcx+4]
  ... truncated ...
```
