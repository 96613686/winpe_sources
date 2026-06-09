# VidSchiRedirectedFlipWaitOnSyncObject

- ea: `0x1400406e0`
- end: `0x140040bc5`
- name: `VidSchiRedirectedFlipWaitOnSyncObject`
- size: `1253`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, _DWORD *Src, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14003e7e0`

## callees

- `0x140004268`
- `0x140007120`
- `0x140017750`
- `0x14001dc9c`
- `0x14001f640`
- `0x140027b90`
- `0x140030bf4`
- `0x14003fcb0`
- `0x1400406e0`
- `0x140059030`
- `0x140059080`
- `0x1401033a0`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400408f1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400408f1`
- `watchdog!WdLogSingleEntry3` at `0x140040ae9`
- `watchdog!WdLogSingleEntry3` at `0x140040b56`
- `watchdog!WdLogSingleEntry3` at `0x140040ae9`
- `watchdog!WdLogSingleEntry3` at `0x140040b56`
- `watchdog!WdLogSingleEntry4` at `0x140040a5b`
- `watchdog!WdLogSingleEntry4` at `0x140040a5b`
- `watchdog!WdLogSingleEntry0` at `0x1400408a2`
- `watchdog!WdLogSingleEntry0` at `0x140040908`
- `watchdog!WdLogSingleEntry0` at `0x1400408a2`
- `watchdog!WdLogSingleEntry0` at `0x140040908`

## string_xrefs

- `0x1400408b3`: `Synchronization object already has LONG_MAX reference pending, can't reference more.\n`

## pseudocode

