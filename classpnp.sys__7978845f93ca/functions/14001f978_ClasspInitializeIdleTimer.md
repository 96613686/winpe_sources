# ClasspInitializeIdleTimer

- ea: `0x14001f978`
- end: `0x14001fb4f`
- name: `ClasspInitializeIdleTimer`
- size: `471`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1400579b4`

## callees

- `0x14001f978`
- `0x14001fc38`
- `0x14005be14`
- `0x14005f690`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14001faa6`
- `ntoskrnl!KeInitializeDpc` at `0x14001faa6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fa76`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fa76`
- `ntoskrnl!KeInitializeTimer` at `0x14001fa89`
- `ntoskrnl!KeInitializeTimer` at `0x14001fa89`

## pseudocode

```c
__int64 __fastcall ClasspInitializeIdleTimer(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rbx
  __int64 v3; // rdx
  __int64 result; // rax
  __int64 i; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  ULONG v8; // [rsp+40h] [rbp+20h] BYREF
  ULONG ParameterValue; // [rsp+48h] [rbp+28h] BYREF
  unsigned int v10; // [rsp+50h] [rbp+30h] BYREF
  ULONG v11; // [rsp+58h] [rbp+38h] BYREF

  PrivateFdoData = FdoExtension->PrivateFdoData;
  v8 = 12;
  ParameterValue = 1;
  v10 = 0;
  v11 = 1;
  ClassGetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"IdlePrioritySupported", &ParameterValue);
  if ( ParameterValue )
  {
    ClassGetServiceParameter((__int64)FdoExtension, v3, &v10);
    ClassGetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"IdleInterval", &v8);
    if ( v8 - 12 > 0xFFF3 )
      v8 = 12;
    _InterlockedOr((volatile signed __int32 *)&PrivateFdoData->FdoDataFlags, 1u);
    if ( v10 )
      _InterlockedOr((volatile signed __int32 *)&PrivateFdoData->FdoDataFlags, 2u);
    else
      _InterlockedAnd((volatile signed __int32 *)&PrivateFdoData->FdoDataFlags, 0xFFFFFFFD);
    KeInitializeSpinLock(&PrivateFdoData->IdleListLock);
    KeInitializeTimer(&PrivateFdoData->IdleTimer);
    KeInitializeDpc(&PrivateFdoData->IdleDpc, ClasspIdleTimerDpc, FdoExtension);
    for ( i = 0; i != 2; ++i )
    {
      v6 = (__int64)&PrivateFdoData->IdleIrpList[i];
      PrivateFdoData->IdleIrpList[i].Blink = (_LIST_ENTRY *)v6;
      v7 = 2 * (i + 230);
      *((_QWORD *)&PrivateFdoData->SmrReadCapacityMutex.Header.Lock + v7) = v6;
    }
    PrivateFdoData->IdleIoCount = 0;
    PrivateFdoData->StarvationDuration = 500;
    PrivateFdoData->IdleInterval = v8;
    PrivateFdoData->ActiveIdleIoCount = 0;
    ClassGetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"IdleOutstandingIoMax", &v11);
    result = v11;
    if ( v11 <= 1 )
      result = 1;
    if ( (unsigned int)result >= 0xFFFF )
      result = 0xFFFF;
    PrivateFdoData->IdleActiveIoMax = result;
  }
  else
  {
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x80u) != 0LL && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        result = WPP_SF_q(
                   WPP_GLOBAL_Control->AttachedDevice,
                   10,
                   WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids,
                   FdoExtension);
    }
    _InterlockedAnd((volatile signed __int32 *)&PrivateFdoData->FdoDataFlags, 0xFFFFFFFC);
    PrivateFdoData->IdleIoCount = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001f978  push    rbp
