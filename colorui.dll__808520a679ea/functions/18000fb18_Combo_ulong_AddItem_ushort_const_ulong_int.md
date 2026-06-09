# Combo<ulong>::AddItem(ushort const *,ulong *,int *)

- ea: `0x18000fb18`
- end: `0x18000fbae`
- name: `?AddItem@?$Combo@K@@QEAAJPEBGPEAKPEAH@Z`
- size: `150`
- prototype: `__int64 __fastcall(HWND *, LPARAM, LPARAM, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ffe0`
- `0x180010404`
- `0x180010780`

## callees

- `0x18000fb18`

## import_xrefs

- `USER32!SendMessageW` at `0x18000fb3e`
- `USER32!SendMessageW` at `0x18000fb6d`
- `USER32!SendMessageW` at `0x18000fb8a`
- `USER32!SendMessageW` at `0x18000fb3e`
- `USER32!SendMessageW` at `0x18000fb6d`
- `USER32!SendMessageW` at `0x18000fb8a`

## pseudocode

```c
__int64 __fastcall Combo<unsigned long>::AddItem(HWND *a1, LPARAM a2, LPARAM a3, int *a4)
{
  int v7; // eax
  int v8; // edi
  int v9; // r14d
  int v10; // ebx

  v7 = SendMessageW(*a1, 0x143u, 0, a2);
  v8 = -1;
  v9 = v7;
  if ( v7 == -1 )
  {
    v10 = -2147467259;
  }
  else
  {
    v10 = 0;
    if ( a3 && (unsigned int)SendMessageW(*a1, 0x151u, v7, a3) == -1 )
    {
      v10 = -2147467259;
      SendMessageW(*a1, 0x144u, v9, 0);
    }
  }
  if ( a4 )
  {
    if ( v10 >= 0 )
      v8 = v9;
    *a4 = v8;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000fb18  push    rbx
0x18000fb1a  push    rbp
0x18000fb1b  push    rsi
0x18000fb1c  push    rdi
0x18000fb1d  push    r12
0x18000fb1f  push    r14
0x18000fb21  push    r15
0x18000fb23  sub     rsp, 20h
0x18000fb27  mov     rsi, r9
0x18000fb2a  mov     rbp, r8
0x18000fb2d  mov     r9, rdx; lParam
0x18000fb30  mov     r15, rcx
0x18000fb33  mov     rcx, [rcx]; hWnd
0x18000fb36  mov     edx, 143h; Msg
0x18000fb3b  xor     r8d, r8d; wParam
0x18000fb3e  call    cs:__imp_SendMessageW
0x18000fb44  or      edi, 0FFFFFFFFh
0x18000fb47  mov     r14, rax
0x18000fb4a  cmp     eax, edi
0x18000fb4c  jnz     short loc_18000FB55
0x18000fb4e  mov     ebx, 80004005h
0x18000fb53  jmp     short loc_18000FB90
0x18000fb55  xor     ebx, ebx
0x18000fb57  test    rbp, rbp
0x18000fb5a  jz      short loc_18000FB90
0x18000fb5c  mov     rcx, [r15]; hWnd
0x18000fb5f  mov     r9, rbp; lParam
0x18000fb62  movsxd  r12, r14d
0x18000fb65  mov     edx, 151h; Msg
0x18000fb6a  mov     r8, r12; wParam
0x18000fb6d  call    cs:__imp_SendMessageW
0x18000fb73  cmp     eax, edi
0x18000fb75  jnz     short loc_18000FB90
0x18000fb77  mov     ebx, 80004005h
0x18000fb7c  mov     rcx, [r15]; hWnd
0x18000fb7f  xor     r9d, r9d; lParam
0x18000fb82  mov     r8, r12; wParam
0x18000fb85  mov     edx, 144h; Msg
0x18000fb8a  call    cs:__imp_SendMessageW
0x18000fb90  test    rsi, rsi
0x18000fb93  jz      short loc_18000FB9D
0x18000fb95  test    ebx, ebx
0x18000fb97  cmovns  edi, r14d
0x18000fb9b  mov     [rsi], edi
0x18000fb9d  mov     eax, ebx
0x18000fb9f  add     rsp, 20h
0x18000fba3  pop     r15
0x18000fba5  pop     r14
0x18000fba7  pop     r12
0x18000fba9  pop     rdi
0x18000fbaa  pop     rsi
0x18000fbab  pop     rbp
0x18000fbac  pop     rbx
0x18000fbad  retn
```
