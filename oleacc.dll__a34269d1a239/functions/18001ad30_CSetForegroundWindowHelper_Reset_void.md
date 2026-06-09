# CSetForegroundWindowHelper::Reset(void)

- ea: `0x18001ad30`
- end: `0x18001ad91`
- name: `?Reset@CSetForegroundWindowHelper@@AEAAXXZ`
- size: `97`
- prototype: `void __fastcall(CSetForegroundWindowHelper *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800476bc`
- `0x180048a40`

## callees

- `0x18001ad30`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ad69`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ad69`
- `USER32!UnregisterHotKey` at `0x18001ad5f`
- `USER32!UnregisterHotKey` at `0x18001ad5f`
- `USER32!KillTimer` at `0x18001ad7d`
- `USER32!KillTimer` at `0x18001ad7d`
- `USER32!DestroyWindow` at `0x18001ad86`
- `USER32!DestroyWindow` at `0x18001ad86`

## pseudocode

```c
void __fastcall CSetForegroundWindowHelper::Reset(CSetForegroundWindowHelper *this)
{
  if ( *((_WORD *)this + 4) )
  {
    UnregisterHotKey(*(HWND *)this, *((unsigned __int16 *)this + 4));
    GlobalDeleteAtom(*((_WORD *)this + 4));
    *((_DWORD *)this + 2) = 12124160;
  }
  if ( *(_QWORD *)this )
  {
    KillTimer(*(HWND *)this, 1u);
    DestroyWindow(*(HWND *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18001ad30  mov     [rsp+arg_0], rbx
0x18001ad35  push    rdi
0x18001ad36  sub     rsp, 20h
0x18001ad3a  xor     edi, edi
0x18001ad3c  mov     rbx, rcx
0x18001ad3f  cmp     [rcx+8], di
0x18001ad43  jnz     short loc_18001AD58
0x18001ad45  mov     rcx, [rbx]; hWnd
0x18001ad48  test    rcx, rcx
0x18001ad4b  jnz     short loc_18001AD78
0x18001ad4d  mov     rbx, [rsp+28h+arg_0]
0x18001ad52  add     rsp, 20h
0x18001ad56  pop     rdi
0x18001ad57  retn
0x18001ad58  movzx   edx, word ptr [rcx+8]; id
0x18001ad5c  mov     rcx, [rcx]; hWnd
0x18001ad5f  call    cs:__imp_UnregisterHotKey
0x18001ad65  movzx   ecx, word ptr [rbx+8]; nAtom
0x18001ad69  call    cs:__imp_GlobalDeleteAtom
0x18001ad6f  mov     dword ptr [rbx+8], 0B90000h
0x18001ad76  jmp     short loc_18001AD45
0x18001ad78  mov     edx, 1; uIDEvent
0x18001ad7d  call    cs:__imp_KillTimer
0x18001ad83  mov     rcx, [rbx]; hWnd
0x18001ad86  call    cs:__imp_DestroyWindow
0x18001ad8c  mov     [rbx], rdi
0x18001ad8f  jmp     short loc_18001AD4D
```
