# CscDclMRxSetPinInformation

- ea: `0x14008caec`
- end: `0x14008d2fc`
- name: `CscDclMRxSetPinInformation`
- size: `2064`
- prototype: `__int64 __fastcall(struct _MRX_FCB_ *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14007ae70`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x140004e6c`
- `0x14000a634`
- `0x14000dfc0`
- `0x14000e030`
- `0x14000e100`
- `0x1400111f8`
- `0x140012118`
- `0x14001404c`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x140019204`
- `0x14001958c`
- `0x14001a69c`
- `0x14001ac70`
- `0x14001b710`
- `0x14001baf4`
- `0x140022ed8`
- `0x1400232fc`
- `0x14002f010`
- `0x140075b10`
- `0x140081428`
- `0x140087e94`
- `0x14008caec`

## import_xrefs

- `rdbss!RxInitNetInfoFromFcb` at `0x14008cd5f`
- `rdbss!RxInitNetInfoFromFcb` at `0x14008cd5f`
- `rdbss!RxAcquirePowerContextLock` at `0x14008d202`
- `rdbss!RxAcquirePowerContextLock` at `0x14008d202`
- `rdbss!RxFcbTableNameFromFcb` at `0x14008cd49`
- `rdbss!RxFcbTableNameFromFcb` at `0x14008cd49`
- `rdbss!RxUpdateFcbPowerState` at `0x14008d228`
- `rdbss!RxUpdateFcbPowerState` at `0x14008d228`
- `rdbss!RxReleasePowerContextLock` at `0x14008d234`
- `rdbss!RxReleasePowerContextLock` at `0x14008d234`

## pseudocode

