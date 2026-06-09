# InTheShell(HWND__ *,int)

- ea: `0x18000619c`
- end: `0x18000627f`
- name: `?InTheShell@@YAHPEAUHWND__@@H@Z`
- size: `227`
- prototype: `__int64 __fastcall(HWND hWnd, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180004de4`
- `0x180005910`
- `0x180016338`
- `0x18003abd0`
- `0x180041d58`
- `0x1800425b0`
- `0x180042690`

## callees

- `0x18000619c`
- `0x1800151d4`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180006201`
- `USER32!GetWindowThreadProcessId` at `0x18000620f`
- `USER32!GetWindowThreadProcessId` at `0x180006201`
- `USER32!GetWindowThreadProcessId` at `0x18000620f`
- `USER32!FindWindowExW` at `0x180006251`
- `USER32!FindWindowExW` at `0x180006251`
- `USER32!GetShellWindow` at `0x1800061bf`
- `USER32!GetShellWindow` at `0x1800061bf`

## pseudocode

```c
__int64 __fastcall InTheShell(HWND hWnd, int a2)
{
  HWND ShellWindow; // rax
  HWND v5; // rdi
  int v6; // ebx
  int v7; // ebx
  HWND Ancestor; // rax
  unsigned int v10; // ecx
  bool v11; // zf
  HWND Window; // rbx
  HWND v13; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF
  DWORD v15; // [rsp+40h] [rbp+18h] BYREF

  dwProcessId = 0;
  v15 = 0;
  ShellWindow = GetShellWindow();
  v5 = ShellWindow;
  v6 = a2 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        dwProcessId = 0;
        v15 = 0;
        GetWindowThreadProcessId(hWnd, &dwProcessId);
        GetWindowThreadProcessId(v5, &v15);
        if ( dwProcessId )
        {
          if ( dwProcessId == v15 )
            return 1;
        }
      }
      return 0;
    }
    if ( !ShellWindow )
      return 0;
    Ancestor = MyGetAncestor(hWnd, 2u);
    v10 = 0;
    v11 = Ancestor == v5;
  }
  else
  {
    Window = FindWindowExW(0, 0, aShellTraywnd, 0);
    if ( !Window )
      return 0;
    v13 = MyGetAncestor(hWnd, 3u);
    v10 = 0;
    v11 = v13 == Window;
  }
  LOBYTE(v10) = v11;
  return v10;
}

```

## disassembly

```asm
0x18000619c  mov     rax, rsp
0x18000619f  mov     [rax+8], rbx
0x1800061a3  mov     [rax+20h], rsi
0x1800061a7  push    rdi
0x1800061a8  sub     rsp, 20h
0x1800061ac  mov     ebx, edx
0x1800061ae  mov     dword ptr [rax+10h], 0
0x1800061b5  mov     rsi, rcx
0x1800061b8  mov     dword ptr [rax+18h], 0
0x1800061bf  call    cs:__imp_GetShellWindow
0x1800061c5  mov     rdi, rax
0x1800061c8  sub     ebx, 1
0x1800061cb  jz      short loc_180006243
0x1800061cd  sub     ebx, 1
0x1800061d0  jz      short loc_18000622A
0x1800061d2  cmp     ebx, 1
0x1800061d5  jz      short loc_1800061E9
0x1800061d7  xor     eax, eax
0x1800061d9  mov     rbx, [rsp+28h+arg_0]
0x1800061de  mov     rsi, [rsp+28h+arg_18]
0x1800061e3  add     rsp, 20h
0x1800061e7  pop     rdi
0x1800061e8  retn
0x1800061e9  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x1800061ee  mov     [rsp+28h+dwProcessId], 0
0x1800061f6  mov     rcx, rsi; hWnd
0x1800061f9  mov     [rsp+28h+arg_10], 0
0x180006201  call    cs:__imp_GetWindowThreadProcessId
0x180006207  lea     rdx, [rsp+28h+arg_10]; lpdwProcessId
0x18000620c  mov     rcx, rdi; hWnd
0x18000620f  call    cs:__imp_GetWindowThreadProcessId
0x180006215  mov     eax, [rsp+28h+dwProcessId]
0x180006219  test    eax, eax
0x18000621b  jz      short loc_1800061D7
0x18000621d  cmp     eax, [rsp+28h+arg_10]
0x180006221  jnz     short loc_1800061D7
0x180006223  mov     eax, 1
0x180006228  jmp     short loc_1800061D9
0x18000622a  test    rdi, rdi
0x18000622d  jz      short loc_1800061D7
0x18000622f  mov     edx, 2; unsigned int
0x180006234  mov     rcx, rsi; hWnd
0x180006237  call    ?MyGetAncestor@@YAPEAUHWND__@@PEAU1@I@Z; MyGetAncestor(HWND__ *,uint)
0x18000623c  xor     ecx, ecx
0x18000623e  cmp     rax, rdi
0x180006241  jmp     short loc_180006271
0x180006243  xor     r9d, r9d; lpszWindow
0x180006246  lea     r8, aShellTraywnd; "Shell_TrayWnd"
0x18000624d  xor     edx, edx; hWndChildAfter
0x18000624f  xor     ecx, ecx; hWndParent
0x180006251  call    cs:__imp_FindWindowExW
0x180006257  mov     rbx, rax
0x18000625a  test    rax, rax
0x18000625d  jz      short loc_180006276
0x18000625f  mov     edx, 3; unsigned int
0x180006264  mov     rcx, rsi; hWnd
0x180006267  call    ?MyGetAncestor@@YAPEAUHWND__@@PEAU1@I@Z; MyGetAncestor(HWND__ *,uint)
0x18000626c  xor     ecx, ecx
0x18000626e  cmp     rax, rbx
0x180006271  setz    cl
0x180006274  jmp     short loc_180006278
0x180006276  xor     ecx, ecx
0x180006278  mov     eax, ecx
0x18000627a  jmp     loc_1800061D9
```
