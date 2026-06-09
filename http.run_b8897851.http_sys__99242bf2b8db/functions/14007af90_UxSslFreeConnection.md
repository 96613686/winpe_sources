# UxSslFreeConnection

- ea: `0x14007af90`
- end: `0x14007b9a5`
- name: `UxSslFreeConnection`
- size: `2581`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000a350`
- `0x140018f04`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x14006e50c`
- `0x14007984c`
- `0x14007af90`
- `0x14007ebc0`
- `0x140097b3c`
- `0x1400eda1c`
- `0x1401339a0`
- `0x1401386dc`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007b38a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007b38a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14007b2d9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14007b2d9`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14007b91a`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14007b91a`
- `ntoskrnl!KeSetEvent` at `0x14007b939`
- `ntoskrnl!KeSetEvent` at `0x14007b939`
- `ntoskrnl!ZwClose` at `0x14007b6a4`
- `ntoskrnl!ZwClose` at `0x14007b6a4`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007b435`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007b435`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140178c75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140178c75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b278`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b709`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b72a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b87c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b8df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b278`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b709`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b72a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b87c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b8df`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140178c69`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140178c69`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140178c16`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140178c16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140178c04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140178c04`
- `ksecdd!SspiFreeAsyncContext` at `0x14007b097`
- `ksecdd!SspiFreeAsyncContext` at `0x14007b097`
- `ksecdd!SspiDeleteSecurityContextAsync` at `0x14007b031`
- `ksecdd!SspiDeleteSecurityContextAsync` at `0x14007b031`
- `ksecdd!FreeContextBuffer` at `0x14007b267`
- `ksecdd!FreeContextBuffer` at `0x14007b68c`
- `ksecdd!FreeContextBuffer` at `0x14007b8f7`
- `ksecdd!FreeContextBuffer` at `0x14007b267`
- `ksecdd!FreeContextBuffer` at `0x14007b68c`
- `ksecdd!FreeContextBuffer` at `0x14007b8f7`

## pseudocode

