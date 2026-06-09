# ndisPowerDispatch(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14005aad0`
- end: `0x14005ae3f`
- name: `?ndisPowerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `879`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14001c050`
- `0x14001cf50`
- `0x14001d030`
- `0x14001d350`
- `0x14005aad0`
- `0x14005ae50`
- `0x14005af60`
- `0x1401774c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005ab56`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005abab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ab56`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005abab`
- `ntoskrnl!IofCallDriver` at `0x14005ac8a`
- `ntoskrnl!IofCallDriver` at `0x1400eca1d`
- `ntoskrnl!IofCallDriver` at `0x14005ac8a`
- `ntoskrnl!IofCallDriver` at `0x1400eca1d`
- `ntoskrnl!IofCompleteRequest` at `0x14005ad58`
- `ntoskrnl!IofCompleteRequest` at `0x1400eca78`
- `ntoskrnl!IofCompleteRequest` at `0x14005ad58`
- `ntoskrnl!IofCompleteRequest` at `0x1400eca78`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400eca62`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400eca62`

## pseudocode

```c
__int64 __fastcall ndisPowerDispatch(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  void *DeviceExtension; // rbx
  char v3; // si
  struct _IRP *v4; // rdi
  struct _DEVICE_OBJECT *v5; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int MinorFunction; // ecx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  NTSTATUS Power; // eax
  int v12; // edx
  int v13; // edx
  unsigned int v14; // esi
  _IO_STACK_LOCATION *v16; // rax
  _IO_STACK_LOCATION *v17; // rax
  _IO_STACK_LOCATION *v18; // rax
  char v19; // [rsp+30h] [rbp-28h]

  DeviceExtension = a1->DeviceExtension;
  v3 = (char)a1;
  v4 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v19 = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      14,
      108,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)DeviceExtension,
      v19);
  }
  if ( *(_BYTE *)DeviceExtension == 17 )
  {
    v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 480);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        (int)a2,
        14,
        110,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)DeviceExtension);
    }
    CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
    MinorFunction = CurrentStackLocation->MinorFunction;
    if ( MinorFunction == 2 )
    {
      if ( !KeGetCurrentIrql() )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 4;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v13,
            14,
            114,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)DeviceExtension);
        }
        Power = ndisSetPower(v4, CurrentStackLocation, (struct _NDIS_MINIPORT_BLOCK *)DeviceExtension);
        goto LABEL_18;
      }
      goto LABEL_25;
    }
    v8 = CurrentStackLocation->MinorFunction;
    if ( CurrentStackLocation->MinorFunction )
    {
      v9 = MinorFunction - 1;
      if ( MinorFunction == 1 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 4;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v9,
            14,
            111,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)DeviceExtension);
        }
        v18 = v4->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v18[-1].MajorFunction = *(_OWORD *)&v18->MajorFunction;
        *(_OWORD *)&v18[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v18->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)&v18[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&v18->Parameters.ReadWriteConfig.Length;
        v18[-1].FileObject = v18->FileObject;
        v18[-1].Control = 0;
        v14 = IoSynchronousCallDriver(v5, v4);
        v4->IoStatus.Status = v14;
        IofCompleteRequest(v4, 0);
      }
      else
      {
        if ( MinorFunction == 3 )
        {
          if ( !KeGetCurrentIrql() )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = 4;
              WPP_RECORDER_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v10,
                14,
                113,
                (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
                (char)DeviceExtension);
            }
            Power = ndisQueryPower(v4, CurrentStackLocation, (struct _NDIS_MINIPORT_BLOCK *)DeviceExtension);
LABEL_18:
            v14 = Power;
            goto LABEL_19;
          }
LABEL_25:
          ndisQueuePowerIrp((struct _NDIS_MINIPORT_BLOCK *)DeviceExtension, v4);
          v14 = 259;
          goto LABEL_19;
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 4;
          WPP_RECORDER_SF_qL(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v9,
            14,
            115,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)DeviceExtension,
            MinorFunction);
        }
        ++v4->CurrentLocation;
        ++v4->Tail.Overlay.CurrentStackLocation;
        v14 = IofCallDriver(v5, v4);
      }
    }
    else
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v8,
          14,
          112,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)DeviceExtension);
      }
      CurrentStackLocation->Parameters.Read.Length = *((_DWORD *)DeviceExtension + 333);
      v16 = v4->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v16[-1].MajorFunction = *(_OWORD *)&v16->MajorFunction;
      *(_OWORD *)&v16[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v16->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)&v16[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&v16->Parameters.ReadWriteConfig.Length;
      v16[-1].FileObject = v16->FileObject;
      v16[-1].Control = 0;
      v17 = v4->Tail.Overlay.CurrentStackLocation;
      v17[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ndisWaitWakeIoCompletion;
      v17[-1].Context = DeviceExtension;
      v17[-1].Control = -32;
      v14 = IofCallDriver(v5, v4);
    }
  }
  else
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        (int)a2,
        14,
        109,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        v3,
        (char)v4);
    }
    v14 = -1073741808;
    v4->IoStatus.Status = -1073741808;
    IofCompleteRequest(v4, 0);
  }
LABEL_19:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v12,
      14,
      116,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)DeviceExtension,
      v14);
  }
  return v14;
}

```

