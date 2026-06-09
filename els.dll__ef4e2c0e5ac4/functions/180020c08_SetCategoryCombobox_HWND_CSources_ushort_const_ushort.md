# SetCategoryCombobox(HWND__ *,CSources *,ushort const *,ushort)

- ea: `0x180020c08`
- end: `0x180020cdb`
- name: `?SetCategoryCombobox@@YAXPEAUHWND__@@PEAVCSources@@PEBGG@Z`
- size: `211`
- prototype: `void(HWND, struct CSources *, const unsigned __int16 *, unsigned __int16)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011bc0`
- `0x180012940`
- `0x18001edf0`
- `0x180020160`

## callees

- `0x180004710`
- `0x180004774`
- `0x180020c08`

## import_xrefs

- `USER32!SendMessageW` at `0x180020c39`
- `USER32!SendMessageW` at `0x180020c51`
- `USER32!SendMessageW` at `0x180020c97`
- `USER32!SendMessageW` at `0x180020c39`
- `USER32!SendMessageW` at `0x180020c51`
- `USER32!SendMessageW` at `0x180020c97`
- `USER32!SendMessageW` at `0x180020cd4`
- `USER32!GetDlgItem` at `0x180020c22`
- `USER32!GetDlgItem` at `0x180020c22`

## pseudocode

```c
void __fastcall SetCategoryCombobox(HWND a1, struct CSources *a2, const unsigned __int16 *a3, unsigned __int16 a4)
{
  unsigned int v5; // ebp
  HWND DlgItem; // rsi
  struct CCategories *Categories; // rax
  CCategories *v9; // rbx
  unsigned int v10; // edi
  const unsigned __int16 *Name; // rax
  LPARAM *v12; // r9

  v5 = a4;
  DlgItem = GetDlgItem(a1, 127);
  SendMessageW(DlgItem, 0x14Bu, 0, 0);
  SendMessageW(DlgItem, 0x143u, 0, (LPARAM)&g_wszAll);
  if ( !a3 )
    goto LABEL_8;
  Categories = CSources::GetCategories(a2, a3);
  v9 = Categories;
  if ( !Categories )
    goto LABEL_8;
  if ( !*(_DWORD *)Categories )
    goto LABEL_8;
  v10 = 1;
  do
  {
    Name = CCategories::GetName(v9, v10);
    SendMessageW(DlgItem, 0x143u, 0, (LPARAM)Name);
    ++v10;
  }
  while ( v10 <= *(_DWORD *)v9 );
  if ( (_WORD)v5 )
    v12 = (LPARAM *)CCategories::GetName(v9, v5);
  else
LABEL_8:
    v12 = &g_wszAll;
  SendMessageW(DlgItem, 0x14Du, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v12);
}

```

## disassembly

```asm
0x180020c08  push    rbx
0x180020c0a  push    rbp
0x180020c0b  push    rsi
0x180020c0c  push    rdi
0x180020c0d  push    r14
0x180020c0f  sub     rsp, 20h
0x180020c13  mov     rdi, rdx
0x180020c16  movzx   ebp, r9w
0x180020c1a  mov     edx, 7Fh; nIDDlgItem
0x180020c1f  mov     rbx, r8
0x180020c22  call    cs:__imp_GetDlgItem
0x180020c28  xor     r9d, r9d; lParam
0x180020c2b  xor     r8d, r8d; wParam
0x180020c2e  mov     rcx, rax; hWnd
0x180020c31  mov     edx, 14Bh; Msg
0x180020c36  mov     rsi, rax
0x180020c39  call    cs:__imp_SendMessageW
0x180020c3f  lea     r9, ?g_wszAll@@3PAGA; lParam
0x180020c46  xor     r8d, r8d; wParam
0x180020c49  mov     edx, 143h; Msg
0x180020c4e  mov     rcx, rsi; hWnd
0x180020c51  call    cs:__imp_SendMessageW
0x180020c57  xor     r14d, r14d
0x180020c5a  test    rbx, rbx
0x180020c5d  jz      short loc_180020CB7
0x180020c5f  mov     rdx, rbx; unsigned __int16 *
0x180020c62  mov     rcx, rdi; this
0x180020c65  call    ?GetCategories@CSources@@QEAAPEAVCCategories@@PEBG@Z; CSources::GetCategories(ushort const *)
0x180020c6a  mov     rbx, rax
0x180020c6d  test    rax, rax
0x180020c70  jz      short loc_180020CB7
0x180020c72  cmp     [rax], r14d
0x180020c75  jz      short loc_180020CB7
0x180020c77  lea     edi, [r14+1]
0x180020c7b  cmp     [rax], edi
0x180020c7d  jb      short loc_180020CA3
0x180020c7f  mov     edx, edi; unsigned int
0x180020c81  mov     rcx, rbx; this
0x180020c84  call    ?GetName@CCategories@@QEAAPEBGK@Z; CCategories::GetName(ulong)
0x180020c89  mov     r9, rax; lParam
0x180020c8c  xor     r8d, r8d; wParam
0x180020c8f  mov     edx, 143h; Msg
0x180020c94  mov     rcx, rsi; hWnd
0x180020c97  call    cs:__imp_SendMessageW
0x180020c9d  inc     edi
0x180020c9f  cmp     edi, [rbx]
0x180020ca1  jbe     short loc_180020C7F
0x180020ca3  test    bp, bp
0x180020ca6  jz      short loc_180020CB7
0x180020ca8  mov     edx, ebp; unsigned int
0x180020caa  mov     rcx, rbx; this
0x180020cad  call    ?GetName@CCategories@@QEAAPEBGK@Z; CCategories::GetName(ulong)
0x180020cb2  mov     r9, rax
0x180020cb5  jmp     short loc_180020CBE
0x180020cb7  lea     r9, ?g_wszAll@@3PAGA; ushort near * g_wszAll
0x180020cbe  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020cc2  mov     edx, 14Dh
0x180020cc7  mov     rcx, rsi
0x180020cca  add     rsp, 20h
0x180020cce  pop     r14
0x180020cd0  pop     rdi
0x180020cd1  pop     rsi
0x180020cd2  pop     rbp
0x180020cd3  pop     rbx
0x180020cd4  jmp     cs:__imp_SendMessageW
```