```c
void __fastcall UxSslFreeConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rbx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  SspiAsyncContext *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rax
  _OWORD *v17; // r12
  char v18; // r13
  int v19; // ebp
  signed __int32 v20; // r15d
  int v21; // eax
  volatile signed __int32 *v22; // rsi
  volatile signed __int32 *v23; // rdx
  int v24; // eax
  _QWORD *v25; // rsi
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rsi
  __int64 v30; // rdx
  ULONG_PTR v31; // rdx
  int v32; // edi
  __int64 v33; // rbp
  void (__fastcall *v34)(__int64); // rsi
  bool v35; // zf
  unsigned __int64 v36; // rdi
  __int64 v37; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v39; // rcx
  int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v44[24]; // [rsp+40h] [rbp-98h] BYREF

  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 17, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1);
  v5 = (char *)(a1 - 160);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 18, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, v5);
  if ( *(_BYTE *)(*((_QWORD *)v5 + 212) + 8162LL)
    && !v5[1366]
    && *((_QWORD *)v5 + 55) != -1
    && *((_QWORD *)v5 + 56) != -1
    && !v5[1368] )
  {
    UxSslConnectionDisableReconnects((PCtxtHandle)(v5 + 440));
  }
  v6 = (void *)*((_QWORD *)v5 + 158);
  if ( v6 )
  {
    FreeContextBuffer(v6);
    *((_QWORD *)v5 + 158) = 0;
  }
  v7 = (void *)*((_QWORD *)v5 + 160);
  if ( v7 )
  {
    ZwClose(v7);
    *((_QWORD *)v5 + 160) = 0;
  }
  if ( *((_QWORD *)v5 + 55) != -1 && *((_QWORD *)v5 + 56) != -1 )
  {
    SspiDeleteSecurityContextAsync(*((SspiAsyncContext **)v5 + 196), (PCtxtHandle)(v5 + 440));
    *((_QWORD *)v5 + 56) = -1;
    *((_QWORD *)v5 + 55) = -1;
  }
  if ( *((_QWORD *)v5 + 227) )
  {
    UxWfpFreeThrottleContext();
    *((_QWORD *)v5 + 227) = 0;
  }
  v8 = (void *)*((_QWORD *)v5 + 193);
  if ( v8 )
  {
    UxSslFreeAchContext(v8);
    *((_QWORD *)v5 + 193) = 0;
  }
  v9 = (void *)*((_QWORD *)v5 + 194);
  if ( v9 )
  {
    UxSslFreeAscContext(v9);
    *((_QWORD *)v5 + 194) = 0;
  }
  v10 = (void *)*((_QWORD *)v5 + 195);
  if ( v10 )
  {
    UxSslFreeAscContext(v10);
    *((_QWORD *)v5 + 195) = 0;
  }
  v11 = (SspiAsyncContext *)*((_QWORD *)v5 + 196);
  if ( v11 )
  {
    SspiFreeAsyncContext(v11);
    *((_QWORD *)v5 + 196) = 0;
  }
  v12 = (void *)*((_QWORD *)v5 + 202);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  *((_QWORD *)v5 + 202) = 0;
  v13 = (void *)*((_QWORD *)v5 + 207);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  *((_QWORD *)v5 + 207) = 0;
  if ( *((_DWORD *)v5 + 410) )
  {
    ExFreePoolWithTag(*((PVOID *)v5 + 204), 0);
    *((_QWORD *)v5 + 204) = 0;
    *((_DWORD *)v5 + 410) = 0;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 197, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, v5);
  v14 = (void *)*((_QWORD *)v5 + 197);
  if ( v14 )
  {
    ExFreePoolWithTag(v14, 0);
    *((_QWORD *)v5 + 197) = 0;
    *((_DWORD *)v5 + 396) = 0;
    *((_QWORD *)v5 + 199) = 0;
    *((_DWORD *)v5 + 400) = 0;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 198, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
  v15 = *((_QWORD *)v5 + 54);
  if ( v15 )
  {
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qD(1041, 53, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, v15, 0);
    v16 = *(_QWORD *)(v15 + 856);
    v17 = 0;
    v18 = *(_BYTE *)(v16 + 8165);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qD(1041, 148, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, v15 + 16, *(unsigned __int8 *)(v16 + 8165));
    LODWORD(v43) = *(_DWORD *)(v15 + 104);
    do
    {
      v19 = v43;
      if ( (_DWORD)v43 == 1 )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v15 + 16, 0);
        v20 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 104), 0, 1);
        LODWORD(v43) = v20;
        if ( v20 == 1 )
        {
          v17 = *(_OWORD **)(v15 + 24);
          v17[3] = *(_OWORD *)(v15 + 88);
          *((_DWORD *)v17 + 16) = *(_DWORD *)(v15 + 112);
          v42 = *(unsigned int *)(v15 + 112);
          *(_QWORD *)(v15 + 24) = 0;
          UxpSslEndpointInvalidateCertificate(v15 + 88, v42);
          _InterlockedExchange((volatile __int32 *)(v15 + 108), 0);
        }
        ExReleasePushLockExclusiveEx(v15 + 16, 0);
        KeLeaveCriticalRegion();
      }
      else
      {
        v20 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 104), v43 - 1, v43);
        LODWORD(v43) = v20;
      }
    }
    while ( v20 != v19 );
    if ( v17 )
    {
      *(_QWORD *)v17 = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 4) = 0;
      if ( v18 )
      {
        UxpSslUnloadEndpointCertificateWorker(v17);
      }
      else
      {
        LOBYTE(a4) = 1;
        UlThreadPoolEnqueueWorkItem(1, v17, UxpSslUnloadEndpointCertificateWorker, a4, -1, -1);
      }
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 149, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
    v21 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 4));
    if ( UxDebugCheckRefcount && v21 <= -1 )
      UlBugCheckEx(3u, v15 + 4, 0xFu, v21);
    if ( !v21 )
      UxSslDestroyConfiguration(v15);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 54, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
    *((_QWORD *)v5 + 54) = 0;
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)v5 + 192);
  if ( v22 )
  {
    v40 = _InterlockedDecrement(v22 + 5);
    if ( UxDebugCheckRefcount && v40 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v22 + 5), 1u, v40);
    if ( v40 )
      goto LABEL_98;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v22);
    v41 = *((_DWORD *)v22 + 30);
    *((_DWORD *)v22 + 4) = 1819498613;
    if ( v41 )
    {
      switch ( v41 )
      {
        case 1u:
          if ( UxDebugDisableLookaside )
          {
            memset(v44, 0, sizeof(v44));
            v44[10] = dword_1401A0658;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0668)(v22, v44);
            goto LABEL_96;
          }
          v39 = qword_1401A0640;
          break;
        case 2u:
          if ( UxDebugDisableLookaside )
          {
            memset(v44, 0, sizeof(v44));
            v44[10] = dword_1401A0688;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0698)(v22, v44);
            goto LABEL_96;
          }
          v39 = qword_1401A0670;
          break;
        case 3u:
          if ( UxDebugDisableLookaside )
          {
            memset(v44, 0, sizeof(v44));
            v44[10] = dword_1401A06B8;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06C8)(v22, v44);
            goto LABEL_96;
          }
          v39 = qword_1401A06A0;
          break;
        default:
          ExFreePoolWithTag((PVOID)v22, 0);
          goto LABEL_96;
      }
    }
    else
    {
      if ( UxDebugDisableLookaside )
      {
        memset(v44, 0, sizeof(v44));
        v44[10] = dword_1401A0628;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0638)(v22, v44);
        goto LABEL_96;
      }
      v39 = qword_1401A0610;
    }
    if ( UxCompactMode )
      PnlFreeToLookasideList(v39, v22);
    else
      PplFreeToLookasideListProcessor(v39, v22, *(unsigned int *)v22);
LABEL_96:
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
LABEL_98:
    *((_QWORD *)v5 + 192) = 0;
  }
  v23 = (volatile signed __int32 *)*((_QWORD *)v5 + 48);
  if ( v23 )
  {
    v24 = _InterlockedDecrement(v23);
    if ( UxDebugCheckRefcount && v24 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v23, 0xAu, v24);
    if ( !v24 )
    {
      v25 = (_QWORD *)*((_QWORD *)v5 + 48);
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 117, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, *((_QWORD *)v5 + 48));
      v26 = (void *)v25[2];
      if ( v26 )
        FreeContextBuffer(v26);
      ExFreePoolWithTag(v25, 0);
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 118, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
    }
    *((_QWORD *)v5 + 48) = 0;
  }
  v27 = (void *)*((_QWORD *)v5 + 50);
  if ( v27 )
  {
    ExFreePoolWithTag(v27, 0);
    *((_QWORD *)v5 + 50) = 0;
  }
  v28 = (void *)*((_QWORD *)v5 + 53);
  if ( v28 )
  {
    FreeContextBuffer(v28);
    *((_OWORD *)v5 + 26) = 0;
  }
  v29 = (void *)*((_QWORD *)v5 + 211);
  v30 = (unsigned int)UxPodMonitorSlot;
  *((_QWORD *)v5 + 212) = 0;
  v43 = 0;
  PsGetPermanentSiloContext(v29, v30, &v43);
  if ( v29 )
    ObfDereferenceObjectWithTag(v29, 0x43546C55u);
  v31 = v43 + 24;
  v32 = _InterlockedDecrement((volatile signed __int32 *)(v43 + 24));
  if ( UxDebugCheckRefcount && v32 <= -1 )
    UlBugCheckEx(3u, v31, 0xFu, v32);
  if ( !v32 )
    KeSetEvent((PRKEVENT)(v43 + 32), 0, 0);
  *((_QWORD *)v5 + 211) = 0;
  *((_DWORD *)v5 + 10) = 7;
  if ( *((_DWORD *)v5 + 16) == 4 )
  {
    v33 = *((_QWORD *)v5 + 6);
    v34 = *(void (__fastcall **)(__int64))(*((_QWORD *)v5 + 7) + 16LL);
  }
  else
  {
    v34 = 0;
    v33 = 0;
  }
  v35 = UxDebugDisableLookaside == 0;
  *((_DWORD *)v5 + 16) = 5;
  *((_QWORD *)v5 + 7) = 0;
  *((_DWORD *)v5 + 4) = 1634949237;
  if ( v35 )
  {
    if ( UxCompactMode )
    {
      v37 = qword_1401A03D0;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v37, v5, CurrentNodeNumber);
    }
    else
    {
      v36 = qword_1401A03D0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v5 + 1) << 7);
      if ( !*(_BYTE *)(v36 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A03D0, v36 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v36 + 64), v5);
    }
  }
  else
  {
    memset(v44, 0, sizeof(v44));
    v44[10] = dword_1401A03E8;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A03F8)(v5, v44);
  }
  if ( v34 )
    v34(v33);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 19, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
}

```

