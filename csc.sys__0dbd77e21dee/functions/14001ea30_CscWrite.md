# CscWrite

- ea: `0x14001ea30`
- end: `0x14001eed8`
- name: `CscWrite`
- size: `1192`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003a00`
- `0x14000e070`
- `0x14000fd40`
- `0x140014888`
- `0x1400169d4`
- `0x1400170cc`
- `0x140018930`
- `0x14001a494`
- `0x14001e980`
- `0x14001ea30`
- `0x14001ef50`
- `0x14001f038`
- `0x14002f010`
- `0x14002f0f0`

## import_xrefs

- `rdbss!RxLowIoGetBufferAddress` at `0x14001ebcb`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001ebcb`
- `rdbss!RxWaitSync` at `0x14001edcc`
- `rdbss!RxWaitSync` at `0x14001edcc`

## pseudocode

```c
__int64 __fastcall CscWrite(PRX_CONTEXT RxContext)
{
  PMRX_FCB pFcb; // rsi
  PMRX_SRV_OPEN pRelevantSrvOpen; // r13
  bool v4; // zf
  bool v5; // r12
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbx
  struct _MRX_FCB_ *v11; // r8
  int v12; // eax
  bool v13; // si
  char v14; // al
  unsigned int StoredStatus; // ebx
  int v16; // esi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  bool v20; // r15
  _QWORD *v21; // r14
  _QWORD *v22; // rax
  int v23; // esi
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  int v28; // [rsp+20h] [rbp-89h]
  PMRX_FCB v29; // [rsp+28h] [rbp-81h]
  int v30; // [rsp+70h] [rbp-39h]
  PMRX_FOBX pFobx; // [rsp+78h] [rbp-31h]
  __int128 v32; // [rsp+80h] [rbp-29h] BYREF
  __int128 v33; // [rsp+90h] [rbp-19h]
  __int64 v34; // [rsp+A0h] [rbp-9h]
  __int128 v35; // [rsp+A8h] [rbp-1h] BYREF

  pFcb = RxContext->pFcb;
  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  pFobx = RxContext->pFobx;
  v30 = (__int64)RxContext->RdbssDbgExtension & 0x1000;
  v34 = 0;
  v4 = RxContext->NonPagedFcb == (PNON_PAGED_FCB)CscDeviceObject;
  v32 = 0;
  v5 = !v4;
  v33 = 0;
  v35 = 0;
  CscGetContextsEx(RxContext, pFcb, &v32);
  CscUpdateAndCaptureConnectionStateEx((__int64)pFcb, (__int64)pRelevantSrvOpen, v6, 1u, (__int64)&v35, 1);
  v10 = v33;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      LOBYTE(v7) = v30 != 0 ? 78 : 89;
      LOBYTE(v9) = v5 ? 89 : 78;
      v29 = pFcb;
      LOBYTE(v28) = v7;
      WPP_SF_ccqqDDDDDi(WPP_GLOBAL_Control->AttachedDevice, v7, v8, v9);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      if ( v10 )
        v11 = *(struct _MRX_FCB_ **)(v10 + 8);
      else
        v11 = 0;
      if ( v10 )
        v12 = *(_DWORD *)(v10 + 24);
      else
        v12 = 0;
      v29 = v11;
      v28 = v12;
      WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, v10);
    }
  }
  v13 = v10 && *(_QWORD *)(v10 + 8);
  v14 = v35;
  if ( (v35 & 0x20) != 0 )
  {
    if ( !RxLowIoGetBufferAddress(RxContext) && *((_DWORD *)&RxContext->9 + 42) )
    {
      StoredStatus = -1073741670;
      v16 = 2243;
      goto LABEL_67;
    }
    v14 = v35;
  }
  if ( (BYTE1(v35) & 0x40) != 0 || (v14 & 0x10) != 0 && (BYTE1(v35) & 2) != 0 )
  {
    v16 = 2254;
    StoredStatus = (BYTE2(v35) & 1) != 0 ? -1073741628 : -1073741300;
    goto LABEL_67;
  }
  if ( (*(_DWORD *)&pFobx[1].NodeTypeCode & 2) != 0 )
  {
    v16 = 2266;
LABEL_27:
    StoredStatus = -1073741528;
    goto LABEL_67;
  }
  if ( ((__int64)pRelevantSrvOpen->Key & 0x404) != 0 )
  {
    v16 = 2273;
    goto LABEL_27;
  }
  CscWritePreventOplockBreak(RxContext, &v35);
  if ( (v35 & 0x10) == 0 || v13 )
  {
    if ( v10 && (*(_DWORD *)(v10 + 24) & 0x809) != 0 )
    {
      v16 = 2293;
      StoredStatus = -1073741811;
    }
    else
    {
      StoredStatus = 0;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      if ( v5 && (v35 & 0x10) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_a14d127135023115663fdf7ff6985b18_Traceguids);
        }
        if ( (v35 & 0x20) != 0 && v30 )
        {
          v22 = (_QWORD *)CscReadWriteAsyncContextAllocate(RxContext, v17, 8);
          v21 = v22;
          if ( v22 )
          {
            *((_WORD *)&RxContext->9 + 61) &= ~8u;
            v22[2] = *((_QWORD *)&RxContext->9 + 16);
            *((_QWORD *)&RxContext->9 + 16) = CscWriteCompletion;
            *(_DWORD *)v22 = 7924393;
            RxContext->WorkQueueItem.Parameter = v22;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_a14d127135023115663fdf7ff6985b18_Traceguids);
            }
            LODWORD(RxContext->RdbssDbgExtension) &= ~0x1000u;
          }
        }
        v23 = (__int64)RxContext->RdbssDbgExtension & 0x1000;
        v20 = v23 != 0;
        if ( RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[19].Blink )
        {
          if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
          {
            StoredStatus = -1073741536;
          }
          else
          {
            *(_OWORD *)&RxContext->MRxContext[2] = 0;
            *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
            RxContext->ResumeRoutine = 0;
            StoredStatus = ((__int64 (__fastcall *)(PRX_CONTEXT, __int64, __int64, __int64))RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[19].Blink)(
                             RxContext,
                             v17,
                             v18,
                             v19);
            if ( StoredStatus == 259 )
            {
              if ( v23 )
              {
                v16 = 2359;
                goto LABEL_67;
              }
              RxWaitSync(RxContext);
              StoredStatus = RxContext->StoredStatus;
            }
          }
        }
        else
        {
          StoredStatus = -1073741822;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            66,
            WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
            StoredStatus);
        }
      }
      v16 = 0;
      if ( (v35 & 0x20) != 0 )
      {
        StoredStatus = CscWriteFinalize(RxContext);
        if ( v21 )
        {
          v26 = v21[2];
          *((_QWORD *)&RxContext->9 + 16) = v26;
          CscReadWriteAsyncContextFree(v26, v21, v24, v25, v28, v29);
          RxContext->WorkQueueItem.Parameter = 0;
        }
      }
      if ( !v20 && v30 )
        LODWORD(RxContext->RdbssDbgExtension) |= 0x1000u;
    }
  }
  else
  {
    v16 = 2286;
    StoredStatus = -1073741108;
  }
LABEL_67:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      67,
      WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
      StoredStatus,
      v16,
      0);
  return StoredStatus;
}

```

