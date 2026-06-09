# SelectFormatTag

- ea: `0x180010da8`
- end: `0x180010e10`
- name: `SelectFormatTag`
- size: `104`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e608`
- `0x18000e7d4`
- `0x18000f330`
- `0x18000fba0`

## callees

- `0x18000a250`
- `0x180010da8`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010dcd`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010df6`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010dcd`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010df6`

## pseudocode

```c
char __fastcall SelectFormatTag(__int64 a1)
{
  int v2; // eax
  int v3; // edi

  LOBYTE(v2) = IsSendMessageWPresent();
  if ( (_BYTE)v2 )
  {
    v2 = SendMessageW(*(HWND *)(a1 + 24), 0x147u, 0, 0);
    v3 = v2;
    if ( v2 == -1 )
    {
      *(_DWORD *)(a1 + 200) = 0;
    }
    else
    {
      v2 = SendMessageW(*(HWND *)(a1 + 24), 0x150u, v2, 0);
      *(_DWORD *)(a1 + 200) = v2;
      *(_DWORD *)(a1 + 32) = v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180010da8  mov     [rsp+arg_0], rbx
0x180010dad  push    rdi
0x180010dae  sub     rsp, 20h
0x180010db2  mov     rbx, rcx
0x180010db5  call    IsSendMessageWPresent
0x180010dba  test    al, al
0x180010dbc  jz      short loc_180010E05
0x180010dbe  mov     rcx, [rbx+18h]; hWnd
0x180010dc2  xor     r9d, r9d; lParam
0x180010dc5  xor     r8d, r8d; wParam
0x180010dc8  mov     edx, 147h; Msg
0x180010dcd  call    cs:__imp_SendMessageW
0x180010dd3  mov     rdi, rax
0x180010dd6  cmp     eax, 0FFFFFFFFh
0x180010dd9  jnz     short loc_180010DE7
0x180010ddb  mov     dword ptr [rbx+0C8h], 0
0x180010de5  jmp     short loc_180010E05
0x180010de7  mov     rcx, [rbx+18h]; hWnd
0x180010deb  xor     r9d, r9d; lParam
0x180010dee  movsxd  r8, edi; wParam
0x180010df1  mov     edx, 150h; Msg
0x180010df6  call    cs:__imp_SendMessageW
0x180010dfc  mov     [rbx+0C8h], eax
0x180010e02  mov     [rbx+20h], edi
0x180010e05  mov     rbx, [rsp+28h+arg_0]
0x180010e0a  add     rsp, 20h
0x180010e0e  pop     rdi
0x180010e0f  retn
```
