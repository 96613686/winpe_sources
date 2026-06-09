# NatTriggerTimer

- ea: `0x14001f794`
- end: `0x14001f862`
- name: `NatTriggerTimer`
- size: `206`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400060c0`
- `0x14000d50c`
- `0x140017718`
- `0x140020580`
- `0x140020970`
- `0x140021150`
- `0x140022d70`
- `0x140023160`
- `0x140023940`

## callees

- `0x14000218c`
- `0x14001f794`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x14001f81c`
- `ntoskrnl!KeInsertQueueDpc` at `0x14001f81c`

## pseudocode

```c
char NatTriggerTimer()
{
  signed __int32 Timer_high; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Bu,
      (__int64)WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
  }
  Timer_high = _InterlockedCompareExchange(&CleanupDpcPending, 1, 0);
  if ( !Timer_high )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Cu,
        (__int64)WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
    }
    LOBYTE(Timer_high) = KeInsertQueueDpc(&CleanupDpcObject, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      LOBYTE(Timer_high) = WPP_SF_(
                             (__int64)WPP_GLOBAL_Control->AttachedDevice,
                             0x1Du,
                             (__int64)WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
  }
  return Timer_high;
}

```

## disassembly

```asm
0x14001f794  mov     [rsp+arg_0], rbx
0x14001f799  push    rdi
0x14001f79a  sub     rsp, 20h
0x14001f79e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f7a5  lea     rdi, WPP_GLOBAL_Control
0x14001f7ac  mov     ebx, 1
0x14001f7b1  cmp     rcx, rdi
0x14001f7b4  jz      short loc_14001F7D6
0x14001f7b6  mov     eax, [rcx+2Ch]
0x14001f7b9  test    bl, al
0x14001f7bb  jz      short loc_14001F7D6
0x14001f7bd  cmp     byte ptr [rcx+29h], 6
0x14001f7c1  jb      short loc_14001F7D6
0x14001f7c3  mov     rcx, [rcx+18h]
0x14001f7c7  lea     edx, [rbx+1Ah]
0x14001f7ca  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f7d1  call    WPP_SF_
0x14001f7d6  xor     eax, eax
0x14001f7d8  lock cmpxchg cs:CleanupDpcPending, ebx
0x14001f7e0  jnz     short loc_14001F828
0x14001f7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f7e9  cmp     rcx, rdi
0x14001f7ec  jz      short loc_14001F810
0x14001f7ee  mov     eax, [rcx+2Ch]
0x14001f7f1  test    bl, al
0x14001f7f3  jz      short loc_14001F810
0x14001f7f5  cmp     byte ptr [rcx+29h], 5
0x14001f7f9  jb      short loc_14001F810
0x14001f7fb  mov     rcx, [rcx+18h]
0x14001f7ff  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f806  mov     edx, 1Ch
0x14001f80b  call    WPP_SF_
0x14001f810  xor     r8d, r8d; SystemArgument2
0x14001f813  lea     rcx, CleanupDpcObject; Dpc
0x14001f81a  xor     edx, edx; SystemArgument1
0x14001f81c  call    cs:__imp_KeInsertQueueDpc
0x14001f823  nop     dword ptr [rax+rax+00h]
0x14001f828  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f82f  cmp     rcx, rdi
0x14001f832  jz      short loc_14001F856
0x14001f834  mov     eax, [rcx+2Ch]
0x14001f837  test    bl, al
0x14001f839  jz      short loc_14001F856
0x14001f83b  cmp     byte ptr [rcx+29h], 6
0x14001f83f  jb      short loc_14001F856
0x14001f841  mov     rcx, [rcx+18h]
0x14001f845  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f84c  mov     edx, 1Dh
0x14001f851  call    WPP_SF_
0x14001f856  mov     rbx, [rsp+28h+arg_0]
0x14001f85b  add     rsp, 20h
0x14001f85f  pop     rdi
0x14001f860  retn
```
