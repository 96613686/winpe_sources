# CTimer::onTimeout(void)

- ea: `0x14000fbb0`
- end: `0x14000fc06`
- name: `?onTimeout@CTimer@@IEAAXXZ`
- size: `86`
- prototype: `void __fastcall(CTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007370`

## callees

- `0x14000f2a0`
- `0x14000fbb0`

## import_xrefs

- `USER32!KillTimer` at `0x14000fbc0`
- `USER32!KillTimer` at `0x14000fbc0`
- `USER32!EnumThreadWindows` at `0x14000fbf3`
- `USER32!EnumThreadWindows` at `0x14000fbf3`

## pseudocode

```c
void __fastcall CTimer::onTimeout(CTimer *this)
{
  CHost *v2; // rcx
  DWORD v3; // ecx
  LPARAM lParam; // [rsp+30h] [rbp+8h] BYREF

  KillTimer(*(HWND *)this, *((_QWORD *)this + 1));
  v2 = (CHost *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 1) = 0;
  CHost::Interrupt(v2, -2147155970);
  do
  {
    v3 = *((_DWORD *)this + 11);
    LODWORD(lParam) = 0;
    EnumThreadWindows(v3, enum_thread_windows, (LPARAM)&lParam);
  }
  while ( (_DWORD)lParam );
}

```

## disassembly

```asm
0x14000fbb0  push    rbx
0x14000fbb2  sub     rsp, 20h
0x14000fbb6  mov     rdx, [rcx+8]; uIDEvent
0x14000fbba  mov     rbx, rcx
0x14000fbbd  mov     rcx, [rcx]; hWnd
0x14000fbc0  call    cs:__imp_KillTimer
0x14000fbc6  mov     rcx, [rbx+10h]; this
0x14000fbca  mov     edx, 8004FFFEh; int
0x14000fbcf  mov     qword ptr [rbx+8], 0
0x14000fbd7  call    ?Interrupt@CHost@@QEAAJJ@Z; CHost::Interrupt(long)
0x14000fbdc  mov     ecx, [rbx+2Ch]; dwThreadId
0x14000fbdf  lea     r8, [rsp+28h+lParam]; lParam
0x14000fbe4  lea     rdx, enum_thread_windows; lpfn
0x14000fbeb  mov     dword ptr [rsp+28h+lParam], 0
0x14000fbf3  call    cs:__imp_EnumThreadWindows
0x14000fbf9  cmp     dword ptr [rsp+28h+lParam], 0
0x14000fbfe  jnz     short loc_14000FBDC
0x14000fc00  add     rsp, 20h
0x14000fc04  pop     rbx
0x14000fc05  retn
```
