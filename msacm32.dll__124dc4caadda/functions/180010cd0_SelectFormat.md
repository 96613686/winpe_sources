# SelectFormat

- ea: `0x180010cd0`
- end: `0x180010da0`
- name: `SelectFormat`
- size: `208`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e608`
- `0x18000e7d4`
- `0x18000f330`
- `0x18000fba0`

## callees

- `0x18000a250`
- `0x18000df38`
- `0x180010cd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010d2f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010d2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010d10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010d26`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010d10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010d26`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180010d19`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180010d19`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010cf9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010d51`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010cf9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010d51`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010d83`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010d8f`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010d83`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010d8f`

## pseudocode

```c
char __fastcall SelectFormat(__int64 a1)
{
  int v2; // eax
  const void *v3; // rcx
  HGLOBAL v4; // rax
  HGLOBAL v5; // rax
  unsigned __int16 *v6; // rax
  void *v7; // rax
  BOOL v8; // ebx

  LOBYTE(v2) = IsSendMessageWPresent();
  if ( (_BYTE)v2 )
  {
    v2 = SendMessageW(*(HWND *)(a1 + 40), 0x147u, 0, 0);
    if ( v2 == -1 )
    {
      v3 = *(const void **)(a1 + 192);
      if ( v3 )
      {
        v4 = GlobalHandle(v3);
        GlobalUnlock(v4);
        v5 = GlobalHandle(*(LPCVOID *)(a1 + 192));
        LOBYTE(v2) = (unsigned __int8)GlobalFree(v5);
      }
      *(_QWORD *)(a1 + 192) = 0;
    }
    else
    {
      v6 = (unsigned __int16 *)SendMessageW(*(HWND *)(a1 + 40), 0x150u, v2, 0);
      v7 = CopyStruct(*(LPCVOID *)(a1 + 192), v6, *(_DWORD *)a1);
      if ( v7 )
        *(_QWORD *)(a1 + 192) = v7;
      v8 = v7 != 0;
      EnableWindow(*(HWND *)(a1 + 64), v8);
      LOBYTE(v2) = EnableWindow(*(HWND *)(a1 + 88), v8);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180010cd0  mov     [rsp+arg_0], rbx
0x180010cd5  push    rdi
0x180010cd6  sub     rsp, 20h
0x180010cda  mov     rdi, rcx
0x180010cdd  call    IsSendMessageWPresent
0x180010ce2  test    al, al
0x180010ce4  jz      loc_180010D95
0x180010cea  mov     rcx, [rdi+28h]; hWnd
0x180010cee  xor     r9d, r9d; lParam
0x180010cf1  xor     r8d, r8d; wParam
0x180010cf4  mov     edx, 147h; Msg
0x180010cf9  call    cs:__imp_SendMessageW
0x180010cff  cmp     eax, 0FFFFFFFFh
0x180010d02  jnz     short loc_180010D42
0x180010d04  mov     rcx, [rdi+0C0h]; pMem
0x180010d0b  test    rcx, rcx
0x180010d0e  jz      short loc_180010D35
0x180010d10  call    cs:__imp_GlobalHandle
0x180010d16  mov     rcx, rax; hMem
0x180010d19  call    cs:__imp_GlobalUnlock
0x180010d1f  mov     rcx, [rdi+0C0h]; pMem
0x180010d26  call    cs:__imp_GlobalHandle
0x180010d2c  mov     rcx, rax; hMem
0x180010d2f  call    cs:__imp_GlobalFree
0x180010d35  mov     qword ptr [rdi+0C0h], 0
0x180010d40  jmp     short loc_180010D95
0x180010d42  mov     rcx, [rdi+28h]; hWnd
0x180010d46  xor     r9d, r9d; lParam
0x180010d49  movsxd  r8, eax; wParam
0x180010d4c  mov     edx, 150h; Msg
0x180010d51  call    cs:__imp_SendMessageW
0x180010d57  mov     r8d, [rdi]
0x180010d5a  mov     rdx, rax; Src
0x180010d5d  mov     rcx, [rdi+0C0h]; pMem
0x180010d64  call    CopyStruct
0x180010d69  test    rax, rax
0x180010d6c  jz      short loc_180010D75
0x180010d6e  mov     [rdi+0C0h], rax
0x180010d75  mov     rcx, [rdi+40h]; hWnd
0x180010d79  xor     ebx, ebx
0x180010d7b  test    rax, rax
0x180010d7e  setnz   bl
0x180010d81  mov     edx, ebx; bEnable
0x180010d83  call    cs:__imp_EnableWindow
0x180010d89  mov     rcx, [rdi+58h]; hWnd
0x180010d8d  mov     edx, ebx; bEnable
0x180010d8f  call    cs:__imp_EnableWindow
0x180010d95  mov     rbx, [rsp+28h+arg_0]
0x180010d9a  add     rsp, 20h
0x180010d9e  pop     rdi
0x180010d9f  retn
```
