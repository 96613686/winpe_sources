# MRxSmbInitUnwind

- ea: `0x140080ce4`
- end: `0x140081167`
- name: `MRxSmbInitUnwind`
- size: `1155`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14007fd3c`
- `0x140081170`

## callees

- `0x14002834c`
- `0x140039fa8`
- `0x14003afa8`
- `0x14003b37c`
- `0x14003b60c`
- `0x14003b87c`
- `0x140041748`
- `0x1400417ec`
- `0x1400432d8`
- `0x14004d4b8`
- `0x140054ad4`
- `0x140080ce4`
- `0x1400811d8`
- `0x140082160`
- `0x140082428`
- `0x140087850`
- `0x140087d5c`
- `0x14008c184`
- `0x14008cef0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140081041`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140081054`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140081067`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400810f2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140081041`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140081054`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140081067`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400810f2`
- `ntoskrnl!EtwUnregister` at `0x140080eb3`
- `ntoskrnl!EtwUnregister` at `0x140080eb3`
- `ntoskrnl!IoUnregisterFileSystem` at `0x140080df1`
- `ntoskrnl!IoUnregisterFileSystem` at `0x140080df1`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140080d62`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140080d62`
- `ntoskrnl!ZwClose` at `0x140080e4a`
- `ntoskrnl!ZwClose` at `0x140080e4a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140080ffa`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140080ffa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080f54`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080f54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080fb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080fd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081082`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400810aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400810d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081111`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080fb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080fd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081082`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400810aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400810d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081111`
- `ntoskrnl!PcwUnregister` at `0x140080d81`
- `ntoskrnl!PcwUnregister` at `0x140080d81`
- `rdbss!RxUnregisterMinirdr` at `0x140080da8`
- `rdbss!RxUnregisterMinirdr` at `0x140080e13`
- `rdbss!RxUnregisterMinirdr` at `0x140080da8`
- `rdbss!RxUnregisterMinirdr` at `0x140080e13`
- `rdbss!RxNameCacheFinalize` at `0x140080e04`
- `rdbss!RxNameCacheFinalize` at `0x140080e04`

## pseudocode

