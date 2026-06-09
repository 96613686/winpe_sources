# CDiskPnpMonitor::Shutdown(void)

- ea: `0x18001ac20`
- end: `0x18001ae1b`
- name: `?Shutdown@CDiskPnpMonitor@@QEAAXXZ`
- size: `507`
- prototype: `void __fastcall(CDiskPnpMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016d24`

## callees

- `0x180006470`
- `0x180006874`
- `0x180009088`
- `0x1800137d4`
- `0x180016220`
- `0x180016364`
- `0x18001ac20`
- `0x18001b5ac`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x18001adde`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x18001adde`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001acd6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001acd6`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001ac81`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001ad2e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001ac81`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001ad2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDiskPnpMonitor::Shutdown(CDiskPnpMonitor *this)
{
  __int64 v2; // rax
  PVOID *v3; // rcx
  _QWORD *v4; // rdi
  _QWORD *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
      *((_QWORD *)this + 30));
  }
  v2 = CHandleT<void *,NtHandleTrait>::Detach((__int64 *)this + 30);
  CM_Unregister_Notification(v2);
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
      *((_QWORD *)this + 30));
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = (_QWORD *)*((_QWORD *)this + 15);
  while ( v4 )
  {
    v5 = v4;
    v4 = (_QWORD *)*v4;
    v10 = (RTL_SRWLOCK *)(v5[2] + 80LL);
    AcquireSRWLockExclusive(v10);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v10);
    v7 = v5[2];
    if ( !*(_QWORD *)(v7 + 88) )
      goto LABEL_19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v6, v7, *(_QWORD *)(v7 + 88));
    }
    v8 = CHandleT<void *,NtHandleTrait>::Detach((__int64 *)(v5[2] + 88LL));
    CM_Unregister_Notification(v8);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v9, v5[2], *(_QWORD *)(v5[2] + 88LL));
LABEL_19:
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
    WPP_SF_(v3[2], 19, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<CDeviceNotifyData *>>::RemoveAll((__int64)this + 168);
  ATL::CAtlList<ATL::CAutoPtr<CDeviceNotifyData>,ATL::CAutoPtrElementTraits<CDeviceNotifyData>>::RemoveAll((__int64)this + 120);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids);
  }
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 13), 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids);
  }
}

```

## disassembly

