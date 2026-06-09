# RxCommonClose

- ea: `0x1400649a0`
- end: `0x140065381`
- name: `RxCommonClose`
- size: `2529`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002ff0`
- `0x140004180`
- `0x140009b80`
- `0x14000ce10`
- `0x140015230`
- `0x140016d40`
- `0x140016e20`
- `0x140016e70`
- `0x140016fc0`
- `0x140017280`
- `0x140017370`
- `0x14001820c`
- `0x140018360`
- `0x140018480`
- `0x140025d00`
- `0x140057660`
- `0x140057a80`
- `0x140058540`
- `0x140058f00`
- `0x1400649a0`
- `0x140065390`
- `0x140065580`
- `0x140065690`
- `0x140065ca0`
- `0x14006a4c0`
- `0x14006ba40`
- `0x14006f3e0`
- `0x1400769b0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14006509e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006509e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400651c9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400651c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400651e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400651e4`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x140064ffa`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x140064ffa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f45`
- `ntoskrnl!KeBugCheckEx` at `0x140064e14`
- `ntoskrnl!KeBugCheckEx` at `0x140064e38`
- `ntoskrnl!KeBugCheckEx` at `0x140064e14`
- `ntoskrnl!KeBugCheckEx` at `0x140064e38`

## string_xrefs

- `0x14007b146`: `RxCommonClose`

## pseudocode

```c
__int64 __fastcall RxCommonClose(PRX_CONTEXT RxContext, __int64 a2)
{
  _QWORD *v3; // r15
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *Flink; // rax
  ULONG_PTR v6; // rsi
  struct _FOBX *v7; // r14
  unsigned __int16 v8; // di
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r12d
  PDEVICE_OBJECT v12; // rcx
  LARGE_INTEGER *v13; // rdi
  _DWORD *Context2; // rcx
  int v15; // eax
  LARGE_INTEGER v16; // rdx
  char v17; // di
  _DWORD *v18; // rdx
  int v19; // eax
  PVOID v20; // rcx
  char *v21; // r8
  unsigned int i; // edi
  BOOLEAN v23; // al
  ULONG v24; // r8d
  const CHAR *v25; // r9
  int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rax
  LARGE_INTEGER v29; // rax
  __int64 Timer_high; // rdx
  int v31; // ecx
  ULONG v32; // r8d
  PCSTR v33; // r9
  const CHAR *BugCheckParameter4; // [rsp+20h] [rbp-98h]
  ULONG BugCheckParameter4a; // [rsp+20h] [rbp-98h]
  PCSTR BugCheckParameter4b; // [rsp+20h] [rbp-98h]
  ULONG v38; // [rsp+28h] [rbp-90h]
  ULONG LowPart; // [rsp+28h] [rbp-90h]
  int v40; // [rsp+54h] [rbp-64h]
  __int64 v41; // [rsp+60h] [rbp-58h]
  _DWORD *v42; // [rsp+68h] [rbp-50h]
  LARGE_INTEGER *v43; // [rsp+70h] [rbp-48h]
  _DWORD *v44; // [rsp+C8h] [rbp+10h]
  char *v45; // [rsp+C8h] [rbp+10h]
  LARGE_INTEGER Interval; // [rsp+D0h] [rbp+18h] BYREF
  ULONG_PTR v47; // [rsp+D8h] [rbp+20h]

  v3 = *(_QWORD **)(*(_QWORD *)(a2 + 184) + 48LL);
  Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
  if ( Blink )
  {
    Flink = Blink[42].Flink;
    if ( Flink )
    {
      LOBYTE(a2) = 5;
      ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(RxContext, a2);
    }
  }
  if ( v3 )
  {
    v6 = v3[3];
    v47 = v6;
    v7 = (struct _FOBX *)v3[4];
    if ( *(_WORD *)v6 == 0xEC23 && v7 )
      v8 = -5080;
    else
      v8 = *(_WORD *)v6;
  }
  else
  {
    v6 = 0;
    v47 = 0;
    v7 = 0;
    v8 = -5088;
  }
  *((_BYTE *)&RxContext->9 + 104) &= ~2u;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqqL(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids,
      RxContext,
      v6,
      v3,
      v8);
  }
  if ( v7
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, v7, v7->Context2);
  }
  v11 = _RxAcquireFcb((PFCB)v6, RxContext, 1u, 0, BugCheckParameter4, v38);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, v6);
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LowPart = *(_DWORD *)(v6 + 192);
      BugCheckParameter4a = *(_DWORD *)(v6 + 156);
      WPP_SF_qDdddd(WPP_GLOBAL_Control->AttachedDevice, v9, v10, v6);
    }
    if ( v8 != 60455 )
    {
      v9 = 0x140000000uLL;
      switch ( v8 )
      {
        case 0xEC20u:
        case 0xEC21u:
        case 0xEC22u:
        case 0xEC25u:
        case 0xEC26u:
          break;
        case 0xEC24u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids);
          }
          ExFreePoolWithTag(v7->Context2, 0);
          ExFreePoolWithTag(v7, 0);
          _InterlockedDecrement((volatile signed __int32 *)(v6 + 192));
          RxpDereferenceAndFinalizeNetFcb((PFCB)v6, RxContext, 0, 0);
          v3[3] = -1;
          v3[5] = 0;
          goto LABEL_116;
        default:
          KeBugCheckEx(0x27u, 0xC10E019C, v8, 0, 0);
      }
    }
    v13 = *(LARGE_INTEGER **)(v6 + 120);
    v43 = v13;
    if ( _InterlockedIncrement((volatile signed __int32 *)(v6 + 152)) == 1 )
      KeBugCheckEx(0x27u, 0xFCB003A5, v6, 1u, 0);
    if ( v7 )
    {
      RxSelectAndSwitchPagingFileObject(v6, 0, (ULONG_PTR)v7, 2u);
      Context2 = v7->Context2;
      v44 = Context2;
      if ( (*(_DWORD *)(v6 + 156) & 0x81) != 0 )
        goto LABEL_27;
      v15 = *(_DWORD *)(v6 + 164);
      if ( (v15 & 0x10) == 0 && (v15 & 0x20) == 0 )
        goto LABEL_27;
      if ( (*(_DWORD *)(v6 + 160) & 0x800) == 0 )
        goto LABEL_27;
      v16 = v13[4];
      Interval = v16;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, v7, Context2);
        Context2 = v44;
        v16 = Interval;
      }
      if ( Context2
        && Context2[23] == 1
        && (Context2[18] & 0x1200) == 0
        && *(_DWORD *)(v16.QuadPart + 232) < *(_DWORD *)(v16.QuadPart + 100)
        && (v13[7].LowPart & 0x400) == 0 )
      {
        ((void (*)(void))RxDelayCloseSrvOpen)();
        v17 = 1;
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 0x10) != 0 )
          McTemplateK0ppp_EtwWriteTransfer(
            v26,
            (unsigned int)RxDelayClose,
            (_DWORD)RxContext + 412,
            v6,
            (char)v44,
            (char)v7);
        Context2 = v44;
      }
      else
      {
LABEL_27:
        v17 = 0;
      }
      if ( !v17 && (*(_DWORD *)(v6 + 156) & 0x80u) == 0 && Context2[23] == 1 )
      {
        v18 = *(_DWORD **)(v6 + 712);
        v42 = v18;
        if ( v18 )
        {
          if ( *(_DWORD **)(v6 + 720) == Context2 )
          {
            v27 = 0;
            while ( 1 )
            {
              v40 = v27;
              if ( (unsigned int)v27 >= *v18 )
                break;
              v28 = 2 * v27;
              Interval = *(LARGE_INTEGER *)&v18[2 * v28 + 4];
              v41 = *(_QWORD *)&v18[2 * v28 + 6];
              v29.QuadPart = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FsRtlIsExtentDangling)(
                               (LARGE_INTEGER)Interval.QuadPart,
                               v41,
                               0);
              if ( Interval.QuadPart <= (unsigned __int64)v29.QuadPart
                && v29.QuadPart < (unsigned __int64)(Interval.QuadPart + v41) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
                  if ( (Timer_high & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    LowPart = v29.LowPart;
                    BugCheckParameter4a = v6;
                    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqqqqD)(
                      WPP_GLOBAL_Control->AttachedDevice,
                      Timer_high,
                      (LARGE_INTEGER)Interval.QuadPart,
                      v44);
                  }
                }
                Interval.QuadPart = -160000;
                KeDelayExecutionThread(0, 0, &Interval);
                if ( (unsigned __int8)RxHasDanglingExtent(v44, v6) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_qq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids,
                      v7,
                      v44);
                  }
                  RxDelayCloseSrvOpen(v44);
                  v17 = 1;
                  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 0x10) != 0 )
                    McTemplateK0ppp_EtwWriteTransfer(
                      v31,
                      (unsigned int)RxDelayClose,
                      (_DWORD)RxContext + 412,
                      v6,
                      (char)v44,
                      (char)v7);
                }
                break;
              }
              v27 = (unsigned int)(v40 + 1);
              v18 = v42;
            }
          }
        }
      }
      RxMarkFobxOnClose(v7);
      v7->PipeHandleInformation = 0;
    }
    else
    {
      v17 = 0;
    }
    if ( !v17 )
      v11 = RxCloseAssociatedSrvOpen(RxContext, v7);
    if ( RxContext->TrackerHistory[9].Flags == 2 )
    {
      RfsReleaseRundownProtection(&v7->ScavengerFinalizationList.Blink->Blink);
      *(_QWORD *)&RxContext->TrackerHistory[10].AcquireRelease = 0;
      RxContext->TrackerHistory[9].Flags = 0;
    }
    if ( v17 )
    {
      RxContext->MRxContext[1] = 0;
      if ( RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink )
        RdbssStatisticsEntryArrayRelease(v12, &v7[1].1 + 2);
      RxDereference(v7, LHS_SharedLockHeld);
    }
    else if ( v7 )
    {
      if ( BYTE5(v43[9].QuadPart) != 3 && !*(_DWORD *)(v6 + 192) )
      {
        v19 = *(_DWORD *)(v6 + 156);
        if ( (v19 & 1) != 0 && (v19 & 0x1000080) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, v6);
          }
          LOBYTE(v10) = 1;
          RxFcbScavengeRelatedFobxs(v6, 0, v10);
          _RxReleaseFcb(0, (PMRX_FCB)v6, v32, v33, BugCheckParameter4a);
          ExAcquireResourceExclusiveLite((PERESOURCE)&v43[43], 1u);
          RxOrphanThisFcb((PFCB)v6);
          ExReleaseResourceLite((PERESOURCE)&v43[43]);
          _RxAcquireFcb((PFCB)v6, 0, 1u, 0, BugCheckParameter4b, LowPart);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, v6);
          }
        }
      }
      v20 = RxContext->MRxContext[1];
      if ( v20 )
      {
        RdbssStatisticsEntryUpdateSocketCounters(
          v20,
          v9,
          LODWORD(RxContext->ForceLonglongAligmentDummyField),
          HIDWORD(RxContext->MRxContext[0]));
        RxContext->MRxContext[1] = 0;
      }
      if ( RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink )
      {
        v21 = (char *)(&v7[1].1 + 2);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_9c28be90d7bc318928ff989cb0a9d2b4_Traceguids,
            &v7[1].1 + 2);
          v21 = (char *)(&v7[1].1 + 2);
        }
        for ( i = 0; i < 4; ++i )
        {
          v45 = &v21[8 * i];
          if ( *(_QWORD *)v45 )
          {
            RdbssStatisticsEntryRelease();
            *(_QWORD *)v45 = 0;
            v21 = (char *)(&v7[1].1 + 2);
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_9c28be90d7bc318928ff989cb0a9d2b4_Traceguids);
        }
      }
      RxDereference(v7, LHS_ExclusiveLockHeld);
    }
    if ( (*(_DWORD *)(v6 + 156) & 0x80040) == 0 )
      RxProcessFcbChangeBufferingStateRequestInternal((PVOID)v6);
    v23 = RxpDereferenceAndFinalizeNetFcb((PFCB)v6, RxContext, 0, 0);
    v3[3] = -1;
    v3[5] = 0;
    if ( !v23 )
      _RxReleaseFcb(RxContext, (PMRX_FCB)v6, v24, v25, BugCheckParameter4a);
  }
