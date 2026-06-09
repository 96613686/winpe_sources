# CscDclMRxSetPinInformation

- ea: `0x14008caec`
- end: `0x14008d2fc`
- name: `CscDclMRxSetPinInformation`
- size: `2064`
- prototype: `__int64 __fastcall(struct _MRX_FCB_ *, __int64, unsigned __int8 *, __int64)`
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
__int64 __fastcall CscDclMRxSetPinInformation(struct _MRX_FCB_ *a1, __int64 a2, unsigned __int8 *a3, __int64 a4)
{
  struct _LIST_ENTRY *Blink; // rsi
  struct _LIST_ENTRY *Flink; // r13
  char v9; // r14
  int v10; // r9d
  int v11; // ecx
  int v12; // r10d
  int DatabaseInformation; // esi
  int v14; // r14d
  __int64 v15; // r12
  __int64 v16; // r8
  unsigned __int8 v17; // al
  int v18; // ecx
  unsigned __int8 v19; // dl
  char v20; // al
  __int64 v21; // rdi
  const UNICODE_STRING *String2; // r14
  struct _LIST_ENTRY *v23; // rcx
  int v24; // r15d
  struct _LIST_ENTRY *v25; // rcx
  bool v26; // bl
  bool v27; // cf
  PMRX_FCB v28; // rbx
  __int64 v29; // r15
  unsigned int v30; // eax
  char v32; // bl
  __int64 v33; // rdx
  __int64 v34; // r8
  char v35; // al
  struct _LIST_ENTRY *v36; // rcx
  int Flink_high; // ebx
  struct _LIST_ENTRY *v38; // rdi
  struct _LIST_ENTRY *v39; // rbx
  _BYTE v40[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+44h] [rbp-BCh] BYREF
  char v42; // [rsp+48h] [rbp-B8h]
  char v43[3]; // [rsp+49h] [rbp-B7h] BYREF
  __int16 v44; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  struct _LIST_ENTRY *v47; // [rsp+60h] [rbp-A0h]
  PMRX_FCB Fcb; // [rsp+68h] [rbp-98h]
  _OWORD v49[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _LIST_ENTRY *v50; // [rsp+98h] [rbp-68h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  _OWORD v52[3]; // [rsp+A8h] [rbp-58h] BYREF
  int v53; // [rsp+D8h] [rbp-28h]
  int v54[4]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v55[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v56; // [rsp+120h] [rbp+20h]

  Blink = a1->Header.FilterContexts.Blink;
  Flink = a1->Header.FilterContexts.Flink;
  v51 = a2;
  Fcb = a1;
  v47 = Blink[2].Flink;
  v50 = Blink;
  v49[0] = 0;
  v45 = 0;
  v9 = 0;
  *(_OWORD *)v54 = 0;
  v56 = 0;
  memset(v55, 0, sizeof(v55));
  v46 = 0;
  v53 = 0;
  memset(v52, 0, sizeof(v52));
  v40[0] = 0;
  v43[0] = 0;
  v44 = 0;
  v41 = 0;
  CscGetContexts(a1, v49, a3, a4);
  LOBYTE(v10) = 1;
  CscUpdateAndCaptureConnectionStateEx((_DWORD)Flink, v12, v11, v10, (__int64)v54, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      a2,
      a3[3],
      a3[1],
      a3[2],
      *a3);
  if ( (v54[0] & 0x4000) != 0 )
  {
    DatabaseInformation = CscDetermineAbortStatus(v54);
    v14 = 2431;
    goto LABEL_62;
  }
  if ( !Flink[8].Flink )
  {
    DatabaseInformation = -1073741811;
    v14 = 2437;
    goto LABEL_62;
  }
  if ( a2 )
    v15 = a2;
  else
    v15 = (__int64)&Blink[2].Flink[2].Blink[7];
  DatabaseInformation = CscStoreQueryDatabaseInformation(v52, 0, 0, 0);
  if ( DatabaseInformation < 0 )
  {
    v14 = 2463;
    goto LABEL_62;
  }
  v17 = a3[1];
  v18 = *(_DWORD *)a3;
  v19 = a3[3];
  v42 = 0;
  v41 = v18;
  if ( (v17 & 2) != 0 )
  {
    LOBYTE(v18) = BYTE1(v18) | 1;
    BYTE1(v41) = BYTE1(v18) | 1;
  }
  else
  {
    LOBYTE(v18) = BYTE1(v41);
  }
  LOBYTE(v16) = 4;
  if ( (v17 & 8) != 0 )
  {
    LOBYTE(v18) = v18 | 4;
    BYTE1(v41) = v18;
  }
  v20 = HIBYTE(v41);
  if ( (v19 & 2) != 0 )
  {
    v20 = HIBYTE(v41) | 1;
    HIBYTE(v41) |= 1u;
  }
  if ( (v19 & 8) != 0 )
  {
    v20 |= 4u;
    HIBYTE(v41) = v20;
  }
  if ( (v19 & 0x20) != 0 )
  {
    v20 |= 0x10u;
    HIBYTE(v41) = v20;
  }
  if ( LOWORD(Flink->Flink) == 0xEC22 )
  {
    LOBYTE(v18) = v18 & 0xF5;
    v20 &= 0xD5u;
    BYTE1(v41) = v18;
    HIBYTE(v41) = v20;
  }
  if ( (v54[0] & 0x20) != 0 )
  {
    v21 = *((_QWORD *)&v49[0] + 1);
    v29 = *(_QWORD *)(*((_QWORD *)&v49[0] + 1) + 56LL);
    v45 = v29;
  }
  else
  {
    if ( (v54[0] & 4) == 0 || (v21 = *((_QWORD *)&v49[0] + 1)) == 0 )
    {
      DatabaseInformation = -1073741790;
      v14 = 2503;
      goto LABEL_62;
    }
    if ( !(_BYTE)v18 && !v20 )
    {
      DatabaseInformation = 0;
      v14 = 2516;
      goto LABEL_62;
    }
    DatabaseInformation = CscFcbForceFlowOpens(a1, Flink, v16);
    if ( DatabaseInformation < 0 )
    {
      v14 = 2531;
      goto LABEL_62;
    }
    String2 = (const UNICODE_STRING *)RxFcbTableNameFromFcb(Flink);
    RxInitNetInfoFromFcb(Flink, v55);
    v23 = Flink[8].Flink;
    v24 = (LOBYTE(v54[0]) >> 4) & 1;
    if ( v23[3].Flink )
    {
      CscAcquireLViewLock(v23);
      v25 = Flink[8].Flink;
      v26 = (HIDWORD(v25[3].Flink->Flink) & 0x1000) != 0;
      v40[0] = (HIDWORD(v25[3].Flink->Flink) & 8) != 0;
      CscReleaseLViewLock(v25);
    }
    else
    {
      v26 = 0;
    }
    v27 = v26;
    v28 = Fcb;
    DatabaseInformation = CscUpdateShareInfoForLogicalView(
                            (int)Fcb,
                            v24 + 3,
                            v15,
                            v54[3],
                            (unsigned __int64)v40 & -(__int64)v27,
                            String2,
                            (__int64)&v46,
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
      v14 = 2593;
      goto LABEL_62;
    }
    DatabaseInformation = CscStoreFindOrCreatePinnedEntry(
                            (unsigned int)&v45,
                            (unsigned int)&v46 + 4,
                            (_DWORD)String2,
                            v24 + 3,
                            (__int64)v55,
                            (__int64)&v41);
    if ( DatabaseInformation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_ZD(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          (unsigned int)WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
          (_DWORD)String2,
          DatabaseInformation);
      v29 = v45;
      v14 = 2608;
      goto LABEL_57;
    }
    v9 = BYTE4(v46) | v46;
    v29 = v45;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
        v45,
        Flink,
        v47);
    v42 = 1;
    if ( (v9 & 2) != 0 )
    {
      v30 = CscBumpGlobalNewlyCachedEpoch();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids, v30);
    }
    if ( !*(_QWORD *)&v49[0] )
    {
      DatabaseInformation = CscCreateAndInitializeFobxContext(v50, v49, (2 * ((v54[0] & 0x10) == 0)) | 1u, 0);
      if ( DatabaseInformation )
      {
        v14 = 2652;
        goto LABEL_57;
      }
      v21 = *((_QWORD *)&v49[0] + 1);
      if ( (v54[0] & 0x10) == 0 )
        *(_QWORD *)(*(_QWORD *)&v49[0] + 64LL) = *(_QWORD *)(*((_QWORD *)v28->Header.FileContextSupportPointer + 44)
                                                           + 144LL);
    }
  }
  if ( (v9 & 1) == 0 || v51 )
    goto LABEL_77;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      LODWORD(v47[9].Blink));
  DatabaseInformation = CscStoreSetExplicitAccessEntry(v29, 0, v15, v47[9].Blink, 3);
  if ( DatabaseInformation >= 0 )
  {
LABEL_77:
    if ( (v52[0] & 1) != 0 )
    {
      v40[0] = 0;
      DatabaseInformation = CscStoreQueryCanSidDecryptEntry(v29, v15, v40);
      if ( DatabaseInformation < 0 )
      {
        v14 = 2708;
        goto LABEL_57;
      }
      if ( !v40[0] )
      {
        DatabaseInformation = -1073741165;
        v14 = 2715;
        goto LABEL_57;
      }
    }
    DatabaseInformation = CscStoreSetPinInformationEntry(v29, v15, &v41, &v44);
    if ( DatabaseInformation >= 0 )
    {
      v14 = 0;
      v32 = v44 | HIBYTE(v44);
      if ( !v44 && LOWORD(Flink->Flink) != 0xEC21 )
        *(_DWORD *)(v21 + 4) |= 0x20000u;
      if ( !BYTE1(v41) && !HIBYTE(v41) )
        goto LABEL_95;
      *(_DWORD *)(v21 + 4) &= ~0x20000u;
      if ( (*(_DWORD *)(v21 + 4) & 0x800) != 0 )
      {
        v40[0] = 0;
        DatabaseInformation = CscStoreSetInformationEntry(v29, 0, 0, 0, 0, v40, 0);
      }
      *(_DWORD *)(v21 + 4) = *(_DWORD *)(v21 + 4) & 0xFCFFFF7F | 0x80;
      if ( (v54[0] & 0x20) == 0 )
      {
        v42 = 0;
        v29 = 0;
        DatabaseInformation = CscApplyStoreHandleToFcbOrDeref(Fcb);
        v45 = 0;
      }
      if ( !BYTE1(v41) && !HIBYTE(v41) )
      {
LABEL_95:
        RxAcquirePowerContextLock();
        v35 = BYTE2(Flink[17].Blink);
        if ( (v35 & 1) != 0 )
        {
          LOBYTE(v33) = 1;
          LOBYTE(v34) = 4;
          if ( v35 >= 0 )
            LOBYTE(v34) = 2;
          RxUpdateFcbPowerState(Flink, v33, v34);
        }
        RxReleasePowerContextLock();
      }
      if ( *(_QWORD *)(v21 + 56) )
      {
        if ( v32 )
        {
          CscAcquireLViewLock(Flink[8].Flink);
          v36 = Flink[8].Flink;
          Flink_high = HIDWORD(v36[3].Flink->Flink);
          CscReleaseLViewLock(v36);
          if ( (Flink_high & 0x4000) == 0 && (int)CscStoreIsScopePartlyPinned(*(_QWORD *)(v21 + 56), v43) >= 0 )
          {
            if ( v43[0] )
            {
              v38 = Flink[8].Flink;
              v39 = v38[3].Flink;
              CscAcquireLViewLock(v38);
              HIDWORD(v39->Flink) |= 0x4000u;
              CscReleaseLViewLock(v38);
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
      v14 = 2733;
    }
  }
  else
  {
    v14 = 2690;
  }
LABEL_57:
  if ( v29 && v42 )
  {
    CscStoreDereferenceEntry(&v45);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)DatabaseInformation;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
        v45,
        Flink,
        v47);
  }
LABEL_62:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      (unsigned int)DatabaseInformation,
      v14);
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
