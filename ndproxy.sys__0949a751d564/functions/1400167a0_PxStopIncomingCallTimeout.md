# PxStopIncomingCallTimeout

- ea: `0x1400167a0`
- end: `0x140016829`
- name: `PxStopIncomingCallTimeout`
- size: `137`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011660`
- `0x140015290`

## callees

- `0x140007d84`
- `0x1400167a0`

## import_xrefs

- `NDIS!NdisCancelTimer` at `0x140016808`
- `NDIS!NdisCancelTimer` at `0x140016808`

## pseudocode

```c
void __fastcall PxStopIncomingCallTimeout(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 TimerCancelled; // [rsp+50h] [rbp+8h] BYREF

  TimerCancelled = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qLqLL(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      a3,
      a1,
      *(_DWORD *)(a1 + 32),
      *(_QWORD *)(a1 + 40),
      *(_DWORD *)(a1 + 292),
      *(_DWORD *)(a1 + 296));
  NdisCancelTimer((PNDIS_TIMER)(a1 + 320), &TimerCancelled);
  *(_DWORD *)(a1 + 32) &= ~4u;
  if ( TimerCancelled )
    --*(_DWORD *)(a1 + 28);
}

```

## disassembly

```asm
0x1400167a0  push    rbx
0x1400167a2  sub     rsp, 40h
0x1400167a6  mov     rbx, rcx
0x1400167a9  mov     [rsp+48h+TimerCancelled], 0
0x1400167ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167b5  lea     rax, WPP_GLOBAL_Control
0x1400167bc  cmp     rcx, rax
0x1400167bf  jz      short loc_1400167FC
0x1400167c1  cmp     byte ptr [rcx+29h], 5
0x1400167c5  jb      short loc_1400167FC
0x1400167c7  mov     eax, [rbx+128h]
0x1400167cd  mov     edx, 22h ; '"'
0x1400167d2  mov     rcx, [rcx+18h]
0x1400167d6  mov     r9, rbx
0x1400167d9  mov     [rsp+48h+var_10], eax
0x1400167dd  mov     eax, [rbx+124h]
0x1400167e3  mov     [rsp+48h+var_18], eax
0x1400167e7  mov     rax, [rbx+28h]
0x1400167eb  mov     [rsp+48h+var_20], rax
0x1400167f0  mov     eax, [rbx+20h]
0x1400167f3  mov     [rsp+48h+var_28], eax
0x1400167f7  call    WPP_SF_qLqLL
0x1400167fc  lea     rcx, [rbx+140h]; Timer
0x140016803  lea     rdx, [rsp+48h+TimerCancelled]; TimerCancelled
0x140016808  call    cs:__imp_NdisCancelTimer
0x14001680f  nop     dword ptr [rax+rax+00h]
0x140016814  and     dword ptr [rbx+20h], 0FFFFFFFBh
0x140016818  cmp     [rsp+48h+TimerCancelled], 0
0x14001681d  jz      short loc_140016822
0x14001681f  dec     dword ptr [rbx+1Ch]
0x140016822  add     rsp, 40h
0x140016826  pop     rbx
0x140016827  retn
```
