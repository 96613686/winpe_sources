# CComboBox::AddString(ushort *)

- ea: `0x180008bbc`
- end: `0x180008cb7`
- name: `?AddString@CComboBox@@QEAAHPEAG@Z`
- size: `251`
- prototype: `int(CComboBox *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800099f0`

## callees

- `0x180008bbc`

## import_xrefs

- `USER32!SendMessageW` at `0x180008c10`
- `USER32!SendMessageW` at `0x180008c8a`
- `USER32!SendMessageW` at `0x180008c10`
- `USER32!SendMessageW` at `0x180008c8a`
- `USER32!SendMessageW` at `0x180008cb0`
- `USER32!GetDC` at `0x180008bde`
- `USER32!GetDC` at `0x180008bde`
- `USER32!ReleaseDC` at `0x180008c6e`
- `USER32!ReleaseDC` at `0x180008c6e`
- `USER32!GetSystemMetrics` at `0x180008c50`
- `USER32!GetSystemMetrics` at `0x180008c50`
- `GDI32!SelectObject` at `0x180008c21`
- `GDI32!SelectObject` at `0x180008c21`
- `GDI32!GetTextExtentPoint32W` at `0x180008c41`
- `GDI32!GetTextExtentPoint32W` at `0x180008c41`
- `GDI32!RestoreDC` at `0x180008c62`
- `GDI32!RestoreDC` at `0x180008c62`
- `GDI32!SaveDC` at `0x180008bf3`
- `GDI32!SaveDC` at `0x180008bf3`

## pseudocode

```c
LRESULT __fastcall CComboBox::AddString(HWND *this, unsigned __int16 *a2)
{
  HWND v3; // rcx
  HDC DC; // rax
  HDC v6; // rdi
  int v7; // r14d
  void *v8; // rax
  __int64 v9; // r8
  int v10; // esi
  HWND v11; // rcx
  tagSIZE psizl; // [rsp+40h] [rbp+8h] BYREF

  v3 = *this;
  psizl = 0;
  DC = GetDC(v3);
  v6 = DC;
  if ( DC )
  {
    v7 = SaveDC(DC);
    if ( v7 )
    {
      v8 = (void *)SendMessageW(*this, 0x31u, 0, 0);
      if ( v8 )
        SelectObject(v6, v8);
      v9 = -1;
      do
        ++v9;
      while ( a2[v9] );
      if ( GetTextExtentPoint32W(v6, a2, v9, &psizl) )
      {
        v10 = GetSystemMetrics(2) + psizl.cx;
        RestoreDC(v6, v7);
        ReleaseDC(*this, v6);
        if ( *((_DWORD *)this + 2) < v10 )
        {
          v11 = *this;
          *((_DWORD *)this + 2) = v10;
          SendMessageW(v11, 0x160u, v10, 0);
        }
      }
    }
  }
  return SendMessageW(*this, 0x143u, 0, (LPARAM)a2);
}

```

## disassembly

```asm
0x180008bbc  mov     [rsp+arg_8], rbx
0x180008bc1  mov     [rsp+arg_10], rbp
0x180008bc6  push    rsi
0x180008bc7  push    rdi
0x180008bc8  push    r14
0x180008bca  sub     rsp, 20h
0x180008bce  mov     rbx, rcx
0x180008bd1  xor     esi, esi
0x180008bd3  mov     rcx, [rcx]; hWnd
0x180008bd6  mov     rbp, rdx
0x180008bd9  mov     qword ptr [rsp+38h+psizl.cx], rsi
0x180008bde  call    cs:__imp_GetDC
0x180008be4  mov     rdi, rax
0x180008be7  test    rax, rax
0x180008bea  jz      loc_180008C90
0x180008bf0  mov     rcx, rax; hdc
0x180008bf3  call    cs:__imp_SaveDC
0x180008bf9  mov     r14d, eax
0x180008bfc  test    eax, eax
0x180008bfe  jz      loc_180008C90
0x180008c04  mov     rcx, [rbx]; hWnd
0x180008c07  lea     edx, [rsi+31h]; Msg
0x180008c0a  xor     r9d, r9d; lParam
0x180008c0d  xor     r8d, r8d; wParam
0x180008c10  call    cs:__imp_SendMessageW
0x180008c16  test    rax, rax
0x180008c19  jz      short loc_180008C27
0x180008c1b  mov     rdx, rax; h
0x180008c1e  mov     rcx, rdi; hdc
0x180008c21  call    cs:__imp_SelectObject
0x180008c27  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008c2b  inc     r8; c
0x180008c2e  cmp     [rbp+r8*2+0], si
0x180008c34  jnz     short loc_180008C2B
0x180008c36  lea     r9, [rsp+38h+psizl]; psizl
0x180008c3b  mov     rdx, rbp; lpString
0x180008c3e  mov     rcx, rdi; hdc
0x180008c41  call    cs:__imp_GetTextExtentPoint32W
0x180008c47  test    eax, eax
0x180008c49  jz      short loc_180008C90
0x180008c4b  mov     ecx, 2; nIndex
0x180008c50  call    cs:__imp_GetSystemMetrics
0x180008c56  mov     esi, [rsp+38h+psizl.cx]
0x180008c5a  mov     edx, r14d; nSavedDC
0x180008c5d  mov     rcx, rdi; hdc
0x180008c60  add     esi, eax
0x180008c62  call    cs:__imp_RestoreDC
0x180008c68  mov     rcx, [rbx]; hWnd
0x180008c6b  mov     rdx, rdi; hDC
0x180008c6e  call    cs:__imp_ReleaseDC
0x180008c74  cmp     [rbx+8], esi
0x180008c77  jge     short loc_180008C90
0x180008c79  mov     rcx, [rbx]; hWnd
0x180008c7c  xor     r9d, r9d; lParam
0x180008c7f  movsxd  r8, esi; wParam
0x180008c82  mov     edx, 160h; Msg
0x180008c87  mov     [rbx+8], esi
0x180008c8a  call    cs:__imp_SendMessageW
0x180008c90  mov     rcx, [rbx]
0x180008c93  mov     r9, rbp
0x180008c96  xor     r8d, r8d
0x180008c99  mov     edx, 143h
0x180008c9e  mov     rbx, [rsp+38h+arg_8]
0x180008ca3  mov     rbp, [rsp+38h+arg_10]
0x180008ca8  add     rsp, 20h
0x180008cac  pop     r14
0x180008cae  pop     rdi
0x180008caf  pop     rsi
0x180008cb0  jmp     cs:__imp_SendMessageW
```
