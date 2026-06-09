# CTiNotify::CreateMsgWindow(void)

- ea: `0x180015948`
- end: `0x180015abb`
- name: `?CreateMsgWindow@CTiNotify@@AEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180015718`

## callees

- `0x1800091a8`
- `0x180015948`
- `0x180032f60`
- `0x180034970`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001598b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001598b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a2f`
- `USER32!RegisterClassW` at `0x1800159c7`
- `USER32!RegisterClassW` at `0x1800159c7`
- `USER32!SetWindowLongPtrW` at `0x180015aa2`
- `USER32!SetWindowLongPtrW` at `0x180015aa2`
- `USER32!CreateWindowExW` at `0x180015a20`
- `USER32!CreateWindowExW` at `0x180015a20`

## string_xrefs

- `0x1800159b3`: `TiBusUpdate`

## pseudocode

```c
__int64 __fastcall CTiNotify::CreateMsgWindow(LONG_PTR dwNewLong)
{
  HWND Window; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-58h] BYREF
  HMODULE phModule; // [rsp+C0h] [rbp+8h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  phModule = 0;
  GetModuleHandleExW(6u, (LPCWSTR)CTiNotify::staticWndProc, &phModule);
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.lpfnWndProc = (WNDPROC)CTiNotify::staticWndProc;
  WndClass.hInstance = phModule;
  WndClass.lpszClassName = L"TiBusUpdate";
  RegisterClassW(&WndClass);
  Window = CreateWindowExW(0, L"TiBusUpdate", 0, 0, 0, 0, 0, 0, 0, 0, phModule, 0);
  *(_QWORD *)(dwNewLong + 88) = Window;
  if ( Window )
  {
    LastError = 0;
    SetWindowLongPtrW(Window, -21, dwNewLong);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180015948  mov     [rsp+arg_8], rbx
0x18001594d  push    rdi
0x18001594e  sub     rsp, 0B0h
0x180015955  xor     edx, edx; Val
0x180015957  mov     rdi, rcx
0x18001595a  lea     rcx, [rsp+0B8h+WndClass]; void *
0x18001595f  lea     r8d, [rdx+48h]; Size
0x180015963  call    memset_0
0x180015968  lea     rbx, ?staticWndProc@CTiNotify@@CA_JPEAUHWND__@@I_K_J@Z; CTiNotify::staticWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001596f  mov     [rsp+0B8h+phModule], 0
0x18001597b  mov     rdx, rbx; lpModuleName
0x18001597e  lea     r8, [rsp+0B8h+phModule]; phModule
0x180015986  mov     ecx, 6; dwFlags
0x18001598b  call    cs:__imp_GetModuleHandleExW
0x180015991  xor     edx, edx; Val
0x180015993  lea     rcx, [rsp+0B8h+WndClass]; void *
0x180015998  lea     r8d, [rdx+48h]; Size
0x18001599c  call    memset_0
0x1800159a1  mov     rax, [rsp+0B8h+phModule]
0x1800159a9  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x1800159ae  mov     [rsp+0B8h+WndClass.lpfnWndProc], rbx
0x1800159b3  lea     rbx, ClassName; "TiBusUpdate"
0x1800159ba  mov     [rsp+0B8h+WndClass.hInstance], rax
0x1800159bf  mov     [rsp+0B8h+WndClass.lpszClassName], rbx
0x1800159c7  call    cs:__imp_RegisterClassW
0x1800159cd  mov     rax, [rsp+0B8h+phModule]
0x1800159d5  xor     r9d, r9d; dwStyle
0x1800159d8  mov     [rsp+0B8h+lpParam], 0; lpParam
0x1800159e1  xor     r8d, r8d; lpWindowName
0x1800159e4  mov     [rsp+0B8h+hInstance], rax; hInstance
0x1800159e9  mov     rdx, rbx; lpClassName
0x1800159ec  mov     [rsp+0B8h+hMenu], 0; hMenu
0x1800159f5  xor     ecx, ecx; dwExStyle
0x1800159f7  mov     [rsp+0B8h+hWndParent], 0; hWndParent
0x180015a00  mov     [rsp+0B8h+nHeight], 0; nHeight
0x180015a08  mov     [rsp+0B8h+nWidth], 0; nWidth
0x180015a10  mov     [rsp+0B8h+Y], 0; Y
0x180015a18  mov     [rsp+0B8h+X], 0; X
0x180015a20  call    cs:__imp_CreateWindowExW
0x180015a26  mov     [rdi+58h], rax
0x180015a2a  test    rax, rax
0x180015a2d  jnz     short loc_180015A97
0x180015a2f  call    cs:__imp_GetLastError
0x180015a35  mov     ebx, eax
0x180015a37  mov     rax, cs:WPP_GLOBAL_Control
0x180015a3e  lea     rcx, WPP_GLOBAL_Control
0x180015a45  cmp     rax, rcx
0x180015a48  jz      short loc_180015A7E
0x180015a4a  test    byte ptr [rax+1Ch], 8
0x180015a4e  jz      short loc_180015A7E
0x180015a50  cmp     byte ptr [rax+19h], 2
0x180015a54  jb      short loc_180015A7E
0x180015a56  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180015a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a62  lea     r8, WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids
0x180015a69  mov     edx, 13h
0x180015a6e  mov     [rsp+0B8h+X], ebx
0x180015a72  mov     r9d, eax
0x180015a75  mov     rcx, [rcx+10h]
0x180015a79  call    WPP_SF_Dd
0x180015a7e  test    ebx, ebx
0x180015a80  jle     short loc_180015A8B
0x180015a82  movzx   ebx, bx
0x180015a85  or      ebx, 80070000h
0x180015a8b  test    ebx, ebx
0x180015a8d  mov     eax, 80004005h
0x180015a92  cmovns  ebx, eax
0x180015a95  jmp     short loc_180015AA8
0x180015a97  xor     ebx, ebx
0x180015a99  mov     r8, rdi; dwNewLong
0x180015a9c  mov     rcx, rax; hWnd
0x180015a9f  lea     edx, [rbx-15h]; nIndex
0x180015aa2  call    cs:__imp_SetWindowLongPtrW
0x180015aa8  mov     eax, ebx
0x180015aaa  mov     rbx, [rsp+0B8h+arg_8]
0x180015ab2  add     rsp, 0B0h
0x180015ab9  pop     rdi
0x180015aba  retn
```
