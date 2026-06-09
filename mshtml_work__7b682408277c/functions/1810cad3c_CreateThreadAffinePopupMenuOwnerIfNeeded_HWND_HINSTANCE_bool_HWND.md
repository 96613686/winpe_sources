# CreateThreadAffinePopupMenuOwnerIfNeeded(HWND__ *,HINSTANCE__ *,bool,HWND__ * *)

- ea: `0x1810cad3c`
- end: `0x1810caf0d`
- name: `?CreateThreadAffinePopupMenuOwnerIfNeeded@@YAHPEAUHWND__@@PEAUHINSTANCE__@@_NPEAPEAU1@@Z`
- size: `465`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, bool, HWND *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180b4eb30`
- `0x180f28618`

## callees

- `0x1810cad3c`
- `0x1810f6516`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1810cadad`
- `KERNEL32!GetCurrentThreadId` at `0x1810cadad`
- `USER32!SetWindowLongPtrW` at `0x1810caedd`
- `USER32!SetWindowLongPtrW` at `0x1810caedd`
- `USER32!GetWindowThreadProcessId` at `0x1810cad9f`
- `USER32!GetWindowThreadProcessId` at `0x1810cad9f`
- `USER32!LoadCursorW` at `0x1810cade0`
- `USER32!LoadCursorW` at `0x1810cade0`
- `USER32!GetAncestor` at `0x1810cad8e`
- `USER32!GetAncestor` at `0x1810cad8e`
- `USER32!GetWindowRect` at `0x1810cae24`
- `USER32!GetWindowRect` at `0x1810cae24`
- `USER32!CreateWindowExW` at `0x1810cae7e`
- `USER32!CreateWindowExW` at `0x1810cae7e`
- `USER32!SetLayeredWindowAttributes` at `0x1810cae9e`
- `USER32!SetLayeredWindowAttributes` at `0x1810cae9e`
- `USER32!RegisterClassExW` at `0x1810cae0a`
- `USER32!RegisterClassExW` at `0x1810cae0a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1810caeaf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1810caec4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1810caeaf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1810caec4`

## pseudocode

