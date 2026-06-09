# WPP_RECORDER_SF_sd

- ea: `0x140008f88`
- end: `0x14000904c`
- name: `WPP_RECORDER_SF_sd`
- size: `196`
- prototype: `__int64(__int64, int, int, USHORT, LPCGUID MessageGuid, int, ...)`
- caller_count: `51`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a88`
- `0x140008b5c`
- `0x140008d7c`
- `0x140009180`
- `0x140009328`
- `0x1400095a0`
- `0x1400096e0`
- `0x140009850`
- `0x140009be0`
- `0x140009e3c`
- `0x14000a268`
- `0x14000a4f4`
- `0x14000a920`
- `0x14000aae0`
- `0x14000acf0`
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
- `0x14000cdac`
- `0x14000ceec`
- `0x14000d020`
- `0x14000d110`
- `0x14000d1f0`
- `0x14000d590`
- `0x14000d880`
- `0x14000d930`
- `0x14000da80`
- `0x14000dbe0`
- `0x14000de10`
- `0x14000deb0`
- `0x14000e0d0`
- `0x14000e1a0`
- `0x14000e2c0`
- `0x14000f6c0`
- `0x14000fea4`

## callees

- `0x140008f88`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140008fec`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140008fec`
- `WppRecorderUM!WppAutoLogTrace` at `0x140009035`
- `WppRecorderUM!WppAutoLogTrace` at `0x140009035`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sd(__int64 a1, int a2, int a3, USHORT a4, LPCGUID MessageGuid, int a6, ...)
{
  int v9; // [rsp+20h] [rbp-38h]
  va_list va; // [rsp+90h] [rbp+38h] BYREF

  va_start(va, a6);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    TraceMessage(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Bu, MessageGuid, a4, " ", 2, va, 4, 0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, MessageGuid, v9, " ", 2, va);
}

```

## disassembly

```asm
0x140008f88  mov     r11, rsp
0x140008f8b  mov     [r11+8], rbx
0x140008f8f  mov     [r11+10h], rdi
0x140008f93  push    r14
0x140008f95  sub     rsp, 50h
0x140008f99  mov     rdi, rcx
0x140008f9c  movzx   ebx, r9w
0x140008fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fa7  lea     r14, asc_140022F28; " "
0x140008fae  test    byte ptr [rcx+1Ch], 1
0x140008fb2  jz      short loc_140008FF2
0x140008fb4  mov     r8, [rsp+58h+MessageGuid]; MessageGuid
0x140008fbc  lea     rax, [r11+38h]
0x140008fc0  mov     rcx, [rcx+10h]; LoggerHandle
0x140008fc4  mov     r9d, ebx; MessageNumber
0x140008fc7  mov     qword ptr [r11-18h], 0
0x140008fcf  mov     edx, 2Bh ; '+'; MessageFlags
0x140008fd4  mov     qword ptr [r11-20h], 4
0x140008fdc  mov     [r11-28h], rax
0x140008fe0  mov     qword ptr [r11-30h], 2
0x140008fe8  mov     [r11-38h], r14
0x140008fec  call    cs:__imp_TraceMessage
0x140008ff2  mov     r9, [rsp+58h+MessageGuid]
0x140008ffa  lea     rax, [rsp+58h+arg_30]
0x140009002  mov     [rsp+58h+var_10], 0
0x14000900b  xor     edx, edx
0x14000900d  mov     [rsp+58h+var_18], 4
0x140009016  mov     rcx, rdi
0x140009019  mov     [rsp+58h+var_20], rax
0x14000901e  mov     [rsp+58h+var_28], 2
0x140009027  lea     r8d, [rdx+1]
0x14000902b  mov     [rsp+58h+var_30], r14
0x140009030  mov     [rsp+58h+var_38], bx
0x140009035  call    cs:__imp_WppAutoLogTrace
0x14000903b  mov     rbx, [rsp+58h+arg_0]
0x140009040  mov     rdi, [rsp+58h+arg_8]
0x140009045  add     rsp, 50h
0x140009049  pop     r14
0x14000904b  retn
```