0x14001f97a  push    rbx
0x14001f97b  push    rdi
0x14001f97c  mov     rbp, rsp
0x14001f97f  sub     rsp, 20h
0x14001f983  mov     rbx, [rcx+478h]
0x14001f98a  lea     r9, [rbp+ParameterValue]; ParameterValue
0x14001f98e  lea     r8, aIdleprioritysu; "IdlePrioritySupported"
0x14001f995  mov     [rbp+arg_0], 0Ch
0x14001f99c  lea     rdx, SubkeyName; "Classpnp"
0x14001f9a3  mov     [rbp+ParameterValue], 1
0x14001f9aa  mov     rdi, rcx
0x14001f9ad  mov     [rbp+arg_10], 0
0x14001f9b4  mov     [rbp+arg_18], 1
0x14001f9bb  call    ClassGetDeviceParameter
0x14001f9c0  cmp     [rbp+ParameterValue], 0
0x14001f9c4  jnz     short loc_14001FA15
0x14001f9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9cd  lea     rax, WPP_GLOBAL_Control
0x14001f9d4  cmp     rcx, rax
0x14001f9d7  jz      short loc_14001F9FE
0x14001f9d9  mov     eax, [rcx+2Ch]
0x14001f9dc  test    al, al
0x14001f9de  jns     short loc_14001F9FE
0x14001f9e0  cmp     byte ptr [rcx+29h], 4
0x14001f9e4  jb      short loc_14001F9FE
0x14001f9e6  mov     rcx, [rcx+18h]
0x14001f9ea  lea     r8, WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids
0x14001f9f1  mov     edx, 0Ah
0x14001f9f6  mov     r9, rdi
0x14001f9f9  call    WPP_SF_q
0x14001f9fe  lock and dword ptr [rbx+298h], 0FFFFFFFCh
0x14001fa06  mov     dword ptr [rbx+0F18h], 0
0x14001fa10  jmp     loc_14001FB46
0x14001fa15  lea     r8, [rbp+arg_10]
0x14001fa19  mov     rcx, rdi
0x14001fa1c  call    ClassGetServiceParameter
0x14001fa21  lea     r9, [rbp+arg_0]; ParameterValue
0x14001fa25  mov     rcx, rdi; FdoExtension
0x14001fa28  lea     r8, aIdleinterval; "IdleInterval"
0x14001fa2f  lea     rdx, SubkeyName; "Classpnp"
0x14001fa36  call    ClassGetDeviceParameter
0x14001fa3b  mov     eax, [rbp+arg_0]
0x14001fa3e  add     eax, 0FFFFFFF4h
0x14001fa41  cmp     eax, 0FFF3h
0x14001fa46  jbe     short loc_14001FA4F
0x14001fa48  mov     [rbp+arg_0], 0Ch
0x14001fa4f  lock or dword ptr [rbx+298h], 1
0x14001fa57  cmp     [rbp+arg_10], 0
0x14001fa5b  jz      short loc_14001FA67
0x14001fa5d  lock or dword ptr [rbx+298h], 2
0x14001fa65  jmp     short loc_14001FA6F
0x14001fa67  lock and dword ptr [rbx+298h], 0FFFFFFFDh
0x14001fa6f  lea     rcx, [rbx+0E58h]; SpinLock
0x14001fa76  call    cs:__imp_KeInitializeSpinLock
0x14001fa7d  nop     dword ptr [rax+rax+00h]
0x14001fa82  lea     rcx, [rbx+0E90h]; Timer
0x14001fa89  call    cs:__imp_KeInitializeTimer
0x14001fa90  nop     dword ptr [rax+rax+00h]
0x14001fa95  lea     rcx, [rbx+0ED0h]; Dpc
0x14001fa9c  mov     r8, rdi; DeferredContext
0x14001fa9f  lea     rdx, ClasspIdleTimerDpc; DeferredRoutine
0x14001faa6  call    cs:__imp_KeInitializeDpc
0x14001faad  nop     dword ptr [rax+rax+00h]
0x14001fab2  xor     r8d, r8d
0x14001fab5  mov     rax, r8
0x14001fab8  lea     rcx, [rbx+0E60h]
0x14001fabf  shl     rax, 4
0x14001fac3  add     rcx, rax
0x14001fac6  mov     [rax+rbx+0E68h], rcx
0x14001face  lea     rax, [r8+0E6h]
0x14001fad5  add     rax, rax
0x14001fad8  inc     r8
0x14001fadb  mov     [rbx+rax*8], rcx
0x14001fadf  cmp     r8, 2
0x14001fae3  jnz     short loc_14001FAB5
0x14001fae5  mov     dword ptr [rbx+0F18h], 0
0x14001faef  lea     r9, [rbp+arg_18]; ParameterValue
0x14001faf3  mov     word ptr [rbx+0F14h], 1F4h
0x14001fafc  lea     r8, aIdleoutstandin; "IdleOutstandingIoMax"
0x14001fb03  movzx   eax, word ptr [rbp+arg_0]
0x14001fb07  lea     rdx, SubkeyName; "Classpnp"
0x14001fb0e  mov     rcx, rdi; FdoExtension
0x14001fb11  mov     [rbx+0F10h], ax
0x14001fb18  mov     dword ptr [rbx+0F28h], 0
0x14001fb22  call    ClassGetDeviceParameter
0x14001fb27  mov     eax, [rbp+arg_18]
0x14001fb2a  cmp     eax, 1
0x14001fb2d  ja      short loc_14001FB34
0x14001fb2f  mov     eax, 1
0x14001fb34  mov     ecx, 0FFFFh
0x14001fb39  cmp     eax, ecx
0x14001fb3b  jb      short loc_14001FB3F
0x14001fb3d  mov     eax, ecx
0x14001fb3f  mov     [rbx+0F12h], ax
0x14001fb46  add     rsp, 20h
0x14001fb4a  pop     rdi
0x14001fb4b  pop     rbx
0x14001fb4c  pop     rbp
0x14001fb4d  retn
```
