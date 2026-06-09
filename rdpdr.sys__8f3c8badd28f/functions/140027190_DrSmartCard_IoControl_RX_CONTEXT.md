# DrSmartCard::IoControl(_RX_CONTEXT *)

- ea: `0x140027190`
- end: `0x140027c05`
- name: `?IoControl@DrSmartCard@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `2677`
- prototype: `__int64 __fastcall(DrSmartCard *this, PRX_CONTEXT RxContext, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001660`
- `0x1400016a0`
- `0x140001830`
- `0x140001890`
- `0x140002284`
- `0x14000324c`
- `0x14000327c`
- `0x140005a1c`
- `0x140006560`
- `0x1400065c0`
- `0x1400068c0`
- `0x140011af8`
- `0x14001f298`
- `0x14001f310`
- `0x140024180`
- `0x140027190`
- `0x140027c10`
- `0x14002ac20`
- `0x14002be3c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002759d`
- `ntoskrnl!ExAllocatePool2` at `0x140027630`
- `ntoskrnl!ExAllocatePool2` at `0x14002759d`
- `ntoskrnl!ExAllocatePool2` at `0x140027630`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027342`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027342`
- `ntoskrnl!ProbeForRead` at `0x1400274e9`
- `ntoskrnl!ProbeForRead` at `0x1400274e9`
- `ntoskrnl!ProbeForWrite` at `0x1400274cc`
- `ntoskrnl!ProbeForWrite` at `0x1400274cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027b50`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027b50`
- `ntoskrnl!KeSetEvent` at `0x140027819`
- `ntoskrnl!KeSetEvent` at `0x140027819`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400276b3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400276b3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400276e2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400276e2`
- `ntoskrnl!KeClearEvent` at `0x1400275fc`
- `ntoskrnl!KeClearEvent` at `0x1400275fc`
- `rdbss!RxAssociateContextWithMid` at `0x1400278a1`
- `rdbss!RxAssociateContextWithMid` at `0x1400278a1`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x140027a4d`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x140027a4d`
- `rdbss!RxLowIoCompletion` at `0x1400277a4`
- `rdbss!RxLowIoCompletion` at `0x1400277a4`

## pseudocode

```c
__int64 __fastcall DrSmartCard::IoControl(DrSmartCard *this, PRX_CONTEXT RxContext, int a3)
{
  RefCount *v5; // rbx
  RefCount *v6; // rdi
  int v7; // esi
  __int64 v8; // r9
  SIZE_T v9; // rdx
  SIZE_T v10; // r12
  volatile void *v11; // rcx
  wchar_t *Buffer; // r13
  unsigned int v13; // eax
  unsigned __int64 v14; // rcx
  _DWORD *v15; // rsi
  size_t v16; // r12
  __int64 v17; // r9
  unsigned int StoredStatus; // r12d
  DrExchange *v20; // rsi
  __int64 Pool2; // rax
  __int64 v22; // r12
  struct IExchangeUser *v23; // rsi
  DrExchange *v24; // rax
  int v25; // ecx
  struct _RX_MID_ATLAS *v26; // rcx
  int v27; // r12d
  int Entry; // eax
  int v29; // ecx
  char RealDevice; // al
  PIRP CurrentIrp; // rax
  struct _FILE_OBJECT *FileObject; // rcx
  PIRP v33; // rax
  struct _FILE_OBJECT *v34; // rcx
  PDEVICE_OBJECT v35; // rcx
  RefCount *v36; // [rsp+48h] [rbp-50h] BYREF
  void *v37; // [rsp+50h] [rbp-48h]
  union _LARGE_INTEGER NewMid; // [rsp+A0h] [rbp+8h] BYREF
  PRX_CONTEXT v39; // [rsp+A8h] [rbp+10h]
  PVOID Object; // [rsp+B0h] [rbp+18h]
  RefCount *v41; // [rsp+B8h] [rbp+20h] BYREF

  v39 = RxContext;
  NewMid.QuadPart = (LONGLONG)this;
  v5 = (RefCount *)*((_QWORD *)this + 4);
  v41 = v5;
  if ( v5 )
    RefCount::AddRef(v5);
  v6 = *(RefCount **)&RxContext->pFobx->OffsetOfNextEaToReturn;
  v36 = v6;
  if ( v6 )
    RefCount::AddRef(v6);
  v7 = *((_DWORD *)&RxContext->9 + 35);
  v8 = *((unsigned int *)this + 14);
  if ( (_DWORD)v8 != 2 && v7 != 589828 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids, v8);
    if ( v6 )
      RefCount::Release(v6);
    if ( v5 )
      RefCount::Release(v5);
    return 3221225629LL;
  }
  if ( *((_DWORD *)this + 18) && v7 == 589828 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v36);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v41);
    return 3221225629LL;
  }
  v9 = *((unsigned int *)&RxContext->9 + 42);
  v10 = *((unsigned int *)&RxContext->9 + 43);
  v11 = (volatile void *)*((_QWORD *)&RxContext->9 + 19);
  Buffer = RxContext->Create.TransportName.Buffer;
  if ( RxContext->CurrentIrp->RequestorMode )
  {
    if ( (v7 & 1) != 0 && v11 && (_DWORD)v9 )
      ProbeForRead(v11, v9, 1u);
    if ( (v7 & 2) != 0 && Buffer && (_DWORD)v10 )
      ProbeForWrite(Buffer, v10, 1u);
  }
  if ( v7 != 589828 )
  {
    v13 = *((_DWORD *)&RxContext->9 + 42);
    v14 = v13 + 56;
    LODWORD(Object) = v14;
    if ( (unsigned int)v14 < v13 || (unsigned int)v14 < 0x38 )
    {
      v15 = 0;
      v37 = 0;
      v16 = (unsigned int)v14;
    }
    else
    {
      v16 = (unsigned int)v14;
      v15 = operator new(v14, v9, a3);
      v37 = v15;
    }
    if ( v15 )
    {
      memset(v15, 0, v16);
      *v15 = 1230128242;
      v15[1] = *((_DWORD *)this + 10);
      v15[2] = *((_DWORD *)v6 + 6);
      v15[4] = 14;
      v15[5] = *((unsigned __int8 *)&RxContext->9 + 176);
      v15[6] = *((_DWORD *)&RxContext->9 + 43);
      v15[7] = *((_DWORD *)&RxContext->9 + 42);
      v15[8] = *((_DWORD *)&RxContext->9 + 35);
      v17 = *((unsigned int *)&RxContext->9 + 42);
      if ( (_DWORD)v17 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids, v17);
        memmove(v15 + 14, *((const void **)&RxContext->9 + 19), *((unsigned int *)&RxContext->9 + 42));
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
      }
      StoredStatus = (*(__int64 (__fastcall **)(DrSmartCard *, PRX_CONTEXT, _DWORD *, _QWORD, bool, union _LARGE_INTEGER *, _DWORD))(*(_QWORD *)this + 24LL))(
                       this,
                       RxContext,
                       v15,
                       (unsigned int)Object,
                       ((__int64)RxContext->RdbssDbgExtension & 0x1000) == 0,
                       &g_IOTimeOut,
                       0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids, StoredStatus);
      ExFreePoolWithTag(v15, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids, 0);
      StoredStatus = -1073741670;
    }
    goto LABEL_16;
  }
  if ( *((_DWORD *)this + 14) != 2 )
  {
    v20 = 0;
    v41 = 0;
    NewMid.QuadPart = (LONGLONG)this;
    RefCount::AddRef(this);
    Pool2 = ExAllocatePool2(64, 72, 1128886852);
    if ( Pool2 && (v37 = (void *)DrIoContext::DrIoContext(Pool2, RxContext, &NewMid)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
      Object = &RxContext->PrefixClaim.NetRootType;
      KeClearEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType);
      v22 = *((_QWORD *)this + 4);
      v23 = (DrSmartCard *)((char *)this + 24);
      if ( !this )
        v23 = 0;
      LOWORD(NewMid.LowPart) = 0;
      v24 = (DrExchange *)ExAllocatePool2(64, 56, 2017817156);
      if ( v24 )
        v20 = DrExchange::DrExchange(v24, (struct DrExchangeManager *)(v22 + 688), v23, v37);
      else
        v20 = 0;
      v41 = v20;
      if ( v20 )
      {
        RefCount::AddRef(v20);
        ExAcquireFastMutex(&DrMutex);
        v26 = *(struct _RX_MID_ATLAS **)(v22 + 720);
        if ( v26 && RxAssociateContextWithMid(v26, v20, (PUSHORT)&NewMid) >= 0 )
        {
          v27 = 1;
          LODWORD(v39) = 1;
          *((_WORD *)v20 + 24) = NewMid.LowPart;
          RefCount::AddRef(v20);
        }
        else
        {
          v27 = 0;
          LODWORD(v39) = 0;
        }
        ExReleaseFastMutex(&DrMutex);
        if ( v27 )
        {
          RxContext->MRxContext[2] = v20;
          Entry = DoubleList::CreateEntry((DrSmartCard *)((char *)this + 80), (void *)*((unsigned __int16 *)v20 + 24));
          v29 = 0;
          if ( !Entry )
            v29 = -1073741670;
          StoredStatus = v29;
          if ( !Entry )
          {
            Object = &RxContext->PrefixClaim.NetRootType;
            v25 = (int)v39;
LABEL_65:
            if ( ((__int64)RxContext->RdbssDbgExtension & 0x1000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
                v25 = (int)v39;
              }
              if ( !v25 )
                DrDevice::CompleteRxContext(RxContext, StoredStatus, 0);
              StoredStatus = 259;
            }
            else if ( v25 )
            {
              NewMid.QuadPart = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
              NewMid.QuadPart = -6000000000LL;
              StoredStatus = KeWaitForSingleObject(Object, UserRequest, 0, 0, &NewMid);
              if ( StoredStatus == 258 )
              {
                RxContext->StoredStatus = 258;
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
                DrDevice::MarkTimedOut(v35, &v41);
              }
              else
              {
                StoredStatus = RxContext->StoredStatus;
              }
            }
            else
            {
              RxContext->StoredStatus = StoredStatus;
              RxContext->InformationToReturn = 0;
              if ( (*((_BYTE *)&RxContext->9 + 122) & 1) != 0 || !LOBYTE(RxContext->RealDevice) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
                KeSetEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, 0, 0);
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
                RealDevice = (char)RxContext->RealDevice;
                if ( RealDevice || StoredStatus )
                {
                  if ( RealDevice == 2 )
                  {
                    CurrentIrp = RxContext->CurrentIrp;
                    if ( CurrentIrp )
                    {
                      FileObject = CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject;
                      if ( FileObject )
                        DrRemoveOpenHandle(FileObject);
                    }
                  }
                }
                else
                {
                  v33 = RxContext->CurrentIrp;
                  if ( v33 )
                  {
                    v34 = v33->Tail.Overlay.CurrentStackLocation->FileObject;
                    if ( v34 )
                      DrAddOpenHandle(v34);
                  }
                }
                RxLowIoCompletion(RxContext);
              }
            }
            RefCount::Release(this);
            if ( v20 )
              RefCount::Release(v20);
            goto LABEL_16;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
          StoredStatus = RxSetMinirdrCancelRoutine(RxContext, DrDevice::MinirdrCancelRoutine);
          if ( StoredStatus == -1073741536 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
            DrDevice::MinirdrCancelRoutine(RxContext);
            StoredStatus = 0;
            v25 = (int)v39;
            goto LABEL_65;
          }
          v25 = (int)v39;
LABEL_78:
          Object = &RxContext->PrefixClaim.NetRootType;
          goto LABEL_65;
        }
        SmartPtr<VirtualChannel>::operator=(&v41, 0);
        v20 = v41;
      }
      else
      {
        LODWORD(v39) = 0;
      }
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v37 + 16LL))(v37, 1);
      v25 = (int)v39;
    }
    else
    {
      v25 = 0;
      LODWORD(v39) = 0;
    }
    StoredStatus = -1073741670;
    goto LABEL_78;
  }
  StoredStatus = 0;
