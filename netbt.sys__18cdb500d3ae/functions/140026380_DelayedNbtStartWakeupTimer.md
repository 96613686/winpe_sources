# DelayedNbtStartWakeupTimer

- ea: `0x140026380`
- end: `0x14002674f`
- name: `DelayedNbtStartWakeupTimer`
- size: `975`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000bdfc`
- `0x14001a210`
- `0x140026380`
- `0x14002bfc0`
- `0x140030f40`
- `0x1400400a4`
- `0x140040428`
- `0x140041970`
- `0x1400419cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140026658`
- `ntoskrnl!ZwClose` at `0x140026658`
- `ntoskrnl!ZwCreateTimer` at `0x14002653c`
- `ntoskrnl!ZwCreateTimer` at `0x14002653c`
- `ntoskrnl!ZwSetTimer` at `0x14002661b`
- `ntoskrnl!ZwSetTimer` at `0x14002661b`
- `ntoskrnl!KeSetEvent` at `0x140026728`
- `ntoskrnl!KeSetEvent` at `0x140026728`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140026710`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140026710`
- `ntoskrnl!KeStackAttachProcess` at `0x1400263e8`
- `ntoskrnl!KeStackAttachProcess` at `0x1400263e8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400263cc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400263cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400266fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400266fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400266ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400266ef`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026411`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026411`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400263fc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400263fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026424`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026424`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400264ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400264ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400266a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400264ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400264ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400266a4`

## pseudocode

```c
LONG __fastcall DelayedNbtStartWakeupTimer(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v3; // bl
  char v4; // si
  KIRQL v5; // di
  __int64 i; // rcx
  int TimerEntry; // ebx
  char *v8; // rbx
  HANDLE *v9; // rdi
  NTSTATUS v10; // eax
  unsigned int v11; // r9d
  NTSTATUS v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  PVOID TimerContext; // [rsp+40h] [rbp-49h] BYREF
  union _LARGE_INTEGER DueTime; // [rsp+48h] [rbp-41h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+80h] [rbp-9h] BYREF

  DueTime.QuadPart = 0;
  TimerContext = 0;
  v3 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&ApcState, 0, sizeof(ApcState));
  if ( (PRKPROCESS)PsGetCurrentProcess(a1, a2, a3) == NbtFspProcess )
  {
    v4 = 0;
  }
  else
  {
    KeStackAttachProcess(NbtFspProcess, &ApcState);
    v4 = 1;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline();
  for ( i = NbtConfig; (__int64 *)i != &NbtConfig; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 376) && *(_DWORD *)(i + 144) && *(_DWORD *)(i + 160) != 2130706432 )
    {
      v3 = 1;
      break;
    }
  }
  if ( !byte_140039752 && v3 && (byte_140039680 & 2) != 0 )
  {
    TimerEntry = GetTimerEntry(&TimerContext);
    if ( TimerEntry >= 0 )
    {
      v8 = (char *)TimerContext;
      *((_BYTE *)TimerContext + 23) = 1;
      *((_QWORD *)v8 + 5) = WakeupRefreshTimeout;
      *((_QWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 7) = 0;
      KeReleaseSpinLock(&SpinLock, v5);
      ObjectAttributes.Length = 48;
      v9 = (HANDLE *)(v8 + 88);
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v10 = ZwCreateTimer((PHANDLE)v8 + 11, 0x1F0003u, &ObjectAttributes, NotificationTimer);
      if ( v10 < 0 )
      {
        if ( (BYTE3(xmmword_140038420) & 1) != 0 )
          WPP_SF_d(1048, 15, WPP_8528aed0382a3da68b410153017c41e5_Traceguids, (unsigned int)v10);
      }
      else
      {
        v11 = (dword_1400395F0
             - (unsigned int)((unsigned int)dword_1400395F0
                            * (unsigned __int64)(unsigned __int16)dword_14003962C
                            / (unsigned int)dword_1400395F4)) >> 1;
        if ( v11 < dword_140039604 )
          v11 = dword_140039604;
        *((_DWORD *)v8 + 6) = v11;
        if ( (BYTE3(xmmword_140038420) & 1) != 0 )
          WPP_SF_dddd(
            v11 / 0xEA60 % 0x3C,
            13,
            WPP_8528aed0382a3da68b410153017c41e5_Traceguids,
            v11 / 0x36EE80,
            v11 / 0xEA60 % 0x3C,
            (unsigned __int16)dword_14003962C,
            dword_1400395F4);
        DueTime.QuadPart = -10000LL * *((unsigned int *)v8 + 6);
        v8[22] = 1;
        v12 = ZwSetTimer(*v9, &DueTime, WakeupTimerExpiry, v8, 1u, 0, 0);
        if ( v12 >= 0 )
        {
          qword_1400394F0 = (__int64)v8;
          goto LABEL_33;
        }
        if ( (BYTE3(xmmword_140038420) & 1) != 0 )
          WPP_SF_dq(1048, 14, WPP_8528aed0382a3da68b410153017c41e5_Traceguids, (unsigned int)v12, *v9);
        ZwClose(*v9);
      }
      ReturnTimerToFreeQ(v8);
    }
    else
    {
      KeReleaseSpinLock(&SpinLock, v5);
      if ( (BYTE1(xmmword_140038420) & 2) != 0 )
        WPP_SF_d(1033, 12, WPP_8528aed0382a3da68b410153017c41e5_Traceguids, (unsigned int)TimerEntry);
    }
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v5);
    if ( (BYTE1(xmmword_140038420) & 2) != 0 )
      WPP_SF_DDD(v13, v3, v14, (unsigned __int8)byte_140039752, v3, (unsigned __int8)byte_140039680);
  }
LABEL_33:
  if ( (unsigned int)Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline() )
    byte_140039764 = 0;
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( v4 )
    KeUnstackDetachProcess(&ApcState);
  return KeSetEvent(&Object, 0, 0);
}

```

