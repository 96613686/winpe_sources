# CIsoBurnUI::OnComplete(ISO_BURN_STATUS,long)

- ea: `0x14000ad10`
- end: `0x14000ad30`
- name: `?OnComplete@CIsoBurnUI@@UEAAJW4ISO_BURN_STATUS@@J@Z`
- size: `32`
- prototype: `int __high(enum ISO_BURN_STATUS, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `USER32!PostMessageW` at `0x14000ad23`
- `USER32!PostMessageW` at `0x14000ad23`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::OnComplete(__int64 a1, unsigned int a2, int a3)
{
  PostMessageW(*(HWND *)(a1 - 56), 0x8001u, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x14000ad10  sub     rsp, 28h
0x14000ad14  mov     rcx, [rcx-38h]; hWnd
0x14000ad18  movsxd  r9, r8d; lParam
0x14000ad1b  mov     r8d, edx; wParam
0x14000ad1e  mov     edx, 8001h; Msg
0x14000ad23  call    cs:__imp_PostMessageW
0x14000ad29  xor     eax, eax
0x14000ad2b  add     rsp, 28h
0x14000ad2f  retn
```