LABEL_16:
  if ( v6 )
    RefCount::Release(v6);
  if ( v5 )
    RefCount::Release(v5);
  return StoredStatus;
}

```

## disassembly

```asm
0x140027190  mov     [rsp+arg_8], rdx
0x140027195  mov     [rsp+NewMid], rcx
0x14002719a  push    rbx
0x14002719b  push    rsi
0x14002719c  push    rdi
0x14002719d  push    r12
0x14002719f  push    r13
0x1400271a1  push    r14
0x1400271a3  push    r15
0x1400271a5  sub     rsp, 60h
0x1400271a9  mov     r14, rdx
0x1400271ac  mov     r15, rcx
0x1400271af  mov     rbx, [rcx+20h]
0x1400271b3  mov     [rsp+98h+arg_18], rbx
0x1400271bb  test    rbx, rbx
0x1400271be  jz      short loc_1400271C8
0x1400271c0  mov     rcx, rbx; this
0x1400271c3  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400271c8  mov     rdi, [rdx+40h]
0x1400271cc  mov     rdi, [rdi+40h]
0x1400271d0  mov     [rsp+98h+var_50], rdi
0x1400271d5  test    rdi, rdi
0x1400271d8  jz      short loc_1400271E2
0x1400271da  mov     rcx, rdi; this
0x1400271dd  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400271e2  mov     esi, [rdx+21Ch]
0x1400271e8  mov     r9d, [r15+38h]
0x1400271ec  cmp     r9d, 2
0x1400271f0  jnz     loc_140027457
0x1400271f6  cmp     dword ptr [r15+48h], 0
0x1400271fb  jnz     loc_140027900
0x140027201  mov     edx, [rdx+238h]; unsigned __int64
0x140027207  mov     r12d, [r14+23Ch]
0x14002720e  mov     rcx, [r14+228h]; Address
0x140027215  mov     r13, [r14+230h]
0x14002721c  mov     rax, [r14+28h]
0x140027220  cmp     byte ptr [rax+40h], 0
0x140027224  jnz     loc_1400274AA
0x14002722a  cmp     esi, 90004h
0x140027230  jz      loc_140027420
0x140027236  mov     eax, [r14+238h]
0x14002723d  lea     ecx, [rax+38h]; unsigned __int64
0x140027240  mov     dword ptr [rsp+98h+Object], ecx
0x140027247  cmp     ecx, eax
0x140027249  jnb     loc_140027436
0x14002724f  xor     r13d, r13d
0x140027252  mov     esi, r13d
0x140027255  mov     [rsp+98h+var_48], r13
0x14002725a  mov     r12d, ecx
0x14002725d  test    rsi, rsi
0x140027260  jz      loc_140027999
0x140027266  mov     r8, r12; Size
0x140027269  xor     edx, edx; Val
0x14002726b  mov     rcx, rsi; void *
0x14002726e  call    memset
0x140027273  mov     dword ptr [rsi], 49524472h
0x140027279  mov     eax, [r15+28h]
0x14002727d  mov     [rsi+4], eax
0x140027280  mov     eax, [rdi+18h]
0x140027283  mov     [rsi+8], eax
0x140027286  mov     dword ptr [rsi+10h], 0Eh
0x14002728d  movzx   eax, byte ptr [r14+240h]
0x140027295  mov     [rsi+14h], eax
0x140027298  mov     eax, [r14+23Ch]
0x14002729f  mov     [rsi+18h], eax
0x1400272a2  mov     eax, [r14+238h]
0x1400272a9  mov     [rsi+1Ch], eax
0x1400272ac  mov     eax, [r14+21Ch]
0x1400272b3  mov     [rsi+20h], eax
0x1400272b6  mov     r9d, [r14+238h]
0x1400272bd  test    r9d, r9d
0x1400272c0  jnz     loc_14002737C
0x1400272c6  mov     r12d, r13d
0x1400272c9  lea     rax, WPP_GLOBAL_Control
0x1400272d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400272d7  cmp     rcx, rax
0x1400272da  jnz     loc_140027975
0x1400272e0  test    r12d, r12d
0x1400272e3  js      short loc_14002733D
0x1400272e5  mov     rax, [r15]
0x1400272e8  mov     ecx, [r14+78h]
0x1400272ec  shr     ecx, 0Ch
0x1400272ef  not     cl
0x1400272f1  and     cl, 1
0x1400272f4  mov     rax, [rax+18h]
0x1400272f8  mov     [rsp+98h+var_68], r13d
0x1400272fd  lea     rdx, ?g_IOTimeOut@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_IOTimeOut
0x140027304  mov     [rsp+98h+var_70], rdx
0x140027309  mov     byte ptr [rsp+98h+Timeout], cl
0x14002730d  mov     r9d, dword ptr [rsp+98h+Object]
0x140027315  mov     r8, rsi
0x140027318  mov     rdx, r14
0x14002731b  mov     rcx, r15
0x14002731e  call    _guard_dispatch_icall
0x140027323  mov     r12d, eax
0x140027326  mov     rcx, cs:WPP_GLOBAL_Control
0x14002732d  lea     rax, WPP_GLOBAL_Control
0x140027334  cmp     rcx, rax
0x140027337  jnz     loc_14002754B
0x14002733d  xor     edx, edx; Tag
0x14002733f  mov     rcx, rsi; P
0x140027342  call    cs:__imp_ExFreePoolWithTag
0x140027349  nop     dword ptr [rax+rax+00h]
0x14002734e  test    rdi, rdi
0x140027351  jz      short loc_14002735B
0x140027353  mov     rcx, rdi; this
0x140027356  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002735b  test    rbx, rbx
0x14002735e  jz      short loc_140027368
0x140027360  mov     rcx, rbx; this
0x140027363  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140027368  mov     eax, r12d
0x14002736b  add     rsp, 60h
0x14002736f  pop     r15
0x140027371  pop     r14
0x140027373  pop     r13
0x140027375  pop     r12
0x140027377  pop     rdi
0x140027378  pop     rsi
0x140027379  pop     rbx
0x14002737a  retn
0x14002737c  lea     rax, WPP_GLOBAL_Control
0x140027383  mov     rcx, cs:WPP_GLOBAL_Control
0x14002738a  cmp     rcx, rax
0x14002738d  jz      short loc_140027399
0x14002738f  cmp     byte ptr [rcx+29h], 4
0x140027393  jnb     loc_14002795B
0x140027399  mov     r8d, [r14+238h]; Size
0x1400273a0  lea     rcx, [rsi+38h]; void *
0x1400273a4  mov     rdx, [r14+228h]; Src
0x1400273ab  call    memmove
0x1400273b0  mov     r12d, r13d
0x1400273b3  mov     [rsp+98h+var_58], r13d
0x1400273b8  jmp     loc_1400272E0
0x1400273bd  lea     rax, WPP_GLOBAL_Control
0x1400273c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400273cb  cmp     rcx, rax
0x1400273ce  jz      short loc_1400273EB
0x1400273d0  cmp     byte ptr [rcx+29h], 2
0x1400273d4  jb      short loc_1400273EB
0x1400273d6  mov     edx, 11h
0x1400273db  lea     r8, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids
0x1400273e2  mov     rcx, [rcx+18h]
0x1400273e6  call    WPP_SF_
0x1400273eb  mov     r12d, 0C000000Dh
0x1400273f1  mov     [rsp+98h+var_58], r12d
0x1400273f6  xor     r13d, r13d
0x1400273f9  mov     r15, [rsp+98h+NewMid]
0x140027401  mov     r14, [rsp+98h+arg_8]
0x140027409  mov     rbx, [rsp+98h+arg_18]
0x140027411  mov     rdi, [rsp+98h+var_50]
0x140027416  mov     rsi, [rsp+98h+var_48]
0x14002741b  jmp     loc_1400272E0
0x140027420  xor     r13d, r13d
0x140027423  cmp     dword ptr [r15+38h], 2
0x140027428  jnz     loc_140027572
0x14002742e  mov     r12d, r13d
0x140027431  jmp     loc_14002734E
0x140027436  cmp     ecx, 38h ; '8'
0x140027439  jb      loc_14002724F
0x14002743f  mov     r12d, ecx
0x140027442  call    ??2@YAPEAX_K0H@Z; operator new(unsigned __int64,unsigned __int64,int)
0x140027447  mov     rsi, rax
0x14002744a  mov     [rsp+98h+var_48], rax
0x14002744f  xor     r13d, r13d
0x140027452  jmp     loc_14002725D
0x140027457  cmp     esi, 90004h
0x14002745d  jz      loc_1400271F6
0x140027463  lea     rax, WPP_GLOBAL_Control
0x14002746a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027471  cmp     rcx, rax
0x140027474  jnz     loc_1400278DC
0x14002747a  test    rdi, rdi
0x14002747d  jz      short loc_140027487
0x14002747f  mov     rcx, rdi; this
0x140027482  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140027487  test    rbx, rbx
0x14002748a  jz      short loc_140027494
0x14002748c  mov     rcx, rbx; this
0x14002748f  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140027494  mov     eax, 0C000009Dh
0x140027499  add     rsp, 60h
0x14002749d  pop     r15
0x14002749f  pop     r14
0x1400274a1  pop     r13
0x1400274a3  pop     r12
0x1400274a5  pop     rdi
0x1400274a6  pop     rsi
0x1400274a7  pop     rbx
0x1400274a8  retn
0x1400274aa  test    sil, 1
0x1400274ae  jnz     short loc_1400274DA
0x1400274b0  test    sil, 2
0x1400274b4  jz      short loc_1400274F7
0x1400274b6  test    r13, r13
0x1400274b9  jz      short loc_1400274F7
0x1400274bb  test    r12d, r12d
0x1400274be  jz      short loc_1400274F7
0x1400274c0  mov     rdx, r12; Length
0x1400274c3  mov     r8d, 1; Alignment
0x1400274c9  mov     rcx, r13; Address
0x1400274cc  call    cs:__imp_ProbeForWrite
0x1400274d3  nop     dword ptr [rax+rax+00h]
0x1400274d8  jmp     short loc_1400274F7
0x1400274da  test    rcx, rcx
0x1400274dd  jz      short loc_1400274B0
0x1400274df  test    edx, edx
0x1400274e1  jz      short loc_1400274B0
0x1400274e3  mov     r8d, 1; Alignment
0x1400274e9  call    cs:__imp_ProbeForRead
0x1400274f0  nop     dword ptr [rax+rax+00h]
0x1400274f5  jmp     short loc_1400274B0
0x1400274f7  jmp     loc_14002722A
0x1400274fc  lea     rax, WPP_GLOBAL_Control
0x140027503  mov     rcx, cs:WPP_GLOBAL_Control
0x14002750a  cmp     rcx, rax
0x14002750d  jz      short loc_14002752A
0x14002750f  cmp     byte ptr [rcx+29h], 2
0x140027513  jb      short loc_14002752A
0x140027515  mov     edx, 0Fh
0x14002751a  lea     r8, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids
0x140027521  mov     rcx, [rcx+18h]
0x140027525  call    WPP_SF_
0x14002752a  lea     rcx, [rsp+98h+var_50]
0x14002752f  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140027534  lea     rcx, [rsp+98h+arg_18]
0x14002753c  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140027541  mov     eax, 0C000000Dh
0x140027546  jmp     loc_14002736B
0x14002754b  cmp     byte ptr [rcx+29h], 4
0x14002754f  jb      loc_14002733D
0x140027555  mov     edx, 13h
0x14002755a  mov     r9d, r12d
0x14002755d  lea     r8, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids
0x140027564  mov     rcx, [rcx+18h]
0x140027568  call    WPP_SF_d
0x14002756d  jmp     loc_14002733D
0x140027572  mov     rsi, r13
0x140027575  mov     [rsp+98h+arg_18], r13
0x14002757d  mov     [rsp+98h+NewMid], r15
0x140027585  mov     rcx, r15; this
0x140027588  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002758d  mov     edx, 48h ; 'H'
0x140027592  mov     ecx, 40h ; '@'
0x140027597  mov     r8d, 43497244h
0x14002759d  call    cs:__imp_ExAllocatePool2
0x1400275a4  nop     dword ptr [rax+rax+00h]
0x1400275a9  test    rax, rax
0x1400275ac  jz      loc_1400277D6
0x1400275b2  lea     r8, [rsp+98h+NewMid]
0x1400275ba  mov     rdx, r14
0x1400275bd  mov     rcx, rax
0x1400275c0  call    ??0DrIoContext@@QEAA@PEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z; DrIoContext::DrIoContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)
0x1400275c5  mov     [rsp+98h+var_48], rax
0x1400275ca  test    rax, rax
0x1400275cd  jz      loc_1400277D6
0x1400275d3  lea     rax, WPP_GLOBAL_Control
0x1400275da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400275e1  cmp     rcx, rax
0x1400275e4  jnz     loc_1400279D5
0x1400275ea  lea     rax, [r14+180h]
0x1400275f1  mov     [rsp+98h+Object], rax
0x1400275f9  mov     rcx, rax; Event
0x1400275fc  call    cs:__imp_KeClearEvent
0x140027603  nop     dword ptr [rax+rax+00h]
0x140027608  mov     r12, [r15+20h]
0x14002760c  lea     rsi, [r15+18h]
0x140027610  test    r15, r15
0x140027613  cmovz   rsi, r13
0x140027617  mov     word ptr [rsp+98h+NewMid], r13w
0x140027620  mov     edx, 38h ; '8'
0x140027625  mov     ecx, 40h ; '@'
0x14002762a  mov     r8d, 78457244h
0x140027630  call    cs:__imp_ExAllocatePool2
0x140027637  nop     dword ptr [rax+rax+00h]
0x14002763c  test    rax, rax
0x14002763f  jz      loc_1400277CE
0x140027645  mov     r9, [rsp+98h+var_48]; void *
0x14002764a  mov     r8, rsi; struct IExchangeUser *
0x14002764d  lea     rdx, [r12+2B0h]; struct DrExchangeManager *
0x140027655  mov     rcx, rax; this
0x140027658  call    ??0DrExchange@@AEAA@PEAVDrExchangeManager@@PEAVIExchangeUser@@PEAX@Z; DrExchange::DrExchange(DrExchangeManager *,IExchangeUser *,void *)
0x14002765d  mov     rsi, rax
0x140027660  mov     [rsp+98h+arg_18], rsi
0x140027668  test    rsi, rsi
0x14002766b  jz      short loc_14002767A
0x14002766d  mov     rcx, rsi; this
0x140027670  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140027675  test    rsi, rsi
0x140027678  jnz     short loc_1400276AC
0x14002767a  mov     r12d, r13d
0x14002767d  mov     dword ptr [rsp+98h+arg_8], r13d
0x140027685  test    r12d, r12d
0x140027688  jnz     short loc_1400276F7
0x14002768a  mov     rcx, [rsp+98h+var_48]
0x14002768f  mov     rax, [rcx]
0x140027692  mov     rax, [rax+10h]
0x140027696  mov     edx, 1
0x14002769b  call    _guard_dispatch_icall
0x1400276a0  mov     ecx, dword ptr [rsp+98h+arg_8]
  ... truncated ...
```
