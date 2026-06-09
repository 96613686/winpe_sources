# TdiConnStateLocked

- ea: `0x140007488`
- end: `0x1400074c9`
- name: `TdiConnStateLocked`
- size: `65`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006a04`
- `0x140006bc0`
- `0x140007350`
- `0x1400074d0`
- `0x14000877c`
- `0x140008ac0`
- `0x14000a060`

## callees

- `0x140007488`
- `0x14000c3b4`

## pseudocode

```c
__int64 __fastcall TdiConnStateLocked(__int64 a1, __int32 a2, int a3, int a4)
{
  unsigned __int32 v4; // ebx

  v4 = _InterlockedExchange((volatile __int32 *)(a1 + 80), a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qLL(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
  return v4;
}

```

## disassembly

```asm
0x140007488  push    rbx
0x14000748a  sub     rsp, 40h
0x14000748e  mov     ebx, edx
0x140007490  xchg    ebx, [rcx+50h]
0x140007493  lea     rax, WPP_RECORDER_INITIALIZED
0x14000749a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400074a1  jz      short loc_1400074C0
0x1400074a3  mov     [rsp+48h+var_10], edx
0x1400074a7  mov     [rsp+48h+var_18], ebx
0x1400074ab  mov     [rsp+48h+var_20], rcx
0x1400074b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074b7  mov     rcx, [rcx+40h]
0x1400074bb  call    WPP_RECORDER_SF_qLL
0x1400074c0  mov     eax, ebx
0x1400074c2  add     rsp, 40h
0x1400074c6  pop     rbx
0x1400074c7  retn
```
