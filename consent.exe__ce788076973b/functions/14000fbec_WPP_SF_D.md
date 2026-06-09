# WPP_SF_D

- ea: `0x14000fbec`
- end: `0x14000fc23`
- name: `WPP_SF_D`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `36`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140003820`
- `0x140003b00`
- `0x140003e40`
- `0x140004ab0`
- `0x140004fb8`
- `0x140005040`
- `0x140005260`
- `0x1400056a0`
- `0x140005a80`
- `0x140005d40`
- `0x1400061a0`
- `0x140006a30`
- `0x140006d00`
- `0x140006fd0`
- `0x140008480`
- `0x1400095c0`
- `0x140009950`
- `0x14000a280`
- `0x14000af70`
- `0x14000b820`
- `0x14000c350`
- `0x14000cfdc`
- `0x14000eee4`
- `0x14000f5b4`
- `0x14000f7dc`
- `0x14000f8c0`
- `0x14000fdc4`
- `0x140015c28`
- `0x140015d68`
- `0x14001700c`
- `0x140019038`
- `0x140019ac4`
- `0x140019f40`
- `0x14001a080`
- `0x14001adb0`
- `0x14001e3bf`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x14000fc18`
- `ntdll!EtwTraceMessage` at `0x14000fc18`

## pseudocode

```c
__int64 __fastcall WPP_SF_D(__int64 a1, __int64 a2, __int64 a3)
{
  return EtwTraceMessage(a1, 43, a3);
}

```

## disassembly

```asm
0x14000fbec  mov     r11, rsp
0x14000fbef  mov     [r11+20h], r9d
0x14000fbf3  sub     rsp, 48h
0x14000fbf7  mov     qword ptr [r11-18h], 0
0x14000fbff  lea     rax, [r11+20h]
0x14000fc03  movzx   r9d, dx
0x14000fc07  mov     edx, 2Bh ; '+'
0x14000fc0c  mov     qword ptr [r11-20h], 4
0x14000fc14  mov     [r11-28h], rax
0x14000fc18  call    cs:__imp_EtwTraceMessage
0x14000fc1e  add     rsp, 48h
0x14000fc22  retn
```
