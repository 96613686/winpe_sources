# CSchedulePage::_DeleteTimerToUpdateTriggerStr(void)

- ea: `0x180013850`
- end: `0x180013883`
- name: `?_DeleteTimerToUpdateTriggerStr@CSchedulePage@@AEAAXXZ`
- size: `51`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180015520`
- `0x1800158d0`
- `0x180015af0`

## callees

- `0x180013850`

## import_xrefs

- `USER32!KillTimer` at `0x18001386c`
- `USER32!KillTimer` at `0x18001386c`

## pseudocode

```c
void __fastcall CSchedulePage::_DeleteTimerToUpdateTriggerStr(HWND *this)
{
  if ( this[93] )
  {
    KillTimer(this[14], 1u);
    this[93] = 0;
  }
}

```

## disassembly

```asm
0x180013850  push    rbx
0x180013852  sub     rsp, 20h
0x180013856  cmp     qword ptr [rcx+2E8h], 0
0x18001385e  mov     rbx, rcx
0x180013861  jz      short loc_18001387D
0x180013863  mov     rcx, [rcx+70h]; hWnd
0x180013867  mov     edx, 1; uIDEvent
0x18001386c  call    cs:__imp_KillTimer
0x180013872  mov     qword ptr [rbx+2E8h], 0
0x18001387d  add     rsp, 20h
0x180013881  pop     rbx
0x180013882  retn
```
