# CMFCDynamicLayout::GetHostWndRect(CRect &)

- ea: `0x18001895c`
- end: `0x180018a22`
- name: `?GetHostWndRect@CMFCDynamicLayout@@QEBAXAEAVCRect@@@Z`
- size: `198`
- prototype: `void(CMFCDynamicLayout *__hidden this, struct CRect *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800185e4`
- `0x180018c44`

## callees

- `0x18001895c`

## import_xrefs

- `MFC42u!__imp_?AfxDynamicDownCast@@YAPEAVCObject@@PEAUCRuntimeClass@@PEAV1@@Z` at `0x1800189a2`
- `MFC42u!__imp_?AfxDynamicDownCast@@YAPEAVCObject@@PEAUCRuntimeClass@@PEAV1@@Z` at `0x1800189a2`
- `MFC42u!__imp_?classCFormView@CFormView@@2UCRuntimeClass@@B` at `0x18001899b`
- `MFC42u!__imp_?GetScrollPos@CWnd@@QEBAHH@Z` at `0x1800189b6`
- `MFC42u!__imp_?GetScrollPos@CWnd@@QEBAHH@Z` at `0x1800189c4`
- `MFC42u!__imp_?GetScrollPos@CWnd@@QEBAHH@Z` at `0x1800189b6`
- `MFC42u!__imp_?GetScrollPos@CWnd@@QEBAHH@Z` at `0x1800189c4`
- `MFC42u!__imp_?InflateRect@CRect@@QEAAXHHHH@Z` at `0x1800189db`
- `MFC42u!__imp_?InflateRect@CRect@@QEAAXHHHH@Z` at `0x1800189db`
- `USER32!OffsetRect` at `0x1800189ed`
- `USER32!OffsetRect` at `0x1800189ed`
- `USER32!GetClientRect` at `0x180018991`
- `USER32!GetClientRect` at `0x180018991`
- `USER32!SetRectEmpty` at `0x18001896e`
- `USER32!SetRectEmpty` at `0x18001896e`

## pseudocode

```c
void __fastcall CMFCDynamicLayout::GetHostWndRect(CMFCDynamicLayout *this, struct tagRECT *a2)
{
  __int64 v4; // rax
  HWND v5; // rcx
  int ScrollPos; // edi
  int v7; // ebx
  int v8; // ecx
  int v9; // eax
  int v10; // ecx

  SetRectEmpty(a2);
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = *(HWND *)(v4 + 64);
    if ( v5 )
    {
      GetClientRect(v5, a2);
      if ( AfxDynamicDownCast(CFormView::classCFormView, *((struct CObject **)this + 1)) )
      {
        ScrollPos = CWnd::GetScrollPos(*((CWnd **)this + 1), 1);
        v7 = CWnd::GetScrollPos(*((CWnd **)this + 1), 0);
        CRect::InflateRect((CRect *)a2, 0, 0, v7, ScrollPos);
        OffsetRect(a2, -v7, -ScrollPos);
      }
      v8 = *((_DWORD *)this + 4);
      if ( v8 <= a2->right - a2->left )
        v8 = a2->right - a2->left;
      v9 = a2->bottom - a2->top;
      a2->right = a2->left + v8;
      v10 = *((_DWORD *)this + 5);
      if ( v10 <= v9 )
        v10 = v9;
      a2->bottom = a2->top + v10;
    }
  }
}

```

## disassembly

```asm
0x18001895c  push    rbx
0x18001895e  push    rbp
0x18001895f  push    rsi
0x180018960  push    rdi
0x180018961  sub     rsp, 38h
0x180018965  mov     rbp, rcx
0x180018968  mov     rsi, rdx
0x18001896b  mov     rcx, rdx; lprc
0x18001896e  call    cs:__imp_SetRectEmpty
0x180018974  mov     rax, [rbp+8]
0x180018978  test    rax, rax
0x18001897b  jz      loc_180018A19
0x180018981  mov     rcx, [rax+40h]; hWnd
0x180018985  test    rcx, rcx
0x180018988  jz      loc_180018A19
0x18001898e  mov     rdx, rsi; lpRect
0x180018991  call    cs:__imp_GetClientRect
0x180018997  mov     rdx, [rbp+8]
0x18001899b  mov     rcx, cs:__imp_?classCFormView@CFormView@@2UCRuntimeClass@@B; CRuntimeClass const CFormView::classCFormView
0x1800189a2  call    cs:__imp_?AfxDynamicDownCast@@YAPEAVCObject@@PEAUCRuntimeClass@@PEAV1@@Z; AfxDynamicDownCast(CRuntimeClass *,CObject *)
0x1800189a8  test    rax, rax
0x1800189ab  jz      short loc_1800189F3
0x1800189ad  mov     rcx, [rbp+8]
0x1800189b1  mov     edx, 1
0x1800189b6  call    cs:__imp_?GetScrollPos@CWnd@@QEBAHH@Z; CWnd::GetScrollPos(int)
0x1800189bc  mov     rcx, [rbp+8]
0x1800189c0  xor     edx, edx
0x1800189c2  mov     edi, eax
0x1800189c4  call    cs:__imp_?GetScrollPos@CWnd@@QEBAHH@Z; CWnd::GetScrollPos(int)
0x1800189ca  xor     r8d, r8d
0x1800189cd  mov     [rsp+58h+var_38], edi
0x1800189d1  mov     r9d, eax
0x1800189d4  xor     edx, edx
0x1800189d6  mov     rcx, rsi
0x1800189d9  mov     ebx, eax
0x1800189db  call    cs:__imp_?InflateRect@CRect@@QEAAXHHHH@Z; CRect::InflateRect(int,int,int,int)
0x1800189e1  neg     edi
0x1800189e3  neg     ebx
0x1800189e5  mov     r8d, edi; dy
0x1800189e8  mov     edx, ebx; dx
0x1800189ea  mov     rcx, rsi; lprc
0x1800189ed  call    cs:__imp_OffsetRect
0x1800189f3  mov     ecx, [rbp+10h]
0x1800189f6  mov     eax, [rsi+8]
0x1800189f9  sub     eax, [rsi]
0x1800189fb  cmp     ecx, eax
0x1800189fd  cmovle  ecx, eax
0x180018a00  mov     eax, [rsi+0Ch]
0x180018a03  add     ecx, [rsi]
0x180018a05  sub     eax, [rsi+4]
0x180018a08  mov     [rsi+8], ecx
0x180018a0b  mov     ecx, [rbp+14h]
0x180018a0e  cmp     ecx, eax
0x180018a10  cmovle  ecx, eax
0x180018a13  add     ecx, [rsi+4]
0x180018a16  mov     [rsi+0Ch], ecx
0x180018a19  add     rsp, 38h
0x180018a1d  pop     rdi
0x180018a1e  pop     rsi
0x180018a1f  pop     rbp
0x180018a20  pop     rbx
0x180018a21  retn
```
