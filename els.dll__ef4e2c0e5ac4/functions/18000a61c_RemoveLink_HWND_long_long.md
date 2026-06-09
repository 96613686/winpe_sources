# RemoveLink(HWND__ *,long,long)

- ea: `0x18000a61c`
- end: `0x18000a6a8`
- name: `?RemoveLink@@YAXPEAUHWND__@@JJ@Z`
- size: `140`
- prototype: `void __fastcall(HWND hWnd, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb38`

## callees

- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000a650`
- `USER32!SendMessageW` at `0x18000a689`
- `USER32!SendMessageW` at `0x18000a650`
- `USER32!SendMessageW` at `0x18000a689`

## pseudocode

```c
void __fastcall RemoveLink(HWND hWnd, int a2, int a3)
{
  _DWORD lParam[4]; // [rsp+20h] [rbp-A8h] BYREF
  LPARAM v5; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v6[120]; // [rsp+38h] [rbp-90h] BYREF

  lParam[0] = a2;
  lParam[1] = a3;
  SendMessageW(hWnd, 0x437u, 0, (LPARAM)lParam);
  memset_0(v6, 0, 0x6Cu);
  v5 = 0x2000000074LL;
  SendMessageW(hWnd, 0x444u, 1u, (LPARAM)&v5);
}

```

## disassembly

```asm
0x18000a61c  push    rbx
0x18000a61e  sub     rsp, 0C0h
0x18000a625  mov     rax, cs:__security_cookie
0x18000a62c  xor     rax, rsp
0x18000a62f  mov     [rsp+0C8h+var_18], rax
0x18000a637  mov     [rsp+0C8h+lParam], edx
0x18000a63b  lea     r9, [rsp+0C8h+lParam]; lParam
0x18000a640  mov     [rsp+0C8h+lParam+4], r8d
0x18000a645  mov     edx, 437h; Msg
0x18000a64a  xor     r8d, r8d; wParam
0x18000a64d  mov     rbx, rcx
0x18000a650  call    cs:__imp_SendMessageW
0x18000a656  xor     edx, edx; Val
0x18000a658  lea     rcx, [rsp+0C8h+var_90]; void *
0x18000a65d  lea     r8d, [rdx+6Ch]; Size
0x18000a661  call    memset_0
0x18000a666  lea     r9, [rsp+0C8h+var_98]; lParam
0x18000a66b  mov     dword ptr [rsp+0C8h+var_98], 74h ; 't'
0x18000a673  mov     edx, 444h; Msg
0x18000a678  mov     dword ptr [rsp+0C8h+var_98+4], 20h ; ' '
0x18000a680  mov     r8d, 1; wParam
0x18000a686  mov     rcx, rbx; hWnd
0x18000a689  call    cs:__imp_SendMessageW
0x18000a68f  mov     rcx, [rsp+0C8h+var_18]
0x18000a697  xor     rcx, rsp; StackCookie
0x18000a69a  call    __security_check_cookie
0x18000a69f  add     rsp, 0C0h
0x18000a6a6  pop     rbx
0x18000a6a7  retn
```
