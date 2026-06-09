# HIDSM_SettingIoStateToFailAndFlushSentIoOnRemove

- ea: `0x1800131f0`
- end: `0x180013206`
- name: `HIDSM_SettingIoStateToFailAndFlushSentIoOnRemove`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001320c`

## pseudocode

```c
__int64 __fastcall HIDSM_SettingIoStateToFailAndFlushSentIoOnRemove(__int64 a1)
{
  return HidpFdoSetIoStateToFailAndFlushSentIo(*(_QWORD *)(a1 + 960));
}

```

## disassembly

```asm
0x1800131f0  sub     rsp, 28h
0x1800131f4  mov     rcx, [rcx+3C0h]
0x1800131fb  call    HidpFdoSetIoStateToFailAndFlushSentIo
0x180013200  add     rsp, 28h
0x180013204  retn
```