## disassembly

```asm
0x14001ea30  push    rbp
0x14001ea32  push    rbx
0x14001ea33  push    rsi
0x14001ea34  push    rdi
0x14001ea35  push    r12
0x14001ea37  push    r13
0x14001ea39  push    r14
0x14001ea3b  push    r15
0x14001ea3d  lea     rbp, [rsp-1Fh]
0x14001ea42  sub     rsp, 0C8h
0x14001ea49  mov     rax, cs:__security_cookie
0x14001ea50  xor     rax, rsp
0x14001ea53  mov     [rbp+57h+var_48], rax
0x14001ea57  mov     rax, [rcx+40h]
0x14001ea5b  lea     r8, [rbp+57h+var_80]
0x14001ea5f  mov     rsi, [rcx+38h]
0x14001ea63  xorps   xmm0, xmm0
0x14001ea66  mov     r13, [rcx+48h]
0x14001ea6a  mov     rdx, rsi
0x14001ea6d  mov     r14, [rcx+230h]
0x14001ea74  mov     rdi, rcx
0x14001ea77  mov     r15d, [rcx+238h]
0x14001ea7e  mov     [rbp+57h+var_88], rax
0x14001ea82  mov     eax, [rcx+78h]
0x14001ea85  and     eax, 1000h
0x14001ea8a  mov     [rbp+57h+var_90], eax
0x14001ea8d  xor     eax, eax
0x14001ea8f  mov     [rbp+57h+var_60], rax
0x14001ea93  mov     rax, cs:CscDeviceObject
0x14001ea9a  cmp     [rcx+50h], rax
0x14001ea9e  movups  [rbp+57h+var_80], xmm0
0x14001eaa2  setnz   r12b
0x14001eaa6  movups  [rbp+57h+var_70], xmm0
0x14001eaaa  movups  [rbp+57h+var_58], xmm0
0x14001eaae  call    CscGetContextsEx
0x14001eab3  lea     rax, [rbp+57h+var_58]
0x14001eab7  mov     byte ptr [rsp+100h+var_D8], 1
0x14001eabc  mov     r8, rcx
0x14001eabf  mov     [rsp+100h+var_E0], rax
0x14001eac4  mov     r9b, 1
0x14001eac7  mov     rdx, r13
0x14001eaca  mov     rcx, rsi
0x14001eacd  call    CscUpdateAndCaptureConnectionStateEx
0x14001ead2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ead9  lea     rax, WPP_GLOBAL_Control
0x14001eae0  mov     rbx, qword ptr [rbp+57h+var_70]
0x14001eae4  cmp     rcx, rax
0x14001eae7  jz      loc_14001EBAD
0x14001eaed  mov     eax, [rcx+2Ch]
0x14001eaf0  test    al, 20h
0x14001eaf2  jz      short loc_14001EB58
0x14001eaf4  mov     eax, [rbp+57h+var_90]
0x14001eaf7  mov     rcx, [rcx+18h]
0x14001eafb  neg     eax
0x14001eafd  mov     [rsp+100h+var_A0], r14
0x14001eb02  mov     al, r12b
0x14001eb05  sbb     dl, dl
0x14001eb07  mov     [rsp+100h+var_A8], r15d
0x14001eb0c  and     dl, 0F5h
0x14001eb0f  add     dl, 59h ; 'Y'
0x14001eb12  neg     al
0x14001eb14  mov     eax, [r13+48h]
0x14001eb18  mov     [rsp+100h+var_B0], eax
0x14001eb1c  sbb     r9b, r9b
0x14001eb1f  mov     eax, [rsi+0A0h]
0x14001eb25  and     r9b, 0Bh
0x14001eb29  mov     [rsp+100h+var_B8], eax
0x14001eb2d  add     r9b, 4Eh ; 'N'
0x14001eb31  mov     eax, [rsi+0A4h]
0x14001eb37  mov     [rsp+100h+var_C0], eax
0x14001eb3b  mov     eax, [rsi+9Ch]
0x14001eb41  mov     [rsp+100h+var_C8], eax
0x14001eb45  mov     [rsp+100h+var_D0], r13
0x14001eb4a  mov     [rsp+100h+var_D8], rsi
0x14001eb4f  mov     byte ptr [rsp+100h+var_E0], dl
0x14001eb53  call    WPP_SF_ccqqDDDDDi
0x14001eb58  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb5f  lea     rax, WPP_GLOBAL_Control
0x14001eb66  cmp     rcx, rax
0x14001eb69  jz      short loc_14001EBAD
0x14001eb6b  mov     eax, [rcx+2Ch]
0x14001eb6e  test    al, 40h
0x14001eb70  jz      short loc_14001EBAD
0x14001eb72  test    rbx, rbx
0x14001eb75  jz      short loc_14001EB7D
0x14001eb77  mov     r8, [rbx+8]
0x14001eb7b  jmp     short loc_14001EB80
0x14001eb7d  xor     r8d, r8d
0x14001eb80  test    rbx, rbx
0x14001eb83  jz      short loc_14001EB8A
0x14001eb85  mov     eax, [rbx+18h]
0x14001eb88  jmp     short loc_14001EB8C
0x14001eb8a  xor     eax, eax
0x14001eb8c  mov     rcx, [rcx+18h]
0x14001eb90  mov     edx, 3Fh ; '?'
0x14001eb95  mov     [rsp+100h+var_D8], r8
0x14001eb9a  mov     r9, rbx
0x14001eb9d  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001eba4  mov     dword ptr [rsp+100h+var_E0], eax
0x14001eba8  call    WPP_SF_qdq
0x14001ebad  test    rbx, rbx
0x14001ebb0  jz      short loc_14001EBBE
0x14001ebb2  cmp     qword ptr [rbx+8], 0
0x14001ebb7  jz      short loc_14001EBBE
0x14001ebb9  mov     sil, 1
0x14001ebbc  jmp     short loc_14001EBC1
0x14001ebbe  xor     sil, sil
0x14001ebc1  mov     al, byte ptr [rbp+57h+var_58]
0x14001ebc4  test    al, 20h
0x14001ebc6  jz      short loc_14001EBF6
0x14001ebc8  mov     rcx, rdi; RxContext
0x14001ebcb  call    cs:__imp_RxLowIoGetBufferAddress
0x14001ebd2  nop     dword ptr [rax+rax+00h]
0x14001ebd7  test    rax, rax
0x14001ebda  jnz     short loc_14001EBF3
0x14001ebdc  cmp     [rdi+238h], eax
0x14001ebe2  jz      short loc_14001EBF3
0x14001ebe4  mov     ebx, 0C000009Ah
0x14001ebe9  mov     esi, 8C3h
0x14001ebee  jmp     loc_14001EE77
0x14001ebf3  mov     al, byte ptr [rbp+57h+var_58]
0x14001ebf6  test    byte ptr [rbp+57h+var_58+1], 40h
0x14001ebfa  jnz     loc_14001EE5D
0x14001ec00  test    al, 10h
0x14001ec02  jz      short loc_14001EC0E
0x14001ec04  test    byte ptr [rbp+57h+var_58+1], 2
0x14001ec08  jnz     loc_14001EE5D
0x14001ec0e  mov     rax, [rbp+57h+var_88]
0x14001ec12  mov     eax, [rax+48h]
0x14001ec15  test    al, 2
0x14001ec17  jz      short loc_14001EC28
0x14001ec19  mov     esi, 8DAh
0x14001ec1e  mov     ebx, 0C0000128h
0x14001ec23  jmp     loc_14001EE77
0x14001ec28  test    dword ptr [r13+48h], 404h
0x14001ec30  jz      short loc_14001EC39
0x14001ec32  mov     esi, 8E1h
0x14001ec37  jmp     short loc_14001EC1E
0x14001ec39  lea     rdx, [rbp+57h+var_58]
0x14001ec3d  mov     rcx, rdi
0x14001ec40  call    CscWritePreventOplockBreak
0x14001ec45  mov     cl, byte ptr [rbp+57h+var_58]
0x14001ec48  shr     cl, 4
0x14001ec4b  and     cl, 1
0x14001ec4e  jz      short loc_14001EC64
0x14001ec50  test    sil, sil
0x14001ec53  jnz     short loc_14001EC64
0x14001ec55  mov     esi, 8EEh
0x14001ec5a  mov     ebx, 0C00002CCh
0x14001ec5f  jmp     loc_14001EE77
0x14001ec64  test    rbx, rbx
0x14001ec67  jz      short loc_14001EC81
0x14001ec69  test    dword ptr [rbx+18h], 809h
0x14001ec70  jz      short loc_14001EC81
0x14001ec72  mov     esi, 8F5h
0x14001ec77  mov     ebx, 0C000000Dh
0x14001ec7c  jmp     loc_14001EE77
0x14001ec81  xor     ebx, ebx
0x14001ec83  xor     r9d, r9d
0x14001ec86  xor     r15b, r15b
0x14001ec89  xor     r14d, r14d
0x14001ec8c  test    r12b, r12b
0x14001ec8f  jz      loc_14001EE13
0x14001ec95  test    cl, cl
0x14001ec97  jnz     loc_14001EE13
0x14001ec9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eca4  lea     r12, WPP_GLOBAL_Control
0x14001ecab  cmp     rcx, r12
0x14001ecae  jz      short loc_14001ECCA
0x14001ecb0  mov     eax, [rcx+2Ch]
0x14001ecb3  test    al, 40h
0x14001ecb5  jz      short loc_14001ECCA
0x14001ecb7  mov     rcx, [rcx+18h]
0x14001ecbb  lea     edx, [rbx+40h]
0x14001ecbe  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001ecc5  call    WPP_SF_
0x14001ecca  test    byte ptr [rbp+57h+var_58], 20h
0x14001ecce  jz      short loc_14001ED4C
0x14001ecd0  cmp     [rbp+57h+var_90], ebx
0x14001ecd3  jz      short loc_14001ED4C
0x14001ecd5  mov     r8d, 8
0x14001ecdb  mov     rcx, rdi
0x14001ecde  call    CscReadWriteAsyncContextAllocate
0x14001ece3  mov     r14, rax
0x14001ece6  test    rax, rax
0x14001ece9  jnz     short loc_14001ED19
0x14001eceb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ecf2  cmp     rcx, r12
0x14001ecf5  jz      short loc_14001ED12
0x14001ecf7  mov     eax, [rcx+2Ch]
0x14001ecfa  test    al, 40h
0x14001ecfc  jz      short loc_14001ED12
0x14001ecfe  mov     rcx, [rcx+18h]
0x14001ed02  lea     edx, [r14+41h]
0x14001ed06  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001ed0d  call    WPP_SF_
0x14001ed12  btr     dword ptr [rdi+78h], 0Ch
0x14001ed17  jmp     short loc_14001ED4C
0x14001ed19  mov     eax, 0FFF7h
0x14001ed1e  and     [rdi+20Ah], ax
0x14001ed25  mov     rax, [rdi+210h]
0x14001ed2c  mov     [r14+10h], rax
0x14001ed30  lea     rax, CscWriteCompletion
0x14001ed37  mov     [rdi+210h], rax
0x14001ed3e  mov     dword ptr [r14], 78EAA9h
0x14001ed45  mov     [rdi+110h], r14
0x14001ed4c  mov     rax, [rdi+50h]
0x14001ed50  mov     esi, [rdi+78h]
0x14001ed53  and     esi, 1000h
0x14001ed59  mov     rcx, [rax+160h]
0x14001ed60  setnz   r15b
0x14001ed64  cmp     [rcx+138h], rbx
0x14001ed6b  jnz     short loc_14001ED74
0x14001ed6d  mov     ebx, 0C0000002h
0x14001ed72  jmp     short loc_14001EDE5
0x14001ed74  mov     eax, [rdi+80h]
0x14001ed7a  test    al, 2
0x14001ed7c  jnz     short loc_14001EDE0
0x14001ed7e  xor     eax, eax
0x14001ed80  xorps   xmm0, xmm0
0x14001ed83  movups  xmmword ptr [rdi+0D0h], xmm0
0x14001ed8a  movups  xmmword ptr [rdi+0E0h], xmm0
0x14001ed91  mov     [rdi+0F0h], rax
0x14001ed98  mov     rax, [rdi+50h]
0x14001ed9c  mov     rcx, [rax+160h]
0x14001eda3  mov     rax, [rcx+138h]
0x14001edaa  mov     rcx, rdi
0x14001edad  call    _guard_dispatch_icall
0x14001edb2  mov     ebx, eax
0x14001edb4  cmp     eax, 103h
0x14001edb9  jnz     short loc_14001EDE5
0x14001edbb  test    esi, esi
0x14001edbd  jz      short loc_14001EDC9
0x14001edbf  mov     esi, 937h
0x14001edc4  jmp     loc_14001EE77
0x14001edc9  mov     rcx, rdi
0x14001edcc  call    cs:__imp_RxWaitSync
0x14001edd3  nop     dword ptr [rax+rax+00h]
0x14001edd8  mov     ebx, [rdi+0B0h]
0x14001edde  jmp     short loc_14001EDE5
0x14001ede0  mov     ebx, 0C0000120h
0x14001ede5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001edec  cmp     rcx, r12
0x14001edef  jz      short loc_14001EE10
0x14001edf1  mov     eax, [rcx+2Ch]
0x14001edf4  test    al, 40h
0x14001edf6  jz      short loc_14001EE10
0x14001edf8  mov     rcx, [rcx+18h]
0x14001edfc  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001ee03  mov     edx, 42h ; 'B'
0x14001ee08  mov     r9d, ebx
0x14001ee0b  call    WPP_SF_d
0x14001ee10  mov     r9d, ebx
0x14001ee13  xor     esi, esi
0x14001ee15  test    byte ptr [rbp+57h+var_58], 20h
0x14001ee19  jz      short loc_14001EE4C
0x14001ee1b  lea     r8, [rbp+57h+var_58]
0x14001ee1f  mov     rcx, rdi; RxContext
0x14001ee22  lea     rdx, [rbp+57h+var_80]
0x14001ee26  call    CscWriteFinalize
0x14001ee2b  mov     ebx, eax
0x14001ee2d  test    r14, r14
0x14001ee30  jz      short loc_14001EE4C
0x14001ee32  mov     rcx, [r14+10h]
0x14001ee36  mov     rdx, r14
0x14001ee39  mov     [rdi+210h], rcx
0x14001ee40  call    CscReadWriteAsyncContextFree
0x14001ee45  mov     [rdi+110h], rsi
0x14001ee4c  test    r15b, r15b
0x14001ee4f  jnz     short loc_14001EE77
0x14001ee51  cmp     [rbp+57h+var_90], esi
0x14001ee54  jz      short loc_14001EE77
0x14001ee56  bts     dword ptr [rdi+78h], 0Ch
0x14001ee5b  jmp     short loc_14001EE77
0x14001ee5d  mov     al, byte ptr [rbp+57h+var_58+2]
0x14001ee60  mov     esi, 8CEh
0x14001ee65  and     al, 1
0x14001ee67  neg     al
0x14001ee69  sbb     ebx, ebx
0x14001ee6b  and     ebx, 0FFFFFEB8h
0x14001ee71  add     ebx, 0C000020Ch
0x14001ee77  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee7e  lea     rax, WPP_GLOBAL_Control
0x14001ee85  cmp     rcx, rax
0x14001ee88  jz      short loc_14001EEB5
0x14001ee8a  mov     eax, [rcx+2Ch]
0x14001ee8d  test    al, 20h
0x14001ee8f  jz      short loc_14001EEB5
0x14001ee91  mov     rcx, [rcx+18h]
0x14001ee95  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001ee9c  mov     edx, 43h ; 'C'
0x14001eea1  mov     dword ptr [rsp+100h+var_D8], 0
0x14001eea9  mov     r9d, ebx
0x14001eeac  mov     dword ptr [rsp+100h+var_E0], esi
0x14001eeb0  call    WPP_SF_DDd
0x14001eeb5  mov     eax, ebx
0x14001eeb7  mov     rcx, [rbp+57h+var_48]
0x14001eebb  xor     rcx, rsp; StackCookie
0x14001eebe  call    __security_check_cookie
0x14001eec3  add     rsp, 0C8h
  ... truncated ...
```
