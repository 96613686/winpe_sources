# DlgTemplate::DialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000b400`
- end: `0x18000b47c`
- name: `?DialogProc@DlgTemplate@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `124`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b400`
- `0x18000b54c`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x18000b449`
- `USER32!SetWindowLongPtrW` at `0x18000b449`
- `USER32!GetWindowLongPtrW` at `0x18000b456`
- `USER32!GetWindowLongPtrW` at `0x18000b456`
- `USER32!EndDialog` at `0x18000b427`
- `USER32!EndDialog` at `0x18000b427`

## pseudocode

```c
INT_PTR __fastcall DlgTemplate::DialogProc(HWND a1, unsigned int a2, unsigned __int64 a3, LONG_PTR a4)
{
  HWND *WindowLongPtrW; // rsi

  if ( a2 == 272 )
  {
    if ( !a4 )
    {
      EndDialog(a1, -1);
      return 0;
    }
    *(_QWORD *)(a4 + 8) = a1;
    WindowLongPtrW = (HWND *)a4;
    SetWindowLongPtrW(a1, -21, a4);
  }
  else
  {
    WindowLongPtrW = (HWND *)GetWindowLongPtrW(a1, -21);
    if ( !WindowLongPtrW )
      return 0;
  }
  if ( WindowLongPtrW[1] != a1 )
    return 0;
  return DlgTemplate::ProcessMessage((DlgTemplate *)WindowLongPtrW, (HWND)a2, a3, a4);
}

```

## disassembly

```asm
0x18000b400  push    rbx
0x18000b402  push    rbp
0x18000b403  push    rsi
0x18000b404  push    rdi
0x18000b405  push    r14
0x18000b407  sub     rsp, 20h
0x18000b40b  mov     rdi, r9
0x18000b40e  mov     r14, r8
0x18000b411  mov     ebp, edx
0x18000b413  mov     rbx, rcx
0x18000b416  cmp     edx, 110h
0x18000b41c  jnz     short loc_18000B451
0x18000b41e  test    r9, r9
0x18000b421  jnz     short loc_18000B43A
0x18000b423  or      rdx, 0FFFFFFFFFFFFFFFFh; nResult
0x18000b427  call    cs:__imp_EndDialog
0x18000b42d  xor     eax, eax
0x18000b42f  add     rsp, 20h
0x18000b433  pop     r14
0x18000b435  pop     rdi
0x18000b436  pop     rsi
0x18000b437  pop     rbp
0x18000b438  pop     rbx
0x18000b439  retn
0x18000b43a  mov     r8, rdi; dwNewLong
0x18000b43d  mov     [r9+8], rbx
0x18000b441  mov     edx, 0FFFFFFEBh; nIndex
0x18000b446  mov     rsi, rdi
0x18000b449  call    cs:__imp_SetWindowLongPtrW
0x18000b44f  jmp     short loc_18000B464
0x18000b451  mov     edx, 0FFFFFFEBh; nIndex
0x18000b456  call    cs:__imp_GetWindowLongPtrW
0x18000b45c  mov     rsi, rax
0x18000b45f  test    rax, rax
0x18000b462  jz      short loc_18000B42D
0x18000b464  cmp     [rsi+8], rbx
0x18000b468  jnz     short loc_18000B42D
0x18000b46a  mov     r9, rdi; __int64
0x18000b46d  mov     r8, r14; unsigned __int64
0x18000b470  mov     edx, ebp; unsigned int
0x18000b472  mov     rcx, rsi; this
0x18000b475  call    ?ProcessMessage@DlgTemplate@@AEAA_JI_K_J@Z; DlgTemplate::ProcessMessage(uint,unsigned __int64,__int64)
0x18000b47a  jmp     short loc_18000B42F
```
