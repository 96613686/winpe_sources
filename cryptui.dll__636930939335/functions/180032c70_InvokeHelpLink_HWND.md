# InvokeHelpLink(HWND__ *)

- ea: `0x180032c70`
- end: `0x180032d04`
- name: `?InvokeHelpLink@@YAXPEAUHWND__@@@Z`
- size: `148`
- prototype: `void __fastcall(HWND)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180006100`
- `0x180009000`
- `0x180009b10`
- `0x18000b220`
- `0x18000c7d0`
- `0x18000e040`
- `0x18000f2b0`
- `0x180010de0`
- `0x18001fda0`
- `0x180027a80`

## callees

- `0x1800323e0`
- `0x180032c70`
- `0x18003e582`
- `0x18003e5c0`
- `0x18003e680`

## import_xrefs

- `USER32!SendMessageA` at `0x180032cd0`
- `USER32!SendMessageA` at `0x180032cd0`

## pseudocode

```c
void __fastcall InvokeHelpLink(HWND a1)
{
  LPARAM lParam[2]; // [rsp+20h] [rbp-10D8h] BYREF
  _BYTE v3[96]; // [rsp+30h] [rbp-10C8h] BYREF
  WCHAR Parameters[2088]; // [rsp+90h] [rbp-1068h] BYREF

  if ( a1 )
  {
    memset_0(v3, 0, 0x10A8u);
    lParam[0] = 9;
    lParam[1] = 0;
    if ( SendMessageA(a1, 0x703u, 0, (LPARAM)lParam) )
      DisplayHtmlHelp(a1, Parameters);
  }
}

```

## disassembly

```asm
0x180032c70  test    rcx, rcx
0x180032c73  jz      locret_180032D03
0x180032c79  push    rbx
0x180032c7a  mov     eax, 10F0h
0x180032c7f  call    _alloca_probe
0x180032c84  sub     rsp, rax
0x180032c87  mov     rax, cs:__security_cookie
0x180032c8e  xor     rax, rsp
0x180032c91  mov     [rsp+10F8h+var_18], rax
0x180032c99  mov     rbx, rcx
0x180032c9c  xor     edx, edx; Val
0x180032c9e  lea     rcx, [rsp+10F8h+var_10C8]; void *
0x180032ca3  mov     r8d, 10A8h; Size
0x180032ca9  call    memset_0
0x180032cae  lea     r9, [rsp+10F8h+lParam]; lParam
0x180032cb3  mov     [rsp+10F8h+lParam], 9
0x180032cbc  xor     r8d, r8d; wParam
0x180032cbf  mov     [rsp+10F8h+var_10D0], 0
0x180032cc8  mov     edx, 703h; Msg
0x180032ccd  mov     rcx, rbx; hWnd
0x180032cd0  call    cs:__imp_SendMessageA
0x180032cd6  test    rax, rax
0x180032cd9  jz      short loc_180032CEB
0x180032cdb  lea     rdx, [rsp+10F8h+Parameters]; lpParameters
0x180032ce3  mov     rcx, rbx; hwndCaller
0x180032ce6  call    ?DisplayHtmlHelp@@YAXPEAUHWND__@@PEBG@Z; DisplayHtmlHelp(HWND__ *,ushort const *)
0x180032ceb  mov     rcx, [rsp+10F8h+var_18]
0x180032cf3  xor     rcx, rsp; StackCookie
0x180032cf6  call    __security_check_cookie
0x180032cfb  add     rsp, 10F0h
0x180032d02  pop     rbx
0x180032d03  retn
```
