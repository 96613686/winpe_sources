# GetActiveThreadInfo(ulong *,HWND__ * *,ulong *)

- ea: `0x1800438e0`
- end: `0x180043a17`
- name: `?GetActiveThreadInfo@@YAXPEAKPEAPEAUHWND__@@0@Z`
- size: `311`
- prototype: `void(unsigned int *, HWND *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c300`
- `0x1800415f0`
- `0x180043858`

## callees

- `0x1800438e0`
- `0x18009c868`
- `0x18009eaea`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800439e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800439e6`
- `USER32!GetWindowThreadProcessId` at `0x1800439a4`
- `USER32!GetWindowThreadProcessId` at `0x180043a07`
- `USER32!GetWindowThreadProcessId` at `0x1800439a4`
- `USER32!GetWindowThreadProcessId` at `0x180043a07`
- `USER32!RealGetWindowClassW` at `0x180043989`
- `USER32!RealGetWindowClassW` at `0x180043989`
- `USER32!GetGUIThreadInfo` at `0x180043929`
- `USER32!GetGUIThreadInfo` at `0x180043929`
- `IMM32!ImmGetDefaultIMEWnd` at `0x1800439f6`
- `IMM32!ImmGetDefaultIMEWnd` at `0x1800439f6`

## pseudocode

```c
void __fastcall GetActiveThreadInfo(unsigned int *a1, HWND *a2, unsigned int *a3)
{
  HWND hwndFocus; // rbp
  UINT WindowClassW; // eax
  HWND DefaultIMEWnd; // rax
  struct tagGUITHREADINFO pgui; // [rsp+30h] [rbp-B8h] BYREF
  WCHAR ptszClassName[32]; // [rsp+80h] [rbp-68h] BYREF

  memset_0(&pgui, 0, sizeof(pgui));
  pgui.cbSize = 72;
  GetGUIThreadInfo(0, &pgui);
  hwndFocus = pgui.hwndFocus;
  *a2 = pgui.hwndFocus;
  *a1 = 0;
  if ( hwndFocus )
  {
    memset_0(ptszClassName, 0, sizeof(ptszClassName));
    WindowClassW = RealGetWindowClassW(hwndFocus, ptszClassName, 0x1Fu);
    if ( WindowClassW - 1 <= 0x1E )
    {
      if ( 2 * (unsigned __int64)WindowClassW >= 0x40 )
        _report_rangecheckfailure();
      ptszClassName[WindowClassW] = 0;
      if ( CompareStringW(0x7Fu, 0, ptszClassName, -1, L"ConsoleWindowClass", -1) == 2 )
      {
        DefaultIMEWnd = ImmGetDefaultIMEWnd(pgui.hwndFocus);
        if ( DefaultIMEWnd )
          LODWORD(DefaultIMEWnd) = GetWindowThreadProcessId(DefaultIMEWnd, a3);
        *a1 = (unsigned int)DefaultIMEWnd;
      }
    }
    if ( !*a1 )
      *a1 = GetWindowThreadProcessId(pgui.hwndFocus, a3);
  }
}

```

## disassembly

```asm
0x1800438e0  mov     [rsp+arg_18], rbx
0x1800438e5  push    rbp
0x1800438e6  push    rsi
0x1800438e7  push    rdi
0x1800438e8  sub     rsp, 0D0h
0x1800438ef  mov     rax, cs:__security_cookie
0x1800438f6  xor     rax, rsp
0x1800438f9  mov     [rsp+0E8h+var_28], rax
0x180043901  mov     rsi, r8
0x180043904  mov     rbx, rdx
0x180043907  mov     rdi, rcx
0x18004390a  mov     ebp, 48h ; 'H'
0x18004390f  mov     r8d, ebp; Size
0x180043912  lea     rcx, [rsp+0E8h+pgui]; void *
0x180043917  xor     edx, edx; Val
0x180043919  call    memset_0
0x18004391e  lea     rdx, [rsp+0E8h+pgui]; pgui
0x180043923  mov     [rsp+0E8h+pgui.cbSize], ebp
0x180043927  xor     ecx, ecx; idThread
0x180043929  call    cs:__imp_GetGUIThreadInfo
0x18004392f  mov     rbp, [rsp+0E8h+pgui.hwndFocus]
0x180043934  mov     [rbx], rbp
0x180043937  mov     dword ptr [rdi], 0
0x18004393d  test    rbp, rbp
0x180043940  jnz     short loc_180043965
0x180043942  mov     rcx, [rsp+0E8h+var_28]
0x18004394a  xor     rcx, rsp; StackCookie
0x18004394d  call    __security_check_cookie
0x180043952  mov     rbx, [rsp+0E8h+arg_18]
0x18004395a  add     rsp, 0D0h
0x180043961  pop     rdi
0x180043962  pop     rsi
0x180043963  pop     rbp
0x180043964  retn
0x180043965  xor     edx, edx; Val
0x180043967  lea     rcx, [rsp+0E8h+ptszClassName]; void *
0x18004396f  lea     r8d, [rdx+40h]; Size
0x180043973  call    memset_0
0x180043978  mov     r8d, 1Fh; cchClassNameMax
0x18004397e  lea     rdx, [rsp+0E8h+ptszClassName]; ptszClassName
0x180043986  mov     rcx, rbp; hwnd
0x180043989  call    cs:__imp_RealGetWindowClassW
0x18004398f  lea     ecx, [rax-1]
0x180043992  cmp     ecx, 1Eh
0x180043995  jbe     short loc_1800439AE
0x180043997  cmp     dword ptr [rdi], 0
0x18004399a  jnz     short loc_180043942
0x18004399c  mov     rcx, [rsp+0E8h+pgui.hwndFocus]; hWnd
0x1800439a1  mov     rdx, rsi; lpdwProcessId
0x1800439a4  call    cs:__imp_GetWindowThreadProcessId
0x1800439aa  mov     [rdi], eax
0x1800439ac  jmp     short loc_180043942
0x1800439ae  mov     eax, eax
0x1800439b0  lea     rcx, [rax+rax]
0x1800439b4  cmp     rcx, 40h ; '@'
0x1800439b8  jnb     short loc_180043A11
0x1800439ba  xor     eax, eax
0x1800439bc  lea     r8, [rsp+0E8h+ptszClassName]; lpString1
0x1800439c4  mov     [rsp+rcx+0E8h+ptszClassName], ax
0x1800439cc  xor     edx, edx; dwCmpFlags
0x1800439ce  or      r9d, 0FFFFFFFFh; cchCount1
0x1800439d2  lea     rax, aConsolewindowc; "ConsoleWindowClass"
0x1800439d9  mov     [rsp+0E8h+cchCount2], r9d; cchCount2
0x1800439de  mov     [rsp+0E8h+lpString2], rax; lpString2
0x1800439e3  lea     ecx, [rdx+7Fh]; Locale
0x1800439e6  call    cs:__imp_CompareStringW
0x1800439ec  cmp     eax, 2
0x1800439ef  jnz     short loc_180043997
0x1800439f1  mov     rcx, [rsp+0E8h+pgui.hwndFocus]; HWND
0x1800439f6  call    cs:__imp_ImmGetDefaultIMEWnd
0x1800439fc  test    rax, rax
0x1800439ff  jz      short loc_180043A0D
0x180043a01  mov     rdx, rsi; lpdwProcessId
0x180043a04  mov     rcx, rax; hWnd
0x180043a07  call    cs:__imp_GetWindowThreadProcessId
0x180043a0d  mov     [rdi], eax
0x180043a0f  jmp     short loc_180043997
0x180043a11  call    __report_rangecheckfailure
```
