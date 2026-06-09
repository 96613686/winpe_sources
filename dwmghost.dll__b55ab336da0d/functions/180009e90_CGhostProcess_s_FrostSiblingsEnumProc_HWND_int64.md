# CGhostProcess::s_FrostSiblingsEnumProc(HWND__ *,__int64)

- ea: `0x180009e90`
- end: `0x180009f29`
- name: `?s_FrostSiblingsEnumProc@CGhostProcess@@CAHPEAUHWND__@@_J@Z`
- size: `153`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180008eec`
- `0x180009e90`

## import_xrefs

- `USER32!GetWindowLongW` at `0x180009eff`
- `USER32!GetWindowLongW` at `0x180009eff`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180009eef`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180009eef`
- `ext-ms-win-ntuser-window-l1-1-4!GhostWindowFromHungWindow` at `0x180009ed6`
- `ext-ms-win-ntuser-window-l1-1-4!GhostWindowFromHungWindow` at `0x180009ed6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180009ec0`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180009ec0`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x180009eae`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x180009eae`

## pseudocode

```c
__int64 __fastcall CGhostProcess::s_FrostSiblingsEnumProc(HWND a1, CGhostProcess *a2)
{
  bool v2; // zf
  HWND v5; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  v2 = *((_DWORD *)a2 + 17) == 0;
  dwProcessId = 0;
  if ( !v2 && IsWindowVisible(a1) && GetWindowThreadProcessId(a1, &dwProcessId) && dwProcessId == *((_DWORD *)a2 + 14) )
  {
    v5 = (HWND)GhostWindowFromHungWindow(a1);
    if ( v5 )
    {
      PostMessageW(v5, 0x400u, 0, 0);
    }
    else if ( (GetWindowLongW(a1, -16) & 0xC00000) == 0xC00000 )
    {
      CGhostProcess::CreateSiblingFrostWindow(a2, a1);
    }
  }
  return *((unsigned int *)a2 + 17);
}

```

## disassembly

```asm
0x180009e90  mov     [rsp+arg_0], rbx
0x180009e95  push    rdi
0x180009e96  sub     rsp, 20h
0x180009e9a  cmp     dword ptr [rdx+44h], 0
0x180009e9e  mov     rbx, rdx
0x180009ea1  mov     rdi, rcx
0x180009ea4  mov     [rsp+28h+dwProcessId], 0
0x180009eac  jz      short loc_180009F1B
0x180009eae  call    cs:__imp_IsWindowVisible
0x180009eb4  test    eax, eax
0x180009eb6  jz      short loc_180009F1B
0x180009eb8  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180009ebd  mov     rcx, rdi; hWnd
0x180009ec0  call    cs:__imp_GetWindowThreadProcessId
0x180009ec6  test    eax, eax
0x180009ec8  jz      short loc_180009F1B
0x180009eca  mov     eax, [rbx+38h]
0x180009ecd  cmp     [rsp+28h+dwProcessId], eax
0x180009ed1  jnz     short loc_180009F1B
0x180009ed3  mov     rcx, rdi
0x180009ed6  call    cs:__imp_GhostWindowFromHungWindow
0x180009edc  test    rax, rax
0x180009edf  jz      short loc_180009EF7
0x180009ee1  xor     r9d, r9d; lParam
0x180009ee4  xor     r8d, r8d; wParam
0x180009ee7  mov     edx, 400h; Msg
0x180009eec  mov     rcx, rax; hWnd
0x180009eef  call    cs:__imp_PostMessageW
0x180009ef5  jmp     short loc_180009F1B
0x180009ef7  mov     edx, 0FFFFFFF0h; nIndex
0x180009efc  mov     rcx, rdi; hWnd
0x180009eff  call    cs:__imp_GetWindowLongW
0x180009f05  mov     ecx, 0C00000h
0x180009f0a  and     eax, ecx
0x180009f0c  cmp     eax, ecx
0x180009f0e  jnz     short loc_180009F1B
0x180009f10  mov     rdx, rdi; HWND
0x180009f13  mov     rcx, rbx; this
0x180009f16  call    ?CreateSiblingFrostWindow@CGhostProcess@@AEAAHPEAUHWND__@@@Z; CGhostProcess::CreateSiblingFrostWindow(HWND__ *)
0x180009f1b  mov     eax, [rbx+44h]
0x180009f1e  mov     rbx, [rsp+28h+arg_0]
0x180009f23  add     rsp, 20h
0x180009f27  pop     rdi
0x180009f28  retn
```
