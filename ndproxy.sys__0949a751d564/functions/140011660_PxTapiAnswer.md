# PxTapiAnswer

- ea: `0x140011660`
- end: `0x14001183c`
- name: `PxTapiAnswer`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001b54`
- `0x140007308`
- `0x140007488`
- `0x1400113a0`
- `0x140011660`
- `0x1400156d8`
- `0x1400167a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400117cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400117cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001174d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001174d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117f6`
- `NDIS!NdisClIncomingCallComplete` at `0x1400117c0`
- `NDIS!NdisClIncomingCallComplete` at `0x1400117c0`

## pseudocode

```c
__int64 __fastcall PxTapiAnswer(__int64 a1)
{
  __int64 v2; // r8
  _DWORD *v4; // rbx
  KSPIN_LOCK *v5; // rdi
  __int64 v6; // r8
  KIRQL v7; // al
  PVOID Entry; // [rsp+40h] [rbp+8h] BYREF

  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  if ( IsVcValid(*(_QWORD *)(a1 + 56), &Entry) )
  {
    v4 = Entry;
    v5 = (KSPIN_LOCK *)((char *)Entry + 512);
    *((_BYTE *)v4 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
    if ( v4[4] == 2 )
    {
      if ( (v4[8] & 4) != 0 )
        PxStopIncomingCallTimeout(v4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
      v4[5] = v4[4];
      v4[4] = 4;
      KeReleaseSpinLock(v5, *((_BYTE *)v4 + 520));
      NdisClIncomingCallComplete(0, *((NDIS_HANDLE *)v4 + 5), *((PCO_CALL_PARAMETERS *)v4 + 39));
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qLL(WPP_GLOBAL_Control->AttachedDevice, 31, v6, v4, v4[8], v4[73]);
      KeReleaseSpinLock(v5, *((_BYTE *)v4 + 520));
    }
    v7 = KeAcquireSpinLockRaiseToDpc(v5);
    *((_BYTE *)v4 + 520) = v7;
    if ( v4[7]-- == 1 )
      DoDerefVcWork(v4);
    else
      KeReleaseSpinLock(v5, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_P(WPP_GLOBAL_Control->AttachedDevice, 30, v2, *(_QWORD *)(a1 + 56));
    return 3221299213LL;
  }
}

```

## disassembly

```asm
0x140011660  mov     [rsp+arg_8], rbx
0x140011665  mov     [rsp+arg_10], rsi
0x14001166a  push    rdi
0x14001166b  sub     rsp, 30h
0x14001166f  mov     rbx, rcx
0x140011672  mov     [rsp+38h+Entry], 0
0x14001167b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011682  lea     rsi, WPP_GLOBAL_Control
0x140011689  cmp     rcx, rsi
0x14001168c  jz      short loc_1400116A9
0x14001168e  cmp     byte ptr [rcx+29h], 4
0x140011692  jb      short loc_1400116A9
0x140011694  mov     rcx, [rcx+18h]
0x140011698  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14001169f  mov     edx, 1Dh
0x1400116a4  call    WPP_SF_
0x1400116a9  mov     rcx, [rbx+38h]
0x1400116ad  lea     rdx, [rsp+38h+Entry]
0x1400116b2  call    IsVcValid
0x1400116b7  test    al, al
0x1400116b9  jnz     short loc_1400116E9
0x1400116bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116c2  cmp     rcx, rsi
0x1400116c5  jz      short loc_1400116DF
0x1400116c7  cmp     byte ptr [rcx+29h], 3
0x1400116cb  jb      short loc_1400116DF
0x1400116cd  mov     r9, [rbx+38h]
0x1400116d1  mov     edx, 1Eh
0x1400116d6  mov     rcx, [rcx+18h]
0x1400116da  call    WPP_SF_P
0x1400116df  mov     eax, 0C001200Dh
0x1400116e4  jmp     loc_14001182B
0x1400116e9  mov     rbx, [rsp+38h+Entry]
0x1400116ee  lea     rdi, [rbx+200h]
0x1400116f5  mov     rcx, rdi; SpinLock
0x1400116f8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400116ff  nop     dword ptr [rax+rax+00h]
0x140011704  mov     [rbx+208h], al
0x14001170a  cmp     dword ptr [rbx+10h], 2
0x14001170e  jz      short loc_14001175B
0x140011710  mov     rcx, cs:WPP_GLOBAL_Control
0x140011717  cmp     rcx, rsi
0x14001171a  jz      short loc_140011744
0x14001171c  cmp     byte ptr [rcx+29h], 1
0x140011720  jb      short loc_140011744
0x140011722  mov     eax, [rbx+124h]
0x140011728  mov     edx, 1Fh
0x14001172d  mov     rcx, [rcx+18h]
0x140011731  mov     r9, rbx
0x140011734  mov     [rsp+38h+var_10], eax
0x140011738  mov     eax, [rbx+20h]
0x14001173b  mov     [rsp+38h+var_18], eax
0x14001173f  call    WPP_SF_qLL
0x140011744  mov     dl, [rbx+208h]; NewIrql
0x14001174a  mov     rcx, rdi; SpinLock
0x14001174d  call    cs:__imp_KeReleaseSpinLock
0x140011754  nop     dword ptr [rax+rax+00h]
0x140011759  jmp     short loc_1400117CC
0x14001175b  mov     eax, [rbx+20h]
0x14001175e  test    al, 4
0x140011760  jz      short loc_14001176A
0x140011762  mov     rcx, rbx
0x140011765  call    PxStopIncomingCallTimeout
0x14001176a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011771  cmp     rcx, rsi
0x140011774  jz      short loc_140011791
0x140011776  cmp     byte ptr [rcx+29h], 5
0x14001177a  jb      short loc_140011791
0x14001177c  mov     rcx, [rcx+18h]
0x140011780  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011787  mov     edx, 20h ; ' '
0x14001178c  call    WPP_SF_
0x140011791  mov     eax, [rbx+10h]
0x140011794  mov     rcx, rdi; SpinLock
0x140011797  mov     [rbx+14h], eax
0x14001179a  mov     dword ptr [rbx+10h], 4
0x1400117a1  mov     dl, [rbx+208h]; NewIrql
0x1400117a7  call    cs:__imp_KeReleaseSpinLock
0x1400117ae  nop     dword ptr [rax+rax+00h]
0x1400117b3  mov     r8, [rbx+138h]; CallParameters
0x1400117ba  xor     ecx, ecx; Status
0x1400117bc  mov     rdx, [rbx+28h]; NdisVcHandle
0x1400117c0  call    cs:__imp_NdisClIncomingCallComplete
0x1400117c7  nop     dword ptr [rax+rax+00h]
0x1400117cc  mov     rcx, rdi; SpinLock
0x1400117cf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400117d6  nop     dword ptr [rax+rax+00h]
0x1400117db  mov     [rbx+208h], al
0x1400117e1  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1400117e5  jnz     short loc_1400117F1
0x1400117e7  mov     rcx, rbx; Entry
0x1400117ea  call    DoDerefVcWork
0x1400117ef  jmp     short loc_140011802
0x1400117f1  mov     dl, al; NewIrql
0x1400117f3  mov     rcx, rdi; SpinLock
0x1400117f6  call    cs:__imp_KeReleaseSpinLock
0x1400117fd  nop     dword ptr [rax+rax+00h]
0x140011802  mov     rcx, cs:WPP_GLOBAL_Control
0x140011809  cmp     rcx, rsi
0x14001180c  jz      short loc_140011829
0x14001180e  cmp     byte ptr [rcx+29h], 5
0x140011812  jb      short loc_140011829
0x140011814  mov     rcx, [rcx+18h]
0x140011818  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14001181f  mov     edx, 21h ; '!'
0x140011824  call    WPP_SF_
0x140011829  xor     eax, eax
0x14001182b  mov     rbx, [rsp+38h+arg_8]
0x140011830  mov     rsi, [rsp+38h+arg_10]
0x140011835  add     rsp, 30h
0x140011839  pop     rdi
0x14001183a  retn
```
