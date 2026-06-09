# DiskInfoExceptionComplete

- ea: `0x140004ca0`
- end: `0x140005111`
- name: `DiskInfoExceptionComplete`
- size: `1137`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, PVOID P)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001da0`
- `0x140002940`
- `0x1400034a0`
- `0x1400034f0`
- `0x14000431c`
- `0x140004ca0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400050eb`
- `ntoskrnl!IoFreeIrp` at `0x1400050eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005060`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005076`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000508c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000509d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005060`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005076`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000508c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000509d`
- `ntoskrnl!IofCallDriver` at `0x140004f1e`
- `ntoskrnl!IofCallDriver` at `0x140004f1e`
- `ntoskrnl!IoFreeMdl` at `0x1400050dc`
- `ntoskrnl!IoFreeMdl` at `0x1400050dc`
- `CLASSPNP!ClassReleaseQueue` at `0x140004dce`
- `CLASSPNP!ClassReleaseQueue` at `0x140004dce`
- `CLASSPNP!ClassInterpretSenseInfo` at `0x140004e07`
- `CLASSPNP!ClassInterpretSenseInfo` at `0x140004e07`
- `CLASSPNP!ClassModeSenseTranslate` at `0x140004f39`
- `CLASSPNP!ClassModeSenseTranslate` at `0x140004f39`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x1400050cc`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x1400050cc`
- `CLASSPNP!ClassFindModePage` at `0x140004f60`
- `CLASSPNP!ClassFindModePage` at `0x140004f60`

## pseudocode

```c
__int64 __fastcall DiskInfoExceptionComplete(
        PDEVICE_OBJECT DeviceObject,
        struct _SINGLE_LIST_ENTRY *Irp,
        unsigned __int8 *P)
{
  struct _IO_STACK_LOCATION *Next; // r12
  int v6; // r14d
  unsigned int v7; // r14d
  bool v8; // zf
  PVOID v10; // r13
  unsigned __int8 *v11; // rsi
  struct _MODE_PARAMETER_HEADER *v12; // rcx
  ULONG v13; // eax
  ULONG v14; // eax
  BOOLEAN v15; // al
  int v16; // edx
  int v17; // r9d
  char v18; // al
  ULONG v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // eax
  struct _IO_STACK_LOCATION *v22; // rax
  _QWORD *v23; // rcx
  int v24; // eax
  PCHAR v25; // r12
  _BYTE *ModePage; // rsi
  __int64 v27; // rcx
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  int v31; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-25h]
  ULONG RetryInterval; // [rsp+48h] [rbp-21h] BYREF
  PCHAR ModeSenseBuffer; // [rsp+50h] [rbp-19h]
  void *v35; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *DeviceExtension; // [rsp+60h] [rbp-9h]
  __int64 v37; // [rsp+68h] [rbp-1h]
  PVOID Pa; // [rsp+70h] [rbp+7h]
  char v39; // [rsp+D0h] [rbp+67h] BYREF
  char v40; // [rsp+D8h] [rbp+6Fh] BYREF
  NTSTATUS Status; // [rsp+E0h] [rbp+77h] BYREF
  ULONG ModeSenseBufferSize; // [rsp+E8h] [rbp+7Fh] BYREF

  Next = (struct _IO_STACK_LOCATION *)Irp[23].Next;
  v6 = P[3];
  DeviceExtension = DeviceObject->DeviceExtension;
  v7 = v6 & 0xFFFFFF3F;
  v8 = P[2] == 40;
  v10 = 0;
  v37 = DeviceExtension[12];
  Status = 0;
  RetryInterval = 0;
  Pa = Next->Parameters.SetFile.FileObject;
  LOBYTE(v32) = 1;
  v35 = 0;
  v40 = 0;
  v31 = 0;
  v39 = 0;
  if ( v8 )
  {
    v11 = P;
    v12 = (struct _MODE_PARAMETER_HEADER *)*((_QWORD *)P + 8);
    v13 = *((_DWORD *)P + 15);
    ModeSenseBuffer = (PCHAR)v12;
    ModeSenseBufferSize = v13;
    if ( !*((_DWORD *)P + 5) && *((_DWORD *)P + 14) )
    {
      GetSrbScsiData((_DWORD)P, (unsigned int)&v40, (unsigned int)&v31, 0, (__int64)&v35, (__int64)&v39);
      v12 = (struct _MODE_PARAMETER_HEADER *)ModeSenseBuffer;
      v10 = v35;
    }
  }
  else
  {
    v12 = (struct _MODE_PARAMETER_HEADER *)*((_QWORD *)P + 3);
    v11 = 0;
    v14 = *((_DWORD *)P + 4);
    v10 = (PVOID)*((_QWORD *)P + 4);
    ModeSenseBuffer = (PCHAR)v12;
    ModeSenseBufferSize = v14;
  }
  if ( v7 == 1 || v7 == 18 )
  {
    v24 = ClassModeSenseTranslate(DeviceObject, v12, &ModeSenseBufferSize);
    v25 = ModeSenseBuffer;
    Status = v24;
    if ( v24 < 0 )
      goto LABEL_53;
    ModePage = ClassFindModePage(ModeSenseBuffer, ModeSenseBufferSize, 0x1Cu, 1u);
    if ( ModePage )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_a9711c54c416383df697b4e008bb3725_Traceguids, DeviceObject);
      }
      v27 = v37;
      *(_BYTE *)(v37 + 21) = 1;
      if ( (ModePage[2] & 8) == 0 && (unsigned __int8)((ModePage[3] & 0xF) - 2) <= 4u )
      {
        *(_DWORD *)(v27 + 16) = 3;
        *(_BYTE *)(v27 + 22) = 1;
        v32 = (unsigned int)DiskPostReregisterRequest(DeviceObject, Irp) >> 31;
LABEL_51:
        Status = 0;
        goto LABEL_53;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_51;
      }
      v29 = 22;
    }
    else
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_51;
      }
      v29 = 23;
    }
    WPP_SF_q(v28->AttachedDevice, v29, WPP_a9711c54c416383df697b4e008bb3725_Traceguids, DeviceObject);
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_a9711c54c416383df697b4e008bb3725_Traceguids, Irp, P);
  }
  if ( (P[3] & 0x40) != 0 )
    ClassReleaseQueue(DeviceObject);
  v15 = ClassInterpretSenseInfo(
          DeviceObject,
          (PSCSI_REQUEST_BLOCK)P,
          Next->MajorFunction,
          0,
          4 - Next->Parameters.Create.EaLength,
          &Status,
          &RetryInterval);
  if ( (Next->Flags & 2) != 0 && Status == -2147483626 )
  {
    Status = -1073741435;
  }
  else if ( !v15 )
  {
LABEL_20:
    v18 = 0;
    goto LABEL_21;
  }
  if ( !Next->Parameters.CreatePipe.Parameters )
    goto LABEL_20;
  v18 = 1;
