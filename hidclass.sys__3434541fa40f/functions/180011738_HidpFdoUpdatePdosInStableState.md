# HidpFdoUpdatePdosInStableState

- ea: `0x180011738`
- end: `0x18001188e`
- name: `HidpFdoUpdatePdosInStableState`
- size: `342`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800100e4`
- `0x1800101a0`
- `0x1800118c4`
- `0x180019694`
- `0x18003e5b0`
- `0x180042b00`
- `0x180042f24`

## callees

- `0x18000ce08`
- `0x18000ddc8`
- `0x180011738`
- `0x18001e944`
- `0x180024e20`
- `0x180024e88`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x180011878`
- `ntoskrnl!KeReleaseSpinLock` at `0x180011878`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011751`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011751`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180011844`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180011844`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180011852`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180011852`

## pseudocode

```c
void __fastcall HidpFdoUpdatePdosInStableState(__int64 a1, char a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // al
  int v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // r8
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  KIRQL NewIrql; // [rsp+88h] [rbp+10h] BYREF

  v2 = (KSPIN_LOCK *)(a1 + 1792);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1792));
  v6 = 0;
  NewIrql = v5;
  LOBYTE(v7) = 1;
  if ( a2 == 1 )
    v6 = 2;
  v8 = *(_DWORD *)(a1 + 1768) & 0xFFFFFFFD | v6;
  *(_DWORD *)(a1 + 1768) = v8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    LOBYTE(v7) = 0;
  }
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v8,
      *(_QWORD *)(a1 + 672),
      4,
      9,
      38,
      (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
      *(_QWORD *)a1,
      a2);
  if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline(v9, v7, v8) )
  {
    v10 = a1 + 2144;
    if ( (*(_DWORD *)(a1 + 1768) & 2) != 0 )
      HidpFdoSleepstudyHelperComponentInactiveSafe(a1, v10);
    else
      HidpFdoSleepstudyHelperComponentActiveSafe(a1, v10);
  }
  else if ( *(_QWORD *)(a1 + 2144) )
  {
    if ( (*(_DWORD *)(a1 + 1768) & 2) != 0 )
      SleepstudyHelper_ComponentInactive();
    else
      SleepstudyHelper_ComponentActive();
  }
  HidFdoRunTimePolicyEngine(a1, &NewIrql);
  KeReleaseSpinLock(v2, NewIrql);
}

```

## disassembly

```asm
0x180011738  push    rbx
0x18001173a  push    rbp
0x18001173b  push    rsi
0x18001173c  push    rdi
0x18001173d  sub     rsp, 58h
0x180011741  lea     rsi, [rcx+700h]
0x180011748  movzx   edi, dl
0x18001174b  mov     rbx, rcx
0x18001174e  mov     rcx, rsi; SpinLock
0x180011751  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180011758  nop     dword ptr [rax+rax+00h]
0x18001175d  xor     r8d, r8d
0x180011760  mov     [rsp+78h+NewIrql], al
0x180011767  mov     eax, [rbx+6E8h]
0x18001176d  mov     dl, 1
0x18001176f  cmp     dil, dl
0x180011772  lea     ebp, [r8+2]
0x180011776  cmovz   r8d, ebp
0x18001177a  and     eax, 0FFFFFFFDh
0x18001177d  or      r8d, eax
0x180011780  mov     [rbx+6E8h], r8d
0x180011787  mov     rcx, cs:WPP_GLOBAL_Control
0x18001178e  lea     rax, WPP_GLOBAL_Control
0x180011795  cmp     rcx, rax
0x180011798  jz      short loc_1800117A9
0x18001179a  test    dword ptr [rcx+2Ch], 100h
0x1800117a1  jz      short loc_1800117A9
0x1800117a3  cmp     byte ptr [rcx+29h], 4
0x1800117a7  jnb     short loc_1800117AB
0x1800117a9  xor     dl, dl
0x1800117ab  lea     rax, WPP_RECORDER_INITIALIZED
0x1800117b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800117b9  setnz   r8b
0x1800117bd  test    dl, dl
0x1800117bf  jnz     short loc_1800117C6
0x1800117c1  test    r8b, r8b
0x1800117c4  jz      short loc_180011802
0x1800117c6  mov     rax, [rbx]
0x1800117c9  mov     r9, [rbx+2A0h]
0x1800117d0  mov     rcx, [rcx+18h]
0x1800117d4  mov     [rsp+78h+var_30], edi
0x1800117d8  mov     [rsp+78h+var_38], rax
0x1800117dd  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x1800117e4  mov     [rsp+78h+var_40], rax
0x1800117e9  mov     [rsp+78h+var_48], 26h ; '&'
0x1800117f0  mov     [rsp+78h+var_50], 9
0x1800117f8  mov     [rsp+78h+var_58], 4
0x1800117fd  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180011802  lea     rdi, [rbx+860h]
0x180011809  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x18001180e  test    eax, eax
0x180011810  jz      short loc_180011831
0x180011812  mov     eax, [rbx+6E8h]
0x180011818  mov     rdx, rdi
0x18001181b  mov     rcx, rbx
0x18001181e  test    bpl, al
0x180011821  jz      short loc_18001182A
0x180011823  call    HidpFdoSleepstudyHelperComponentInactiveSafe
0x180011828  jmp     short loc_18001185E
0x18001182a  call    HidpFdoSleepstudyHelperComponentActiveSafe
0x18001182f  jmp     short loc_18001185E
0x180011831  mov     rcx, [rdi]
0x180011834  test    rcx, rcx
0x180011837  jz      short loc_18001185E
0x180011839  mov     eax, [rbx+6E8h]
0x18001183f  test    bpl, al
0x180011842  jz      short loc_180011852
0x180011844  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x18001184b  nop     dword ptr [rax+rax+00h]
0x180011850  jmp     short loc_18001185E
0x180011852  call    cs:__imp_SleepstudyHelper_ComponentActive
0x180011859  nop     dword ptr [rax+rax+00h]
0x18001185e  lea     rdx, [rsp+78h+NewIrql]
0x180011866  mov     rcx, rbx
0x180011869  call    HidFdoRunTimePolicyEngine
0x18001186e  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x180011875  mov     rcx, rsi; SpinLock
0x180011878  call    cs:__imp_KeReleaseSpinLock
0x18001187f  nop     dword ptr [rax+rax+00h]
0x180011884  add     rsp, 58h
0x180011888  pop     rdi
0x180011889  pop     rsi
0x18001188a  pop     rbp
0x18001188b  pop     rbx
0x18001188c  retn
```
