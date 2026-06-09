# CMSMQEvent::CreateHiddenWindow(void)

- ea: `0x180009988`
- end: `0x180009a4d`
- name: `?CreateHiddenWindow@CMSMQEvent@@QEAAJXZ`
- size: `197`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cfa8`
- `0x18000da68`

## callees

- `0x180009988`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009a06`
- `KERNEL32!GetLastError` at `0x180009a06`
- `USER32!SetWindowLongPtrW` at `0x1800099fc`
- `USER32!SetWindowLongPtrW` at `0x1800099fc`
- `USER32!CreateWindowExW` at `0x1800099e5`
- `USER32!CreateWindowExW` at `0x1800099e5`
- `mqrt!MQLogHR` at `0x180009a2e`
- `mqrt!MQLogHR` at `0x180009a2e`

## pseudocode

```c
__int64 __fastcall CMSMQEvent::CreateHiddenWindow(LONG_PTR dwNewLong)
{
  HWND Window; // rax
  signed int LastError; // eax
  int v5; // edi
  int v6; // ebx
  unsigned int v7; // ecx

  Window = CreateWindowExW(
             0,
             (LPCWSTR)g_atomWndClass,
             L"EventWindow",
             0x8000000u,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             0,
             0,
             g_wndclassAsyncRcv.hInstance,
             0);
  *(_QWORD *)(dwNewLong + 72) = Window;
  if ( Window )
  {
    SetWindowLongPtrW(Window, 0, dwNewLong);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError;
    v6 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    else
      v7 = LastError;
    MQLogHR(v7, L"mqoa\\event", 0x3FCu);
    if ( v6 > 0 )
      return v5 | 0x80070000;
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180009988  mov     r11, rsp
0x18000998b  mov     [r11+8], rbx
0x18000998f  push    rdi
0x180009990  sub     rsp, 60h
0x180009994  mov     rax, cs:?g_wndclassAsyncRcv@@3UtagWNDCLASSA@@A.hInstance; tagWNDCLASSA g_wndclassAsyncRcv ...
0x18000999b  lea     r8, WindowName; "EventWindow"
0x1800099a2  movzx   edx, cs:?g_atomWndClass@@3GA; lpClassName
0x1800099a9  mov     rbx, rcx
0x1800099ac  mov     qword ptr [r11-10h], 0
0x1800099b4  mov     r9d, 8000000h; dwStyle
0x1800099ba  mov     [r11-18h], rax
0x1800099be  xor     ecx, ecx; dwExStyle
0x1800099c0  mov     qword ptr [r11-20h], 0
0x1800099c8  mov     eax, 80000000h
0x1800099cd  mov     qword ptr [r11-28h], 0
0x1800099d5  mov     [rsp+68h+nHeight], eax; nHeight
0x1800099d9  mov     [rsp+68h+nWidth], eax; nWidth
0x1800099dd  mov     [rsp+68h+Y], eax; Y
0x1800099e1  mov     [rsp+68h+X], eax; X
0x1800099e5  call    cs:__imp_CreateWindowExW
0x1800099eb  mov     [rbx+48h], rax
0x1800099ef  test    rax, rax
0x1800099f2  jz      short loc_180009A06
0x1800099f4  mov     r8, rbx; dwNewLong
0x1800099f7  xor     edx, edx; nIndex
0x1800099f9  mov     rcx, rax; hWnd
0x1800099fc  call    cs:__imp_SetWindowLongPtrW
0x180009a02  xor     eax, eax
0x180009a04  jmp     short loc_180009A42
0x180009a06  call    cs:__imp_GetLastError
0x180009a0c  movzx   edi, ax
0x180009a0f  mov     ebx, eax
0x180009a11  test    eax, eax
0x180009a13  jg      short loc_180009A19
0x180009a15  mov     ecx, eax
0x180009a17  jmp     short loc_180009A21
0x180009a19  mov     ecx, edi
0x180009a1b  or      ecx, 80070000h
0x180009a21  mov     r8d, 3FCh
0x180009a27  lea     rdx, aMqoaEvent; "mqoa\\event"
0x180009a2e  call    cs:__imp_?MQLogHR@@YAXJPEB_WG@Z; MQLogHR(long,wchar_t const *,ushort)
0x180009a34  test    ebx, ebx
0x180009a36  jle     short loc_180009A40
0x180009a38  mov     ebx, edi
0x180009a3a  or      ebx, 80070000h
0x180009a40  mov     eax, ebx
0x180009a42  mov     rbx, [rsp+68h+arg_0]
0x180009a47  add     rsp, 60h
0x180009a4b  pop     rdi
0x180009a4c  retn
```