LABEL_116:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1400649a0  mov     [rsp+arg_0], rcx
0x1400649a5  push    rbx
0x1400649a6  push    rsi
0x1400649a7  push    rdi
0x1400649a8  push    r12
0x1400649aa  push    r13
0x1400649ac  push    r14
0x1400649ae  push    r15
0x1400649b0  sub     rsp, 80h
0x1400649b7  mov     rbx, rcx
0x1400649ba  mov     rax, [rdx+0B8h]
0x1400649c1  mov     r15, [rax+30h]
0x1400649c5  mov     [rsp+0B8h+var_68], 0
0x1400649ca  mov     rax, [rcx+50h]
0x1400649ce  mov     rax, [rax+160h]
0x1400649d5  test    rax, rax
0x1400649d8  jz      short loc_1400649ED
0x1400649da  mov     rax, [rax+2A0h]
0x1400649e1  test    rax, rax
0x1400649e4  jz      short loc_1400649ED
0x1400649e6  mov     dl, 5
0x1400649e8  call    _guard_dispatch_icall
0x1400649ed  test    r15, r15
0x1400649f0  jz      loc_1400652FE
0x1400649f6  mov     rsi, [r15+18h]
0x1400649fa  mov     [rsp+0B8h+arg_18], rsi
0x140064a02  mov     r14, [r15+20h]
0x140064a06  movzx   eax, word ptr [rsi]
0x140064a09  mov     ecx, 0EC23h
0x140064a0e  cmp     ax, cx
0x140064a11  jz      loc_1400652E8
0x140064a17  movzx   edi, ax
0x140064a1a  xor     r13d, r13d
0x140064a1d  and     byte ptr [rbx+1F8h], 0FDh
0x140064a24  lea     rax, WPP_GLOBAL_Control
0x140064a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a32  cmp     rcx, rax
0x140064a35  jz      short loc_140064A49
0x140064a37  mov     eax, [rcx+2Ch]
0x140064a3a  test    al, 4
0x140064a3c  jnz     loc_140065319
0x140064a42  lea     rax, WPP_GLOBAL_Control
0x140064a49  test    r14, r14
0x140064a4c  jz      short loc_140064A65
0x140064a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a55  cmp     rcx, rax
0x140064a58  jz      short loc_140064A65
0x140064a5a  mov     eax, [rcx+2Ch]
0x140064a5d  test    al, 8
0x140064a5f  jnz     loc_140065351
0x140064a65  xor     r9d, r9d; LineNumber
0x140064a68  mov     r8d, 1; Mode
0x140064a6e  mov     rdx, rbx; RxContext
0x140064a71  mov     rcx, rsi; Fcb
0x140064a74  call    __RxAcquireFcb
0x140064a79  mov     r12d, eax
0x140064a7c  mov     [rsp+0B8h+var_5C], eax
0x140064a80  test    eax, eax
0x140064a82  jnz     loc_140064E45
0x140064a88  mov     [rsp+0B8h+var_68], 1
0x140064a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a94  lea     rax, WPP_GLOBAL_Control
0x140064a9b  cmp     rcx, rax
0x140064a9e  jz      short loc_140064AAB
0x140064aa0  mov     eax, [rcx+2Ch]
0x140064aa3  test    al, 8
0x140064aa5  jnz     loc_140064E93
0x140064aab  movzx   eax, di
0x140064aae  cmp     eax, 0EC27h
0x140064ab3  jnz     loc_140064DF0
0x140064ab9  mov     rdi, [rsi+78h]; jumptable 0000000140064EF3 cases 60448-60450,60453,60454
0x140064abd  mov     [rsp+0B8h+var_48], rdi
0x140064ac2  mov     eax, 1
0x140064ac7  lock xadd [rsi+98h], eax
0x140064acf  inc     eax
0x140064ad1  cmp     eax, 1
0x140064ad4  jz      loc_140064E20
0x140064ada  test    r14, r14
0x140064add  jz      loc_140064D44
0x140064ae3  mov     r9d, 2
0x140064ae9  mov     r8, r14
0x140064aec  xor     edx, edx
0x140064aee  mov     rcx, rsi; BugCheckParameter3
0x140064af1  call    RxSelectAndSwitchPagingFileObject
0x140064af6  mov     rcx, [r14+20h]
0x140064afa  mov     [rsp+0B8h+arg_8], rcx
0x140064b02  mov     eax, [rsi+9Ch]
0x140064b08  test    al, 81h
0x140064b0a  jnz     short loc_140064B69
0x140064b0c  mov     eax, [rsi+0A4h]
0x140064b12  test    al, 10h
0x140064b14  jnz     short loc_140064B1A
0x140064b16  test    al, 20h
0x140064b18  jz      short loc_140064B69
0x140064b1a  test    dword ptr [rsi+0A0h], 800h
0x140064b24  jz      short loc_140064B69
0x140064b26  mov     rdx, [rdi+20h]
0x140064b2a  mov     qword ptr [rsp+0B8h+Interval], rdx
0x140064b32  mov     r10, cs:WPP_GLOBAL_Control
0x140064b39  lea     rax, WPP_GLOBAL_Control
0x140064b40  cmp     r10, rax
0x140064b43  jz      short loc_140064B51
0x140064b45  mov     eax, [r10+2Ch]
0x140064b49  test    al, 8
0x140064b4b  jnz     loc_140064F81
0x140064b51  test    rcx, rcx
0x140064b54  jz      short loc_140064B69
0x140064b56  cmp     dword ptr [rcx+5Ch], 1
0x140064b5a  jnz     short loc_140064B69
0x140064b5c  test    dword ptr [rcx+48h], 1200h
0x140064b63  jz      loc_140064D89
0x140064b69  xor     dil, dil
0x140064b6c  test    dil, dil
0x140064b6f  jnz     short loc_140064B9B
0x140064b71  mov     eax, [rsi+9Ch]
0x140064b77  test    al, al
0x140064b79  js      short loc_140064B9B
0x140064b7b  cmp     dword ptr [rcx+5Ch], 1
0x140064b7f  jnz     short loc_140064B9B
0x140064b81  mov     [rsp+0B8h+var_67], dil
0x140064b86  mov     rdx, [rsi+2C8h]
0x140064b8d  mov     [rsp+0B8h+var_50], rdx
0x140064b92  test    rdx, rdx
0x140064b95  jnz     loc_140064FBE
0x140064b9b  mov     rcx, r14; Fobx
0x140064b9e  call    RxMarkFobxOnClose
0x140064ba3  mov     [r14+30h], r13
0x140064ba7  test    dil, dil
0x140064baa  jnz     short loc_140064BBE
0x140064bac  mov     rdx, r14; Fobx
0x140064baf  mov     rcx, rbx; RxContext
0x140064bb2  call    RxCloseAssociatedSrvOpen
0x140064bb7  mov     r12d, eax
0x140064bba  mov     [rsp+0B8h+var_5C], eax
0x140064bbe  cmp     dword ptr [rbx+368h], 2
0x140064bc5  jnz     short loc_140064BE2
0x140064bc7  mov     rcx, [r14+68h]
0x140064bcb  add     rcx, 8
0x140064bcf  call    RfsReleaseRundownProtection
0x140064bd4  mov     [rbx+370h], r13
0x140064bdb  mov     [rbx+368h], r13d
0x140064be2  test    dil, dil
0x140064be5  jnz     loc_140064D4C
0x140064beb  test    r14, r14
0x140064bee  jz      loc_140064D7D
0x140064bf4  mov     rdi, [rsp+0B8h+var_48]
0x140064bf9  cmp     byte ptr [rdi+4Dh], 3
0x140064bfd  jz      short loc_140064C16
0x140064bff  cmp     dword ptr [rsi+0C0h], 0
0x140064c06  jnz     short loc_140064C16
0x140064c08  mov     eax, [rsi+9Ch]
0x140064c0e  test    al, 1
0x140064c10  jnz     loc_140065166
0x140064c16  lea     rdi, WPP_GLOBAL_Control
0x140064c1d  mov     rcx, [rbx+0C8h]
0x140064c24  test    rcx, rcx
0x140064c27  jz      short loc_140064C43
0x140064c29  mov     r9d, [rbx+0C4h]
0x140064c30  mov     r8d, [rbx+0C0h]
0x140064c37  call    RdbssStatisticsEntryUpdateSocketCounters
0x140064c3c  mov     [rbx+0C8h], r13
0x140064c43  mov     rax, cs:RxFileSystemDeviceObject
0x140064c4a  cmp     qword ptr [rax+4E8h], 0
0x140064c52  jz      loc_140064CDF
0x140064c58  lea     r8, [r14+118h]
0x140064c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c66  cmp     rcx, rdi
0x140064c69  jz      short loc_140064C78
0x140064c6b  test    dword ptr [rcx+2Ch], 2000h
0x140064c72  jnz     loc_14006524C
0x140064c78  mov     [rsp+0B8h+var_60], r13d
0x140064c7d  mov     edi, r13d
0x140064c80  mov     [rsp+0B8h+var_60], r13d
0x140064c85  cmp     edi, 4
0x140064c88  jnb     short loc_140064CBF
0x140064c8a  mov     eax, edi
0x140064c8c  lea     rax, [r8+rax*8]
0x140064c90  mov     [rsp+0B8h+arg_8], rax
0x140064c98  mov     rcx, [rax]
0x140064c9b  test    rcx, rcx
0x140064c9e  jz      short loc_140064CB7
0x140064ca0  call    RdbssStatisticsEntryRelease
0x140064ca5  mov     rax, [rsp+0B8h+arg_8]
0x140064cad  mov     [rax], r13
0x140064cb0  lea     r8, [r14+118h]
0x140064cb7  inc     edi
0x140064cb9  mov     [rsp+0B8h+var_60], edi
0x140064cbd  jmp     short loc_140064C85
0x140064cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140064cc6  lea     rdi, WPP_GLOBAL_Control
0x140064ccd  cmp     rcx, rdi
0x140064cd0  jz      short loc_140064CDF
0x140064cd2  test    dword ptr [rcx+2Ch], 2000h
0x140064cd9  jnz     loc_14006527A
0x140064cdf  mov     edx, 2; LockHoldingState
0x140064ce4  mov     rcx, r14; Instance
0x140064ce7  call    RxDereference
0x140064cec  test    dword ptr [rsi+9Ch], 80040h
0x140064cf6  jz      short loc_140064D38
0x140064cf8  xor     r9d, r9d; ForceFinalize
0x140064cfb  xor     r8d, r8d; RecursiveFinalize
0x140064cfe  mov     rdx, rbx; RxContext
0x140064d01  mov     rcx, rsi; ThisFcb
0x140064d04  call    RxpDereferenceAndFinalizeNetFcb
0x140064d09  test    al, al
0x140064d0b  setz    [rsp+0B8h+var_68]
0x140064d10  mov     qword ptr [r15+18h], 0FFFFFFFFFFFFFFFFh
0x140064d18  mov     [r15+28h], r13
0x140064d1c  test    al, al
0x140064d1e  jnz     loc_14006529E
0x140064d24  mov     [rsp+0B8h+var_68], al
0x140064d28  mov     rdx, rsi; MrxFcb
0x140064d2b  mov     rcx, rbx; RxContext
0x140064d2e  call    __RxReleaseFcb
0x140064d33  jmp     loc_14006529E
0x140064d38  xor     edx, edx
0x140064d3a  mov     rcx, rsi; Instance
0x140064d3d  call    RxProcessFcbChangeBufferingStateRequestInternal
0x140064d42  jmp     short loc_140064CF8
0x140064d44  xor     dil, dil
0x140064d47  jmp     loc_140064BA7
0x140064d4c  mov     [rbx+0C8h], r13
0x140064d53  mov     rax, cs:RxFileSystemDeviceObject
0x140064d5a  cmp     qword ptr [rax+4E8h], 0
0x140064d62  jz      short loc_140064D70
0x140064d64  lea     rdx, [r14+118h]
0x140064d6b  call    RdbssStatisticsEntryArrayRelease
0x140064d70  mov     edx, 1; LockHoldingState
0x140064d75  mov     rcx, r14; Instance
0x140064d78  call    RxDereference
0x140064d7d  lea     rdi, WPP_GLOBAL_Control
0x140064d84  jmp     loc_140064CEC
0x140064d89  mov     eax, [rdx+64h]
0x140064d8c  cmp     [rdx+0E8h], eax
0x140064d92  jge     loc_140064B69
0x140064d98  test    dword ptr [rdi+38h], 400h
0x140064d9f  jnz     loc_140064B69
0x140064da5  call    RxDelayCloseSrvOpen
0x140064daa  mov     dil, 1
0x140064dad  mov     [rsp+0B8h+var_66], dil
0x140064db2  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 10h
0x140064db9  jz      short loc_140064DE3
0x140064dbb  lea     r8, [rbx+19Ch]
0x140064dc2  mov     [rsp+0B8h+var_90], r14
0x140064dc7  mov     r9, [rsp+0B8h+arg_8]
0x140064dcf  mov     [rsp+0B8h+BugCheckParameter4], r9
0x140064dd4  mov     r9, rsi
0x140064dd7  lea     rdx, RxDelayClose
0x140064dde  call    McTemplateK0ppp_EtwWriteTransfer
0x140064de3  mov     rcx, [rsp+0B8h+arg_8]
0x140064deb  jmp     loc_140064B6C
0x140064df0  add     eax, 0FFFF13E0h; switch 7 cases
0x140064df5  cmp     eax, 6
0x140064df8  jbe     loc_140064EE0
0x140064dfe  movzx   r8d, di; jumptable 0000000140064EF3 default case, case 60451
0x140064e02  mov     [rsp+0B8h+BugCheckParameter4], r13; BugCheckParameter4
0x140064e07  xor     r9d, r9d; BugCheckParameter3
0x140064e0a  mov     edx, 0C10E019Ch; BugCheckParameter1
0x140064e0f  mov     ecx, 27h ; '''; BugCheckCode
0x140064e14  call    cs:__imp_KeBugCheckEx
0x140064e20  mov     [rsp+0B8h+BugCheckParameter4], r13; BugCheckParameter4
0x140064e25  mov     r9d, 1; BugCheckParameter3
0x140064e2b  mov     r8, rsi; BugCheckParameter2
0x140064e2e  mov     edx, 0FCB003A5h; BugCheckParameter1
0x140064e33  mov     ecx, 27h ; '''; BugCheckCode
0x140064e38  call    cs:__imp_KeBugCheckEx
0x140064e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140064e4c  lea     rdi, WPP_GLOBAL_Control
0x140064e53  cmp     rcx, rdi
0x140064e56  jz      loc_14006529E
0x140064e5c  mov     edx, [rcx+2Ch]
0x140064e5f  test    dl, 8
0x140064e62  jz      loc_14006529E
0x140064e68  cmp     byte ptr [rcx+29h], 4
0x140064e6c  jb      loc_14006529E
0x140064e72  mov     edx, 0Ch
0x140064e77  mov     dword ptr [rsp+0B8h+BugCheckParameter4], eax
0x140064e7b  mov     r9, rsi
0x140064e7e  lea     r8, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids
0x140064e85  mov     rcx, [rcx+18h]
0x140064e89  call    WPP_SF_qD
0x140064e8e  jmp     loc_14006529E
0x140064e93  cmp     byte ptr [rcx+29h], 4
0x140064e97  jb      loc_140064AAB
0x140064e9d  mov     eax, [rsi+0C4h]
0x140064ea3  mov     [rsp+0B8h+var_78], eax
0x140064ea7  mov     eax, [rsi+0BCh]
0x140064ead  mov     dword ptr [rsp+0B8h+var_80], eax
0x140064eb1  mov     eax, [rsi+0B8h]
0x140064eb7  mov     dword ptr [rsp+0B8h+var_88], eax
0x140064ebb  mov     eax, [rsi+0C0h]
0x140064ec1  mov     dword ptr [rsp+0B8h+var_90], eax
0x140064ec5  mov     eax, [rsi+9Ch]
0x140064ecb  mov     dword ptr [rsp+0B8h+BugCheckParameter4], eax
0x140064ecf  mov     r9, rsi
0x140064ed2  mov     rcx, [rcx+18h]
0x140064ed6  call    WPP_SF_qDdddd
0x140064edb  jmp     loc_140064AAB
0x140064ee0  cdqe
0x140064ee2  lea     rdx, cs:140000000h
  ... truncated ...
```