```asm
0x18001ac20  push    rbx
0x18001ac22  push    rsi
0x18001ac23  push    rdi
0x18001ac24  push    r12
0x18001ac26  push    r13
0x18001ac28  push    r14
0x18001ac2a  sub     rsp, 38h
0x18001ac2e  mov     rbx, rcx
0x18001ac31  lea     r12, WPP_GLOBAL_Control
0x18001ac38  lea     r13, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001ac3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac46  cmp     rcx, r12
0x18001ac49  jz      short loc_18001AC6F
0x18001ac4b  test    byte ptr [rcx+1Ch], 1
0x18001ac4f  jz      short loc_18001AC6F
0x18001ac51  cmp     byte ptr [rcx+19h], 4
0x18001ac55  jb      short loc_18001AC6F
0x18001ac57  mov     edx, 0Fh
0x18001ac5c  mov     r9, [rbx+0F0h]
0x18001ac63  mov     r8, r13
0x18001ac66  mov     rcx, [rcx+10h]
0x18001ac6a  call    WPP_SF_q
0x18001ac6f  lea     rdi, [rbx+0F0h]
0x18001ac76  mov     rcx, rdi
0x18001ac79  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18001ac7e  mov     rcx, rax
0x18001ac81  call    cs:__imp_CM_Unregister_Notification
0x18001ac87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac8e  cmp     rcx, r12
0x18001ac91  jz      short loc_18001ACBA
0x18001ac93  test    byte ptr [rcx+1Ch], 1
0x18001ac97  jz      short loc_18001ACBA
0x18001ac99  cmp     byte ptr [rcx+19h], 4
0x18001ac9d  jb      short loc_18001ACBA
0x18001ac9f  mov     edx, 10h
0x18001aca4  mov     r9, [rdi]
0x18001aca7  mov     r8, r13
0x18001acaa  mov     rcx, [rcx+10h]
0x18001acae  call    WPP_SF_q
0x18001acb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acba  mov     rdi, [rbx+78h]
0x18001acbe  jmp     loc_18001AD6E
0x18001acc3  lea     rsi, [rdi]
0x18001acc6  mov     rdi, [rdi]
0x18001acc9  mov     rcx, [rsi+10h]
0x18001accd  add     rcx, 50h ; 'P'; SRWLock
0x18001acd1  mov     [rsp+68h+arg_0], rcx
0x18001acd6  call    cs:__imp_AcquireSRWLockExclusive
0x18001acdc  lea     rcx, [rsp+68h+arg_0]; this
0x18001ace1  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x18001ace6  mov     r9, [rsi+10h]
0x18001acea  mov     rax, [r9+58h]
0x18001acee  test    rax, rax
0x18001acf1  jz      short loc_18001AD67
0x18001acf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acfa  cmp     rcx, r12
0x18001acfd  jz      short loc_18001AD1E
0x18001acff  test    byte ptr [rcx+1Ch], 1
0x18001ad03  jz      short loc_18001AD1E
0x18001ad05  cmp     byte ptr [rcx+19h], 4
0x18001ad09  jb      short loc_18001AD1E
0x18001ad0b  mov     edx, 11h
0x18001ad10  mov     [rsp+68h+var_48], rax
0x18001ad15  mov     rcx, [rcx+10h]
0x18001ad19  call    WPP_SF_qq
0x18001ad1e  mov     rcx, [rsi+10h]
0x18001ad22  add     rcx, 58h ; 'X'
0x18001ad26  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18001ad2b  mov     rcx, rax
0x18001ad2e  call    cs:__imp_CM_Unregister_Notification
0x18001ad34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad3b  cmp     rcx, r12
0x18001ad3e  jz      short loc_18001AD6E
0x18001ad40  test    byte ptr [rcx+1Ch], 1
0x18001ad44  jz      short loc_18001AD6E
0x18001ad46  cmp     byte ptr [rcx+19h], 4
0x18001ad4a  jb      short loc_18001AD6E
0x18001ad4c  mov     r9, [rsi+10h]
0x18001ad50  mov     edx, 12h
0x18001ad55  mov     rax, [r9+58h]
0x18001ad59  mov     [rsp+68h+var_48], rax
0x18001ad5e  mov     rcx, [rcx+10h]
0x18001ad62  call    WPP_SF_qq
0x18001ad67  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad6e  test    rdi, rdi
0x18001ad71  jnz     loc_18001ACC3
0x18001ad77  cmp     rcx, r12
0x18001ad7a  jz      short loc_18001AD97
0x18001ad7c  test    byte ptr [rcx+1Ch], 1
0x18001ad80  jz      short loc_18001AD97
0x18001ad82  cmp     byte ptr [rcx+19h], 4
0x18001ad86  jb      short loc_18001AD97
0x18001ad88  lea     edx, [rdi+13h]
0x18001ad8b  mov     r8, r13
0x18001ad8e  mov     rcx, [rcx+10h]
0x18001ad92  call    WPP_SF_
0x18001ad97  lea     rcx, [rbx+0A8h]
0x18001ad9e  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceNotifyData@@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@PEAVCDeviceNotifyData@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::RemoveAll(void)
0x18001ada3  lea     rcx, [rbx+78h]
0x18001ada7  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCDeviceNotifyData@@@ATL@@V?$CAutoPtrElementTraits@VCDeviceNotifyData@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CDeviceNotifyData>,ATL::CAutoPtrElementTraits<CDeviceNotifyData>>::RemoveAll(void)
0x18001adac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adb3  cmp     rcx, r12
0x18001adb6  jz      short loc_18001ADD5
0x18001adb8  test    byte ptr [rcx+1Ch], 1
0x18001adbc  jz      short loc_18001ADD5
0x18001adbe  cmp     byte ptr [rcx+19h], 4
0x18001adc2  jb      short loc_18001ADD5
0x18001adc4  mov     edx, 14h
0x18001adc9  mov     r8, r13
0x18001adcc  mov     rcx, [rcx+10h]
0x18001add0  call    WPP_SF_
0x18001add5  xor     r8d, r8d; pvCleanupContext
0x18001add8  xor     edx, edx; fCancelPendingCallbacks
0x18001adda  mov     rcx, [rbx+68h]; ptpcg
0x18001adde  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001ade4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adeb  cmp     rcx, r12
0x18001adee  jz      short loc_18001AE0D
0x18001adf0  test    byte ptr [rcx+1Ch], 1
0x18001adf4  jz      short loc_18001AE0D
0x18001adf6  cmp     byte ptr [rcx+19h], 4
0x18001adfa  jb      short loc_18001AE0D
0x18001adfc  mov     edx, 15h
0x18001ae01  mov     r8, r13
0x18001ae04  mov     rcx, [rcx+10h]
0x18001ae08  call    WPP_SF_
0x18001ae0d  add     rsp, 38h
0x18001ae11  pop     r14
0x18001ae13  pop     r13
0x18001ae15  pop     r12
0x18001ae17  pop     rdi
0x18001ae18  pop     rsi
0x18001ae19  pop     rbx
0x18001ae1a  retn
```
