# ProxyWindow::CreateProxyWindowImpl(ProxyWindow::CreationParams const &)

- ea: `0x180061ab4`
- end: `0x180061cfd`
- name: `?CreateProxyWindowImpl@ProxyWindow@@AEAAJAEBUCreationParams@1@@Z`
- size: `585`
- prototype: `__int64 __fastcall(ProxyWindow *__hidden this, const struct ProxyWindow::CreationParams *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18005ec60`

## callees

- `0x18005ec9c`
- `0x180061ab4`
- `0x1800a74d4`
- `0x1800a7528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061bd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061c10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061c10`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180061c99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180061c99`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180061b2d`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180061b2d`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180061c43`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180061c69`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180061c7d`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180061c43`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180061c69`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180061c7d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180061c08`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180061c08`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x180061bc5`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x180061bc5`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180061ce1`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180061ce1`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x180061b59`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x180061b59`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrA` at `0x180061c2f`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrA` at `0x180061c2f`
- `ext-ms-win-ntuser-misc-l1-2-0!AttachThreadInput` at `0x180061c1d`
- `ext-ms-win-ntuser-misc-l1-2-0!AttachThreadInput` at `0x180061c1d`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconA` at `0x180061b1b`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconA` at `0x180061b1b`

## pseudocode

```c
signed int __fastcall ProxyWindow::CreateProxyWindowImpl(
        ProxyWindow *this,
        const struct ProxyWindow::CreationParams *a2)
{
  int *v2; // r14
  int v5; // ebp
  int v6; // r15d
  HCURSOR CursorW; // rax
  HWND hWndParent; // rdx
  char v9; // bl
  HWND Window; // rax
  signed int result; // eax
  DWORD WindowThreadProcessId; // ebx
  DWORD CurrentThreadId; // eax
  ProxyWindow *v14; // rcx
  WNDCLASSA WndClass; // [rsp+60h] [rbp-98h] BYREF

  v2 = (int *)*((_QWORD *)a2 + 1);
  v5 = 0;
  if ( *((_QWORD *)this + 7) )
    goto LABEL_16;
  v6 = *((_DWORD *)a2 + 4);
  if ( !word_18010C2D8 )
  {
    *(_QWORD *)&WndClass.style = 0;
    WndClass.lpfnWndProc = (WNDPROC)ProxyWndProc;
    *(_QWORD *)&WndClass.cbClsExtra = 0;
    WndClass.hInstance = 0;
    WndClass.hIcon = LoadIconA(0, (LPCSTR)0x7F00);
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
    *(__m128i *)&WndClass.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
    WndClass.hCursor = CursorW;
    WndClass.lpszClassName = "D3DProxyWindow";
    word_18010C2D8 = RegisterClassA(&WndClass);
  }
  if ( v6 == 1 )
  {
    v9 = 0;
    hWndParent = 0;
  }
  else
  {
    hWndParent = *(HWND *)a2;
    v9 = 1;
  }
  Window = CreateWindowExA(
             0x8280020u,
             "D3DProxyWindow",
             "D3DProxyWindow",
             0x80000000,
             *v2,
             v2[1],
             v2[2] - *v2,
             v2[3] - v2[1],
             hWndParent,
             0,
             0,
             0);
  *((_QWORD *)this + 7) = Window;
  if ( Window )
  {
    if ( *(_QWORD *)a2 )
    {
      *((_QWORD *)this + 8) = *(_QWORD *)a2;
      if ( v9 )
      {
        WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)a2, 0);
        CurrentThreadId = GetCurrentThreadId();
        AttachThreadInput(CurrentThreadId, WindowThreadProcessId, 0);
        SetWindowLongPtrA(*((HWND *)this + 7), -21, (LONG_PTR)this);
      }
      SetPropW(*(HWND *)a2, L"__D3DProxyProp__", *((HANDLE *)this + 7));
      DwmUpdateProxyWindow(*(HWND *)a2, *((HWND *)this + 7));
      if ( v6 == 1 )
      {
        SetPropW(*((HWND *)this + 7), L"__D3DVisualProxyProp__", *(HANDLE *)a2);
        SetPropW(*((HWND *)this + 7), L"TreatAsDesktopFullscreen", HANDLE_FLAG_INHERIT);
        v5 = ProxyWindow::PromoteWindowHelper(v14, *((HWND *)this + 7));
        if ( v5 < 0 )
        {
          OutputDebugStringA("Proxy window promotion failed\n");
          ProxyWindow::DestroyProxyWindowImpl(this);
          return v5;
        }
      }
    }
LABEL_16:
    SetWindowPos(*((HWND *)this + 7), 0, *v2, v2[1], v2[2] - *v2, v2[3] - v2[1], *(_QWORD *)a2 != 0 ? 592 : 528);
    return v5;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180061ab4  push    rbx
0x180061ab6  push    rbp
0x180061ab7  push    rsi
0x180061ab8  push    rdi
0x180061ab9  push    r12
0x180061abb  push    r13
0x180061abd  push    r14
0x180061abf  push    r15
0x180061ac1  sub     rsp, 0B8h
0x180061ac8  mov     r14, [rdx+8]
0x180061acc  xor     r12d, r12d
0x180061acf  mov     rsi, rdx
0x180061ad2  mov     rdi, rcx
0x180061ad5  mov     ebp, r12d
0x180061ad8  cmp     [rcx+38h], r12
0x180061adc  jnz     loc_180061CA9
0x180061ae2  cmp     cs:word_18010C2D8, r12w
0x180061aea  lea     r13, ClassName; "D3DProxyWindow"
0x180061af1  mov     r15d, [rdx+10h]
0x180061af5  jnz     short loc_180061B66
0x180061af7  lea     rax, ProxyWndProc
0x180061afe  mov     qword ptr [rsp+0F8h+WndClass.style], r12
0x180061b03  mov     ebx, 7F00h
0x180061b08  mov     [rsp+0F8h+WndClass.lpfnWndProc], rax
0x180061b0d  mov     edx, ebx; lpIconName
0x180061b0f  mov     qword ptr [rsp+0F8h+WndClass.cbClsExtra], r12
0x180061b14  xor     ecx, ecx; hInstance
0x180061b16  mov     [rsp+0F8h+WndClass.hInstance], r12
0x180061b1b  call    cs:__imp_LoadIconA
0x180061b21  mov     edx, ebx; lpCursorName
0x180061b23  xor     ecx, ecx; hInstance
0x180061b25  mov     [rsp+0F8h+WndClass.hIcon], rax
0x180061b2d  call    cs:__imp_LoadCursorW
0x180061b33  movdqa  xmm0, cs:__xmm@00000000000000000000000000000004
0x180061b3b  lea     rcx, [rsp+0F8h+WndClass]; lpWndClass
0x180061b40  movdqa  xmmword ptr [rsp+0F8h+WndClass.hbrBackground], xmm0
0x180061b49  mov     [rsp+0F8h+WndClass.hCursor], rax
0x180061b51  mov     [rsp+0F8h+WndClass.lpszClassName], r13
0x180061b59  call    cs:__imp_RegisterClassA
0x180061b5f  mov     cs:word_18010C2D8, ax
0x180061b66  cmp     r15d, 1
0x180061b6a  jz      short loc_180061B73
0x180061b6c  mov     rdx, [rsi]
0x180061b6f  mov     bl, 1
0x180061b71  jmp     short loc_180061B79
0x180061b73  mov     bl, r12b
0x180061b76  mov     rdx, r12
0x180061b79  mov     r8d, [r14+4]
0x180061b7d  mov     r9d, [r14]
0x180061b80  mov     ecx, [r14+0Ch]
0x180061b84  mov     eax, [r14+8]
0x180061b88  sub     ecx, r8d
0x180061b8b  mov     [rsp+0F8h+lpParam], r12; lpParam
0x180061b90  sub     eax, r9d
0x180061b93  mov     [rsp+0F8h+hInstance], r12; hInstance
0x180061b98  mov     [rsp+0F8h+hMenu], r12; hMenu
0x180061b9d  mov     [rsp+0F8h+hWndParent], rdx; hWndParent
0x180061ba2  mov     rdx, r13; lpClassName
0x180061ba5  mov     [rsp+0F8h+nHeight], ecx; nHeight
0x180061ba9  mov     ecx, 8280020h; dwExStyle
0x180061bae  mov     [rsp+0F8h+nWidth], eax; nWidth
0x180061bb2  mov     [rsp+0F8h+Y], r8d; Y
0x180061bb7  mov     r8, r13; lpWindowName
0x180061bba  mov     [rsp+0F8h+X], r9d; X
0x180061bbf  mov     r9d, 80000000h; dwStyle
0x180061bc5  call    cs:__imp_CreateWindowExA
0x180061bcb  mov     [rdi+38h], rax
0x180061bcf  test    rax, rax
0x180061bd2  jnz     short loc_180061BEF
0x180061bd4  call    cs:__imp_GetLastError
0x180061bda  test    eax, eax
0x180061bdc  jle     loc_180061CE9
0x180061be2  movzx   eax, ax
0x180061be5  or      eax, 80070000h
0x180061bea  jmp     loc_180061CE9
0x180061bef  mov     rax, [rsi]
0x180061bf2  test    rax, rax
0x180061bf5  jz      loc_180061CA9
0x180061bfb  mov     [rdi+40h], rax
0x180061bff  test    bl, bl
0x180061c01  jz      short loc_180061C35
0x180061c03  mov     rcx, [rsi]; hWnd
0x180061c06  xor     edx, edx; lpdwProcessId
0x180061c08  call    cs:__imp_GetWindowThreadProcessId
0x180061c0e  mov     ebx, eax
0x180061c10  call    cs:__imp_GetCurrentThreadId
0x180061c16  xor     r8d, r8d; fAttach
0x180061c19  mov     edx, ebx; idAttachTo
0x180061c1b  mov     ecx, eax; idAttach
0x180061c1d  call    cs:__imp_AttachThreadInput
0x180061c23  mov     rcx, [rdi+38h]; hWnd
0x180061c27  mov     r8, rdi; dwNewLong
0x180061c2a  mov     edx, 0FFFFFFEBh; nIndex
0x180061c2f  call    cs:__imp_SetWindowLongPtrA
0x180061c35  mov     r8, [rdi+38h]; hData
0x180061c39  lea     rdx, aD3dproxyprop; "__D3DProxyProp__"
0x180061c40  mov     rcx, [rsi]; hWnd
0x180061c43  call    cs:__imp_SetPropW
0x180061c49  mov     rdx, [rdi+38h]; HWND
0x180061c4d  mov     rcx, [rsi]; HWND
0x180061c50  call    ?DwmUpdateProxyWindow@@YAXPEAUHWND__@@0@Z; DwmUpdateProxyWindow(HWND__ *,HWND__ *)
0x180061c55  cmp     r15d, 1
0x180061c59  jnz     short loc_180061CA9
0x180061c5b  mov     r8, [rsi]; hData
0x180061c5e  lea     rdx, aD3dvisualproxy; "__D3DVisualProxyProp__"
0x180061c65  mov     rcx, [rdi+38h]; hWnd
0x180061c69  call    cs:__imp_SetPropW
0x180061c6f  mov     rcx, [rdi+38h]; hWnd
0x180061c73  lea     rdx, aTreatasdesktop; "TreatAsDesktopFullscreen"
0x180061c7a  mov     r8d, r15d; hData
0x180061c7d  call    cs:__imp_SetPropW
0x180061c83  mov     rdx, [rdi+38h]; HWND
0x180061c87  call    ?PromoteWindowHelper@ProxyWindow@@AEAAJPEAUHWND__@@@Z; ProxyWindow::PromoteWindowHelper(HWND__ *)
0x180061c8c  mov     ebp, eax
0x180061c8e  test    eax, eax
0x180061c90  jns     short loc_180061CA9
0x180061c92  lea     rcx, aProxyWindowPro; "Proxy window promotion failed\n"
0x180061c99  call    cs:__imp_OutputDebugStringA
0x180061c9f  mov     rcx, rdi; this
0x180061ca2  call    ?DestroyProxyWindowImpl@ProxyWindow@@AEAAXXZ; ProxyWindow::DestroyProxyWindowImpl(void)
0x180061ca7  jmp     short loc_180061CE7
0x180061ca9  mov     ecx, [r14+0Ch]
0x180061cad  mov     rax, [rsi]
0x180061cb0  mov     r9d, [r14+4]; Y
0x180061cb4  neg     rax
0x180061cb7  mov     eax, [r14+8]
0x180061cbb  mov     r8d, [r14]; X
0x180061cbe  sbb     edx, edx
0x180061cc0  sub     eax, [r14]
0x180061cc3  and     edx, 40h
0x180061cc6  add     edx, 210h
0x180061ccc  sub     ecx, r9d
0x180061ccf  mov     [rsp+0F8h+nWidth], edx; uFlags
0x180061cd3  xor     edx, edx; hWndInsertAfter
0x180061cd5  mov     [rsp+0F8h+Y], ecx; cy
0x180061cd9  mov     rcx, [rdi+38h]; hWnd
0x180061cdd  mov     [rsp+0F8h+X], eax; cx
0x180061ce1  call    cs:__imp_SetWindowPos
0x180061ce7  mov     eax, ebp
0x180061ce9  add     rsp, 0B8h
0x180061cf0  pop     r15
0x180061cf2  pop     r14
0x180061cf4  pop     r13
0x180061cf6  pop     r12
0x180061cf8  pop     rdi
0x180061cf9  pop     rsi
0x180061cfa  pop     rbp
0x180061cfb  pop     rbx
0x180061cfc  retn
```
