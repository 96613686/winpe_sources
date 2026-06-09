# UpdateCustomFormats

- ea: `0x1800115f0`
- end: `0x1800116c0`
- name: `UpdateCustomFormats`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000fba0`

## callees

- `0x1800074d0`
- `0x180008964`
- `0x18000a250`
- `0x18000eb6c`
- `0x18000f24c`
- `0x18000fb50`
- `0x1800102b0`
- `0x1800115f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011681`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011681`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18001162d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180011642`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180011675`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800116a1`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18001162d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180011642`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180011675`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800116a1`

## pseudocode

```c
__int64 __fastcall UpdateCustomFormats(__int64 a1)
{
  __int64 result; // rax
  HWND *v3; // rsi
  void *v4; // rbp
  int v5; // eax
  int v6; // ebx
  int v7; // eax

  result = IsSendMessageWPresent();
  if ( (_BYTE)result )
  {
    v3 = (HWND *)(a1 + 56);
    v4 = (void *)NewNameStore(128);
    if ( v4 )
    {
      v5 = SendMessageW(*v3, 0x147u, 0, 0);
      SendMessageW(*v3, 0x148u, v5, (LPARAM)v4 + 2);
    }
    EmptyCustomFormats(a1);
    InitCustomFormats(a1);
    RefreshCustomFormats(a1);
    if ( v4 )
    {
      v6 = SendMessageW(*v3, 0x158u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v4 + 2);
      LocalFree(v4);
      v7 = 0;
      if ( v6 != -1 )
        v7 = v6;
    }
    else
    {
      v7 = 0;
    }
    SendMessageW(*v3, 0x14Eu, v7, 0);
    SelectCustomFormat(a1);
    return FindSelCustomFormat(a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800115f0  push    rbx
0x1800115f2  push    rbp
0x1800115f3  push    rsi
0x1800115f4  push    rdi
0x1800115f5  sub     rsp, 28h
0x1800115f9  mov     rdi, rcx
0x1800115fc  call    IsSendMessageWPresent
0x180011601  test    al, al
0x180011603  jz      loc_1800116B7
0x180011609  mov     ecx, 80h
0x18001160e  call    NewNameStore
0x180011613  lea     rsi, [rdi+38h]
0x180011617  mov     rbp, rax
0x18001161a  test    rax, rax
0x18001161d  jz      short loc_180011648
0x18001161f  mov     rcx, [rsi]; hWnd
0x180011622  xor     r9d, r9d; lParam
0x180011625  xor     r8d, r8d; wParam
0x180011628  mov     edx, 147h; Msg
0x18001162d  call    cs:__imp_SendMessageW
0x180011633  mov     rcx, [rsi]; hWnd
0x180011636  lea     r9, [rbp+2]; lParam
0x18001163a  movsxd  r8, eax; wParam
0x18001163d  mov     edx, 148h; Msg
0x180011642  call    cs:__imp_SendMessageW
0x180011648  mov     rcx, rdi
0x18001164b  call    EmptyCustomFormats
0x180011650  mov     rcx, rdi
0x180011653  call    InitCustomFormats
0x180011658  mov     rcx, rdi
0x18001165b  call    RefreshCustomFormats
0x180011660  test    rbp, rbp
0x180011663  jz      short loc_180011691
0x180011665  mov     rcx, [rsi]; hWnd
0x180011668  lea     r9, [rbp+2]; lParam
0x18001166c  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180011670  mov     edx, 158h; Msg
0x180011675  call    cs:__imp_SendMessageW
0x18001167b  mov     rcx, rbp; hMem
0x18001167e  mov     rbx, rax
0x180011681  call    cs:__imp_LocalFree
0x180011687  xor     eax, eax
0x180011689  cmp     ebx, 0FFFFFFFFh
0x18001168c  cmovnz  eax, ebx
0x18001168f  jmp     short loc_180011693
0x180011691  xor     eax, eax
0x180011693  mov     rcx, [rsi]; hWnd
0x180011696  xor     r9d, r9d; lParam
0x180011699  movsxd  r8, eax; wParam
0x18001169c  mov     edx, 14Eh; Msg
0x1800116a1  call    cs:__imp_SendMessageW
0x1800116a7  mov     rcx, rdi
0x1800116aa  call    SelectCustomFormat
0x1800116af  mov     rcx, rdi
0x1800116b2  call    FindSelCustomFormat
0x1800116b7  add     rsp, 28h
0x1800116bb  pop     rdi
0x1800116bc  pop     rsi
0x1800116bd  pop     rbp
0x1800116be  pop     rbx
0x1800116bf  retn
```
