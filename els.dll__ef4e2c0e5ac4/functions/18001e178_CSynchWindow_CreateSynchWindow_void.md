# CSynchWindow::CreateSynchWindow(void)

- ea: `0x18001e178`
- end: `0x18001e20e`
- name: `?CreateSynchWindow@CSynchWindow@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(CSynchWindow *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001435c`

## callees

- `0x18001e178`
- `0x18001e544`
- `0x18001e658`
- `0x180022292`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e1cf`
- `KERNEL32!GetLastError` at `0x18001e1e6`
- `KERNEL32!GetLastError` at `0x18001e1cf`
- `KERNEL32!GetLastError` at `0x18001e1e6`

## pseudocode

```c
__int64 __fastcall CSynchWindow::CreateSynchWindow(CSynchWindow *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-58h] BYREF

  v1 = 0;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.lpfnWndProc = (WNDPROC)CSynchWindow::_WndProc;
  WndClass.hInstance = g_hinst;
  WndClass.lpszClassName = L"Event Viewer Snapin Synch";
  if ( !(unsigned __int16)IsolationAwareRegisterClassW(&WndClass) )
    GetLastError();
  g_SynchWnd = IsolationAwareCreateWindowExW();
  if ( !g_SynchWnd )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x18001e178  mov     [rsp+arg_0], rbx
0x18001e17d  push    rdi
0x18001e17e  sub     rsp, 0B0h
0x18001e185  xor     edi, edi
0x18001e187  lea     rcx, [rsp+0B8h+WndClass]; void *
0x18001e18c  xor     edx, edx; Val
0x18001e18e  mov     ebx, edi
0x18001e190  lea     r8d, [rdi+48h]; Size
0x18001e194  call    memset_0
0x18001e199  lea     rax, ?_WndProc@CSynchWindow@@CA_JPEAUHWND__@@I_K_J@Z; CSynchWindow::_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001e1a0  mov     [rsp+0B8h+WndClass.lpfnWndProc], rax
0x18001e1a5  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x18001e1aa  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18001e1b1  mov     [rsp+0B8h+WndClass.hInstance], rax
0x18001e1b6  lea     rax, ClassName; "Event Viewer Snapin Synch"
0x18001e1bd  mov     [rsp+0B8h+WndClass.lpszClassName], rax
0x18001e1c5  call    IsolationAwareRegisterClassW
0x18001e1ca  test    ax, ax
0x18001e1cd  jnz     short loc_18001E1D5
0x18001e1cf  call    cs:__imp_GetLastError
0x18001e1d5  call    IsolationAwareCreateWindowExW
0x18001e1da  mov     cs:?g_SynchWnd@@3VCSynchWindow@@A, rax; CSynchWindow g_SynchWnd
0x18001e1e1  test    rax, rax
0x18001e1e4  jnz     short loc_18001E1FB
0x18001e1e6  call    cs:__imp_GetLastError
0x18001e1ec  mov     ebx, eax
0x18001e1ee  test    eax, eax
0x18001e1f0  jle     short loc_18001E1FB
0x18001e1f2  movzx   ebx, ax
0x18001e1f5  or      ebx, 80070000h
0x18001e1fb  mov     eax, ebx
0x18001e1fd  mov     rbx, [rsp+0B8h+arg_0]
0x18001e205  add     rsp, 0B0h
0x18001e20c  pop     rdi
0x18001e20d  retn
```
