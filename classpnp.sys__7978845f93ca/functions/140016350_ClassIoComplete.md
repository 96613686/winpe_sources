# ClassIoComplete

- ea: `0x140016350`
- end: `0x14001671b`
- name: `ClassIoComplete`
- size: `971`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1400073d4`
- `0x140008360`
- `0x140016320`
- `0x140016350`
- `0x140016730`
- `0x1400176f8`
- `0x140017fa0`
- `0x140019130`
- `0x14001fc38`
- `0x14001feac`
- `0x140022668`
- `0x140026640`
- `0x1400317e0`
- `0x1400360d4`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140016578`
- `ntoskrnl!IoFreeMdl` at `0x140016578`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040b40`
- `ntoskrnl!IoStartNextPacket` at `0x1400166de`
- `ntoskrnl!IoStartNextPacket` at `0x1400166de`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016633`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016633`
- `ntoskrnl!KeLowerIrql` at `0x1400166ed`
- `ntoskrnl!KeLowerIrql` at `0x1400166ed`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140040b66`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140040b66`
- `ntoskrnl!KfRaiseIrql` at `0x1400166ca`
- `ntoskrnl!KfRaiseIrql` at `0x1400166ca`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140016524`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140016524`

## pseudocode

```c
NTSTATUS __stdcall ClassIoComplete(PDEVICE_OBJECT DeviceObject, PIRP Irp, PVOID Context)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r12
  bool v4; // r15
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rdi
  __int64 v7; // rax
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rcx
  int v11; // esi
  __int64 v12; // r8
  _SENSE_DATA *v13; // r9
  NTSTATUS v14; // ecx
  char v15; // dl
  _DWORD **v16; // r8
  signed __int32 v17; // eax
  struct _SCSI_REQUEST_BLOCK *v19; // rdx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v20; // rcx
  KIRQL v21; // bl
  signed __int32 v22; // ett
  __int64 MajorFunction; // r9
  unsigned int LowPart; // ecx
  char v25; // dl
  unsigned int v26; // ecx
  unsigned int EaLength; // edx
  struct _SCSI_REQUEST_BLOCK *v28; // rdx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v29; // rcx
  NTSTATUS v30; // [rsp+40h] [rbp-68h] BYREF
  __int64 v31; // [rsp+48h] [rbp-60h] BYREF
  __int128 v32; // [rsp+50h] [rbp-58h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  v7 = 24;
  if ( *((_BYTE *)Context + 2) != 40 )
    v7 = 12;
  PrivateFdoData = DeviceExtension->PrivateFdoData;
  v30 = 0;
  v32 = 0;
  v11 = *(_DWORD *)((char *)Context + v7);
  if ( (*((_BYTE *)Context + 3) & 0x3F) == 1 )
  {
    PrivateFdoData->LoggedTURFailureSinceLastIO = 0;
    ClasspPerfIncrementSuccessfulIo(DeviceExtension);
    v14 = 0;
    v30 = 0;
    goto LABEL_5;
  }
  v31 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, Irp, Context);
  }
  if ( (*((_BYTE *)Context + 3) & 0x40) != 0 )
    ClasspReleaseQueue((ULONG_PTR)DeviceObject, 0);
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( (_BYTE)MajorFunction == 14 )
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  else
    LowPart = 0;
  v25 = InterpretSenseInfoWithoutHistory(
          DeviceObject,
          Irp,
          Context,
          MajorFunction,
          LowPart,
          4 - CurrentStackLocation->Parameters.Create.EaLength,
          &v30,
          &v31);
  if ( CurrentStackLocation->MajorFunction == 14
    && ((v26 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart, v26 == 2969624) || v26 == 3002396) )
  {
    v14 = v30;
    if ( v30 == -1073741764 )
    {
      v14 = 0;
      v25 = 0;
      v30 = 0;
    }
  }
  else
  {
    v14 = v30;
  }
  if ( (CurrentStackLocation->Flags & 2) != 0 && v14 == -2147483626 )
  {
    v30 = -1073741435;
  }
  else if ( !v25 )
  {
    goto LABEL_5;
  }
  EaLength = CurrentStackLocation->Parameters.Create.EaLength;
  CurrentStackLocation->Parameters.CreatePipe.Parameters = (_NAMED_PIPE_CREATE_PARAMETERS *)(EaLength - 1);
  if ( EaLength )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, Irp);
    }
    if ( PORT_ALLOCATED_SENSE(DeviceExtension, (PSCSI_REQUEST_BLOCK)Context) )
      FREE_PORT_ALLOCATED_SENSE_BUFFER(v29, v28);
    RetryRequest((_DWORD)DeviceObject, (_DWORD)Irp, (_DWORD)Context, 0, v31);
    return -1073741802;
  }
  v14 = v30;
