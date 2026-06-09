# TdiIndicateReceive

- ea: `0x1400097f4`
- end: `0x140009cbf`
- name: `TdiIndicateReceive`
- size: `1227`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008334`
- `0x14000877c`
- `0x140008ac0`
- `0x14000a9d0`

## callees

- `0x140003bf4`
- `0x140005c38`
- `0x14000877c`
- `0x1400097f4`
- `0x14000ab70`
- `0x14000aba8`
- `0x14000c2e0`
- `0x14000cba8`
- `0x14000fe48`
- `0x14001bfa8`
- `0x14001ea34`
- `0x14001ebd8`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009817`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009aa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009bb8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009817`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009aa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009bb8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009846`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009bff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009c20`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009846`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009bff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009c20`
- `ntoskrnl!IofCompleteRequest` at `0x140009b93`
- `ntoskrnl!IofCompleteRequest` at `0x140009b93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ac5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ba9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ac5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ba9`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x140009931`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x140009931`
- `TDI!TdiCopyBufferToMdl` at `0x140009b56`
- `TDI!TdiCopyBufferToMdl` at `0x140009b56`

## string_xrefs

- `0x140009c48`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140009c78`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140009c98`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
void __fastcall TdiIndicateReceive(__int64 a1)
{
  KSPIN_LOCK *v1; // r15
  __int64 v3; // r13
  unsigned int v4; // ebx
  char **v5; // r12
  char v6; // al
  char *v7; // r14
  char *v8; // rax
  IRP *v9; // r9
  int v10; // edx
  unsigned int v11; // eax
  __int64 v12; // rcx
  ULONG v13; // ebx
  void *DeviceExtension; // rdi
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  char *v21; // rax
  NTSTATUS v22; // ecx
  unsigned int i; // ebx
  int DestinationOffset; // [rsp+20h] [rbp-49h]
  unsigned int v25; // [rsp+50h] [rbp-19h]
  PIRP Irp; // [rsp+58h] [rbp-11h]
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64); // [rsp+60h] [rbp-9h]
  __int64 v28; // [rsp+68h] [rbp-1h]
  __int64 v29; // [rsp+70h] [rbp+7h]
  char v30; // [rsp+D0h] [rbp+67h]
  char v31; // [rsp+D8h] [rbp+6Fh]
  ULONG BytesCopied; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v33; // [rsp+E8h] [rbp+7Fh]

  v1 = (KSPIN_LOCK *)(a1 + 48);
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v3 = TdiReferenceAddrLocked(a1, 1447249234);
  if ( *(_BYTE *)(a1 + 809) )
  {
    KeReleaseSpinLock(v1, *(_BYTE *)(a1 + 56));
    goto LABEL_51;
  }
  v27 = 0;
  v4 = 0;
  v28 = 0;
  v33 = 0;
  v25 = 0;
  v30 = 0;
  *(_BYTE *)(a1 + 809) = 1;
  if ( v3 && *(_BYTE *)(a1 + 96) )
  {
    v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v3 + 176);
    v28 = *(_QWORD *)(v3 + 184);
  }
  v29 = TdiReferenceChannelLocked(a1, 1313754947);
  v5 = (char **)(a1 + 792);
  v6 = 0;
  while ( 1 )
  {
    v7 = *v5;
    if ( *v5 == (char *)v5 || v6 )
      break;
    BytesCopied = 0;
    if ( *((char ***)v7 + 1) != v5 || (v8 = *(char **)v7, *(char **)(*(_QWORD *)v7 + 8LL) != v7) )
LABEL_40:
      __fastfail(3u);
    *v5 = v8;
    *((_QWORD *)v8 + 1) = v5;
    *((_QWORD *)v7 + 1) = v7;
    *(_QWORD *)v7 = v7;
    v31 = 0;
    KeReleaseSpinLock(v1, *(_BYTE *)(a1 + 56));
    Irp = (PIRP)IrpList_Dequeue(a1 + 512);
    v9 = Irp;
    if ( Irp )
    {
      while ( 1 )
      {
        if ( *(_QWORD *)(a1 + 88) )
        {
          if ( (int)IoDecrementKeepAliveCount(*(_QWORD *)(a1 + 72)) < 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              2,
              132,
              (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
          }
          v9 = Irp;
        }
        if ( v9->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length )
          break;
        RfcommCompleteTdiIrp(v9);
        Irp = (PIRP)IrpList_Dequeue(a1 + 512);
        v9 = Irp;
        if ( !Irp )
          goto LABEL_22;
      }
      v33 = -1073741802;
      v31 = 1;
    }
    if ( v9 )
    {
      v12 = v33;
    }
    else
    {
LABEL_22:
      if ( v27 )
      {
        DestinationOffset = *((_DWORD *)v7 + 7);
        v11 = v27(v28, *(_QWORD *)(a1 + 328), 3104);
        v9 = Irp;
        v12 = v11;
        v33 = v11;
      }
      else
      {
        v12 = 3221226011LL;
        BytesCopied = 0;
        v33 = -1073741285;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = *((_DWORD *)v7 + 7) - BytesCopied;
      DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
      v15 = NtStatusTxt(v12);
      WPP_RECORDER_SF_qqsdd(
        (_DWORD)DeviceExtension,
        BytesCopied,
        v16,
        v17,
        DestinationOffset,
        a1,
        (char)v27,
        v15,
        BytesCopied,
        v13);
      v9 = Irp;
      v4 = v25;
    }
    if ( v33 == -1073741802 )
    {
      v22 = TdiCopyBufferToMdl(
              &v7[*((unsigned int *)v7 + 6) + 32],
              0,
              *((_DWORD *)v7 + 7),
              v9->MdlAddress,
              0,
              &BytesCopied);
      if ( v31 )
      {
        RfcommCompleteTdiIrp(Irp);
      }
      else
      {
        Irp->IoStatus.Status = v22;
        Irp->IoStatus.Information = BytesCopied;
        IofCompleteRequest(Irp, 2);
      }
      goto LABEL_38;
    }
    if ( v33 )
    {
      *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc(v1);
      if ( *(_BYTE *)(a1 + 96) )
      {
        v21 = *v5;
        if ( *((char ***)*v5 + 1) != v5 )
          goto LABEL_40;
        *(_QWORD *)v7 = v21;
        *((_QWORD *)v7 + 1) = v5;
        *((_QWORD *)v21 + 1) = v7;
        v6 = 1;
        v30 = 1;
        *v5 = v7;
      }
      else
      {
        v25 = ++v4;
        ExFreePoolWithTag(v7, 0);
        v27 = 0;
        v6 = v30;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_qL(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            v19,
            v20,
            DestinationOffset,
            a1,
            *(_DWORD *)(a1 + 80));
          goto LABEL_39;
        }
      }
    }
    else
    {
LABEL_38:
      v25 = ++v4;
      ExFreePoolWithTag(v7, 0);
      *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc(v1);
      _InterlockedAdd((volatile signed __int32 *)(a1 + 816), BytesCopied);
LABEL_39:
      v6 = v30;
    }
  }
  *(_BYTE *)(a1 + 809) = 0;
  if ( v7 == (char *)(a1 + 792) && *(_DWORD *)(a1 + 80) == 3 )
  {
    KeReleaseSpinLock(v1, *(_BYTE *)(a1 + 56));
    TdiDisconnectInd(a1, 3221225788LL);
  }
  else
  {
    KeReleaseSpinLock(v1, *(_BYTE *)(a1 + 56));
  }
  for ( i = 0; i < v25; ++i )
  {
    if ( v29 )
      ChannelGrantCredit(v29);
    RefObj_ReleaseEx(a1 + 24, 1447249234, 3856, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  }
  if ( v29 )
    RefObj_ReleaseEx(v29 + 24, 1313754947, 3863, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
LABEL_51:
  if ( v3 )
    RefObj_ReleaseEx(v3 + 24, 1447249234, 3868, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
}

```

