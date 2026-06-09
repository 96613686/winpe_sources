# CListBase::PopulateComboBox(HWND__ *)

- ea: `0x1800186e8`
- end: `0x1800187a0`
- name: `?PopulateComboBox@CListBase@@QEAAXPEAUHWND__@@@Z`
- size: `184`
- prototype: `void(CListBase *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001151c`
- `0x18001fcac`

## callees

- `0x1800186e8`
- `0x180029b74`

## import_xrefs

- `USER32!SendMessageW` at `0x180018709`
- `USER32!SendMessageW` at `0x18001874a`
- `USER32!SendMessageW` at `0x180018762`
- `USER32!SendMessageW` at `0x180018709`
- `USER32!SendMessageW` at `0x18001874a`
- `USER32!SendMessageW` at `0x180018762`
- `USER32!SendMessageW` at `0x180018799`

## pseudocode

```c
void __fastcall CListBase::PopulateComboBox(CListBase *this, HWND a2)
{
  int *v4; // r14
  int v5; // r14d
  int i; // ebx
  PVOID ItemPtr; // rax
  LPARAM v8; // rbp
  int v9; // eax

  SendMessageW(a2, 0x14Bu, 0, 0);
  v4 = (int *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = *v4;
    for ( i = 0; i < v5; ++i )
    {
      ItemPtr = DSA_GetItemPtr(*((HDSA *)this + 1), i);
      v8 = (LPARAM)ItemPtr;
      if ( ItemPtr && (int)SendMessageW(a2, 0x14Au, i, (LPARAM)ItemPtr + 160) >= 0 )
        SendMessageW(a2, 0x151u, i, v8);
    }
  }
  v9 = *((_DWORD *)this + 5);
  if ( v9 < 0 )
  {
    *((_DWORD *)this + 5) = 0;
    v9 = 0;
  }
  SendMessageW(a2, 0x14Eu, (unsigned int)v9, 0);
}

```

## disassembly

```asm
0x1800186e8  push    rbx
0x1800186ea  push    rbp
0x1800186eb  push    rsi
0x1800186ec  push    rdi
0x1800186ed  push    r14
0x1800186ef  push    r15
0x1800186f1  sub     rsp, 28h
0x1800186f5  mov     rsi, rdx
0x1800186f8  mov     rdi, rcx
0x1800186fb  mov     rcx, rsi; hWnd
0x1800186fe  xor     r9d, r9d; lParam
0x180018701  xor     r8d, r8d; wParam
0x180018704  mov     edx, 14Bh; Msg
0x180018709  call    cs:__imp_SendMessageW
0x18001870f  mov     r14, [rdi+8]
0x180018713  test    r14, r14
0x180018716  jz      short loc_18001876F
0x180018718  mov     r14d, [r14]
0x18001871b  xor     ebx, ebx
0x18001871d  test    r14d, r14d
0x180018720  jle     short loc_18001876F
0x180018722  mov     rcx, [rdi+8]; hdsa
0x180018726  mov     edx, ebx; i
0x180018728  call    DSA_GetItemPtr
0x18001872d  mov     rbp, rax
0x180018730  test    rax, rax
0x180018733  jz      short loc_180018768
0x180018735  movsxd  r15, ebx
0x180018738  lea     r9, [rax+0A0h]; lParam
0x18001873f  mov     r8, r15; wParam
0x180018742  mov     edx, 14Ah; Msg
0x180018747  mov     rcx, rsi; hWnd
0x18001874a  call    cs:__imp_SendMessageW
0x180018750  test    eax, eax
0x180018752  js      short loc_180018768
0x180018754  mov     r9, rbp; lParam
0x180018757  mov     r8, r15; wParam
0x18001875a  mov     edx, 151h; Msg
0x18001875f  mov     rcx, rsi; hWnd
0x180018762  call    cs:__imp_SendMessageW
0x180018768  inc     ebx
0x18001876a  cmp     ebx, r14d
0x18001876d  jl      short loc_180018722
0x18001876f  mov     eax, [rdi+14h]
0x180018772  test    eax, eax
0x180018774  jns     short loc_18001877F
0x180018776  mov     dword ptr [rdi+14h], 0
0x18001877d  xor     eax, eax
0x18001877f  mov     r8d, eax
0x180018782  xor     r9d, r9d
0x180018785  mov     edx, 14Eh
0x18001878a  mov     rcx, rsi
0x18001878d  add     rsp, 28h
0x180018791  pop     r15
0x180018793  pop     r14
0x180018795  pop     rdi
0x180018796  pop     rsi
0x180018797  pop     rbp
0x180018798  pop     rbx
0x180018799  jmp     cs:__imp_SendMessageW
```
