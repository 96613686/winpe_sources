# IDriverBroadcastNotify

- ea: `0x180008dd8`
- end: `0x180008e6c`
- name: `IDriverBroadcastNotify`
- size: `148`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012a0`
- `0x180002900`
- `0x180005990`
- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`
- `0x18000da50`
- `0x1800119c0`

## callees

- `0x180002220`
- `0x1800043d0`
- `0x180008dd8`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180008e2b`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180008e2b`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180008e16`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180008e16`

## pseudocode

```c
__int64 __fastcall IDriverBroadcastNotify(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v2; // r8
  __int64 v3; // rbx
  int v4; // eax
  HWND v5; // rdi
  UINT v6; // esi
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  v1 = a1;
  v8 = 0;
  v2 = 0;
  while ( !(unsigned int)IDriverGetNext(a1, &v8, v2, 0xFFFFFFFF) )
  {
    v3 = v8;
    v4 = *(_DWORD *)(v8 + 56);
    if ( (v4 & 1) != 0 && v4 >= 0 )
    {
      if ( (*(_BYTE *)(v8 + 52) & 7) == 4 )
      {
        v5 = *(HWND *)(v8 + 44);
        v6 = *(_DWORD *)(v8 + 104);
        if ( IsWindow(v5) )
          PostMessageW(v5, v6, 0, 0);
      }
      else
      {
        IDriverMessageId(v8, 0x6001u, 0, 0);
      }
    }
    v2 = v3;
    a1 = v1;
  }
  return 1;
}

```

## disassembly

```asm
0x180008dd8  push    rbx
0x180008dda  push    rbp
0x180008ddb  push    rsi
0x180008ddc  push    rdi
0x180008ddd  sub     rsp, 28h
0x180008de1  mov     rbp, rcx
0x180008de4  mov     [rsp+48h+arg_8], 0
0x180008ded  xor     r8d, r8d
0x180008df0  jmp     short loc_180008E4C
0x180008df2  mov     rbx, [rsp+48h+arg_8]
0x180008df7  mov     eax, [rbx+38h]
0x180008dfa  test    al, 1
0x180008dfc  jz      short loc_180008E46
0x180008dfe  test    eax, eax
0x180008e00  js      short loc_180008E46
0x180008e02  mov     eax, [rbx+34h]
0x180008e05  and     eax, 7
0x180008e08  cmp     al, 4
0x180008e0a  jnz     short loc_180008E33
0x180008e0c  mov     rdi, [rbx+2Ch]
0x180008e10  mov     esi, [rbx+68h]
0x180008e13  mov     rcx, rdi; hWnd
0x180008e16  call    cs:__imp_IsWindow
0x180008e1c  test    eax, eax
0x180008e1e  jz      short loc_180008E46
0x180008e20  xor     r9d, r9d; lParam
0x180008e23  xor     r8d, r8d; wParam
0x180008e26  mov     edx, esi; Msg
0x180008e28  mov     rcx, rdi; hWnd
0x180008e2b  call    cs:__imp_PostMessageW
0x180008e31  jmp     short loc_180008E46
0x180008e33  xor     r9d, r9d
0x180008e36  xor     r8d, r8d
0x180008e39  mov     edx, 6001h
0x180008e3e  mov     rcx, rbx
0x180008e41  call    IDriverMessageId
0x180008e46  mov     r8, rbx
0x180008e49  mov     rcx, rbp
0x180008e4c  or      r9d, 0FFFFFFFFh
0x180008e50  lea     rdx, [rsp+48h+arg_8]
0x180008e55  call    IDriverGetNext
0x180008e5a  test    eax, eax
0x180008e5c  jz      short loc_180008DF2
0x180008e5e  mov     eax, 1
0x180008e63  add     rsp, 28h
0x180008e67  pop     rdi
0x180008e68  pop     rsi
0x180008e69  pop     rbp
0x180008e6a  pop     rbx
0x180008e6b  retn
```
