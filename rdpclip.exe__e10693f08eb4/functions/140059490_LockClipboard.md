# LockClipboard

- ea: `0x140059490`
- end: `0x1400595eb`
- name: `LockClipboard`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400595f4`
- `0x140059700`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x140059490`

## import_xrefs

- `USER32!RegisterClassW` at `0x140059569`
- `USER32!RegisterClassW` at `0x140059569`
- `USER32!CreateWindowExW` at `0x1400595bc`
- `USER32!CreateWindowExW` at `0x1400595bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400594cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400594cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400594d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400594d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400595d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400595d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400594a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400594a0`

## pseudocode

```c
HWND LockClipboard()
{
  HWND result; // rax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-58h] BYREF
  HMODULE phModule; // [rsp+C0h] [rbp+8h] BYREF

  AcquireSRWLockExclusive(&SRWLock);
  result = hWnd;
  if ( !hWnd )
  {
    phModule = 0;
    if ( !GetModuleHandleExW(2u, 0, &phModule) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_5c94b9cef7b3331dfbf1e812a2f772b8_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
    }
    memset_0(&WndClass, 0, sizeof(WndClass));
    WndClass.cbWndExtra = 8;
    WndClass.lpfnWndProc = (WNDPROC)ClipboardWndProc;
    WndClass.hInstance = phModule;
    WndClass.lpszClassName = L"CLIPBRDWNDCLASS";
    RegisterClassW(&WndClass);
    result = CreateWindowExW(
               0,
               WndClass.lpszClassName,
               0,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               HWND_MESSAGE,
               0,
               WndClass.hInstance,
               0);
    hWnd = result;
    if ( !result )
    {
      ReleaseSRWLockExclusive(&SRWLock);
      return hWnd;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140059490  push    rbx
0x140059492  sub     rsp, 0B0h
0x140059499  lea     rcx, SRWLock; SRWLock
0x1400594a0  call    cs:__imp_AcquireSRWLockExclusive
0x1400594a6  mov     rax, cs:hWnd
0x1400594ad  test    rax, rax
0x1400594b0  jnz     loc_1400595E2
0x1400594b6  lea     r8, [rsp+0B8h+phModule]; phModule
0x1400594be  mov     [rsp+0B8h+phModule], rax
0x1400594c6  xor     edx, edx; lpModuleName
0x1400594c8  lea     ecx, [rax+2]; dwFlags
0x1400594cb  call    cs:__imp_GetModuleHandleExW
0x1400594d1  test    eax, eax
0x1400594d3  jnz     short loc_140059524
0x1400594d5  call    cs:__imp_GetLastError
0x1400594db  mov     ebx, eax
0x1400594dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400594e4  lea     rax, WPP_GLOBAL_Control
0x1400594eb  cmp     rcx, rax
0x1400594ee  jz      short loc_140059524
0x1400594f0  test    byte ptr [rcx+1Ch], 8
0x1400594f4  jz      short loc_140059524
0x1400594f6  cmp     byte ptr [rcx+19h], 2
0x1400594fa  jb      short loc_140059524
0x1400594fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059501  mov     rcx, cs:WPP_GLOBAL_Control
0x140059508  lea     r8, WPP_5c94b9cef7b3331dfbf1e812a2f772b8_Traceguids
0x14005950f  mov     edx, 0Ah
0x140059514  mov     [rsp+0B8h+X], ebx
0x140059518  mov     r9d, eax
0x14005951b  mov     rcx, [rcx+10h]
0x14005951f  call    WPP_SF_Dd
0x140059524  xor     edx, edx; Val
0x140059526  lea     rcx, [rsp+0B8h+WndClass]; void *
0x14005952b  lea     r8d, [rdx+48h]; Size
0x14005952f  call    memset_0
0x140059534  lea     rax, ClipboardWndProc
0x14005953b  mov     [rsp+0B8h+WndClass.cbWndExtra], 8
0x140059543  mov     [rsp+0B8h+WndClass.lpfnWndProc], rax
0x140059548  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x14005954d  mov     rax, [rsp+0B8h+phModule]
0x140059555  mov     [rsp+0B8h+WndClass.hInstance], rax
0x14005955a  lea     rax, aClipbrdwndclas; "CLIPBRDWNDCLASS"
0x140059561  mov     [rsp+0B8h+WndClass.lpszClassName], rax
0x140059569  call    cs:__imp_RegisterClassW
0x14005956f  mov     rax, [rsp+0B8h+WndClass.hInstance]
0x140059574  mov     r9d, 80000000h; dwStyle
0x14005957a  mov     rdx, [rsp+0B8h+WndClass.lpszClassName]; lpClassName
0x140059582  xor     r8d, r8d; lpWindowName
0x140059585  mov     [rsp+0B8h+lpParam], 0; lpParam
0x14005958e  xor     ecx, ecx; dwExStyle
0x140059590  mov     [rsp+0B8h+hInstance], rax; hInstance
0x140059595  mov     eax, 80000000h
0x14005959a  mov     [rsp+0B8h+hMenu], 0; hMenu
0x1400595a3  mov     [rsp+0B8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1400595ac  mov     [rsp+0B8h+nHeight], eax; nHeight
0x1400595b0  mov     [rsp+0B8h+nWidth], eax; nWidth
0x1400595b4  mov     [rsp+0B8h+Y], eax; Y
0x1400595b8  mov     [rsp+0B8h+X], eax; X
0x1400595bc  call    cs:__imp_CreateWindowExW
0x1400595c2  mov     cs:hWnd, rax
0x1400595c9  test    rax, rax
0x1400595cc  jnz     short loc_1400595E2
0x1400595ce  lea     rcx, SRWLock; SRWLock
0x1400595d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1400595db  mov     rax, cs:hWnd
0x1400595e2  add     rsp, 0B0h
0x1400595e9  pop     rbx
0x1400595ea  retn
```
