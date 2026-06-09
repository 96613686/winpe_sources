# SetColumnWidth

- ea: `0x18000dc18`
- end: `0x18000dc61`
- name: `SetColumnWidth`
- size: `73`
- prototype: `__int64 __fastcall(HWND hWnd, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a3b0`
- `0x18000b9c0`
- `0x18000d208`

## callees

- `0x18000dc18`

## import_xrefs

- `USER32!SendMessageW` at `0x18000dc43`
- `USER32!SendMessageW` at `0x18000dc43`

## pseudocode

```c
__int64 __fastcall SetColumnWidth(HWND hWnd, int a2)
{
  unsigned int i; // ebx

  for ( i = 0; (int)i < a2; ++i )
    SendMessageW(hWnd, 0x101Eu, i, 65534);
  return 0;
}

```

## disassembly

```asm
0x18000dc18  mov     [rsp+arg_0], rbx
0x18000dc1d  mov     [rsp+arg_8], rsi
0x18000dc22  push    rdi
0x18000dc23  sub     rsp, 20h
0x18000dc27  xor     ebx, ebx
0x18000dc29  mov     edi, edx
0x18000dc2b  mov     rsi, rcx
0x18000dc2e  test    edx, edx
0x18000dc30  jle     short loc_18000DC4F
0x18000dc32  mov     r8d, ebx; wParam
0x18000dc35  mov     edx, 101Eh; Msg
0x18000dc3a  mov     r9d, 0FFFEh; lParam
0x18000dc40  mov     rcx, rsi; hWnd
0x18000dc43  call    cs:__imp_SendMessageW
0x18000dc49  inc     ebx
0x18000dc4b  cmp     ebx, edi
0x18000dc4d  jl      short loc_18000DC32
0x18000dc4f  mov     rbx, [rsp+28h+arg_0]
0x18000dc54  xor     eax, eax
0x18000dc56  mov     rsi, [rsp+28h+arg_8]
0x18000dc5b  add     rsp, 20h
0x18000dc5f  pop     rdi
0x18000dc60  retn
```
