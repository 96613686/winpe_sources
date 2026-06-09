# GetCurrentThreadLastPopup

- ea: `0x180029f08`
- end: `0x180029fe8`
- name: `GetCurrentThreadLastPopup`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029ff0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180029f08`

## import_xrefs

- `USER32!GetLastActivePopup` at `0x180029fb8`
- `USER32!GetLastActivePopup` at `0x180029fb8`
- `USER32!GetWindow` at `0x180029fa2`
- `USER32!GetWindow` at `0x180029fa2`
- `USER32!GetParent` at `0x180029f91`
- `USER32!GetParent` at `0x180029f91`
- `USER32!GetGUIThreadInfo` at `0x180029f72`
- `USER32!GetGUIThreadInfo` at `0x180029f72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029f58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029f58`

## pseudocode

```c
__int64 __fastcall GetCurrentThreadLastPopup(HWND *a1)
{
  unsigned int v2; // edi
  HWND hwndActive; // rcx
  HWND Parent; // rax
  HWND Window; // rax
  HWND LastActivePopup; // rax
  tagGUITHREADINFO pgui; // [rsp+20h] [rbp-68h] BYREF

  v2 = -2147024809;
  memset_0(&pgui, 0, sizeof(pgui));
  if ( a1 )
  {
    *a1 = 0;
    v2 = -2147467259;
    if ( !GetModuleHandleW(L"splwow64.exe") )
    {
      pgui.cbSize = 72;
      if ( GetGUIThreadInfo(0, &pgui) )
      {
        hwndActive = pgui.hwndActive;
        if ( pgui.hwndActive )
        {
          *a1 = pgui.hwndActive;
          while ( 1 )
          {
            Parent = GetParent(hwndActive);
            if ( !Parent )
              break;
            *a1 = Parent;
            hwndActive = Parent;
          }
          Window = GetWindow(*a1, 4u);
          if ( Window )
            *a1 = Window;
          if ( *a1 )
          {
            LastActivePopup = GetLastActivePopup(*a1);
            *a1 = LastActivePopup;
            if ( LastActivePopup )
              return 0;
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180029f08  mov     [rsp+arg_8], rbx
0x180029f0d  push    rdi
0x180029f0e  sub     rsp, 80h
0x180029f15  mov     rax, cs:__security_cookie
0x180029f1c  xor     rax, rsp
0x180029f1f  mov     [rsp+88h+var_18], rax
0x180029f24  xor     edx, edx; Val
0x180029f26  mov     rbx, rcx
0x180029f29  lea     rcx, [rsp+88h+pgui]; void *
0x180029f2e  mov     edi, 80070057h
0x180029f33  lea     r8d, [rdx+48h]; Size
0x180029f37  call    memset_0
0x180029f3c  test    rbx, rbx
0x180029f3f  jz      loc_180029FC8
0x180029f45  lea     rcx, aSplwow64Exe; "splwow64.exe"
0x180029f4c  mov     qword ptr [rbx], 0
0x180029f53  mov     edi, 80004005h
0x180029f58  call    cs:__imp_GetModuleHandleW
0x180029f5e  test    rax, rax
0x180029f61  jnz     short loc_180029FC8
0x180029f63  lea     rdx, [rsp+88h+pgui]; pgui
0x180029f68  mov     [rsp+88h+pgui.cbSize], 48h ; 'H'
0x180029f70  xor     ecx, ecx; idThread
0x180029f72  call    cs:__imp_GetGUIThreadInfo
0x180029f78  test    eax, eax
0x180029f7a  jz      short loc_180029FC8
0x180029f7c  mov     rcx, [rsp+88h+pgui.hwndActive]
0x180029f81  test    rcx, rcx
0x180029f84  jz      short loc_180029FC8
0x180029f86  mov     [rbx], rcx
0x180029f89  jmp     short loc_180029F91
0x180029f8b  mov     [rbx], rax
0x180029f8e  mov     rcx, rax; hWnd
0x180029f91  call    cs:__imp_GetParent
0x180029f97  test    rax, rax
0x180029f9a  jnz     short loc_180029F8B
0x180029f9c  mov     rcx, [rbx]; hWnd
0x180029f9f  lea     edx, [rax+4]; uCmd
0x180029fa2  call    cs:__imp_GetWindow
0x180029fa8  test    rax, rax
0x180029fab  jz      short loc_180029FB0
0x180029fad  mov     [rbx], rax
0x180029fb0  mov     rcx, [rbx]; hWnd
0x180029fb3  test    rcx, rcx
0x180029fb6  jz      short loc_180029FC8
0x180029fb8  call    cs:__imp_GetLastActivePopup
0x180029fbe  mov     [rbx], rax
0x180029fc1  test    rax, rax
0x180029fc4  jz      short loc_180029FC8
0x180029fc6  xor     edi, edi
0x180029fc8  mov     eax, edi
0x180029fca  mov     rcx, [rsp+88h+var_18]
0x180029fcf  xor     rcx, rsp; StackCookie
0x180029fd2  call    __security_check_cookie
0x180029fd7  mov     rbx, [rsp+88h+arg_8]
0x180029fdf  add     rsp, 80h
0x180029fe6  pop     rdi
0x180029fe7  retn
```
