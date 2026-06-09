# HidpPdoPower

- ea: `0x180015438`
- end: `0x180015b91`
- name: `HidpPdoPower`
- size: `1881`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x180009a78`
- `0x180012d1c`
- `0x180013860`
- `0x180013d94`
- `0x18001414c`
- `0x180015438`
- `0x1800170e8`
- `0x18001e8ec`
- `0x18001f468`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x180015731`
- `ntoskrnl!PoSetPowerState` at `0x180015731`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180015aa4`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180015aa4`
- `ntoskrnl!IofCompleteRequest` at `0x180015ab8`
- `ntoskrnl!IofCompleteRequest` at `0x180015ab8`
- `ntoskrnl!PoRequestPowerIrp` at `0x1800158e9`
- `ntoskrnl!PoRequestPowerIrp` at `0x1800158e9`

## pseudocode

```c
__int64 __fastcall HidpPdoPower(__int64 a1, IRP *a2, __int64 a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v4; // rsi
  __int64 v5; // r10
  int MinorFunction; // r13d
  __int64 v8; // rdx
  char v9; // di
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rcx
  unsigned int Status; // ebx
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // ecx
  unsigned int LowPart; // eax
  POWER_STATE v17; // ebx
  unsigned int Options; // ecx
  int v19; // edx
  int v20; // r8d
  int Context; // [rsp+20h] [rbp-A8h]
  IRP *v23; // [rsp+58h] [rbp-70h]
  __int64 v24; // [rsp+D0h] [rbp+8h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = a1 + 32;
  v5 = *(_QWORD *)(a1 + 96) + 32LL;
  v24 = v5;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v8 = 4;
  if ( CurrentStackLocation->MinorFunction )
  {
    if ( (unsigned int)CurrentStackLocation->MinorFunction - 2 >= 2 )
    {
      v9 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v8) = 0;
      }
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qdqqcc(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          a3,
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 704LL),
          3,
          9,
          22,
          (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 32LL),
          *(_DWORD *)(a1 + 40),
          *(_QWORD *)(a1 + 80),
          (char)a2,
          22,
          CurrentStackLocation->MinorFunction);
      goto LABEL_33;
    }
    if ( CurrentStackLocation->Parameters.Create.Options )
    {
      v10 = WPP_GLOBAL_Control;
      v9 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v8) = 0;
      }
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v23 = a2;
        goto LABEL_32;
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      v9 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v8) = 0;
      }
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v23 = a2;
LABEL_32:
        WPP_RECORDER_AND_TRACE_SF_qdqqccL(v10->AttachedDevice, v8, a3, *(_QWORD *)(v5 + 672));
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    v9 = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v8) = 0;
    }
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = a2;
      goto LABEL_32;
    }
  }
LABEL_33:
  if ( (unsigned int)(*(_DWORD *)(v4 + 4) - 3) > 2 )
  {
    if ( !MinorFunction )
    {
      Status = -1073741101;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v8) = 0;
      }
      if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdq(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          a3,
          *(_QWORD *)(v24 + 672),
          4,
          9,
          26,
          (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v4 + 64) + 32LL),
          *(_DWORD *)(v4 + 8),
          *(_QWORD *)(v4 + 48),
          v23);
      }
      goto LABEL_94;
    }
    v11 = (unsigned int)(MinorFunction - 2);
    if ( MinorFunction == 2 )
    {
      if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(v11, v8, a3) )
      {
        Options = CurrentStackLocation->Parameters.Create.Options;
        if ( Options )
        {
          if ( Options == 1 )
            *(_DWORD *)(v4 + 80) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        }
        else
        {
          *(_DWORD *)(v4 + 76) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        }
      }
      goto LABEL_55;
    }
    goto LABEL_37;
  }
  if ( !MinorFunction )
  {
    if ( *(_DWORD *)(v24 + 360) <= *(_DWORD *)(v24 + 340) )
    {
      Status = EnqueueCollectionWaitWakeIrp(v24, v4, a2, 0);
      if ( Status == 259 )
        return Status;
    }
    else
    {
      Status = -1073741101;
    }
    goto LABEL_94;
  }
  if ( MinorFunction == 1 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v8) = 0;
    }
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqq(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        a3,
        *(_QWORD *)(v24 + 672),
        2,
        9,
        25,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v4 + 64) + 32LL),
        *(_DWORD *)(v4 + 8),
        *(_QWORD *)(v4 + 48),
        (char)a2);
    }
    goto LABEL_38;
  }
  LODWORD(v11) = MinorFunction - 2;
  if ( MinorFunction != 2 )
  {
LABEL_37:
    if ( (_DWORD)v11 != 1 )
    {
LABEL_38:
      Status = a2->IoStatus.Status;
LABEL_94:
      PoStartNextPowerIrp(a2);
      a2->IoStatus.Status = Status;
      IofCompleteRequest(a2, 0);
      if ( (int)(Status + 0x80000000) >= 0 && Status != -1073741637 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v9 = 0;
        }
        if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = v9;
          LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qdqqccd(
            WPP_GLOBAL_Control->AttachedDevice,
            v19,
            v20,
            *(_QWORD *)(v24 + 672),
            Context,
            9,
            27,
            (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v4 + 64) + 32LL),
            *(_DWORD *)(v4 + 8),
            *(_QWORD *)(v4 + 48),
            (char)a2,
            22,
            MinorFunction,
            Status);
        }
      }
      return Status;
    }
LABEL_55:
    Status = 0;
    goto LABEL_94;
  }
  PoSetPowerState(
    *(PDEVICE_OBJECT *)(v4 + 48),
    CurrentStackLocation->Parameters.Power.Type,
    CurrentStackLocation->Parameters.Power.State);
  v15 = CurrentStackLocation->Parameters.Create.Options;
  if ( v15 )
  {
    if ( v15 != 1 )
      goto LABEL_38;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v13) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v13) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v14) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v14) = 0;
    }
    if ( (_BYTE)v13 || (_BYTE)v14 )
      WPP_RECORDER_AND_TRACE_SF_qdqL(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v14,
        *(_QWORD *)(v24 + 672),
        5,
        9,
        24,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v4 + 64) + 32LL),
        *(_DWORD *)(v4 + 8),
        *(_QWORD *)(v4 + 48),
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 1);
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1
      && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 2
      && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 3 > 1 )
    {
      goto LABEL_38;
    }
    *(_DWORD *)(v4 + 80) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    goto LABEL_55;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  *(_DWORD *)(v4 + 76) = LowPart;
  v17.SystemState = PowerSystemWorking;
  if ( LowPart != 1 )
    v17.SystemState = PowerSystemSleeping3;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || (LOBYTE(v13) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(v13) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v14) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v14) = 0;
  }
  if ( (_BYTE)v13 || (_BYTE)v14 )
    WPP_RECORDER_AND_TRACE_SF_qdqL(
      WPP_GLOBAL_Control->AttachedDevice,
      v13,
      v14,
      *(_QWORD *)(v24 + 672),
      5,
      9,
      23,
      (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
      *(_QWORD *)(*(_QWORD *)(v4 + 64) + 32LL),
      *(_DWORD *)(v4 + 8),
      *(_QWORD *)(v4 + 48),
      LOBYTE(v17.SystemState) - 1);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  PoRequestPowerIrp(
    *(PDEVICE_OBJECT *)(v4 + 48),
    2u,
    v17,
    (PREQUEST_POWER_COMPLETE)CollectionPowerRequestCompletion,
    a2,
    0);
  return 259;
}

```

