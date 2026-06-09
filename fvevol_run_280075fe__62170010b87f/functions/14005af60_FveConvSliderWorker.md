# FveConvSliderWorker

- ea: `0x14005af60`
- end: `0x14005b0c8`
- name: `FveConvSliderWorker`
- size: `360`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140008dc0`
- `0x14005822c`
- `0x14005adb0`
- `0x14005af60`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14005b065`
- `ntoskrnl!KeReadStateEvent` at `0x14005b065`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14005afee`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14005afee`
- `ntoskrnl!KeClearEvent` at `0x14005b03e`
- `ntoskrnl!KeClearEvent` at `0x14005b03e`
- `ntoskrnl!PsTerminateSystemThread` at `0x14005b0b1`
- `ntoskrnl!PsTerminateSystemThread` at `0x14005b0b1`
- `ntoskrnl!KeSetEvent` at `0x14005b056`
- `ntoskrnl!KeSetEvent` at `0x14005b056`

## pseudocode

```c
void __fastcall FveConvSliderWorker(char *StartContext)
{
  NTSTATUS v2; // eax
  PVOID Object[7]; // [rsp+40h] [rbp-38h] BYREF

  *(_OWORD *)Object = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
  }
  Object[0] = StartContext + 464;
  Object[1] = StartContext + 440;
  do
  {
    v2 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
    if ( v2 )
    {
      if ( v2 == 1
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
      }
    }
    else
    {
      FveConvSliderMove(StartContext);
      KeClearEvent((PRKEVENT)(StartContext + 464));
      KeSetEvent((PRKEVENT)(StartContext + 488), 0, 0);
    }
  }
  while ( !KeReadStateEvent((PRKEVENT)(StartContext + 440)) );
  FveConvFreeControl(StartContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14005af60  push    rbx
0x14005af62  push    rsi
0x14005af63  push    rdi
0x14005af64  push    r13
0x14005af66  sub     rsp, 58h
0x14005af6a  xorps   xmm0, xmm0
0x14005af6d  mov     rbx, rcx
0x14005af70  movups  xmmword ptr [rsp+78h+Object], xmm0
0x14005af75  mov     rcx, cs:WPP_GLOBAL_Control
0x14005af7c  lea     r13, WPP_GLOBAL_Control
0x14005af83  cmp     rcx, r13
0x14005af86  jz      short loc_14005AFAA
0x14005af88  mov     eax, [rcx+2Ch]
0x14005af8b  test    al, 2
0x14005af8d  jz      short loc_14005AFAA
0x14005af8f  cmp     byte ptr [rcx+29h], 5
0x14005af93  jb      short loc_14005AFAA
0x14005af95  mov     rcx, [rcx+18h]
0x14005af99  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x14005afa0  mov     edx, 8Ah
0x14005afa5  call    WPP_SF_
0x14005afaa  lea     rsi, [rbx+1D0h]
0x14005afb1  lea     rdi, [rbx+1B8h]
0x14005afb8  mov     [rsp+78h+Object], rsi
0x14005afbd  mov     [rsp+78h+Object+8], rdi
0x14005afc2  xor     r9d, r9d; WaitReason
0x14005afc5  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14005afce  mov     [rsp+78h+Timeout], 0; Timeout
0x14005afd7  lea     rdx, [rsp+78h+Object]; Object
0x14005afdc  mov     [rsp+78h+Alertable], 0; Alertable
0x14005afe1  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14005afe6  lea     r8d, [r9+1]; WaitType
0x14005afea  lea     ecx, [r9+2]; Count
0x14005afee  call    cs:__imp_KeWaitForMultipleObjects
0x14005aff5  nop     dword ptr [rax+rax+00h]
0x14005affa  test    eax, eax
0x14005affc  jz      short loc_14005B033
0x14005affe  cmp     eax, 1
0x14005b001  jnz     short loc_14005B062
0x14005b003  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b00a  cmp     rcx, r13
0x14005b00d  jz      short loc_14005B062
0x14005b00f  mov     eax, [rcx+2Ch]
0x14005b012  test    al, 2
0x14005b014  jz      short loc_14005B062
0x14005b016  cmp     byte ptr [rcx+29h], 5
0x14005b01a  jb      short loc_14005B062
0x14005b01c  mov     rcx, [rcx+18h]
0x14005b020  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x14005b027  mov     edx, 8Bh
0x14005b02c  call    WPP_SF_
0x14005b031  jmp     short loc_14005B062
0x14005b033  mov     rcx, rbx
0x14005b036  call    FveConvSliderMove
0x14005b03b  mov     rcx, rsi; Event
0x14005b03e  call    cs:__imp_KeClearEvent
0x14005b045  nop     dword ptr [rax+rax+00h]
0x14005b04a  lea     rcx, [rbx+1E8h]; Event
0x14005b051  xor     r8d, r8d; Wait
0x14005b054  xor     edx, edx; Increment
0x14005b056  call    cs:__imp_KeSetEvent
0x14005b05d  nop     dword ptr [rax+rax+00h]
0x14005b062  mov     rcx, rdi; Event
0x14005b065  call    cs:__imp_KeReadStateEvent
0x14005b06c  nop     dword ptr [rax+rax+00h]
0x14005b071  test    eax, eax
0x14005b073  jz      loc_14005AFC2
0x14005b079  mov     rcx, rbx; P
0x14005b07c  call    FveConvFreeControl
0x14005b081  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b088  cmp     rcx, r13
0x14005b08b  jz      short loc_14005B0AF
0x14005b08d  mov     eax, [rcx+2Ch]
0x14005b090  test    al, 2
0x14005b092  jz      short loc_14005B0AF
0x14005b094  cmp     byte ptr [rcx+29h], 5
0x14005b098  jb      short loc_14005B0AF
0x14005b09a  mov     rcx, [rcx+18h]
0x14005b09e  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x14005b0a5  mov     edx, 8Ch
0x14005b0aa  call    WPP_SF_
0x14005b0af  xor     ecx, ecx; ExitStatus
0x14005b0b1  call    cs:__imp_PsTerminateSystemThread
0x14005b0b8  nop     dword ptr [rax+rax+00h]
0x14005b0bd  add     rsp, 58h
0x14005b0c1  pop     r13
0x14005b0c3  pop     rdi
0x14005b0c4  pop     rsi
0x14005b0c5  pop     rbx
0x14005b0c6  retn
```