LABEL_5:
  v15 = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction == 14 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2956480 )
    {
      ClasspTelemetryLogRemoveElementAndTruncateComplete(
        DeviceObject,
        Context,
        (unsigned int)v14,
        4 - CurrentStackLocation->Parameters.Create.EaLength);
      v15 = CurrentStackLocation->MajorFunction;
      v14 = v30;
    }
    else
    {
      v15 = 14;
    }
  }
  if ( v15 != 14 )
    v4 = (v11 & 0x800000) == 0;
  if ( v11 < 0 )
  {
    if ( *((_BYTE *)Context + 2) == 40 )
      *((_DWORD *)Context + 6) &= ~0x80000000;
    else
      *((_DWORD *)Context + 3) &= ~0x80000000;
    IoFreeMdl(Irp->MdlAddress);
    v14 = v30;
    Irp->MdlAddress = 0;
  }
  if ( v14 < 0 && ClassPnPETWEnabled )
  {
    IoGetActivityIdIrp(Irp, &v32);
    ClasspWriteSrbErrorResultEvent(
      (unsigned int)&v32,
      (_DWORD)DeviceObject,
      Irp->IoStatus.Status,
      (_DWORD)Context,
      4 - CurrentStackLocation->Parameters.SetFile.ReplaceIfExists);
    v14 = v30;
  }
  if ( (v11 & 0x20000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, Context);
      v14 = v30;
    }
    if ( (*((_DWORD *)Context + 3) & 0x200400) != 0x200400 )
      goto LABEL_19;
    v13 = (_SENSE_DATA *)*((_QWORD *)Context + 4);
    if ( v13 == DeviceExtension->SenseData
      || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_19;
    }
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v13);
  }
  else
  {
    if ( PORT_ALLOCATED_SENSE(DeviceExtension, (PSCSI_REQUEST_BLOCK)Context) )
      FREE_PORT_ALLOCATED_SENSE_BUFFER(v20, v19);
    if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 4) != 0 )
    {
      ClassFreeOrReuseSrb(DeviceExtension, Context);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      ExFreePoolWithTag(Context, 0);
    }
  }
  v14 = v30;
LABEL_19:
  Irp->IoStatus.Status = v14;
  if ( v14 >= 0 )
    goto LABEL_21;
  if ( ((unsigned int)(v14 + 1073741662) <= 1
     || (unsigned int)(v14 + 1073741806) <= 2
     || v14 == -2147483626
     || v14 == -1073741643)
    && Irp->Tail.Overlay.Thread )
  {
    IoSetHardErrorOrVerifyDevice(Irp, DeviceObject);
    v14 = v30;
    Irp->IoStatus.Information = 0;
  }
  if ( v14 >= 0 )
  {
LABEL_21:
    if ( CurrentStackLocation->MajorFunction == 14
      && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 3005448 )
    {
      ClasspLogSystemEventWithDeviceNumber(DeviceObject, 1074004127, v12, v13);
    }
  }
  if ( Irp->PendingReturned )
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( DeviceExtension->CommonExtension.DriverExtension->InitData.ClassStartIo )
  {
    if ( v4 )
    {
      v21 = KfRaiseIrql(2u);
      IoStartNextPacket(DeviceObject, 1u);
      KeLowerIrql(v21);
    }
  }
  v16 = (_DWORD **)DeviceObject->DeviceExtension;
  v17 = *v16[55];
  if ( v17 )
  {
    while ( 1 )
    {
      v22 = v17;
      v17 = _InterlockedCompareExchange(v16[55], v17 - 1, v17);
      if ( v22 == v17 )
        break;
      if ( !v17 )
        goto LABEL_31;
    }
  }
  else
  {
LABEL_31:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v16[55] + 2));
  }
  return v30;
}

