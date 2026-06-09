# FveConvSliderWorker

- ea: `0x14005cfc0`
- end: `0x14005d128`
- name: `FveConvSliderWorker`
- size: `360`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140008e80`
- `0x14005a27c`
- `0x14005ce08`
- `0x14005cfc0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14005d0c5`
- `ntoskrnl!KeReadStateEvent` at `0x14005d0c5`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14005d04e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14005d04e`
- `ntoskrnl!KeClearEvent` at `0x14005d09e`
- `ntoskrnl!KeClearEvent` at `0x14005d09e`
- `ntoskrnl!PsTerminateSystemThread` at `0x14005d111`
- `ntoskrnl!PsTerminateSystemThread` at `0x14005d111`
- `ntoskrnl!KeSetEvent` at `0x14005d0b6`
- `ntoskrnl!KeSetEvent` at `0x14005d0b6`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
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
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14005cfc0  push    rbx
0x14005cfc2  push    rsi
0x14005cfc3  push    rdi
0x14005cfc4  push    r13
0x14005cfc6  sub     rsp, 58h
0x14005cfca  xorps   xmm0, xmm0
0x14005cfcd  mov     rbx, rcx
0x14005cfd0  movups  xmmword ptr [rsp+78h+Object], xmm0
0x14005cfd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cfdc  lea     r13, WPP_GLOBAL_Control
0x14005cfe3  cmp     rcx, r13
0x14005cfe6  jz      short loc_14005D00A
0x14005cfe8  mov     eax, [rcx+2Ch]
0x14005cfeb  test    al, 2
0x14005cfed  jz      short loc_14005D00A
0x14005cfef  cmp     byte ptr [rcx+29h], 5
0x14005cff3  jb      short loc_14005D00A
0x14005cff5  mov     rcx, [rcx+18h]
0x14005cff9  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x14005d000  mov     edx, 8Ah
0x14005d005  call    WPP_SF_
0x14005d00a  lea     rsi, [rbx+1D0h]
0x14005d011  lea     rdi, [rbx+1B8h]
0x14005d018  mov     [rsp+78h+Object], rsi
0x14005d01d  mov     [rsp+78h+Object+8], rdi
0x14005d022  xor     r9d, r9d; WaitReason
0x14005d025  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14005d02e  mov     [rsp+78h+Timeout], 0; Timeout
0x14005d037  lea     rdx, [rsp+78h+Object]; Object
0x14005d03c  mov     [rsp+78h+Alertable], 0; Alertable
0x14005d041  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14005d046  lea     r8d, [r9+1]; WaitType
0x14005d04a  lea     ecx, [r9+2]; Count
0x14005d04e  call    cs:__imp_KeWaitForMultipleObjects
0x14005d055  nop     dword ptr [rax+rax+00h]
0x14005d05a  test    eax, eax
0x14005d05c  jz      short loc_14005D093
0x14005d05e  cmp     eax, 1
0x14005d061  jnz     short loc_14005D0C2
0x14005d063  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d06a  cmp     rcx, r13
0x14005d06d  jz      short loc_14005D0C2
0x14005d06f  mov     eax, [rcx+2Ch]
0x14005d072  test    al, 2
0x14005d074  jz      short loc_14005D0C2
0x14005d076  cmp     byte ptr [rcx+29h], 5
0x14005d07a  jb      short loc_14005D0C2
0x14005d07c  mov     rcx, [rcx+18h]
0x14005d080  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x14005d087  mov     edx, 8Bh
0x14005d08c  call    WPP_SF_
0x14005d091  jmp     short loc_14005D0C2
0x14005d093  mov     rcx, rbx
0x14005d096  call    FveConvSliderMove
0x14005d09b  mov     rcx, rsi; Event
0x14005d09e  call    cs:__imp_KeClearEvent
0x14005d0a5  nop     dword ptr [rax+rax+00h]
0x14005d0aa  lea     rcx, [rbx+1E8h]; Event
0x14005d0b1  xor     r8d, r8d; Wait
0x14005d0b4  xor     edx, edx; Increment
0x14005d0b6  call    cs:__imp_KeSetEvent
0x14005d0bd  nop     dword ptr [rax+rax+00h]
0x14005d0c2  mov     rcx, rdi; Event
0x14005d0c5  call    cs:__imp_KeReadStateEvent
0x14005d0cc  nop     dword ptr [rax+rax+00h]
0x14005d0d1  test    eax, eax
0x14005d0d3  jz      loc_14005D022
0x14005d0d9  mov     rcx, rbx; P
0x14005d0dc  call    FveConvFreeControl
0x14005d0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d0e8  cmp     rcx, r13
0x14005d0eb  jz      short loc_14005D10F
0x14005d0ed  mov     eax, [rcx+2Ch]
0x14005d0f0  test    al, 2
0x14005d0f2  jz      short loc_14005D10F
0x14005d0f4  cmp     byte ptr [rcx+29h], 5
0x14005d0f8  jb      short loc_14005D10F
0x14005d0fa  mov     rcx, [rcx+18h]
0x14005d0fe  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x14005d105  mov     edx, 8Ch
0x14005d10a  call    WPP_SF_
0x14005d10f  xor     ecx, ecx; ExitStatus
0x14005d111  call    cs:__imp_PsTerminateSystemThread
0x14005d118  nop     dword ptr [rax+rax+00h]
0x14005d11d  add     rsp, 58h
0x14005d121  pop     r13
0x14005d123  pop     rdi
0x14005d124  pop     rsi
0x14005d125  pop     rbx
0x14005d126  retn
```
