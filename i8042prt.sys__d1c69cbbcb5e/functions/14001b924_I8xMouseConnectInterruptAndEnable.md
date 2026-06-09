# I8xMouseConnectInterruptAndEnable

- ea: `0x14001b924`
- end: `0x14001bcd7`
- name: `I8xMouseConnectInterruptAndEnable`
- size: `947`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x140019714`
- `0x14001bce0`
- `0x14001e950`

## callees

- `0x1400014e0`
- `0x140004530`
- `0x140007b10`
- `0x140009840`
- `0x1400098f0`
- `0x14000b2b8`
- `0x14000b334`
- `0x14000b72c`
- `0x14000b8a8`
- `0x14000c9f8`
- `0x14000da60`
- `0x14001b924`
- `0x14001ce6c`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001baf9`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001baf9`
- `ntoskrnl!IoConnectInterrupt` at `0x14001bacf`
- `ntoskrnl!IoConnectInterrupt` at `0x14001bacf`
- `ntoskrnl!ObfDereferenceObject` at `0x14001bb3c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001bb3c`

## pseudocode

```c
__int64 __fastcall I8xMouseConnectInterruptAndEnable(__int64 a1, char a2)
{
  struct _DEVICE_OBJECT *v5; // r15
  BOOLEAN *v6; // rbx
  char *v7; // rsi
  const char *v8; // r10
  const char *v9; // r8
  const char *v10; // rdx
  BOOLEAN ShareVector; // zf
  __int64 v12; // rdx
  int v13; // esi
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rax
  struct _DEVICE_OBJECT *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  int Vector; // [rsp+20h] [rbp-79h]
  KIRQL Irql[8]; // [rsp+28h] [rbp-71h]
  int v26; // [rsp+70h] [rbp-29h] BYREF
  __int128 InputBuffer; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v28[2]; // [rsp+88h] [rbp-11h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      14,
      10,
      (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids,
      a2);
  if ( *(_QWORD *)(a1 + 8) )
    return 0;
  v5 = *(struct _DEVICE_OBJECT **)a1;
  v6 = (BOOLEAN *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 80LL);
  v7 = (char *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 68LL);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = "yes";
    if ( !*v6 )
      v8 = "no";
    v9 = "true";
    v10 = "Latched";
    if ( *(_BYTE *)(a1 + 537) != 3 )
      v9 = "false";
    if ( *(_WORD *)(a1 + 538) != 1 )
      v10 = "LevelSensitive";
    WPP_RECORDER_SF_qDDDssDs(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      (_DWORD)v9,
      11,
      (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids,
      (char)v5,
      *(_DWORD *)(a1 + 544),
      *(_DWORD *)(a1 + 540),
      *v7,
      (__int64)v10,
      (__int64)v9,
      *(_DWORD *)(a1 + 548),
      (__int64)v8);
  }
  ShareVector = *(_BYTE *)(a1 + 537) == 3;
  *(_BYTE *)(a1 + 564) = 1;
  v13 = IoConnectInterrupt(
          (PKINTERRUPT *)(a1 + 8),
          (PKSERVICE_ROUTINE)I8042MouseInterruptService,
          v5,
          (PKSPIN_LOCK)(a1 + 16),
          *(_DWORD *)(a1 + 544),
          *(_BYTE *)(a1 + 540),
          *v7,
          (KINTERRUPT_MODE)(*(_WORD *)(a1 + 538) == 1),
          ShareVector,
          *(_QWORD *)(a1 + 548),
          *v6);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v12,
        0x11u,
        0xCu,
        (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids);
    v26 = *(_DWORD *)(a1 + 540);
    I8xLogError(v5, -1073414095, 1090, -1073741670, (__int64)&v26, 1u);
    TraceLoggingConnectInterruptFailed((unsigned int)v13);
    I8xManuallyRemoveDevice(a1, v23);
  }
  else
  {
    memset(v28, 0, 28);
    InputBuffer = 0;
    AttachedDeviceReference = IoGetAttachedDeviceReference(v5);
    *((_QWORD *)&InputBuffer + 1) = *(_QWORD *)(a1 + 8);
    *(_QWORD *)&InputBuffer = 48;
    v15 = AttachedDeviceReference;
    memset(v28, 0, sizeof(v28));
    I8xSendIoctl(AttachedDeviceReference, 0xF3FCFu, &InputBuffer, 0x30u);
    ObfDereferenceObject(v15);
    if ( a2 )
    {
      if ( *(_BYTE *)(a1 + 1108) )
      {
        v19 = I8xMouseEnableTransmission(a1, v16, v17, v18);
        v13 = v19;
        if ( v19 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            *(_DWORD *)Irql = v19;
            WPP_RECORDER_SF_D(
              (__int64)WPP_GLOBAL_Control->DeviceExtension,
              v20,
              0x11u,
              0xDu,
              (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids,
              *(_QWORD *)Irql);
          }
          return 0;
        }
      }
      else
      {
        *(_WORD *)(a1 + 1012) = -1;
        *(_WORD *)(a1 + 560) = 0;
        v13 = I8xResetMouse(a1, v16);
        if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Dddd(
            WPP_GLOBAL_Control->DeviceExtension,
            *(unsigned __int8 *)(a1 + 1012),
            v21,
            v22,
            Vector,
            v13,
            *(_BYTE *)(a1 + 1012),
            *(_BYTE *)(a1 + 1013),
            *(_WORD *)(a1 + 560));
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v16,
        0xEu,
        0xFu,
        (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14001b924  push    rbp
0x14001b926  push    rbx
0x14001b927  push    rsi
0x14001b928  push    rdi
0x14001b929  push    r12
0x14001b92b  push    r13
0x14001b92d  push    r14
0x14001b92f  push    r15
0x14001b931  lea     rbp, [rsp-1Fh]
0x14001b936  sub     rsp, 0B8h
0x14001b93d  mov     rax, cs:__security_cookie
0x14001b944  xor     rax, rsp
0x14001b947  mov     [rbp+57h+var_48], rax
0x14001b94b  movzx   r12d, dl
0x14001b94f  mov     rdi, rcx
0x14001b952  lea     r13, WPP_RECORDER_INITIALIZED
0x14001b959  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001b960  lea     r11, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001b967  jz      short loc_14001B994
0x14001b969  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b970  mov     r9d, 0Ah
0x14001b976  mov     dword ptr [rsp+0F0h+Irql], r12d
0x14001b97b  mov     qword ptr [rsp+0F0h+Vector], r11
0x14001b980  mov     rcx, [rcx+40h]
0x14001b984  lea     r8d, [r9+4]
0x14001b988  call    WPP_RECORDER_SF_d
0x14001b98d  lea     r11, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001b994  lea     r14, [rdi+8]
0x14001b998  cmp     qword ptr [r14], 0
0x14001b99c  jz      short loc_14001B9A5
0x14001b99e  xor     eax, eax
0x14001b9a0  jmp     loc_14001BCB6
0x14001b9a5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001b9ac  mov     r15, [rdi]
0x14001b9af  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001b9b6  lea     rbx, [rax+50h]
0x14001b9ba  lea     rsi, [rax+44h]
0x14001b9be  mov     r9d, 1
0x14001b9c4  jz      loc_14001BA6C
0x14001b9ca  cmp     byte ptr [rbx], 0
0x14001b9cd  lea     rcx, aNo; "no"
0x14001b9d4  mov     eax, [rdi+224h]
0x14001b9da  lea     r10, aYes; "yes"
0x14001b9e1  cmovz   r10, rcx
0x14001b9e5  lea     r8, aTrue; "true"
0x14001b9ec  cmp     byte ptr [rdi+219h], 3
0x14001b9f3  lea     rcx, aFalse; "false"
0x14001b9fa  mov     [rsp+0F0h+var_90], r10
0x14001b9ff  lea     rdx, aLatched; "Latched"
0x14001ba06  mov     [rsp+0F0h+var_98], eax
0x14001ba0a  cmovnz  r8, rcx
0x14001ba0e  cmp     [rdi+21Ah], r9w
0x14001ba16  lea     rcx, aLevelsensitive; "LevelSensitive"
0x14001ba1d  mov     eax, [rdi+21Ch]
0x14001ba23  mov     r9d, 0Bh
0x14001ba29  mov     qword ptr [rsp+0F0h+FloatingSave], r8
0x14001ba2e  cmovnz  rdx, rcx
0x14001ba32  movzx   ecx, byte ptr [rsi]
0x14001ba35  mov     [rsp+0F0h+ProcessorEnableMask], rdx
0x14001ba3a  mov     dword ptr [rsp+0F0h+ShareVector], ecx
0x14001ba3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba45  mov     [rsp+0F0h+InterruptMode], eax
0x14001ba49  mov     eax, [rdi+220h]
0x14001ba4f  mov     dword ptr [rsp+0F0h+SynchronizeIrql], eax
0x14001ba53  mov     rcx, [rcx+40h]
0x14001ba57  mov     qword ptr [rsp+0F0h+Irql], r15
0x14001ba5c  mov     qword ptr [rsp+0F0h+Vector], r11
0x14001ba61  call    WPP_RECORDER_SF_qDDDssDs
0x14001ba66  mov     r9d, 1
0x14001ba6c  cmp     byte ptr [rdi+219h], 3
0x14001ba73  mov     r8, r15; ServiceContext
0x14001ba76  mov     [rdi+234h], r9b
0x14001ba7d  mov     al, [rbx]
0x14001ba7f  setz    cl
0x14001ba82  mov     [rsp+0F0h+FloatingSave], al; FloatingSave
0x14001ba86  xor     edx, edx
0x14001ba88  mov     rax, [rdi+224h]
0x14001ba8f  cmp     [rdi+21Ah], r9w
0x14001ba97  lea     r9, [rdi+10h]; SpinLock
0x14001ba9b  mov     [rsp+0F0h+ProcessorEnableMask], rax; ProcessorEnableMask
0x14001baa0  mov     al, [rsi]
0x14001baa2  setz    dl
0x14001baa5  mov     [rsp+0F0h+ShareVector], cl; ShareVector
0x14001baa9  mov     rcx, r14; InterruptObject
0x14001baac  mov     [rsp+0F0h+InterruptMode], edx; InterruptMode
0x14001bab0  lea     rdx, I8042MouseInterruptService; ServiceRoutine
0x14001bab7  mov     [rsp+0F0h+SynchronizeIrql], al; SynchronizeIrql
0x14001babb  mov     al, [rdi+21Ch]
0x14001bac1  mov     [rsp+0F0h+Irql], al; Irql
0x14001bac5  mov     eax, [rdi+220h]
0x14001bacb  mov     [rsp+0F0h+Vector], eax; Vector
0x14001bacf  call    cs:__imp_IoConnectInterrupt
0x14001bad6  nop     dword ptr [rax+rax+00h]
0x14001badb  mov     esi, eax
0x14001badd  test    eax, eax
0x14001badf  js      loc_14001BC43
0x14001bae5  xorps   xmm0, xmm0
0x14001bae8  xor     eax, eax
0x14001baea  movups  [rbp+57h+var_68], xmm0
0x14001baee  mov     rcx, r15; DeviceObject
0x14001baf1  movups  [rbp+57h+var_68+0Ch], xmm0
0x14001baf5  movups  [rbp+57h+InputBuffer], xmm0
0x14001baf9  call    cs:__imp_IoGetAttachedDeviceReference
0x14001bb00  nop     dword ptr [rax+rax+00h]
0x14001bb05  mov     rdx, [r14]
0x14001bb08  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x14001bb0c  xorps   xmm0, xmm0
0x14001bb0f  mov     r9d, 30h ; '0'; InputBufferLength
0x14001bb15  movups  [rbp+57h+InputBuffer], xmm0
0x14001bb19  mov     qword ptr [rbp+57h+InputBuffer+8], rdx
0x14001bb1d  mov     rcx, rax; DeviceObject
0x14001bb20  mov     edx, 0F3FCFh; IoControlCode
0x14001bb25  mov     dword ptr [rbp+57h+InputBuffer], r9d
0x14001bb29  mov     rbx, rax
0x14001bb2c  movups  [rbp+57h+var_68], xmm0
0x14001bb30  movups  [rbp+57h+var_58], xmm0
0x14001bb34  call    I8xSendIoctl
0x14001bb39  mov     rcx, rbx; Object
0x14001bb3c  call    cs:__imp_ObfDereferenceObject
0x14001bb43  nop     dword ptr [rax+rax+00h]
0x14001bb48  test    r12b, r12b
0x14001bb4b  jz      loc_14001BC0E
0x14001bb51  cmp     byte ptr [rdi+454h], 0
0x14001bb58  mov     rcx, rdi
0x14001bb5b  jz      short loc_14001BBA6
0x14001bb5d  call    I8xMouseEnableTransmission
0x14001bb62  mov     esi, eax
0x14001bb64  test    eax, eax
0x14001bb66  jns     loc_14001BCB4
0x14001bb6c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001bb73  jz      short loc_14001BB9F
0x14001bb75  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb7c  mov     r9d, 0Dh
0x14001bb82  mov     dword ptr [rsp+0F0h+Irql], eax
0x14001bb86  lea     rax, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001bb8d  mov     qword ptr [rsp+0F0h+Vector], rax
0x14001bb92  mov     rcx, [rcx+40h]
0x14001bb96  lea     r8d, [r9+4]
0x14001bb9a  call    WPP_RECORDER_SF_D
0x14001bb9f  xor     esi, esi
0x14001bba1  jmp     loc_14001BCB4
0x14001bba6  xor     eax, eax
0x14001bba8  mov     word ptr [rdi+3F4h], 0FFFFh
0x14001bbb1  mov     [rdi+230h], ax
0x14001bbb8  call    I8xResetMouse
0x14001bbbd  mov     esi, eax
0x14001bbbf  test    eax, eax
0x14001bbc1  jns     loc_14001BCB4
0x14001bbc7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001bbce  jz      loc_14001BCB4
0x14001bbd4  movzx   ecx, byte ptr [rdi+3F5h]
0x14001bbdb  movsx   eax, word ptr [rdi+230h]
0x14001bbe2  movzx   edx, byte ptr [rdi+3F4h]
0x14001bbe9  mov     dword ptr [rsp+0F0h+ShareVector], eax
0x14001bbed  mov     [rsp+0F0h+InterruptMode], ecx
0x14001bbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbf8  mov     dword ptr [rsp+0F0h+SynchronizeIrql], edx
0x14001bbfc  mov     dword ptr [rsp+0F0h+Irql], esi
0x14001bc00  mov     rcx, [rcx+40h]
0x14001bc04  call    WPP_RECORDER_SF_Dddd
0x14001bc09  jmp     loc_14001BCB4
0x14001bc0e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001bc15  jz      loc_14001BCB4
0x14001bc1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc22  lea     rax, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001bc29  mov     r9d, 0Fh
0x14001bc2f  mov     qword ptr [rsp+0F0h+Vector], rax
0x14001bc34  mov     rcx, [rcx+40h]
0x14001bc38  lea     r8d, [r9-1]
0x14001bc3c  call    WPP_RECORDER_SF_
0x14001bc41  jmp     short loc_14001BCB4
0x14001bc43  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001bc4a  jz      short loc_14001BC72
0x14001bc4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc53  lea     rax, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001bc5a  mov     r9d, 0Ch
0x14001bc60  mov     qword ptr [rsp+0F0h+Vector], rax
0x14001bc65  mov     rcx, [rcx+40h]
0x14001bc69  lea     r8d, [r9+5]
0x14001bc6d  call    WPP_RECORDER_SF_
0x14001bc72  mov     eax, [rdi+21Ch]
0x14001bc78  mov     edx, 0C0050031h
0x14001bc7d  mov     [rbp+57h+var_80], eax
0x14001bc80  mov     r9d, 0C000009Ah
0x14001bc86  lea     rax, [rbp+57h+var_80]
0x14001bc8a  mov     dword ptr [rsp+0F0h+Irql], 1
0x14001bc92  mov     r8d, 442h
0x14001bc98  mov     qword ptr [rsp+0F0h+Vector], rax
0x14001bc9d  mov     rcx, r15
0x14001bca0  call    I8xLogError
0x14001bca5  mov     ecx, esi
0x14001bca7  call    TraceLoggingConnectInterruptFailed
0x14001bcac  mov     rcx, rdi
0x14001bcaf  call    I8xManuallyRemoveDevice
0x14001bcb4  mov     eax, esi
0x14001bcb6  mov     rcx, [rbp+57h+var_48]
0x14001bcba  xor     rcx, rsp; StackCookie
0x14001bcbd  call    __security_check_cookie
0x14001bcc2  add     rsp, 0B8h
0x14001bcc9  pop     r15
0x14001bccb  pop     r14
0x14001bccd  pop     r13
0x14001bccf  pop     r12
0x14001bcd1  pop     rdi
0x14001bcd2  pop     rsi
0x14001bcd3  pop     rbx
0x14001bcd4  pop     rbp
0x14001bcd5  retn
```
