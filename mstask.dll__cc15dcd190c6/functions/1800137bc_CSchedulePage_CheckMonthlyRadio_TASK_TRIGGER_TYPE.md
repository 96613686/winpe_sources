# CSchedulePage::_CheckMonthlyRadio(_TASK_TRIGGER_TYPE)

- ea: `0x1800137bc`
- end: `0x180013808`
- name: `?_CheckMonthlyRadio@CSchedulePage@@AEAAXW4_TASK_TRIGGER_TYPE@@@Z`
- size: `76`
- prototype: `void __fastcall(CSchedulePage *__hidden this, enum _TASK_TRIGGER_TYPE)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180013c28`
- `0x180014aa0`
- `0x1800168a4`

## callees

- `0x1800137bc`

## import_xrefs

- `USER32!CheckDlgButton` at `0x1800137d9`
- `USER32!CheckDlgButton` at `0x1800137e7`
- `USER32!CheckDlgButton` at `0x1800137d9`
- `USER32!CheckDlgButton` at `0x1800137e7`
- `USER32!CheckDlgButton` at `0x180013801`

## pseudocode

```c
void __fastcall CSchedulePage::_CheckMonthlyRadio(CSchedulePage *this, enum _TASK_TRIGGER_TYPE a2)
{
  HWND v3; // rcx
  UINT v4; // r8d

  v3 = (HWND)*((_QWORD *)this + 14);
  if ( a2 == TASK_TIME_TRIGGER_MONTHLYDATE )
  {
    CheckDlgButton(v3, 1732, 1u);
    v4 = 0;
  }
  else
  {
    CheckDlgButton(v3, 1732, 0);
    v4 = 1;
  }
  CheckDlgButton(*((HWND *)this + 14), 1736, v4);
}

```

## disassembly

```asm
0x1800137bc  push    rbx
0x1800137be  sub     rsp, 20h
0x1800137c2  mov     rbx, rcx
0x1800137c5  cmp     edx, 3
0x1800137c8  mov     rcx, [rcx+70h]; hDlg
0x1800137cc  mov     edx, 6C4h; nIDButton
0x1800137d1  jnz     short loc_1800137E4
0x1800137d3  mov     r8d, 1; uCheck
0x1800137d9  call    cs:__imp_CheckDlgButton
0x1800137df  xor     r8d, r8d
0x1800137e2  jmp     short loc_1800137F3
0x1800137e4  xor     r8d, r8d; uCheck
0x1800137e7  call    cs:__imp_CheckDlgButton
0x1800137ed  mov     r8d, 1
0x1800137f3  mov     rcx, [rbx+70h]
0x1800137f7  mov     edx, 6C8h
0x1800137fc  add     rsp, 20h
0x180013800  pop     rbx
0x180013801  jmp     cs:__imp_CheckDlgButton
```
