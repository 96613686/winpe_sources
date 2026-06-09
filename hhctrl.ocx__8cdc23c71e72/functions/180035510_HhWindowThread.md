# HhWindowThread

- ea: `0x180035510`
- end: `0x1800356dd`
- name: `HhWindowThread`
- size: `461`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180011490`
- `0x1800229a4`
- `0x18002d12c`
- `0x180035510`
- `0x180075c5a`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800356b7`
- `KERNEL32!CloseHandle` at `0x1800356b7`
- `KERNEL32!ReleaseSemaphore` at `0x1800355e2`
- `KERNEL32!ReleaseSemaphore` at `0x180035692`
- `KERNEL32!ReleaseSemaphore` at `0x1800355e2`
- `KERNEL32!ReleaseSemaphore` at `0x180035692`
- `KERNEL32!CreateSemaphoreA` at `0x180035629`
- `KERNEL32!CreateSemaphoreA` at `0x180035629`
- `KERNEL32!CreateFileMappingA` at `0x1800355b3`
- `KERNEL32!CreateFileMappingA` at `0x1800355b3`
- `KERNEL32!MapViewOfFile` at `0x1800355ff`
- `KERNEL32!MapViewOfFile` at `0x1800355ff`
- `ole32!OleInitialize` at `0x18003567e`
- `ole32!OleInitialize` at `0x18003567e`
- `ole32!OleUninitialize` at `0x1800356bd`
- `ole32!OleUninitialize` at `0x1800356bd`

## pseudocode

