# SmbCeCompleteSessionEntryInitialization

- ea: `0x14002dab0`
- end: `0x14002dfe6`
- name: `SmbCeCompleteSessionEntryInitialization`
- size: `1334`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400014b8`
- `0x140003480`
- `0x140005320`
- `0x1400093a0`
- `0x140021130`
- `0x1400221e0`
- `0x14002dab0`
- `0x1400377dc`
- `0x14003e14c`
- `0x1400459cc`
- `0x140045b68`
- `0x1400468c8`
- `0x140046a24`
- `0x140059ea0`
- `0x140090750`
- `0x140093050`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002de11`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002df0b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002de11`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002df0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dfc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dfc1`
- `rdbss!RxDispatchToWorkerThread` at `0x14002df30`
- `rdbss!RxDispatchToWorkerThread` at `0x14002df30`

## pseudocode

```c
void __fastcall SmbCeCompleteSessionEntryInitialization(_QWORD *P)
{
  ULONG_PTR v1; // rbx
  int v3; // edi
  __int64 v4; // r15
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // r13
  int InvalidAuthEntryListForDeviceSilo; // eax
  __int64 v9; // r8
  int v10; // r9d
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  PDEVICE_OBJECT v14; // rcx
  KIRQL v15; // r12
  _DWORD *v16; // rax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r11
  __int64 v20; // rcx
  __int64 v21; // rcx
  char v22; // bp
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  KIRQL v29; // bp
  _DWORD *v30; // rax
  int v31; // eax
  NTSTATUS v32; // eax
  int v33; // eax
  int v34; // [rsp+28h] [rbp-70h]
  __int64 v35; // [rsp+A0h] [rbp+8h]
  __int64 v36; // [rsp+A0h] [rbp+8h]
  PVOID pContext; // [rsp+A8h] [rbp+10h] BYREF

  v1 = P[3];
  v3 = *((_DWORD *)P + 2);
  v4 = P[2];
  v5 = P[4];
  v6 = *(_QWORD *)(v1 + 384);
  v7 = *(_QWORD *)(v1 + 24);
  pContext = 0;
  InvalidAuthEntryListForDeviceSilo = SmbCeGetInvalidAuthEntryListForDeviceSilo(v7, *(_QWORD *)(v6 + 520));
  SmbCeUpdateInvalidAuthEntryList(InvalidAuthEntryListForDeviceSilo, v1, v9, v10, v9, v3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids, v1, v3);
  }
  v15 = SmbCeAcquireSpinLock(v7, v11, v12);
  if ( v3 >= 0 )
  {
    if ( (unsigned __int8)SmbCeIsBindingObjectListEmpty(v1) )
    {
      v3 = -1073741300;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
          v1,
          -1073741300);
      }
    }
  }
  v16 = *(_DWORD **)(v1 + 384);
  if ( v16[3] )
  {
    v3 = v16[100];
    if ( v3 >= 0 )
      __int2c();
    v17 = v16[101];
    *((_DWORD *)P + 2) = v3;
    *((_DWORD *)P + 3) = v17;
  }
  if ( v5 )
    SmbCeCompleteObjectConstructionLite(v5, P[1], &pContext);
  if ( v3 >= 0 && *(_DWORD *)(v1 + 264) > 1u && (byte_1400712C2 & 2) != 0 )
  {
    v18 = *(_QWORD *)(v5 + 392);
    v19 = *(_QWORD *)(v1 + 384);
    McTemplateK0qxqhzr3qbr5tt_EtwWriteTransfer(
      *(_BYTE *)(v18 + 325) != 0 ? 28 : 16,
      *(_WORD *)(v19 + 80) >> 1,
      *(unsigned __int8 *)(v1 + 464),
      v3,
      *(_QWORD *)(v1 + 440),
      v34,
      *(_WORD *)(v19 + 80) >> 1,
      *(_QWORD *)(v19 + 88),
      *(_BYTE *)(v18 + 325) != 0 ? 28 : 16,
      v18 + 428,
      *(_BYTE *)(v1 + 464),
      (*(_DWORD *)(v1 + 4) & 4) != 0);
  }
  if ( byte_14007D22F )
  {
    if ( v3 < 0 )
    {
      if ( v5 && (byte_1400712C2 & 0x20) != 0 )
      {
        v21 = *(_QWORD *)(v5 + 392);
        McTemplateK0qxhzr2qbr4qbr6_EtwWriteTransfer(
          v21 + 428,
          (unsigned int)&SessionSetupErrorNoisy,
          *(_BYTE *)(v21 + 325) != 0 ? 28 : 16,
          v3,
          *(_QWORD *)(v1 + 440),
          *(_WORD *)(*(_QWORD *)(v1 + 384) + 80LL) >> 1,
          *(_QWORD *)(*(_QWORD *)(v1 + 384) + 88LL),
          *(_BYTE *)(v21 + 325) != 0 ? 28 : 16,
          v21 + 428,
          *(_BYTE *)(v21 + 325) != 0 ? 28 : 16,
          v21 + 400);
      }
    }
    else if ( (byte_1400712C2 & 0x10) != 0 )
    {
      v20 = *(_QWORD *)(v5 + 392);
      McTemplateK0qxhzr2qbr4qbr6_EtwWriteTransfer(
        v20 + 428,
        (unsigned int)&SessionEstablishedNoisy,
        *(_BYTE *)(v20 + 325) != 0 ? 28 : 16,
        v3,
        *(_QWORD *)(v1 + 440),
        *(_WORD *)(*(_QWORD *)(v1 + 384) + 80LL) >> 1,
        *(_QWORD *)(*(_QWORD *)(v1 + 384) + 88LL),
        *(_BYTE *)(v20 + 325) != 0 ? 28 : 16,
        v20 + 428,
        *(_BYTE *)(v20 + 325) != 0 ? 28 : 16,
        v20 + 400);
    }
  }
  HIDWORD(v35) = *((_DWORD *)P + 3);
  *(_QWORD *)(v1 + 336) = SmbCePrepareNonMitigatedExchangeForRestart;
  LODWORD(v35) = v3;
  if ( v3 >= 0 && *(_QWORD *)(*(_QWORD *)(v1 + 384) + 576LL) && (unsigned __int8)SmbCeMultiChannelInitiated(v1) )
  {
    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v14, v13);
    v22 = 1;
    if ( (*(_BYTE *)(*(_QWORD *)(v1 + 384) + 737LL) & 0x10) != 0 )
    {
      _InterlockedExchange((volatile __int32 *)(v1 + 12), 12);
      goto LABEL_35;
    }
  }
  else
  {
    v22 = 0;
    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v14, v13);
  }
  SmbCeCompleteObjectConstructionLite(v1, v35, &pContext);
LABEL_35:
  *(_DWORD *)(v7 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v7 + 1920), v15);
  Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v24, v23);
  if ( v22 )
  {
    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v26, v25);
    if ( (*(_BYTE *)(*(_QWORD *)(v1 + 384) + 737LL) & 0x10) != 0 )
    {
      SmbCeWaitForMultichannelConnections(v1);
      v29 = SmbCeAcquireSpinLock(v7, v27, v28);
      if ( v3 >= 0 )
      {
        if ( (unsigned __int8)SmbCeIsBindingObjectListEmpty(v1) )
        {
          v3 = -1073741300;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              30,
              &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
              v1,
              -1073741300);
          }
        }
      }
      v30 = *(_DWORD **)(v1 + 384);
      if ( v30[3] )
      {
        v3 = v30[100];
        if ( v3 >= 0 )
          __int2c();
        v31 = v30[101];
        *((_DWORD *)P + 2) = v3;
        *((_DWORD *)P + 3) = v31;
      }
      HIDWORD(v36) = *((_DWORD *)P + 3);
      LODWORD(v36) = v3;
      SmbCeCompleteObjectConstructionLite(v1, v36, &pContext);
      *(_DWORD *)(v7 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v7 + 1920), v29);
    }
    else
    {
      SmbCeReferenceSessionEntry(v1);
      v32 = RxDispatchToWorkerThread(
              (PRDBSS_DEVICE_OBJECT)v7,
              NormalWorkQueue,
              SmbCeEstablishMultipleChannels,
              (PVOID)v1);
      if ( v32 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids, v1, v32);
        }
        SmbCeDereferenceSessionEntryEx(v1);
      }
    }
  }
  Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v26, v25);
  if ( pContext )
    SmbCeDereferenceExchange((unsigned __int64)pContext);
  if ( v4 )
  {
    v33 = *((_DWORD *)P + 3);
    *(_DWORD *)(v4 + 8) = v3;
    *(_DWORD *)(v4 + 12) = v33;
    (*(void (__fastcall **)(__int64))v4)(v4);
  }
  ExFreePoolWithTag(P, 0x6D536243u);
}

```

