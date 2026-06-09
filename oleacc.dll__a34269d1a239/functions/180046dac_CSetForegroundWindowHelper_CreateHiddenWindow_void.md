# CSetForegroundWindowHelper::CreateHiddenWindow(void)

- ea: `0x180046dac`
- end: `0x180046e6f`
- name: `?CreateHiddenWindow@CSetForegroundWindowHelper@@AEAAHXZ`
- size: `195`
- prototype: `__int64 __fastcall(CSetForegroundWindowHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800476bc`

## callees

- `0x18001efc4`
- `0x180046dac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046dfa`
- `USER32!RegisterClassExW` at `0x180046ded`
- `USER32!RegisterClassExW` at `0x180046ded`
- `USER32!CreateWindowExW` at `0x180046e4f`
- `USER32!CreateWindowExW` at `0x180046e4f`

## pseudocode

```c
_BOOL8 __fastcall CSetForegroundWindowHelper::CreateHiddenWindow(CSetForegroundWindowHelper *this)
{
  WNDCLASSEXW v2; // [rsp+60h] [rbp-58h] BYREF

  memset_0(&v2, 0, sizeof(v2));
  v2.cbSize = 80;
  v2.lpfnWndProc = (WNDPROC)MessageWindowProc;
  v2.lpszClassName = L"MSAAMessageWindow";
  if ( !RegisterClassExW(&v2) && GetLastError() != 1410 )
    return 0;
  g_GetFocus = CreateWindowExW(
                 0,
                 L"MSAAMessageWindow",
                 L"MSAAMessageWindow",
                 0,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 HWND_MESSAGE,
                 0,
                 0,
                 0);
  return g_GetFocus != 0;
}

```

## disassembly

```asm
0x180046dac  push    rdi
0x180046dae  sub     rsp, 0B0h
0x180046db5  xor     edx, edx; Val
0x180046db7  lea     rcx, [rsp+0B8h+var_58]; void *
0x180046dbc  lea     r8d, [rdx+50h]; Size
0x180046dc0  call    memset_0
0x180046dc5  lea     rax, ?MessageWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; MessageWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180046dcc  mov     [rsp+0B8h+var_58.cbSize], 50h ; 'P'
0x180046dd4  lea     rdi, WindowName; "MSAAMessageWindow"
0x180046ddb  mov     [rsp+0B8h+var_58.lpfnWndProc], rax
0x180046de0  lea     rcx, [rsp+0B8h+var_58]; WNDCLASSEXW *
0x180046de5  mov     [rsp+0B8h+var_58.lpszClassName], rdi
0x180046ded  call    cs:__imp_RegisterClassExW
0x180046df3  xor     ecx, ecx
0x180046df5  cmp     cx, ax
0x180046df8  jnz     short loc_180046E0B
0x180046dfa  call    cs:__imp_GetLastError
0x180046e00  cmp     eax, 582h
0x180046e05  jz      short loc_180046E0B
0x180046e07  xor     eax, eax
0x180046e09  jmp     short loc_180046E66
0x180046e0b  mov     [rsp+0B8h+lpParam], 0; lpParam
0x180046e14  mov     eax, 80000000h
0x180046e19  mov     [rsp+0B8h+hInstance], 0; hInstance
0x180046e22  xor     r9d, r9d; dwStyle
0x180046e25  mov     [rsp+0B8h+hMenu], 0; hMenu
0x180046e2e  mov     r8, rdi; lpWindowName
0x180046e31  mov     [rsp+0B8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180046e3a  mov     rdx, rdi; lpClassName
0x180046e3d  mov     [rsp+0B8h+nHeight], eax; nHeight
0x180046e41  xor     ecx, ecx; dwExStyle
0x180046e43  mov     [rsp+0B8h+nWidth], eax; nWidth
0x180046e47  mov     [rsp+0B8h+Y], eax; Y
0x180046e4b  mov     [rsp+0B8h+X], eax; X
0x180046e4f  call    cs:__imp_CreateWindowExW
0x180046e55  xor     ecx, ecx
0x180046e57  mov     cs:?g_GetFocus@@3VCSetForegroundWindowHelper@@A, rax; CSetForegroundWindowHelper g_GetFocus
0x180046e5e  test    rax, rax
0x180046e61  setnz   cl
0x180046e64  mov     eax, ecx
0x180046e66  add     rsp, 0B0h
0x180046e6d  pop     rdi
0x180046e6e  retn
```
