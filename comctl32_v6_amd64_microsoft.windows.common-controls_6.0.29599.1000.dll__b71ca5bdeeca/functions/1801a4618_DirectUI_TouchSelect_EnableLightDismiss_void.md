# DirectUI::TouchSelect::_EnableLightDismiss(void)

- ea: `0x1801a4618`
- end: `0x1801a47ac`
- name: `?_EnableLightDismiss@TouchSelect@DirectUI@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801a507c`

## callees

- `0x180099cb0`
- `0x18009a2b0`
- `0x1801a4618`
- `0x1801d1010`

## import_xrefs

- `USER32!ShowWindow` at `0x1801a4769`
- `USER32!ShowWindow` at `0x1801a4769`
- `USER32!SetWindowPos` at `0x1801a4792`
- `USER32!SetWindowPos` at `0x1801a4792`
- `USER32!MoveWindow` at `0x1801a472b`
- `USER32!MoveWindow` at `0x1801a472b`
- `USER32!SetWindowLongPtrW` at `0x1801a46c3`
- `USER32!SetWindowLongPtrW` at `0x1801a46d8`
- `USER32!SetWindowLongPtrW` at `0x1801a46c3`
- `USER32!SetWindowLongPtrW` at `0x1801a46d8`
- `USER32!GetSystemMetrics` at `0x1801a46e3`
- `USER32!GetSystemMetrics` at `0x1801a46f0`
- `USER32!GetSystemMetrics` at `0x1801a46fd`
- `USER32!GetSystemMetrics` at `0x1801a470a`
- `USER32!GetSystemMetrics` at `0x1801a46e3`
- `USER32!GetSystemMetrics` at `0x1801a46f0`
- `USER32!GetSystemMetrics` at `0x1801a46fd`
- `USER32!GetSystemMetrics` at `0x1801a470a`
- `USER32!CreateWindowExW` at `0x1801a469e`
- `USER32!CreateWindowExW` at `0x1801a469e`
- `USER32!SetWindowsHookExW` at `0x1801a4746`
- `USER32!SetWindowsHookExW` at `0x1801a4746`

## pseudocode

```c
__int64 __fastcall DirectUI::TouchSelect::_EnableLightDismiss(LONG_PTR dwNewLong)
{
  struct DirectUI::Element *Root; // rax
  __int64 v3; // rax
  HWND hWndParent; // rax
  HWND Window; // rax
  int SystemMetrics; // esi
  int v7; // edi
  int v8; // ebx
  int v9; // eax
  HHOOK v10; // rax
  HWND v11; // rcx
  unsigned int v12; // ebx

  Root = DirectUI::Element::GetRoot((DirectUI::Element *)dwNewLong);
  v3 = element_cast<DirectUI::HWNDElement>(Root);
  hWndParent = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 360LL))(v3);
  Window = CreateWindowExW(
             0x8080008u,
             L"TouchSelectPopupHost",
             &WindowName,
             0x80000000,
             0,
             0,
             0x7FFF,
             0x7FFF,
             hWndParent,
             0,
             &_ImageBase,
             0);
  *(_QWORD *)(dwNewLong + 488) = Window;
  if ( !Window )
    return (unsigned int)-2147467259;
  SetWindowLongPtrW(Window, -4, (LONG_PTR)DirectUI::TouchSelect::_FullScreenWndProc);
  SetWindowLongPtrW(*(HWND *)(dwNewLong + 488), -21, dwNewLong);
  SystemMetrics = GetSystemMetrics(76);
  v7 = GetSystemMetrics(77);
  v8 = GetSystemMetrics(78);
  v9 = GetSystemMetrics(79);
  if ( !MoveWindow(*(HWND *)(dwNewLong + 488), SystemMetrics, v7, v8, v9, 0) )
    return (unsigned int)-2147467259;
  v10 = SetWindowsHookExW(13, DirectUI::TouchSelect::_StaticKeyboardHookProc, &_ImageBase, 0);
  *(_QWORD *)(dwNewLong + 480) = v10;
  if ( v10 )
  {
    v11 = *(HWND *)(dwNewLong + 488);
    v12 = 0;
    if ( v11 )
    {
      ShowWindow(v11, 8);
      SetWindowPos(*(HWND *)(*(_QWORD *)(dwNewLong + 440) + 8LL), 0, 0, 0, 0, 0, 0x1Bu);
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v12;
}

```

## disassembly