## disassembly

```asm
0x14005aad0  push    rbx
0x14005aad2  push    rsi
0x14005aad3  push    r15
0x14005aad5  sub     rsp, 40h
0x14005aad9  mov     rbx, [rcx+40h]
0x14005aadd  mov     rsi, rcx
0x14005aae0  mov     [rsp+58h+arg_8], rdi
0x14005aae5  mov     rdi, rdx
0x14005aae8  mov     [rsp+58h+arg_10], r14
0x14005aaed  lea     r14, WPP_RECORDER_INITIALIZED
0x14005aaf4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005aafb  lea     r15, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14005ab02  jnz     loc_14005ACE3
0x14005ab08  cmp     byte ptr [rbx], 11h
0x14005ab0b  jnz     loc_14005AD42
0x14005ab11  mov     [rsp+58h+arg_0], rbp
0x14005ab16  mov     rbp, [rbx+0F00h]
0x14005ab1d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005ab24  jnz     loc_14005AD15
0x14005ab2a  mov     rsi, [rdi+0B8h]
0x14005ab31  movzx   ecx, byte ptr [rsi+1]
0x14005ab35  cmp     ecx, 2
0x14005ab38  jz      short loc_14005ABAB
0x14005ab3a  mov     edx, ecx
0x14005ab3c  test    ecx, ecx
0x14005ab3e  jz      loc_14005AC28
0x14005ab44  sub     edx, 1
0x14005ab47  jz      loc_14005ADD7
0x14005ab4d  cmp     edx, 2
0x14005ab50  jnz     loc_14005AD98
0x14005ab56  call    cs:__imp_KeGetCurrentIrql
0x14005ab5d  nop     dword ptr [rax+rax+00h]
0x14005ab62  test    al, al
0x14005ab64  jnz     loc_14005ACCE
0x14005ab6a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005ab71  jz      short loc_14005AB9B
0x14005ab73  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab7a  mov     r9d, 71h ; 'q'; int
0x14005ab80  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005ab85  mov     r8d, 0Eh; int
0x14005ab8b  mov     dl, 4; int
0x14005ab8d  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005ab92  mov     rcx, [rcx+40h]; int
0x14005ab96  call    WPP_RECORDER_SF_q
0x14005ab9b  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005ab9e  mov     rdx, rsi; struct _IO_STACK_LOCATION *
0x14005aba1  mov     rcx, rdi; Irp
0x14005aba4  call    ?ndisQueryPower@@_Y2PAGENPNP@@AJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisQueryPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x14005aba9  jmp     short loc_14005ABFE
0x14005abab  call    cs:__imp_KeGetCurrentIrql
0x14005abb2  nop     dword ptr [rax+rax+00h]
0x14005abb7  test    al, al
0x14005abb9  jnz     loc_14005ACCE
0x14005abbf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005abc6  jz      short loc_14005ABF0
0x14005abc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005abcf  mov     r9d, 72h ; 'r'; int
0x14005abd5  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005abda  mov     r8d, 0Eh; int
0x14005abe0  mov     dl, 4; int
0x14005abe2  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005abe7  mov     rcx, [rcx+40h]; int
0x14005abeb  call    WPP_RECORDER_SF_q
0x14005abf0  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005abf3  mov     rdx, rsi; struct _IO_STACK_LOCATION *
0x14005abf6  mov     rcx, rdi; Irp
0x14005abf9  call    ?ndisSetPower@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x14005abfe  mov     esi, eax
0x14005ac00  mov     rbp, [rsp+58h+arg_0]
0x14005ac05  mov     rdi, [rsp+58h+arg_8]
0x14005ac0a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005ac11  mov     r14, [rsp+58h+arg_10]
0x14005ac16  jnz     loc_14005AC9D
0x14005ac1c  mov     eax, esi
0x14005ac1e  add     rsp, 40h
0x14005ac22  pop     r15
0x14005ac24  pop     rsi
0x14005ac25  pop     rbx
0x14005ac26  retn
0x14005ac28  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005ac2f  jnz     loc_14005AE12
0x14005ac35  mov     eax, [rbx+534h]
0x14005ac3b  lea     rcx, ?ndisWaitWakeIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisWaitWakeIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14005ac42  mov     [rsi+8], eax
0x14005ac45  mov     rdx, rdi; Irp
0x14005ac48  mov     rax, [rdi+0B8h]
0x14005ac4f  movups  xmm0, xmmword ptr [rax]
0x14005ac52  movups  xmmword ptr [rax-48h], xmm0
0x14005ac56  movups  xmm1, xmmword ptr [rax+10h]
0x14005ac5a  movups  xmmword ptr [rax-38h], xmm1
0x14005ac5e  movups  xmm0, xmmword ptr [rax+20h]
0x14005ac62  movups  xmmword ptr [rax-28h], xmm0
0x14005ac66  movsd   xmm1, qword ptr [rax+30h]
0x14005ac6b  movsd   qword ptr [rax-18h], xmm1
0x14005ac70  mov     byte ptr [rax-45h], 0
0x14005ac74  mov     rax, [rdi+0B8h]
0x14005ac7b  mov     [rax-10h], rcx
0x14005ac7f  mov     rcx, rbp; DeviceObject
0x14005ac82  mov     [rax-8], rbx
0x14005ac86  mov     byte ptr [rax-45h], 0E0h
0x14005ac8a  call    cs:__imp_IofCallDriver
0x14005ac91  nop     dword ptr [rax+rax+00h]
0x14005ac96  mov     esi, eax
0x14005ac98  jmp     loc_14005AC00
0x14005ac9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aca4  mov     r9d, 74h ; 't'; int
0x14005acaa  mov     dword ptr [rsp+58h+var_28], esi; char
0x14005acae  mov     r8d, 0Eh; int
0x14005acb4  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005acb9  mov     dl, 4; int
0x14005acbb  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005acc0  mov     rcx, [rcx+40h]; int
0x14005acc4  call    WPP_RECORDER_SF_qD
0x14005acc9  jmp     loc_14005AC1C
0x14005acce  mov     rdx, rdi; struct _IRP *
0x14005acd1  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005acd4  call    ?ndisQueuePowerIrp@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@@Z; ndisQueuePowerIrp(_NDIS_MINIPORT_BLOCK *,_IRP *)
0x14005acd9  mov     esi, 103h
0x14005acde  jmp     loc_14005AC00
0x14005ace3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005acea  mov     r9d, 6Ch ; 'l'; int
0x14005acf0  mov     qword ptr [rsp+58h+var_28], rdi; char
0x14005acf5  mov     r8d, 0Eh; int
0x14005acfb  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005ad00  mov     dl, 4; int
0x14005ad02  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005ad07  mov     rcx, [rcx+40h]; int
0x14005ad0b  call    WPP_RECORDER_SF_qq
0x14005ad10  jmp     loc_14005AB08
0x14005ad15  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad1c  mov     r9d, 6Eh ; 'n'; int
0x14005ad22  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005ad27  mov     r8d, 0Eh; int
0x14005ad2d  mov     dl, 4; int
0x14005ad2f  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005ad34  mov     rcx, [rcx+40h]; int
0x14005ad38  call    WPP_RECORDER_SF_q
0x14005ad3d  jmp     loc_14005AB2A
0x14005ad42  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005ad49  jnz     short loc_14005AD69
0x14005ad4b  mov     esi, 0C0000010h
0x14005ad50  xor     edx, edx; PriorityBoost
0x14005ad52  mov     rcx, rdi; Irp
0x14005ad55  mov     [rdi+30h], esi
0x14005ad58  call    cs:__imp_IofCompleteRequest
0x14005ad5f  nop     dword ptr [rax+rax+00h]
0x14005ad64  jmp     loc_14005AC05
0x14005ad69  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad70  mov     r9d, 6Dh ; 'm'; int
0x14005ad76  mov     qword ptr [rsp+58h+var_28], rdi; char
0x14005ad7b  mov     r8d, 0Eh; int
0x14005ad81  mov     qword ptr [rsp+58h+var_30], rsi; char
0x14005ad86  mov     dl, 4; int
0x14005ad88  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005ad8d  mov     rcx, [rcx+40h]; int
0x14005ad91  call    WPP_RECORDER_SF_qq
0x14005ad96  jmp     short loc_14005AD4B
0x14005ad98  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005ad9f  jz      loc_1400ECA0C
0x14005ada5  mov     dword ptr [rsp+58h+var_28], ecx; char
0x14005ada9  mov     r9d, 73h ; 's'; int
0x14005adaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005adb6  mov     r8d, 0Eh; int
0x14005adbc  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005adc1  mov     dl, 4; int
0x14005adc3  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005adc8  mov     rcx, [rcx+40h]; int
0x14005adcc  call    WPP_RECORDER_SF_qL
0x14005add1  nop
0x14005add2  jmp     loc_1400ECA0C
0x14005add7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005adde  jz      loc_1400ECA30
0x14005ade4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005adeb  mov     r9d, 6Fh ; 'o'; int
0x14005adf1  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005adf6  mov     r8d, 0Eh; int
0x14005adfc  mov     dl, 4; int
0x14005adfe  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005ae03  mov     rcx, [rcx+40h]; int
0x14005ae07  call    WPP_RECORDER_SF_q
0x14005ae0c  nop
0x14005ae0d  jmp     loc_1400ECA30
0x14005ae12  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae19  mov     r9d, 70h ; 'p'; int
0x14005ae1f  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005ae24  mov     r8d, 0Eh; int
0x14005ae2a  mov     dl, 4; int
0x14005ae2c  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005ae31  mov     rcx, [rcx+40h]; int
0x14005ae35  call    WPP_RECORDER_SF_q
0x14005ae3a  jmp     loc_14005AC35
0x1400eca0c  inc     byte ptr [rdi+43h]
0x1400eca0f  mov     rdx, rdi; Irp
0x1400eca12  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400eca1a  mov     rcx, rbp; DeviceObject
0x1400eca1d  call    cs:__imp_IofCallDriver
0x1400eca24  nop     dword ptr [rax+rax+00h]
0x1400eca29  mov     esi, eax
0x1400eca2b  jmp     loc_14005AC00
0x1400eca30  mov     rax, [rdi+0B8h]
0x1400eca37  mov     rdx, rdi
0x1400eca3a  mov     rcx, rbp
0x1400eca3d  movups  xmm0, xmmword ptr [rax]
0x1400eca40  movups  xmmword ptr [rax-48h], xmm0
0x1400eca44  movups  xmm1, xmmword ptr [rax+10h]
0x1400eca48  movups  xmmword ptr [rax-38h], xmm1
0x1400eca4c  movups  xmm0, xmmword ptr [rax+20h]
0x1400eca50  movups  xmmword ptr [rax-28h], xmm0
0x1400eca54  movsd   xmm1, qword ptr [rax+30h]
0x1400eca59  movsd   qword ptr [rax-18h], xmm1
0x1400eca5e  mov     byte ptr [rax-45h], 0
0x1400eca62  call    cs:__imp_IoSynchronousCallDriver
0x1400eca69  nop     dword ptr [rax+rax+00h]
0x1400eca6e  xor     edx, edx; PriorityBoost
0x1400eca70  mov     rcx, rdi; Irp
0x1400eca73  mov     esi, eax
0x1400eca75  mov     [rdi+30h], eax
0x1400eca78  call    cs:__imp_IofCompleteRequest
0x1400eca7f  nop     dword ptr [rax+rax+00h]
0x1400eca84  nop
0x1400eca85  jmp     loc_14005AC00
```
