# FveWipeSliderWorker

- ea: `0x14007b2d0`
- end: `0x14007b43c`
- name: `FveWipeSliderWorker`
- size: `364`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140008e80`
- `0x140079a40`
- `0x14007b034`
- `0x14007b2d0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14007b3d7`
- `ntoskrnl!KeReadStateEvent` at `0x14007b3d7`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14007b360`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14007b360`
- `ntoskrnl!KeClearEvent` at `0x14007b3b0`
- `ntoskrnl!KeClearEvent` at `0x14007b3b0`
- `ntoskrnl!PsTerminateSystemThread` at `0x14007b425`
- `ntoskrnl!PsTerminateSystemThread` at `0x14007b425`
- `ntoskrnl!KeSetEvent` at `0x14007b3c8`
- `ntoskrnl!KeSetEvent` at `0x14007b3c8`

## pseudocode

```c
void __fastcall FveWipeSliderWorker(struct _KEVENT *StartContext)
{
  NTSTATUS v2; // eax
  PVOID Object[7]; // [rsp+40h] [rbp-38h] BYREF

  *(_OWORD *)Object = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
  }
  Object[0] = &StartContext[14];
  Object[1] = &StartContext[13];
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
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
      }
    }
    else
    {
      FveWipeSliderMove(StartContext);
      KeClearEvent(StartContext + 14);
      KeSetEvent(StartContext + 15, 0, 0);
    }
  }
  while ( !KeReadStateEvent(StartContext + 13) );
  FveWipeFreeControl(StartContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14007b2d0  push    rbx
0x14007b2d2  push    rsi
0x14007b2d3  push    rdi
0x14007b2d4  push    r12
0x14007b2d6  sub     rsp, 58h
0x14007b2da  xorps   xmm0, xmm0
0x14007b2dd  mov     rbx, rcx
0x14007b2e0  movups  xmmword ptr [rsp+78h+Object], xmm0
0x14007b2e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b2ec  lea     r12, WPP_GLOBAL_Control
0x14007b2f3  cmp     rcx, r12
0x14007b2f6  jz      short loc_14007B31C
0x14007b2f8  test    dword ptr [rcx+2Ch], 1000h
0x14007b2ff  jz      short loc_14007B31C
0x14007b301  cmp     byte ptr [rcx+29h], 5
0x14007b305  jb      short loc_14007B31C
0x14007b307  mov     rcx, [rcx+18h]
0x14007b30b  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007b312  mov     edx, 3Bh ; ';'
0x14007b317  call    WPP_SF_
0x14007b31c  lea     rsi, [rbx+150h]
0x14007b323  lea     rdi, [rbx+138h]
0x14007b32a  mov     [rsp+78h+Object], rsi
0x14007b32f  mov     [rsp+78h+Object+8], rdi
0x14007b334  xor     r9d, r9d; WaitReason
0x14007b337  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14007b340  mov     [rsp+78h+Timeout], 0; Timeout
0x14007b349  lea     rdx, [rsp+78h+Object]; Object
0x14007b34e  mov     [rsp+78h+Alertable], 0; Alertable
0x14007b353  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14007b358  lea     r8d, [r9+1]; WaitType
0x14007b35c  lea     ecx, [r9+2]; Count
0x14007b360  call    cs:__imp_KeWaitForMultipleObjects
0x14007b367  nop     dword ptr [rax+rax+00h]
0x14007b36c  test    eax, eax
0x14007b36e  jz      short loc_14007B3A5
0x14007b370  cmp     eax, 1
0x14007b373  jnz     short loc_14007B3D4
0x14007b375  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b37c  cmp     rcx, r12
0x14007b37f  jz      short loc_14007B3D4
0x14007b381  mov     eax, [rcx+2Ch]
0x14007b384  test    al, 2
0x14007b386  jz      short loc_14007B3D4
0x14007b388  cmp     byte ptr [rcx+29h], 5
0x14007b38c  jb      short loc_14007B3D4
0x14007b38e  mov     rcx, [rcx+18h]
0x14007b392  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007b399  mov     edx, 3Ch ; '<'
0x14007b39e  call    WPP_SF_
0x14007b3a3  jmp     short loc_14007B3D4
0x14007b3a5  mov     rcx, rbx
0x14007b3a8  call    FveWipeSliderMove
0x14007b3ad  mov     rcx, rsi; Event
0x14007b3b0  call    cs:__imp_KeClearEvent
0x14007b3b7  nop     dword ptr [rax+rax+00h]
0x14007b3bc  lea     rcx, [rbx+168h]; Event
0x14007b3c3  xor     r8d, r8d; Wait
0x14007b3c6  xor     edx, edx; Increment
0x14007b3c8  call    cs:__imp_KeSetEvent
0x14007b3cf  nop     dword ptr [rax+rax+00h]
0x14007b3d4  mov     rcx, rdi; Event
0x14007b3d7  call    cs:__imp_KeReadStateEvent
0x14007b3de  nop     dword ptr [rax+rax+00h]
0x14007b3e3  test    eax, eax
0x14007b3e5  jz      loc_14007B334
0x14007b3eb  mov     rcx, rbx; P
0x14007b3ee  call    FveWipeFreeControl
0x14007b3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b3fa  cmp     rcx, r12
0x14007b3fd  jz      short loc_14007B423
0x14007b3ff  test    dword ptr [rcx+2Ch], 1000h
0x14007b406  jz      short loc_14007B423
0x14007b408  cmp     byte ptr [rcx+29h], 5
0x14007b40c  jb      short loc_14007B423
0x14007b40e  mov     rcx, [rcx+18h]
0x14007b412  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007b419  mov     edx, 3Dh ; '='
0x14007b41e  call    WPP_SF_
0x14007b423  xor     ecx, ecx; ExitStatus
0x14007b425  call    cs:__imp_PsTerminateSystemThread
0x14007b42c  nop     dword ptr [rax+rax+00h]
0x14007b431  add     rsp, 58h
0x14007b435  pop     r12
0x14007b437  pop     rdi
0x14007b438  pop     rsi
0x14007b439  pop     rbx
0x14007b43a  retn
```
