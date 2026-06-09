# Combo<ulong>::GetItemLParam(int,ulong * *)

- ea: `0x18000fc30`
- end: `0x18000fc71`
- name: `?GetItemLParam@?$Combo@K@@QEBAJHPEAPEAK@Z`
- size: `65`
- prototype: `__int64 __fastcall(HWND *, int, LRESULT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fc80`

## callees

- `0x18000fc30`

## import_xrefs

- `USER32!SendMessageW` at `0x18000fc53`
- `USER32!SendMessageW` at `0x18000fc53`

## pseudocode

```c
__int64 __fastcall Combo<unsigned long>::GetItemLParam(HWND *a1, int a2, LRESULT *a3)
{
  LRESULT v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v5 = SendMessageW(*a1, 0x150u, a2, 0);
  if ( v5 == -1 )
    return 2147500037LL;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000fc30  push    rbx
0x18000fc32  sub     rsp, 20h
0x18000fc36  mov     rbx, r8
0x18000fc39  test    r8, r8
0x18000fc3c  jnz     short loc_18000FC45
0x18000fc3e  mov     eax, 80070057h
0x18000fc43  jmp     short loc_18000FC6B
0x18000fc45  mov     rcx, [rcx]; hWnd
0x18000fc48  xor     r9d, r9d; lParam
0x18000fc4b  movsxd  r8, edx; wParam
0x18000fc4e  mov     edx, 150h; Msg
0x18000fc53  call    cs:__imp_SendMessageW
0x18000fc59  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fc5d  jnz     short loc_18000FC66
0x18000fc5f  mov     eax, 80004005h
0x18000fc64  jmp     short loc_18000FC6B
0x18000fc66  mov     [rbx], rax
0x18000fc69  xor     eax, eax
0x18000fc6b  add     rsp, 20h
0x18000fc6f  pop     rbx
0x18000fc70  retn
```
