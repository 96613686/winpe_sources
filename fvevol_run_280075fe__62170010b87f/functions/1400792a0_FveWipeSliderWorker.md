# FveWipeSliderWorker

- ea: `0x1400792a0`
- end: `0x14007940c`
- name: `FveWipeSliderWorker`
- size: `364`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140008dc0`
- `0x140077a10`
- `0x140079004`
- `0x1400792a0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400793a7`
- `ntoskrnl!KeReadStateEvent` at `0x1400793a7`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140079330`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140079330`
- `ntoskrnl!KeClearEvent` at `0x140079380`
- `ntoskrnl!KeClearEvent` at `0x140079380`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400793f5`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400793f5`
- `ntoskrnl!KeSetEvent` at `0x140079398`
- `ntoskrnl!KeSetEvent` at `0x140079398`

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
0x1400792a0  push    rbx
0x1400792a2  push    rsi
0x1400792a3  push    rdi
0x1400792a4  push    r12
0x1400792a6  sub     rsp, 58h
0x1400792aa  xorps   xmm0, xmm0
0x1400792ad  mov     rbx, rcx
0x1400792b0  movups  xmmword ptr [rsp+78h+Object], xmm0
0x1400792b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400792bc  lea     r12, WPP_GLOBAL_Control
0x1400792c3  cmp     rcx, r12
0x1400792c6  jz      short loc_1400792EC
0x1400792c8  test    dword ptr [rcx+2Ch], 1000h
0x1400792cf  jz      short loc_1400792EC
0x1400792d1  cmp     byte ptr [rcx+29h], 5
0x1400792d5  jb      short loc_1400792EC
0x1400792d7  mov     rcx, [rcx+18h]
0x1400792db  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x1400792e2  mov     edx, 3Bh ; ';'
0x1400792e7  call    WPP_SF_
0x1400792ec  lea     rsi, [rbx+150h]
0x1400792f3  lea     rdi, [rbx+138h]
0x1400792fa  mov     [rsp+78h+Object], rsi
0x1400792ff  mov     [rsp+78h+Object+8], rdi
0x140079304  xor     r9d, r9d; WaitReason
0x140079307  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x140079310  mov     [rsp+78h+Timeout], 0; Timeout
0x140079319  lea     rdx, [rsp+78h+Object]; Object
0x14007931e  mov     [rsp+78h+Alertable], 0; Alertable
0x140079323  mov     [rsp+78h+WaitMode], 0; WaitMode
0x140079328  lea     r8d, [r9+1]; WaitType
0x14007932c  lea     ecx, [r9+2]; Count
0x140079330  call    cs:__imp_KeWaitForMultipleObjects
0x140079337  nop     dword ptr [rax+rax+00h]
0x14007933c  test    eax, eax
0x14007933e  jz      short loc_140079375
0x140079340  cmp     eax, 1
0x140079343  jnz     short loc_1400793A4
0x140079345  mov     rcx, cs:WPP_GLOBAL_Control
0x14007934c  cmp     rcx, r12
0x14007934f  jz      short loc_1400793A4
0x140079351  mov     eax, [rcx+2Ch]
0x140079354  test    al, 2
0x140079356  jz      short loc_1400793A4
0x140079358  cmp     byte ptr [rcx+29h], 5
0x14007935c  jb      short loc_1400793A4
0x14007935e  mov     rcx, [rcx+18h]
0x140079362  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x140079369  mov     edx, 3Ch ; '<'
0x14007936e  call    WPP_SF_
0x140079373  jmp     short loc_1400793A4
0x140079375  mov     rcx, rbx
0x140079378  call    FveWipeSliderMove
0x14007937d  mov     rcx, rsi; Event
0x140079380  call    cs:__imp_KeClearEvent
0x140079387  nop     dword ptr [rax+rax+00h]
0x14007938c  lea     rcx, [rbx+168h]; Event
0x140079393  xor     r8d, r8d; Wait
0x140079396  xor     edx, edx; Increment
0x140079398  call    cs:__imp_KeSetEvent
0x14007939f  nop     dword ptr [rax+rax+00h]
0x1400793a4  mov     rcx, rdi; Event
0x1400793a7  call    cs:__imp_KeReadStateEvent
0x1400793ae  nop     dword ptr [rax+rax+00h]
0x1400793b3  test    eax, eax
0x1400793b5  jz      loc_140079304
0x1400793bb  mov     rcx, rbx; P
0x1400793be  call    FveWipeFreeControl
0x1400793c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400793ca  cmp     rcx, r12
0x1400793cd  jz      short loc_1400793F3
0x1400793cf  test    dword ptr [rcx+2Ch], 1000h
0x1400793d6  jz      short loc_1400793F3
0x1400793d8  cmp     byte ptr [rcx+29h], 5
0x1400793dc  jb      short loc_1400793F3
0x1400793de  mov     rcx, [rcx+18h]
0x1400793e2  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x1400793e9  mov     edx, 3Dh ; '='
0x1400793ee  call    WPP_SF_
0x1400793f3  xor     ecx, ecx; ExitStatus
0x1400793f5  call    cs:__imp_PsTerminateSystemThread
0x1400793fc  nop     dword ptr [rax+rax+00h]
0x140079401  add     rsp, 58h
0x140079405  pop     r12
0x140079407  pop     rdi
0x140079408  pop     rsi
0x140079409  pop     rbx
0x14007940a  retn
```