## disassembly

```asm
0x1400097f4  push    rbp
0x1400097f6  push    rbx
0x1400097f7  push    rsi
0x1400097f8  push    rdi
0x1400097f9  push    r12
0x1400097fb  push    r13
0x1400097fd  push    r14
0x1400097ff  push    r15
0x140009801  lea     rbp, [rsp-1Fh]
0x140009806  sub     rsp, 88h
0x14000980d  lea     r15, [rcx+30h]
0x140009811  mov     rsi, rcx
0x140009814  mov     rcx, r15; SpinLock
0x140009817  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000981e  nop     dword ptr [rax+rax+00h]
0x140009823  mov     edx, 56434552h
0x140009828  mov     rcx, rsi
0x14000982b  mov     [rsi+38h], al
0x14000982e  call    TdiReferenceAddrLocked
0x140009833  mov     r13, rax
0x140009836  xor     eax, eax
0x140009838  cmp     [rsi+329h], al
0x14000983e  jz      short loc_140009857
0x140009840  mov     dl, [rsi+38h]; NewIrql
0x140009843  mov     rcx, r15; SpinLock
0x140009846  call    cs:__imp_KeReleaseSpinLock
0x14000984d  nop     dword ptr [rax+rax+00h]
0x140009852  jmp     loc_140009C8A
0x140009857  mov     [rbp+57h+var_60], rax
0x14000985b  mov     ebx, eax
0x14000985d  mov     [rbp+57h+var_58], rax
0x140009861  mov     [rbp+57h+arg_18], eax
0x140009864  mov     [rbp+57h+var_70], eax
0x140009867  mov     [rbp+57h+arg_0], al
0x14000986a  mov     byte ptr [rsi+329h], 1
0x140009871  test    r13, r13
0x140009874  jz      short loc_140009891
0x140009876  cmp     [rsi+60h], al
0x140009879  jz      short loc_140009891
0x14000987b  mov     rax, [r13+0B0h]
0x140009882  mov     [rbp+57h+var_60], rax
0x140009886  mov     rax, [r13+0B8h]
0x14000988d  mov     [rbp+57h+var_58], rax
0x140009891  mov     edx, 4E4E4F43h
0x140009896  mov     rcx, rsi
0x140009899  call    TdiReferenceChannelLocked
0x14000989e  mov     [rbp+57h+var_50], rax
0x1400098a2  lea     r12, [rsi+318h]
0x1400098a9  mov     al, bl
0x1400098ab  xor     edi, edi
0x1400098ad  mov     r14, [r12]
0x1400098b1  cmp     r14, r12
0x1400098b4  jz      loc_140009BE0
0x1400098ba  test    al, al
0x1400098bc  jnz     loc_140009BE0
0x1400098c2  mov     [rbp+57h+Irp], rdi
0x1400098c6  mov     [rbp+57h+arg_10], edi
0x1400098c9  cmp     [r14+8], r12
0x1400098cd  jnz     loc_140009BD9
0x1400098d3  mov     rax, [r14]
0x1400098d6  cmp     [rax+8], r14
0x1400098da  jnz     loc_140009BD9
0x1400098e0  mov     [r12], rax
0x1400098e4  mov     rcx, r15; SpinLock
0x1400098e7  mov     [rax+8], r12
0x1400098eb  mov     [r14+8], r14
0x1400098ef  mov     [r14], r14
0x1400098f2  mov     dl, [rsi+38h]; NewIrql
0x1400098f5  mov     [rbp+57h+arg_8], dil
0x1400098f9  call    cs:__imp_KeReleaseSpinLock
0x140009900  nop     dword ptr [rax+rax+00h]
0x140009905  lea     rdi, [rsi+200h]
0x14000990c  mov     rcx, rdi
0x14000990f  call    IrpList_Dequeue
0x140009914  mov     [rbp+57h+Irp], rax
0x140009918  mov     r9, rax
0x14000991b  test    rax, rax
0x14000991e  jz      loc_1400099BE
0x140009924  mov     rdx, [rsi+58h]
0x140009928  test    rdx, rdx
0x14000992b  jz      short loc_14000997D
0x14000992d  mov     rcx, [rsi+48h]
0x140009931  call    cs:__imp_IoDecrementKeepAliveCount
0x140009938  nop     dword ptr [rax+rax+00h]
0x14000993d  test    eax, eax
0x14000993f  jns     short loc_140009979
0x140009941  lea     rax, WPP_RECORDER_INITIALIZED
0x140009948  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000994f  jz      short loc_140009979
0x140009951  mov     rcx, cs:WPP_GLOBAL_Control
0x140009958  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000995f  mov     r9d, 84h
0x140009965  mov     qword ptr [rsp+0C0h+DestinationOffset], rax
0x14000996a  mov     r8d, 2
0x140009970  mov     rcx, [rcx+40h]
0x140009974  call    WPP_RECORDER_SF_
0x140009979  mov     r9, [rbp+57h+Irp]
0x14000997d  mov     rax, [r9+0B8h]
0x140009984  cmp     dword ptr [rax+8], 0
0x140009988  ja      short loc_1400099B3
0x14000998a  xor     r8d, r8d
0x14000998d  xor     edx, edx
0x14000998f  mov     rcx, r9; Irp
0x140009992  call    RfcommCompleteTdiIrp
0x140009997  mov     rcx, rdi
0x14000999a  call    IrpList_Dequeue
0x14000999f  mov     [rbp+57h+Irp], rax
0x1400099a3  mov     r9, rax
0x1400099a6  test    rax, rax
0x1400099a9  jnz     loc_140009924
0x1400099af  xor     edi, edi
0x1400099b1  jmp     short loc_1400099C5
0x1400099b3  mov     [rbp+57h+arg_18], 0C0000016h
0x1400099ba  mov     [rbp+57h+arg_8], 1
0x1400099be  xor     edi, edi
0x1400099c0  test    r9, r9
0x1400099c3  jnz     short loc_140009A2A
0x1400099c5  mov     r10, [rbp+57h+var_60]
0x1400099c9  test    r10, r10
0x1400099cc  jz      short loc_140009A1D
0x1400099ce  mov     ecx, [r14+18h]
0x1400099d2  lea     rax, [rbp+57h+Irp]
0x1400099d6  mov     r9d, [r14+1Ch]
0x1400099da  add     rcx, 20h ; ' '
0x1400099de  mov     rdx, [rsi+148h]
0x1400099e5  add     rcx, r14
0x1400099e8  mov     [rsp+0C0h+var_88], rax
0x1400099ed  mov     r8d, 0C20h
0x1400099f3  mov     [rsp+0C0h+var_90], rcx
0x1400099f8  lea     rax, [rbp+57h+arg_10]
0x1400099fc  mov     rcx, [rbp+57h+var_58]
0x140009a00  mov     [rsp+0C0h+BytesCopied], rax
0x140009a05  mov     rax, r10
0x140009a08  mov     [rsp+0C0h+DestinationOffset], r9d
0x140009a0d  call    _guard_dispatch_icall
0x140009a12  mov     r9, [rbp+57h+Irp]
0x140009a16  mov     ecx, eax
0x140009a18  mov     [rbp+57h+arg_18], eax
0x140009a1b  jmp     short loc_140009A2D
0x140009a1d  mov     ecx, 0C000021Bh
0x140009a22  mov     [rbp+57h+arg_10], edi
0x140009a25  mov     [rbp+57h+arg_18], ecx
0x140009a28  jmp     short loc_140009A2D
0x140009a2a  mov     ecx, [rbp+57h+arg_18]
0x140009a2d  lea     rax, WPP_RECORDER_INITIALIZED
0x140009a34  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009a3b  jz      short loc_140009A83
0x140009a3d  mov     rax, cs:WPP_GLOBAL_Control
0x140009a44  mov     ebx, [r14+1Ch]
0x140009a48  sub     ebx, [rbp+57h+arg_10]
0x140009a4b  mov     rdi, [rax+40h]
0x140009a4f  call    NtStatusTxt
0x140009a54  mov     edx, [rbp+57h+arg_10]
0x140009a57  mov     rcx, rdi
0x140009a5a  mov     [rsp+0C0h+var_78], ebx
0x140009a5e  mov     [rsp+0C0h+var_80], edx
0x140009a62  mov     [rsp+0C0h+var_88], rax
0x140009a67  mov     rax, [rbp+57h+var_60]
0x140009a6b  mov     [rsp+0C0h+var_90], rax
0x140009a70  mov     [rsp+0C0h+BytesCopied], rsi
0x140009a75  call    WPP_RECORDER_SF_qqsdd
0x140009a7a  mov     r9, [rbp+57h+Irp]
0x140009a7e  xor     edi, edi
0x140009a80  mov     ebx, [rbp+57h+var_70]
0x140009a83  mov     ecx, [rbp+57h+arg_18]
0x140009a86  cmp     ecx, 0C0000016h
0x140009a8c  jz      loc_140009B34
0x140009a92  test    dil, dil
0x140009a95  jnz     loc_140009B9F
0x140009a9b  test    ecx, ecx
0x140009a9d  jz      loc_140009B9F
0x140009aa3  mov     rcx, r15; SpinLock
0x140009aa6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009aad  nop     dword ptr [rax+rax+00h]
0x140009ab2  mov     [rsi+38h], al
0x140009ab5  cmp     [rsi+60h], dil
0x140009ab9  jnz     short loc_140009B0D
0x140009abb  inc     ebx
0x140009abd  xor     edx, edx; Tag
0x140009abf  mov     rcx, r14; P
0x140009ac2  mov     [rbp+57h+var_70], ebx
0x140009ac5  call    cs:__imp_ExFreePoolWithTag
0x140009acc  nop     dword ptr [rax+rax+00h]
0x140009ad1  mov     [rbp+57h+var_60], rdi
0x140009ad5  lea     rax, WPP_RECORDER_INITIALIZED
0x140009adc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009ae3  mov     al, [rbp+57h+arg_0]
0x140009ae6  jz      loc_1400098AD
0x140009aec  mov     rcx, cs:WPP_GLOBAL_Control
0x140009af3  mov     eax, [rsi+50h]
0x140009af6  mov     dword ptr [rsp+0C0h+var_90], eax
0x140009afa  mov     [rsp+0C0h+BytesCopied], rsi
0x140009aff  mov     rcx, [rcx+40h]
0x140009b03  call    WPP_RECORDER_SF_qL
0x140009b08  jmp     loc_140009BD1
0x140009b0d  mov     rax, [r12]
0x140009b11  cmp     [rax+8], r12
0x140009b15  jnz     loc_140009BD9
0x140009b1b  mov     [r14], rax
0x140009b1e  mov     [r14+8], r12
0x140009b22  mov     [rax+8], r14
0x140009b26  mov     al, 1
0x140009b28  mov     [rbp+57h+arg_0], al
0x140009b2b  mov     [r12], r14
0x140009b2f  jmp     loc_1400098AD
0x140009b34  mov     ecx, [r14+18h]
0x140009b38  lea     rax, [rbp+57h+arg_10]
0x140009b3c  mov     r9, [r9+8]; DestinationMdlChain
0x140009b40  add     rcx, 20h ; ' '
0x140009b44  mov     r8d, [r14+1Ch]; SourceBytesToCopy
0x140009b48  add     rcx, r14; SourceBuffer
0x140009b4b  mov     [rsp+0C0h+BytesCopied], rax; BytesCopied
0x140009b50  xor     edx, edx; SourceOffset
0x140009b52  mov     [rsp+0C0h+DestinationOffset], edi; DestinationOffset
0x140009b56  call    cs:__imp_TdiCopyBufferToMdl
0x140009b5d  nop     dword ptr [rax+rax+00h]
0x140009b62  mov     ecx, eax
0x140009b64  cmp     [rbp+57h+arg_8], dil
0x140009b68  jz      short loc_140009B7B
0x140009b6a  mov     r8d, [rbp+57h+arg_10]
0x140009b6e  mov     edx, eax
0x140009b70  mov     rcx, [rbp+57h+Irp]; Irp
0x140009b74  call    RfcommCompleteTdiIrp
0x140009b79  jmp     short loc_140009B9F
0x140009b7b  mov     rax, [rbp+57h+Irp]
0x140009b7f  mov     dl, 2; PriorityBoost
0x140009b81  mov     [rax+30h], ecx
0x140009b84  mov     ecx, [rbp+57h+arg_10]
0x140009b87  mov     rax, [rbp+57h+Irp]
0x140009b8b  mov     [rax+38h], rcx
0x140009b8f  mov     rcx, [rbp+57h+Irp]; Irp
0x140009b93  call    cs:__imp_IofCompleteRequest
0x140009b9a  nop     dword ptr [rax+rax+00h]
0x140009b9f  inc     ebx
0x140009ba1  xor     edx, edx; Tag
0x140009ba3  mov     rcx, r14; P
0x140009ba6  mov     [rbp+57h+var_70], ebx
0x140009ba9  call    cs:__imp_ExFreePoolWithTag
0x140009bb0  nop     dword ptr [rax+rax+00h]
0x140009bb5  mov     rcx, r15; SpinLock
0x140009bb8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009bbf  nop     dword ptr [rax+rax+00h]
0x140009bc4  mov     [rsi+38h], al
0x140009bc7  mov     eax, [rbp+57h+arg_10]
0x140009bca  lock add [rsi+330h], eax
0x140009bd1  mov     al, [rbp+57h+arg_0]
0x140009bd4  jmp     loc_1400098AD
0x140009bd9  mov     ecx, 3
0x140009bde  int     29h; Win8: RtlFailFast(ecx)
0x140009be0  lea     rax, [rsi+318h]
0x140009be7  mov     [rsi+329h], dil
0x140009bee  cmp     r14, rax
0x140009bf1  jnz     short loc_140009C1A
0x140009bf3  cmp     dword ptr [rsi+50h], 3
0x140009bf7  jnz     short loc_140009C1A
0x140009bf9  mov     dl, [rsi+38h]; NewIrql
0x140009bfc  mov     rcx, r15; SpinLock
0x140009bff  call    cs:__imp_KeReleaseSpinLock
0x140009c06  nop     dword ptr [rax+rax+00h]
0x140009c0b  mov     edx, 0C000013Ch
0x140009c10  mov     rcx, rsi
0x140009c13  call    TdiDisconnectInd
0x140009c18  jmp     short loc_140009C2C
0x140009c1a  mov     dl, [rsi+38h]; NewIrql
0x140009c1d  mov     rcx, r15; SpinLock
0x140009c20  call    cs:__imp_KeReleaseSpinLock
0x140009c27  nop     dword ptr [rax+rax+00h]
0x140009c2c  mov     r14d, [rbp+57h+var_70]
0x140009c30  mov     ebx, edi
0x140009c32  mov     rdi, [rbp+57h+var_50]
0x140009c36  test    r14d, r14d
0x140009c39  jz      short loc_140009C6A
0x140009c3b  test    rdi, rdi
0x140009c3e  jz      short loc_140009C48
0x140009c40  mov     rcx, rdi
0x140009c43  call    ChannelGrantCredit
0x140009c48  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009c4f  mov     edx, 56434552h
0x140009c54  mov     r8d, 0F10h
0x140009c5a  lea     rcx, [rsi+18h]
0x140009c5e  call    RefObj_ReleaseEx
0x140009c63  inc     ebx
0x140009c65  cmp     ebx, r14d
0x140009c68  jb      short loc_140009C3B
0x140009c6a  test    rdi, rdi
0x140009c6d  jz      short loc_140009C8A
0x140009c6f  lea     rcx, [rdi+18h]
0x140009c73  mov     edx, 4E4E4F43h
0x140009c78  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009c7f  mov     r8d, 0F17h
0x140009c85  call    RefObj_ReleaseEx
0x140009c8a  test    r13, r13
0x140009c8d  jz      short loc_140009CAA
0x140009c8f  lea     rcx, [r13+18h]
0x140009c93  mov     edx, 56434552h
0x140009c98  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009c9f  mov     r8d, 0F1Ch
0x140009ca5  call    RefObj_ReleaseEx
0x140009caa  add     rsp, 88h
0x140009cb1  pop     r15
  ... truncated ...
```
