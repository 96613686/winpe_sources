# COskNativeHWNDHost::CacheForegroundWindowHandle(void)

- ea: `0x1400144ac`
- end: `0x1400144f3`
- name: `?CacheForegroundWindowHandle@COskNativeHWNDHost@@AEAAXXZ`
- size: `71`
- prototype: `void __fastcall(COskNativeHWNDHost *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140014f60`
- `0x140015d58`
- `0x140016a5c`

## callees

- `0x1400144ac`

## import_xrefs

- `USER32!GetForegroundWindow` at `0x1400144b9`
- `USER32!GetForegroundWindow` at `0x1400144b9`
- `USER32!IsWindow` at `0x1400144d8`
- `USER32!IsWindow` at `0x1400144d8`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400144ca`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400144ca`

## pseudocode

```c
void __fastcall COskNativeHWNDHost::CacheForegroundWindowHandle(COskNativeHWNDHost *this)
{
  HWND ForegroundWindow; // rbx

  ForegroundWindow = GetForegroundWindow();
  if ( !ForegroundWindow || ForegroundWindow == DirectUI::NativeHWNDHost::GetHWND(this) || !IsWindow(ForegroundWindow) )
    ForegroundWindow = 0;
  *((_QWORD *)this + 7) = ForegroundWindow;
}

```

## disassembly

```asm
0x1400144ac  mov     [rsp+arg_0], rbx
0x1400144b1  push    rdi
0x1400144b2  sub     rsp, 20h
0x1400144b6  mov     rdi, rcx
0x1400144b9  call    cs:__imp_GetForegroundWindow
0x1400144bf  mov     rbx, rax
0x1400144c2  test    rax, rax
0x1400144c5  jz      short loc_1400144E2
0x1400144c7  mov     rcx, rdi
0x1400144ca  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1400144d0  cmp     rbx, rax
0x1400144d3  jz      short loc_1400144E2
0x1400144d5  mov     rcx, rbx; hWnd
0x1400144d8  call    cs:__imp_IsWindow
0x1400144de  test    eax, eax
0x1400144e0  jnz     short loc_1400144E4
0x1400144e2  xor     ebx, ebx
0x1400144e4  mov     [rdi+38h], rbx
0x1400144e8  mov     rbx, [rsp+28h+arg_0]
0x1400144ed  add     rsp, 20h
0x1400144f1  pop     rdi
0x1400144f2  retn
```