LABEL_21:
  --Next->Parameters.CreatePipe.Parameters;
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a9711c54c416383df697b4e008bb3725_Traceguids, Irp);
    }
    v19 = (ULONG)Irp[1].Next[5].Next;
    if ( P[2] == 40 )
    {
      v8 = *((_DWORD *)v11 + 5) == 0;
      *((_DWORD *)v11 + 15) = v19;
      v11[3] = 0;
      if ( v8 && *((_DWORD *)v11 + 14) )
      {
        LOBYTE(v16) = v40;
        SetSrbScsiData((_DWORD)v11, v16, v31, v17, (__int64)v10, v39);
      }
      v20 = *((_DWORD *)v11 + 6) & 0xFFFFFFFD;
      *((_WORD *)v11 + 19) = 32;
      *((_DWORD *)v11 + 8) = 255;
      *((_DWORD *)v11 + 6) = v20 | 0xC;
    }
    else
    {
      v21 = *((_DWORD *)P + 3) & 0xFFFFFFFD;
      *((_DWORD *)P + 4) = v19;
      *(_WORD *)(P + 3) = 0;
      *((_DWORD *)P + 3) = v21 | 0xC;
      *((_WORD *)P + 4) = 8447;
    }
    Next[-1].MajorFunction = 15;
    Next[-1].Parameters.WMI.ProviderId = (ULONG_PTR)P;
    v22 = (struct _IO_STACK_LOCATION *)Irp[23].Next;
    v22[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)DiskInfoExceptionComplete;
    v23 = DeviceExtension;
    v22[-1].Context = P;
    v22[-1].Control = -32;
    IofCallDriver((PDEVICE_OBJECT)v23[2], (PIRP)Irp);
    return 3221225494LL;
  }
  v25 = ModeSenseBuffer;
