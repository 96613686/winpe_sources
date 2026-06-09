# HidpFdoPower

- ea: `0x180015b98`
- end: `0x180016180`
- name: `HidpFdoPower`
- size: `1512`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x18000a020`
- `0x18000ddc8`
- `0x18000ff44`
- `0x180013500`
- `0x180013a14`
- `0x180014368`
- `0x180015b98`
- `0x1800177e4`
- `0x18001e8ec`
- `0x18001f980`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x180015e90`
- `ntoskrnl!PoSetPowerState` at `0x180015e90`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180015fb4`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180015fb4`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18001601a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18001601a`
- `ntoskrnl!IofCompleteRequest` at `0x180016039`
- `ntoskrnl!IofCompleteRequest` at `0x180016039`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180015efe`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180015efe`

## pseudocode

```c
__int64 __fastcall HidpFdoPower(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // r8d
  int v7; // edx
  char v8; // di
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 Options; // rcx
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  int LowPart; // esi
  __int64 v17; // rcx
  char v18; // si
  int v19; // edx
  int v20; // r8d
  _IO_STACK_LOCATION *v21; // rax
  _IO_STACK_LOCATION *v22; // rax
  ULONG RemlockSize; // [rsp+20h] [rbp-88h]
  IRP *v25; // [rsp+48h] [rbp-60h]
  char v27; // [rsp+C0h] [rbp+18h]
  unsigned __int8 MinorFunction; // [rsp+C8h] [rbp+20h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v27 = 0;
  v5 = 0x80000000;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v6 = MinorFunction;
  v7 = 4;
  if ( MinorFunction )
  {
    v6 = MinorFunction - 2;
    if ( v6 >= 2 )
    {
      v8 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v7) = 0;
      }
      if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qqcc(
          WPP_GLOBAL_Control->AttachedDevice,
          v7,
          v6,
          *(_QWORD *)(a1 + 704),
          3,
          9,
          31,
          (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
          *(_QWORD *)(a1 + 32),
          (char)a2,
          22,
          CurrentStackLocation->MinorFunction);
      }
      goto LABEL_33;
    }
    if ( CurrentStackLocation->Parameters.Create.Options )
    {
      v9 = WPP_GLOBAL_Control;
      v8 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v7) = 0;
      }
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = a2;
        goto LABEL_32;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      v8 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v7) = 0;
      }
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = a2;
LABEL_32:
        WPP_RECORDER_AND_TRACE_SF_qqccL(v9->AttachedDevice, v7, v6, *(_QWORD *)(a1 + 704));
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    v8 = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v7) = 0;
    }
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = a2;
      goto LABEL_32;
    }
  }
LABEL_33:
  if ( !*(_DWORD *)(a1 + 1752) )
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v6,
        *(_QWORD *)(a1 + 704),
        3,
        9,
        32,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *(_QWORD *)(a1 + 32),
        v25);
    }
  }
  if ( !MinorFunction )
  {
    *(_QWORD *)(a1 + 400) = a2;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 408), 4, 2) == 3 )
    {
      *(_DWORD *)(a1 + 408) = 7;
      v5 = -1073741536;
LABEL_68:
      v27 = 1;
    }
LABEL_69:
    v18 = 0;
    goto LABEL_70;
  }
  if ( MinorFunction != 2 )
    goto LABEL_69;
  PoSetPowerState(
    *(PDEVICE_OBJECT *)(a1 + 32),
    CurrentStackLocation->Parameters.Power.Type,
    CurrentStackLocation->Parameters.Power.State);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( (_DWORD)Options )
  {
    if ( (_DWORD)Options == 1 )
    {
      if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
      {
        if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2
          || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 3 <= 1 )
        {
          CancelAllPingPongIrps(a1 + 32);
          *(_DWORD *)(a1 + 396) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        }
        goto LABEL_69;
      }
      v13 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 672), a2, File, 1u, 0x20u);
      v5 = v13;
      if ( v13 < 0 )
      {
        LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v14,
            v15,
            *(_QWORD *)(a1 + 704),
            2,
            9,
            33,
            (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
            *(_QWORD *)(a1 + 32),
            v13);
        }
        goto LABEL_68;
      }
    }
    goto LABEL_69;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  *(_DWORD *)(a1 + 392) = LowPart;
  if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(Options, v10, v11) )
  {
    v17 = a1 + 2280;
    if ( LowPart <= 1 )
      v17 = a1 + 2288;
    KeQuerySystemTimePrecise(v17);
  }
  if ( LowPart > *(_DWORD *)(a1 + 372) )
    CompleteAllCollectionWaitWakeIrps(a1 + 32, 3221226195LL);
  v18 = 1;
