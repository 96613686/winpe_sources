# MupRefreshRegistryParametersKeyTimerCallback

- ea: `0x1400046c0`
- end: `0x1400048e2`
- name: `MupRefreshRegistryParametersKeyTimerCallback`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x1400046c0`
- `0x140016808`
- `0x140016844`
- `0x1400169e4`
- `0x140016b44`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140004714`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004714`
- `ntoskrnl!ZwClose` at `0x1400047bf`
- `ntoskrnl!ZwClose` at `0x1400048bc`
- `ntoskrnl!ZwClose` at `0x1400047bf`
- `ntoskrnl!ZwClose` at `0x1400048bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000488f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000488f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140004746`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140004746`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140004807`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140004807`
- `ntoskrnl!PsInitialSystemProcess` at `0x140004815`
- `ntoskrnl!ObDuplicateObject` at `0x140004844`
- `ntoskrnl!ObDuplicateObject` at `0x140004844`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140004883`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140004883`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004726`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004726`

## pseudocode

```c
void __fastcall MupRefreshRegistryParametersKeyTimerCallback(__int64 a1, struct _EX_RUNDOWN_REF *a2)
{
  HANDLE *v3; // rdi
  ULONG_PTR Count; // rdx
  int v5; // esi
  int v6; // eax
  HANDLE Handle; // [rsp+78h] [rbp+10h] BYREF

  Handle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Au) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&a2[2], 0);
  v3 = (HANDLE *)&a2[3];
  Count = a2[3].Count;
  if ( Count )
  {
    v6 = ObDuplicateObject(PsInitialSystemProcess, Count, PsInitialSystemProcess, &Handle, 0, 512, 2, 0);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_511a9a8026a53b8720c76e64765e5363_Traceguids,
        (unsigned int)v6);
    }
  }
  else if ( ExAcquireRundownProtection(a2 + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Au) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids);
    }
    if ( (int)MupiOpenParametersKeyFromRegistry((void **)&a2[3]) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Au) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids);
      }
      v5 = MupiRegisterParametersKeyRegistryChangeNotification(a2);
      if ( v5 < 0 )
      {
        ZwClose(*v3);
        *v3 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_511a9a8026a53b8720c76e64765e5363_Traceguids,
            (unsigned int)v5);
        }
      }
    }
    MupiArmParametersKeyRefreshTimer(a2);
    ExReleaseRundownProtection(a2 + 1);
  }
  ExReleasePushLockSharedEx(&a2[2], 0);
  KeLeaveCriticalRegion();
  if ( Handle )
  {
    MupEnableMailslots = MupiReadEnableMailslotsFromRegistry(Handle);
    if ( Handle )
      ZwClose(Handle);
  }
}

```

## disassembly