```c
void __fastcall MRxSmbInitUnwind(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  struct _RDBSS_DEVICE_OBJECT *v10; // rbx
  struct _RDBSS_DEVICE_OBJECT *NextDevice; // rsi
  __int64 v12; // rdi
  unsigned int i; // edi
  char *v14; // rsi
  __int64 v15; // rbx
  void *v16; // rcx
  void *v17; // rcx

  if ( a2 > 5 )
  {
    v6 = a2 - 6;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 != 1 )
              goto LABEL_39;
            SmbCompressionCleanup();
            if ( qword_140070B40 )
              ExUnsubscribeWnfStateChange();
            qword_140070B40 = 0;
          }
          if ( MRxSmbShareCounters )
          {
            PcwUnregister(MRxSmbShareCounters);
            MRxSmbShareCounters = 0;
          }
        }
      }
      MRxSmbTearDownConnectionEngine(a1);
    }
    MRxSmbTearDownMm();
    goto LABEL_21;
  }
  if ( a2 == 5 )
  {
LABEL_21:
    RxUnregisterMinirdr(MRxMailslotDeviceObject);
    goto LABEL_22;
  }
  if ( !a2 )
    goto LABEL_34;
  v3 = a2 - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( !v5 )
      {
LABEL_28:
        SmbWskProviderTerminate();
        SmbQuicProviderTerminate();
        if ( !_InterlockedCompareExchange(&SmbdInitingOrDeiniting, 2, 0) )
        {
          if ( SmbdHandle )
          {
            ZwClose(SmbdHandle);
            SmbdHandle = 0;
            SmbdFastDispatch = 0;
          }
          _InterlockedExchange(&SmbdInitingOrDeiniting, 0);
        }
        MRxSmbUninitializeGlobalTransport();
        goto LABEL_33;
      }
      if ( v5 != 1 )
        goto LABEL_39;
    }
LABEL_22:
    v10 = *(struct _RDBSS_DEVICE_OBJECT **)(a1 + 8);
    if ( v10 )
    {
      do
      {
        NextDevice = (struct _RDBSS_DEVICE_OBJECT *)v10->DeviceObject.NextDevice;
        if ( (unsigned int)MRxSmbIsMrxSmbDeviceObjectType(v10) )
        {
          v12 = MRxSmbCastToMrxSmbDeviceObject();
          UninitialializeSubRdrDialectTable(v12);
          MRxSmbUninitializeTransportArrayInstance(v12);
          if ( (*(_BYTE *)(v12 + 1314) & 2) != 0 )
            IoUnregisterFileSystem(&v10->DeviceObject);
          RxNameCacheFinalize((PNAME_CACHE_CONTROL)(v12 + 2416));
        }
        RxUnregisterMinirdr(v10);
        v10 = NextDevice;
      }
      while ( NextDevice );
    }
    goto LABEL_28;
  }
LABEL_33:
  SmbCamUnload();
LABEL_34:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids);
  }
  EtwUnregister(Microsoft_Windows_Networking_CorrelationHandle);
  Microsoft_Windows_Networking_CorrelationHandle = 0;
  TlgUnregisterAggregateProvider(&dword_140070128);
  McGenEventUnregister_EtwUnregister();
  TlgUnregisterAggregateProvider(&dword_1400700C0);
  WppCleanupKm();
LABEL_39:
  RxCeDeinitializeCryptoSupport();
  if ( stru_140070F60.Buffer )
  {
    ExFreePoolWithTag(stru_140070F60.Buffer - 6, 0x6D536643u);
    stru_140070F60.Buffer = 0;
    *(_DWORD *)&stru_140070F60.Length = 0;
  }
  if ( stru_140070F70.Buffer )
  {
    ExFreePoolWithTag(stru_140070F70.Buffer - 6, 0x6D536643u);
    stru_140070F70.Buffer = 0;
    *(_DWORD *)&stru_140070F70.Length = 0;
  }
  ExAcquirePushLockExclusiveEx(&qword_14007D0D8, 0);
  if ( P )
  {
    for ( i = 0; i < dword_14007D0E8; ++i )
    {
      v14 = (char *)P;
      v15 = 32LL * i;
      v16 = *(void **)((char *)P + v15 + 24);
      if ( v16 )
      {
        ExFreePoolWithTag(v16, 0x63437852u);
        *(_QWORD *)&v14[v15 + 24] = 0;
      }
      v17 = *(void **)&v14[v15];
      if ( v17 )
      {
        ExFreePoolWithTag(v17, 0x63437852u);
        *(_QWORD *)&v14[v15] = 0;
      }
    }
    ExFreePoolWithTag(P, 0x63437852u);
    P = 0;
    dword_14007D0E8 = 0;
  }
  ExReleasePushLockExclusiveEx(&qword_14007D0D8, 0);
  ClearTargetServerExceptionList(&qword_14007D250, byte_14007D258, &qword_14007D248);
  ClearTargetServerExceptionList(&qword_14007D270, &word_14007D278, &qword_14007D268);
  RtlFreeUnicodeString(&MRxSmbRemoteBootMachineName);
  RtlFreeUnicodeString(&MRxSmbRemoteBootMachineDomain);
  RtlFreeUnicodeString(&MRxSmbRemoteBootMachinePassword);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6D536643u);
  DestinationString.Buffer = 0;
  *(_DWORD *)&DestinationString.Length = 0;
  if ( stru_140070F40.Buffer )
    ExFreePoolWithTag(stru_140070F40.Buffer, 0x6D536643u);
  stru_140070F40.Buffer = 0;
  *(_DWORD *)&stru_140070F40.Length = 0;
  if ( stru_140070F50.Buffer )
    ExFreePoolWithTag(stru_140070F50.Buffer, 0x6D536643u);
  stru_140070F50.Buffer = 0;
  *(_DWORD *)&stru_140070F50.Length = 0;
  RtlFreeUnicodeString(&SmbCeContext);
  if ( MRxSmbLegacyPerfCtrs )
  {
    ExFreePoolWithTag(MRxSmbLegacyPerfCtrs, 0x6D537250u);
    MRxSmbLegacyPerfCtrs = 0;
  }
  if ( RdrPerfBlockLookasideList )
  {
    PplDestroyLookasideList(RdrPerfBlockLookasideList, 0x6D537250u);
    RdrPerfBlockLookasideList = 0;
  }
  if ( RxsmbdAsyncSendContextLookasideList )
  {
    PplDestroyLookasideList(RxsmbdAsyncSendContextLookasideList, 0x64437852u);
    RxsmbdAsyncSendContextLookasideList = 0;
  }
}

```

## disassembly

