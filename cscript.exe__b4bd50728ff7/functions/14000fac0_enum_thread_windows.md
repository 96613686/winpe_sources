# enum_thread_windows

- ea: `0x14000fac0`
- end: `0x14000fb20`
- name: `enum_thread_windows`
- size: `96`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000fac0`
- `0x14000fb28`

## import_xrefs

- `USER32!PostMessageA` at `0x14000faf3`
- `USER32!PostMessageA` at `0x14000fb08`
- `USER32!PostMessageA` at `0x14000faf3`
- `USER32!PostMessageA` at `0x14000fb08`
- `USER32!IsWindowVisible` at `0x14000fad0`
- `USER32!IsWindowVisible` at `0x14000fad0`

## pseudocode

```c
__int64 __fastcall enum_thread_windows(HWND a1, _DWORD *a2)
{
  if ( IsWindowVisible(a1) && !(unsigned __int8)isIMEwindow(a1) )
  {
    PostMessageA(a1, 0x10u, 0, 0);
    PostMessageA(a1, 0x100u, 0xDu, 0);
    ++*a2;
  }
  return 1;
}

```

## disassembly

```asm
0x14000fac0  mov     [rsp+arg_0], rbx
0x14000fac5  push    rdi
0x14000fac6  sub     rsp, 20h
0x14000faca  mov     rdi, rdx
0x14000facd  mov     rbx, rcx
0x14000fad0  call    cs:__imp_IsWindowVisible
0x14000fad6  test    eax, eax
0x14000fad8  jz      short loc_14000FB10
0x14000fada  mov     rcx, rbx; hWnd
0x14000fadd  call    isIMEwindow
0x14000fae2  test    al, al
0x14000fae4  jnz     short loc_14000FB10
0x14000fae6  xor     r9d, r9d; lParam
0x14000fae9  xor     r8d, r8d; wParam
0x14000faec  mov     rcx, rbx; hWnd
0x14000faef  lea     edx, [r9+10h]; Msg
0x14000faf3  call    cs:__imp_PostMessageA
0x14000faf9  xor     r9d, r9d; lParam
0x14000fafc  mov     edx, 100h; Msg
0x14000fb01  mov     rcx, rbx; hWnd
0x14000fb04  lea     r8d, [r9+0Dh]; wParam
0x14000fb08  call    cs:__imp_PostMessageA
0x14000fb0e  inc     dword ptr [rdi]
0x14000fb10  mov     rbx, [rsp+28h+arg_0]
0x14000fb15  mov     eax, 1
0x14000fb1a  add     rsp, 20h
0x14000fb1e  pop     rdi
0x14000fb1f  retn
```