```c
__int64 __fastcall VidSchiRedirectedFlipWaitOnSyncObject(
        struct _VIDSCH_GLOBAL *a1,
        _DWORD *Src,
        __int64 a3,
        _DWORD *a4)
{
  struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *v4; // r13
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // r14
  __int64 v12; // rdx
  void (__fastcall *v13)(_QWORD, __int64, __int64); // rax
  unsigned int v14; // edx
  struct _VIDSCH_GLOBAL *v15; // rcx
  unsigned __int64 v16; // r8
  bool v17; // cf
  _DWORD *v18; // rax
  __int64 v19; // r8
  int v20; // ecx
  int v21; // r8d
  _QWORD *v22; // rax
  _QWORD *v23; // r14
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // r10
  char *v27; // rdi
  char **v28; // rcx
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // rax
  unsigned int *v32; // rax
  unsigned __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r9
  unsigned int *v40; // rax
  __int64 v41; // r10
  struct _VIDSCH_GLOBAL *v43; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v44[2]; // [rsp+58h] [rbp-31h] BYREF
  char v45; // [rsp+68h] [rbp-21h]
  int v46; // [rsp+6Ch] [rbp-1Dh]
  _BYTE v47[112]; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v48; // [rsp+F0h] [rbp+67h]

  v4 = (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(Src + 150);
  v48 = 0;
  v9 = *(_QWORD *)((char *)Src + (unsigned int)(8 * Src[151] * (Src[152] + 28)) + 656);
  if ( v9 )
    v10 = *(_QWORD *)(*(_QWORD *)(v9 + 8) + 32LL);
  else
    v10 = 0;
  v11 = (unsigned int)Src[29];
  if ( (*Src & 0x1000000) != 0 && (_DWORD)v11 != -1 )
  {
    v12 = *(unsigned int *)(*((_QWORD *)a1 + v11 + 441) + 44488LL);
    if ( (_DWORD)v12 != -1 )
    {
      v13 = (void (__fastcall *)(_QWORD, __int64, __int64))*((_QWORD *)a1 + 423);
      if ( v13 )
        v13(*((_QWORD *)a1 + 431), v12, 0xFFFFFFFFLL);
    }
  }
  if ( (*a4 & 0x1000) != 0 && (*a4 & 0xC00) != 0x400 && (_DWORD)v11 != -1 && (*Src & 0x1040000) == 0x1040000 )
  {
    _InterlockedIncrement((volatile signed __int32 *)a1 + 220);
    IncrementNumberOfQueuedFlipPerSource(a1, v11);
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 1836));
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 4 * v11 + 1772));
    if ( (*(_DWORD *)(v10 + 56) & 2) != 0 || (int)Src[30] >= 4 || *((_BYTE *)a1 + 164) )
      VidSchIsVSyncEnabled(v15, v14);
  }
  AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v47, (unsigned __int64 *)a1 + 262, 1, 0);
  v43 = a1;
  v44[1] = v44;
  v44[0] = v44;
  v46 = 1;
  v45 = 0;
  if ( *(_BYTE *)(a3 + 29) )
    goto LABEL_23;
  v16 = *((_QWORD *)Src + 59);
  if ( *(_DWORD *)(a3 + 48) == 6 )
  {
    v17 = *(_QWORD *)(*(unsigned int *)(a3 + 80) + *(_QWORD *)(*(_QWORD *)(a3 + 64) + 208LL)) < v16;
  }
  else
  {
    v18 = *(_DWORD **)(a3 + 72);
    if ( !*(_BYTE *)(a3 + 30) )
    {
      if ( *v18 - (int)v16 >= 0 )
        goto LABEL_23;
      goto LABEL_26;
    }
    v17 = *(_QWORD *)v18 < v16;
  }
  if ( !v17 )
  {
LABEL_23:
    if ( *(_DWORD *)(a3 + 48) == 6 )
    {
      v19 = *(_QWORD *)(*(unsigned int *)(a3 + 80) + *(_QWORD *)(*(_QWORD *)(a3 + 64) + 208LL));
    }
    else
    {
      v40 = *(unsigned int **)(a3 + 72);
      if ( *(_BYTE *)(a3 + 30) )
        v19 = *(_QWORD *)v40;
      else
        v19 = *v40;
    }
    WdLogSingleEntry3(4, a3, v19, *((_QWORD *)Src + 59));
    WdLogGlobalForLineNumber = 13770;
    VidSchiAcquirePrivateDataReference(a1, v4);
    v41 = *((_QWORD *)Src + 4);
    if ( v41 )
      _InterlockedAdd((volatile signed __int32 *)(v41 + 12), 1u);
    VidSchiSubmitPresentHistoryToken((unsigned int)&v43, 0, (_DWORD)Src, 0, (__int64)a1);
    goto LABEL_71;
  }
LABEL_26:
  if ( *(_DWORD *)(a3 + 36) == 0x7FFFFFFF )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 13808;
    DxgkLogInternalTriageEvent(
      v20,
      0x40000,
      v21,
      (unsigned int)L"Synchronization object already has LONG_MAX reference pending, can't reference more.\n",
      13808,
      0,
      0,
      0);
    v48 = -1073741823;
  }
  else
  {
    v22 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)a1 + 1024));
    v23 = v22;
    if ( v22 )
    {
      v22[1] = a3;
      v22[2] = *((_QWORD *)Src + 59);
      memmove(v22 + 5, Src, (unsigned int)Src[139]);
      Src[84] = 0;
      Src[154] = 0;
      VidSchiAcquirePrivateDataReference(a1, (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(v23 + 80));
      v26 = v23[9];
      if ( v26 )
        _InterlockedIncrement((volatile signed __int32 *)(v26 + 12));
      v27 = (char *)a1 + 1000;
      v28 = (char **)*((_QWORD *)v27 + 1);
      if ( *v28 != v27 )
        __fastfail(3u);
      v23[3] = v27;
      v23[4] = v28;
      *v28 = (char *)(v23 + 3);
      *((_QWORD *)v27 + 1) = v23 + 3;
      ++*(_DWORD *)(a3 + 44);
      _InterlockedIncrement((volatile signed __int32 *)(a3 + 36));
      if ( *(_DWORD *)(a3 + 48) == 6
        && (!*(_BYTE *)(a3 + 28) || *(_BYTE *)(a3 + 280))
        && (unsigned int)(((2 * *(_DWORD *)(a3 + 52)) >> 1) - 3) > 1 )
      {
        v29 = v23[2];
        v30 = *(_QWORD *)(*(unsigned int *)(a3 + 144) + *(_QWORD *)(*(_QWORD *)(a3 + 128) + 208LL));
        if ( *(_DWORD *)(a3 + 48) == 6 )
        {
          v31 = *(_QWORD *)(*(unsigned int *)(a3 + 80) + *(_QWORD *)(*(_QWORD *)(a3 + 64) + 208LL));
        }
        else
        {
          v32 = *(unsigned int **)(a3 + 72);
          if ( *(_BYTE *)(a3 + 30) )
            v31 = *(_QWORD *)v32;
          else
            v31 = *v32;
        }
        if ( v29 <= v30 || v31 >= v30 )
        {
          if ( *(_BYTE *)(a3 + 28) )
          {
            v33 = *(_QWORD *)(*(_QWORD *)(a3 + 360) + 40LL);
          }
          else
          {
            v34 = *(_DWORD *)(a3 + 48);
            if ( v34 == 2 )
            {
              v33 = *(_QWORD *)(a3 + 72);
            }
            else if ( v34 == 6 )
            {
              v33 = *(_QWORD *)(a3 + 200);
            }
            else
            {
              v33 = *(_QWORD *)(a3 + 96);
            }
          }
          if ( v29 > v33 )
          {
            v37 = *(_QWORD *)(a3 + 8);
            v38 = *(unsigned int *)(a3 + 144);
            v39 = *(_QWORD *)(*(_QWORD *)(a3 + 128) + 208LL);
            if ( *(_BYTE *)(v37 + 7946) )
              *(_QWORD *)(v38 + v39) = v29;
            else
              VidSchiUpdateNativeFenceMonitoredValue(v37, *(_QWORD *)(a3 + 192), v29, v38 + v39);
          }
          else
          {
            if ( *(_BYTE *)(a3 + 28) )
            {
              v35 = *(_QWORD *)(*(_QWORD *)(a3 + 360) + 40LL);
            }
            else
            {
              v36 = *(_DWORD *)(a3 + 48);
              if ( v36 == 2 )
              {
                v35 = *(_QWORD *)(a3 + 72);
              }
              else if ( v36 == 6 )
              {
                v35 = *(_QWORD *)(a3 + 200);
              }
              else
              {
                v35 = *(_QWORD *)(a3 + 96);
              }
            }
            WdLogSingleEntry3(3, a3, v29, v35);
            WdLogGlobalForLineNumber = 6236;
          }
        }
        else
        {
          WdLogSingleEntry4(3, a3, v29, v30, v31);
          WdLogGlobalForLineNumber = 6226;
        }
      }
    }
    else
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 13820;
      DxgkLogInternalTriageEvent(
        v24,
        0x40000,
        v25,
        (unsigned int)L"Failed to allocate VIDSCH_SYNCOBJ_PHT_DATA",
        13820,
        0,
        0,
        0);
      v48 = -1073741801;
    }
  }
LABEL_71:
  HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v43);
  AcquireSpinLock::Release((AcquireSpinLock *)v47);
  return v48;
}

```

