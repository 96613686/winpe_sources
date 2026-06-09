# CBasePropertyPage::GetPageInfo(tagPROPPAGEINFO *)

- ea: `0x18001ce60`
- end: `0x18001cf8f`
- name: `?GetPageInfo@CBasePropertyPage@@UEAAJPEAUtagPROPPAGEINFO@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(CBasePropertyPage *__hidden this, struct tagPROPPAGEINFO *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x1800077a8`
- `0x18001ce60`

## import_xrefs

- `USER32!GetWindowRect` at `0x18001cf47`
- `USER32!GetWindowRect` at `0x18001cf47`
- `USER32!LoadStringW` at `0x18001cea9`
- `USER32!LoadStringW` at `0x18001cea9`
- `USER32!DestroyWindow` at `0x18001cf66`
- `USER32!DestroyWindow` at `0x18001cf66`
- `USER32!GetDesktopWindow` at `0x18001cf0e`
- `USER32!GetDesktopWindow` at `0x18001cf0e`
- `USER32!CreateDialogParamW` at `0x18001cf31`
- `USER32!CreateDialogParamW` at `0x18001cf31`

## pseudocode

```c
__int64 __fastcall CBasePropertyPage::GetPageInfo(CBasePropertyPage *this, struct tagPROPPAGEINFO *a2)
{
  __int64 result; // rax
  int v5; // ebx
  HWND DesktopWindow; // rax
  HWND DialogParamW; // rax
  HWND v8; // rbx
  tagRECT Rect; // [rsp+30h] [rbp-228h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-218h] BYREF

  if ( !a2 )
    return 2147500035LL;
  LoadStringW(g_hInst, *((_DWORD *)this + 15), Buffer, 256);
  *(_QWORD *)&Rect.left = 0;
  result = AMGetWideString(Buffer, &Rect);
  if ( (int)result >= 0 )
  {
    a2->pszTitle = *(LPOLESTR *)&Rect.left;
    a2->cb = 48;
    a2->pszDocString = 0;
    a2->pszHelpFile = 0;
    a2->dwHelpContext = 0;
    a2->size.cx = 340;
    a2->size.cy = 150;
    v5 = *((_DWORD *)this + 16);
    Rect = 0;
    DesktopWindow = GetDesktopWindow();
    DialogParamW = CreateDialogParamW(
                     g_hInst,
                     (LPCWSTR)(unsigned __int16)v5,
                     DesktopWindow,
                     CBasePropertyPage::DialogProc,
                     0);
    v8 = DialogParamW;
    if ( DialogParamW )
    {
      GetWindowRect(DialogParamW, &Rect);
      a2->size.cx = Rect.right - Rect.left;
      a2->size.cy = Rect.bottom - Rect.top;
      DestroyWindow(v8);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001ce60  mov     [rsp+arg_10], rbx
0x18001ce65  push    rdi
0x18001ce66  sub     rsp, 250h
0x18001ce6d  mov     rax, cs:__security_cookie
0x18001ce74  xor     rax, rsp
0x18001ce77  mov     [rsp+258h+var_18], rax
0x18001ce7f  mov     rdi, rdx
0x18001ce82  mov     rbx, rcx
0x18001ce85  test    rdx, rdx
0x18001ce88  jnz     short loc_18001CE94
0x18001ce8a  mov     eax, 80004003h
0x18001ce8f  jmp     loc_18001CF6E
0x18001ce94  mov     edx, [rcx+3Ch]; uID
0x18001ce97  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x18001ce9c  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001cea3  mov     r9d, 100h; cchBufferMax
0x18001cea9  call    cs:__imp_LoadStringW
0x18001ceaf  lea     rdx, [rsp+258h+Rect]
0x18001ceb4  mov     qword ptr [rsp+258h+Rect.left], 0
0x18001cebd  lea     rcx, [rsp+258h+Buffer]; Src
0x18001cec2  call    AMGetWideString
0x18001cec7  test    eax, eax
0x18001cec9  js      loc_18001CF6E
0x18001cecf  mov     rax, qword ptr [rsp+258h+Rect.left]
0x18001ced4  xorps   xmm0, xmm0
0x18001ced7  mov     [rdi+8], rax
0x18001cedb  mov     dword ptr [rdi], 30h ; '0'
0x18001cee1  mov     qword ptr [rdi+18h], 0
0x18001cee9  mov     qword ptr [rdi+20h], 0
0x18001cef1  mov     dword ptr [rdi+28h], 0
0x18001cef8  mov     dword ptr [rdi+10h], 154h
0x18001ceff  mov     dword ptr [rdi+14h], 96h
0x18001cf06  mov     ebx, [rbx+40h]
0x18001cf09  movups  xmmword ptr [rsp+258h+Rect.left], xmm0
0x18001cf0e  call    cs:__imp_GetDesktopWindow
0x18001cf14  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001cf1b  lea     r9, ?DialogProc@CBasePropertyPage@@KA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18001cf22  mov     r8, rax; hWndParent
0x18001cf25  movzx   edx, bx; lpTemplateName
0x18001cf28  mov     [rsp+258h+dwInitParam], 0; dwInitParam
0x18001cf31  call    cs:__imp_CreateDialogParamW
0x18001cf37  mov     rbx, rax
0x18001cf3a  test    rax, rax
0x18001cf3d  jz      short loc_18001CF6C
0x18001cf3f  lea     rdx, [rsp+258h+Rect]; lpRect
0x18001cf44  mov     rcx, rax; hWnd
0x18001cf47  call    cs:__imp_GetWindowRect
0x18001cf4d  mov     ecx, [rsp+258h+Rect.right]
0x18001cf51  sub     ecx, [rsp+258h+Rect.left]
0x18001cf55  mov     [rdi+10h], ecx
0x18001cf58  mov     ecx, [rsp+258h+Rect.bottom]
0x18001cf5c  sub     ecx, [rsp+258h+Rect.top]
0x18001cf60  mov     [rdi+14h], ecx
0x18001cf63  mov     rcx, rbx; hWnd
0x18001cf66  call    cs:__imp_DestroyWindow
0x18001cf6c  xor     eax, eax
0x18001cf6e  mov     rcx, [rsp+258h+var_18]
0x18001cf76  xor     rcx, rsp; StackCookie
0x18001cf79  call    __security_check_cookie
0x18001cf7e  mov     rbx, [rsp+258h+arg_10]
0x18001cf86  add     rsp, 250h
0x18001cf8d  pop     rdi
0x18001cf8e  retn
```