```c
__int64 __fastcall HhWindowThread(PVOID Parameter)
{
  HANDLE v1; // rax
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+60h] [rbp-78h] BYREF
  WNDCLASSA WndClass; // [rsp+80h] [rbp-58h] BYREF

  if ( !dword_18008C428 )
  {
    dword_18008C428 = 1;
    memset_0(&WndClass, 0, sizeof(WndClass));
    WndClass.lpszClassName = "HH_API";
    WndClass.lpfnWndProc = (WNDPROC)ApiWndProc;
    WndClass.hInstance = hInstance;
    IsolationAwareRegisterClassA(&WndClass);
  }
  *(_QWORD *)&FileMappingAttributes.nLength = 24;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  v1 = CreateFileMappingA((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0x2000u, "hh_share");
  g_hSharedMemory = v1;
  if ( v1 )
  {
    g_pszShare = (char *)MapViewOfFile(v1, 6u, 0, 0, 0);
    if ( !g_hsemMemory )
      g_hsemMemory = CreateSemaphoreA(0, 1, 9999, "hh_semaphore");
    g_hwndApi = (HWND)IsolationAwareCreateWindowExA(0, "HH_API", Class, 0, 0, 0, 0, 0, 0, 0, hInstance, 0);
    OleInitialize(0);
    ReleaseSemaphore(g_hsemMemory, 1, 0);
    AWMessagePump(g_hwndApi);
    g_hwndApi = 0;
    if ( g_hSharedMemory )
      CloseHandle(g_hSharedMemory);
    OleUninitialize();
    hObject = 0;
  }
  else
  {
    hObject = 0;
    if ( g_hsemMemory )
      ReleaseSemaphore(g_hsemMemory, 1, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180035510  mov     rax, rsp
0x180035513  mov     [rax+8], rbx
0x180035517  push    rsi
0x180035518  sub     rsp, 0D0h
0x18003551f  xor     ebx, ebx
0x180035521  lea     rsi, aHhApi; "HH_API"
0x180035528  cmp     cs:dword_18008C428, ebx
0x18003552e  jnz     short loc_18003557C
0x180035530  xor     edx, edx; Val
0x180035532  mov     cs:dword_18008C428, 1
0x18003553c  lea     r8d, [rbx+48h]; Size
0x180035540  lea     rcx, [rax-58h]; void *
0x180035544  call    memset_0
0x180035549  lea     rax, ?ApiWndProc@@YA_JPEAUHWND__@@I_K_J@Z; ApiWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180035550  mov     [rsp+0D8h+WndClass.lpszClassName], rsi
0x180035558  mov     [rsp+0D8h+WndClass.lpfnWndProc], rax
0x180035560  lea     rcx, [rsp+0D8h+WndClass]; lpWndClass
0x180035568  mov     rax, cs:hInstance
0x18003556f  mov     [rsp+0D8h+WndClass.hInstance], rax
0x180035577  call    IsolationAwareRegisterClassA
0x18003557c  xor     r9d, r9d; dwMaximumSizeHigh
0x18003557f  mov     qword ptr [rsp+0D8h+FileMappingAttributes.nLength], 18h
0x180035588  lea     rax, Name; "hh_share"
0x18003558f  mov     qword ptr [rsp+0D8h+FileMappingAttributes.bInheritHandle], rbx
0x180035594  mov     [rsp+0D8h+lpName], rax; lpName
0x180035599  lea     rdx, [rsp+0D8h+FileMappingAttributes]; lpFileMappingAttributes
0x18003559e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800355a2  mov     [rsp+0D8h+FileMappingAttributes.lpSecurityDescriptor], rbx
0x1800355a7  lea     r8d, [r9+4]; flProtect
0x1800355ab  mov     [rsp+0D8h+dwMaximumSizeLow], 2000h; dwMaximumSizeLow
0x1800355b3  call    cs:__imp_CreateFileMappingA
0x1800355b9  mov     cs:?g_hSharedMemory@@3PEAXEA, rax; void * g_hSharedMemory
0x1800355c0  test    rax, rax
0x1800355c3  jnz     short loc_1800355ED
0x1800355c5  mov     rcx, cs:?g_hsemMemory@@3PEAXEA; hSemaphore
0x1800355cc  mov     cs:hObject, rbx
0x1800355d3  test    rcx, rcx
0x1800355d6  jz      loc_1800356CA
0x1800355dc  xor     r8d, r8d; lpPreviousCount
0x1800355df  lea     edx, [rax+1]; lReleaseCount
0x1800355e2  call    cs:__imp_ReleaseSemaphore
0x1800355e8  jmp     loc_1800356CA
0x1800355ed  xor     r9d, r9d; dwFileOffsetLow
0x1800355f0  mov     qword ptr [rsp+0D8h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x1800355f5  xor     r8d, r8d; dwFileOffsetHigh
0x1800355f8  mov     rcx, rax; hFileMappingObject
0x1800355fb  lea     edx, [r9+6]; dwDesiredAccess
0x1800355ff  call    cs:__imp_MapViewOfFile
0x180035605  cmp     cs:?g_hsemMemory@@3PEAXEA, rbx; void * g_hsemMemory
0x18003560c  mov     cs:?g_pszShare@@3PEADEA, rax; char * g_pszShare
0x180035613  jnz     short loc_180035636
0x180035615  lea     r9, aHhSemaphore; "hh_semaphore"
0x18003561c  mov     edx, 1; lInitialCount
0x180035621  xor     ecx, ecx; lpSemaphoreAttributes
0x180035623  mov     r8d, 270Fh; lMaximumCount
0x180035629  call    cs:__imp_CreateSemaphoreA
0x18003562f  mov     cs:?g_hsemMemory@@3PEAXEA, rax; void * g_hsemMemory
0x180035636  mov     rax, cs:hInstance
0x18003563d  lea     r8, Class; lpWindowName
0x180035644  mov     [rsp+0D8h+var_80], rbx; LPVOID
0x180035649  xor     r9d, r9d; dwStyle
0x18003564c  mov     [rsp+0D8h+var_88], rax; HINSTANCE
0x180035651  mov     rdx, rsi; lpClassName
0x180035654  mov     [rsp+0D8h+var_90], rbx; HMENU
0x180035659  xor     ecx, ecx; dwExStyle
0x18003565b  mov     [rsp+0D8h+var_98], rbx; HWND
0x180035660  mov     [rsp+0D8h+var_A0], ebx; int
0x180035664  mov     [rsp+0D8h+var_A8], ebx; int
0x180035668  mov     dword ptr [rsp+0D8h+lpName], ebx; int
0x18003566c  mov     [rsp+0D8h+dwMaximumSizeLow], ebx; int
0x180035670  call    IsolationAwareCreateWindowExA
0x180035675  xor     ecx, ecx; pvReserved
0x180035677  mov     cs:?g_hwndApi@@3PEAUHWND__@@EA, rax; HWND__ * g_hwndApi
0x18003567e  call    cs:__imp_OleInitialize
0x180035684  mov     rcx, cs:?g_hsemMemory@@3PEAXEA; hSemaphore
0x18003568b  xor     r8d, r8d; lpPreviousCount
0x18003568e  lea     edx, [r8+1]; lReleaseCount
0x180035692  call    cs:__imp_ReleaseSemaphore
0x180035698  mov     rcx, cs:?g_hwndApi@@3PEAUHWND__@@EA; HWND
0x18003569f  call    ?AWMessagePump@@YAXPEAUHWND__@@@Z; AWMessagePump(HWND__ *)
0x1800356a4  mov     rcx, cs:?g_hSharedMemory@@3PEAXEA; hObject
0x1800356ab  mov     cs:?g_hwndApi@@3PEAUHWND__@@EA, rbx; HWND__ * g_hwndApi
0x1800356b2  test    rcx, rcx
0x1800356b5  jz      short loc_1800356BD
0x1800356b7  call    cs:__imp_CloseHandle
0x1800356bd  call    cs:__imp_OleUninitialize
0x1800356c3  mov     cs:hObject, rbx
0x1800356ca  mov     rbx, [rsp+0D8h+arg_0]
0x1800356d2  xor     eax, eax
0x1800356d4  add     rsp, 0D0h
0x1800356db  pop     rsi
0x1800356dc  retn
```
