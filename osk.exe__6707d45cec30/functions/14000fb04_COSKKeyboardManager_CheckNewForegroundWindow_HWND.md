# COSKKeyboardManager::CheckNewForegroundWindow(HWND__ *)

- ea: `0x14000fb04`
- end: `0x14000fbbe`
- name: `?CheckNewForegroundWindow@COSKKeyboardManager@@AEAAXPEAUHWND__@@@Z`
- size: `186`
- prototype: `void(COSKKeyboardManager *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140013e50`

## callees

- `0x14000fb04`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000fb40`
- `KERNEL32!GetCurrentProcessId` at `0x14000fb40`
- `KERNEL32!GetTickCount` at `0x14000fb55`
- `KERNEL32!GetTickCount` at `0x14000fba7`
- `KERNEL32!GetTickCount` at `0x14000fb55`
- `KERNEL32!GetTickCount` at `0x14000fba7`
- `USER32!SetWindowPos` at `0x14000fb9a`
- `USER32!SetWindowPos` at `0x14000fb9a`
- `USER32!GetWindowLongW` at `0x14000fb1c`
- `USER32!GetWindowLongW` at `0x14000fb1c`
- `USER32!GetWindowThreadProcessId` at `0x14000fb3a`
- `USER32!GetWindowThreadProcessId` at `0x14000fb3a`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14000fb6f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14000fb6f`

## pseudocode

```c
void __fastcall COSKKeyboardManager::CheckNewForegroundWindow(
        DirectUI::NativeHWNDHost **this,
        DirectUI::NativeHWNDHost *a2)
{
  HWND HWND; // rax
  DWORD dwProcessId; // [rsp+60h] [rbp+18h] BYREF

  if ( (GetWindowLongW((HWND)a2, -20) & 8) != 0 )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId((HWND)a2, &dwProcessId);
    if ( dwProcessId != GetCurrentProcessId() && (a2 != this[26] || GetTickCount() - *((_DWORD *)this + 54) > 0x3E8) )
    {
      HWND = DirectUI::NativeHWNDHost::GetHWND(this[16]);
      SetWindowPos(HWND, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x13u);
      this[26] = a2;
      *((_DWORD *)this + 54) = GetTickCount();
    }
  }
}

```

## disassembly

```asm
0x14000fb04  mov     [rsp+arg_0], rbx
0x14000fb09  push    rdi
0x14000fb0a  sub     rsp, 40h
0x14000fb0e  mov     rbx, rdx
0x14000fb11  mov     rdi, rcx
0x14000fb14  mov     rcx, rbx; hWnd
0x14000fb17  mov     edx, 0FFFFFFECh; nIndex
0x14000fb1c  call    cs:__imp_GetWindowLongW
0x14000fb22  test    al, 8
0x14000fb24  jz      loc_14000FBB3
0x14000fb2a  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x14000fb2f  mov     [rsp+48h+dwProcessId], 0
0x14000fb37  mov     rcx, rbx; hWnd
0x14000fb3a  call    cs:__imp_GetWindowThreadProcessId
0x14000fb40  call    cs:__imp_GetCurrentProcessId
0x14000fb46  cmp     [rsp+48h+dwProcessId], eax
0x14000fb4a  jz      short loc_14000FBB3
0x14000fb4c  cmp     rbx, [rdi+0D0h]
0x14000fb53  jnz     short loc_14000FB68
0x14000fb55  call    cs:__imp_GetTickCount
0x14000fb5b  sub     eax, [rdi+0D8h]
0x14000fb61  cmp     eax, 3E8h
0x14000fb66  jbe     short loc_14000FBB3
0x14000fb68  mov     rcx, [rdi+80h]
0x14000fb6f  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x14000fb75  mov     [rsp+48h+uFlags], 13h; uFlags
0x14000fb7d  xor     r9d, r9d; Y
0x14000fb80  mov     rcx, rax; hWnd
0x14000fb83  mov     [rsp+48h+cy], 0; cy
0x14000fb8b  xor     r8d, r8d; X
0x14000fb8e  mov     [rsp+48h+var_28], 0; cx
0x14000fb96  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x14000fb9a  call    cs:__imp_SetWindowPos
0x14000fba0  mov     [rdi+0D0h], rbx
0x14000fba7  call    cs:__imp_GetTickCount
0x14000fbad  mov     [rdi+0D8h], eax
0x14000fbb3  mov     rbx, [rsp+48h+arg_0]
0x14000fbb8  add     rsp, 40h
0x14000fbbc  pop     rdi
0x14000fbbd  retn
```