```asm
0x1801a4618  push    rbx
0x1801a461a  push    rbp
0x1801a461b  push    rsi
0x1801a461c  push    rdi
0x1801a461d  push    r15
0x1801a461f  sub     rsp, 60h
0x1801a4623  mov     rbp, rcx
0x1801a4626  call    ?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x1801a462b  mov     rcx, rax
0x1801a462e  call    ??$element_cast@VHWNDElement@DirectUI@@@@YAPEAVHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::HWNDElement>(DirectUI::Element *)
0x1801a4633  mov     rcx, rax
0x1801a4636  mov     rdx, [rax]
0x1801a4639  mov     rax, [rdx+168h]
0x1801a4640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4645  mov     [rsp+88h+lpParam], 0; lpParam
0x1801a464e  lea     r15, __ImageBase
0x1801a4655  mov     [rsp+88h+hInstance], r15; hInstance
0x1801a465a  lea     r8, WindowName; lpWindowName
0x1801a4661  mov     [rsp+88h+hMenu], 0; hMenu
0x1801a466a  lea     rdx, aTouchselectpop; "TouchSelectPopupHost"
0x1801a4671  mov     [rsp+88h+hWndParent], rax; hWndParent
0x1801a4676  mov     r9d, 80000000h; dwStyle
0x1801a467c  mov     eax, 7FFFh
0x1801a4681  mov     ecx, 8080008h; dwExStyle
0x1801a4686  mov     [rsp+88h+nHeight], eax; nHeight
0x1801a468a  mov     [rsp+88h+nWidth], eax; nWidth
0x1801a468e  mov     [rsp+88h+Y], 0; Y
0x1801a4696  mov     [rsp+88h+X], 0; X
0x1801a469e  call    cs:__imp_CreateWindowExW
0x1801a46a4  mov     [rbp+1E8h], rax
0x1801a46ab  test    rax, rax
0x1801a46ae  jz      loc_1801A479A
0x1801a46b4  lea     r8, ?_FullScreenWndProc@TouchSelect@DirectUI@@CA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x1801a46bb  mov     edx, 0FFFFFFFCh; nIndex
0x1801a46c0  mov     rcx, rax; hWnd
0x1801a46c3  call    cs:__imp_SetWindowLongPtrW
0x1801a46c9  mov     rcx, [rbp+1E8h]; hWnd
0x1801a46d0  mov     r8, rbp; dwNewLong
0x1801a46d3  mov     edx, 0FFFFFFEBh; nIndex
0x1801a46d8  call    cs:__imp_SetWindowLongPtrW
0x1801a46de  mov     ecx, 4Ch ; 'L'; nIndex
0x1801a46e3  call    cs:__imp_GetSystemMetrics
0x1801a46e9  mov     ecx, 4Dh ; 'M'; nIndex
0x1801a46ee  mov     esi, eax
0x1801a46f0  call    cs:__imp_GetSystemMetrics
0x1801a46f6  mov     ecx, 4Eh ; 'N'; nIndex
0x1801a46fb  mov     edi, eax
0x1801a46fd  call    cs:__imp_GetSystemMetrics
0x1801a4703  mov     ecx, 4Fh ; 'O'; nIndex
0x1801a4708  mov     ebx, eax
0x1801a470a  call    cs:__imp_GetSystemMetrics
0x1801a4710  mov     rcx, [rbp+1E8h]; hWnd
0x1801a4717  mov     r9d, ebx; nWidth
0x1801a471a  mov     r8d, edi; Y
0x1801a471d  mov     [rsp+88h+Y], 0; bRepaint
0x1801a4725  mov     edx, esi; X
0x1801a4727  mov     [rsp+88h+X], eax; nHeight
0x1801a472b  call    cs:__imp_MoveWindow
0x1801a4731  test    eax, eax
0x1801a4733  jz      short loc_1801A479A
0x1801a4735  xor     r9d, r9d; dwThreadId
0x1801a4738  lea     rdx, ?_StaticKeyboardHookProc@TouchSelect@DirectUI@@CA_JH_K_J@Z; lpfn
0x1801a473f  mov     r8, r15; hmod
0x1801a4742  lea     ecx, [r9+0Dh]; idHook
0x1801a4746  call    cs:__imp_SetWindowsHookExW
0x1801a474c  mov     [rbp+1E0h], rax
0x1801a4753  test    rax, rax
0x1801a4756  jz      short loc_1801A479A
0x1801a4758  mov     rcx, [rbp+1E8h]; hWnd
0x1801a475f  xor     ebx, ebx
0x1801a4761  test    rcx, rcx
0x1801a4764  jz      short loc_1801A479F
0x1801a4766  lea     edx, [rbx+8]; nCmdShow
0x1801a4769  call    cs:__imp_ShowWindow
0x1801a476f  mov     rcx, [rbp+1B8h]
0x1801a4776  xor     r9d, r9d; Y
0x1801a4779  mov     [rsp+88h+nWidth], 1Bh; uFlags
0x1801a4781  xor     r8d, r8d; X
0x1801a4784  mov     [rsp+88h+Y], ebx; cy
0x1801a4788  xor     edx, edx; hWndInsertAfter
0x1801a478a  mov     [rsp+88h+X], ebx; cx
0x1801a478e  mov     rcx, [rcx+8]; hWnd
0x1801a4792  call    cs:__imp_SetWindowPos
0x1801a4798  jmp     short loc_1801A479F
0x1801a479a  mov     ebx, 80004005h
0x1801a479f  mov     eax, ebx
0x1801a47a1  add     rsp, 60h
0x1801a47a5  pop     r15
0x1801a47a7  pop     rdi
0x1801a47a8  pop     rsi
0x1801a47a9  pop     rbp
0x1801a47aa  pop     rbx
0x1801a47ab  retn
```
