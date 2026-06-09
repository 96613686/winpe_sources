# CreateThreadAffinePopupMenuOwnerIfNeeded(HWND__ *,HINSTANCE__ *,bool,HWND__ * *)

- ea: `0x18109873c`
- end: `0x1810988ca`
- name: `?CreateThreadAffinePopupMenuOwnerIfNeeded@@YAHPEAUHWND__@@PEAUHINSTANCE__@@_NPEAPEAU1@@Z`
- size: `398`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, bool, HWND *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180b36f60`
- `0x180f00438`

## callees

- `0x18109873c`
- `0x1810c2cb6`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1810987a1`
- `KERNEL32!GetCurrentThreadId` at `0x1810987a1`
- `USER32!SetWindowLongPtrW` at `0x1810988a1`
- `USER32!SetWindowLongPtrW` at `0x1810988a1`
- `USER32!GetWindowThreadProcessId` at `0x181098799`
- `USER32!GetWindowThreadProcessId` at `0x181098799`
- `USER32!LoadCursorW` at `0x1810987ce`
- `USER32!LoadCursorW` at `0x1810987ce`
- `USER32!GetAncestor` at `0x18109878e`
- `USER32!GetAncestor` at `0x18109878e`
- `USER32!GetWindowRect` at `0x181098806`
- `USER32!GetWindowRect` at `0x181098806`
- `USER32!CreateWindowExW` at `0x18109885a`
- `USER32!CreateWindowExW` at `0x18109885a`
- `USER32!SetLayeredWindowAttributes` at `0x181098874`
- `USER32!SetLayeredWindowAttributes` at `0x181098874`
- `USER32!RegisterClassExW` at `0x1810987f2`
- `USER32!RegisterClassExW` at `0x1810987f2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18109887f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18109888e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18109887f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18109888e`

## pseudocode

