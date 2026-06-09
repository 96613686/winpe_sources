# CoreDispatcherInterop::RuntimeClassInitialize(void)

- ea: `0x180064338`
- end: `0x18006445a`
- name: `?RuntimeClassInitialize@CoreDispatcherInterop@@QEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CoreDispatcherInterop *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800100dc`

## callees

- `0x180018b30`
- `0x18002c5b0`
- `0x180037b5c`
- `0x180064338`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180064408`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180064408`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18006439b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18006439b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006434a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006434a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800643a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800643a6`

## pseudocode

```c
__int64 __fastcall CoreDispatcherInterop::RuntimeClassInitialize(CoreDispatcherInterop *this)
{
  HMODULE hInstance; // rdi
  ATOM v3; // ax
  const char *v4; // r9
  HWND Window; // rax
  const char *v6; // r9
  WNDCLASSEXW v8; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  hInstance = GetModuleHandleW(0);
  if ( !CoreDispatcherInterop::windowClassAtom )
  {
    memset_0(&v8, 0, sizeof(v8));
    v8.cbSize = 80;
    v8.lpfnWndProc = (WNDPROC)CoreDispatcherInterop::WndProc;
    v8.hInstance = hInstance;
    v8.lpszClassName = L"CoreDispatcher Interop Message Window";
    v3 = RegisterClassExW(&v8);
    if ( v3 )
    {
      CoreDispatcherInterop::windowClassAtom = v3;
    }
    else if ( GetLastError() != 1410 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\coredispatcherinterop.cpp",
        v4);
    }
  }
  Window = CreateWindowExW(
             0,
             L"CoreDispatcher Interop Message Window",
             0,
             0x88000000,
             0,
             0,
             0,
             0,
             HWND_MESSAGE,
             0,
             hInstance,
             this);
  if ( *((HWND *)this + 4) != Window )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\coredispatcherinterop.cpp",
      v6);
  if ( !Window )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\coredispatcherinterop.cpp",
      v6);
  return 0;
}

```

## disassembly

```asm
0x180064338  push    rbx
0x18006433a  push    rbp
0x18006433b  push    rdi
0x18006433c  push    r14
0x18006433e  sub     rsp, 0B8h
0x180064345  mov     rbx, rcx
0x180064348  xor     ecx, ecx; lpModuleName
0x18006434a  call    cs:__imp_GetModuleHandleW
0x180064350  xor     ebp, ebp
0x180064352  lea     r14, ClassName; "CoreDispatcher Interop Message Window"
0x180064359  cmp     cs:?windowClassAtom@CoreDispatcherInterop@@0GA, bp; ushort CoreDispatcherInterop::windowClassAtom
0x180064360  mov     rdi, rax
0x180064363  jnz     short loc_1800643D2
0x180064365  xor     edx, edx; Val
0x180064367  lea     r8d, [rbp+50h]; Size
0x18006436b  lea     rcx, [rsp+0D8h+var_78]; void *
0x180064370  call    memset_0
0x180064375  lea     rax, ?WndProc@CoreDispatcherInterop@@CA_JPEAUHWND__@@I_K_J@Z; CoreDispatcherInterop::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18006437c  mov     [rsp+0D8h+var_78.cbSize], 50h ; 'P'
0x180064384  lea     rcx, [rsp+0D8h+var_78]; WNDCLASSEXW *
0x180064389  mov     [rsp+0D8h+var_78.lpfnWndProc], rax
0x18006438e  mov     [rsp+0D8h+var_78.hInstance], rdi
0x180064393  mov     [rsp+0D8h+var_78.lpszClassName], r14
0x18006439b  call    cs:__imp_RegisterClassExW
0x1800643a1  test    ax, ax
0x1800643a4  jnz     short loc_1800643CB
0x1800643a6  call    cs:__imp_GetLastError
0x1800643ac  cmp     eax, 582h
0x1800643b1  jz      short loc_1800643D2
0x1800643b3  mov     rcx, [rsp+0D8h]; this
0x1800643bb  lea     r8, aOnecoreuapInet_22; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800643c2  lea     edx, [rbp+2Dh]; void *
0x1800643c5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800643cb  mov     cs:?windowClassAtom@CoreDispatcherInterop@@0GA, ax; ushort CoreDispatcherInterop::windowClassAtom
0x1800643d2  mov     [rsp+0D8h+lpParam], rbx; lpParam
0x1800643d7  mov     r9d, 88000000h; dwStyle
0x1800643dd  mov     [rsp+0D8h+hInstance], rdi; hInstance
0x1800643e2  xor     r8d, r8d; lpWindowName
0x1800643e5  mov     [rsp+0D8h+hMenu], rbp; hMenu
0x1800643ea  mov     rdx, r14; lpClassName
0x1800643ed  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1800643f6  xor     ecx, ecx; dwExStyle
0x1800643f8  mov     [rsp+0D8h+nHeight], ebp; nHeight
0x1800643fc  mov     [rsp+0D8h+nWidth], ebp; nWidth
0x180064400  mov     [rsp+0D8h+Y], ebp; Y
0x180064404  mov     [rsp+0D8h+X], ebp; X
0x180064408  call    cs:__imp_CreateWindowExW
0x18006440e  cmp     [rbx+20h], rax
0x180064412  jz      short loc_18006442E
0x180064414  mov     rcx, [rsp+0D8h]; this
0x18006441c  lea     r8, aOnecoreuapInet_22; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180064423  mov     edx, 41h ; 'A'; void *
0x180064428  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006442e  test    rax, rax
0x180064431  jnz     short loc_18006444B
0x180064433  mov     rcx, [rsp+0D8h]; this
0x18006443b  lea     r8, aOnecoreuapInet_22; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180064442  lea     edx, [rax+44h]; void *
0x180064445  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006444b  xor     eax, eax
0x18006444d  add     rsp, 0B8h
0x180064454  pop     r14
0x180064456  pop     rdi
0x180064457  pop     rbp
0x180064458  pop     rbx
0x180064459  retn
```