## disassembly

```asm
0x180015438  push    rbx
0x18001543a  push    rbp
0x18001543b  push    rsi
0x18001543c  push    rdi
0x18001543d  push    r12
0x18001543f  push    r13
0x180015441  push    r14
0x180015443  push    r15
0x180015445  sub     rsp, 88h
0x18001544c  mov     rbx, [rdx+0B8h]
0x180015453  lea     rsi, [rcx+20h]
0x180015457  mov     r10, [rcx+60h]
0x18001545b  lea     r11, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x180015462  add     r10, 20h ; ' '
0x180015466  xor     r9d, r9d
0x180015469  mov     rbp, rdx
0x18001546c  mov     [rsp+0C8h+arg_0], r10
0x180015474  movzx   r13d, byte ptr [rbx+1]
0x180015479  mov     edx, 4
0x18001547e  mov     ecx, r13d
0x180015481  test    r13d, r13d
0x180015484  jz      loc_18001565A
0x18001548a  sub     ecx, 2
0x18001548d  jz      loc_180015543
0x180015493  cmp     ecx, 1
0x180015496  jz      loc_180015543
0x18001549c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154a3  lea     r12, WPP_GLOBAL_Control
0x1800154aa  lea     edi, [rdx-3]
0x1800154ad  mov     r14d, 100h
0x1800154b3  cmp     rcx, r12
0x1800154b6  jz      short loc_1800154C7
0x1800154b8  test    [rcx+2Ch], r14d
0x1800154bc  jz      short loc_1800154C7
0x1800154be  cmp     byte ptr [rcx+29h], 3
0x1800154c2  mov     dl, dil
0x1800154c5  jnb     short loc_1800154CA
0x1800154c7  mov     dl, r9b
0x1800154ca  lea     r15, WPP_RECORDER_INITIALIZED
0x1800154d1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800154d8  setnz   r8b
0x1800154dc  test    dl, dl
0x1800154de  jnz     short loc_1800154E9
0x1800154e0  test    r8b, r8b
0x1800154e3  jz      loc_1800156E9
0x1800154e9  mov     rax, [rsi+30h]
0x1800154ed  mov     r9, [rsi+40h]
0x1800154f1  mov     rcx, [rcx+18h]
0x1800154f5  mov     [rsp+0C8h+var_60], r13b
0x1800154fa  mov     [rsp+0C8h+var_68], 16h
0x1800154ff  mov     [rsp+0C8h+var_70], rbp
0x180015504  mov     [rsp+0C8h+var_78], rax
0x180015509  mov     eax, [rsi+8]
0x18001550c  mov     [rsp+0C8h+var_80], eax
0x180015510  mov     rax, [r9+20h]
0x180015514  mov     r9, [r10+2A0h]
0x18001551b  mov     [rsp+0C8h+var_88], rax
0x180015520  mov     [rsp+0C8h+var_90], r11
0x180015525  mov     [rsp+0C8h+var_98], 16h
0x18001552c  mov     dword ptr [rsp+0C8h+Irp], 9
0x180015534  mov     byte ptr [rsp+0C8h+Context], 3
0x180015539  call    WPP_RECORDER_AND_TRACE_SF_qdqqcc
0x18001553e  jmp     loc_1800156E9
0x180015543  cmp     [rbx+10h], r9d
0x180015547  jnz     loc_1800155D5
0x18001554d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015554  lea     r12, WPP_GLOBAL_Control
0x18001555b  mov     edi, 1
0x180015560  mov     r14d, 100h
0x180015566  cmp     rcx, r12
0x180015569  jz      short loc_180015579
0x18001556b  test    [rcx+2Ch], r14d
0x18001556f  jz      short loc_180015579
0x180015571  cmp     [rcx+29h], dl
0x180015574  mov     dl, dil
0x180015577  jnb     short loc_18001557C
0x180015579  mov     dl, r9b
0x18001557c  lea     r15, WPP_RECORDER_INITIALIZED
0x180015583  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001558a  setnz   r8b
0x18001558e  test    dl, dl
0x180015590  jnz     short loc_18001559B
0x180015592  test    r8b, r8b
0x180015595  jz      loc_1800156E9
0x18001559b  mov     eax, [rbx+18h]
0x18001559e  mov     r9, [rsi+40h]
0x1800155a2  mov     [rsp+0C8h+var_58], eax
0x1800155a6  mov     rax, [rsi+30h]
0x1800155aa  mov     [rsp+0C8h+var_60], r13b
0x1800155af  mov     [rsp+0C8h+var_70], rbp
0x1800155b4  mov     [rsp+0C8h+var_78], rax
0x1800155b9  mov     eax, [rsi+8]
0x1800155bc  mov     [rsp+0C8h+var_80], eax
0x1800155c0  mov     rax, [r9+20h]
0x1800155c4  mov     [rsp+0C8h+var_88], rax
0x1800155c9  mov     [rsp+0C8h+var_98], 13h
0x1800155d0  jmp     loc_1800156D9
0x1800155d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155dc  lea     r12, WPP_GLOBAL_Control
0x1800155e3  mov     edi, 1
0x1800155e8  mov     r14d, 100h
0x1800155ee  cmp     rcx, r12
0x1800155f1  jz      short loc_180015601
0x1800155f3  test    [rcx+2Ch], r14d
0x1800155f7  jz      short loc_180015601
0x1800155f9  cmp     [rcx+29h], dl
0x1800155fc  mov     dl, dil
0x1800155ff  jnb     short loc_180015604
0x180015601  mov     dl, r9b
0x180015604  lea     r15, WPP_RECORDER_INITIALIZED
0x18001560b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015612  setnz   r8b
0x180015616  test    dl, dl
0x180015618  jnz     short loc_180015623
0x18001561a  test    r8b, r8b
0x18001561d  jz      loc_1800156E9
0x180015623  mov     eax, [rbx+18h]
0x180015626  mov     r9, [rsi+40h]
0x18001562a  mov     [rsp+0C8h+var_58], eax
0x18001562e  mov     rax, [rsi+30h]
0x180015632  mov     [rsp+0C8h+var_60], r13b
0x180015637  mov     [rsp+0C8h+var_70], rbp
0x18001563c  mov     [rsp+0C8h+var_78], rax
0x180015641  mov     eax, [rsi+8]
0x180015644  mov     [rsp+0C8h+var_80], eax
0x180015648  mov     rax, [r9+20h]
0x18001564c  mov     [rsp+0C8h+var_88], rax
0x180015651  mov     [rsp+0C8h+var_98], 14h
0x180015658  jmp     short loc_1800156D9
0x18001565a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015661  lea     r12, WPP_GLOBAL_Control
0x180015668  mov     edi, 1
0x18001566d  mov     r14d, 100h
0x180015673  cmp     rcx, r12
0x180015676  jz      short loc_180015686
0x180015678  test    [rcx+2Ch], r14d
0x18001567c  jz      short loc_180015686
0x18001567e  cmp     [rcx+29h], dl
0x180015681  mov     dl, dil
0x180015684  jnb     short loc_180015689
0x180015686  mov     dl, r9b
0x180015689  lea     r15, WPP_RECORDER_INITIALIZED
0x180015690  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015697  setnz   r8b
0x18001569b  test    dl, dl
0x18001569d  jnz     short loc_1800156A4
0x18001569f  test    r8b, r8b
0x1800156a2  jz      short loc_1800156E9
0x1800156a4  mov     eax, [rbx+8]
0x1800156a7  mov     r9, [rsi+40h]
0x1800156ab  mov     [rsp+0C8h+var_58], eax
0x1800156af  mov     rax, [rsi+30h]
0x1800156b3  mov     [rsp+0C8h+var_60], r13b
0x1800156b8  mov     [rsp+0C8h+var_70], rbp
0x1800156bd  mov     [rsp+0C8h+var_78], rax
0x1800156c2  mov     eax, [rsi+8]
0x1800156c5  mov     [rsp+0C8h+var_80], eax
0x1800156c9  mov     rax, [r9+20h]
0x1800156cd  mov     [rsp+0C8h+var_88], rax
0x1800156d2  mov     [rsp+0C8h+var_98], 15h
0x1800156d9  mov     r9, [r10+2A0h]
0x1800156e0  mov     rcx, [rcx+18h]
0x1800156e4  call    WPP_RECORDER_AND_TRACE_SF_qdqqccL
0x1800156e9  mov     eax, [rsi+4]
0x1800156ec  xor     r9d, r9d
0x1800156ef  sub     eax, 3
0x1800156f2  mov     ecx, r13d
0x1800156f5  cmp     eax, 2
0x1800156f8  ja      loc_1800159D1
0x1800156fe  test    r13d, r13d
0x180015701  jz      loc_180015994
0x180015707  sub     ecx, 1
0x18001570a  jz      loc_1800158FF
0x180015710  sub     ecx, 1
0x180015713  jz      short loc_180015726
0x180015715  cmp     ecx, 1
0x180015718  jz      loc_18001580E
0x18001571e  mov     ebx, [rbp+30h]
0x180015721  jmp     loc_180015AA1
0x180015726  mov     r8d, [rbx+18h]; State
0x18001572a  mov     edx, [rbx+10h]; Type
0x18001572d  mov     rcx, [rsi+30h]; DeviceObject
0x180015731  call    cs:__imp_PoSetPowerState
0x180015738  nop     dword ptr [rax+rax+00h]
0x18001573d  mov     ecx, [rbx+10h]
0x180015740  xor     r9d, r9d
0x180015743  test    ecx, ecx
0x180015745  jz      loc_180015816
0x18001574b  cmp     ecx, 1
0x18001574e  jnz     short loc_18001571E
0x180015750  mov     rcx, cs:WPP_GLOBAL_Control
0x180015757  cmp     rcx, r12
0x18001575a  jz      short loc_18001576B
0x18001575c  test    [rcx+2Ch], r14d
0x180015760  jz      short loc_18001576B
0x180015762  cmp     byte ptr [rcx+29h], 5
0x180015766  mov     dl, dil
0x180015769  jnb     short loc_18001576E
0x18001576b  mov     dl, r9b
0x18001576e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015775  jz      short loc_180015781
0x180015777  mov     r8b, dil
0x18001577a  cmp     [rcx+48h], r9w
0x18001577f  jnz     short loc_180015784
0x180015781  mov     r8b, r9b
0x180015784  test    dl, dl
0x180015786  jnz     short loc_18001578D
0x180015788  test    r8b, r8b
0x18001578b  jz      short loc_1800157EE
0x18001578d  mov     eax, [rbx+18h]
0x180015790  mov     r9, [rsi+40h]
0x180015794  sub     eax, edi
0x180015796  mov     rcx, [rcx+18h]
0x18001579a  mov     dword ptr [rsp+0C8h+var_70], eax
0x18001579e  mov     rax, [rsi+30h]
0x1800157a2  mov     [rsp+0C8h+var_78], rax
0x1800157a7  mov     eax, [rsi+8]
0x1800157aa  mov     [rsp+0C8h+var_80], eax
0x1800157ae  mov     rax, [r9+20h]
0x1800157b2  mov     r9, [rsp+0C8h+arg_0]
0x1800157ba  mov     [rsp+0C8h+var_88], rax
0x1800157bf  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x1800157c6  mov     [rsp+0C8h+var_90], rax
0x1800157cb  mov     [rsp+0C8h+var_98], 18h
0x1800157d2  mov     r9, [r9+2A0h]
0x1800157d9  mov     dword ptr [rsp+0C8h+Irp], 9
0x1800157e1  mov     byte ptr [rsp+0C8h+Context], 5
0x1800157e6  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x1800157eb  xor     r9d, r9d
0x1800157ee  mov     edx, [rbx+18h]
0x1800157f1  mov     ecx, edx
0x1800157f3  sub     ecx, 1
0x1800157f6  jz      short loc_18001580B
0x1800157f8  sub     ecx, 1
0x1800157fb  jz      short loc_18001580B
0x1800157fd  sub     ecx, 1
0x180015800  jz      short loc_18001580B
0x180015802  cmp     ecx, 1
0x180015805  jnz     loc_18001571E
0x18001580b  mov     [rsi+50h], edx
0x18001580e  mov     ebx, r9d
0x180015811  jmp     loc_180015AA1
0x180015816  mov     eax, [rbx+18h]
0x180015819  cmp     eax, edi
0x18001581b  mov     [rsi+4Ch], eax
0x18001581e  mov     ebx, edi
0x180015820  mov     eax, 4
0x180015825  cmovnz  ebx, eax
0x180015828  mov     rcx, cs:WPP_GLOBAL_Control
0x18001582f  cmp     rcx, r12
0x180015832  jz      short loc_180015843
0x180015834  test    [rcx+2Ch], r14d
0x180015838  jz      short loc_180015843
0x18001583a  cmp     byte ptr [rcx+29h], 5
0x18001583e  mov     dl, dil
0x180015841  jnb     short loc_180015846
0x180015843  mov     dl, r9b
0x180015846  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001584d  jz      short loc_180015859
0x18001584f  mov     r8b, dil
0x180015852  cmp     [rcx+48h], r9w
0x180015857  jnz     short loc_18001585C
0x180015859  mov     r8b, r9b
0x18001585c  test    dl, dl
0x18001585e  jnz     short loc_180015865
0x180015860  test    r8b, r8b
0x180015863  jz      short loc_1800158C4
0x180015865  mov     r10, [rsi+40h]
0x180015869  lea     eax, [rbx-1]
0x18001586c  mov     r9, [rsp+0C8h+arg_0]
0x180015874  mov     rcx, [rcx+18h]
0x180015878  mov     dword ptr [rsp+0C8h+var_70], eax
0x18001587c  mov     rax, [rsi+30h]
0x180015880  mov     r9, [r9+2A0h]
0x180015887  mov     [rsp+0C8h+var_78], rax
0x18001588c  mov     eax, [rsi+8]
0x18001588f  mov     [rsp+0C8h+var_80], eax
0x180015893  mov     rax, [r10+20h]
0x180015897  mov     [rsp+0C8h+var_88], rax
0x18001589c  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x1800158a3  mov     [rsp+0C8h+var_90], rax
0x1800158a8  mov     [rsp+0C8h+var_98], 17h
0x1800158af  mov     dword ptr [rsp+0C8h+Irp], 9
0x1800158b7  mov     byte ptr [rsp+0C8h+Context], 5
0x1800158bc  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x1800158c1  xor     r9d, r9d
0x1800158c4  mov     rax, [rbp+0B8h]
0x1800158cb  mov     r8d, ebx; PowerState
0x1800158ce  mov     [rsp+0C8h+Irp], r9; Irp
0x1800158d3  mov     dl, 2; MinorFunction
0x1800158d5  lea     r9, CollectionPowerRequestCompletion; CompletionFunction
0x1800158dc  mov     [rsp+0C8h+Context], rbp; Context
0x1800158e1  or      [rax+3], dil
0x1800158e5  mov     rcx, [rsi+30h]; DeviceObject
0x1800158e9  call    cs:__imp_PoRequestPowerIrp
0x1800158f0  nop     dword ptr [rax+rax+00h]
0x1800158f5  mov     ebx, 103h
0x1800158fa  jmp     loc_180015B7A
0x1800158ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180015906  cmp     rcx, r12
  ... truncated ...
```
