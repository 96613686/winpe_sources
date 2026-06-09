# _RemoveShieldIcon

- ea: `0x180001d40`
- end: `0x180001d6a`
- name: `_RemoveShieldIcon`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001d40`

## import_xrefs

- `USER32!SendMessageW` at `0x180001d4f`
- `USER32!SendMessageW` at `0x180001d4f`
- `USER32!DestroyIcon` at `0x180001d5d`
- `USER32!DestroyIcon` at `0x180001d5d`

## pseudocode

```c
__int64 __fastcall RemoveShieldIcon(HWND a1)
{
  HICON v1; // rax

  v1 = (HICON)SendMessageW(a1, 0x170u, 0, 0);
  if ( v1 )
    DestroyIcon(v1);
  return 0;
}

```

## disassembly

```asm
0x180001d40  sub     rsp, 28h
0x180001d44  xor     r9d, r9d; lParam
0x180001d47  xor     r8d, r8d; wParam
0x180001d4a  mov     edx, 170h; Msg
0x180001d4f  call    cs:__imp_SendMessageW
0x180001d55  test    rax, rax
0x180001d58  jz      short loc_180001D63
0x180001d5a  mov     rcx, rax; hIcon
0x180001d5d  call    cs:__imp_DestroyIcon
0x180001d63  xor     eax, eax
0x180001d65  add     rsp, 28h
0x180001d69  retn
```
