# CTouchSelectionHandle::UpdateLayeredWindow(tagPOINT *,int)

- ea: `0x180203b78`
- end: `0x180203cb1`
- name: `?UpdateLayeredWindow@CTouchSelectionHandle@@IEAAXPEAUtagPOINT@@H@Z`
- size: `313`
- prototype: `void __fastcall(CTouchSelectionHandle *__hidden this, POINT *pptDst, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180203148`
- `0x180203cb8`
- `0x180203ddc`

## callees

- `0x1801ff800`
- `0x180203b78`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-1!UpdateLayeredWindow` at `0x180203c5c`
- `ext-ms-win-ntuser-window-l1-1-1!UpdateLayeredWindow` at `0x180203c5c`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180203c90`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180203c90`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180203bd4`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180203bd4`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180203bf2`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180203c81`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180203bf2`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180203c81`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180203bc2`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180203bc2`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180203c6f`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180203c6f`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::UpdateLayeredWindow(CTouchSelectionHandle *this, POINT *pptDst, BYTE a3)
{
  __int64 v3; // r10
  int i; // r9d
  __int64 v8; // r8
  HDC DC; // rdi
  HDC hdcSrc; // rsi
  HGDIOBJ v11; // rax
  HWND v12; // rcx
  void *v13; // rbx
  POINT pptSrc; // [rsp+80h] [rbp+8h] BYREF
  BLENDFUNCTION pblend; // [rsp+90h] [rbp+18h] BYREF
  SIZE psize; // [rsp+98h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 16);
  pptSrc = 0;
  for ( i = 0; i != 8; i += 4 )
  {
    v8 = i;
    *(LONG *)((char *)&psize.cx + v8) = *(_DWORD *)(v3 + 8);
  }
  DC = GetDC(*((HWND *)this + 9));
  hdcSrc = CreateCompatibleDC(DC);
  CTouchSelectionHandle::EnsureGripperBitmap(this);
  v11 = SelectObject(hdcSrc, *((HGDIOBJ *)this + 10));
  v12 = (HWND)*((_QWORD *)this + 9);
  v13 = v11;
  *(_WORD *)&pblend.BlendOp = 0;
  pblend.SourceConstantAlpha = a3;
  pblend.AlphaFormat = 1;
  UpdateLayeredWindow(v12, DC, pptDst, &psize, hdcSrc, &pptSrc, 0xFF00u, &pblend, 2u);
  ReleaseDC(*((HWND *)this + 9), DC);
  SelectObject(hdcSrc, v13);
  DeleteDC(hdcSrc);
}

```

## disassembly

```asm
0x180203b78  mov     rax, rsp
0x180203b7b  mov     [rax+10h], rbx
0x180203b7f  push    rbp
0x180203b80  push    rsi
0x180203b81  push    rdi
0x180203b82  push    r14
0x180203b84  push    r15
0x180203b86  sub     rsp, 50h
0x180203b8a  mov     r10, [rcx+80h]
0x180203b91  mov     r14d, r8d
0x180203b94  mov     r15, rdx
0x180203b97  mov     qword ptr [rax+8], 0
0x180203b9f  mov     rbp, rcx
0x180203ba2  xor     r9d, r9d
0x180203ba5  mov     eax, [r10+8]
0x180203ba9  movsxd  r8, r9d
0x180203bac  add     r9d, 4
0x180203bb0  mov     [rsp+r8+78h+psize.cx], eax
0x180203bb8  cmp     r9d, 8
0x180203bbc  jnz     short loc_180203BA5
0x180203bbe  mov     rcx, [rcx+48h]; hWnd
0x180203bc2  call    cs:__imp_GetDC
0x180203bc9  nop     dword ptr [rax+rax+00h]
0x180203bce  mov     rcx, rax; hdc
0x180203bd1  mov     rdi, rax
0x180203bd4  call    cs:__imp_CreateCompatibleDC
0x180203bdb  nop     dword ptr [rax+rax+00h]
0x180203be0  mov     rcx, rbp; this
0x180203be3  mov     rsi, rax
0x180203be6  call    ?EnsureGripperBitmap@CTouchSelectionHandle@@IEAAXXZ; CTouchSelectionHandle::EnsureGripperBitmap(void)
0x180203beb  mov     rdx, [rbp+50h]; h
0x180203bef  mov     rcx, rsi; hdc
0x180203bf2  call    cs:__imp_SelectObject
0x180203bf9  nop     dword ptr [rax+rax+00h]
0x180203bfe  mov     rcx, [rbp+48h]; hWnd
0x180203c02  lea     r9, [rsp+78h+psize]; psize
0x180203c0a  mov     [rsp+78h+dwFlags], 2; dwFlags
0x180203c12  mov     rbx, rax
0x180203c15  lea     rax, [rsp+78h+arg_10]
0x180203c1d  mov     word ptr [rsp+78h+arg_10.BlendOp], 0
0x180203c27  mov     [rsp+78h+pblend], rax; pblend
0x180203c2c  mov     r8, r15; pptDst
0x180203c2f  lea     rax, [rsp+78h+arg_0]
0x180203c37  mov     [rsp+78h+crKey], 0FF00h; crKey
0x180203c3f  mov     [rsp+78h+pptSrc], rax; pptSrc
0x180203c44  mov     rdx, rdi; hdcDst
0x180203c47  mov     [rsp+78h+hdcSrc], rsi; hdcSrc
0x180203c4c  mov     [rsp+78h+arg_10.SourceConstantAlpha], r14b
0x180203c54  mov     [rsp+78h+arg_10.AlphaFormat], 1
0x180203c5c  call    cs:__imp_UpdateLayeredWindow
0x180203c63  nop     dword ptr [rax+rax+00h]
0x180203c68  mov     rcx, [rbp+48h]; hWnd
0x180203c6c  mov     rdx, rdi; hDC
0x180203c6f  call    cs:__imp_ReleaseDC
0x180203c76  nop     dword ptr [rax+rax+00h]
0x180203c7b  mov     rdx, rbx; h
0x180203c7e  mov     rcx, rsi; hdc
0x180203c81  call    cs:__imp_SelectObject
0x180203c88  nop     dword ptr [rax+rax+00h]
0x180203c8d  mov     rcx, rsi; hdc
0x180203c90  call    cs:__imp_DeleteDC
0x180203c97  nop     dword ptr [rax+rax+00h]
0x180203c9c  mov     rbx, [rsp+78h+arg_8]
0x180203ca4  add     rsp, 50h
0x180203ca8  pop     r15
0x180203caa  pop     r14
0x180203cac  pop     rdi
0x180203cad  pop     rsi
0x180203cae  pop     rbp
0x180203caf  retn
```