```

## disassembly

```asm
0x140016350  mov     [rsp+arg_18], rbx
0x140016355  push    rbp
0x140016356  push    rsi
0x140016357  push    rdi
0x140016358  push    r12
0x14001635a  push    r13
0x14001635c  push    r14
0x14001635e  push    r15
0x140016360  sub     rsp, 70h
0x140016364  mov     rax, cs:__security_cookie
0x14001636b  xor     rax, rsp
0x14001636e  mov     [rsp+0A8h+var_48], rax
0x140016373  mov     r12, [rdx+0B8h]
0x14001637a  xor     r15d, r15d
0x14001637d  cmp     byte ptr [r8+2], 28h ; '('
0x140016382  mov     rbx, rdx
0x140016385  mov     rdi, [rcx+40h]
0x140016389  mov     edx, 0Ch
0x14001638e  mov     eax, 18h
0x140016393  mov     r14, rcx
0x140016396  cmovnz  eax, edx
0x140016399  xorps   xmm0, xmm0
0x14001639c  mov     rbp, r8
0x14001639f  lea     rdx, WPP_GLOBAL_Control
0x1400163a6  mov     rcx, [rdi+478h]
0x1400163ad  mov     r13d, 4
0x1400163b3  mov     [rsp+0A8h+var_68], r15d
0x1400163b8  movups  [rsp+0A8h+var_58], xmm0
0x1400163bd  mov     esi, [rax+r8]
0x1400163c1  movzx   eax, byte ptr [r8+3]
0x1400163c6  and     al, 3Fh
0x1400163c8  cmp     al, 1
0x1400163ca  jnz     loc_14001659E
0x1400163d0  mov     [rcx+295h], r15b
0x1400163d7  mov     rcx, rdi
0x1400163da  call    ClasspPerfIncrementSuccessfulIo
0x1400163df  mov     ecx, r15d
0x1400163e2  mov     [rsp+0A8h+var_68], ecx
0x1400163e6  movzx   edx, byte ptr [r12]
0x1400163eb  cmp     dl, 0Eh
0x1400163ee  jz      loc_1400165EB
0x1400163f4  mov     eax, esi
0x1400163f6  shr     eax, 17h
0x1400163f9  not     al
0x1400163fb  and     al, 1
0x1400163fd  cmp     dl, 0Eh
0x140016400  movzx   eax, al
0x140016403  cmovnz  r15d, eax
0x140016407  test    esi, esi
0x140016409  js      loc_140016567
0x14001640f  test    ecx, ecx
0x140016411  js      loc_14001661E
0x140016417  bt      esi, 1Dh
0x14001641b  jnb     loc_140016666
0x140016421  mov     r10, cs:WPP_GLOBAL_Control
0x140016428  lea     rsi, WPP_GLOBAL_Control
0x14001642f  cmp     r10, rsi
0x140016432  jnz     short loc_1400164B0
0x140016434  mov     eax, [rbp+0Ch]
0x140016437  and     eax, 200400h
0x14001643c  cmp     eax, 200400h
0x140016441  jnz     short loc_140016484
0x140016443  mov     r9, [rbp+20h]
0x140016447  cmp     r9, [rdi+240h]
0x14001644e  jz      short loc_140016484
0x140016450  mov     r10, cs:WPP_GLOBAL_Control
0x140016457  cmp     r10, rsi
0x14001645a  jz      short loc_140016484
0x14001645c  mov     eax, [r10+2Ch]
0x140016460  test    al, 1
0x140016462  jz      short loc_140016484
0x140016464  cmp     byte ptr [r10+29h], 4
0x140016469  jb      short loc_140016484
0x14001646b  mov     rcx, [r10+18h]
0x14001646f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140016476  mov     edx, 46h ; 'F'
0x14001647b  call    WPP_SF_q
0x140016480  mov     ecx, [rsp+0A8h+var_68]
0x140016484  mov     [rbx+30h], ecx
0x140016487  test    ecx, ecx
0x140016489  js      loc_140016684
0x14001648f  cmp     byte ptr [r12], 0Eh
0x140016494  jnz     short loc_1400164EC
0x140016496  cmp     dword ptr [r12+18h], 2DDC08h
0x14001649f  jnz     short loc_1400164EC
0x1400164a1  mov     edx, 4004009Fh
0x1400164a6  mov     rcx, r14
0x1400164a9  call    ClasspLogSystemEventWithDeviceNumber
0x1400164ae  jmp     short loc_1400164EC
0x1400164b0  mov     eax, [r10+2Ch]
0x1400164b4  test    al, 1
0x1400164b6  jz      loc_140016434
0x1400164bc  cmp     byte ptr [r10+29h], 4
0x1400164c1  jb      loc_140016434
0x1400164c7  mov     rcx, [r10+18h]
0x1400164cb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400164d2  mov     edx, 45h ; 'E'
0x1400164d7  mov     r9, rbp
0x1400164da  call    WPP_SF_q
0x1400164df  mov     ecx, [rsp+0A8h+var_68]
0x1400164e3  jmp     loc_140016434
0x1400164e8  test    ecx, ecx
0x1400164ea  jns     short loc_14001648F
0x1400164ec  cmp     byte ptr [rbx+41h], 0
0x1400164f0  jnz     short loc_14001655A
0x1400164f2  mov     rax, [rdi+20h]
0x1400164f6  cmp     qword ptr [rax+180h], 0
0x1400164fe  jnz     loc_1400166BF
0x140016504  mov     r8, [r14+40h]
0x140016508  mov     rax, [r8+1B8h]
0x14001650f  mov     eax, [rax]
0x140016511  test    eax, eax
0x140016513  jnz     loc_1400166FE
0x140016519  mov     rcx, [r8+1B8h]
0x140016520  add     rcx, 8; RunRefCacheAware
0x140016524  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001652b  nop     dword ptr [rax+rax+00h]
0x140016530  mov     eax, [rsp+0A8h+var_68]
0x140016534  mov     rcx, [rsp+0A8h+var_48]
0x140016539  xor     rcx, rsp; StackCookie
0x14001653c  call    __security_check_cookie
0x140016541  mov     rbx, [rsp+0A8h+arg_18]
0x140016549  add     rsp, 70h
0x14001654d  pop     r15
0x14001654f  pop     r14
0x140016551  pop     r13
0x140016553  pop     r12
0x140016555  pop     rdi
0x140016556  pop     rsi
0x140016557  pop     rbp
0x140016558  retn
0x14001655a  mov     rax, [rbx+0B8h]
0x140016561  or      byte ptr [rax+3], 1
0x140016565  jmp     short loc_1400164F2
0x140016567  cmp     byte ptr [rbp+2], 28h ; '('
0x14001656b  jnz     short loc_140016595
0x14001656d  and     dword ptr [rbp+18h], 7FFFFFFFh
0x140016574  mov     rcx, [rbx+8]; Mdl
0x140016578  call    cs:__imp_IoFreeMdl
0x14001657f  nop     dword ptr [rax+rax+00h]
0x140016584  mov     ecx, [rsp+0A8h+var_68]
0x140016588  mov     qword ptr [rbx+8], 0
0x140016590  jmp     loc_14001640F
0x140016595  and     dword ptr [rbp+0Ch], 7FFFFFFFh
0x14001659c  jmp     short loc_140016574
0x14001659e  mov     [rsp+0A8h+var_60], r15
0x1400165a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400165aa  cmp     rcx, rdx
0x1400165ad  jz      loc_1400409AA
0x1400165b3  mov     eax, [rcx+2Ch]
0x1400165b6  test    al, 1
0x1400165b8  jz      loc_1400409AA
0x1400165be  cmp     [rcx+29h], r13b
0x1400165c2  jb      loc_1400409AA
0x1400165c8  mov     rcx, [rcx+18h]
0x1400165cc  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400165d3  mov     edx, 42h ; 'B'
0x1400165d8  mov     [rsp+0A8h+var_88], rbp
0x1400165dd  mov     r9, rbx
0x1400165e0  call    WPP_SF_qq
0x1400165e5  nop
0x1400165e6  jmp     loc_1400409AA
0x1400165eb  cmp     dword ptr [r12+18h], 2D1CC0h
0x1400165f4  jnz     loc_140040AE8
0x1400165fa  mov     r9d, r13d
0x1400165fd  mov     r8d, ecx
0x140016600  sub     r9d, [r12+20h]
0x140016605  mov     rdx, rbp
0x140016608  mov     rcx, r14
0x14001660b  call    ClasspTelemetryLogRemoveElementAndTruncateComplete
0x140016610  movzx   edx, byte ptr [r12]
0x140016615  mov     ecx, [rsp+0A8h+var_68]
0x140016619  jmp     loc_1400163F4
0x14001661e  cmp     cs:ClassPnPETWEnabled, 0
0x140016625  jz      loc_140016417
0x14001662b  lea     rdx, [rsp+0A8h+var_58]
0x140016630  mov     rcx, rbx
0x140016633  call    cs:__imp_IoGetActivityIdIrp
0x14001663a  nop     dword ptr [rax+rax+00h]
0x14001663f  sub     r13b, [r12+20h]
0x140016644  lea     rcx, [rsp+0A8h+var_58]
0x140016649  mov     r8d, [rbx+30h]
0x14001664d  mov     r9, rbp
0x140016650  mov     rdx, r14
0x140016653  mov     byte ptr [rsp+0A8h+var_88], r13b
0x140016658  call    ClasspWriteSrbErrorResultEvent
0x14001665d  mov     ecx, [rsp+0A8h+var_68]
0x140016661  jmp     loc_140016417
0x140016666  mov     rdx, rbp; Srb
0x140016669  mov     rcx, rdi; FdoExtension
0x14001666c  call    PORT_ALLOCATED_SENSE
0x140016671  test    al, al
0x140016673  jz      loc_140040AEF
0x140016679  call    FREE_PORT_ALLOCATED_SENSE_BUFFER
0x14001667e  nop
0x14001667f  jmp     loc_140040AEF
0x140016684  lea     eax, [rcx+3FFFFF5Eh]
0x14001668a  cmp     eax, 1
0x14001668d  jbe     loc_140040B52
0x140016693  lea     eax, [rcx+3FFFFFEEh]
0x140016699  cmp     eax, 2
0x14001669c  jbe     loc_140040B52
0x1400166a2  cmp     ecx, 80000016h
0x1400166a8  jz      loc_140040B52
0x1400166ae  cmp     ecx, 0C00000B5h
0x1400166b4  jnz     loc_1400164E8
0x1400166ba  jmp     loc_140040B52
0x1400166bf  test    r15b, r15b
0x1400166c2  jz      loc_140016504
0x1400166c8  mov     cl, 2; NewIrql
0x1400166ca  call    cs:__imp_KfRaiseIrql
0x1400166d1  nop     dword ptr [rax+rax+00h]
0x1400166d6  mov     dl, 1; Cancelable
0x1400166d8  mov     rcx, r14; DeviceObject
0x1400166db  movzx   ebx, al
0x1400166de  call    cs:__imp_IoStartNextPacket
0x1400166e5  nop     dword ptr [rax+rax+00h]
0x1400166ea  movzx   ecx, bl; NewIrql
0x1400166ed  call    cs:__imp_KeLowerIrql
0x1400166f4  nop     dword ptr [rax+rax+00h]
0x1400166f9  jmp     loc_140016504
0x1400166fe  mov     rcx, [r8+1B8h]
0x140016705  lea     edx, [rax-1]
0x140016708  lock cmpxchg [rcx], edx
0x14001670c  jz      loc_140016530
0x140016712  test    eax, eax
0x140016714  jnz     short loc_1400166FE
0x140016716  jmp     loc_140016519
0x1400409aa  test    byte ptr [rbp+3], 40h
0x1400409ae  jz      short loc_1400409BA
0x1400409b0  xor     edx, edx; Irp
0x1400409b2  mov     rcx, r14; BugCheckParameter2
0x1400409b5  call    ClasspReleaseQueue
0x1400409ba  movzx   r9d, byte ptr [r12]
0x1400409bf  cmp     r9b, 0Eh
0x1400409c3  jnz     short loc_1400409CC
0x1400409c5  mov     ecx, [r12+18h]
0x1400409ca  jmp     short loc_1400409CF
0x1400409cc  mov     ecx, r15d
0x1400409cf  lea     rdx, [rsp+0A8h+var_60]
0x1400409d4  mov     eax, r13d
0x1400409d7  sub     eax, [r12+20h]
0x1400409dc  mov     r8, rbp
0x1400409df  mov     [rsp+0A8h+var_70], rdx
0x1400409e4  lea     rdx, [rsp+0A8h+var_68]
0x1400409e9  mov     [rsp+0A8h+var_78], rdx
0x1400409ee  mov     rdx, rbx
0x1400409f1  mov     [rsp+0A8h+var_80], eax
0x1400409f5  mov     dword ptr [rsp+0A8h+var_88], ecx
0x1400409f9  mov     rcx, r14
0x1400409fc  call    InterpretSenseInfoWithoutHistory
0x140040a01  cmp     byte ptr [r12], 0Eh
0x140040a06  movzx   edx, al
0x140040a09  jnz     short loc_140040A37
0x140040a0b  mov     ecx, [r12+18h]
0x140040a10  cmp     ecx, 2D5018h
0x140040a16  jz      short loc_140040A20
0x140040a18  cmp     ecx, 2DD01Ch
0x140040a1e  jnz     short loc_140040A37
0x140040a20  mov     ecx, [rsp+0A8h+var_68]
0x140040a24  cmp     ecx, 0C000003Ch
0x140040a2a  jnz     short loc_140040A3B
0x140040a2c  mov     ecx, r15d
0x140040a2f  xor     dl, dl
0x140040a31  mov     [rsp+0A8h+var_68], ecx
0x140040a35  jmp     short loc_140040A3B
0x140040a37  mov     ecx, [rsp+0A8h+var_68]
0x140040a3b  test    byte ptr [r12+2], 2
0x140040a41  jz      short loc_140040A55
0x140040a43  cmp     ecx, 80000016h
0x140040a49  jnz     short loc_140040A55
0x140040a4b  mov     [rsp+0A8h+var_68], 0C0000185h
0x140040a53  jmp     short loc_140040A5D
0x140040a55  test    dl, dl
0x140040a57  jz      loc_1400163E6
0x140040a5d  mov     edx, [r12+20h]
0x140040a62  lea     ecx, [rdx-1]
0x140040a65  mov     [r12+20h], rcx
0x140040a6a  test    edx, edx
0x140040a6c  jz      short loc_140040ADF
0x140040a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a75  lea     rsi, WPP_GLOBAL_Control
0x140040a7c  cmp     rcx, rsi
0x140040a7f  jz      short loc_140040AA6
0x140040a81  mov     eax, [rcx+2Ch]
0x140040a84  test    al, 1
0x140040a86  jz      short loc_140040AA6
0x140040a88  cmp     byte ptr [rcx+29h], 3
0x140040a8c  jb      short loc_140040AA6
0x140040a8e  mov     rcx, [rcx+18h]
0x140040a92  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140040a99  mov     edx, 43h ; 'C'
0x140040a9e  mov     r9, rbx
0x140040aa1  call    WPP_SF_q
0x140040aa6  mov     rdx, rbp; Srb
0x140040aa9  mov     rcx, rdi; FdoExtension
0x140040aac  call    PORT_ALLOCATED_SENSE
0x140040ab1  test    al, al
0x140040ab3  jz      short loc_140040ABA
0x140040ab5  call    FREE_PORT_ALLOCATED_SENSE_BUFFER
  ... truncated ...
```
