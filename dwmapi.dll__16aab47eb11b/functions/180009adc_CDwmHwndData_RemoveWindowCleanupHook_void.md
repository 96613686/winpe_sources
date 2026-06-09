# CDwmHwndData::RemoveWindowCleanupHook(void)

- ea: `0x180009adc`
- end: `0x180009b02`
- name: `?RemoveWindowCleanupHook@CDwmHwndData@@SAXXZ`
- size: `38`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`

## callees

- `0x180009adc`

## import_xrefs

- `USER32!UnhookWinEvent` at `0x180009aec`
- `USER32!UnhookWinEvent` at `0x180009aec`

## pseudocode

```c
void CDwmHwndData::RemoveWindowCleanupHook(void)
{
  if ( CDwmHwndData::s_hCleanupHook )
  {
    UnhookWinEvent(CDwmHwndData::s_hCleanupHook);
    CDwmHwndData::s_hCleanupHook = 0;
  }
}

```

## disassembly

```asm
0x180009adc  sub     rsp, 28h
0x180009ae0  mov     rcx, cs:?s_hCleanupHook@CDwmHwndData@@0PEAUHWINEVENTHOOK__@@EA; hWinEventHook
0x180009ae7  test    rcx, rcx
0x180009aea  jz      short loc_180009AFD
0x180009aec  call    cs:__imp_UnhookWinEvent
0x180009af2  mov     cs:?s_hCleanupHook@CDwmHwndData@@0PEAUHWINEVENTHOOK__@@EA, 0; HWINEVENTHOOK__ * CDwmHwndData::s_hCleanupHook
0x180009afd  add     rsp, 28h
0x180009b01  retn
```
