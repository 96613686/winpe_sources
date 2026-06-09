# RfcommStartTimerLocked

- ea: `0x140003868`
- end: `0x1400038f5`
- name: `RfcommStartTimerLocked`
- size: `141`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003818`
- `0x140017704`
- `0x140018e9c`

## callees

- `0x140003868`
- `0x140004a68`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x1400038a7`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400038a7`

## pseudocode

```c
_UNKNOWN **__fastcall RfcommStartTimerLocked(__int64 a1)
{
  int v2; // edx
  _UNKNOWN **result; // rax

  if ( !*(_BYTE *)(a1 + 264) )
  {
    *(_BYTE *)(a1 + 264) = 1;
    KeSetCoalescableTimer((PKTIMER)(a1 + 136), (LARGE_INTEGER)-10000000LL, 0x3E8u, 0x23u, (PKDPC)(a1 + 200));
    result = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (_UNKNOWN **)WPP_RECORDER_SF_q(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v2,
                            31,
                            114,
                            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
                            a1);
  }
  return result;
}

```

## disassembly

```asm
0x140003868  push    rbx
0x14000386a  sub     rsp, 30h
0x14000386e  cmp     byte ptr [rcx+108h], 0
0x140003875  mov     rbx, rcx
0x140003878  jnz     short loc_1400038EE
0x14000387a  lea     rax, [rcx+0C8h]
0x140003881  mov     byte ptr [rcx+108h], 1
0x140003888  add     rcx, 88h; Timer
0x14000388f  mov     [rsp+38h+Dpc], rax; Dpc
0x140003894  mov     rdx, 0FFFFFFFFFF676980h; DueTime
0x14000389b  mov     r9d, 23h ; '#'; TolerableDelay
0x1400038a1  mov     r8d, 3E8h; Period
0x1400038a7  call    cs:__imp_KeSetCoalescableTimer
0x1400038ae  nop     dword ptr [rax+rax+00h]
0x1400038b3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400038ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400038c1  jz      short loc_1400038EE
0x1400038c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038ca  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400038d1  mov     r9d, 72h ; 'r'
0x1400038d7  mov     [rsp+38h+var_10], rbx
0x1400038dc  mov     [rsp+38h+Dpc], rax
0x1400038e1  mov     rcx, [rcx+40h]
0x1400038e5  lea     r8d, [r9-53h]
0x1400038e9  call    WPP_RECORDER_SF_q
0x1400038ee  add     rsp, 30h
0x1400038f2  pop     rbx
0x1400038f3  retn
```
