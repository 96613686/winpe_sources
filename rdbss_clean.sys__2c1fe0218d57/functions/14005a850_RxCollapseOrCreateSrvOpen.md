# RxCollapseOrCreateSrvOpen

- ea: `0x14005a850`
- end: `0x14005b2a7`
- name: `RxCollapseOrCreateSrvOpen`
- size: `2647`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `25`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140054ca0`

## callees

- `0x140002050`
- `0x140007d40`
- `0x14000f4b0`
- `0x14000f5e0`
- `0x14000f910`
- `0x140014b70`
- `0x140014c10`
- `0x140014d10`
- `0x140014ec0`
- `0x140016e20`
- `0x140016e70`
- `0x140017370`
- `0x140017a38`
- `0x1400186b8`
- `0x140025d00`
- `0x1400446a4`
- `0x140058f00`
- `0x140059e20`
- `0x14005a850`
- `0x14005b2b0`
- `0x14005b620`
- `0x14005be90`
- `0x14005c450`
- `0x14005c5f0`
- `0x14006ba40`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14005ac5c`
- `ntoskrnl!FsRtlCheckOplock` at `0x14005ac5c`
- `ntoskrnl!IoCheckShareAccess` at `0x14005a97c`
- `ntoskrnl!IoCheckShareAccess` at `0x14005ad11`
- `ntoskrnl!IoCheckShareAccess` at `0x14005adf9`
- `ntoskrnl!IoCheckShareAccess` at `0x14007cd9f`
- `ntoskrnl!IoCheckShareAccess` at `0x14005a97c`
- `ntoskrnl!IoCheckShareAccess` at `0x14005ad11`
- `ntoskrnl!IoCheckShareAccess` at `0x14005adf9`
- `ntoskrnl!IoCheckShareAccess` at `0x14007cd9f`
- `ntoskrnl!KeResetEvent` at `0x14005ac35`
- `ntoskrnl!KeResetEvent` at `0x14005afe0`
- `ntoskrnl!KeResetEvent` at `0x14005ac35`
- `ntoskrnl!KeResetEvent` at `0x14005afe0`
- `ntoskrnl!FsRtlOplockBreakH2` at `0x14005b024`
- `ntoskrnl!FsRtlOplockBreakH2` at `0x14005b024`

## pseudocode