## disassembly

```asm
0x14007af90  push    rbx
0x14007af92  push    rsi
0x14007af93  push    rdi
0x14007af94  push    r15
0x14007af96  sub     rsp, 0B8h
0x14007af9d  mov     rax, cs:__security_cookie
0x14007afa4  xor     rax, rsp
0x14007afa7  mov     [rsp+0D8h+var_38], rax
0x14007afaf  mov     rbx, rcx
0x14007afb2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007afb9  jnz     loc_14007B60D
0x14007afbf  add     rbx, 0FFFFFFFFFFFFFF60h
0x14007afc6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007afcd  jnz     loc_14007B62B
0x14007afd3  mov     rax, [rbx+6A0h]
0x14007afda  cmp     byte ptr [rax+1FE2h], 0
0x14007afe1  jnz     loc_14007B649
0x14007afe7  mov     rcx, [rbx+4F0h]; pvContextBuffer
0x14007afee  xor     r15d, r15d
0x14007aff1  test    rcx, rcx
0x14007aff4  jnz     loc_14007B68C
0x14007affa  mov     rcx, [rbx+500h]; Handle
0x14007b001  test    rcx, rcx
0x14007b004  jnz     loc_14007B6A4
0x14007b00a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14007b011  cmp     [rbx+1B8h], rdi
0x14007b018  jz      short loc_14007B04B
0x14007b01a  cmp     [rbx+1C0h], rdi
0x14007b021  jz      short loc_14007B04B
0x14007b023  mov     rcx, [rbx+620h]; AsyncContext
0x14007b02a  lea     rdx, [rbx+1B8h]; phContext
0x14007b031  call    cs:__imp_SspiDeleteSecurityContextAsync
0x14007b038  nop     dword ptr [rax+rax+00h]
0x14007b03d  mov     [rbx+1C0h], rdi
0x14007b044  mov     [rbx+1B8h], rdi
0x14007b04b  mov     rcx, [rbx+718h]
0x14007b052  test    rcx, rcx
0x14007b055  jnz     loc_14007B6BC
0x14007b05b  mov     rcx, [rbx+608h]; P
0x14007b062  test    rcx, rcx
0x14007b065  jnz     loc_14007B6CD
0x14007b06b  mov     rcx, [rbx+610h]; P
0x14007b072  test    rcx, rcx
0x14007b075  jnz     loc_14007B6DE
0x14007b07b  mov     rcx, [rbx+618h]; P
0x14007b082  test    rcx, rcx
0x14007b085  jnz     loc_14007B6EF
0x14007b08b  mov     rcx, [rbx+620h]; Handle
0x14007b092  test    rcx, rcx
0x14007b095  jz      short loc_14007B0AA
0x14007b097  call    cs:__imp_SspiFreeAsyncContext
0x14007b09e  nop     dword ptr [rax+rax+00h]
0x14007b0a3  mov     [rbx+620h], r15
0x14007b0aa  mov     rcx, [rbx+650h]; P
0x14007b0b1  test    rcx, rcx
0x14007b0b4  jz      short loc_14007B0C4
0x14007b0b6  xor     edx, edx; Tag
0x14007b0b8  call    cs:__imp_ExFreePoolWithTag
0x14007b0bf  nop     dword ptr [rax+rax+00h]
0x14007b0c4  mov     [rbx+650h], r15
0x14007b0cb  mov     rcx, [rbx+678h]; P
0x14007b0d2  test    rcx, rcx
0x14007b0d5  jz      short loc_14007B0E5
0x14007b0d7  xor     edx, edx; Tag
0x14007b0d9  call    cs:__imp_ExFreePoolWithTag
0x14007b0e0  nop     dword ptr [rax+rax+00h]
0x14007b0e5  mov     [rbx+678h], r15
0x14007b0ec  cmp     [rbx+668h], r15d
0x14007b0f3  jnz     loc_14007B700
0x14007b0f9  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b100  jnz     loc_14007B478
0x14007b106  mov     rcx, [rbx+628h]; P
0x14007b10d  test    rcx, rcx
0x14007b110  jnz     loc_14007B728
0x14007b116  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b11d  jnz     loc_14007B757
0x14007b123  mov     rsi, [rbx+1B0h]
0x14007b12a  mov     [rsp+0D8h+arg_8], rbp
0x14007b132  test    rsi, rsi
0x14007b135  jz      loc_14007B215
0x14007b13b  mov     [rsp+0D8h+arg_10], r12
0x14007b143  mov     [rsp+0D8h+arg_18], r13
0x14007b14b  mov     [rsp+0D8h+var_28], r14
0x14007b153  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b15a  jnz     loc_14007B455
0x14007b160  mov     rax, [rsi+358h]
0x14007b167  mov     r12, r15
0x14007b16a  movzx   r13d, byte ptr [rax+1FE5h]
0x14007b172  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b179  jnz     loc_14007B496
0x14007b17f  mov     eax, [rsi+68h]
0x14007b182  mov     dword ptr [rsp+0D8h+var_A8], eax
0x14007b186  mov     ebp, dword ptr [rsp+0D8h+var_A8]
0x14007b18a  lea     ecx, [rbp-1]
0x14007b18d  test    ecx, ecx
0x14007b18f  jz      loc_140178C04
0x14007b195  mov     eax, ebp
0x14007b197  lock cmpxchg [rsi+68h], ecx
0x14007b19c  mov     r15d, eax
0x14007b19f  mov     dword ptr [rsp+0D8h+var_A8], eax
0x14007b1a3  cmp     r15d, ebp
0x14007b1a6  mov     r15d, 0
0x14007b1ac  jnz     short loc_14007B186
0x14007b1ae  mov     r14, [rsp+0D8h+var_28]
0x14007b1b6  test    r12, r12
0x14007b1b9  jnz     loc_14007B772
0x14007b1bf  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b1c6  mov     r13, [rsp+0D8h+arg_18]
0x14007b1ce  mov     r12, [rsp+0D8h+arg_10]
0x14007b1d6  jnz     loc_14007B4BA
0x14007b1dc  lea     rdx, [rsi+4]; BugCheckParameter2
0x14007b1e0  mov     eax, edi
0x14007b1e2  lock xadd [rdx], eax
0x14007b1e6  dec     eax
0x14007b1e8  cmp     cs:UxDebugCheckRefcount, 0
0x14007b1ef  jnz     loc_14007B412
0x14007b1f5  test    eax, eax
0x14007b1f7  jnz     short loc_14007B201
0x14007b1f9  mov     rcx, rsi
0x14007b1fc  call    UxSslDestroyConfiguration
0x14007b201  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b208  jnz     loc_14007B796
0x14007b20e  mov     [rbx+1B0h], r15
0x14007b215  mov     rsi, [rbx+600h]
0x14007b21c  test    rsi, rsi
0x14007b21f  jnz     loc_14007B564
0x14007b225  mov     rdx, [rbx+180h]; BugCheckParameter2
0x14007b22c  test    rdx, rdx
0x14007b22f  jz      short loc_14007B298
0x14007b231  mov     eax, edi
0x14007b233  lock xadd [rdx], eax
0x14007b237  dec     eax
0x14007b239  cmp     cs:UxDebugCheckRefcount, 0
0x14007b240  jnz     loc_14007B3F6
0x14007b246  test    eax, eax
0x14007b248  jnz     short loc_14007B291
0x14007b24a  mov     rsi, [rbx+180h]
0x14007b251  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b258  jnz     loc_14007B4D5
0x14007b25e  mov     rcx, [rsi+10h]; pvContextBuffer
0x14007b262  test    rcx, rcx
0x14007b265  jz      short loc_14007B273
0x14007b267  call    cs:__imp_FreeContextBuffer
0x14007b26e  nop     dword ptr [rax+rax+00h]
0x14007b273  xor     edx, edx; Tag
0x14007b275  mov     rcx, rsi; P
0x14007b278  call    cs:__imp_ExFreePoolWithTag
0x14007b27f  nop     dword ptr [rax+rax+00h]
0x14007b284  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b28b  jnz     loc_14007B4F3
0x14007b291  mov     [rbx+180h], r15
0x14007b298  mov     rcx, [rbx+190h]; P
0x14007b29f  test    rcx, rcx
0x14007b2a2  jnz     loc_14007B8DD
0x14007b2a8  mov     rcx, [rbx+1A8h]; pvContextBuffer
0x14007b2af  test    rcx, rcx
0x14007b2b2  jnz     loc_14007B8F7
0x14007b2b8  mov     rsi, [rbx+698h]
0x14007b2bf  lea     r8, [rsp+0D8h+var_A8]
0x14007b2c4  mov     edx, cs:UxPodMonitorSlot
0x14007b2ca  mov     rcx, rsi
0x14007b2cd  mov     [rbx+6A0h], r15
0x14007b2d4  mov     [rsp+0D8h+var_A8], r15
0x14007b2d9  call    cs:__imp_PsGetPermanentSiloContext
0x14007b2e0  nop     dword ptr [rax+rax+00h]
0x14007b2e5  test    rsi, rsi
0x14007b2e8  jnz     loc_14007B912
0x14007b2ee  mov     rdx, [rsp+0D8h+var_A8]
0x14007b2f3  add     rdx, 18h; BugCheckParameter2
0x14007b2f7  lock xadd [rdx], edi
0x14007b2fb  dec     edi
0x14007b2fd  cmp     cs:UxDebugCheckRefcount, 0
0x14007b304  jnz     loc_14007B3D9
0x14007b30a  test    edi, edi
0x14007b30c  jz      loc_14007B92B
0x14007b312  mov     [rbx+698h], r15
0x14007b319  mov     dword ptr [rbx+28h], 7
0x14007b320  cmp     dword ptr [rbx+40h], 4
0x14007b324  jnz     loc_14007B94A
0x14007b32a  mov     rax, [rbx+38h]
0x14007b32e  mov     rbp, [rbx+30h]
0x14007b332  mov     rsi, [rax+10h]
0x14007b336  cmp     cs:UxDebugDisableLookaside, 0
0x14007b33d  mov     dword ptr [rbx+40h], 5
0x14007b344  mov     [rbx+38h], r15
0x14007b348  mov     dword ptr [rbx+10h], 61735875h
0x14007b34f  jnz     loc_14007B955
0x14007b355  cmp     cs:UxCompactMode, 0
0x14007b35c  jnz     loc_14007B42E
0x14007b362  mov     edi, [rbx]
0x14007b364  mov     rcx, cs:qword_1401A03D0
0x14007b36b  inc     edi
0x14007b36d  shl     rdi, 7
0x14007b371  add     rdi, rcx
0x14007b374  movzx   eax, byte ptr [rdi+0B0h]
0x14007b37b  test    al, al
0x14007b37d  jz      loc_14007B50E
0x14007b383  mov     rdx, rbx; Entry
0x14007b386  lea     rcx, [rdi+40h]; Lookaside
0x14007b38a  call    cs:__imp_ExFreeToLookasideListEx
0x14007b391  nop     dword ptr [rax+rax+00h]
0x14007b396  test    rsi, rsi
0x14007b399  jz      short loc_14007B3A6
0x14007b39b  mov     rcx, rbp
0x14007b39e  mov     rax, rsi
0x14007b3a1  call    _guard_dispatch_icall
0x14007b3a6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b3ad  jnz     loc_14007B98A
0x14007b3b3  mov     rbp, [rsp+0D8h+arg_8]
0x14007b3bb  mov     rcx, [rsp+0D8h+var_38]
0x14007b3c3  xor     rcx, rsp; StackCookie
0x14007b3c6  call    __security_check_cookie
0x14007b3cb  add     rsp, 0B8h
0x14007b3d2  pop     r15
0x14007b3d4  pop     rdi
0x14007b3d5  pop     rsi
0x14007b3d6  pop     rbx
0x14007b3d7  retn
0x14007b3d9  cmp     edi, 0FFFFFFFFh
0x14007b3dc  jg      loc_14007B30A
0x14007b3e2  movsxd  r9, edi; BugCheckParameter4
0x14007b3e5  mov     ecx, 3; BugCheckParameter1
0x14007b3ea  mov     r8d, 0Fh; BugCheckParameter3
0x14007b3f0  call    UlBugCheckEx
0x14007b3f6  cmp     eax, edi
0x14007b3f8  jg      loc_14007B246
0x14007b3fe  movsxd  r9, eax; BugCheckParameter4
0x14007b401  mov     ecx, 3; BugCheckParameter1
0x14007b406  mov     r8d, 0Ah; BugCheckParameter3
0x14007b40c  call    UlBugCheckEx
0x14007b412  cmp     eax, edi
0x14007b414  jg      loc_14007B1F5
0x14007b41a  movsxd  r9, eax; BugCheckParameter4
0x14007b41d  mov     ecx, 3; BugCheckParameter1
0x14007b422  mov     r8d, 0Fh; BugCheckParameter3
0x14007b428  call    UlBugCheckEx
0x14007b42e  mov     rdi, cs:qword_1401A03D0
0x14007b435  call    cs:__imp_KeGetCurrentNodeNumber
0x14007b43c  nop     dword ptr [rax+rax+00h]
0x14007b441  movzx   r8d, ax
0x14007b445  mov     rdx, rbx
0x14007b448  mov     rcx, rdi
0x14007b44b  call    PplFreeToLookasideListProcessor
0x14007b450  jmp     loc_14007B396
0x14007b455  mov     edx, 35h ; '5'
0x14007b45a  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x14007b45f  mov     ecx, 411h
0x14007b464  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b46b  mov     r9, rsi
0x14007b46e  call    WPP_SF_qD
0x14007b473  jmp     loc_14007B160
0x14007b478  mov     edx, 0C5h
0x14007b47d  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b484  mov     ecx, 411h
0x14007b489  mov     r9, rbx
0x14007b48c  call    WPP_SF_q
0x14007b491  jmp     loc_14007B106
0x14007b496  mov     edx, 94h
0x14007b49b  mov     dword ptr [rsp+0D8h+var_B8], r13d
0x14007b4a0  mov     ecx, 411h
0x14007b4a5  lea     r9, [rsi+10h]
0x14007b4a9  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b4b0  call    WPP_SF_qD
0x14007b4b5  jmp     loc_14007B17F
0x14007b4ba  mov     edx, 95h
0x14007b4bf  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b4c6  mov     ecx, 411h
0x14007b4cb  call    WPP_SF_
0x14007b4d0  jmp     loc_14007B1DC
0x14007b4d5  mov     edx, 75h ; 'u'
0x14007b4da  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14007b4e1  mov     ecx, 411h
0x14007b4e6  mov     r9, rsi
0x14007b4e9  call    WPP_SF_q
0x14007b4ee  jmp     loc_14007B25E
0x14007b4f3  mov     edx, 76h ; 'v'
0x14007b4f8  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14007b4ff  mov     ecx, 411h
0x14007b504  call    WPP_SF_
0x14007b509  jmp     loc_14007B291
0x14007b50e  lea     rdx, [rdi+40h]
0x14007b512  call    PplpLazyInitializeLookasideList
0x14007b517  jmp     loc_14007B383
0x14007b51c  cmp     cs:UxDebugDisableLookaside, 0
0x14007b523  jnz     loc_14007B804
0x14007b529  mov     rcx, cs:qword_1401A0640
0x14007b530  cmp     cs:UxCompactMode, 0
0x14007b537  mov     rdx, rsi
0x14007b53a  jz      short loc_14007B55A
0x14007b53c  call    PnlFreeToLookasideList
0x14007b541  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b548  jnz     loc_14007B8C2
0x14007b54e  mov     [rbx+600h], r15
0x14007b555  jmp     loc_14007B225
0x14007b55a  mov     r8d, [rsi]
0x14007b55d  call    PplFreeToLookasideListProcessor
0x14007b562  jmp     short loc_14007B541
0x14007b564  lea     rdx, [rsi+14h]; BugCheckParameter2
0x14007b568  mov     eax, edi
0x14007b56a  lock xadd [rdx], eax
  ... truncated ...
```
