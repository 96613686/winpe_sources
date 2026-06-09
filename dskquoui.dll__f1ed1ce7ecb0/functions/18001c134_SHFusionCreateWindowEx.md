# SHFusionCreateWindowEx

- ea: `0x18001c134`
- end: `0x18001c207`
- name: `SHFusionCreateWindowEx`
- size: `211`
- prototype: `__int64 __fastcall(DWORD dwExStyle, LPCWSTR lpClassName, LPCWSTR lpWindowName, DWORD dwStyle, int, int, int, int, HWND, HMENU, HINSTANCE, LPVOID)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000946c`
- `0x1800098ac`
- `0x180009b34`

## callees

- `0x18001c0c4`
- `0x18001c134`
- `0x18001c888`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001c1f5`
- `KERNEL32!DeactivateActCtx` at `0x18001c1f5`
- `USER32!CreateWindowExW` at `0x18001c1e0`
- `USER32!CreateWindowExW` at `0x18001c1e0`

## pseudocode

```c
HWND __fastcall SHFusionCreateWindowEx(
        DWORD dwExStyle,
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        HMENU hMenu,
        HINSTANCE hInstance,
        LPVOID lpParam)
{
  HWND Window; // rbx
  ULONG_PTR ulCookie[7]; // [rsp+60h] [rbp-38h] BYREF

  ulCookie[0] = 0;
  if ( !(unsigned int)SHActivateContext(ulCookie) )
    return 0;
  if ( g_hActCtx != (HANDLE)-3LL )
    DelayLoadCC();
  Window = CreateWindowExW(
             dwExStyle,
             lpClassName,
             lpWindowName,
             dwStyle,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             hMenu,
             hInstance,
             lpParam);
  if ( ulCookie[0] )
    DeactivateActCtx(0, ulCookie[0]);
  return Window;
}

```

## disassembly

```asm
0x18001c134  push    rbx
0x18001c136  push    rbp
0x18001c137  push    rsi
0x18001c138  push    rdi
0x18001c139  sub     rsp, 78h
0x18001c13d  mov     ebp, ecx
0x18001c13f  mov     [rsp+98h+ulCookie], 0
0x18001c148  lea     rcx, [rsp+98h+ulCookie]
0x18001c14d  mov     ebx, r9d
0x18001c150  mov     rdi, r8
0x18001c153  mov     rsi, rdx
0x18001c156  call    SHActivateContext
0x18001c15b  test    eax, eax
0x18001c15d  jnz     short loc_18001C166
0x18001c15f  xor     eax, eax
0x18001c161  jmp     loc_18001C1FE
0x18001c166  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18001c16e  jz      short loc_18001C175
0x18001c170  call    DelayLoadCC
0x18001c175  mov     rax, [rsp+98h+arg_58]
0x18001c17d  mov     r9d, ebx; dwStyle
0x18001c180  mov     [rsp+98h+lpParam], rax; lpParam
0x18001c185  mov     r8, rdi; lpWindowName
0x18001c188  mov     rax, [rsp+98h+arg_50]
0x18001c190  mov     rdx, rsi; lpClassName
0x18001c193  mov     [rsp+98h+hInstance], rax; hInstance
0x18001c198  mov     ecx, ebp; dwExStyle
0x18001c19a  mov     rax, [rsp+98h+arg_48]
0x18001c1a2  mov     [rsp+98h+hMenu], rax; hMenu
0x18001c1a7  mov     rax, [rsp+98h+arg_40]
0x18001c1af  mov     [rsp+98h+hWndParent], rax; hWndParent
0x18001c1b4  mov     eax, [rsp+98h+arg_38]
0x18001c1bb  mov     [rsp+98h+nHeight], eax; nHeight
0x18001c1bf  mov     eax, [rsp+98h+arg_30]
0x18001c1c6  mov     [rsp+98h+nWidth], eax; nWidth
0x18001c1ca  mov     eax, [rsp+98h+arg_28]
0x18001c1d1  mov     [rsp+98h+Y], eax; Y
0x18001c1d5  mov     eax, [rsp+98h+arg_20]
0x18001c1dc  mov     [rsp+98h+X], eax; X
0x18001c1e0  call    cs:__imp_CreateWindowExW
0x18001c1e6  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x18001c1eb  mov     rbx, rax
0x18001c1ee  test    rdx, rdx
0x18001c1f1  jz      short loc_18001C1FB
0x18001c1f3  xor     ecx, ecx; dwFlags
0x18001c1f5  call    cs:__imp_DeactivateActCtx
0x18001c1fb  mov     rax, rbx
0x18001c1fe  add     rsp, 78h
0x18001c202  pop     rdi
0x18001c203  pop     rsi
0x18001c204  pop     rbp
0x18001c205  pop     rbx
0x18001c206  retn
```