```c
__int64 __fastcall CreateThreadAffinePopupMenuOwnerIfNeeded(HWND a1, HINSTANCE a2, __int64 a3, HWND *a4)
{
  unsigned int v5; // edi
  HINSTANCE hInstance; // r15
  HWND Ancestor; // rax
  DWORD WindowThreadProcessId; // ebx
  HWND Window; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  WNDCLASSEXW v18; // [rsp+68h] [rbp-49h] BYREF
  struct tagRECT Rect; // [rsp+B8h] [rbp+7h] BYREF

  v5 = 0;
  hInstance = g_hInstCore;
  *a4 = 0;
  Ancestor = GetAncestor(a1, 2u);
  WindowThreadProcessId = GetWindowThreadProcessId(Ancestor, 0);
  if ( WindowThreadProcessId != GetCurrentThreadId() )
  {
    memset_0(&v18, 0, sizeof(v18));
    v18.cbSize = 80;
    v18.hInstance = hInstance;
    v18.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
    v18.lpszClassName = L"IE_PopupMenuOwner";
    v18.lpfnWndProc = s_PopupMenuOwnerWndProc;
    RegisterClassExW(&v18);
    Rect = 0;
    GetWindowRect(a1, &Rect);
    Window = CreateWindowExW(
               0x82800A8u,
               L"IE_PopupMenuOwner",
               &LocaleName,
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
      if ( (unsigned __int8)IEConfiguration_GetBool(268435461, v11, v12, v13)
        && (unsigned __int8)IEConfiguration_GetBool(536870914, v14, v15, v16) )
      {
        SetWindowLongPtrW(*a4, -21, (LONG_PTR)a1);
      }
      return 1;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18109873c  mov     rax, rsp
0x18109873f  mov     [rax+20h], r9
0x181098743  mov     [rax+18h], r8b
0x181098747  mov     [rax+10h], rdx
0x18109874b  mov     [rax+8], rcx
0x18109874f  push    rbp
0x181098750  push    rbx
0x181098751  push    rsi
0x181098752  push    rdi
0x181098753  push    r14
0x181098755  push    r15
0x181098757  lea     rbp, [rax-5Fh]
0x18109875b  sub     rsp, 0D8h
0x181098762  mov     rax, cs:__security_cookie
0x181098769  xor     rax, rsp
0x18109876c  mov     [rbp+57h+var_40], rax
0x181098770  mov     r14, [rbp+57h+arg_18]
0x181098774  xor     edi, edi
0x181098776  mov     rsi, [rbp+57h+hwnd]
0x18109877a  mov     r15, cs:?g_hInstCore@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstCore
0x181098781  mov     rcx, rsi; hwnd
0x181098784  lea     edx, [rdi+2]; gaFlags
0x181098787  mov     qword ptr [r14], 0
0x18109878e  call    cs:__imp_GetAncestor
0x181098794  mov     rcx, rax; hWnd
0x181098797  xor     edx, edx; lpdwProcessId
0x181098799  call    cs:__imp_GetWindowThreadProcessId
0x18109879f  mov     ebx, eax
0x1810987a1  call    cs:__imp_GetCurrentThreadId
0x1810987a7  cmp     ebx, eax
0x1810987a9  jz      loc_1810988AC
0x1810987af  lea     ebx, [rdi+50h]
0x1810987b2  xor     edx, edx; Val
0x1810987b4  mov     r8d, ebx; Size
0x1810987b7  lea     rcx, [rbp+57h+var_A0]; void *
0x1810987bb  call    memset_0
0x1810987c0  mov     edx, 7F00h; lpCursorName
0x1810987c5  mov     [rbp+57h+var_A0.cbSize], ebx
0x1810987c8  xor     ecx, ecx; hInstance
0x1810987ca  mov     [rbp+57h+var_A0.hInstance], r15
0x1810987ce  call    cs:__imp_LoadCursorW
0x1810987d4  mov     [rbp+57h+var_A0.hCursor], rax
0x1810987d8  lea     rbx, aIePopupmenuown; "IE_PopupMenuOwner"
0x1810987df  lea     rax, ?s_PopupMenuOwnerWndProc@@YA_JPEAUHWND__@@I_K_J@Z; s_PopupMenuOwnerWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1810987e6  mov     [rbp+57h+var_A0.lpszClassName], rbx
0x1810987ea  lea     rcx, [rbp+57h+var_A0]; WNDCLASSEXW *
0x1810987ee  mov     [rbp+57h+var_A0.lpfnWndProc], rax
0x1810987f2  call    cs:__imp_RegisterClassExW
0x1810987f8  xorps   xmm0, xmm0
0x1810987fb  lea     rdx, [rbp+57h+Rect]; lpRect
0x1810987ff  mov     rcx, rsi; hWnd
0x181098802  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x181098806  call    cs:__imp_GetWindowRect
0x18109880c  mov     ecx, [rbp+57h+Rect.left]
0x18109880f  mov     r9d, 80000000h; dwStyle
0x181098815  mov     r8d, [rbp+57h+Rect.bottom]
0x181098819  mov     rdx, rbx; lpClassName
0x18109881c  mov     r10d, [rbp+57h+Rect.top]
0x181098820  sub     r8d, r10d
0x181098823  mov     eax, [rbp+57h+Rect.right]
0x181098826  mov     [rsp+58h], rdi; lpParam
0x18109882b  sub     eax, ecx
0x18109882d  mov     [rsp+100h+hInstance], r15; hInstance
0x181098832  mov     [rsp+100h+hMenu], rdi; hMenu
0x181098837  mov     [rsp+100h+hWndParent], rsi; hWndParent
0x18109883c  mov     [rsp+100h+nHeight], r8d; nHeight
0x181098841  lea     r8, LocaleName; lpWindowName
0x181098848  mov     [rsp+100h+nWidth], eax; nWidth
0x18109884c  mov     [rsp+100h+Y], r10d; Y
0x181098851  mov     [rsp+100h+X], ecx; X
0x181098855  mov     ecx, 82800A8h; dwExStyle
0x18109885a  call    cs:__imp_CreateWindowExW
0x181098860  mov     [r14], rax
0x181098863  test    rax, rax
0x181098866  jz      short loc_1810988AC
0x181098868  lea     r9d, [rdi+2]; dwFlags
0x18109886c  mov     r8b, 0FFh; bAlpha
0x18109886f  xor     edx, edx; crKey
0x181098871  mov     rcx, rax; hwnd
0x181098874  call    cs:__imp_SetLayeredWindowAttributes
0x18109887a  mov     ecx, 10000005h
0x18109887f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x181098885  test    al, al
0x181098887  jz      short loc_1810988A7
0x181098889  mov     ecx, 20000002h
0x18109888e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x181098894  test    al, al
0x181098896  jz      short loc_1810988A7
0x181098898  mov     rcx, [r14]; hWnd
0x18109889b  lea     edx, [rdi-15h]; nIndex
0x18109889e  mov     r8, rsi; dwNewLong
0x1810988a1  call    cs:__imp_SetWindowLongPtrW
0x1810988a7  mov     edi, 1
0x1810988ac  mov     eax, edi
0x1810988ae  mov     rcx, [rbp+57h+var_40]
0x1810988b2  xor     rcx, rsp; StackCookie
0x1810988b5  call    __security_check_cookie
0x1810988ba  add     rsp, 0D8h
0x1810988c1  pop     r15
0x1810988c3  pop     r14
0x1810988c5  pop     rdi
0x1810988c6  pop     rsi
0x1810988c7  pop     rbx
0x1810988c8  pop     rbp
0x1810988c9  retn
```
