# I8xPower

- ea: `0x14001f4e0`
- end: `0x14001fa1f`
- name: `I8xPower`
- size: `1343`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400014e0`
- `0x1400043e0`
- `0x140004530`
- `0x140008e80`
- `0x140008ef0`
- `0x14001f4e0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001f65e`
- `ntoskrnl!IofCompleteRequest` at `0x14001f914`
- `ntoskrnl!IofCompleteRequest` at `0x14001f65e`
- `ntoskrnl!IofCompleteRequest` at `0x14001f914`
- `ntoskrnl!PoSetPowerState` at `0x14001f94f`
- `ntoskrnl!PoSetPowerState` at `0x14001f94f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f646`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f79f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f8fc`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f9d1`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f9e2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f646`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f79f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f8fc`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f9d1`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001f9e2`
- `ntoskrnl!IoDisconnectInterrupt` at `0x14001f9ae`
- `ntoskrnl!IoDisconnectInterrupt` at `0x14001f9ae`
- `ntoskrnl!PoCallDriver` at `0x14001f876`
- `ntoskrnl!PoCallDriver` at `0x14001fa05`
- `ntoskrnl!PoCallDriver` at `0x14001f876`
- `ntoskrnl!PoCallDriver` at `0x14001fa05`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001f7f8`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001f7f8`

## pseudocode

```c
NTSTATUS __fastcall I8xPower(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rsi
  PIRP v3; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  const char *v6; // rcx
  int MinorFunction; // ecx
  int v8; // edx
  int v9; // r9d
  int v10; // r8d
  int v11; // edx
  DWORD LowPart; // eax
  int v14; // eax
  DWORD v15; // ecx
  unsigned int v16; // edi
  __int64 v17; // rdx
  struct _IO_STACK_LOCATION *v18; // rax
  struct _IO_STACK_LOCATION *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // edx
  struct _KINTERRUPT *v23; // r14

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v3 = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = "keyboard";
    if ( !DeviceExtension[565] )
      v6 = "mouse";
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)"mouse",
      23,
      37,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      (__int64)v6);
  }
  if ( !DeviceExtension[566] || !DeviceExtension[563] )
  {
    PoStartNextPowerIrp(v3);
    v3->IoStatus.Status = 0;
    goto LABEL_62;
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( MinorFunction != 2 )
  {
    v8 = CurrentStackLocation->MinorFunction;
    if ( CurrentStackLocation->MinorFunction )
    {
      LODWORD(Irp) = MinorFunction - 1;
      if ( MinorFunction == 1 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_40;
        v9 = 40;
        v10 = 22;
      }
      else
      {
        if ( MinorFunction != 3 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)Irp,
              22,
              50,
              (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
              MinorFunction);
            goto LABEL_38;
          }
LABEL_40:
          PoStartNextPowerIrp(v3);
LABEL_62:
          ++v3->CurrentLocation;
          ++v3->Tail.Overlay.CurrentStackLocation;
          return PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), v3);
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_40;
        v9 = 49;
        v10 = 22;
      }
      goto LABEL_37;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        22,
        38,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
    if ( DeviceExtension[565] || *((_WORD *)DeviceExtension + 269) )
      goto LABEL_38;
    PoStartNextPowerIrp(v3);
    v3->IoStatus.Status = -1073741436;
    IofCompleteRequest(v3, 0);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        25,
        39,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
    return -1073741436;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      22,
      41,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
  if ( CurrentStackLocation->Parameters.Create.Options != 1 )
  {
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    *((_DWORD *)DeviceExtension + 21) = LowPart;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_40;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      24,
      42,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      LowPart - 1);
