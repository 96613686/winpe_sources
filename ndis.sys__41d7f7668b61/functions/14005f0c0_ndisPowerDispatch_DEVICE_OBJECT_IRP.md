# ndisPowerDispatch(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14005f0c0`
- end: `0x14005f42f`
- name: `?ndisPowerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `879`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400100f0`
- `0x1400110b0`
- `0x140011190`
- `0x1400114b0`
- `0x14005f0c0`
- `0x14005f440`
- `0x14005f550`
- `0x14017d490`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005f146`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005f19b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005f146`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005f19b`
- `ntoskrnl!IofCallDriver` at `0x14005f27a`
- `ntoskrnl!IofCallDriver` at `0x1400f199d`
- `ntoskrnl!IofCallDriver` at `0x14005f27a`
- `ntoskrnl!IofCallDriver` at `0x1400f199d`
- `ntoskrnl!IofCompleteRequest` at `0x14005f348`
- `ntoskrnl!IofCompleteRequest` at `0x1400f19f8`
- `ntoskrnl!IofCompleteRequest` at `0x14005f348`
- `ntoskrnl!IofCompleteRequest` at `0x1400f19f8`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400f19e2`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400f19e2`

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
0x14005f0c0  push    rbx
0x14005f0c2  push    rsi
0x14005f0c3  push    r15
0x14005f0c5  sub     rsp, 40h
0x14005f0c9  mov     rbx, [rcx+40h]
0x14005f0cd  mov     rsi, rcx
0x14005f0d0  mov     [rsp+58h+arg_8], rdi
0x14005f0d5  mov     rdi, rdx
0x14005f0d8  mov     [rsp+58h+arg_10], r14
0x14005f0dd  lea     r14, WPP_RECORDER_INITIALIZED
0x14005f0e4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f0eb  lea     r15, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14005f0f2  jnz     loc_14005F2D3
0x14005f0f8  cmp     byte ptr [rbx], 11h
0x14005f0fb  jnz     loc_14005F332
0x14005f101  mov     [rsp+58h+arg_0], rbp
0x14005f106  mov     rbp, [rbx+0F00h]
0x14005f10d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f114  jnz     loc_14005F305
0x14005f11a  mov     rsi, [rdi+0B8h]
0x14005f121  movzx   ecx, byte ptr [rsi+1]
0x14005f125  cmp     ecx, 2
0x14005f128  jz      short loc_14005F19B
0x14005f12a  mov     edx, ecx
0x14005f12c  test    ecx, ecx
0x14005f12e  jz      loc_14005F218
0x14005f134  sub     edx, 1
0x14005f137  jz      loc_14005F3C7
0x14005f13d  cmp     edx, 2
0x14005f140  jnz     loc_14005F388
0x14005f146  call    cs:__imp_KeGetCurrentIrql
0x14005f14d  nop     dword ptr [rax+rax+00h]
0x14005f152  test    al, al
0x14005f154  jnz     loc_14005F2BE
0x14005f15a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f161  jz      short loc_14005F18B
0x14005f163  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f16a  mov     r9d, 71h ; 'q'; int
0x14005f170  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f175  mov     r8d, 0Eh; int
0x14005f17b  mov     dl, 4; int
0x14005f17d  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f182  mov     rcx, [rcx+40h]; int
0x14005f186  call    WPP_RECORDER_SF_q
0x14005f18b  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005f18e  mov     rdx, rsi; struct _IO_STACK_LOCATION *
0x14005f191  mov     rcx, rdi; Irp
0x14005f194  call    ?ndisQueryPower@@_Y2PAGENPNP@@AJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisQueryPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x14005f199  jmp     short loc_14005F1EE
0x14005f19b  call    cs:__imp_KeGetCurrentIrql
0x14005f1a2  nop     dword ptr [rax+rax+00h]
0x14005f1a7  test    al, al
0x14005f1a9  jnz     loc_14005F2BE
0x14005f1af  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f1b6  jz      short loc_14005F1E0
0x14005f1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f1bf  mov     r9d, 72h ; 'r'; int
0x14005f1c5  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f1ca  mov     r8d, 0Eh; int
0x14005f1d0  mov     dl, 4; int
0x14005f1d2  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f1d7  mov     rcx, [rcx+40h]; int
0x14005f1db  call    WPP_RECORDER_SF_q
0x14005f1e0  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005f1e3  mov     rdx, rsi; struct _IO_STACK_LOCATION *
0x14005f1e6  mov     rcx, rdi; Irp
0x14005f1e9  call    ?ndisSetPower@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x14005f1ee  mov     esi, eax
0x14005f1f0  mov     rbp, [rsp+58h+arg_0]
0x14005f1f5  mov     rdi, [rsp+58h+arg_8]
0x14005f1fa  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f201  mov     r14, [rsp+58h+arg_10]
0x14005f206  jnz     loc_14005F28D
0x14005f20c  mov     eax, esi
0x14005f20e  add     rsp, 40h
0x14005f212  pop     r15
0x14005f214  pop     rsi
0x14005f215  pop     rbx
0x14005f216  retn
0x14005f218  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f21f  jnz     loc_14005F402
0x14005f225  mov     eax, [rbx+534h]
0x14005f22b  lea     rcx, ?ndisWaitWakeIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisWaitWakeIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14005f232  mov     [rsi+8], eax
0x14005f235  mov     rdx, rdi; Irp
0x14005f238  mov     rax, [rdi+0B8h]
0x14005f23f  movups  xmm0, xmmword ptr [rax]
0x14005f242  movups  xmmword ptr [rax-48h], xmm0
0x14005f246  movups  xmm1, xmmword ptr [rax+10h]
0x14005f24a  movups  xmmword ptr [rax-38h], xmm1
0x14005f24e  movups  xmm0, xmmword ptr [rax+20h]
0x14005f252  movups  xmmword ptr [rax-28h], xmm0
0x14005f256  movsd   xmm1, qword ptr [rax+30h]
0x14005f25b  movsd   qword ptr [rax-18h], xmm1
0x14005f260  mov     byte ptr [rax-45h], 0
0x14005f264  mov     rax, [rdi+0B8h]
0x14005f26b  mov     [rax-10h], rcx
0x14005f26f  mov     rcx, rbp; DeviceObject
0x14005f272  mov     [rax-8], rbx
0x14005f276  mov     byte ptr [rax-45h], 0E0h
0x14005f27a  call    cs:__imp_IofCallDriver
0x14005f281  nop     dword ptr [rax+rax+00h]
0x14005f286  mov     esi, eax
0x14005f288  jmp     loc_14005F1F0
0x14005f28d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f294  mov     r9d, 74h ; 't'; int
0x14005f29a  mov     dword ptr [rsp+58h+var_28], esi; char
0x14005f29e  mov     r8d, 0Eh; int
0x14005f2a4  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f2a9  mov     dl, 4; int
0x14005f2ab  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f2b0  mov     rcx, [rcx+40h]; int
0x14005f2b4  call    WPP_RECORDER_SF_qD
0x14005f2b9  jmp     loc_14005F20C
0x14005f2be  mov     rdx, rdi; struct _IRP *
0x14005f2c1  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005f2c4  call    ?ndisQueuePowerIrp@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@@Z; ndisQueuePowerIrp(_NDIS_MINIPORT_BLOCK *,_IRP *)
0x14005f2c9  mov     esi, 103h
0x14005f2ce  jmp     loc_14005F1F0
0x14005f2d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f2da  mov     r9d, 6Ch ; 'l'; int
0x14005f2e0  mov     qword ptr [rsp+58h+var_28], rdi; char
0x14005f2e5  mov     r8d, 0Eh; int
0x14005f2eb  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f2f0  mov     dl, 4; int
0x14005f2f2  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f2f7  mov     rcx, [rcx+40h]; int
0x14005f2fb  call    WPP_RECORDER_SF_qq
0x14005f300  jmp     loc_14005F0F8
0x14005f305  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f30c  mov     r9d, 6Eh ; 'n'; int
0x14005f312  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f317  mov     r8d, 0Eh; int
0x14005f31d  mov     dl, 4; int
0x14005f31f  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f324  mov     rcx, [rcx+40h]; int
0x14005f328  call    WPP_RECORDER_SF_q
0x14005f32d  jmp     loc_14005F11A
0x14005f332  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f339  jnz     short loc_14005F359
0x14005f33b  mov     esi, 0C0000010h
0x14005f340  xor     edx, edx; PriorityBoost
0x14005f342  mov     rcx, rdi; Irp
0x14005f345  mov     [rdi+30h], esi
0x14005f348  call    cs:__imp_IofCompleteRequest
0x14005f34f  nop     dword ptr [rax+rax+00h]
0x14005f354  jmp     loc_14005F1F5
0x14005f359  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f360  mov     r9d, 6Dh ; 'm'; int
0x14005f366  mov     qword ptr [rsp+58h+var_28], rdi; char
0x14005f36b  mov     r8d, 0Eh; int
0x14005f371  mov     qword ptr [rsp+58h+var_30], rsi; char
0x14005f376  mov     dl, 4; int
0x14005f378  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f37d  mov     rcx, [rcx+40h]; int
0x14005f381  call    WPP_RECORDER_SF_qq
0x14005f386  jmp     short loc_14005F33B
0x14005f388  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f38f  jz      loc_1400F198C
0x14005f395  mov     dword ptr [rsp+58h+var_28], ecx; char
0x14005f399  mov     r9d, 73h ; 's'; int
0x14005f39f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f3a6  mov     r8d, 0Eh; int
0x14005f3ac  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f3b1  mov     dl, 4; int
0x14005f3b3  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f3b8  mov     rcx, [rcx+40h]; int
0x14005f3bc  call    WPP_RECORDER_SF_qL
0x14005f3c1  nop
0x14005f3c2  jmp     loc_1400F198C
0x14005f3c7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005f3ce  jz      loc_1400F19B0
0x14005f3d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f3db  mov     r9d, 6Fh ; 'o'; int
0x14005f3e1  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f3e6  mov     r8d, 0Eh; int
0x14005f3ec  mov     dl, 4; int
0x14005f3ee  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f3f3  mov     rcx, [rcx+40h]; int
0x14005f3f7  call    WPP_RECORDER_SF_q
0x14005f3fc  nop
0x14005f3fd  jmp     loc_1400F19B0
0x14005f402  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f409  mov     r9d, 70h ; 'p'; int
0x14005f40f  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005f414  mov     r8d, 0Eh; int
0x14005f41a  mov     dl, 4; int
0x14005f41c  mov     [rsp+58h+var_38], r15; struct _GUID *
0x14005f421  mov     rcx, [rcx+40h]; int
0x14005f425  call    WPP_RECORDER_SF_q
0x14005f42a  jmp     loc_14005F225
0x1400f198c  inc     byte ptr [rdi+43h]
0x1400f198f  mov     rdx, rdi; Irp
0x1400f1992  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400f199a  mov     rcx, rbp; DeviceObject
0x1400f199d  call    cs:__imp_IofCallDriver
0x1400f19a4  nop     dword ptr [rax+rax+00h]
0x1400f19a9  mov     esi, eax
0x1400f19ab  jmp     loc_14005F1F0
0x1400f19b0  mov     rax, [rdi+0B8h]
0x1400f19b7  mov     rdx, rdi
0x1400f19ba  mov     rcx, rbp
0x1400f19bd  movups  xmm0, xmmword ptr [rax]
0x1400f19c0  movups  xmmword ptr [rax-48h], xmm0
0x1400f19c4  movups  xmm1, xmmword ptr [rax+10h]
0x1400f19c8  movups  xmmword ptr [rax-38h], xmm1
0x1400f19cc  movups  xmm0, xmmword ptr [rax+20h]
0x1400f19d0  movups  xmmword ptr [rax-28h], xmm0
0x1400f19d4  movsd   xmm1, qword ptr [rax+30h]
0x1400f19d9  movsd   qword ptr [rax-18h], xmm1
0x1400f19de  mov     byte ptr [rax-45h], 0
0x1400f19e2  call    cs:__imp_IoSynchronousCallDriver
0x1400f19e9  nop     dword ptr [rax+rax+00h]
0x1400f19ee  xor     edx, edx; PriorityBoost
0x1400f19f0  mov     rcx, rdi; Irp
0x1400f19f3  mov     esi, eax
0x1400f19f5  mov     [rdi+30h], eax
0x1400f19f8  call    cs:__imp_IofCompleteRequest
0x1400f19ff  nop     dword ptr [rax+rax+00h]
0x1400f1a04  nop
0x1400f1a05  jmp     loc_14005F1F0
```