## disassembly

```asm
0x14002dab0  mov     rax, rsp
0x14002dab3  mov     [rax+18h], rbx
0x14002dab7  push    rbp
0x14002dab8  push    rsi
0x14002dab9  push    rdi
0x14002daba  push    r12
0x14002dabc  push    r13
0x14002dabe  push    r14
0x14002dac0  push    r15
0x14002dac2  sub     rsp, 60h
0x14002dac6  mov     rbx, [rcx+18h]
0x14002daca  mov     rsi, rcx
0x14002dacd  mov     edi, [rcx+8]
0x14002dad0  mov     r15, [rcx+10h]
0x14002dad4  mov     rbp, [rcx+20h]
0x14002dad8  mov     rdx, [rbx+180h]
0x14002dadf  mov     r13, [rbx+18h]
0x14002dae3  mov     rcx, r13
0x14002dae6  mov     qword ptr [rax+10h], 0
0x14002daee  lea     r8, [rdx+50h]
0x14002daf2  mov     rdx, [rdx+208h]
0x14002daf9  call    SmbCeGetInvalidAuthEntryListForDeviceSilo
0x14002dafe  mov     rcx, rax
0x14002db01  mov     [rsp+98h+var_70], edi
0x14002db05  mov     rdx, rbx
0x14002db08  mov     [rsp+98h+var_78], r8
0x14002db0d  call    SmbCeUpdateInvalidAuthEntryList
0x14002db12  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002db19  lea     r14, WPP_GLOBAL_Control
0x14002db20  cmp     rcx, r14
0x14002db23  jz      short loc_14002DB4E
0x14002db25  mov     eax, [rcx+2Ch]
0x14002db28  test    al, 40h
0x14002db2a  jz      short loc_14002DB4E
0x14002db2c  cmp     byte ptr [rcx+29h], 2
0x14002db30  jb      short loc_14002DB4E
0x14002db32  mov     rcx, [rcx+18h]
0x14002db36  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002db3d  mov     edx, 1Ch
0x14002db42  mov     dword ptr [rsp+98h+var_78], edi
0x14002db46  mov     r9, rbx
0x14002db49  call    WPP_SF_qD
0x14002db4e  mov     rcx, r13
0x14002db51  call    SmbCeAcquireSpinLock
0x14002db56  mov     r12b, al
0x14002db59  test    edi, edi
0x14002db5b  js      short loc_14002DBA7
0x14002db5d  mov     rcx, rbx
0x14002db60  call    SmbCeIsBindingObjectListEmpty
0x14002db65  test    al, al
0x14002db67  jz      short loc_14002DBA7
0x14002db69  mov     edi, 0C000020Ch
0x14002db6e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002db75  cmp     rcx, r14
0x14002db78  jz      short loc_14002DBA7
0x14002db7a  mov     eax, [rcx+2Ch]
0x14002db7d  test    al, 1
0x14002db7f  jz      short loc_14002DBA7
0x14002db81  cmp     byte ptr [rcx+29h], 1
0x14002db85  jb      short loc_14002DBA7
0x14002db87  mov     rcx, [rcx+18h]
0x14002db8b  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002db92  mov     edx, 1Dh
0x14002db97  mov     dword ptr [rsp+98h+var_78], 0C000020Ch
0x14002db9f  mov     r9, rbx
0x14002dba2  call    WPP_SF_qD
0x14002dba7  mov     rax, [rbx+180h]
0x14002dbae  cmp     dword ptr [rax+0Ch], 0
0x14002dbb2  jz      short loc_14002DBCC
0x14002dbb4  mov     edi, [rax+190h]
0x14002dbba  test    edi, edi
0x14002dbbc  js      short loc_14002DBC0
0x14002dbbe  int     2Ch; Windows NT - assertion failure
0x14002dbc0  mov     eax, [rax+194h]
0x14002dbc6  mov     [rsi+8], edi
0x14002dbc9  mov     [rsi+0Ch], eax
0x14002dbcc  test    rbp, rbp
0x14002dbcf  jz      short loc_14002DBE5
0x14002dbd1  mov     rdx, [rsi+8]
0x14002dbd5  lea     r8, [rsp+98h+pContext]
0x14002dbdd  mov     rcx, rbp
0x14002dbe0  call    SmbCeCompleteObjectConstructionLite
0x14002dbe5  mov     r14d, 0Ch
0x14002dbeb  test    edi, edi
0x14002dbed  js      loc_14002DC7B
0x14002dbf3  cmp     dword ptr [rbx+108h], 1
0x14002dbfa  jbe     short loc_14002DC7B
0x14002dbfc  test    cs:byte_1400712C2, 2
0x14002dc03  jz      short loc_14002DC7B
0x14002dc05  mov     rax, [rbp+188h]
0x14002dc0c  mov     r11, [rbx+180h]
0x14002dc13  mov     r10d, [rbx+4]
0x14002dc17  movzx   r8d, byte ptr [rbx+1D0h]
0x14002dc1f  lea     r9, [rax+1ACh]
0x14002dc26  shr     r10d, 2
0x14002dc2a  mov     al, [rax+145h]
0x14002dc30  and     r10d, 1
0x14002dc34  movzx   edx, word ptr [r11+50h]
0x14002dc39  neg     al
0x14002dc3b  mov     rax, [r11+58h]
0x14002dc3f  mov     [rsp+98h+var_40], r10d
0x14002dc44  sbb     ecx, ecx
0x14002dc46  mov     dword ptr [rsp+98h+var_48], r8d
0x14002dc4b  and     ecx, r14d
0x14002dc4e  mov     [rsp+98h+var_50], r9
0x14002dc53  add     ecx, 10h
0x14002dc56  mov     dword ptr [rsp+98h+var_58], ecx
0x14002dc5a  mov     r9d, edi
0x14002dc5d  mov     [rsp+98h+var_60], rax
0x14002dc62  mov     rax, [rbx+1B8h]
0x14002dc69  shr     dx, 1
0x14002dc6c  mov     word ptr [rsp+98h+var_68], dx
0x14002dc71  mov     [rsp+98h+var_78], rax
0x14002dc76  call    McTemplateK0qxqhzr3qbr5tt_EtwWriteTransfer
0x14002dc7b  cmp     cs:byte_14007D22F, 0
0x14002dc82  jz      loc_14002DD7B
0x14002dc88  test    edi, edi
0x14002dc8a  js      short loc_14002DCFA
0x14002dc8c  test    cs:byte_1400712C2, 10h
0x14002dc93  jz      loc_14002DD7B
0x14002dc99  mov     rcx, [rbp+188h]
0x14002dca0  mov     r9, [rbx+180h]
0x14002dca7  mov     al, [rcx+145h]
0x14002dcad  movzx   edx, word ptr [r9+50h]
0x14002dcb2  neg     al
0x14002dcb4  lea     rax, [rcx+190h]
0x14002dcbb  mov     [rsp+98h+var_48], rax
0x14002dcc0  sbb     r8d, r8d
0x14002dcc3  mov     rax, [r9+58h]
0x14002dcc7  and     r8d, r14d
0x14002dcca  add     r8d, 10h
0x14002dcce  add     rcx, 1ACh
0x14002dcd5  mov     dword ptr [rsp+98h+var_50], r8d
0x14002dcda  mov     [rsp+98h+var_58], rcx
0x14002dcdf  mov     dword ptr [rsp+98h+var_60], r8d
0x14002dce4  shr     dx, 1
0x14002dce7  mov     [rsp+98h+var_68], rax
0x14002dcec  mov     word ptr [rsp+98h+var_70], dx
0x14002dcf1  lea     rdx, SessionEstablishedNoisy
0x14002dcf8  jmp     short loc_14002DD67
0x14002dcfa  test    rbp, rbp
0x14002dcfd  jz      short loc_14002DD7B
0x14002dcff  test    cs:byte_1400712C2, 20h
0x14002dd06  jz      short loc_14002DD7B
0x14002dd08  mov     rcx, [rbp+188h]
0x14002dd0f  mov     r9, [rbx+180h]
0x14002dd16  mov     al, [rcx+145h]
0x14002dd1c  movzx   edx, word ptr [r9+50h]
0x14002dd21  neg     al
0x14002dd23  lea     rax, [rcx+190h]
0x14002dd2a  mov     [rsp+98h+var_48], rax
0x14002dd2f  sbb     r8d, r8d
0x14002dd32  mov     rax, [r9+58h]
0x14002dd36  and     r8d, r14d
0x14002dd39  add     r8d, 10h
0x14002dd3d  add     rcx, 1ACh
0x14002dd44  mov     dword ptr [rsp+98h+var_50], r8d
0x14002dd49  mov     [rsp+98h+var_58], rcx
0x14002dd4e  mov     dword ptr [rsp+98h+var_60], r8d
0x14002dd53  shr     dx, 1
0x14002dd56  mov     [rsp+98h+var_68], rax
0x14002dd5b  mov     word ptr [rsp+98h+var_70], dx
0x14002dd60  lea     rdx, SessionSetupErrorNoisy
0x14002dd67  mov     rax, [rbx+1B8h]
0x14002dd6e  mov     r9d, edi
0x14002dd71  mov     [rsp+98h+var_78], rax
0x14002dd76  call    McTemplateK0qxhzr2qbr4qbr6_EtwWriteTransfer
0x14002dd7b  mov     eax, [rsi+0Ch]
0x14002dd7e  mov     dword ptr [rsp+98h+arg_0+4], eax
0x14002dd85  lea     rax, SmbCePrepareNonMitigatedExchangeForRestart
0x14002dd8c  mov     [rbx+150h], rax
0x14002dd93  mov     dword ptr [rsp+98h+arg_0], edi
0x14002dd9a  test    edi, edi
0x14002dd9c  js      short loc_14002DDD9
0x14002dd9e  mov     rax, [rbx+180h]
0x14002dda5  cmp     qword ptr [rax+240h], 0
0x14002ddad  jz      short loc_14002DDD9
0x14002ddaf  mov     rcx, rbx
0x14002ddb2  call    SmbCeMultiChannelInitiated
0x14002ddb7  test    al, al
0x14002ddb9  jz      short loc_14002DDD9
0x14002ddbb  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x14002ddc0  mov     rax, [rbx+180h]
0x14002ddc7  mov     bpl, 1
0x14002ddca  test    byte ptr [rax+2E1h], 10h
0x14002ddd1  jz      short loc_14002DDE1
0x14002ddd3  xchg    r14d, [rbx+0Ch]
0x14002ddd7  jmp     short loc_14002DDF9
0x14002ddd9  xor     bpl, bpl
0x14002dddc  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x14002dde1  mov     rdx, [rsp+98h+arg_0]
0x14002dde9  lea     r8, [rsp+98h+pContext]
0x14002ddf1  mov     rcx, rbx
0x14002ddf4  call    SmbCeCompleteObjectConstructionLite
0x14002ddf9  lea     r14, [r13+780h]
0x14002de00  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002de0b  mov     rcx, r14; SpinLock
0x14002de0e  mov     dl, r12b; OldIrql
0x14002de11  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002de18  nop     dword ptr [rax+rax+00h]
0x14002de1d  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x14002de22  test    bpl, bpl
0x14002de25  jz      loc_14002DF87
0x14002de2b  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x14002de30  mov     rax, [rbx+180h]
0x14002de37  mov     rcx, rbx; BugCheckParameter2
0x14002de3a  test    byte ptr [rax+2E1h], 10h
0x14002de41  jz      loc_14002DF19
0x14002de47  call    SmbCeWaitForMultichannelConnections
0x14002de4c  mov     rcx, r13
0x14002de4f  call    SmbCeAcquireSpinLock
0x14002de54  mov     bpl, al
0x14002de57  test    edi, edi
0x14002de59  js      short loc_14002DEAC
0x14002de5b  mov     rcx, rbx
0x14002de5e  call    SmbCeIsBindingObjectListEmpty
0x14002de63  test    al, al
0x14002de65  jz      short loc_14002DEAC
0x14002de67  mov     edi, 0C000020Ch
0x14002de6c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002de73  lea     rdx, WPP_GLOBAL_Control
0x14002de7a  cmp     rcx, rdx
0x14002de7d  jz      short loc_14002DEAC
0x14002de7f  mov     eax, [rcx+2Ch]
0x14002de82  test    al, 1
0x14002de84  jz      short loc_14002DEAC
0x14002de86  cmp     byte ptr [rcx+29h], 1
0x14002de8a  jb      short loc_14002DEAC
0x14002de8c  mov     rcx, [rcx+18h]
0x14002de90  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002de97  mov     edx, 1Eh
0x14002de9c  mov     dword ptr [rsp+98h+var_78], 0C000020Ch
0x14002dea4  mov     r9, rbx
0x14002dea7  call    WPP_SF_qD
0x14002deac  mov     rax, [rbx+180h]
0x14002deb3  cmp     dword ptr [rax+0Ch], 0
0x14002deb7  jz      short loc_14002DED1
0x14002deb9  mov     edi, [rax+190h]
0x14002debf  test    edi, edi
0x14002dec1  js      short loc_14002DEC5
0x14002dec3  int     2Ch; Windows NT - assertion failure
0x14002dec5  mov     eax, [rax+194h]
0x14002decb  mov     [rsi+8], edi
0x14002dece  mov     [rsi+0Ch], eax
0x14002ded1  mov     eax, [rsi+0Ch]
0x14002ded4  lea     r8, [rsp+98h+pContext]
0x14002dedc  mov     dword ptr [rsp+98h+arg_0+4], eax
0x14002dee3  mov     rcx, rbx
0x14002dee6  mov     dword ptr [rsp+98h+arg_0], edi
0x14002deed  mov     rdx, [rsp+98h+arg_0]
0x14002def5  call    SmbCeCompleteObjectConstructionLite
0x14002defa  mov     dl, bpl; OldIrql
0x14002defd  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002df08  mov     rcx, r14; SpinLock
0x14002df0b  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002df12  nop     dword ptr [rax+rax+00h]
0x14002df17  jmp     short loc_14002DF87
0x14002df19  call    SmbCeReferenceSessionEntry
0x14002df1e  mov     r9, rbx; pContext
0x14002df21  lea     r8, SmbCeEstablishMultipleChannels; Routine
0x14002df28  mov     edx, 3; WorkQueueType
0x14002df2d  mov     rcx, r13; pMRxDeviceObject
0x14002df30  call    cs:__imp_RxDispatchToWorkerThread
0x14002df37  nop     dword ptr [rax+rax+00h]
0x14002df3c  test    eax, eax
0x14002df3e  jns     short loc_14002DF87
0x14002df40  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002df47  lea     rdx, WPP_GLOBAL_Control
0x14002df4e  cmp     rcx, rdx
0x14002df51  jz      short loc_14002DF7D
0x14002df53  mov     edx, [rcx+2Ch]
0x14002df56  test    dl, 1
0x14002df59  jz      short loc_14002DF7D
0x14002df5b  cmp     byte ptr [rcx+29h], 1
0x14002df5f  jb      short loc_14002DF7D
0x14002df61  mov     rcx, [rcx+18h]
0x14002df65  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002df6c  mov     edx, 1Fh
0x14002df71  mov     dword ptr [rsp+98h+var_78], eax
0x14002df75  mov     r9, rbx
0x14002df78  call    WPP_SF_qD
0x14002df7d  xor     edx, edx
0x14002df7f  mov     rcx, rbx; BugCheckParameter2
0x14002df82  call    SmbCeDereferenceSessionEntryEx
0x14002df87  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x14002df8c  mov     rcx, [rsp+98h+pContext]; pContext
0x14002df94  test    rcx, rcx
0x14002df97  jz      short loc_14002DF9E
0x14002df99  call    SmbCeDereferenceExchange
0x14002df9e  test    r15, r15
0x14002dfa1  jz      short loc_14002DFB9
0x14002dfa3  mov     eax, [rsi+0Ch]
0x14002dfa6  mov     rcx, r15
0x14002dfa9  mov     [r15+8], edi
0x14002dfad  mov     [r15+0Ch], eax
0x14002dfb1  mov     rax, [r15]
0x14002dfb4  call    _guard_dispatch_icall
0x14002dfb9  mov     edx, 6D536243h; Tag
0x14002dfbe  mov     rcx, rsi; P
0x14002dfc1  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