## disassembly

```asm
0x140026380  push    rbp
0x140026382  push    rbx
0x140026383  push    rsi
0x140026384  push    rdi
0x140026385  push    r14
0x140026387  lea     rbp, [rsp-37h]
0x14002638c  sub     rsp, 0C0h
0x140026393  mov     rax, cs:__security_cookie
0x14002639a  xor     rax, rsp
0x14002639d  mov     [rbp+57h+var_30], rax
0x1400263a1  xorps   xmm0, xmm0
0x1400263a4  xor     r14d, r14d
0x1400263a7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400263ab  xor     eax, eax
0x1400263ad  mov     qword ptr [rbp+57h+DueTime], r14
0x1400263b1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400263b5  mov     [rbp+57h+TimerContext], r14
0x1400263b9  mov     bl, r14b
0x1400263bc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400263c0  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1400263c4  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400263c8  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1400263cc  call    cs:__imp_PsGetCurrentProcess
0x1400263d3  nop     dword ptr [rax+rax+00h]
0x1400263d8  mov     rcx, cs:NbtFspProcess; PROCESS
0x1400263df  cmp     rax, rcx
0x1400263e2  jz      short loc_1400263F9
0x1400263e4  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1400263e8  call    cs:__imp_KeStackAttachProcess
0x1400263ef  nop     dword ptr [rax+rax+00h]
0x1400263f4  mov     sil, 1
0x1400263f7  jmp     short loc_1400263FC
0x1400263f9  mov     sil, r14b
0x1400263fc  call    cs:__imp_KeEnterCriticalRegion
0x140026403  nop     dword ptr [rax+rax+00h]
0x140026408  mov     dl, 1; Wait
0x14002640a  lea     rcx, Resource; Resource
0x140026411  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140026418  nop     dword ptr [rax+rax+00h]
0x14002641d  lea     rcx, SpinLock; SpinLock
0x140026424  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002642b  nop     dword ptr [rax+rax+00h]
0x140026430  mov     dil, al
0x140026433  call    Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline
0x140026438  mov     rcx, cs:NbtConfig
0x14002643f  lea     rax, NbtConfig
0x140026446  jmp     short loc_140026469
0x140026448  cmp     [rcx+178h], r14d
0x14002644f  jz      short loc_140026466
0x140026451  cmp     [rcx+90h], r14d
0x140026458  jz      short loc_140026466
0x14002645a  cmp     dword ptr [rcx+0A0h], 7F000000h
0x140026464  jnz     short loc_140026470
0x140026466  mov     rcx, [rcx]
0x140026469  cmp     rcx, rax
0x14002646c  jnz     short loc_140026448
0x14002646e  jmp     short loc_140026472
0x140026470  mov     bl, 1
0x140026472  cmp     cs:byte_140039752, r14b
0x140026479  jnz     loc_14002669A
0x14002647f  test    bl, bl
0x140026481  jz      loc_14002669A
0x140026487  test    cs:byte_140039680, 2
0x14002648e  jz      loc_14002669A
0x140026494  lea     rcx, [rbp+57h+TimerContext]
0x140026498  call    GetTimerEntry
0x14002649d  lea     rcx, SpinLock; SpinLock
0x1400264a4  mov     ebx, eax
0x1400264a6  mov     dl, dil; NewIrql
0x1400264a9  test    eax, eax
0x1400264ab  jns     short loc_1400264E4
0x1400264ad  call    cs:__imp_KeReleaseSpinLock
0x1400264b4  nop     dword ptr [rax+rax+00h]
0x1400264b9  test    byte ptr cs:xmmword_140038420+1, 2
0x1400264c0  jz      loc_1400266D8
0x1400264c6  mov     edx, 0Ch
0x1400264cb  lea     r8, WPP_8528aed0382a3da68b410153017c41e5_Traceguids
0x1400264d2  mov     ecx, 409h
0x1400264d7  mov     r9d, ebx
0x1400264da  call    WPP_SF_d
0x1400264df  jmp     loc_1400266D8
0x1400264e4  mov     rbx, [rbp+57h+TimerContext]
0x1400264e8  lea     rax, WakeupRefreshTimeout
0x1400264ef  mov     byte ptr [rbx+17h], 1
0x1400264f3  mov     [rbx+28h], rax
0x1400264f7  mov     [rbx+30h], r14
0x1400264fb  mov     [rbx+38h], r14
0x1400264ff  call    cs:__imp_KeReleaseSpinLock
0x140026506  nop     dword ptr [rax+rax+00h]
0x14002650b  xorps   xmm0, xmm0
0x14002650e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140026515  lea     rdi, [rbx+58h]
0x140026519  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14002651d  mov     rcx, rdi; TimerHandle
0x140026520  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140026527  xor     r9d, r9d; TimerType
0x14002652a  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14002652e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140026532  mov     edx, 1F0003h; DesiredAccess
0x140026537  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002653c  call    cs:__imp_ZwCreateTimer
0x140026543  nop     dword ptr [rax+rax+00h]
0x140026548  mov     r9d, eax
0x14002654b  test    eax, eax
0x14002654d  js      loc_14002666F
0x140026553  mov     r9d, cs:dword_1400395F0
0x14002655a  xor     edx, edx
0x14002655c  movzx   eax, word ptr cs:dword_14003962C
0x140026563  mov     ecx, cs:dword_1400395F4
0x140026569  imul    rax, r9
0x14002656d  div     rcx
0x140026570  sub     r9d, eax
0x140026573  shr     r9d, 1
0x140026576  cmp     r9d, cs:dword_140039604
0x14002657d  cmovb   r9d, cs:dword_140039604
0x140026585  mov     [rbx+18h], r9d
0x140026589  test    byte ptr cs:xmmword_140038420+3, 1
0x140026590  jz      short loc_1400265E9
0x140026592  movzx   r8d, word ptr cs:dword_14003962C
0x14002659a  mov     eax, 45E7B273h
0x14002659f  mul     r9d
0x1400265a2  mov     eax, 88888889h
0x1400265a7  mov     ecx, edx
0x1400265a9  shr     ecx, 0Eh
0x1400265ac  mul     ecx
0x1400265ae  shr     edx, 5
0x1400265b1  imul    eax, edx, 3Ch ; '<'
0x1400265b4  sub     ecx, eax
0x1400265b6  mov     eax, 95217CB1h
0x1400265bb  mul     r9d
0x1400265be  mov     eax, cs:dword_1400395F4
0x1400265c4  mov     r9d, edx
0x1400265c7  mov     dword ptr [rsp+0E0h+PreviousState], eax
0x1400265cb  mov     [rsp+0E0h+Period], r8d
0x1400265d0  mov     edx, 0Dh
0x1400265d5  shr     r9d, 15h
0x1400265d9  lea     r8, WPP_8528aed0382a3da68b410153017c41e5_Traceguids
0x1400265e0  mov     dword ptr [rsp+0E0h+ResumeTimer], ecx
0x1400265e4  call    WPP_SF_dddd
0x1400265e9  mov     eax, [rbx+18h]
0x1400265ec  lea     r8, WakeupTimerExpiry; TimerApcRoutine
0x1400265f3  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1400265fa  mov     [rsp+0E0h+PreviousState], r14; PreviousState
0x1400265ff  lea     rdx, [rbp+57h+DueTime]; DueTime
0x140026603  mov     qword ptr [rbp+57h+DueTime], rcx
0x140026607  mov     r9, rbx; TimerContext
0x14002660a  mov     byte ptr [rbx+16h], 1
0x14002660e  mov     rcx, [rdi]; TimerHandle
0x140026611  mov     [rsp+0E0h+Period], r14d; Period
0x140026616  mov     [rsp+0E0h+ResumeTimer], 1; ResumeTimer
0x14002661b  call    cs:__imp_ZwSetTimer
0x140026622  nop     dword ptr [rax+rax+00h]
0x140026627  test    eax, eax
0x140026629  jns     short loc_140026666
0x14002662b  test    byte ptr cs:xmmword_140038420+3, 1
0x140026632  jz      short loc_140026655
0x140026634  mov     r8, [rdi]
0x140026637  mov     edx, 0Eh
0x14002663c  mov     qword ptr [rsp+0E0h+ResumeTimer], r8
0x140026641  mov     ecx, 418h
0x140026646  lea     r8, WPP_8528aed0382a3da68b410153017c41e5_Traceguids
0x14002664d  mov     r9d, eax
0x140026650  call    WPP_SF_dq
0x140026655  mov     rcx, [rdi]; Handle
0x140026658  call    cs:__imp_ZwClose
0x14002665f  nop     dword ptr [rax+rax+00h]
0x140026664  jmp     short loc_14002668E
0x140026666  mov     cs:qword_1400394F0, rbx
0x14002666d  jmp     short loc_1400266D8
0x14002666f  test    byte ptr cs:xmmword_140038420+3, 1
0x140026676  jz      short loc_14002668E
0x140026678  mov     edx, 0Fh
0x14002667d  lea     r8, WPP_8528aed0382a3da68b410153017c41e5_Traceguids
0x140026684  mov     ecx, 418h
0x140026689  call    WPP_SF_d
0x14002668e  xor     edx, edx
0x140026690  mov     rcx, rbx; Entry
0x140026693  call    ReturnTimerToFreeQ
0x140026698  jmp     short loc_1400266D8
0x14002669a  mov     dl, dil; NewIrql
0x14002669d  lea     rcx, SpinLock; SpinLock
0x1400266a4  call    cs:__imp_KeReleaseSpinLock
0x1400266ab  nop     dword ptr [rax+rax+00h]
0x1400266b0  test    byte ptr cs:xmmword_140038420+1, 2
0x1400266b7  jz      short loc_1400266D8
0x1400266b9  movzx   eax, cs:byte_140039680
0x1400266c0  movzx   r9d, cs:byte_140039752
0x1400266c8  movzx   edx, bl
0x1400266cb  mov     [rsp+0E0h+Period], eax
0x1400266cf  mov     dword ptr [rsp+0E0h+ResumeTimer], edx
0x1400266d3  call    WPP_SF_DDD
0x1400266d8  call    Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline
0x1400266dd  test    eax, eax
0x1400266df  jz      short loc_1400266E8
0x1400266e1  mov     cs:byte_140039764, r14b
0x1400266e8  lea     rcx, Resource; Resource
0x1400266ef  call    cs:__imp_ExReleaseResourceLite
0x1400266f6  nop     dword ptr [rax+rax+00h]
0x1400266fb  call    cs:__imp_KeLeaveCriticalRegion
0x140026702  nop     dword ptr [rax+rax+00h]
0x140026707  test    sil, sil
0x14002670a  jz      short loc_14002671C
0x14002670c  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140026710  call    cs:__imp_KeUnstackDetachProcess
0x140026717  nop     dword ptr [rax+rax+00h]
0x14002671c  xor     r8d, r8d; Wait
0x14002671f  lea     rcx, Object; Event
0x140026726  xor     edx, edx; Increment
0x140026728  call    cs:__imp_KeSetEvent
0x14002672f  nop     dword ptr [rax+rax+00h]
0x140026734  mov     rcx, [rbp+57h+var_30]
0x140026738  xor     rcx, rsp; StackCookie
0x14002673b  call    __security_check_cookie
0x140026740  add     rsp, 0C0h
0x140026747  pop     r14
0x140026749  pop     rdi
0x14002674a  pop     rsi
0x14002674b  pop     rbx
0x14002674c  pop     rbp
0x14002674d  retn
```
