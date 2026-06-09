# PmRemoveHelper(_DEVICE_EXTENSION *)

- ea: `0x14000743c`
- end: `0x14000766d`
- name: `?PmRemoveHelper@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `561`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022988`
- `0x14002579c`

## callees

- `0x14000743c`
- `0x14000a014`
- `0x14000a4d4`
- `0x14000d794`
- `0x140024ac0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400074ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000750b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007569`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000761c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400074ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000750b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007569`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000761c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400075f0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400075f0`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140007598`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140007598`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000747b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400074c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000753a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000747b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400074c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000753a`
- `ntoskrnl!KeReleaseMutex` at `0x14000754c`
- `ntoskrnl!KeReleaseMutex` at `0x140007583`
- `ntoskrnl!KeReleaseMutex` at `0x14000764e`
- `ntoskrnl!KeReleaseMutex` at `0x14000754c`
- `ntoskrnl!KeReleaseMutex` at `0x140007583`
- `ntoskrnl!KeReleaseMutex` at `0x14000764e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400075dd`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400075dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000745c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000751a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000745c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000751a`

## string_xrefs

- `0x140007499`: `PmRemoveHelper`

## pseudocode

```c
void __fastcall PmRemoveHelper(struct _DEVICE_EXTENSION *a1)
{
  KSPIN_LOCK *v1; // rsi
  char *DeviceExtension; // r14
  KIRQL v4; // al
  int v5; // r8d
  KIRQL v6; // bp
  int v7; // ebx
  KIRQL v8; // al
  __int64 i; // rsi
  struct _UNICODE_STRING *v10; // rbx
  _QWORD *v11; // rdi
  __int64 v12; // rdx
  _QWORD *v13; // rax

  v1 = (KSPIN_LOCK *)((char *)a1 + 112);
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  v6 = v4;
  if ( (*((_DWORD *)a1 + 129) & 0x20) != 0 )
  {
    KeReleaseSpinLock(v1, v4);
  }
  else
  {
    *((_DWORD *)a1 + 129) |= 0x20u;
    *((_DWORD *)a1 + 129) &= ~1u;
    v7 = PmQueueNotificationWorkItem(a1, "PmRemoveHelper", v5);
    KeReleaseSpinLock(v1, v6);
    if ( v7 >= 0 )
      KeWaitForSingleObject((char *)a1 + 824, Executive, 0, 0, 0);
    KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
    v8 = KeAcquireSpinLockRaiseToDpc(v1);
    *((_DWORD *)a1 + 129) &= ~2u;
    KeReleaseSpinLock(v1, v8);
    KeReleaseMutex((PRKMUTEX)a1 + 1, 0);
    KeWaitForSingleObject(DeviceExtension + 104, Executive, 0, 0, 0);
    PmRemoveIds(a1);
    KeReleaseMutex((PRKMUTEX)(DeviceExtension + 104), 0);
    IoWMIRegistrationControl(*((PDEVICE_OBJECT *)a1 + 1), 2u);
    PmWmiCounterDisable((struct _PERF_COUNTER_CONTEXT **)a1 + 90, 1u, 0);
    PmPowerCounterDisable(a1);
    for ( i = 0; i != 2; ++i )
    {
      if ( *((_QWORD *)a1 + 2 * i + 61) )
      {
        v10 = (struct _UNICODE_STRING *)((char *)a1 + 16 * i);
        IoSetDeviceInterfaceState(v10 + 30, 0);
        RtlFreeUnicodeString(v10 + 30);
      }
    }
    *((_DWORD *)a1 + 128) = 2;
    KeWaitForSingleObject(DeviceExtension + 16, Executive, 0, 0, 0);
    v11 = (_QWORD *)((char *)a1 + 152);
    v12 = *v11;
    if ( *(_QWORD **)(*v11 + 8LL) != v11 || (v13 = (_QWORD *)v11[1], (_QWORD *)*v13 != v11) )
      __fastfail(3u);
    *v13 = v12;
    *(_QWORD *)(v12 + 8) = v13;
    KeReleaseMutex((PRKMUTEX)(DeviceExtension + 16), 0);
    v11[1] = v11;
    *v11 = v11;
  }
}

```