LABEL_53:
  if ( v10 != Pa && Pa )
    ExFreePoolWithTag(Pa, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v25 )
    ExFreePoolWithTag(v25, 0);
  ExFreePoolWithTag(P, 0);
  if ( (_BYTE)v32 )
  {
    v8 = BYTE1(Irp[8].Next) == 0;
    LODWORD(Irp[6].Next) = Status;
    if ( !v8 )
      BYTE3(Irp[23].Next->Next) |= 1u;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    IoFreeMdl((PMDL)Irp[1].Next);
    IoFreeIrp((PIRP)Irp);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140004ca0  push    rbp
0x140004ca2  push    rbx
0x140004ca3  push    rsi
0x140004ca4  push    rdi
0x140004ca5  push    r12
0x140004ca7  push    r13
0x140004ca9  push    r14
0x140004cab  push    r15
0x140004cad  lea     rbp, [rsp-1Fh]
0x140004cb2  sub     rsp, 88h
0x140004cb9  mov     rax, [rcx+40h]
0x140004cbd  mov     rdi, rdx
0x140004cc0  mov     r12, [rdx+0B8h]
0x140004cc7  mov     rbx, r8
0x140004cca  movzx   r14d, byte ptr [r8+3]
0x140004ccf  xor     edx, edx
0x140004cd1  mov     [rbp+57h+var_60], rax
0x140004cd5  and     r14d, 0FFFFFF3Fh
0x140004cdc  cmp     byte ptr [r8+2], 28h ; '('
0x140004ce1  mov     r15, rcx
0x140004ce4  mov     rax, [rax+60h]
0x140004ce8  mov     r13d, edx
0x140004ceb  mov     [rbp+57h+var_58], rax
0x140004cef  mov     [rbp+57h+arg_10], edx
0x140004cf2  mov     [rbp+57h+var_78], edx
0x140004cf5  mov     rax, [r12+18h]
0x140004cfa  mov     [rbp+57h+P], rax
0x140004cfe  mov     byte ptr [rbp+57h+var_7C], 1
0x140004d02  mov     [rbp+57h+var_68], rdx
0x140004d06  mov     [rbp+57h+arg_8], dl
0x140004d09  mov     [rbp+57h+var_80], edx
0x140004d0c  mov     [rbp+57h+arg_0], dl
0x140004d0f  jnz     short loc_140004D5E
0x140004d11  mov     rsi, rbx
0x140004d14  mov     rcx, [r8+40h]
0x140004d18  mov     eax, [r8+3Ch]
0x140004d1c  mov     [rbp+57h+ModeSenseBuffer], rcx
0x140004d20  mov     [rbp+57h+ModeSenseBufferSize], eax
0x140004d23  cmp     [r8+14h], edx
0x140004d27  jnz     short loc_140004D74
0x140004d29  cmp     [r8+38h], edx
0x140004d2d  jbe     short loc_140004D74
0x140004d2f  lea     rax, [rbp+57h+arg_0]
0x140004d33  xor     r9d, r9d
0x140004d36  mov     [rsp+0C0h+Status], rax
0x140004d3b  lea     r8, [rbp+57h+var_80]
0x140004d3f  lea     rax, [rbp+57h+var_68]
0x140004d43  mov     rcx, rbx
0x140004d46  lea     rdx, [rbp+57h+arg_8]
0x140004d4a  mov     qword ptr [rsp+0C0h+RetryCount], rax
0x140004d4f  call    GetSrbScsiData
0x140004d54  mov     rcx, [rbp+57h+ModeSenseBuffer]
0x140004d58  mov     r13, [rbp+57h+var_68]
0x140004d5c  jmp     short loc_140004D74
0x140004d5e  mov     rcx, [r8+18h]
0x140004d62  mov     rsi, rdx
0x140004d65  mov     eax, [r8+10h]
0x140004d69  mov     r13, [r8+20h]
0x140004d6d  mov     [rbp+57h+ModeSenseBuffer], rcx
0x140004d71  mov     [rbp+57h+ModeSenseBufferSize], eax
0x140004d74  cmp     r14d, 1
0x140004d78  jz      loc_140004F2F
0x140004d7e  cmp     r14d, 12h
0x140004d82  jz      loc_140004F2F
0x140004d88  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d8f  lea     r14, WPP_GLOBAL_Control
0x140004d96  cmp     rcx, r14
0x140004d99  jz      short loc_140004DC5
0x140004d9b  mov     eax, [rcx+2Ch]
0x140004d9e  test    al, 1
0x140004da0  jz      short loc_140004DC5
0x140004da2  cmp     byte ptr [rcx+29h], 4
0x140004da6  jb      short loc_140004DC5
0x140004da8  mov     rcx, [rcx+18h]
0x140004dac  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140004db3  mov     edx, 13h
0x140004db8  mov     qword ptr [rsp+0C0h+RetryCount], rbx
0x140004dbd  mov     r9, rdi
0x140004dc0  call    WPP_SF_qq
0x140004dc5  test    byte ptr [rbx+3], 40h
0x140004dc9  jz      short loc_140004DDA
0x140004dcb  mov     rcx, r15; DeviceObject
0x140004dce  call    cs:__imp_ClassReleaseQueue
0x140004dd5  nop     dword ptr [rax+rax+00h]
0x140004dda  mov     r8b, [r12]; MajorFunctionCode
0x140004dde  lea     rcx, [rbp+57h+var_78]
0x140004de2  mov     [rsp+0C0h+RetryInterval], rcx; RetryInterval
0x140004de7  mov     eax, 4
0x140004dec  sub     eax, [r12+20h]
0x140004df1  lea     rcx, [rbp+57h+arg_10]
0x140004df5  mov     [rsp+0C0h+Status], rcx; Status
0x140004dfa  xor     r9d, r9d; IoDeviceCode
0x140004dfd  mov     rcx, r15; DeviceObject
0x140004e00  mov     [rsp+0C0h+RetryCount], eax; RetryCount
0x140004e04  mov     rdx, rbx; Srb
0x140004e07  call    cs:__imp_ClassInterpretSenseInfo
0x140004e0e  nop     dword ptr [rax+rax+00h]
0x140004e13  test    byte ptr [r12+2], 2
0x140004e19  jz      short loc_140004E2D
0x140004e1b  cmp     [rbp+57h+arg_10], 80000016h
0x140004e22  jnz     short loc_140004E2D
0x140004e24  mov     [rbp+57h+arg_10], 0C0000185h
0x140004e2b  jmp     short loc_140004E31
0x140004e2d  test    al, al
0x140004e2f  jz      short loc_140004E3D
0x140004e31  cmp     qword ptr [r12+20h], 0
0x140004e37  jz      short loc_140004E3D
0x140004e39  mov     al, 1
0x140004e3b  jmp     short loc_140004E3F
0x140004e3d  xor     al, al
0x140004e3f  dec     qword ptr [r12+20h]
0x140004e44  test    al, al
0x140004e46  jz      loc_140005049
0x140004e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e53  cmp     rcx, r14
0x140004e56  jz      short loc_140004E7D
0x140004e58  mov     eax, [rcx+2Ch]
0x140004e5b  test    al, 1
0x140004e5d  jz      short loc_140004E7D
0x140004e5f  cmp     byte ptr [rcx+29h], 4
0x140004e63  jb      short loc_140004E7D
0x140004e65  mov     rcx, [rcx+18h]
0x140004e69  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140004e70  mov     edx, 14h
0x140004e75  mov     r9, rdi
0x140004e78  call    WPP_SF_q
0x140004e7d  cmp     byte ptr [rbx+2], 28h ; '('
0x140004e81  mov     rax, [rdi+8]
0x140004e85  mov     ecx, [rax+28h]
0x140004e88  jnz     short loc_140004ED3
0x140004e8a  cmp     dword ptr [rsi+14h], 0
0x140004e8e  mov     [rsi+3Ch], ecx
0x140004e91  mov     byte ptr [rsi+3], 0
0x140004e95  jnz     short loc_140004EB8
0x140004e97  cmp     dword ptr [rsi+38h], 0
0x140004e9b  jbe     short loc_140004EB8
0x140004e9d  mov     al, [rbp+57h+arg_0]
0x140004ea0  mov     rcx, rsi
0x140004ea3  mov     r8d, [rbp+57h+var_80]
0x140004ea7  mov     dl, [rbp+57h+arg_8]
0x140004eaa  mov     byte ptr [rsp+0C0h+Status], al
0x140004eae  mov     qword ptr [rsp+0C0h+RetryCount], r13
0x140004eb3  call    SetSrbScsiData
0x140004eb8  mov     eax, [rsi+18h]
0x140004ebb  and     eax, 0FFFFFFFDh
0x140004ebe  mov     word ptr [rsi+26h], 20h ; ' '
0x140004ec4  or      eax, 0Ch
0x140004ec7  mov     dword ptr [rsi+20h], 0FFh
0x140004ece  mov     [rsi+18h], eax
0x140004ed1  jmp     short loc_140004EEE
0x140004ed3  mov     eax, [rbx+0Ch]
0x140004ed6  and     eax, 0FFFFFFFDh
0x140004ed9  mov     [rbx+10h], ecx
0x140004edc  or      eax, 0Ch
0x140004edf  mov     word ptr [rbx+3], 0
0x140004ee5  mov     [rbx+0Ch], eax
0x140004ee8  mov     word ptr [rbx+8], 20FFh
0x140004eee  mov     byte ptr [r12-48h], 0Fh
0x140004ef4  lea     rcx, DiskInfoExceptionComplete
0x140004efb  mov     [r12-40h], rbx
0x140004f00  mov     rdx, rdi; Irp
0x140004f03  mov     rax, [rdi+0B8h]
0x140004f0a  mov     [rax-10h], rcx
0x140004f0e  mov     rcx, [rbp+57h+var_60]
0x140004f12  mov     [rax-8], rbx
0x140004f16  mov     byte ptr [rax-45h], 0E0h
0x140004f1a  mov     rcx, [rcx+10h]; DeviceObject
0x140004f1e  call    cs:__imp_IofCallDriver
0x140004f25  nop     dword ptr [rax+rax+00h]
0x140004f2a  jmp     loc_1400050F7
0x140004f2f  mov     rdx, rcx; ModeSenseData
0x140004f32  lea     r8, [rbp+57h+ModeSenseBufferSize]; ModeSenseBufferSize
0x140004f36  mov     rcx, r15; DeviceObject
0x140004f39  call    cs:__imp_ClassModeSenseTranslate
0x140004f40  nop     dword ptr [rax+rax+00h]
0x140004f45  mov     r12, [rbp+57h+ModeSenseBuffer]
0x140004f49  mov     [rbp+57h+arg_10], eax
0x140004f4c  test    eax, eax
0x140004f4e  js      loc_14000504D
0x140004f54  mov     edx, [rbp+57h+ModeSenseBufferSize]; Length
0x140004f57  mov     r9b, 1; Use6Byte
0x140004f5a  mov     r8b, 1Ch; PageMode
0x140004f5d  mov     rcx, r12; ModeSenseBuffer
0x140004f60  call    cs:__imp_ClassFindModePage
0x140004f67  nop     dword ptr [rax+rax+00h]
0x140004f6c  mov     rsi, rax
0x140004f6f  test    rax, rax
0x140004f72  jz      loc_140005008
0x140004f78  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f7f  lea     r14, WPP_GLOBAL_Control
0x140004f86  cmp     rcx, r14
0x140004f89  jz      short loc_140004FB1
0x140004f8b  mov     edx, [rcx+2Ch]
0x140004f8e  test    dl, 40h
0x140004f91  jz      short loc_140004FB1
0x140004f93  cmp     byte ptr [rcx+29h], 4
0x140004f97  jb      short loc_140004FB1
0x140004f99  mov     rcx, [rcx+18h]
0x140004f9d  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140004fa4  mov     edx, 15h
0x140004fa9  mov     r9, r15
0x140004fac  call    WPP_SF_q
0x140004fb1  mov     rcx, [rbp+57h+var_58]
0x140004fb5  mov     byte ptr [rcx+15h], 1
0x140004fb9  test    byte ptr [rsi+2], 8
0x140004fbd  jnz     short loc_140004FE8
0x140004fbf  mov     al, [rsi+3]
0x140004fc2  and     al, 0Fh
0x140004fc4  sub     al, 2
0x140004fc6  cmp     al, 4
0x140004fc8  ja      short loc_140004FE8
0x140004fca  mov     dword ptr [rcx+10h], 3
0x140004fd1  mov     rdx, rdi
0x140004fd4  mov     byte ptr [rcx+16h], 1
0x140004fd8  mov     rcx, r15
0x140004fdb  call    DiskPostReregisterRequest
0x140004fe0  shr     eax, 1Fh
0x140004fe3  mov     [rbp+57h+var_7C], eax
0x140004fe6  jmp     short loc_140005040
0x140004fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x140004fef  cmp     rcx, r14
0x140004ff2  jz      short loc_140005040
0x140004ff4  mov     eax, [rcx+2Ch]
0x140004ff7  test    al, 40h
0x140004ff9  jz      short loc_140005040
0x140004ffb  cmp     byte ptr [rcx+29h], 3
0x140004fff  jb      short loc_140005040
0x140005001  mov     edx, 16h
0x140005006  jmp     short loc_14000502D
0x140005008  mov     rcx, cs:WPP_GLOBAL_Control
0x14000500f  lea     r14, WPP_GLOBAL_Control
0x140005016  cmp     rcx, r14
0x140005019  jz      short loc_140005040
0x14000501b  mov     eax, [rcx+2Ch]
0x14000501e  test    al, 40h
0x140005020  jz      short loc_140005040
0x140005022  cmp     byte ptr [rcx+29h], 3
0x140005026  jb      short loc_140005040
0x140005028  mov     edx, 17h
0x14000502d  mov     rcx, [rcx+18h]
0x140005031  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140005038  mov     r9, r15
0x14000503b  call    WPP_SF_q
0x140005040  mov     [rbp+57h+arg_10], 0
0x140005047  jmp     short loc_14000504D
0x140005049  mov     r12, [rbp+57h+ModeSenseBuffer]
0x14000504d  mov     rax, [rbp+57h+P]
0x140005051  cmp     r13, rax
0x140005054  jz      short loc_14000506C
0x140005056  test    rax, rax
0x140005059  jz      short loc_14000506C
0x14000505b  xor     edx, edx; Tag
0x14000505d  mov     rcx, rax; P
0x140005060  call    cs:__imp_ExFreePoolWithTag
0x140005067  nop     dword ptr [rax+rax+00h]
0x14000506c  test    r13, r13
0x14000506f  jz      short loc_140005082
0x140005071  xor     edx, edx; Tag
0x140005073  mov     rcx, r13; P
0x140005076  call    cs:__imp_ExFreePoolWithTag
0x14000507d  nop     dword ptr [rax+rax+00h]
0x140005082  test    r12, r12
0x140005085  jz      short loc_140005098
0x140005087  xor     edx, edx; Tag
0x140005089  mov     rcx, r12; P
0x14000508c  call    cs:__imp_ExFreePoolWithTag
0x140005093  nop     dword ptr [rax+rax+00h]
0x140005098  xor     edx, edx; Tag
0x14000509a  mov     rcx, rbx; P
0x14000509d  call    cs:__imp_ExFreePoolWithTag
0x1400050a4  nop     dword ptr [rax+rax+00h]
0x1400050a9  cmp     byte ptr [rbp+57h+var_7C], 0
0x1400050ad  jz      short loc_1400050F7
0x1400050af  cmp     byte ptr [rdi+41h], 0
0x1400050b3  mov     eax, [rbp+57h+arg_10]
0x1400050b6  mov     [rdi+30h], eax
0x1400050b9  jz      short loc_1400050C6
0x1400050bb  mov     rax, [rdi+0B8h]
0x1400050c2  or      byte ptr [rax+3], 1
0x1400050c6  mov     rdx, rdi; Tag
0x1400050c9  mov     rcx, r15; DeviceObject
0x1400050cc  call    cs:__imp_ClassReleaseRemoveLock
0x1400050d3  nop     dword ptr [rax+rax+00h]
0x1400050d8  mov     rcx, [rdi+8]; Mdl
0x1400050dc  call    cs:__imp_IoFreeMdl
0x1400050e3  nop     dword ptr [rax+rax+00h]
0x1400050e8  mov     rcx, rdi; Irp
0x1400050eb  call    cs:__imp_IoFreeIrp
0x1400050f2  nop     dword ptr [rax+rax+00h]
0x1400050f7  mov     eax, 0C0000016h
0x1400050fc  add     rsp, 88h
0x140005103  pop     r15
0x140005105  pop     r14
0x140005107  pop     r13
0x140005109  pop     r12
0x14000510b  pop     rdi
0x14000510c  pop     rsi
0x14000510d  pop     rbx
0x14000510e  pop     rbp
0x14000510f  retn
  ... truncated ...
```