LABEL_38:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        23,
        51,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
    goto LABEL_40;
  }
  v14 = *((_DWORD *)DeviceExtension + 20);
  v15 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( v15 == v14 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_40;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      24,
      43,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      v14 - 1);
    goto LABEL_38;
  }
  if ( v15 != 4 )
  {
    if ( v15 == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v15 - 1,
          24,
          44,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v16 = 1;
      IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), v3, File, 1u, 0x20u);
      LOBYTE(v17) = 1;
      if ( !DeviceExtension[565] )
        v16 = 16;
      I8xSetPowerFlag(v16, v17);
      v18 = v3->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v18[-1].MajorFunction = *(_OWORD *)&v18->MajorFunction;
      *(_OWORD *)&v18[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v18->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v18[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v18->Parameters.SetQuota + 6);
      v18[-1].FileObject = v18->FileObject;
      v18[-1].Control = 0;
      v19 = v3->Tail.Overlay.CurrentStackLocation;
      v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)I8xPowerUpToD0Complete;
      v19[-1].Context = 0;
      v19[-1].Control = -32;
      v3->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), v3);
      return 259;
    }
    LODWORD(Irp) = v15 - 2;
    if ( v15 - 2 >= 2 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v9 = 48;
      v10 = 24;
LABEL_37:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        v10,
        v9,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      goto LABEL_38;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      24,
      45,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      v15 - 1);
  if ( !(unsigned __int8)I8xCheckPowerFlag() )
  {
    v21 = 2;
    LOBYTE(v20) = 1;
    if ( !DeviceExtension[565] )
      v21 = 32;
    I8xSetPowerFlag(v21, v20);
    PoSetPowerState(
      DeviceObject,
      CurrentStackLocation->Parameters.Power.Type,
      CurrentStackLocation->Parameters.Power.State);
    if ( !DeviceExtension[565] && !*((_WORD *)DeviceExtension + 269) )
    {
      v23 = (struct _KINTERRUPT *)*((_QWORD *)DeviceExtension + 1);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v22,
          22,
          47,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      *((_QWORD *)DeviceExtension + 1) = 0;
      if ( v23 )
        IoDisconnectInterrupt(v23);
    }
    *((_DWORD *)DeviceExtension + 20) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    *((_DWORD *)DeviceExtension + 22) = CurrentStackLocation->Parameters.Create.EaLength;
    v3->IoStatus.Status = 0;
    PoStartNextPowerIrp(v3);
    goto LABEL_62;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      25,
      46,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
  PoStartNextPowerIrp(v3);
  v3->IoStatus.Status = -1073741101;
  IofCompleteRequest(v3, 0);
  return -1073741101;
}