LABEL_70:
  PoStartNextPowerIrp(a2);
  if ( v27 )
  {
    a2->IoStatus.Status = v5;
    IofCompleteRequest(a2, 0);
  }
  else
  {
    v21 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v21[-1].MajorFunction = *(_OWORD *)&v21->MajorFunction;
    *(_OWORD *)&v21[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v21->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v21[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v21->Parameters.SetQuota + 6);
    v21[-1].FileObject = v21->FileObject;
    v21[-1].Control = 0;
    v22 = a2->Tail.Overlay.CurrentStackLocation;
    v22[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))HidpFdoPowerCompletion;
    v22[-1].Context = (void *)a1;
    v22[-1].Control = -32;
    if ( v18 )
    {
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      HidpCallDriver(*(_QWORD *)(a1 + 32), a2);
      return 259;
    }
    v5 = HidpCallDriver(*(_QWORD *)(a1 + 32), a2);
  }
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -1073741637 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v8 = 0;
    }
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = v8;
      LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqccd(
        WPP_GLOBAL_Control->AttachedDevice,
        v19,
        v20,
        *(_QWORD *)(a1 + 704),
        RemlockSize,
        9,
        34,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *(_QWORD *)(a1 + 32),
        (char)a2,
        22,
        MinorFunction,
        v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180015b98  mov     [rsp+arg_0], rcx
0x180015b9d  push    rbx
0x180015b9e  push    rbp
0x180015b9f  push    rsi
0x180015ba0  push    rdi
0x180015ba1  push    r13
0x180015ba3  push    r14
0x180015ba5  push    r15
0x180015ba7  sub     rsp, 70h
0x180015bab  mov     rsi, [rdx+0B8h]
0x180015bb2  lea     r11, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x180015bb9  xor     r10d, r10d
0x180015bbc  mov     rbp, rdx
0x180015bbf  mov     rbx, rcx
0x180015bc2  mov     [rsp+0A8h+arg_10], r10b
0x180015bca  mov     r14d, 80000000h
0x180015bd0  mov     [rsp+0A8h+arg_8], r10b
0x180015bd8  movzx   r9d, byte ptr [rsi+1]
0x180015bdd  mov     [rsp+0A8h+arg_18], r9d
0x180015be5  mov     r8d, r9d
0x180015be8  lea     edx, [r10+4]
0x180015bec  test    r9d, r9d
0x180015bef  jz      loc_180015D7E
0x180015bf5  sub     r8d, 2
0x180015bf9  jz      loc_180015C99
0x180015bff  cmp     r8d, 1
0x180015c03  jz      loc_180015C99
0x180015c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c10  lea     r13, WPP_GLOBAL_Control
0x180015c17  lea     edi, [rdx-3]
0x180015c1a  cmp     rcx, r13
0x180015c1d  jz      short loc_180015C31
0x180015c1f  test    dword ptr [rcx+2Ch], 100h
0x180015c26  jz      short loc_180015C31
0x180015c28  cmp     byte ptr [rcx+29h], 3
0x180015c2c  mov     dl, dil
0x180015c2f  jnb     short loc_180015C34
0x180015c31  mov     dl, r10b
0x180015c34  lea     r15, WPP_RECORDER_INITIALIZED
0x180015c3b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015c42  setnz   r8b
0x180015c46  test    dl, dl
0x180015c48  jnz     short loc_180015C53
0x180015c4a  test    r8b, r8b
0x180015c4d  jz      loc_180015DF6
0x180015c53  mov     rax, [rbx+20h]
0x180015c57  mov     rcx, [rcx+18h]
0x180015c5b  mov     [rsp+0A8h+var_50], r9b
0x180015c60  mov     r9, [rbx+2C0h]
0x180015c67  mov     [rsp+0A8h+var_58], 16h
0x180015c6c  mov     [rsp+0A8h+var_60], rbp
0x180015c71  mov     [rsp+0A8h+var_68], rax
0x180015c76  mov     [rsp+0A8h+var_70], r11
0x180015c7b  mov     [rsp+0A8h+var_78], 1Fh
0x180015c82  mov     [rsp+0A8h+var_80], 9
0x180015c8a  mov     byte ptr [rsp+0A8h+RemlockSize], 3
0x180015c8f  call    WPP_RECORDER_AND_TRACE_SF_qqcc
0x180015c94  jmp     loc_180015DF6
0x180015c99  cmp     [rsi+10h], r10d
0x180015c9d  jnz     short loc_180015D10
0x180015c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ca6  lea     r13, WPP_GLOBAL_Control
0x180015cad  mov     edi, 1
0x180015cb2  cmp     rcx, r13
0x180015cb5  jz      short loc_180015CC8
0x180015cb7  test    dword ptr [rcx+2Ch], 100h
0x180015cbe  jz      short loc_180015CC8
0x180015cc0  cmp     [rcx+29h], dl
0x180015cc3  mov     dl, dil
0x180015cc6  jnb     short loc_180015CCB
0x180015cc8  mov     dl, r10b
0x180015ccb  lea     r15, WPP_RECORDER_INITIALIZED
0x180015cd2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015cd9  setnz   r8b
0x180015cdd  test    dl, dl
0x180015cdf  jnz     short loc_180015CEA
0x180015ce1  test    r8b, r8b
0x180015ce4  jz      loc_180015DF6
0x180015cea  mov     eax, [rsi+18h]
0x180015ced  mov     [rsp+0A8h+var_48], eax
0x180015cf1  mov     rax, [rbx+20h]
0x180015cf5  mov     [rsp+0A8h+var_50], r9b
0x180015cfa  mov     [rsp+0A8h+var_60], rbp
0x180015cff  mov     [rsp+0A8h+var_68], rax
0x180015d04  mov     [rsp+0A8h+var_78], 1Ch
0x180015d0b  jmp     loc_180015DE6
0x180015d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d17  lea     r13, WPP_GLOBAL_Control
0x180015d1e  mov     edi, 1
0x180015d23  cmp     rcx, r13
0x180015d26  jz      short loc_180015D39
0x180015d28  test    dword ptr [rcx+2Ch], 100h
0x180015d2f  jz      short loc_180015D39
0x180015d31  cmp     [rcx+29h], dl
0x180015d34  mov     dl, dil
0x180015d37  jnb     short loc_180015D3C
0x180015d39  mov     dl, r10b
0x180015d3c  lea     r15, WPP_RECORDER_INITIALIZED
0x180015d43  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015d4a  setnz   r8b
0x180015d4e  test    dl, dl
0x180015d50  jnz     short loc_180015D5B
0x180015d52  test    r8b, r8b
0x180015d55  jz      loc_180015DF6
0x180015d5b  mov     eax, [rsi+18h]
0x180015d5e  mov     [rsp+0A8h+var_48], eax
0x180015d62  mov     rax, [rbx+20h]
0x180015d66  mov     [rsp+0A8h+var_50], r9b
0x180015d6b  mov     [rsp+0A8h+var_60], rbp
0x180015d70  mov     [rsp+0A8h+var_68], rax
0x180015d75  mov     [rsp+0A8h+var_78], 1Dh
0x180015d7c  jmp     short loc_180015DE6
0x180015d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d85  lea     r13, WPP_GLOBAL_Control
0x180015d8c  mov     edi, 1
0x180015d91  cmp     rcx, r13
0x180015d94  jz      short loc_180015DA7
0x180015d96  test    dword ptr [rcx+2Ch], 100h
0x180015d9d  jz      short loc_180015DA7
0x180015d9f  cmp     [rcx+29h], dl
0x180015da2  mov     dl, dil
0x180015da5  jnb     short loc_180015DAA
0x180015da7  mov     dl, r10b
0x180015daa  lea     r15, WPP_RECORDER_INITIALIZED
0x180015db1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015db8  setnz   r8b
0x180015dbc  test    dl, dl
0x180015dbe  jnz     short loc_180015DC5
0x180015dc0  test    r8b, r8b
0x180015dc3  jz      short loc_180015DF6
0x180015dc5  mov     eax, [rsi+8]
0x180015dc8  mov     [rsp+0A8h+var_48], eax
0x180015dcc  mov     rax, [rbx+20h]
0x180015dd0  mov     [rsp+0A8h+var_50], r9b
0x180015dd5  mov     [rsp+0A8h+var_60], rbp
0x180015dda  mov     [rsp+0A8h+var_68], rax
0x180015ddf  mov     [rsp+0A8h+var_78], 1Eh
0x180015de6  mov     r9, [rbx+2C0h]
0x180015ded  mov     rcx, [rcx+18h]
0x180015df1  call    WPP_RECORDER_AND_TRACE_SF_qqccL
0x180015df6  cmp     dword ptr [rbx+6D8h], 0
0x180015dfd  jnz     short loc_180015E6E
0x180015dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e06  cmp     rcx, r13
0x180015e09  jz      short loc_180015E1F
0x180015e0b  test    dword ptr [rcx+2Ch], 100h
0x180015e12  jz      short loc_180015E1F
0x180015e14  cmp     byte ptr [rcx+29h], 3
0x180015e18  jb      short loc_180015E1F
0x180015e1a  mov     dl, dil
0x180015e1d  jmp     short loc_180015E21
0x180015e1f  xor     dl, dl
0x180015e21  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015e28  setnz   r8b
0x180015e2c  test    dl, dl
0x180015e2e  jnz     short loc_180015E35
0x180015e30  test    r8b, r8b
0x180015e33  jz      short loc_180015E6E
0x180015e35  mov     rax, [rbx+20h]
0x180015e39  mov     r9, [rbx+2C0h]
0x180015e40  mov     rcx, [rcx+18h]
0x180015e44  mov     [rsp+0A8h+var_68], rax
0x180015e49  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x180015e50  mov     [rsp+0A8h+var_70], rax
0x180015e55  mov     [rsp+0A8h+var_78], 20h ; ' '
0x180015e5c  mov     [rsp+0A8h+var_80], 9
0x180015e64  mov     byte ptr [rsp+0A8h+RemlockSize], 3
0x180015e69  call    WPP_RECORDER_AND_TRACE_SF_q
0x180015e6e  mov     eax, [rsp+0A8h+arg_18]
0x180015e75  test    al, al
0x180015e77  jz      loc_180015FDB
0x180015e7d  cmp     al, 2
0x180015e7f  jnz     loc_18001600F
0x180015e85  mov     r8d, [rsi+18h]; State
0x180015e89  mov     edx, [rsi+10h]; Type
0x180015e8c  mov     rcx, [rbx+20h]; DeviceObject
0x180015e90  call    cs:__imp_PoSetPowerState
0x180015e97  nop     dword ptr [rax+rax+00h]
0x180015e9c  mov     ecx, [rsi+10h]
0x180015e9f  test    ecx, ecx
0x180015ea1  jz      loc_180015F90
0x180015ea7  cmp     ecx, 1
0x180015eaa  jnz     loc_18001600F
0x180015eb0  mov     ecx, [rsi+18h]
0x180015eb3  sub     ecx, 1
0x180015eb6  jz      short loc_180015EE2
0x180015eb8  sub     ecx, 1
0x180015ebb  jz      short loc_180015ECB
0x180015ebd  sub     ecx, 1
0x180015ec0  jz      short loc_180015ECB
0x180015ec2  cmp     ecx, 1
0x180015ec5  jnz     loc_18001600F
0x180015ecb  lea     rcx, [rbx+20h]
0x180015ecf  call    CancelAllPingPongIrps
0x180015ed4  mov     eax, [rsi+18h]
0x180015ed7  mov     [rbx+18Ch], eax
0x180015edd  jmp     loc_18001600F
0x180015ee2  lea     rcx, [rbx+2A0h]; RemoveLock
0x180015ee9  mov     [rsp+0A8h+RemlockSize], 20h ; ' '; RemlockSize
0x180015ef1  mov     r9d, edi; Line
0x180015ef4  lea     r8, File; File
0x180015efb  mov     rdx, rbp; Tag
0x180015efe  call    cs:__imp_IoAcquireRemoveLockEx
0x180015f05  nop     dword ptr [rax+rax+00h]
0x180015f0a  mov     r14d, eax
0x180015f0d  test    eax, eax
0x180015f0f  jns     loc_18001600F
0x180015f15  mov     r10, cs:WPP_GLOBAL_Control
0x180015f1c  cmp     r10, r13
0x180015f1f  jz      short loc_180015F37
0x180015f21  test    dword ptr [r10+2Ch], 100h
0x180015f29  jz      short loc_180015F37
0x180015f2b  cmp     byte ptr [r10+29h], 2
0x180015f30  jb      short loc_180015F37
0x180015f32  mov     dl, dil
0x180015f35  jmp     short loc_180015F39
0x180015f37  xor     dl, dl
0x180015f39  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180015f40  setnz   r8b
0x180015f44  test    dl, dl
0x180015f46  jnz     short loc_180015F51
0x180015f48  test    r8b, r8b
0x180015f4b  jz      loc_180016007
0x180015f51  mov     r9, [rbx+2C0h]
0x180015f58  mov     rcx, [r10+18h]
0x180015f5c  mov     dword ptr [rsp+0A8h+var_60], eax
0x180015f60  mov     rax, [rbx+20h]
0x180015f64  mov     [rsp+0A8h+var_68], rax
0x180015f69  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x180015f70  mov     [rsp+0A8h+var_70], rax
0x180015f75  mov     [rsp+0A8h+var_78], 21h ; '!'
0x180015f7c  mov     [rsp+0A8h+var_80], 9
0x180015f84  mov     byte ptr [rsp+0A8h+RemlockSize], 2
0x180015f89  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180015f8e  jmp     short loc_180016007
0x180015f90  mov     esi, [rsi+18h]
0x180015f93  mov     [rbx+188h], esi
0x180015f99  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x180015f9e  test    eax, eax
0x180015fa0  jz      short loc_180015FC0
0x180015fa2  lea     rcx, [rbx+8E8h]
0x180015fa9  cmp     esi, edi
0x180015fab  jg      short loc_180015FB4
0x180015fad  lea     rcx, [rbx+8F0h]
0x180015fb4  call    cs:__imp_KeQuerySystemTimePrecise
0x180015fbb  nop     dword ptr [rax+rax+00h]
0x180015fc0  cmp     esi, [rbx+174h]
0x180015fc6  jle     short loc_180015FD6
0x180015fc8  mov     edx, 0C00002D3h
0x180015fcd  lea     rcx, [rbx+20h]
0x180015fd1  call    CompleteAllCollectionWaitWakeIrps
0x180015fd6  mov     sil, dil
0x180015fd9  jmp     short loc_180016017
0x180015fdb  mov     eax, 2
0x180015fe0  mov     [rbx+190h], rbp
0x180015fe7  lea     ecx, [rax+2]
0x180015fea  lock cmpxchg [rbx+198h], ecx
0x180015ff2  cmp     eax, 3
0x180015ff5  jnz     short loc_18001600F
0x180015ff7  mov     dword ptr [rbx+198h], 7
0x180016001  mov     r14d, 0C0000120h
0x180016007  mov     [rsp+0A8h+arg_10], dil
0x18001600f  mov     sil, [rsp+0A8h+arg_8]
0x180016017  mov     rcx, rbp; Irp
0x18001601a  call    cs:__imp_PoStartNextPowerIrp
0x180016021  nop     dword ptr [rax+rax+00h]
0x180016026  cmp     [rsp+0A8h+arg_10], 0
0x18001602e  jz      short loc_18001604A
0x180016030  xor     edx, edx; PriorityBoost
0x180016032  mov     [rbp+30h], r14d
0x180016036  mov     rcx, rbp; Irp
0x180016039  call    cs:__imp_IofCompleteRequest
0x180016040  nop     dword ptr [rax+rax+00h]
0x180016045  jmp     loc_1800160CB
0x18001604a  mov     rax, [rbp+0B8h]
0x180016051  lea     rcx, HidpFdoPowerCompletion
0x180016058  mov     rdx, rbp
0x18001605b  movups  xmm0, xmmword ptr [rax]
0x18001605e  movups  xmmword ptr [rax-48h], xmm0
0x180016062  movups  xmm1, xmmword ptr [rax+10h]
0x180016066  movups  xmmword ptr [rax-38h], xmm1
0x18001606a  movups  xmm0, xmmword ptr [rax+20h]
0x18001606e  movups  xmmword ptr [rax-28h], xmm0
0x180016072  movsd   xmm1, qword ptr [rax+30h]
0x180016077  movsd   qword ptr [rax-18h], xmm1
0x18001607c  mov     byte ptr [rax-45h], 0
0x180016080  mov     rax, [rbp+0B8h]
0x180016087  mov     [rax-10h], rcx
0x18001608b  mov     rcx, [rsp+0A8h+arg_0]
0x180016093  mov     [rax-8], rcx
0x180016097  mov     byte ptr [rax-45h], 0E0h
0x18001609b  test    sil, sil
0x18001609e  jz      short loc_1800160BF
0x1800160a0  mov     rax, [rbp+0B8h]
0x1800160a7  or      [rax+3], dil
0x1800160ab  mov     rcx, [rbx+20h]
0x1800160af  call    HidpCallDriver
0x1800160b4  mov     r14d, 103h
0x1800160ba  jmp     loc_18001616D
0x1800160bf  mov     rcx, [rbx+20h]
  ... truncated ...
```