```c
__int64 __fastcall RxCollapseOrCreateSrvOpen(PVOID Context, IRP *a2, ULONG_PTR a3)
{
  __int16 v3; // di
  ULONG v5; // r9d
  ACCESS_MASK v7; // r8d
  int v8; // r13d
  int v9; // ebx
  struct _SHARE_ACCESS *v10; // rax
  PSRV_OPEN v11; // r14
  int v12; // r13d
  __int16 v13; // di
  struct _FCB *v14; // rdx
  PSRV_OPEN SrvOpen; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // r8
  RX_BLOCK_CONDITION v26; // ecx
  NTSTATUS v28; // eax
  __int64 v29; // r9
  _DWORD *v30; // r14
  struct _DEVICE_OBJECT *v31; // r8
  int v32; // r9d
  NTSTATUS v33; // eax
  int v34; // ecx
  int v35; // r8d
  char v36; // cl
  char v37; // al
  __int64 v38; // r9
  unsigned int v39; // r13d
  unsigned int v40; // edi
  struct _SHARE_ACCESS *v41; // rdi
  int Update; // [rsp+20h] [rbp-30h]
  int Updatea; // [rsp+20h] [rbp-30h]
  ULONG DesiredShareAccess; // [rsp+40h] [rbp-10h] BYREF
  int v45; // [rsp+44h] [rbp-Ch]
  PFILE_OBJECT FileObject; // [rsp+48h] [rbp-8h]
  __int16 v47; // [rsp+90h] [rbp+40h]
  ACCESS_MASK DesiredAccess; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *((_WORD *)Context + 373);
  v5 = *((_DWORD *)Context + 133);
  v7 = *((_DWORD *)Context + 128);
  v8 = *((_DWORD *)Context + 135);
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  DesiredAccess = v7;
  v47 = v3 & 0x2000;
  DesiredShareAccess = v5;
  v45 = v8 & 8;
  v9 = RxSearchForCollapsibleOpen(Context, a3);
  v10 = (struct _SHARE_ACCESS *)(a3 + 424);
  if ( v9 >= 0 )
  {
    v30 = (_DWORD *)*((_QWORD *)Context + 9);
    IoCheckShareAccess(DesiredAccess, DesiredShareAccess, FileObject, (PSHARE_ACCESS)(a3 + 424), 0);
    if ( v30[41] == 3 )
    {
      *((_DWORD *)Context + 185) = *(_DWORD *)(a3 + 160);
      *((_DWORD *)Context + 184) = *(_DWORD *)(a3 + 164);
      if ( *(_QWORD *)(*(_QWORD *)(a3 + 392) + 80LL) )
      {
        if ( (*((_DWORD *)Context + 32) & 2) != 0 )
        {
          v9 = -1073741536;
        }
        else
        {
          *((_OWORD *)Context + 13) = 0;
          *((_OWORD *)Context + 14) = 0;
          *((_QWORD *)Context + 30) = 0;
          v9 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)(a3 + 392) + 80LL))(Context);
        }
      }
      else
      {
        v9 = -1073741822;
      }
      v31 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
          (unsigned int)v9);
        v31 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
      }
      if ( *((_QWORD *)Context + 8) )
      {
        RxUpdateFcbCounts((_DWORD)Context, a3, (unsigned int)&WPP_GLOBAL_Control, v32, v45 != 0);
        RxUpdateSrvOpenCounts(v34, (_DWORD)v30, v35, v47 != 0, Updatea, v47 != 0);
        if ( WPP_GLOBAL_Control != v31 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              26,
              v31,
              *((_QWORD *)Context + 8),
              a3,
              *(_DWORD *)(a3 + 192),
              *(_DWORD *)(a3 + 184),
              *(_DWORD *)(a3 + 188));
            v31 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
          }
          if ( WPP_GLOBAL_Control != v31
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              27,
              &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              v30,
              v30[23],
              v30[25],
              v30[22],
              v30[24]);
          }
        }
      }
      if ( v9 >= 0 )
      {
        *(_QWORD *)(*((_QWORD *)Context + 5) + 56LL) = 1;
        *((_QWORD *)Context + 75) = 1;
      }
    }
    LOBYTE(v31) = 1;
    RxFcbScavengeRelatedFobxs(a3, v30, v31);
    v10 = (struct _SHARE_ACCESS *)(a3 + 424);
  }
  v11 = 0;
  if ( v9 == -1073741275 )
  {
    v12 = v8 & 0x100;
    if ( *(int *)(a3 + 184) > 0 )
    {
      v33 = IoCheckShareAccess(DesiredAccess, DesiredShareAccess, FileObject, v10, 0);
      v9 = v33;
      if ( !v12 && v33 == -1073741757 )
      {
        KeResetEvent((PRKEVENT)Context + 16);
        v9 = FsRtlOplockBreakH2(
               a3 + 88,
               a2,
               128,
               Context,
               RxUpperOplockBreakCompleteSync,
               0,
               &DesiredAccess,
               &DesiredShareAccess);
        if ( v9 == 259 )
          goto LABEL_42;
      }
      v11 = 0;
      if ( v9 )
        goto LABEL_32;
    }
    if ( (unsigned __int8)RxDesiredAccessAffectsOplockState(a3, DesiredAccess)
      && (v3 & 0x1000) != 0
      && (*(_DWORD *)(a3 + 428) || *(_DWORD *)(a3 + 432)) )
    {
      v9 = -1073741757;
      goto LABEL_43;
    }
    v13 = v3 & 0x20;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        (unsigned int)&WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
        a3,
        a3 + 336);
    }
    v9 = RxPurgeConflictingSrvOpensEx(a3);
    if ( !v13 && v9 < 0 )
    {
      if ( v9 == -1073740747 )
      {
        v36 = *((_BYTE *)Context + 749);
        v37 = 0;
        if ( (v36 & 2) == 0 )
          v37 = 2;
        *((_BYTE *)Context + 749) = v36 & 0xFD | v37;
        if ( (v36 & 2) != 0 )
          v9 = -1073741757;
      }
      v11 = 0;
      goto LABEL_32;
    }
    if ( (*(_DWORD *)(a3 + 156) & 1) != 0 )
    {
      if ( !(*(_DWORD *)(a3 + 192) + *(_DWORD *)(a3 + 196)) )
        _InterlockedOr8((volatile signed __int8 *)(a3 + 256), 2u);
      v9 = -1073741738;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, a3);
      }
      goto LABEL_43;
    }
    IoCheckShareAccess(DesiredAccess, DesiredShareAccess, FileObject, (PSHARE_ACCESS)(a3 + 424), 0);
    if ( !v13 )
    {
      v9 = RxCheckShareAccess(a3 + 452, DesiredAccess, DesiredShareAccess);
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
            a3,
            DesiredAccess,
            DesiredShareAccess);
        }
        goto LABEL_43;
      }
    }
    if ( *(int *)(a3 + 184) > 0 && !v12 )
    {
      KeResetEvent((PRKEVENT)Context + 16);
      v28 = FsRtlCheckOplock((POPLOCK)(a3 + 88), a2, Context, RxUpperOplockBreakCompleteSync, 0);
      v9 = v28;
      if ( v28 == 259 )
      {
LABEL_42:
        v9 = 871;
LABEL_43:
        v11 = 0;
LABEL_44:
        v29 = *((_QWORD *)Context + 8);
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, v29);
          }
          --*(_DWORD *)(a3 + 184);
          --*(_DWORD *)(*((_QWORD *)Context + 9) + 88LL);
          --*(_DWORD *)(*((_QWORD *)Context + 9) + 92LL);
          if ( v45 )
            --*(_DWORD *)(a3 + 188);
          if ( v47 )
            --*(_DWORD *)(*((_QWORD *)Context + 9) + 96LL);
          RxDereference(*((PVOID *)Context + 8), LHS_ExclusiveLockHeld);
          *((_BYTE *)Context + 744) &= 0xF3u;
          *((_QWORD *)Context + 8) = 0;
        }
        if ( v11 )
        {
          RxDereference(v11, LHS_ExclusiveLockHeld);
          *((_QWORD *)Context + 9) = 0;
        }
        goto LABEL_37;
      }
      if ( v28 )
      {
        v11 = 0;
        goto LABEL_32;
      }
    }
    SrvOpen = RxCreateSrvOpen((PV_NET_ROOT)Context, v14);
    v11 = SrvOpen;
    if ( !SrvOpen )
    {
      v9 = -1073741670;
      goto LABEL_44;
    }
    *(_DWORD *)&SrvOpen->UpperFinalizationDone = DesiredAccess;
    SrvOpen->Condition = DesiredShareAccess;
    SrvOpen->BufferingToken = *((_DWORD *)Context + 135);
    *((_QWORD *)Context + 9) = SrvOpen;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)SrvOpen->ShadowContext->FastIoWrite + 4) + 276LL));
    HIDWORD(SrvOpen->TransitionWaitList.Blink) = 1;
    v18 = a3 + 392;
    v19 = *(_QWORD *)(a3 + 128);
    if ( v19 )
      v20 = *(_QWORD *)(*(_QWORD *)(v19 + 80) + 352LL);
    else
      v20 = *(_QWORD *)v18;
    if ( *(_QWORD *)(v20 + 56) )
    {
      if ( (*((_DWORD *)Context + 32) & 2) == 0 )
      {
        *((_OWORD *)Context + 13) = 0;
        *((_OWORD *)Context + 14) = 0;
        *((_QWORD *)Context + 30) = 0;
        v21 = *(_QWORD *)(a3 + 128);
        if ( v21 )
          v18 = *(_QWORD *)(v21 + 80) + 352LL;
        v22 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v18 + 56LL))(Context);
        LODWORD(v11[1].VNetRoot) = v22;
        v9 = v22;
        if ( v22 >= 0 && v22 != 260 && (DesiredAccess & 0x2000000) != 0 )
        {
          v39 = 2032127;
          if ( LODWORD(v11->TransitionWaitList.Flink) )
            v39 = (__int64)v11->TransitionWaitList.Flink & 0x1F01FF;
          if ( v13 )
          {
            v41 = (struct _SHARE_ACCESS *)(a3 + 424);
          }
          else
          {
            v40 = v39 & 0xFFFFFFDE;
            if ( (int)RxCheckShareAccess(a3 + 424, 33, DesiredShareAccess) >= 0 )
              v40 = v39;
            v39 = v40 & 0xFFFFFFF9;
            if ( (int)RxCheckShareAccess(a3 + 424, 6, DesiredShareAccess) >= 0 )
              v39 = v40;
            v41 = (struct _SHARE_ACCESS *)(a3 + 424);
            if ( (int)RxCheckShareAccess(a3 + 424, 0x10000, DesiredShareAccess) < 0 )
              v39 &= ~0x10000u;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qDD(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              v11,
              *(_DWORD *)&v11->UpperFinalizationDone,
              v39);
          }
          *(_DWORD *)&v11->UpperFinalizationDone |= v39;
          DesiredAccess |= v39;
          IoCheckShareAccess(DesiredAccess, DesiredShareAccess, FileObject, v41, 0);
        }
LABEL_22:
        if ( *((_QWORD *)Context + 8) )
        {
          RxUpdateFcbCounts((_DWORD)Context, a3, v16, v17, v45 != 0);
          RxUpdateSrvOpenCounts(v23, (_DWORD)v11, v24, v47 != 0, Update, v47 != 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qqDDD(
                WPP_GLOBAL_Control->AttachedDevice,
                32,
                v25,
                *((_QWORD *)Context + 8),
                a3,
                *(_DWORD *)(a3 + 192),
                *(_DWORD *)(a3 + 184),
                *(_DWORD *)(a3 + 188));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qDDDD(
                WPP_GLOBAL_Control->AttachedDevice,
                33,
                &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
                v11,
                v11->BufferingFlags,
                *((_DWORD *)&v11->1 + 25),
                v11->CreateOptions,
                v11->ulFileSizeVersion);
            }
          }
        }
        if ( v9 != -2147483603 )
        {
LABEL_28:
          RxInitailizeFcbPowerState(a3);
          if ( v9 >= 0 && v9 != 260 )
          {
            v26 = Condition_Good;
LABEL_31:
            RxUpdateCondition(v26, 0, (PLIST_ENTRY)((char *)&v11->TransitionWaitList.Blink + 4));
            RxNotifyBufferingManagerOfCompletedOpen(v11);
            *(_QWORD *)(*((_QWORD *)Context + 5) + 56LL) = *((_QWORD *)Context + 75);
            *((_DWORD *)Context + 44) = v9;
            goto LABEL_32;
          }
LABEL_50:
          v26 = Condition_Bad;
          goto LABEL_31;
        }
        v38 = *((_QWORD *)Context + 10);
        if ( (*(_DWORD *)(v38 + 336) & 0x400) != 0 )
        {
          if ( (unsigned __int8)RxpIsReparseTagSupported(Context, v20, *((_QWORD *)Context + 100)) )
            goto LABEL_28;
          v9 = -1073741629;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_28;
          }
          WPP_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
            3221225667LL,
            Context);
        }
        else
        {
          v9 = -1073741629;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_28;
          }
          WPP_SF_ZD(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            (unsigned int)&WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
            v38 + 360,
            195);
        }
        RxInitailizeFcbPowerState(a3);
        goto LABEL_50;
      }
      v9 = -1073741536;
    }
    else
    {
      v9 = -1073741822;
    }
    LODWORD(v11[1].VNetRoot) = v9;
    goto LABEL_22;
  }
LABEL_32:
  if ( v9 < 0 || v9 == 260 || v9 == 871 )
    goto LABEL_44;
  if ( RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Blink )
    *((_QWORD *)Context + 25) = RdbssStatisticsEntryArrayFindOrCreatePrimaryInstance(
                                  (int)RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink,
                                  *((_QWORD *)Context + 8) + 280LL);
LABEL_37:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      *((_QWORD *)Context + 9));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14005a850  mov     [rsp-38h+arg_10], rbx
0x14005a855  mov     [rsp-38h+Irp], rdx
0x14005a85a  push    rbp
0x14005a85b  push    rsi
0x14005a85c  push    rdi
0x14005a85d  push    r12
0x14005a85f  push    r13
0x14005a861  push    r14
0x14005a863  push    r15
0x14005a865  mov     rbp, rsp
0x14005a868  sub     rsp, 50h
0x14005a86c  movzx   edi, word ptr [rcx+2EAh]
0x14005a873  mov     rsi, rcx
0x14005a876  mov     r9d, [rcx+214h]
0x14005a87d  mov     r15, r8
0x14005a880  mov     r8d, [rcx+200h]
0x14005a887  mov     ecx, 2000h
0x14005a88c  mov     rax, [rdx+0B8h]
0x14005a893  mov     rdx, r15
0x14005a896  mov     r13d, [rsi+21Ch]
0x14005a89d  mov     rax, [rax+30h]
0x14005a8a1  mov     [rbp+FileObject], rax
0x14005a8a5  movzx   eax, di
0x14005a8a8  and     ax, cx
0x14005a8ab  mov     [rbp+DesiredAccess], r8d
0x14005a8af  mov     [rbp+arg_0], ax
0x14005a8b3  mov     rcx, rsi
0x14005a8b6  mov     eax, r13d
0x14005a8b9  mov     [rbp+DesiredShareAccess], r9d
0x14005a8bd  and     eax, 8
0x14005a8c0  mov     [rbp+var_C], eax
0x14005a8c3  call    RxSearchForCollapsibleOpen
0x14005a8c8  mov     ebx, eax
0x14005a8ca  lea     rax, [r15+1A8h]
0x14005a8d1  test    ebx, ebx
0x14005a8d3  jns     loc_14005ACFB
0x14005a8d9  xor     r14d, r14d
0x14005a8dc  cmp     ebx, 0C0000225h
0x14005a8e2  jnz     loc_14005AB7B
0x14005a8e8  and     r13d, 100h
0x14005a8ef  mov     r14d, 0C0000043h
0x14005a8f5  cmp     dword ptr [r15+0B8h], 0
0x14005a8fd  jg      loc_14005ADE7
0x14005a903  mov     edx, [rbp+DesiredAccess]
0x14005a906  mov     rcx, r15
0x14005a909  call    RxDesiredAccessAffectsOplockState
0x14005a90e  test    al, al
0x14005a910  jnz     loc_14005AF19
0x14005a916  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a91d  lea     r14, WPP_GLOBAL_Control
0x14005a924  and     di, 20h
0x14005a928  cmp     rcx, r14
0x14005a92b  jz      short loc_14005A938
0x14005a92d  mov     eax, [rcx+2Ch]
0x14005a930  test    al, 8
0x14005a932  jnz     loc_14005B04C
0x14005a938  xor     r9d, r9d
0x14005a93b  lea     r8, [rsi+200h]
0x14005a942  xor     edx, edx
0x14005a944  mov     rcx, r15; BugCheckParameter2
0x14005a947  call    RxPurgeConflictingSrvOpensEx
0x14005a94c  mov     ebx, eax
0x14005a94e  test    di, di
0x14005a951  jz      loc_14005ACDA
0x14005a957  mov     eax, [r15+9Ch]
0x14005a95e  test    al, 1
0x14005a960  jnz     loc_14005B0AF
0x14005a966  mov     r8, [rbp+FileObject]; FileObject
0x14005a96a  lea     r9, [r15+1A8h]; ShareAccess
0x14005a971  mov     edx, [rbp+DesiredShareAccess]; DesiredShareAccess
0x14005a974  mov     ecx, [rbp+DesiredAccess]; DesiredAccess
0x14005a977  mov     [rsp+50h+Update], 0; Update
0x14005a97c  call    cs:__imp_IoCheckShareAccess
0x14005a983  nop     dword ptr [rax+rax+00h]
0x14005a988  test    di, di
0x14005a98b  jnz     short loc_14005A9AA
0x14005a98d  mov     r8d, [rbp+DesiredShareAccess]
0x14005a991  lea     rcx, [r15+1C4h]
0x14005a998  mov     edx, [rbp+DesiredAccess]
0x14005a99b  call    RxCheckShareAccess
0x14005a9a0  mov     ebx, eax
0x14005a9a2  test    eax, eax
0x14005a9a4  js      loc_14005AF89
0x14005a9aa  cmp     dword ptr [r15+0B8h], 0
0x14005a9b2  jg      loc_14005AC25
0x14005a9b8  mov     rcx, rsi; VNetRoot
0x14005a9bb  call    RxCreateSrvOpen
0x14005a9c0  mov     r14, rax
0x14005a9c3  test    rax, rax
0x14005a9c6  jz      loc_14005B10F
0x14005a9cc  mov     eax, [rbp+DesiredAccess]
0x14005a9cf  mov     [r14+78h], eax
0x14005a9d3  mov     eax, [rbp+DesiredShareAccess]
0x14005a9d6  mov     [r14+7Ch], eax
0x14005a9da  mov     eax, [rsi+21Ch]
0x14005a9e0  mov     [r14+80h], eax
0x14005a9e7  mov     [rsi+48h], r14
0x14005a9eb  mov     rax, [r14+28h]
0x14005a9ef  mov     rcx, [rax+20h]
0x14005a9f3  mov     rax, [rcx+20h]
0x14005a9f7  lock inc dword ptr [rax+114h]
0x14005a9fe  mov     dword ptr [r14+0A4h], 1
0x14005aa09  lea     rcx, [r15+188h]
0x14005aa10  mov     rax, [r15+80h]
0x14005aa17  test    rax, rax
0x14005aa1a  jnz     loc_14005ACAF
0x14005aa20  mov     rdx, [rcx]
0x14005aa23  cmp     qword ptr [rdx+38h], 0
0x14005aa28  jz      loc_14005ACBF
0x14005aa2e  mov     eax, [rsi+80h]
0x14005aa34  test    al, 2
0x14005aa36  jnz     loc_14005B19C
0x14005aa3c  xor     eax, eax
0x14005aa3e  xorps   xmm0, xmm0
0x14005aa41  movups  xmmword ptr [rsi+0D0h], xmm0
0x14005aa48  movups  xmmword ptr [rsi+0E0h], xmm0
0x14005aa4f  mov     [rsi+0F0h], rax
0x14005aa56  mov     rax, [r15+80h]
0x14005aa5d  test    rax, rax
0x14005aa60  jz      short loc_14005AA6D
0x14005aa62  mov     rcx, [rax+50h]
0x14005aa66  add     rcx, 160h
0x14005aa6d  mov     rax, [rcx]
0x14005aa70  mov     rcx, rsi
0x14005aa73  mov     rax, [rax+38h]
0x14005aa77  call    _guard_dispatch_icall
0x14005aa7c  mov     [r14+0E8h], eax
0x14005aa83  mov     ebx, eax
0x14005aa85  test    eax, eax
0x14005aa87  js      short loc_14005AA9D
0x14005aa89  cmp     eax, 104h
0x14005aa8e  jz      short loc_14005AA9D
0x14005aa90  test    [rbp+DesiredAccess], 2000000h
0x14005aa97  jnz     loc_14007CCB4
0x14005aa9d  cmp     qword ptr [rsi+40h], 0
0x14005aaa2  jz      loc_14005AF7D
0x14005aaa8  xor     eax, eax
0x14005aaaa  mov     rdx, r15
0x14005aaad  cmp     [rbp+var_C], eax
0x14005aab0  mov     rcx, rsi
0x14005aab3  setnz   al
0x14005aab6  mov     dword ptr [rsp+50h+Update], eax
0x14005aaba  call    RxUpdateFcbCounts
0x14005aabf  xor     r9d, r9d
0x14005aac2  mov     rdx, r14
0x14005aac5  cmp     [rbp+arg_0], r9w
0x14005aaca  setnz   r9b
0x14005aace  mov     dword ptr [rsp+50h+var_28], r9d
0x14005aad3  call    RxUpdateSrvOpenCounts
0x14005aad8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aadf  lea     rdi, WPP_GLOBAL_Control
0x14005aae6  cmp     rcx, rdi
0x14005aae9  jz      short loc_14005AB0D
0x14005aaeb  mov     eax, [rcx+2Ch]
0x14005aaee  test    al, 8
0x14005aaf0  jnz     loc_14005B1A6
0x14005aaf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aafd  cmp     rcx, rdi
0x14005ab00  jz      short loc_14005AB0D
0x14005ab02  mov     eax, [rcx+2Ch]
0x14005ab05  test    al, 8
0x14005ab07  jnz     loc_14005B1ED
0x14005ab0d  cmp     ebx, 8000002Dh
0x14005ab13  jz      loc_14005B119
0x14005ab19  mov     rcx, r15
0x14005ab1c  call    RxInitailizeFcbPowerState
0x14005ab21  test    ebx, ebx
0x14005ab23  js      loc_14005ACD0
0x14005ab29  cmp     ebx, 104h
0x14005ab2f  jz      loc_14005ACD0
0x14005ab35  mov     ecx, 3; NewConditionValue
0x14005ab3a  lea     rax, [r14+0A8h]
0x14005ab41  mov     word ptr [rsp+50h+var_28], 0EB1Ch
0x14005ab48  xor     r9d, r9d
0x14005ab4b  mov     qword ptr [rsp+50h+Update], rax
0x14005ab50  lea     r8, [r14+0A4h]; TransitionWaitList
0x14005ab57  xor     edx, edx; Condition
0x14005ab59  call    RxUpdateCondition
0x14005ab5e  mov     rcx, r14
0x14005ab61  call    RxNotifyBufferingManagerOfCompletedOpen
0x14005ab66  mov     rcx, [rsi+28h]
0x14005ab6a  mov     rax, [rsi+258h]
0x14005ab71  mov     [rcx+38h], rax
0x14005ab75  mov     [rsi+0B0h], ebx
0x14005ab7b  mov     edi, 2
0x14005ab80  test    ebx, ebx
0x14005ab82  js      loc_14005AC82
0x14005ab88  cmp     ebx, 104h
0x14005ab8e  jz      loc_14005AC82
0x14005ab94  cmp     ebx, 367h
0x14005ab9a  jz      loc_14005AC82
0x14005aba0  mov     rax, cs:RxFileSystemDeviceObject
0x14005aba7  mov     rdx, [rax+4F0h]
0x14005abae  test    rdx, rdx
0x14005abb1  jz      short loc_14005ABEC
0x14005abb3  mov     r8, gs:188h
0x14005abbc  mov     rcx, cs:RxFileSystemDeviceObject
0x14005abc3  mov     rax, [rsi+40h]
0x14005abc7  mov     r9, [rsi+220h]
0x14005abce  add     rax, 118h
0x14005abd4  mov     qword ptr [rsp+50h+Update], rax; __int64
0x14005abd9  mov     rcx, [rcx+4E8h]; int
0x14005abe0  call    RdbssStatisticsEntryArrayFindOrCreatePrimaryInstance
0x14005abe5  mov     [rsi+0C8h], rax
0x14005abec  mov     rcx, cs:WPP_GLOBAL_Control
0x14005abf3  lea     rax, WPP_GLOBAL_Control
0x14005abfa  cmp     rcx, rax
0x14005abfd  jz      short loc_14005AC0A
0x14005abff  mov     eax, [rcx+2Ch]
0x14005ac02  test    al, 8
0x14005ac04  jnz     loc_14005B27B
0x14005ac0a  mov     eax, ebx
0x14005ac0c  mov     rbx, [rsp+50h+arg_10]
0x14005ac14  add     rsp, 50h
0x14005ac18  pop     r15
0x14005ac1a  pop     r14
0x14005ac1c  pop     r13
0x14005ac1e  pop     r12
0x14005ac20  pop     rdi
0x14005ac21  pop     rsi
0x14005ac22  pop     rbp
0x14005ac23  retn
0x14005ac25  test    r13d, r13d
0x14005ac28  jnz     loc_14005A9B8
0x14005ac2e  lea     rcx, [rsi+180h]; Event
0x14005ac35  call    cs:__imp_KeResetEvent
0x14005ac3c  nop     dword ptr [rax+rax+00h]
0x14005ac41  mov     rdx, [rbp+Irp]; Irp
0x14005ac45  lea     rcx, [r15+58h]; Oplock
0x14005ac49  lea     r9, RxUpperOplockBreakCompleteSync; CompletionRoutine
0x14005ac50  mov     qword ptr [rsp+50h+Update], 0; PostIrpRoutine
0x14005ac59  mov     r8, rsi; Context
0x14005ac5c  call    cs:__imp_FsRtlCheckOplock
0x14005ac63  nop     dword ptr [rax+rax+00h]
0x14005ac68  mov     ebx, eax
0x14005ac6a  cmp     eax, 103h
0x14005ac6f  jnz     loc_14005B18C
0x14005ac75  mov     ebx, 367h
0x14005ac7a  xor     r14d, r14d
0x14005ac7d  mov     edi, 2
0x14005ac82  mov     r9, [rsi+40h]
0x14005ac86  test    r9, r9
0x14005ac89  jnz     loc_14005B234
0x14005ac8f  test    r14, r14
0x14005ac92  jz      loc_14005ABEC
0x14005ac98  mov     edx, edi; LockHoldingState
0x14005ac9a  mov     rcx, r14; Instance
0x14005ac9d  call    RxDereference
0x14005aca2  mov     qword ptr [rsi+48h], 0
0x14005acaa  jmp     loc_14005ABEC
0x14005acaf  mov     rax, [rax+50h]
0x14005acb3  mov     rdx, [rax+160h]
0x14005acba  jmp     loc_14005AA23
0x14005acbf  mov     ebx, 0C0000002h
0x14005acc4  mov     [r14+0E8h], ebx
0x14005accb  jmp     loc_14005AA9D
0x14005acd0  mov     ecx, 4
0x14005acd5  jmp     loc_14005AB3A
0x14005acda  test    ebx, ebx
0x14005acdc  jns     loc_14005A957
0x14005ace2  mov     edi, 2
0x14005ace7  cmp     ebx, 0C0000435h
0x14005aced  jz      loc_14005B07F
0x14005acf3  xor     r14d, r14d
0x14005acf6  jmp     loc_14005AB80
0x14005acfb  mov     r8, [rbp+FileObject]; FileObject
0x14005acff  mov     r9, rax; ShareAccess
0x14005ad02  mov     edx, [rbp+DesiredShareAccess]; DesiredShareAccess
0x14005ad05  mov     ecx, [rbp+DesiredAccess]; DesiredAccess
0x14005ad08  mov     r14, [rsi+48h]
0x14005ad0c  mov     [rsp+50h+Update], 0; Update
0x14005ad11  call    cs:__imp_IoCheckShareAccess
0x14005ad18  nop     dword ptr [rax+rax+00h]
0x14005ad1d  cmp     dword ptr [r14+0A4h], 3
0x14005ad25  jnz     loc_14005ADCD
0x14005ad2b  mov     eax, [r15+0A0h]
0x14005ad32  mov     [rsi+2E4h], eax
0x14005ad38  mov     eax, [r15+0A4h]
0x14005ad3f  mov     [rsi+2E0h], eax
0x14005ad45  mov     rax, [r15+188h]
0x14005ad4c  cmp     qword ptr [rax+50h], 0
0x14005ad51  jz      loc_14005B042
0x14005ad57  mov     eax, [rsi+80h]
0x14005ad5d  test    al, 2
0x14005ad5f  jnz     loc_14005B182
0x14005ad65  xor     eax, eax
0x14005ad67  xorps   xmm0, xmm0
0x14005ad6a  movups  xmmword ptr [rsi+0D0h], xmm0
0x14005ad71  mov     rcx, rsi
0x14005ad74  movups  xmmword ptr [rsi+0E0h], xmm0
0x14005ad7b  mov     [rsi+0F0h], rax
0x14005ad82  mov     rax, [r15+188h]
0x14005ad89  mov     rax, [rax+50h]
0x14005ad8d  call    _guard_dispatch_icall
0x14005ad92  mov     ebx, eax
0x14005ad94  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad9b  lea     r8, WPP_GLOBAL_Control
0x14005ada2  cmp     rcx, r8
0x14005ada5  jnz     loc_14005AF44
0x14005adab  cmp     qword ptr [rsi+40h], 0
  ... truncated ...
```
