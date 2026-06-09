# RfcommStopTimerLocked

- ea: `0x1400038fc`
- end: `0x14000396a`
- name: `RfcommStopTimerLocked`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ec8`
- `0x140014210`
- `0x140018230`

## callees

- `0x1400038fc`
- `0x140004a68`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14000391c`
- `ntoskrnl!KeCancelTimer` at `0x14000391c`

## pseudocode

```c
_UNKNOWN **__fastcall RfcommStopTimerLocked(__int64 a1)
{
  int v2; // edx
  _UNKNOWN **result; // rax

  if ( *(_BYTE *)(a1 + 264) )
  {
    *(_BYTE *)(a1 + 264) = 0;
    KeCancelTimer((PKTIMER)(a1 + 136));
    result = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (_UNKNOWN **)WPP_RECORDER_SF_q(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v2,
                            31,
                            115,
                            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
                            a1);
  }
  return result;
}

```

## disassembly

```asm
0x1400038fc  push    rbx
0x1400038fe  sub     rsp, 30h
0x140003902  cmp     byte ptr [rcx+108h], 0
0x140003909  mov     rbx, rcx
0x14000390c  jz      short loc_140003963
0x14000390e  mov     byte ptr [rcx+108h], 0
0x140003915  add     rcx, 88h; PKTIMER
0x14000391c  call    cs:__imp_KeCancelTimer
0x140003923  nop     dword ptr [rax+rax+00h]
0x140003928  lea     rax, WPP_RECORDER_INITIALIZED
0x14000392f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003936  jz      short loc_140003963
0x140003938  mov     rcx, cs:WPP_GLOBAL_Control
0x14000393f  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140003946  mov     r9d, 73h ; 's'
0x14000394c  mov     [rsp+38h+var_10], rbx
0x140003951  mov     [rsp+38h+var_18], rax
0x140003956  mov     rcx, [rcx+40h]
0x14000395a  lea     r8d, [r9-54h]
0x14000395e  call    WPP_RECORDER_SF_q
0x140003963  add     rsp, 30h
0x140003967  pop     rbx
0x140003968  retn
```