## disassembly

```asm
0x1400406e0  push    rbp
0x1400406e2  push    rbx
0x1400406e3  push    rsi
0x1400406e4  push    rdi
0x1400406e5  push    r12
0x1400406e7  push    r13
0x1400406e9  push    r14
0x1400406eb  push    r15
0x1400406ed  lea     rbp, [rsp-1Fh]
0x1400406f2  sub     rsp, 0A8h
0x1400406f9  lea     r13, [rdx+258h]
0x140040700  mov     [rbp+57h+arg_0], 0
0x140040707  mov     eax, [r13+8]
0x14004070b  mov     r12, r9
0x14004070e  add     eax, 1Ch
0x140040711  mov     rbx, r8
0x140040714  imul    eax, [r13+4]
0x140040719  mov     rsi, rdx
0x14004071c  mov     rdi, rcx
0x14004071f  shl     eax, 3
0x140040722  mov     rax, [rax+r13+38h]
0x140040727  test    rax, rax
0x14004072a  jnz     short loc_140040731
0x14004072c  xor     r15d, r15d
0x14004072f  jmp     short loc_140040739
0x140040731  mov     rax, [rax+8]
0x140040735  mov     r15, [rax+20h]
0x140040739  mov     r14d, [rdx+74h]
0x14004073d  or      r8d, 0FFFFFFFFh
0x140040741  test    dword ptr [rdx], 1000000h
0x140040747  jz      short loc_14004077D
0x140040749  cmp     r14d, r8d
0x14004074c  jz      short loc_14004077D
0x14004074e  mov     rcx, [rcx+r14*8+0DC8h]
0x140040756  mov     edx, [rcx+0ADC8h]
0x14004075c  cmp     edx, r8d
0x14004075f  jz      short loc_14004077D
0x140040761  mov     rax, [rdi+0D38h]
0x140040768  test    rax, rax
0x14004076b  jz      short loc_14004077D
0x14004076d  mov     rcx, [rdi+0D78h]
0x140040774  call    _guard_dispatch_icall
0x140040779  or      r8d, 0FFFFFFFFh
0x14004077d  mov     eax, [r12]
0x140040781  bt      eax, 0Ch
0x140040785  jnb     short loc_1400407E4
0x140040787  and     eax, 0C00h
0x14004078c  cmp     eax, 400h
0x140040791  jz      short loc_1400407E4
0x140040793  cmp     r14d, r8d
0x140040796  jz      short loc_1400407E4
0x140040798  mov     eax, [rsi]
0x14004079a  mov     ecx, 1040000h
0x14004079f  and     eax, ecx
0x1400407a1  cmp     eax, ecx
0x1400407a3  jnz     short loc_1400407E4
0x1400407a5  lock inc dword ptr [rdi+370h]
0x1400407ac  mov     edx, r14d; unsigned int
0x1400407af  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x1400407b2  call    ?IncrementNumberOfQueuedFlipPerSource@@YAXPEAU_VIDSCH_GLOBAL@@I@Z; IncrementNumberOfQueuedFlipPerSource(_VIDSCH_GLOBAL *,uint)
0x1400407b7  lock inc dword ptr [r15+72Ch]
0x1400407bf  lock inc dword ptr [r15+r14*4+6ECh]
0x1400407c8  mov     eax, [r15+38h]
0x1400407cc  test    al, 2
0x1400407ce  jnz     short loc_1400407DF
0x1400407d0  cmp     dword ptr [rsi+78h], 4
0x1400407d4  jge     short loc_1400407DF
0x1400407d6  cmp     byte ptr [rdi+0A4h], 0
0x1400407dd  jz      short loc_1400407E4
0x1400407df  call    VidSchIsVSyncEnabled
0x1400407e4  lea     rdx, [rdi+830h]; unsigned __int64 *
0x1400407eb  xor     r9d, r9d; bool
0x1400407ee  mov     r8b, 1; bool
0x1400407f1  lea     rcx, [rbp+57h+var_70]; this
0x1400407f5  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x1400407fa  xor     r12d, r12d
0x1400407fd  mov     [rbp+57h+var_90], rdi
0x140040801  lea     rax, [rbp+57h+var_88]
0x140040805  xorps   xmm0, xmm0
0x140040808  movups  [rbp+57h+var_88], xmm0
0x14004080c  mov     qword ptr [rbp+57h+var_88+8], rax
0x140040810  lea     rax, [rbp+57h+var_88]
0x140040814  lea     r14d, [r12+1]
0x140040819  mov     qword ptr [rbp+57h+var_88], rax
0x14004081d  mov     [rbp+57h+var_74], r14d
0x140040821  mov     [rbp+57h+var_78], r12b
0x140040825  cmp     [rbx+1Dh], r12b
0x140040829  jnz     short loc_140040866
0x14004082b  cmp     dword ptr [rbx+30h], 6
0x14004082f  mov     r8, [rsi+1D8h]
0x140040836  jnz     short loc_14004084F
0x140040838  mov     rax, [rbx+40h]
0x14004083c  mov     edx, [rbx+50h]
0x14004083f  mov     rcx, [rax+0D0h]
0x140040846  mov     rax, [rdx+rcx]
0x14004084a  cmp     rax, r8
0x14004084d  jmp     short loc_14004085F
0x14004084f  mov     rax, [rbx+48h]
0x140040853  cmp     [rbx+1Eh], r12b
0x140040857  jz      short loc_14004088E
0x140040859  mov     rcx, [rax]
0x14004085c  cmp     rcx, r8
0x14004085f  setnb   al
0x140040862  test    al, al
0x140040864  jz      short loc_140040895
0x140040866  cmp     dword ptr [rbx+30h], 6
0x14004086a  mov     r9, [rsi+1D8h]
0x140040871  jnz     loc_140040B3C
0x140040877  mov     rax, [rbx+40h]
0x14004087b  mov     edx, [rbx+50h]
0x14004087e  mov     rcx, [rax+0D0h]
0x140040885  mov     r8, [rdx+rcx]
0x140040889  jmp     loc_140040B4E
0x14004088e  mov     edx, [rax]
0x140040890  cmp     edx, r8d
0x140040893  jns     short loc_140040866
0x140040895  mov     eax, [rbx+24h]
0x140040898  cmp     eax, 7FFFFFFFh
0x14004089d  jnz     short loc_1400408EA
0x14004089f  mov     ecx, r14d
0x1400408a2  call    cs:__imp_WdLogSingleEntry0
0x1400408a9  nop     dword ptr [rax+rax+00h]
0x1400408ae  mov     [rsp+0E0h+var_A8], r12
0x1400408b3  lea     r9, aSynchronizatio; "Synchronization object already has LONG"...
0x1400408ba  mov     eax, 35F0h
0x1400408bf  mov     [rsp+0E0h+var_B0], r12
0x1400408c4  mov     [rsp+0E0h+var_B8], r12
0x1400408c9  mov     edx, 40000h
0x1400408ce  mov     cs:WdLogGlobalForLineNumber, eax
0x1400408d4  mov     [rsp+0E0h+var_C0], rax
0x1400408d9  call    DxgkLogInternalTriageEvent
0x1400408de  mov     [rbp+57h+arg_0], 0C0000001h
0x1400408e5  jmp     loc_140040B9B
0x1400408ea  lea     rcx, [rdi+400h]; Lookaside
0x1400408f1  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400408f8  nop     dword ptr [rax+rax+00h]
0x1400408fd  mov     r14, rax
0x140040900  test    rax, rax
0x140040903  jnz     short loc_140040950
0x140040905  lea     ecx, [rax+1]
0x140040908  call    cs:__imp_WdLogSingleEntry0
0x14004090f  nop     dword ptr [rax+rax+00h]
0x140040914  mov     [rsp+0E0h+var_A8], r12
0x140040919  lea     r9, aFailedToAlloca_104; "Failed to allocate VIDSCH_SYNCOBJ_PHT_D"...
0x140040920  mov     eax, 35FCh
0x140040925  mov     [rsp+0E0h+var_B0], r12
0x14004092a  mov     [rsp+0E0h+var_B8], r12
0x14004092f  mov     edx, 40000h
0x140040934  mov     cs:WdLogGlobalForLineNumber, eax
0x14004093a  mov     [rsp+0E0h+var_C0], rax
0x14004093f  call    DxgkLogInternalTriageEvent
0x140040944  mov     [rbp+57h+arg_0], 0C0000017h
0x14004094b  jmp     loc_140040B9B
0x140040950  mov     [rax+8], rbx
0x140040954  lea     rcx, [r14+28h]; void *
0x140040958  mov     rax, [rsi+1D8h]
0x14004095f  mov     rdx, rsi; Src
0x140040962  mov     [r14+10h], rax
0x140040966  mov     r8d, [rsi+22Ch]; Size
0x14004096d  call    memmove
0x140040972  lea     rdx, [r14+280h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140040979  mov     [rsi+150h], r12d
0x140040980  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x140040983  mov     [rsi+268h], r12d
0x14004098a  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x14004098f  mov     r10, [r14+48h]
0x140040993  test    r10, r10
0x140040996  jz      short loc_14004099D
0x140040998  lock inc dword ptr [r10+0Ch]
0x14004099d  add     rdi, 3E8h
0x1400409a4  mov     rcx, [rdi+8]
0x1400409a8  cmp     [rcx], rdi
0x1400409ab  jz      short loc_1400409B4
0x1400409ad  mov     ecx, 3
0x1400409b2  int     29h; Win8: RtlFailFast(ecx)
0x1400409b4  lea     rax, [r14+18h]
0x1400409b8  mov     [rax], rdi
0x1400409bb  mov     [rax+8], rcx
0x1400409bf  mov     [rcx], rax
0x1400409c2  mov     [rdi+8], rax
0x1400409c6  inc     dword ptr [rbx+2Ch]
0x1400409c9  lock inc dword ptr [rbx+24h]
0x1400409cd  cmp     dword ptr [rbx+30h], 6
0x1400409d1  jnz     loc_140040B9B
0x1400409d7  cmp     [rbx+1Ch], r12b
0x1400409db  jz      short loc_1400409EA
0x1400409dd  cmp     [rbx+118h], r12b
0x1400409e4  jz      loc_140040B9B
0x1400409ea  mov     eax, [rbx+34h]
0x1400409ed  add     eax, eax
0x1400409ef  sar     eax, 1
0x1400409f1  sub     eax, 3
0x1400409f4  cmp     eax, 1
0x1400409f7  jbe     loc_140040B9B
0x1400409fd  mov     rax, [rbx+80h]
0x140040a04  mov     ecx, [rbx+90h]
0x140040a0a  mov     r8, [r14+10h]
0x140040a0e  mov     rax, [rax+0D0h]
0x140040a15  mov     r9, [rcx+rax]
0x140040a19  cmp     dword ptr [rbx+30h], 6
0x140040a1d  jnz     short loc_140040A33
0x140040a1f  mov     rax, [rbx+40h]
0x140040a23  mov     edx, [rbx+50h]
0x140040a26  mov     rcx, [rax+0D0h]
0x140040a2d  mov     rax, [rdx+rcx]
0x140040a31  jmp     short loc_140040A44
0x140040a33  mov     rax, [rbx+48h]
0x140040a37  cmp     [rbx+1Eh], r12b
0x140040a3b  jz      short loc_140040A42
0x140040a3d  mov     rax, [rax]
0x140040a40  jmp     short loc_140040A44
0x140040a42  mov     eax, [rax]
0x140040a44  cmp     r8, r9
0x140040a47  jbe     short loc_140040A76
0x140040a49  cmp     rax, r9
0x140040a4c  jnb     short loc_140040A76
0x140040a4e  mov     rdx, rbx
0x140040a51  mov     [rsp+0E0h+var_C0], rax
0x140040a56  mov     ecx, 3
0x140040a5b  call    cs:__imp_WdLogSingleEntry4
0x140040a62  nop     dword ptr [rax+rax+00h]
0x140040a67  mov     cs:WdLogGlobalForLineNumber, 1852h
0x140040a71  jmp     loc_140040B9B
0x140040a76  cmp     [rbx+1Ch], r12b
0x140040a7a  jz      short loc_140040A89
0x140040a7c  mov     rax, [rbx+168h]
0x140040a83  mov     rcx, [rax+28h]
0x140040a87  jmp     short loc_140040AA9
0x140040a89  mov     eax, [rbx+30h]
0x140040a8c  cmp     eax, 2
0x140040a8f  jnz     short loc_140040A97
0x140040a91  mov     rcx, [rbx+48h]
0x140040a95  jmp     short loc_140040AA9
0x140040a97  cmp     eax, 6
0x140040a9a  jnz     short loc_140040AA5
0x140040a9c  mov     rcx, [rbx+0C8h]
0x140040aa3  jmp     short loc_140040AA9
0x140040aa5  mov     rcx, [rbx+60h]
0x140040aa9  cmp     r8, rcx
0x140040aac  ja      short loc_140040B04
0x140040aae  cmp     [rbx+1Ch], r12b
0x140040ab2  jz      short loc_140040AC1
0x140040ab4  mov     rax, [rbx+168h]
0x140040abb  mov     r9, [rax+28h]
0x140040abf  jmp     short loc_140040AE1
0x140040ac1  mov     eax, [rbx+30h]
0x140040ac4  cmp     eax, 2
0x140040ac7  jnz     short loc_140040ACF
0x140040ac9  mov     r9, [rbx+48h]
0x140040acd  jmp     short loc_140040AE1
0x140040acf  cmp     eax, 6
0x140040ad2  jnz     short loc_140040ADD
0x140040ad4  mov     r9, [rbx+0C8h]
0x140040adb  jmp     short loc_140040AE1
0x140040add  mov     r9, [rbx+60h]
0x140040ae1  mov     rdx, rbx
0x140040ae4  mov     ecx, 3
0x140040ae9  call    cs:__imp_WdLogSingleEntry3
0x140040af0  nop     dword ptr [rax+rax+00h]
0x140040af5  mov     cs:WdLogGlobalForLineNumber, 185Ch
0x140040aff  jmp     loc_140040B9B
0x140040b04  mov     rcx, [rbx+8]
0x140040b08  mov     rax, [rbx+80h]
0x140040b0f  mov     edx, [rbx+90h]
0x140040b15  mov     r9, [rax+0D0h]
0x140040b1c  cmp     [rcx+1F0Ah], r12b
0x140040b23  jnz     short loc_140040B36
0x140040b25  add     r9, rdx
0x140040b28  mov     rdx, [rbx+0C0h]
0x140040b2f  call    VidSchiUpdateNativeFenceMonitoredValue
0x140040b34  jmp     short loc_140040B9B
0x140040b36  mov     [rdx+r9], r8
0x140040b3a  jmp     short loc_140040B9B
0x140040b3c  mov     rax, [rbx+48h]
0x140040b40  cmp     [rbx+1Eh], r12b
0x140040b44  jz      short loc_140040B4B
0x140040b46  mov     r8, [rax]
0x140040b49  jmp     short loc_140040B4E
0x140040b4b  mov     r8d, [rax]
0x140040b4e  mov     rdx, rbx
0x140040b51  mov     ecx, 4
0x140040b56  call    cs:__imp_WdLogSingleEntry3
0x140040b5d  nop     dword ptr [rax+rax+00h]
0x140040b62  mov     rdx, r13; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140040b65  mov     cs:WdLogGlobalForLineNumber, 35CAh
0x140040b6f  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x140040b72  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140040b77  mov     r10, [rsi+20h]
0x140040b7b  test    r10, r10
0x140040b7e  jz      short loc_140040B85
0x140040b80  lock add [r10+0Ch], r14d
0x140040b85  mov     r9, r12
0x140040b88  mov     [rsp+0E0h+var_C0], rdi
0x140040b8d  mov     r8, rsi
0x140040b90  lea     rcx, [rbp+57h+var_90]
0x140040b94  xor     edx, edx
0x140040b96  call    VidSchiSubmitPresentHistoryToken
0x140040b9b  lea     rcx, [rbp+57h+var_90]; this
0x140040b9f  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x140040ba4  lea     rcx, [rbp+57h+var_70]; this
  ... truncated ...
```