```asm
0x1400046c0  mov     [rsp+arg_0], rbx
0x1400046c5  mov     [rsp+arg_10], rbp
0x1400046ca  push    rsi
0x1400046cb  push    rdi
0x1400046cc  push    r12
0x1400046ce  push    r13
0x1400046d0  push    r14
0x1400046d2  sub     rsp, 40h
0x1400046d6  mov     rbx, rdx
0x1400046d9  mov     [rsp+68h+Handle], 0
0x1400046e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046e9  lea     r12, WPP_GLOBAL_Control
0x1400046f0  lea     r13, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x1400046f7  cmp     rcx, r12
0x1400046fa  jz      short loc_140004714
0x1400046fc  bt      dword ptr [rcx+2Ch], 1Ah
0x140004701  jnb     short loc_140004714
0x140004703  mov     rcx, [rcx+18h]
0x140004707  mov     edx, 0Eh
0x14000470c  mov     r8, r13
0x14000470f  call    WPP_SF_
0x140004714  call    cs:__imp_KeEnterCriticalRegion
0x14000471b  nop     dword ptr [rax+rax+00h]
0x140004720  xor     edx, edx
0x140004722  lea     rcx, [rbx+10h]
0x140004726  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000472d  nop     dword ptr [rax+rax+00h]
0x140004732  lea     rdi, [rbx+18h]
0x140004736  mov     rdx, [rdi]
0x140004739  test    rdx, rdx
0x14000473c  jnz     loc_140004815
0x140004742  lea     rcx, [rbx+8]; RunRef
0x140004746  call    cs:__imp_ExAcquireRundownProtection
0x14000474d  nop     dword ptr [rax+rax+00h]
0x140004752  test    al, al
0x140004754  jz      loc_14000487D
0x14000475a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004761  cmp     rcx, r12
0x140004764  jz      short loc_14000477E
0x140004766  bt      dword ptr [rcx+2Ch], 1Ah
0x14000476b  jnb     short loc_14000477E
0x14000476d  mov     rcx, [rcx+18h]
0x140004771  mov     edx, 0Fh
0x140004776  mov     r8, r13
0x140004779  call    WPP_SF_
0x14000477e  mov     rcx, rdi
0x140004781  call    MupiOpenParametersKeyFromRegistry
0x140004786  test    eax, eax
0x140004788  js      short loc_1400047FB
0x14000478a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004791  cmp     rcx, r12
0x140004794  jz      short loc_1400047AE
0x140004796  bt      dword ptr [rcx+2Ch], 1Ah
0x14000479b  jnb     short loc_1400047AE
0x14000479d  mov     rcx, [rcx+18h]
0x1400047a1  mov     edx, 10h
0x1400047a6  mov     r8, r13
0x1400047a9  call    WPP_SF_
0x1400047ae  mov     rcx, rbx
0x1400047b1  call    MupiRegisterParametersKeyRegistryChangeNotification
0x1400047b6  mov     esi, eax
0x1400047b8  test    eax, eax
0x1400047ba  jns     short loc_1400047FB
0x1400047bc  mov     rcx, [rdi]; Handle
0x1400047bf  call    cs:__imp_ZwClose
0x1400047c6  nop     dword ptr [rax+rax+00h]
0x1400047cb  mov     qword ptr [rdi], 0
0x1400047d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047d9  cmp     rcx, r12
0x1400047dc  jz      short loc_1400047FB
0x1400047de  test    dword ptr [rcx+2Ch], 1000000h
0x1400047e5  jz      short loc_1400047FB
0x1400047e7  mov     rcx, [rcx+18h]
0x1400047eb  mov     edx, 11h
0x1400047f0  mov     r9d, esi
0x1400047f3  mov     r8, r13
0x1400047f6  call    WPP_SF_d
0x1400047fb  mov     rcx, rbx
0x1400047fe  call    MupiArmParametersKeyRefreshTimer
0x140004803  lea     rcx, [rbx+8]; RunRef
0x140004807  call    cs:__imp_ExReleaseRundownProtection
0x14000480e  nop     dword ptr [rax+rax+00h]
0x140004813  jmp     short loc_14000487D
0x140004815  mov     rax, cs:__imp_PsInitialSystemProcess
0x14000481c  lea     r9, [rsp+68h+Handle]
0x140004821  mov     [rsp+68h+var_30], 0
0x140004826  mov     [rsp+68h+var_38], 2
0x14000482e  mov     [rsp+68h+var_40], 200h
0x140004836  mov     rcx, [rax]
0x140004839  mov     r8, rcx
0x14000483c  mov     [rsp+68h+var_48], 0
0x140004844  call    cs:__imp_ObDuplicateObject
0x14000484b  nop     dword ptr [rax+rax+00h]
0x140004850  test    eax, eax
0x140004852  jns     short loc_14000487D
0x140004854  mov     rcx, cs:WPP_GLOBAL_Control
0x14000485b  cmp     rcx, r12
0x14000485e  jz      short loc_14000487D
0x140004860  test    dword ptr [rcx+2Ch], 1000000h
0x140004867  jz      short loc_14000487D
0x140004869  mov     rcx, [rcx+18h]
0x14000486d  mov     edx, 12h
0x140004872  mov     r9d, eax
0x140004875  mov     r8, r13
0x140004878  call    WPP_SF_d
0x14000487d  xor     edx, edx
0x14000487f  lea     rcx, [rbx+10h]
0x140004883  call    cs:__imp_ExReleasePushLockSharedEx
0x14000488a  nop     dword ptr [rax+rax+00h]
0x14000488f  call    cs:__imp_KeLeaveCriticalRegion
0x140004896  nop     dword ptr [rax+rax+00h]
0x14000489b  mov     rcx, [rsp+68h+Handle]; KeyHandle
0x1400048a0  test    rcx, rcx
0x1400048a3  jz      short loc_1400048C8
0x1400048a5  mov     dl, 1
0x1400048a7  call    MupiReadEnableMailslotsFromRegistry
0x1400048ac  mov     cs:MupEnableMailslots, al
0x1400048b2  mov     rcx, [rsp+68h+Handle]; Handle
0x1400048b7  test    rcx, rcx
0x1400048ba  jz      short loc_1400048C8
0x1400048bc  call    cs:__imp_ZwClose
0x1400048c3  nop     dword ptr [rax+rax+00h]
0x1400048c8  lea     r11, [rsp+68h+var_28]
0x1400048cd  mov     rbx, [r11+30h]
0x1400048d1  mov     rbp, [r11+40h]
0x1400048d5  mov     rsp, r11
0x1400048d8  pop     r14
0x1400048da  pop     r13
0x1400048dc  pop     r12
0x1400048de  pop     rdi
0x1400048df  pop     rsi
0x1400048e0  retn
```
