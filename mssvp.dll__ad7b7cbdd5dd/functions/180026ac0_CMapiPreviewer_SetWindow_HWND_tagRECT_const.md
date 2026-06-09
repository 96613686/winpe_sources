# CMapiPreviewer::SetWindow(HWND__ *,tagRECT const *)

- ea: `0x180026ac0`
- end: `0x180026bf3`
- name: `?SetWindow@CMapiPreviewer@@UEAAJPEAUHWND__@@PEBUtagRECT@@@Z`
- size: `307`
- prototype: `int(CMapiPreviewer *__hidden this, HWND, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000557c`
- `0x180026ac0`
- `0x180026bfc`
- `0x18003d010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180026b78`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180026b78`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180026bab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180026bab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180026b56`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180026b56`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetParent` at `0x180026af4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetParent` at `0x180026af4`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180026bc8`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180026bc8`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::SetWindow(CMapiPreviewer *this, HWND hWndParent, const struct tagRECT *a3)
{
  HWND v3; // rax
  int Error; // ebx
  HWND Window; // rsi
  __int64 v9; // rcx

  v3 = (HWND)*((_QWORD *)this + 18);
  Error = 0;
  if ( hWndParent == v3 )
  {
LABEL_12:
    if ( !EqualRect(a3, (const RECT *)this + 7) )
      return (unsigned int)CMapiPreviewer::SetupWindowSizes((CMapiPreviewer *)((char *)this - 16), a3, 1);
    return (unsigned int)Error;
  }
  if ( v3 )
  {
    SetParent(*((HWND *)this + 19), hWndParent);
LABEL_11:
    *((_QWORD *)this + 18) = hWndParent;
    goto LABEL_12;
  }
  Window = CreateWindowExW(
             0,
             L"MAPI Preview Full class",
             0,
             0x52000000u,
             *((_DWORD *)this + 28),
             *((_DWORD *)this + 29),
             *((_DWORD *)this + 30) - *((_DWORD *)this + 28),
             *((_DWORD *)this + 31) - *((_DWORD *)this + 29),
             hWndParent,
             (HMENU)0xFFFFFFFFFFFFFFFFLL,
             off_180053498,
             0);
  if ( !Window )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  SetWindowLongPtrW(Window, 0, (LONG_PTR)this - 16);
  v9 = *((_QWORD *)this + 11);
  if ( !v9
    || (Error = (*(__int64 (__fastcall **)(__int64, HWND, char *))(*(_QWORD *)v9 + 24LL))(
                  v9,
                  Window,
                  (char *)this + 128),
        Error >= 0) )
  {
    *((_QWORD *)this + 19) = Window;
    goto LABEL_11;
  }
  if ( Window )
    DestroyWindow(Window);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180026ac0  push    rbx
0x180026ac2  push    rbp
0x180026ac3  push    rsi
0x180026ac4  push    rdi
0x180026ac5  push    r14
0x180026ac7  push    r15
0x180026ac9  sub     rsp, 68h
0x180026acd  mov     rax, [rcx+90h]
0x180026ad4  xor     ebx, ebx
0x180026ad6  mov     r15, r8
0x180026ad9  mov     rbp, rdx
0x180026adc  mov     rdi, rcx
0x180026adf  cmp     rdx, rax
0x180026ae2  jz      loc_180026BC1
0x180026ae8  test    rax, rax
0x180026aeb  jz      short loc_180026AFF
0x180026aed  mov     rcx, [rcx+98h]; hWndChild
0x180026af4  call    cs:__imp_SetParent
0x180026afa  jmp     loc_180026BBA
0x180026aff  mov     r8d, [rdi+74h]
0x180026b03  mov     r9d, [rdi+70h]
0x180026b07  mov     rcx, cs:off_180053498
0x180026b0e  mov     edx, [rdi+7Ch]
0x180026b11  mov     eax, [rdi+78h]
0x180026b14  sub     edx, r8d
0x180026b17  mov     [rsp+98h+lpParam], rbx; lpParam
0x180026b1c  sub     eax, r9d
0x180026b1f  mov     [rsp+98h+hInstance], rcx; hInstance
0x180026b24  xor     ecx, ecx; dwExStyle
0x180026b26  mov     [rsp+98h+hMenu], 0FFFFFFFFFFFFFFFFh; hMenu
0x180026b2f  mov     [rsp+98h+hWndParent], rbp; hWndParent
0x180026b34  mov     [rsp+98h+nHeight], edx; nHeight
0x180026b38  lea     rdx, aMapiPreviewFul; "MAPI Preview Full class"
0x180026b3f  mov     [rsp+98h+nWidth], eax; nWidth
0x180026b43  mov     [rsp+98h+Y], r8d; Y
0x180026b48  xor     r8d, r8d; lpWindowName
0x180026b4b  mov     [rsp+98h+X], r9d; X
0x180026b50  mov     r9d, 52000000h; dwStyle
0x180026b56  call    cs:__imp_CreateWindowExW
0x180026b5c  mov     rsi, rax
0x180026b5f  test    rax, rax
0x180026b62  jnz     short loc_180026B6F
0x180026b64  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180026b69  mov     ebx, eax
0x180026b6b  test    eax, eax
0x180026b6d  js      short loc_180026BE4
0x180026b6f  lea     r8, [rdi-10h]; dwNewLong
0x180026b73  xor     edx, edx; nIndex
0x180026b75  mov     rcx, rsi; hWnd
0x180026b78  call    cs:__imp_SetWindowLongPtrW
0x180026b7e  mov     rcx, [rdi+58h]
0x180026b82  test    rcx, rcx
0x180026b85  jz      short loc_180026BB3
0x180026b87  mov     rax, [rcx]
0x180026b8a  lea     r8, [rdi+80h]
0x180026b91  mov     rdx, rsi
0x180026b94  mov     rax, [rax+18h]
0x180026b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b9d  mov     ebx, eax
0x180026b9f  test    eax, eax
0x180026ba1  jns     short loc_180026BB3
0x180026ba3  test    rsi, rsi
0x180026ba6  jz      short loc_180026BE4
0x180026ba8  mov     rcx, rsi; hWnd
0x180026bab  call    cs:__imp_DestroyWindow
0x180026bb1  jmp     short loc_180026BE4
0x180026bb3  mov     [rdi+98h], rsi
0x180026bba  mov     [rdi+90h], rbp
0x180026bc1  lea     rdx, [rdi+70h]; lprc2
0x180026bc5  mov     rcx, r15; lprc1
0x180026bc8  call    cs:__imp_EqualRect
0x180026bce  test    eax, eax
0x180026bd0  jnz     short loc_180026BE4
0x180026bd2  lea     r8d, [rax+1]; int
0x180026bd6  mov     rdx, r15; struct tagRECT *
0x180026bd9  lea     rcx, [rdi-10h]; this
0x180026bdd  call    ?SetupWindowSizes@CMapiPreviewer@@AEAAJPEBUtagRECT@@H@Z; CMapiPreviewer::SetupWindowSizes(tagRECT const *,int)
0x180026be2  mov     ebx, eax
0x180026be4  mov     eax, ebx
0x180026be6  add     rsp, 68h
0x180026bea  pop     r15
0x180026bec  pop     r14
0x180026bee  pop     rdi
0x180026bef  pop     rsi
0x180026bf0  pop     rbp
0x180026bf1  pop     rbx
0x180026bf2  retn
```