```

## disassembly

```asm
0x14001f4e0  push    rbx
0x14001f4e2  push    rbp
0x14001f4e3  push    rsi
0x14001f4e4  push    rdi
0x14001f4e5  push    r12
0x14001f4e7  push    r15
0x14001f4e9  sub     rsp, 38h
0x14001f4ed  mov     rsi, [rcx+40h]
0x14001f4f1  mov     rbx, rdx
0x14001f4f4  mov     rdi, [rdx+0B8h]
0x14001f4fb  mov     rbp, rcx
0x14001f4fe  lea     r15, WPP_RECORDER_INITIALIZED
0x14001f505  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f50c  lea     r12, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14001f513  jz      short loc_14001F554
0x14001f515  cmp     byte ptr [rsi+235h], 0
0x14001f51c  lea     rdx, aMouse_0; "mouse"
0x14001f523  lea     rcx, aKeyboard; "keyboard"
0x14001f52a  mov     r9d, 25h ; '%'
0x14001f530  cmovz   rcx, rdx
0x14001f534  mov     r8d, 17h
0x14001f53a  mov     [rsp+68h+var_40], rcx
0x14001f53f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f546  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f54b  mov     rcx, [rcx+40h]
0x14001f54f  call    WPP_RECORDER_SF_s
0x14001f554  cmp     byte ptr [rsi+236h], 0
0x14001f55b  jz      loc_14001F9DF
0x14001f561  cmp     byte ptr [rsi+233h], 0
0x14001f568  jz      loc_14001F9DF
0x14001f56e  movzx   ecx, byte ptr [rdi+1]
0x14001f572  cmp     ecx, 2
0x14001f575  jz      loc_14001F69E
0x14001f57b  mov     edx, ecx
0x14001f57d  test    ecx, ecx
0x14001f57f  jz      short loc_14001F5FE
0x14001f581  sub     edx, 1
0x14001f584  jz      short loc_14001F5E0
0x14001f586  cmp     edx, 2
0x14001f589  jz      short loc_14001F5C2
0x14001f58b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f592  jz      loc_14001F79C
0x14001f598  mov     r9d, 32h ; '2'
0x14001f59e  mov     dword ptr [rsp+68h+var_40], ecx
0x14001f5a2  mov     r8d, 16h
0x14001f5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5af  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f5b4  mov     rcx, [rcx+40h]
0x14001f5b8  call    WPP_RECORDER_SF_d
0x14001f5bd  jmp     loc_14001F772
0x14001f5c2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f5c9  jz      loc_14001F79C
0x14001f5cf  mov     r9d, 31h ; '1'
0x14001f5d5  mov     r8d, 16h
0x14001f5db  jmp     loc_14001F75D
0x14001f5e0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f5e7  jz      loc_14001F79C
0x14001f5ed  mov     r9d, 28h ; '('
0x14001f5f3  mov     r8d, 16h
0x14001f5f9  jmp     loc_14001F75D
0x14001f5fe  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f605  jz      short loc_14001F628
0x14001f607  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f60e  mov     r9d, 26h ; '&'
0x14001f614  mov     r8d, 16h
0x14001f61a  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f61f  mov     rcx, [rcx+40h]
0x14001f623  call    WPP_RECORDER_SF_
0x14001f628  cmp     byte ptr [rsi+235h], 0
0x14001f62f  jnz     loc_14001F772
0x14001f635  cmp     word ptr [rsi+21Ah], 0
0x14001f63d  jnz     loc_14001F772
0x14001f643  mov     rcx, rbx; Irp
0x14001f646  call    cs:__imp_PoStartNextPowerIrp
0x14001f64d  nop     dword ptr [rax+rax+00h]
0x14001f652  xor     edx, edx; PriorityBoost
0x14001f654  mov     dword ptr [rbx+30h], 0C0000184h
0x14001f65b  mov     rcx, rbx; Irp
0x14001f65e  call    cs:__imp_IofCompleteRequest
0x14001f665  nop     dword ptr [rax+rax+00h]
0x14001f66a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f671  jz      short loc_14001F694
0x14001f673  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f67a  mov     r9d, 27h ; '''
0x14001f680  mov     r8d, 19h
0x14001f686  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f68b  mov     rcx, [rcx+40h]
0x14001f68f  call    WPP_RECORDER_SF_
0x14001f694  mov     eax, 0C0000184h
0x14001f699  jmp     loc_14001FA11
0x14001f69e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f6a5  jz      short loc_14001F6C8
0x14001f6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6ae  mov     r9d, 29h ; ')'
0x14001f6b4  mov     r8d, 16h
0x14001f6ba  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f6bf  mov     rcx, [rcx+40h]
0x14001f6c3  call    WPP_RECORDER_SF_
0x14001f6c8  cmp     dword ptr [rdi+10h], 1
0x14001f6cc  jz      short loc_14001F6F8
0x14001f6ce  mov     eax, [rdi+18h]
0x14001f6d1  mov     [rsi+54h], eax
0x14001f6d4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f6db  jz      loc_14001F79C
0x14001f6e1  dec     eax
0x14001f6e3  mov     r9d, 2Ah ; '*'
0x14001f6e9  mov     dword ptr [rsp+68h+var_40], eax
0x14001f6ed  mov     r8d, 18h
0x14001f6f3  jmp     loc_14001F5A8
0x14001f6f8  mov     eax, [rsi+50h]
0x14001f6fb  mov     ecx, [rdi+18h]
0x14001f6fe  cmp     ecx, eax
0x14001f700  jnz     short loc_14001F726
0x14001f702  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f709  jz      loc_14001F79C
0x14001f70f  dec     eax
0x14001f711  mov     r9d, 2Bh ; '+'
0x14001f717  mov     dword ptr [rsp+68h+var_40], eax
0x14001f71b  mov     r8d, 18h
0x14001f721  jmp     loc_14001F5A8
0x14001f726  cmp     ecx, 4
0x14001f729  jz      loc_14001F895
0x14001f72f  mov     edx, ecx
0x14001f731  sub     edx, 1
0x14001f734  jz      short loc_14001F7B0
0x14001f736  sub     edx, 1
0x14001f739  jz      loc_14001F895
0x14001f73f  cmp     edx, 1
0x14001f742  jz      loc_14001F895
0x14001f748  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f74f  jz      short loc_14001F79C
0x14001f751  mov     r9d, 30h ; '0'
0x14001f757  mov     r8d, 18h
0x14001f75d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f764  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f769  mov     rcx, [rcx+40h]
0x14001f76d  call    WPP_RECORDER_SF_
0x14001f772  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f779  jz      short loc_14001F79C
0x14001f77b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f782  mov     r9d, 33h ; '3'
0x14001f788  mov     r8d, 17h
0x14001f78e  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f793  mov     rcx, [rcx+40h]
0x14001f797  call    WPP_RECORDER_SF_
0x14001f79c  mov     rcx, rbx; Irp
0x14001f79f  call    cs:__imp_PoStartNextPowerIrp
0x14001f7a6  nop     dword ptr [rax+rax+00h]
0x14001f7ab  jmp     loc_14001F9F3
0x14001f7b0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f7b7  jz      short loc_14001F7DA
0x14001f7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f7c0  mov     r9d, 2Ch ; ','
0x14001f7c6  mov     r8d, 18h
0x14001f7cc  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f7d1  mov     rcx, [rcx+40h]
0x14001f7d5  call    WPP_RECORDER_SF_
0x14001f7da  mov     edi, 1
0x14001f7df  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14001f7e7  mov     r9d, edi; Line
0x14001f7ea  lea     rcx, [rsi+28h]; RemoveLock
0x14001f7ee  lea     r8, File; File
0x14001f7f5  mov     rdx, rbx; Tag
0x14001f7f8  call    cs:__imp_IoAcquireRemoveLockEx
0x14001f7ff  nop     dword ptr [rax+rax+00h]
0x14001f804  cmp     byte ptr [rsi+235h], 0
0x14001f80b  mov     eax, 10h
0x14001f810  mov     dl, 1
0x14001f812  cmovz   edi, eax
0x14001f815  mov     ecx, edi
0x14001f817  call    I8xSetPowerFlag
0x14001f81c  mov     rax, [rbx+0B8h]
0x14001f823  lea     rcx, I8xPowerUpToD0Complete
0x14001f82a  xor     ebp, ebp
0x14001f82c  mov     rdx, rbx; Irp
0x14001f82f  movups  xmm0, xmmword ptr [rax]
0x14001f832  movups  xmmword ptr [rax-48h], xmm0
0x14001f836  movups  xmm1, xmmword ptr [rax+10h]
0x14001f83a  movups  xmmword ptr [rax-38h], xmm1
0x14001f83e  movups  xmm0, xmmword ptr [rax+20h]
0x14001f842  movups  xmmword ptr [rax-28h], xmm0
0x14001f846  movsd   xmm1, qword ptr [rax+30h]
0x14001f84b  movsd   qword ptr [rax-18h], xmm1
0x14001f850  mov     byte ptr [rax-45h], 0
0x14001f854  mov     rax, [rbx+0B8h]
0x14001f85b  mov     [rax-10h], rcx
0x14001f85f  mov     [rax-8], rbp
0x14001f863  mov     byte ptr [rax-45h], 0E0h
0x14001f867  mov     rax, [rbx+0B8h]
0x14001f86e  or      byte ptr [rax+3], 1
0x14001f872  mov     rcx, [rsi+18h]; DeviceObject
0x14001f876  call    cs:__imp_PoCallDriver
0x14001f87d  nop     dword ptr [rax+rax+00h]
0x14001f882  mov     eax, 103h
0x14001f887  add     rsp, 38h
0x14001f88b  pop     r15
0x14001f88d  pop     r12
0x14001f88f  pop     rdi
0x14001f890  pop     rsi
0x14001f891  pop     rbp
0x14001f892  pop     rbx
0x14001f893  retn
0x14001f895  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f89c  jz      short loc_14001F8C6
0x14001f89e  lea     eax, [rcx-1]
0x14001f8a1  mov     r9d, 2Dh ; '-'
0x14001f8a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8ae  mov     r8d, 18h
0x14001f8b4  mov     dword ptr [rsp+68h+var_40], eax
0x14001f8b8  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f8bd  mov     rcx, [rcx+40h]
0x14001f8c1  call    WPP_RECORDER_SF_d
0x14001f8c6  call    I8xCheckPowerFlag
0x14001f8cb  test    al, al
0x14001f8cd  jz      short loc_14001F92A
0x14001f8cf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f8d6  jz      short loc_14001F8F9
0x14001f8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8df  mov     r9d, 2Eh ; '.'
0x14001f8e5  mov     r8d, 19h
0x14001f8eb  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f8f0  mov     rcx, [rcx+40h]
0x14001f8f4  call    WPP_RECORDER_SF_
0x14001f8f9  mov     rcx, rbx; Irp
0x14001f8fc  call    cs:__imp_PoStartNextPowerIrp
0x14001f903  nop     dword ptr [rax+rax+00h]
0x14001f908  xor     edx, edx; PriorityBoost
0x14001f90a  mov     dword ptr [rbx+30h], 0C00002D3h
0x14001f911  mov     rcx, rbx; Irp
0x14001f914  call    cs:__imp_IofCompleteRequest
0x14001f91b  nop     dword ptr [rax+rax+00h]
0x14001f920  mov     eax, 0C00002D3h
0x14001f925  jmp     loc_14001FA11
0x14001f92a  cmp     byte ptr [rsi+235h], 0
0x14001f931  mov     ecx, 2
0x14001f936  mov     eax, 20h ; ' '
0x14001f93b  mov     dl, 1
0x14001f93d  cmovz   ecx, eax
0x14001f940  call    I8xSetPowerFlag
0x14001f945  mov     r8d, [rdi+18h]; State
0x14001f949  mov     rcx, rbp; DeviceObject
0x14001f94c  mov     edx, [rdi+10h]; Type
0x14001f94f  call    cs:__imp_PoSetPowerState
0x14001f956  nop     dword ptr [rax+rax+00h]
0x14001f95b  xor     ebp, ebp
0x14001f95d  cmp     [rsi+235h], bpl
0x14001f964  jnz     short loc_14001F9BF
0x14001f966  cmp     [rsi+21Ah], bp
0x14001f96d  jnz     short loc_14001F9BF
0x14001f96f  mov     [rsp+68h+arg_0], r14
0x14001f974  mov     r14, [rsi+8]
0x14001f978  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001f97f  jz      short loc_14001F9A2
0x14001f981  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f988  mov     r9d, 2Fh ; '/'
0x14001f98e  mov     r8d, 16h
0x14001f994  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14001f999  mov     rcx, [rcx+40h]
0x14001f99d  call    WPP_RECORDER_SF_
0x14001f9a2  mov     [rsi+8], rbp
0x14001f9a6  test    r14, r14
0x14001f9a9  jz      short loc_14001F9BA
0x14001f9ab  mov     rcx, r14; InterruptObject
0x14001f9ae  call    cs:__imp_IoDisconnectInterrupt
0x14001f9b5  nop     dword ptr [rax+rax+00h]
0x14001f9ba  mov     r14, [rsp+68h+arg_0]
0x14001f9bf  mov     eax, [rdi+18h]
0x14001f9c2  mov     rcx, rbx; Irp
0x14001f9c5  mov     [rsi+50h], eax
0x14001f9c8  mov     eax, [rdi+20h]
0x14001f9cb  mov     [rsi+58h], eax
0x14001f9ce  mov     [rbx+30h], ebp
0x14001f9d1  call    cs:__imp_PoStartNextPowerIrp
0x14001f9d8  nop     dword ptr [rax+rax+00h]
0x14001f9dd  jmp     short loc_14001F9F3
0x14001f9df  mov     rcx, rbx; Irp
0x14001f9e2  call    cs:__imp_PoStartNextPowerIrp
0x14001f9e9  nop     dword ptr [rax+rax+00h]
0x14001f9ee  xor     ebp, ebp
0x14001f9f0  mov     [rbx+30h], ebp
0x14001f9f3  inc     byte ptr [rbx+43h]
0x14001f9f6  mov     rdx, rbx; Irp
0x14001f9f9  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14001fa01  mov     rcx, [rsi+18h]; DeviceObject
0x14001fa05  call    cs:__imp_PoCallDriver
0x14001fa0c  nop     dword ptr [rax+rax+00h]
0x14001fa11  add     rsp, 38h
0x14001fa15  pop     r15
0x14001fa17  pop     r12
0x14001fa19  pop     rdi
0x14001fa1a  pop     rsi
0x14001fa1b  pop     rbp
0x14001fa1c  pop     rbx
0x14001fa1d  retn
```
