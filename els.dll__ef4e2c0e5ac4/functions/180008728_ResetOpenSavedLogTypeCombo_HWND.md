# _ResetOpenSavedLogTypeCombo(HWND__ *)

- ea: `0x180008728`
- end: `0x1800087b3`
- name: `?_ResetOpenSavedLogTypeCombo@@YAXPEAUHWND__@@@Z`
- size: `139`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007f70`
- `0x18000839c`

## callees

- `0x180001910`
- `0x180008728`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000878a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000878a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000877f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000877f`
- `USER32!SendMessageW` at `0x18000873f`
- `USER32!SendMessageW` at `0x18000875c`
- `USER32!SendMessageW` at `0x18000873f`
- `USER32!SendMessageW` at `0x18000875c`
- `USER32!SendMessageW` at `0x1800087ac`

## pseudocode

```c
void __fastcall _ResetOpenSavedLogTypeCombo(HWND hWnd)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebp
  char *v4; // rax
  __int64 v5; // rdx
  void *v6; // rsi

  v2 = 0;
  v3 = SendMessageW(hWnd, 0x146u, 0, 0);
  if ( v3 )
  {
    do
    {
      v4 = (char *)SendMessageW(hWnd, 0x150u, (int)v2, 0);
      if ( v2 )
      {
        v6 = v4;
        if ( v4 )
        {
          LOBYTE(v5) = 1;
          std::wstring::_Tidy(v4 + 8, v5, 0);
          operator delete(v6);
        }
      }
      else
      {
        operator delete[](v4);
      }
      ++v2;
    }
    while ( v2 < v3 );
  }
  SendMessageW(hWnd, 0x14Bu, 0, 0);
}

```

## disassembly

```asm
0x180008728  push    rbx
0x18000872a  push    rbp
0x18000872b  push    rsi
0x18000872c  push    rdi
0x18000872d  sub     rsp, 28h
0x180008731  xor     r9d, r9d; lParam
0x180008734  xor     r8d, r8d; wParam
0x180008737  mov     edx, 146h; Msg
0x18000873c  mov     rdi, rcx
0x18000873f  call    cs:__imp_SendMessageW
0x180008745  xor     ebx, ebx
0x180008747  mov     rbp, rax
0x18000874a  test    eax, eax
0x18000874c  jz      short loc_180008796
0x18000874e  movsxd  r8, ebx; wParam
0x180008751  xor     r9d, r9d; lParam
0x180008754  mov     edx, 150h; Msg
0x180008759  mov     rcx, rdi; hWnd
0x18000875c  call    cs:__imp_SendMessageW
0x180008762  test    ebx, ebx
0x180008764  jz      short loc_180008787
0x180008766  mov     rsi, rax
0x180008769  test    rax, rax
0x18000876c  jz      short loc_180008790
0x18000876e  lea     rcx, [rax+8]
0x180008772  xor     r8d, r8d
0x180008775  mov     dl, 1
0x180008777  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000877c  mov     rcx, rsi
0x18000877f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008785  jmp     short loc_180008790
0x180008787  mov     rcx, rax
0x18000878a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008790  inc     ebx
0x180008792  cmp     ebx, ebp
0x180008794  jb      short loc_18000874E
0x180008796  xor     r9d, r9d
0x180008799  xor     r8d, r8d
0x18000879c  mov     edx, 14Bh
0x1800087a1  mov     rcx, rdi
0x1800087a4  add     rsp, 28h
0x1800087a8  pop     rdi
0x1800087a9  pop     rsi
0x1800087aa  pop     rbp
0x1800087ab  pop     rbx
0x1800087ac  jmp     cs:__imp_SendMessageW
```