```asm
0x140080ce4  push    rbx
0x140080ce6  push    rbp
0x140080ce7  push    rsi
0x140080ce8  push    rdi
0x140080ce9  push    r14
0x140080ceb  sub     rsp, 20h
0x140080cef  xor     ebp, ebp
0x140080cf1  mov     rbx, rcx
0x140080cf4  lea     r14d, [rbp+2]
0x140080cf8  cmp     edx, 5
0x140080cfb  jg      short loc_140080D34
0x140080cfd  jz      loc_140080DA1
0x140080d03  test    edx, edx
0x140080d05  jz      loc_140080E76
0x140080d0b  sub     edx, 1
0x140080d0e  jz      loc_140080E71
0x140080d14  sub     edx, 1
0x140080d17  jz      loc_140080DB4
0x140080d1d  sub     edx, 1
0x140080d20  jz      loc_140080E27
0x140080d26  cmp     edx, 1
0x140080d29  jz      loc_140080DB4
0x140080d2f  jmp     loc_140080EE8
0x140080d34  sub     edx, 6
0x140080d37  jz      short loc_140080D9C
0x140080d39  sub     edx, 1
0x140080d3c  jz      short loc_140080D94
0x140080d3e  sub     edx, 1
0x140080d41  jz      short loc_140080D94
0x140080d43  sub     edx, 1
0x140080d46  jz      short loc_140080D75
0x140080d48  cmp     edx, 1
0x140080d4b  jnz     loc_140080EE8
0x140080d51  call    SmbCompressionCleanup
0x140080d56  mov     rcx, cs:qword_140070B40
0x140080d5d  test    rcx, rcx
0x140080d60  jz      short loc_140080D6E
0x140080d62  call    cs:__imp_ExUnsubscribeWnfStateChange
0x140080d69  nop     dword ptr [rax+rax+00h]
0x140080d6e  mov     cs:qword_140070B40, rbp
0x140080d75  mov     rcx, cs:MRxSmbShareCounters; Registration
0x140080d7c  test    rcx, rcx
0x140080d7f  jz      short loc_140080D94
0x140080d81  call    cs:__imp_PcwUnregister
0x140080d88  nop     dword ptr [rax+rax+00h]
0x140080d8d  mov     cs:MRxSmbShareCounters, rbp
0x140080d94  mov     rcx, rbx
0x140080d97  call    MRxSmbTearDownConnectionEngine
0x140080d9c  call    MRxSmbTearDownMm
0x140080da1  mov     rcx, cs:MRxMailslotDeviceObject; RxDeviceObject
0x140080da8  call    cs:__imp_RxUnregisterMinirdr
0x140080daf  nop     dword ptr [rax+rax+00h]
0x140080db4  mov     rbx, [rbx+8]
0x140080db8  test    rbx, rbx
0x140080dbb  jz      short loc_140080E27
0x140080dbd  mov     rsi, [rbx+10h]
0x140080dc1  mov     rcx, rbx
0x140080dc4  call    MRxSmbIsMrxSmbDeviceObjectType
0x140080dc9  test    eax, eax
0x140080dcb  jz      short loc_140080E10
0x140080dcd  call    MRxSmbCastToMrxSmbDeviceObject
0x140080dd2  mov     rcx, rax
0x140080dd5  mov     rdi, rax
0x140080dd8  call    UninitialializeSubRdrDialectTable
0x140080ddd  mov     rcx, rdi
0x140080de0  call    MRxSmbUninitializeTransportArrayInstance
0x140080de5  test    [rdi+522h], r14b
0x140080dec  jz      short loc_140080DFD
0x140080dee  mov     rcx, rbx; DeviceObject
0x140080df1  call    cs:__imp_IoUnregisterFileSystem
0x140080df8  nop     dword ptr [rax+rax+00h]
0x140080dfd  lea     rcx, [rdi+970h]; NameCacheCtl
0x140080e04  call    cs:__imp_RxNameCacheFinalize
0x140080e0b  nop     dword ptr [rax+rax+00h]
0x140080e10  mov     rcx, rbx; RxDeviceObject
0x140080e13  call    cs:__imp_RxUnregisterMinirdr
0x140080e1a  nop     dword ptr [rax+rax+00h]
0x140080e1f  mov     rbx, rsi
0x140080e22  test    rsi, rsi
0x140080e25  jnz     short loc_140080DBD
0x140080e27  call    SmbWskProviderTerminate
0x140080e2c  call    SmbQuicProviderTerminate
0x140080e31  xor     eax, eax
0x140080e33  lock cmpxchg cs:SmbdInitingOrDeiniting, r14d
0x140080e3c  jnz     short loc_140080E6C
0x140080e3e  mov     rcx, cs:SmbdHandle; Handle
0x140080e45  test    rcx, rcx
0x140080e48  jz      short loc_140080E64
0x140080e4a  call    cs:__imp_ZwClose
0x140080e51  nop     dword ptr [rax+rax+00h]
0x140080e56  mov     cs:SmbdHandle, rbp
0x140080e5d  mov     cs:SmbdFastDispatch, rbp
0x140080e64  mov     eax, ebp
0x140080e66  xchg    eax, cs:SmbdInitingOrDeiniting
0x140080e6c  call    MRxSmbUninitializeGlobalTransport
0x140080e71  call    SmbCamUnload
0x140080e76  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140080e7d  lea     rax, WPP_GLOBAL_Control
0x140080e84  cmp     rcx, rax
0x140080e87  jz      short loc_140080EAC
0x140080e89  mov     eax, [rcx+2Ch]
0x140080e8c  test    r14b, al
0x140080e8f  jz      short loc_140080EAC
0x140080e91  cmp     [rcx+29h], r14b
0x140080e95  jb      short loc_140080EAC
0x140080e97  mov     rcx, [rcx+18h]
0x140080e9b  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x140080ea2  mov     edx, 21h ; '!'
0x140080ea7  call    WPP_SF_
0x140080eac  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140080eb3  call    cs:__imp_EtwUnregister
0x140080eba  nop     dword ptr [rax+rax+00h]
0x140080ebf  lea     rcx, dword_140070128
0x140080ec6  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, rbp
0x140080ecd  call    TlgUnregisterAggregateProvider
0x140080ed2  call    McGenEventUnregister_EtwUnregister
0x140080ed7  lea     rcx, dword_1400700C0
0x140080ede  call    TlgUnregisterAggregateProvider
0x140080ee3  call    WppCleanupKm
0x140080ee8  call    RxCeDeinitializeCryptoSupport
0x140080eed  mov     rcx, cs:stru_140070F60.Buffer
0x140080ef4  mov     r14d, 6D536643h
0x140080efa  test    rcx, rcx
0x140080efd  jz      short loc_140080F1F
0x140080eff  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x140080f03  mov     edx, r14d; Tag
0x140080f06  call    cs:__imp_ExFreePoolWithTag
0x140080f0d  nop     dword ptr [rax+rax+00h]
0x140080f12  mov     cs:stru_140070F60.Buffer, rbp
0x140080f19  mov     dword ptr cs:stru_140070F60.Length, ebp
0x140080f1f  mov     rcx, cs:stru_140070F70.Buffer
0x140080f26  test    rcx, rcx
0x140080f29  jz      short loc_140080F4B
0x140080f2b  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x140080f2f  mov     edx, r14d; Tag
0x140080f32  call    cs:__imp_ExFreePoolWithTag
0x140080f39  nop     dword ptr [rax+rax+00h]
0x140080f3e  mov     cs:stru_140070F70.Buffer, rbp
0x140080f45  mov     dword ptr cs:stru_140070F70.Length, ebp
0x140080f4b  xor     edx, edx
0x140080f4d  lea     rcx, qword_14007D0D8
0x140080f54  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140080f5b  nop     dword ptr [rax+rax+00h]
0x140080f60  cmp     cs:P, rbp
0x140080f67  jz      loc_140080FF1
0x140080f6d  cmp     cs:dword_14007D0E8, ebp
0x140080f73  mov     edi, ebp
0x140080f75  jz      short loc_140080FCC
0x140080f77  mov     rsi, cs:P
0x140080f7e  mov     ebx, edi
0x140080f80  shl     rbx, 5
0x140080f84  mov     rcx, [rbx+rsi+18h]; P
0x140080f89  test    rcx, rcx
0x140080f8c  jz      short loc_140080FA4
0x140080f8e  mov     edx, 63437852h; Tag
0x140080f93  call    cs:__imp_ExFreePoolWithTag
0x140080f9a  nop     dword ptr [rax+rax+00h]
0x140080f9f  mov     [rbx+rsi+18h], rbp
0x140080fa4  mov     rcx, [rbx+rsi]; P
0x140080fa8  test    rcx, rcx
0x140080fab  jz      short loc_140080FC2
0x140080fad  mov     edx, 63437852h; Tag
0x140080fb2  call    cs:__imp_ExFreePoolWithTag
0x140080fb9  nop     dword ptr [rax+rax+00h]
0x140080fbe  mov     [rbx+rsi], rbp
0x140080fc2  inc     edi
0x140080fc4  cmp     edi, cs:dword_14007D0E8
0x140080fca  jb      short loc_140080F77
0x140080fcc  mov     rcx, cs:P; P
0x140080fd3  mov     edx, 63437852h; Tag
0x140080fd8  call    cs:__imp_ExFreePoolWithTag
0x140080fdf  nop     dword ptr [rax+rax+00h]
0x140080fe4  mov     cs:P, rbp
0x140080feb  mov     cs:dword_14007D0E8, ebp
0x140080ff1  xor     edx, edx
0x140080ff3  lea     rcx, qword_14007D0D8
0x140080ffa  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140081001  nop     dword ptr [rax+rax+00h]
0x140081006  lea     r8, qword_14007D248
0x14008100d  lea     rdx, byte_14007D258
0x140081014  lea     rcx, qword_14007D250
0x14008101b  call    ClearTargetServerExceptionList
0x140081020  lea     r8, qword_14007D268
0x140081027  lea     rdx, word_14007D278
0x14008102e  lea     rcx, qword_14007D270
0x140081035  call    ClearTargetServerExceptionList
0x14008103a  lea     rcx, MRxSmbRemoteBootMachineName; UnicodeString
0x140081041  call    cs:__imp_RtlFreeUnicodeString
0x140081048  nop     dword ptr [rax+rax+00h]
0x14008104d  lea     rcx, MRxSmbRemoteBootMachineDomain; UnicodeString
0x140081054  call    cs:__imp_RtlFreeUnicodeString
0x14008105b  nop     dword ptr [rax+rax+00h]
0x140081060  lea     rcx, MRxSmbRemoteBootMachinePassword; UnicodeString
0x140081067  call    cs:__imp_RtlFreeUnicodeString
0x14008106e  nop     dword ptr [rax+rax+00h]
0x140081073  mov     rcx, cs:DestinationString.Buffer; P
0x14008107a  test    rcx, rcx
0x14008107d  jz      short loc_14008108E
0x14008107f  mov     edx, r14d; Tag
0x140081082  call    cs:__imp_ExFreePoolWithTag
0x140081089  nop     dword ptr [rax+rax+00h]
0x14008108e  mov     rcx, cs:stru_140070F40.Buffer; P
0x140081095  mov     cs:DestinationString.Buffer, rbp
0x14008109c  mov     dword ptr cs:DestinationString.Length, ebp
0x1400810a2  test    rcx, rcx
0x1400810a5  jz      short loc_1400810B6
0x1400810a7  mov     edx, r14d; Tag
0x1400810aa  call    cs:__imp_ExFreePoolWithTag
0x1400810b1  nop     dword ptr [rax+rax+00h]
0x1400810b6  mov     rcx, cs:stru_140070F50.Buffer; P
0x1400810bd  mov     cs:stru_140070F40.Buffer, rbp
0x1400810c4  mov     dword ptr cs:stru_140070F40.Length, ebp
0x1400810ca  test    rcx, rcx
0x1400810cd  jz      short loc_1400810DE
0x1400810cf  mov     edx, r14d; Tag
0x1400810d2  call    cs:__imp_ExFreePoolWithTag
0x1400810d9  nop     dword ptr [rax+rax+00h]
0x1400810de  lea     rcx, SmbCeContext; UnicodeString
0x1400810e5  mov     cs:stru_140070F50.Buffer, rbp
0x1400810ec  mov     dword ptr cs:stru_140070F50.Length, ebp
0x1400810f2  call    cs:__imp_RtlFreeUnicodeString
0x1400810f9  nop     dword ptr [rax+rax+00h]
0x1400810fe  mov     rcx, cs:MRxSmbLegacyPerfCtrs; P
0x140081105  mov     ebx, 6D537250h
0x14008110a  test    rcx, rcx
0x14008110d  jz      short loc_140081124
0x14008110f  mov     edx, ebx; Tag
0x140081111  call    cs:__imp_ExFreePoolWithTag
0x140081118  nop     dword ptr [rax+rax+00h]
0x14008111d  mov     cs:MRxSmbLegacyPerfCtrs, rbp
0x140081124  mov     rcx, cs:RdrPerfBlockLookasideList; P
0x14008112b  test    rcx, rcx
0x14008112e  jz      short loc_14008113E
0x140081130  mov     edx, ebx; Tag
0x140081132  call    PplDestroyLookasideList
0x140081137  mov     cs:RdrPerfBlockLookasideList, rbp
0x14008113e  mov     rcx, cs:RxsmbdAsyncSendContextLookasideList; P
0x140081145  test    rcx, rcx
0x140081148  jz      short loc_14008115B
0x14008114a  mov     edx, 64437852h; Tag
0x14008114f  call    PplDestroyLookasideList
0x140081154  mov     cs:RxsmbdAsyncSendContextLookasideList, rbp
0x14008115b  add     rsp, 20h
0x14008115f  pop     r14
0x140081161  pop     rdi
0x140081162  pop     rsi
0x140081163  pop     rbp
0x140081164  pop     rbx
0x140081165  retn
```