```c
__int64 __fastcall CscDclMRxSetPinInformation(struct _MRX_FCB_ *a1, __int64 a2, unsigned __int8 *a3)
{
  __int64 Blink; // rsi
  struct _LIST_ENTRY *Flink; // r13
  char v8; // r14
  int v9; // r9d
  int v10; // ecx
  int v11; // r10d
  int DatabaseInformation; // esi
  int v13; // r14d
  __int64 v14; // r12
  unsigned __int8 v15; // al
  int v16; // ecx
  unsigned __int8 v17; // dl
  char v18; // al
  __int64 v19; // rdi
  const UNICODE_STRING *String2; // r14
  __int64 v21; // rcx
  int v22; // r15d
  struct _LIST_ENTRY *v23; // rcx
  bool v24; // bl
  bool v25; // cf
  PMRX_FCB v26; // rbx
  struct _LIST_ENTRY *v27; // r15
  unsigned int v28; // eax
  char v30; // bl
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  char v34; // al
  struct _LIST_ENTRY *v35; // rcx
  int Flink_high; // ebx
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // [rsp+40h] [rbp-C0h] BYREF
  char v40; // [rsp+48h] [rbp-B8h]
  char v41[3]; // [rsp+49h] [rbp-B7h] BYREF
  __int16 v42; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _LIST_ENTRY *v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  PMRX_FCB Fcb; // [rsp+68h] [rbp-98h]
  _OWORD v47[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  _OWORD v50[3]; // [rsp+A8h] [rbp-58h] BYREF
  int v51; // [rsp+D8h] [rbp-28h]
  int v52[4]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v53[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+120h] [rbp+20h]

  Blink = (__int64)a1->Header.FilterContexts.Blink;
  Flink = a1->Header.FilterContexts.Flink;
  v49 = a2;
  Fcb = a1;
  v45 = *(_QWORD *)(Blink + 32);
  v48 = Blink;
  v47[0] = 0;
  v43 = 0;
  v8 = 0;
  *(_OWORD *)v52 = 0;
  v54 = 0;
  memset(v53, 0, sizeof(v53));
  v44 = 0;
  v51 = 0;
  memset(v50, 0, sizeof(v50));
  LOBYTE(v39) = 0;
  v41[0] = 0;
  v42 = 0;
  HIDWORD(v39) = 0;
  CscGetContexts(a1, v47);
  LOBYTE(v9) = 1;
  CscUpdateAndCaptureConnectionStateEx((_DWORD)Flink, v11, v10, v9, (__int64)v52, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      a2,
      a3[3],
      a3[1],
      a3[2],
      *a3,
      v39);
  if ( (v52[0] & 0x4000) != 0 )
  {
    DatabaseInformation = CscDetermineAbortStatus(v52);
    v13 = 2431;
    goto LABEL_63;
  }
  if ( !Flink[8].Flink )
  {
    DatabaseInformation = -1073741811;
    v13 = 2437;
    goto LABEL_63;
  }
  if ( a2 )
    v14 = a2;
  else
    v14 = *(_QWORD *)(*(_QWORD *)(Blink + 32) + 40LL) + 112LL;
  DatabaseInformation = CscStoreQueryDatabaseInformation(v50, 0, 0, 0);
  if ( DatabaseInformation < 0 )
  {
    v13 = 2463;
    goto LABEL_63;
  }
  v15 = a3[1];
  v16 = *(_DWORD *)a3;
  v17 = a3[3];
  v40 = 0;
  HIDWORD(v39) = v16;
  if ( (v15 & 2) != 0 )
  {
    LOBYTE(v16) = BYTE1(v16) | 1;
    BYTE5(v39) = BYTE1(v16) | 1;
  }
  else
  {
    LOBYTE(v16) = BYTE5(v39);
  }
  if ( (v15 & 8) != 0 )
  {
    LOBYTE(v16) = v16 | 4;
    BYTE5(v39) = v16;
  }
  v18 = HIBYTE(v39);
  if ( (v17 & 2) != 0 )
  {
    v18 = HIBYTE(v39) | 1;
    HIBYTE(v39) |= 1u;
  }
  if ( (v17 & 8) != 0 )
  {
    v18 |= 4u;
    HIBYTE(v39) = v18;
  }
  if ( (v17 & 0x20) != 0 )
  {
    v18 |= 0x10u;
    HIBYTE(v39) = v18;
  }
  if ( LOWORD(Flink->Flink) == 0xEC22 )
  {
    LOBYTE(v16) = v16 & 0xF5;
    v18 &= 0xD5u;
    BYTE5(v39) = v16;
    HIBYTE(v39) = v18;
  }
  if ( (v52[0] & 0x20) != 0 )
  {
    v19 = *((_QWORD *)&v47[0] + 1);
    v27 = *(struct _LIST_ENTRY **)(*((_QWORD *)&v47[0] + 1) + 56LL);
    v43 = v27;
  }
  else
  {
    if ( (v52[0] & 4) == 0 || (v19 = *((_QWORD *)&v47[0] + 1)) == 0 )
    {
      DatabaseInformation = -1073741790;
      v13 = 2503;
      goto LABEL_63;
    }
    if ( !(_BYTE)v16 && !v18 )
    {
      DatabaseInformation = 0;
      v13 = 2516;
      goto LABEL_63;
    }
    DatabaseInformation = CscFcbForceFlowOpens(a1, Flink);
    if ( DatabaseInformation < 0 )
    {
      v13 = 2531;
      goto LABEL_63;
    }
    String2 = (const UNICODE_STRING *)RxFcbTableNameFromFcb(Flink);
    RxInitNetInfoFromFcb(Flink, v53);
    v21 = (__int64)Flink[8].Flink;
    v22 = (LOBYTE(v52[0]) >> 4) & 1;
    if ( *(_QWORD *)(v21 + 48) )
    {
      CscAcquireLViewLock(v21);
      v23 = Flink[8].Flink;
      v24 = (HIDWORD(v23[3].Flink->Flink) & 0x1000) != 0;
      LOBYTE(v39) = (HIDWORD(v23[3].Flink->Flink) & 8) != 0;
      CscReleaseLViewLock(v23);
    }
    else
    {
      v24 = 0;
    }
    v25 = v24;
    v26 = Fcb;
    DatabaseInformation = CscUpdateShareInfoForLogicalView(
                            (int)Fcb,
                            v22 + 3,
                            v14,
                            v52[3],
                            (unsigned __int64)&v39 & -(__int64)v25,
                            String2,
                            (__int64)&v44,
                            0);
    if ( DatabaseInformation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_ZD(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          (unsigned int)WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
          (_DWORD)String2,
          DatabaseInformation);
      v13 = 2593;
      goto LABEL_63;
    }
    DatabaseInformation = CscStoreFindOrCreatePinnedEntry(
                            (unsigned int)&v43,
                            (unsigned int)&v44 + 4,
                            (_DWORD)String2,
                            v22 + 3,
                            (__int64)v53,
                            (__int64)&v39 + 4);
    if ( DatabaseInformation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_ZD(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          (unsigned int)WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
          (_DWORD)String2,
          DatabaseInformation);
      v27 = v43;
      v13 = 2608;
      goto LABEL_58;
    }
    v8 = BYTE4(v44) | v44;
    v27 = v43;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
        v43,
        Flink,
        v45);
    v40 = 1;
    if ( (v8 & 2) != 0 )
    {
      v28 = CscBumpGlobalNewlyCachedEpoch();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids, v28);
    }
    if ( !*(_QWORD *)&v47[0] )
    {
      DatabaseInformation = CscCreateAndInitializeFobxContext(v48, v47, (2 * ((v52[0] & 0x10) == 0)) | 1u, 0);
      if ( DatabaseInformation )
      {
        v13 = 2652;
        goto LABEL_58;
      }
      v19 = *((_QWORD *)&v47[0] + 1);
      if ( (v52[0] & 0x10) == 0 )
        *(_QWORD *)(*(_QWORD *)&v47[0] + 64LL) = *(_QWORD *)(*((_QWORD *)v26->Header.FileContextSupportPointer + 44)
                                                           + 144LL);
    }
  }
  if ( (v8 & 1) == 0 || v49 )
    goto LABEL_78;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      *(unsigned int *)(v45 + 152));
  DatabaseInformation = CscStoreSetExplicitAccessEntry((_DWORD)v27, 0, v14, *(_DWORD *)(v45 + 152), 3);
  if ( DatabaseInformation >= 0 )
  {
LABEL_78:
    if ( (v50[0] & 1) != 0 )
    {
      LOBYTE(v39) = 0;
      DatabaseInformation = CscStoreQueryCanSidDecryptEntry(v27, v14, &v39);
      if ( DatabaseInformation < 0 )
      {
        v13 = 2708;
        goto LABEL_58;
      }
      if ( !(_BYTE)v39 )
      {
        DatabaseInformation = -1073741165;
        v13 = 2715;
        goto LABEL_58;
      }
    }
    DatabaseInformation = CscStoreSetPinInformationEntry(v27, v14, (char *)&v39 + 4, &v42);
    if ( DatabaseInformation >= 0 )
    {
      v13 = 0;
      v30 = v42 | HIBYTE(v42);
      if ( !v42 && LOWORD(Flink->Flink) != 0xEC21 )
        *(_DWORD *)(v19 + 4) |= 0x20000u;
      if ( !BYTE5(v39) && !HIBYTE(v39) )
        goto LABEL_96;
      *(_DWORD *)(v19 + 4) &= ~0x20000u;
      if ( (*(_DWORD *)(v19 + 4) & 0x800) != 0 )
      {
        LOBYTE(v39) = 0;
        DatabaseInformation = CscStoreSetInformationEntry((__int64)v27, 0, 0, 0, 0, &v39, 0);
      }
      *(_DWORD *)(v19 + 4) = *(_DWORD *)(v19 + 4) & 0xFCFFFF7F | 0x80;
      if ( (v52[0] & 0x20) == 0 )
      {
        v40 = 0;
        v31 = CscApplyStoreHandleToFcbOrDeref(Fcb, v27);
        v27 = 0;
        DatabaseInformation = v31;
        v43 = 0;
      }
      if ( !BYTE5(v39) && !HIBYTE(v39) )
      {
LABEL_96:
        RxAcquirePowerContextLock();
        v34 = BYTE2(Flink[17].Blink);
        if ( (v34 & 1) != 0 )
        {
          LOBYTE(v32) = 1;
          LOBYTE(v33) = 4;
          if ( v34 >= 0 )
            LOBYTE(v33) = 2;
          RxUpdateFcbPowerState(Flink, v32, v33);
        }
        RxReleasePowerContextLock();
      }
      if ( *(_QWORD *)(v19 + 56) )
      {
        if ( v30 )
        {
          CscAcquireLViewLock((__int64)Flink[8].Flink);
          v35 = Flink[8].Flink;
          Flink_high = HIDWORD(v35[3].Flink->Flink);
          CscReleaseLViewLock(v35);
          if ( (Flink_high & 0x4000) == 0 && (int)CscStoreIsScopePartlyPinned(*(_QWORD *)(v19 + 56), v41) >= 0 )
          {
            if ( v41[0] )
            {
              v37 = (__int64)Flink[8].Flink;
              v38 = *(_QWORD *)(v37 + 48);
              CscAcquireLViewLock(v37);
              *(_DWORD *)(v38 + 4) |= 0x4000u;
              CscReleaseLViewLock(v37);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids);
              }
            }
          }
        }
      }
    }
    else
    {
      v13 = 2733;
    }
  }
  else
  {
    v13 = 2690;
  }
LABEL_58:
  if ( v27 && v40 )
  {
    CscStoreDereferenceEntry(&v43);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)DatabaseInformation;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
        v43,
        Flink,
        v45);
  }
LABEL_63:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      (unsigned int)DatabaseInformation,
      v13);
  return (unsigned int)DatabaseInformation;
}

```