```c
__int64 __fastcall CreateThreadAffinePopupMenuOwnerIfNeeded(HWND a1, HINSTANCE a2, __int64 a3, HWND *a4)
{
  unsigned int v5; // edi
  HINSTANCE hInstance; // r15
  HWND Ancestor; // rax
  DWORD WindowThreadProcessId; // ebx
  HWND Window; // rax
  WNDCLASSEXW v12; // [rsp+68h] [rbp-49h] BYREF
  struct tagRECT Rect; // [rsp+B8h] [rbp+7h] BYREF

  v5 = 0;
  hInstance = g_hInstCore;
  *a4 = 0;
  Ancestor = GetAncestor(a1, 2u);
  WindowThreadProcessId = GetWindowThreadProcessId(Ancestor, 0);
  if ( WindowThreadProcessId != GetCurrentThreadId() )
  {
    memset_0(&v12, 0, sizeof(v12));
    v12.cbSize = 80;
    v12.hInstance = hInstance;
    v12.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
    v12.lpszClassName = L"IE_PopupMenuOwner";
    v12.lpfnWndProc = s_PopupMenuOwnerWndProc;
    RegisterClassExW(&v12);
    Rect = 0;
    GetWindowRect(a1, &Rect);
    Window = CreateWindowExW(
               0x82800A8u,
               L"IE_PopupMenuOwner",
               &Source,
               0x80000000,
               Rect.left,
               Rect.top,
               Rect.right - Rect.left,
               Rect.bottom - Rect.top,
               a1,
               0,
               hInstance,
               0);
    *a4 = Window;
    if ( Window )
    {
      SetLayeredWindowAttributes(Window, 0, 0xFFu, 2u);
      if ( (unsigned __int8)IEConfiguration_GetBool(268435461) && (unsigned __int8)IEConfiguration_GetBool(536870914) )
        SetWindowLongPtrW(*a4, -21, (LONG_PTR)a1);
      return 1;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1810cad3c  mov     rax, rsp
0x1810cad3f  mov     [rax+20h], r9
0x1810cad43  mov     [rax+18h], r8b
0x1810cad47  mov     [rax+10h], rdx
0x1810cad4b  mov     [rax+8], rcx
0x1810cad4f  push    rbp
0x1810cad50  push    rbx
0x1810cad51  push    rsi
0x1810cad52  push    rdi
0x1810cad53  push    r14
0x1810cad55  push    r15
0x1810cad57  lea     rbp, [rax-5Fh]
0x1810cad5b  sub     rsp, 0D8h
0x1810cad62  mov     rax, cs:__security_cookie
0x1810cad69  xor     rax, rsp
0x1810cad6c  mov     [rbp+57h+var_40], rax
0x1810cad70  mov     r14, [rbp+57h+arg_18]
0x1810cad74  xor     edi, edi
0x1810cad76  mov     rsi, [rbp+57h+hwnd]
0x1810cad7a  mov     r15, cs:?g_hInstCore@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstCore
0x1810cad81  mov     rcx, rsi; hwnd
0x1810cad84  lea     edx, [rdi+2]; gaFlags
0x1810cad87  mov     qword ptr [r14], 0
0x1810cad8e  call    cs:__imp_GetAncestor
0x1810cad95  nop     dword ptr [rax+rax+00h]
0x1810cad9a  mov     rcx, rax; hWnd
0x1810cad9d  xor     edx, edx; lpdwProcessId
0x1810cad9f  call    cs:__imp_GetWindowThreadProcessId
0x1810cada6  nop     dword ptr [rax+rax+00h]
0x1810cadab  mov     ebx, eax
0x1810cadad  call    cs:__imp_GetCurrentThreadId
0x1810cadb4  nop     dword ptr [rax+rax+00h]
0x1810cadb9  cmp     ebx, eax
0x1810cadbb  jz      loc_1810CAEEE
0x1810cadc1  lea     ebx, [rdi+50h]
0x1810cadc4  xor     edx, edx; Val
0x1810cadc6  mov     r8d, ebx; Size
0x1810cadc9  lea     rcx, [rbp+57h+var_A0]; void *
0x1810cadcd  call    memset_0
0x1810cadd2  mov     edx, 7F00h; lpCursorName
0x1810cadd7  mov     [rbp+57h+var_A0.cbSize], ebx
0x1810cadda  xor     ecx, ecx; hInstance
0x1810caddc  mov     [rbp+57h+var_A0.hInstance], r15
0x1810cade0  call    cs:__imp_LoadCursorW
0x1810cade7  nop     dword ptr [rax+rax+00h]
0x1810cadec  mov     [rbp+57h+var_A0.hCursor], rax
0x1810cadf0  lea     rbx, String2; "IE_PopupMenuOwner"
0x1810cadf7  lea     rax, ?s_PopupMenuOwnerWndProc@@YA_JPEAUHWND__@@I_K_J@Z; s_PopupMenuOwnerWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1810cadfe  mov     [rbp+57h+var_A0.lpszClassName], rbx
0x1810cae02  lea     rcx, [rbp+57h+var_A0]; WNDCLASSEXW *
0x1810cae06  mov     [rbp+57h+var_A0.lpfnWndProc], rax
0x1810cae0a  call    cs:__imp_RegisterClassExW
0x1810cae11  nop     dword ptr [rax+rax+00h]
0x1810cae16  xorps   xmm0, xmm0
0x1810cae19  lea     rdx, [rbp+57h+Rect]; lpRect
0x1810cae1d  mov     rcx, rsi; hWnd
0x1810cae20  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1810cae24  call    cs:__imp_GetWindowRect
0x1810cae2b  nop     dword ptr [rax+rax+00h]
0x1810cae30  mov     ecx, [rbp+57h+Rect.left]
0x1810cae33  mov     r9d, 80000000h; dwStyle
0x1810cae39  mov     r8d, [rbp+57h+Rect.bottom]
0x1810cae3d  mov     rdx, rbx; lpClassName
0x1810cae40  mov     r10d, [rbp+57h+Rect.top]
0x1810cae44  sub     r8d, r10d
0x1810cae47  mov     eax, [rbp+57h+Rect.right]
0x1810cae4a  mov     [rsp+58h], rdi; lpParam
0x1810cae4f  sub     eax, ecx
0x1810cae51  mov     [rsp+100h+hInstance], r15; hInstance
0x1810cae56  mov     [rsp+100h+hMenu], rdi; hMenu
0x1810cae5b  mov     [rsp+100h+hWndParent], rsi; hWndParent
0x1810cae60  mov     [rsp+100h+nHeight], r8d; nHeight
0x1810cae65  lea     r8, Source; lpWindowName
0x1810cae6c  mov     [rsp+100h+nWidth], eax; nWidth
0x1810cae70  mov     [rsp+100h+Y], r10d; Y
0x1810cae75  mov     [rsp+100h+X], ecx; X
0x1810cae79  mov     ecx, 82800A8h; dwExStyle
0x1810cae7e  call    cs:__imp_CreateWindowExW
0x1810cae85  nop     dword ptr [rax+rax+00h]
0x1810cae8a  mov     [r14], rax
0x1810cae8d  test    rax, rax
0x1810cae90  jz      short loc_1810CAEEE
0x1810cae92  lea     r9d, [rdi+2]; dwFlags
0x1810cae96  mov     r8b, 0FFh; bAlpha
0x1810cae99  xor     edx, edx; crKey
0x1810cae9b  mov     rcx, rax; hwnd
0x1810cae9e  call    cs:__imp_SetLayeredWindowAttributes
0x1810caea5  nop     dword ptr [rax+rax+00h]
0x1810caeaa  mov     ecx, 10000005h
0x1810caeaf  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1810caeb6  nop     dword ptr [rax+rax+00h]
0x1810caebb  test    al, al
0x1810caebd  jz      short loc_1810CAEE9
0x1810caebf  mov     ecx, 20000002h
0x1810caec4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1810caecb  nop     dword ptr [rax+rax+00h]
0x1810caed0  test    al, al
0x1810caed2  jz      short loc_1810CAEE9
0x1810caed4  mov     rcx, [r14]; hWnd
0x1810caed7  lea     edx, [rdi-15h]; nIndex
0x1810caeda  mov     r8, rsi; dwNewLong
0x1810caedd  call    cs:__imp_SetWindowLongPtrW
0x1810caee4  nop     dword ptr [rax+rax+00h]
0x1810caee9  mov     edi, 1
0x1810caeee  mov     eax, edi
0x1810caef0  mov     rcx, [rbp+57h+var_40]
0x1810caef4  xor     rcx, rsp; StackCookie
0x1810caef7  call    __security_check_cookie
0x1810caefc  add     rsp, 0D8h
0x1810caf03  pop     r15
0x1810caf05  pop     r14
0x1810caf07  pop     rdi
0x1810caf08  pop     rsi
0x1810caf09  pop     rbx
0x1810caf0a  pop     rbp
0x1810caf0b  retn
```
