# EndDlgPage(HWND__ * const,int)

- ea: `0x180007998`
- end: `0x180007a61`
- name: `?EndDlgPage@@YAXQEAUHWND__@@H@Z`
- size: `201`
- prototype: `void __fastcall(HWND hWnd, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009980`
- `0x18000b5a0`
- `0x18000bdf0`
- `0x18000cea0`
- `0x18000e420`

## callees

- `0x180007998`
- `0x180007e0c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800079b9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180007a23`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800079b9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180007a23`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x1800079ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x1800079ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800079e4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800079fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180007a49`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800079e4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800079fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180007a49`

## pseudocode

```c
void __fastcall EndDlgPage(HWND hWnd, int a2)
{
  HWND Parent; // rax
  HWND v5; // rax

  if ( (*((_BYTE *)gpStateInfo + 96) & 0x40) != 0 )
  {
    SetWindowLongPtrW(hWnd, 0, 0);
  }
  else
  {
    Parent = GetParent(hWnd);
    v5 = (HWND)SendMessageW(Parent, 0x474u, 0, 0);
    gnCurrentPage = SendMessageW(v5, 0x130Bu, 0, 0);
    *((_DWORD *)gpStateInfo + 24) |= 0x40u;
    SetWindowLongPtrW(hWnd, 0, 0);
    if ( a2 )
      SaveConsoleSettingsIfNeeded(hWnd);
    SendMessageW(hWnd, 0x46Du, 0, 0);
  }
}

```

## disassembly

```asm
0x180007998  mov     [rsp+arg_0], rbx
0x18000799d  push    rdi
0x18000799e  sub     rsp, 20h
0x1800079a2  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800079a9  mov     edi, edx
0x1800079ab  mov     rbx, rcx
0x1800079ae  test    byte ptr [rax+60h], 40h
0x1800079b2  jz      short loc_1800079CA
0x1800079b4  xor     r8d, r8d; dwNewLong
0x1800079b7  xor     edx, edx; nIndex
0x1800079b9  call    cs:__imp_SetWindowLongPtrW
0x1800079c0  nop     dword ptr [rax+rax+00h]
0x1800079c5  jmp     loc_180007A55
0x1800079ca  call    cs:__imp_GetParent
0x1800079d1  nop     dword ptr [rax+rax+00h]
0x1800079d6  xor     r9d, r9d; lParam
0x1800079d9  xor     r8d, r8d; wParam
0x1800079dc  mov     rcx, rax; hWnd
0x1800079df  mov     edx, 474h; Msg
0x1800079e4  call    cs:__imp_SendMessageW
0x1800079eb  nop     dword ptr [rax+rax+00h]
0x1800079f0  xor     r9d, r9d; lParam
0x1800079f3  xor     r8d, r8d; wParam
0x1800079f6  mov     rcx, rax; hWnd
0x1800079f9  mov     edx, 130Bh; Msg
0x1800079fe  call    cs:__imp_SendMessageW
0x180007a05  nop     dword ptr [rax+rax+00h]
0x180007a0a  mov     cs:?gnCurrentPage@@3IA, eax; uint gnCurrentPage
0x180007a10  xor     r8d, r8d; dwNewLong
0x180007a13  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007a1a  xor     edx, edx; nIndex
0x180007a1c  mov     rcx, rbx; hWnd
0x180007a1f  or      dword ptr [rax+60h], 40h
0x180007a23  call    cs:__imp_SetWindowLongPtrW
0x180007a2a  nop     dword ptr [rax+rax+00h]
0x180007a2f  test    edi, edi
0x180007a31  jz      short loc_180007A3B
0x180007a33  mov     rcx, rbx; hWnd
0x180007a36  call    ?SaveConsoleSettingsIfNeeded@@YAXQEAUHWND__@@@Z; SaveConsoleSettingsIfNeeded(HWND__ * const)
0x180007a3b  xor     r9d, r9d; lParam
0x180007a3e  xor     r8d, r8d; wParam
0x180007a41  mov     edx, 46Dh; Msg
0x180007a46  mov     rcx, rbx; hWnd
0x180007a49  call    cs:__imp_SendMessageW
0x180007a50  nop     dword ptr [rax+rax+00h]
0x180007a55  mov     rbx, [rsp+28h+arg_0]
0x180007a5a  add     rsp, 20h
0x180007a5e  pop     rdi
0x180007a5f  retn
```
