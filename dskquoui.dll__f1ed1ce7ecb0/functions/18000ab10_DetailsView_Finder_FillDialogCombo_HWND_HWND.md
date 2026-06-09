# DetailsView::Finder::FillDialogCombo(HWND__ *,HWND__ *)

- ea: `0x18000ab10`
- end: `0x18000abdd`
- name: `?FillDialogCombo@Finder@DetailsView@@AEAAXPEAUHWND__@@0@Z`
- size: `205`
- prototype: `void(DetailsView::Finder *__hidden this, HWND, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a510`

## callees

- `0x180006ec0`
- `0x18000ab10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abc2`
- `USER32!SendMessageW` at `0x18000ab33`
- `USER32!SendMessageW` at `0x18000ab47`
- `USER32!SendMessageW` at `0x18000ab70`
- `USER32!SendMessageW` at `0x18000aba5`
- `USER32!SendMessageW` at `0x18000abb9`
- `USER32!SendMessageW` at `0x18000ab33`
- `USER32!SendMessageW` at `0x18000ab47`
- `USER32!SendMessageW` at `0x18000ab70`
- `USER32!SendMessageW` at `0x18000aba5`
- `USER32!SendMessageW` at `0x18000abb9`

## pseudocode

```c
void __fastcall DetailsView::Finder::FillDialogCombo(DetailsView::Finder *this, HWND a2, HWND a3)
{
  int v5; // eax
  int v6; // edi
  unsigned int v7; // ebx
  SIZE_T v8; // rax
  void *v9; // rax
  void *v10; // rsi

  SendMessageW(a3, 0x14Bu, 0, 0);
  v5 = SendMessageW(a2, 0x146u, 0, 0);
  v6 = v5;
  if ( v5 != -1 )
  {
    v7 = 0;
    if ( v5 > 0 )
    {
      do
      {
        v8 = saturated_mul((int)(SendMessageW(a2, 0x149u, v7, 0) + 1), 2u);
        v9 = operator new(v8);
        v10 = v9;
        if ( v9 )
        {
          SendMessageW(a2, 0x148u, v7, (LPARAM)v9);
          SendMessageW(a3, 0x143u, 0, (LPARAM)v10);
          LocalFree(v10);
        }
        ++v7;
      }
      while ( (int)v7 < v6 );
    }
  }
}

```

## disassembly

```asm
0x18000ab10  push    rbx
0x18000ab12  push    rbp
0x18000ab13  push    rsi
0x18000ab14  push    rdi
0x18000ab15  push    r12
0x18000ab17  push    r14
0x18000ab19  push    r15
0x18000ab1b  sub     rsp, 20h
0x18000ab1f  mov     r14, r8
0x18000ab22  mov     rbp, rdx
0x18000ab25  mov     rcx, r14; hWnd
0x18000ab28  xor     r9d, r9d; lParam
0x18000ab2b  xor     r8d, r8d; wParam
0x18000ab2e  mov     edx, 14Bh; Msg
0x18000ab33  call    cs:__imp_SendMessageW
0x18000ab39  xor     r9d, r9d; lParam
0x18000ab3c  xor     r8d, r8d; wParam
0x18000ab3f  mov     edx, 146h; Msg
0x18000ab44  mov     rcx, rbp; hWnd
0x18000ab47  call    cs:__imp_SendMessageW
0x18000ab4d  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ab51  mov     rdi, rax
0x18000ab54  cmp     eax, r12d
0x18000ab57  jz      short loc_18000ABCE
0x18000ab59  xor     ebx, ebx
0x18000ab5b  test    edi, edi
0x18000ab5d  jle     short loc_18000ABCE
0x18000ab5f  xor     r9d, r9d; lParam
0x18000ab62  mov     r8d, ebx; wParam
0x18000ab65  mov     edx, 149h; Msg
0x18000ab6a  mov     r15d, ebx
0x18000ab6d  mov     rcx, rbp; hWnd
0x18000ab70  call    cs:__imp_SendMessageW
0x18000ab76  inc     eax
0x18000ab78  movsxd  rcx, eax
0x18000ab7b  mov     eax, 2
0x18000ab80  mul     rcx
0x18000ab83  cmovb   rax, r12
0x18000ab87  mov     rcx, rax; uBytes
0x18000ab8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab8f  mov     rsi, rax
0x18000ab92  test    rax, rax
0x18000ab95  jz      short loc_18000ABC8
0x18000ab97  mov     r9, rax; lParam
0x18000ab9a  mov     r8d, r15d; wParam
0x18000ab9d  mov     edx, 148h; Msg
0x18000aba2  mov     rcx, rbp; hWnd
0x18000aba5  call    cs:__imp_SendMessageW
0x18000abab  mov     r9, rsi; lParam
0x18000abae  xor     r8d, r8d; wParam
0x18000abb1  mov     edx, 143h; Msg
0x18000abb6  mov     rcx, r14; hWnd
0x18000abb9  call    cs:__imp_SendMessageW
0x18000abbf  mov     rcx, rsi; hMem
0x18000abc2  call    cs:__imp_LocalFree
0x18000abc8  inc     ebx
0x18000abca  cmp     ebx, edi
0x18000abcc  jl      short loc_18000AB5F
0x18000abce  add     rsp, 20h
0x18000abd2  pop     r15
0x18000abd4  pop     r14
0x18000abd6  pop     r12
0x18000abd8  pop     rdi
0x18000abd9  pop     rsi
0x18000abda  pop     rbp
0x18000abdb  pop     rbx
0x18000abdc  retn
```
