# WPP_RECORDER_SF_s

- ea: `0x140008eec`
- end: `0x140008f82`
- name: `WPP_RECORDER_SF_s`
- size: `150`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, USHORT, LPCGUID MessageGuid)`
- caller_count: `61`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a88`
- `0x140008b5c`
- `0x140008d7c`
- `0x1400090c0`
- `0x140009180`
- `0x140009240`
- `0x140009328`
- `0x1400095a0`
- `0x1400096e0`
- `0x140009850`
- `0x140009b60`
- `0x140009be0`
- `0x140009cd8`
- `0x140009e3c`
- `0x14000a268`
- `0x14000a380`
- `0x14000a450`
- `0x14000a4f4`
- `0x14000a920`
- `0x14000aae0`
- `0x14000acf0`
- `0x14000adb0`
- `0x14000afa4`
- `0x14000b3c0`
- `0x14000b494`
- `0x14000b5d4`
- `0x14000b7c4`
- `0x14000b994`
- `0x14000bacc`
- `0x14000bbac`
- `0x14000bc74`
- `0x14000bef0`
- `0x14000bf80`
- `0x14000c350`
- `0x14000c6b0`
- `0x14000c760`
- `0x14000c840`
- `0x14000c970`
- `0x14000ca90`
- `0x14000cb50`
- `0x14000cc70`
- `0x14000cdac`
- `0x14000ceec`
- `0x14000d020`
- `0x14000d110`
- `0x14000d1f0`
- `0x14000d590`
- `0x14000d800`
- `0x14000d880`
- `0x14000d930`

## callees

- `0x140008eec`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140008f3c`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140008f3c`
- `WppRecorderUM!WppAutoLogTrace` at `0x140008f6c`
- `WppRecorderUM!WppAutoLogTrace` at `0x140008f6c`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_s(__int64 a1, __int64 a2, __int64 a3, USHORT a4, LPCGUID MessageGuid)
{
  int v8; // [rsp+20h] [rbp-28h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    TraceMessage(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Bu, MessageGuid, a4, " ", 2, 0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 0, 1, MessageGuid, v8, " ", 2, 0);
}

```

## disassembly

```asm
0x140008eec  mov     rax, rsp
0x140008eef  mov     [rax+8], rbx
0x140008ef3  mov     [rax+10h], rbp
0x140008ef7  push    rdi
0x140008ef8  sub     rsp, 40h
0x140008efc  mov     rdi, rcx
0x140008eff  movzx   ebx, r9w
0x140008f03  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f0a  lea     rbp, asc_140022F28; " "
0x140008f11  test    byte ptr [rcx+1Ch], 1
0x140008f15  jz      short loc_140008F42
0x140008f17  mov     r8, [rsp+48h+MessageGuid]; MessageGuid
0x140008f1c  mov     r9d, ebx; MessageNumber
0x140008f1f  mov     rcx, [rcx+10h]; LoggerHandle
0x140008f23  mov     edx, 2Bh ; '+'; MessageFlags
0x140008f28  mov     qword ptr [rax-18h], 0
0x140008f30  mov     qword ptr [rax-20h], 2
0x140008f38  mov     [rax-28h], rbp
0x140008f3c  call    cs:__imp_TraceMessage
0x140008f42  mov     r9, [rsp+48h+MessageGuid]
0x140008f47  xor     edx, edx
0x140008f49  mov     [rsp+48h+var_10], 0
0x140008f52  mov     rcx, rdi
0x140008f55  mov     [rsp+48h+var_18], 2
0x140008f5e  mov     [rsp+48h+var_20], rbp
0x140008f63  lea     r8d, [rdx+1]
0x140008f67  mov     [rsp+48h+var_28], bx
0x140008f6c  call    cs:__imp_WppAutoLogTrace
0x140008f72  mov     rbx, [rsp+48h+arg_0]
0x140008f77  mov     rbp, [rsp+48h+arg_8]
0x140008f7c  add     rsp, 40h
0x140008f80  pop     rdi
0x140008f81  retn
```