## disassembly

```asm
0x14000743c  push    rbx
0x14000743e  push    rbp
0x14000743f  push    rsi
0x140007440  push    rdi
0x140007441  push    r14
0x140007443  sub     rsp, 30h
0x140007447  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14000744e  lea     rsi, [rcx+70h]
0x140007452  mov     rdi, rcx
0x140007455  mov     rcx, rsi; SpinLock
0x140007458  mov     r14, [rax+40h]
0x14000745c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007463  nop     dword ptr [rax+rax+00h]
0x140007468  mov     edx, [rdi+204h]
0x14000746e  mov     bpl, al
0x140007471  test    dl, 20h
0x140007474  jz      short loc_140007493
0x140007476  mov     dl, al; NewIrql
0x140007478  mov     rcx, rsi; SpinLock
0x14000747b  call    cs:__imp_KeReleaseSpinLock
0x140007482  nop     dword ptr [rax+rax+00h]
0x140007487  add     rsp, 30h
0x14000748b  pop     r14
0x14000748d  pop     rdi
0x14000748e  pop     rsi
0x14000748f  pop     rbp
0x140007490  pop     rbx
0x140007491  retn
0x140007493  mov     eax, [rdi+204h]
0x140007499  lea     rdx, aPmremovehelper; "PmRemoveHelper"
0x1400074a0  or      eax, 20h
0x1400074a3  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400074a6  mov     [rdi+204h], eax
0x1400074ac  mov     eax, [rdi+204h]
0x1400074b2  and     eax, 0FFFFFFFEh
0x1400074b5  mov     [rdi+204h], eax
0x1400074bb  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x1400074c0  mov     dl, bpl; NewIrql
0x1400074c3  mov     rcx, rsi; SpinLock
0x1400074c6  mov     ebx, eax
0x1400074c8  call    cs:__imp_KeReleaseSpinLock
0x1400074cf  nop     dword ptr [rax+rax+00h]
0x1400074d4  xor     ebp, ebp
0x1400074d6  test    ebx, ebx
0x1400074d8  js      short loc_1400074FA
0x1400074da  lea     rcx, [rdi+338h]; Object
0x1400074e1  mov     [rsp+58h+Timeout], rbp; Timeout
0x1400074e6  xor     r9d, r9d; Alertable
0x1400074e9  xor     r8d, r8d; WaitMode
0x1400074ec  xor     edx, edx; WaitReason
0x1400074ee  call    cs:__imp_KeWaitForSingleObject
0x1400074f5  nop     dword ptr [rax+rax+00h]
0x1400074fa  xor     r9d, r9d; Alertable
0x1400074fd  mov     [rsp+58h+Timeout], rbp; Timeout
0x140007502  xor     r8d, r8d; WaitMode
0x140007505  lea     rcx, [rdi+38h]; Object
0x140007509  xor     edx, edx; WaitReason
0x14000750b  call    cs:__imp_KeWaitForSingleObject
0x140007512  nop     dword ptr [rax+rax+00h]
0x140007517  mov     rcx, rsi; SpinLock
0x14000751a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007521  nop     dword ptr [rax+rax+00h]
0x140007526  mov     edx, [rdi+204h]
0x14000752c  mov     rcx, rsi; SpinLock
0x14000752f  and     edx, 0FFFFFFFDh
0x140007532  mov     [rdi+204h], edx
0x140007538  mov     dl, al; NewIrql
0x14000753a  call    cs:__imp_KeReleaseSpinLock
0x140007541  nop     dword ptr [rax+rax+00h]
0x140007546  xor     edx, edx; Wait
0x140007548  lea     rcx, [rdi+38h]; Mutex
0x14000754c  call    cs:__imp_KeReleaseMutex
0x140007553  nop     dword ptr [rax+rax+00h]
0x140007558  xor     r9d, r9d; Alertable
0x14000755b  mov     [rsp+58h+Timeout], rbp; Timeout
0x140007560  xor     r8d, r8d; WaitMode
0x140007563  lea     rcx, [r14+68h]; Object
0x140007567  xor     edx, edx; WaitReason
0x140007569  call    cs:__imp_KeWaitForSingleObject
0x140007570  nop     dword ptr [rax+rax+00h]
0x140007575  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140007578  call    ?PmRemoveIds@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmRemoveIds(_DEVICE_EXTENSION *)
0x14000757d  xor     edx, edx; Wait
0x14000757f  lea     rcx, [r14+68h]; Mutex
0x140007583  call    cs:__imp_KeReleaseMutex
0x14000758a  nop     dword ptr [rax+rax+00h]
0x14000758f  mov     rcx, [rdi+8]; DeviceObject
0x140007593  mov     edx, 2; Action
0x140007598  call    cs:__imp_IoWMIRegistrationControl
0x14000759f  nop     dword ptr [rax+rax+00h]
0x1400075a4  lea     rcx, [rdi+2D0h]; struct _PERF_COUNTER_CONTEXT **
0x1400075ab  xor     r8d, r8d; unsigned __int8
0x1400075ae  mov     dl, 1; unsigned __int8
0x1400075b0  call    ?PmWmiCounterDisable@@YAEPEAPEAU_PERF_COUNTER_CONTEXT@@EE@Z; PmWmiCounterDisable(_PERF_COUNTER_CONTEXT * *,uchar,uchar)
0x1400075b5  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400075b8  call    ?PmPowerCounterDisable@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmPowerCounterDisable(_DEVICE_EXTENSION *)
0x1400075bd  mov     rsi, rbp
0x1400075c0  mov     rax, rsi
0x1400075c3  add     rax, rax
0x1400075c6  cmp     [rdi+rax*8+1E8h], rbp
0x1400075ce  jz      short loc_1400075FC
0x1400075d0  lea     rbx, [rdi+rax*8]
0x1400075d4  xor     edx, edx; Enable
0x1400075d6  lea     rcx, [rbx+1E0h]; SymbolicLinkName
0x1400075dd  call    cs:__imp_IoSetDeviceInterfaceState
0x1400075e4  nop     dword ptr [rax+rax+00h]
0x1400075e9  lea     rcx, [rbx+1E0h]; UnicodeString
0x1400075f0  call    cs:__imp_RtlFreeUnicodeString
0x1400075f7  nop     dword ptr [rax+rax+00h]
0x1400075fc  inc     rsi
0x1400075ff  cmp     rsi, 2
0x140007603  jnz     short loc_1400075C0
0x140007605  xor     r9d, r9d; Alertable
0x140007608  mov     [rdi+200h], esi
0x14000760e  xor     r8d, r8d; WaitMode
0x140007611  mov     [rsp+58h+Timeout], rbp; Timeout
0x140007616  xor     edx, edx; WaitReason
0x140007618  lea     rcx, [r14+10h]; Object
0x14000761c  call    cs:__imp_KeWaitForSingleObject
0x140007623  nop     dword ptr [rax+rax+00h]
0x140007628  add     rdi, 98h
0x14000762f  mov     rdx, [rdi]
0x140007632  cmp     [rdx+8], rdi
0x140007636  jnz     short loc_140007666
0x140007638  mov     rax, [rdi+8]
0x14000763c  cmp     [rax], rdi
0x14000763f  jnz     short loc_140007666
0x140007641  mov     [rax], rdx
0x140007644  lea     rcx, [r14+10h]; Mutex
0x140007648  mov     [rdx+8], rax
0x14000764c  xor     edx, edx; Wait
0x14000764e  call    cs:__imp_KeReleaseMutex
0x140007655  nop     dword ptr [rax+rax+00h]
0x14000765a  mov     [rdi+8], rdi
0x14000765e  mov     [rdi], rdi
0x140007661  jmp     loc_140007487
0x140007666  mov     ecx, 3
0x14000766b  int     29h; Win8: RtlFailFast(ecx)
```