## disassembly

```asm
0x14008caec  mov     [rsp-8+arg_18], rbx
0x14008caf1  push    rbp
0x14008caf2  push    rsi
0x14008caf3  push    rdi
0x14008caf4  push    r12
0x14008caf6  push    r13
0x14008caf8  push    r14
0x14008cafa  push    r15
0x14008cafc  lea     rbp, [rsp-30h]
0x14008cb01  sub     rsp, 130h
0x14008cb08  mov     rax, cs:__security_cookie
0x14008cb0f  xor     rax, rsp
0x14008cb12  mov     [rbp+60h+var_38], rax
0x14008cb16  mov     rsi, [rcx+40h]
0x14008cb1a  xorps   xmm0, xmm0
0x14008cb1d  mov     r13, [rcx+38h]
0x14008cb21  xor     r12d, r12d
0x14008cb24  xor     eax, eax
0x14008cb26  mov     [rbp+60h+var_C0], rdx
0x14008cb2a  mov     rdi, rdx
0x14008cb2d  mov     [rsp+160h+Fcb], rcx
0x14008cb32  mov     r10, [rsi+20h]
0x14008cb36  lea     rdx, [rsp+160h+var_F0]
0x14008cb3b  mov     [rsp+160h+var_100], r10
0x14008cb40  mov     rbx, r8
0x14008cb43  mov     r15, rcx
0x14008cb46  mov     [rbp+60h+var_C8], rsi
0x14008cb4a  movups  [rsp+160h+var_F0], xmm0
0x14008cb4f  mov     [rsp+160h+var_110], r12
0x14008cb54  mov     r14d, r12d
0x14008cb57  movups  xmmword ptr [rbp+60h+var_80], xmm0
0x14008cb5b  mov     [rbp+60h+var_40], rax
0x14008cb5f  movups  [rbp+60h+var_70], xmm0
0x14008cb63  mov     dword ptr [rsp+160h+var_108], r12d
0x14008cb68  movups  [rbp+60h+var_60], xmm0
0x14008cb6c  mov     dword ptr [rsp+160h+var_108+4], r12d
0x14008cb71  movups  [rbp+60h+var_50], xmm0
0x14008cb75  mov     [rbp+60h+var_88], eax
0x14008cb78  movups  [rbp+60h+var_B8], xmm0
0x14008cb7c  mov     [rsp+160h+var_120], r12b
0x14008cb81  movups  [rbp+60h+var_A8], xmm0
0x14008cb85  mov     [rsp+160h+var_117], r12b
0x14008cb8a  movups  [rbp+60h+var_98], xmm0
0x14008cb8e  mov     [rsp+160h+var_114], r12w
0x14008cb94  mov     [rsp+160h+var_11C], r12d
0x14008cb99  call    CscGetContexts
0x14008cb9e  lea     rax, [rbp+60h+var_80]
0x14008cba2  mov     byte ptr [rsp+160h+String2], 1
0x14008cba7  mov     r8, rcx
0x14008cbaa  mov     [rsp+160h+var_140], rax
0x14008cbaf  mov     rcx, r13
0x14008cbb2  mov     r9b, 1
0x14008cbb5  mov     rdx, r10
0x14008cbb8  call    CscUpdateAndCaptureConnectionStateEx
0x14008cbbd  mov     r10, cs:WPP_GLOBAL_Control
0x14008cbc4  lea     rax, WPP_GLOBAL_Control
0x14008cbcb  cmp     r10, rax
0x14008cbce  jz      short loc_14008CC13
0x14008cbd0  mov     eax, [r10+2Ch]
0x14008cbd4  test    al, 20h
0x14008cbd6  jz      short loc_14008CC13
0x14008cbd8  movzx   ecx, byte ptr [rbx+2]
0x14008cbdc  lea     edx, [r12+2Ah]
0x14008cbe1  movzx   r8d, byte ptr [rbx+1]
0x14008cbe6  movzx   r9d, byte ptr [rbx+3]
0x14008cbeb  movzx   eax, byte ptr [rbx]
0x14008cbee  mov     dword ptr [rsp+160h+var_128], eax
0x14008cbf2  mov     dword ptr [rsp+160h+var_130], ecx
0x14008cbf6  mov     rcx, [r10+18h]
0x14008cbfa  mov     dword ptr [rsp+160h+String2], r8d
0x14008cbff  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14008cc06  mov     dword ptr [rsp+160h+var_140], r9d
0x14008cc0b  mov     r9, rdi
0x14008cc0e  call    WPP_SF_qDDDD
0x14008cc13  test    byte ptr [rbp+60h+var_80+1], 40h
0x14008cc17  jz      short loc_14008CC36
0x14008cc19  lea     rcx, [rbp+60h+var_80]
0x14008cc1d  call    CscDetermineAbortStatus
0x14008cc22  mov     esi, eax
0x14008cc24  mov     r14d, 97Fh
0x14008cc2a  lea     rbx, WPP_GLOBAL_Control
0x14008cc31  jmp     loc_14008CFD7
0x14008cc36  cmp     [r13+80h], r12
0x14008cc3d  jnz     short loc_14008CC4C
0x14008cc3f  mov     esi, 0C000000Dh
0x14008cc44  mov     r14d, 985h
0x14008cc4a  jmp     short loc_14008CC2A
0x14008cc4c  test    rdi, rdi
0x14008cc4f  jnz     short loc_14008CC5F
0x14008cc51  mov     rax, [rsi+20h]
0x14008cc55  mov     r12, [rax+28h]
0x14008cc59  add     r12, 70h ; 'p'
0x14008cc5d  jmp     short loc_14008CC62
0x14008cc5f  mov     r12, rdi
0x14008cc62  xor     r9d, r9d
0x14008cc65  lea     rcx, [rbp+60h+var_B8]
0x14008cc69  xor     r8d, r8d
0x14008cc6c  xor     edx, edx
0x14008cc6e  call    CscStoreQueryDatabaseInformation
0x14008cc73  mov     esi, eax
0x14008cc75  test    eax, eax
0x14008cc77  jns     short loc_14008CC81
0x14008cc79  mov     r14d, 99Fh
0x14008cc7f  jmp     short loc_14008CC2A
0x14008cc81  mov     al, [rbx+1]
0x14008cc84  mov     ecx, [rbx]
0x14008cc86  mov     dl, [rbx+3]
0x14008cc89  mov     [rsp+160h+var_118], r14b
0x14008cc8e  mov     [rsp+160h+var_11C], ecx
0x14008cc92  test    al, 2
0x14008cc94  jz      short loc_14008CCA2
0x14008cc96  shr     ecx, 8
0x14008cc99  or      cl, 1
0x14008cc9c  mov     byte ptr [rsp+160h+var_11C+1], cl
0x14008cca0  jmp     short loc_14008CCA6
0x14008cca2  mov     cl, byte ptr [rsp+160h+var_11C+1]
0x14008cca6  mov     r8b, 4
0x14008cca9  test    al, 8
0x14008ccab  jz      short loc_14008CCB4
0x14008ccad  or      cl, r8b
0x14008ccb0  mov     byte ptr [rsp+160h+var_11C+1], cl
0x14008ccb4  mov     al, byte ptr [rsp+160h+var_11C+3]
0x14008ccb8  test    dl, 2
0x14008ccbb  jz      short loc_14008CCC3
0x14008ccbd  or      al, 1
0x14008ccbf  mov     byte ptr [rsp+160h+var_11C+3], al
0x14008ccc3  test    dl, 8
0x14008ccc6  jz      short loc_14008CCCF
0x14008ccc8  or      al, r8b
0x14008cccb  mov     byte ptr [rsp+160h+var_11C+3], al
0x14008cccf  test    dl, 20h
0x14008ccd2  jz      short loc_14008CCDA
0x14008ccd4  or      al, 10h
0x14008ccd6  mov     byte ptr [rsp+160h+var_11C+3], al
0x14008ccda  mov     edx, 0EC22h
0x14008ccdf  cmp     [r13+0], dx
0x14008cce4  jnz     short loc_14008CCF3
0x14008cce6  and     cl, 0F5h
0x14008cce9  and     al, 0D5h
0x14008cceb  mov     byte ptr [rsp+160h+var_11C+1], cl
0x14008ccef  mov     byte ptr [rsp+160h+var_11C+3], al
0x14008ccf3  test    byte ptr [rbp+60h+var_80], 20h
0x14008ccf7  jnz     loc_14008D070
0x14008ccfd  test    byte ptr [rbp+60h+var_80], r8b
0x14008cd01  jz      loc_14008D060
0x14008cd07  mov     rdi, qword ptr [rsp+160h+var_F0+8]
0x14008cd0c  test    rdi, rdi
0x14008cd0f  jz      loc_14008D060
0x14008cd15  test    cl, cl
0x14008cd17  jnz     short loc_14008CD2A
0x14008cd19  test    al, al
0x14008cd1b  jnz     short loc_14008CD2A
0x14008cd1d  xor     esi, esi
0x14008cd1f  mov     r14d, 9D4h
0x14008cd25  jmp     loc_14008CC2A
0x14008cd2a  mov     rdx, r13
0x14008cd2d  mov     rcx, r15
0x14008cd30  call    CscFcbForceFlowOpens
0x14008cd35  mov     esi, eax
0x14008cd37  test    eax, eax
0x14008cd39  jns     short loc_14008CD46
0x14008cd3b  mov     r14d, 9E3h
0x14008cd41  jmp     loc_14008CC2A
0x14008cd46  mov     rcx, r13
0x14008cd49  call    cs:__imp_RxFcbTableNameFromFcb
0x14008cd50  nop     dword ptr [rax+rax+00h]
0x14008cd55  lea     rdx, [rbp+60h+var_70]
0x14008cd59  mov     rcx, r13
0x14008cd5c  mov     r14, rax
0x14008cd5f  call    cs:__imp_RxInitNetInfoFromFcb
0x14008cd66  nop     dword ptr [rax+rax+00h]
0x14008cd6b  movzx   r15d, byte ptr [rbp+60h+var_80]
0x14008cd70  mov     rcx, [r13+80h]
0x14008cd77  shr     r15d, 4
0x14008cd7b  and     r15d, 1
0x14008cd7f  cmp     qword ptr [rcx+30h], 0
0x14008cd84  jz      short loc_14008CDB1
0x14008cd86  call    CscAcquireLViewLock
0x14008cd8b  mov     rcx, [r13+80h]
0x14008cd92  mov     rax, [rcx+30h]
0x14008cd96  mov     ebx, [rax+4]
0x14008cd99  mov     eax, ebx
0x14008cd9b  shr     eax, 3
0x14008cd9e  shr     ebx, 0Ch
0x14008cda1  and     al, 1
0x14008cda3  and     bl, 1
0x14008cda6  mov     [rsp+160h+var_120], al
0x14008cdaa  call    CscReleaseLViewLock
0x14008cdaf  jmp     short loc_14008CDB3
0x14008cdb1  xor     bl, bl
0x14008cdb3  mov     r9d, [rbp+60h+var_80+0Ch]; int
0x14008cdb7  lea     rcx, [rsp+160h+var_120]
0x14008cdbc  mov     [rsp+160h+var_128], 0; __int64
0x14008cdc5  lea     edx, [r15+3]; int
0x14008cdc9  neg     bl
0x14008cdcb  mov     r8, r12; int
0x14008cdce  mov     rbx, [rsp+160h+Fcb]
0x14008cdd3  sbb     rax, rax
0x14008cdd6  and     rax, rcx
0x14008cdd9  lea     rcx, [rsp+160h+var_108]
0x14008cdde  mov     [rsp+160h+var_130], rcx; __int64
0x14008cde3  mov     rcx, rbx; int
0x14008cde6  mov     [rsp+160h+String2], r14; String2
0x14008cdeb  mov     [rsp+160h+var_140], rax; __int64
0x14008cdf0  call    CscUpdateShareInfoForLogicalView
0x14008cdf5  mov     esi, eax
0x14008cdf7  test    eax, eax
0x14008cdf9  jns     short loc_14008CE3C
0x14008cdfb  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce02  lea     rbx, WPP_GLOBAL_Control
0x14008ce09  cmp     rcx, rbx
0x14008ce0c  jz      short loc_14008CE31
0x14008ce0e  mov     eax, [rcx+2Ch]
0x14008ce11  test    al, 40h
0x14008ce13  jz      short loc_14008CE31
0x14008ce15  mov     rcx, [rcx+18h]
0x14008ce19  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14008ce20  mov     edx, 2Bh ; '+'
0x14008ce25  mov     dword ptr [rsp+160h+var_140], esi
0x14008ce29  mov     r9, r14
0x14008ce2c  call    WPP_SF_ZD
0x14008ce31  mov     r14d, 0A21h
0x14008ce37  jmp     loc_14008CFD7
0x14008ce3c  lea     rax, [rsp+160h+var_11C]
0x14008ce41  mov     r8, r14
0x14008ce44  mov     [rsp+160h+String2], rax
0x14008ce49  lea     r9d, [r15+3]
0x14008ce4d  lea     rax, [rbp+60h+var_70]
0x14008ce51  lea     rdx, [rsp+160h+var_108+4]
0x14008ce56  mov     [rsp+160h+var_140], rax
0x14008ce5b  lea     rcx, [rsp+160h+var_110]
0x14008ce60  call    CscStoreFindOrCreatePinnedEntry
0x14008ce65  mov     esi, eax
0x14008ce67  test    eax, eax
0x14008ce69  jns     short loc_14008CEB1
0x14008ce6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce72  lea     rbx, WPP_GLOBAL_Control
0x14008ce79  cmp     rcx, rbx
0x14008ce7c  jz      short loc_14008CEA1
0x14008ce7e  mov     eax, [rcx+2Ch]
0x14008ce81  test    al, 40h
0x14008ce83  jz      short loc_14008CEA1
0x14008ce85  mov     rcx, [rcx+18h]
0x14008ce89  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14008ce90  mov     edx, 2Ch ; ','
0x14008ce95  mov     dword ptr [rsp+160h+var_140], esi
0x14008ce99  mov     r9, r14
0x14008ce9c  call    WPP_SF_ZD
0x14008cea1  mov     r15, [rsp+160h+var_110]
0x14008cea6  mov     r14d, 0A30h
0x14008ceac  jmp     loc_14008CF85
0x14008ceb1  mov     r14d, dword ptr [rsp+160h+var_108]
0x14008ceb6  or      r14d, dword ptr [rsp+160h+var_108+4]
0x14008cebb  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cec2  lea     rsi, WPP_GLOBAL_Control
0x14008cec9  mov     r15, [rsp+160h+var_110]
0x14008cece  cmp     rcx, rsi
0x14008ced1  jz      short loc_14008CF01
0x14008ced3  mov     eax, [rcx+2Ch]
0x14008ced6  test    al, 40h
0x14008ced8  jz      short loc_14008CF01
0x14008ceda  mov     rax, [rsp+160h+var_100]
0x14008cedf  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14008cee6  mov     rcx, [rcx+18h]
0x14008ceea  mov     edx, 2Dh ; '-'
0x14008ceef  mov     [rsp+160h+String2], rax
0x14008cef4  mov     r9, r15
0x14008cef7  mov     [rsp+160h+var_140], r13
0x14008cefc  call    WPP_SF_qqq
0x14008cf01  mov     [rsp+160h+var_118], 1
0x14008cf06  test    r14b, 2
0x14008cf0a  jz      short loc_14008CF3E
0x14008cf0c  call    CscBumpGlobalNewlyCachedEpoch
0x14008cf11  mov     r10, cs:WPP_GLOBAL_Control
0x14008cf18  cmp     r10, rsi
0x14008cf1b  jz      short loc_14008CF3E
0x14008cf1d  mov     ecx, [r10+2Ch]
0x14008cf21  test    cl, 40h
0x14008cf24  jz      short loc_14008CF3E
0x14008cf26  mov     rcx, [r10+18h]
0x14008cf2a  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14008cf31  mov     edx, 2Eh ; '.'
0x14008cf36  mov     r9d, eax
0x14008cf39  call    WPP_SF_d
0x14008cf3e  cmp     qword ptr [rsp+160h+var_F0], 0
0x14008cf44  jnz     loc_14008D085
0x14008cf4a  mov     al, byte ptr [rbp+60h+var_80]
0x14008cf4d  lea     rdx, [rsp+160h+var_F0]
0x14008cf52  mov     rcx, [rbp+60h+var_C8]
0x14008cf56  xor     r9d, r9d
0x14008cf59  shr     al, 4
0x14008cf5c  not     al
0x14008cf5e  and     eax, 1
0x14008cf61  lea     r8d, [rax+rax]
0x14008cf65  or      r8d, 1
0x14008cf69  call    CscCreateAndInitializeFobxContext
0x14008cf6e  mov     esi, eax
0x14008cf70  test    eax, eax
0x14008cf72  jz      loc_14008D031
0x14008cf78  mov     r14d, 0A5Ch
  ... truncated ...
```
