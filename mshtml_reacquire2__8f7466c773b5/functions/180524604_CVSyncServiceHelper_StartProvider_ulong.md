# CVSyncServiceHelper::StartProvider(ulong)

- ea: `0x180524604`
- end: `0x18052491e`
- name: `?StartProvider@CVSyncServiceHelper@@AEAAJK@Z`
- size: `794`
- prototype: `__int64 __fastcall(CVSyncServiceHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x180524570`

## callees

- `0x180524604`
- `0x180525000`
- `0x1807c21cc`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1805246a9`
- `KERNEL32!GetCurrentProcessId` at `0x1805246a9`
- `KERNEL32!MapViewOfFile` at `0x1805248cb`
- `KERNEL32!MapViewOfFile` at `0x1805248cb`
- `KERNEL32!CreateFileMappingW` at `0x1805247d4`
- `KERNEL32!CreateFileMappingW` at `0x1805247d4`
- `KERNEL32!UnmapViewOfFile` at `0x1805248e3`
- `KERNEL32!UnmapViewOfFile` at `0x1805248e3`
- `KERNEL32!GetCurrentThreadId` at `0x1805246b9`
- `KERNEL32!GetCurrentThreadId` at `0x1805246b9`
- `KERNEL32!SetEvent` at `0x18052470c`
- `KERNEL32!SetEvent` at `0x18052470c`
- `KERNEL32!CreateEventW` at `0x180524809`
- `KERNEL32!CreateEventW` at `0x180524809`
- `KERNEL32!CloseHandle` at `0x180524897`
- `KERNEL32!CloseHandle` at `0x1805248a8`
- `KERNEL32!CloseHandle` at `0x180524897`
- `KERNEL32!CloseHandle` at `0x1805248a8`
- `USER32!RegisterClassW` at `0x180524799`
- `USER32!RegisterClassW` at `0x180524799`
- `USER32!SetWindowLongPtrW` at `0x180524886`
- `USER32!SetWindowLongPtrW` at `0x180524886`
- `USER32!CreateWindowExW` at `0x180524862`
- `USER32!CreateWindowExW` at `0x180524862`

## pseudocode

```c
__int64 __fastcall CVSyncServiceHelper::StartProvider(CVSyncServiceHelper *this, unsigned int a2)
{
  ATOM v4; // ax
  DWORD dwMaximumSizeLow; // eax
  void *v6; // rbx
  SIZE_T v7; // rsi
  __int64 v8; // rsi
  int v9; // ebx
  BOOL v10; // eax
  unsigned int v11; // ecx
  unsigned __int64 QPCInUs; // rax
  HANDLE FileMappingW; // rax
  void *v15; // rcx
  HANDLE EventW; // rax
  void *v17; // rcx
  HANDLE v18; // rbx
  HWND Window; // rax
  _DWORD *v20; // rax
  const void *v21; // rcx
  _DWORD *v22; // rbx
  _DWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  WNDCLASSW WndClass; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v27[80]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = *((_WORD *)this + 16);
  if ( !v4 )
  {
    QPCInUs = CVSyncServiceHelper::GetQPCInUs();
    StringCbPrintfW(v27, 0xA0u, L"VSyncHelper-%p-%I64x", this, QPCInUs);
    memset_0(&WndClass, 0, sizeof(WndClass));
    WndClass.lpfnWndProc = (WNDPROC)CVSyncServiceHelper::MsgWindowProc;
    WndClass.lpszClassName = v27;
    v4 = RegisterClassW(&WndClass);
    *((_WORD *)this + 16) = v4;
    if ( !v4 )
      return (unsigned int)-2147418113;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    Window = CreateWindowExW(0, (LPCWSTR)v4, 0, 0, 0, 0, 0, 0, 0, 0, 0, this);
    *((_QWORD *)this + 3) = Window;
    if ( !Window )
      return (unsigned int)-2147418113;
    SetWindowLongPtrW(Window, -21, (LONG_PTR)this);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v17 = (void *)*((_QWORD *)this + 5);
    v18 = EventW;
    if ( v17 )
      CloseHandle(v17);
    *((_QWORD *)this + 5) = v18;
    if ( !v18 )
      return (unsigned int)-2147418113;
  }
  dwMaximumSizeLow = (*(__int64 (__fastcall **)(CVSyncServiceHelper *))(*(_QWORD *)this + 80LL))(this);
  v6 = (void *)*((_QWORD *)this + 6);
  v7 = dwMaximumSizeLow;
  if ( !v6 )
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, dwMaximumSizeLow, 0);
    v15 = (void *)*((_QWORD *)this + 6);
    v6 = FileMappingW;
    if ( v15 )
      CloseHandle(v15);
    *((_QWORD *)this + 6) = v6;
    if ( !v6 )
      return (unsigned int)-2147418113;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    v20 = MapViewOfFile(v6, 6u, 0, 0, v7);
    v21 = (const void *)*((_QWORD *)this + 7);
    v22 = v20;
    if ( v21 )
      UnmapViewOfFile(v21);
    *((_QWORD *)this + 7) = v22;
    if ( !v22 )
      return (unsigned int)-2147418113;
    memset_0(v22, 0, v7);
    *v22 = -838796627;
    v22[1] = 1;
    v22[2] = v7;
  }
  v8 = *((_QWORD *)this + 7);
  v24 = 0;
  v25 = 0;
  v23[0] = GetCurrentProcessId();
  v23[1] = GetCurrentThreadId();
  *(_QWORD *)&v24 = *((_QWORD *)this + 6);
  *((_QWORD *)&v24 + 1) = *((_QWORD *)this + 5);
  v25 = *((_QWORD *)this + 3);
  v9 = (*(__int64 (__fastcall **)(CVSyncServiceHelper *, _DWORD *, _QWORD))(*(_QWORD *)this + 64LL))(this, v23, a2);
  if ( v9 >= 0 )
  {
    *(_DWORD *)(v8 + 12) = 1;
    v10 = SetEvent(*((HANDLE *)this + 5));
    v11 = v9;
    if ( !v10 )
      return (unsigned int)-2147418113;
    return v11;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180524604  mov     rax, rsp
0x180524607  mov     [rax+18h], rbx
0x18052460b  mov     [rax+20h], rsi
0x18052460f  mov     [rax+10h], edx
0x180524612  mov     [rax+8], rcx
0x180524616  push    rbp
0x180524617  push    rdi
0x180524618  push    r12
0x18052461a  push    r14
0x18052461c  push    r15
0x18052461e  lea     rbp, [rsp-80h]
0x180524623  sub     rsp, 180h
0x18052462a  mov     rax, cs:__security_cookie
0x180524631  xor     rax, rsp
0x180524634  mov     [rbp+0A0h+var_30], rax
0x180524638  mov     rdi, [rbp+0A0h+dwNewLong]
0x18052463f  xor     r12d, r12d
0x180524642  mov     r15d, [rbp+0A0h+arg_8]
0x180524649  movzx   eax, word ptr [rdi+20h]
0x18052464d  test    ax, ax
0x180524650  jz      loc_180524751
0x180524656  cmp     [rdi+18h], r12
0x18052465a  jz      loc_18052482F
0x180524660  cmp     [rdi+28h], r12
0x180524664  jz      loc_1805247FF
0x18052466a  mov     rax, [rdi]
0x18052466d  mov     rcx, rdi
0x180524670  mov     rax, [rax+50h]
0x180524674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180524679  mov     rbx, [rdi+30h]
0x18052467d  mov     esi, eax
0x18052467f  test    rbx, rbx
0x180524682  jz      loc_1805247BC
0x180524688  cmp     [rdi+38h], r12
0x18052468c  jz      loc_1805248B9
0x180524692  mov     rsi, [rdi+38h]
0x180524696  xorps   xmm0, xmm0
0x180524699  movdqu  [rsp+1A0h+var_138], xmm0
0x18052469f  mov     [rsp+1A0h+var_140], r12
0x1805246a4  mov     [rsp+1A0h+var_128], r12
0x1805246a9  call    cs:__imp_GetCurrentProcessId
0x1805246b0  nop     dword ptr [rax+rax+00h]
0x1805246b5  mov     dword ptr [rsp+1A0h+var_140], eax
0x1805246b9  call    cs:__imp_GetCurrentThreadId
0x1805246c0  nop     dword ptr [rax+rax+00h]
0x1805246c5  mov     dword ptr [rsp+1A0h+var_140+4], eax
0x1805246c9  mov     r8d, r15d
0x1805246cc  mov     rax, [rdi+30h]
0x1805246d0  lea     rdx, [rsp+1A0h+var_140]
0x1805246d5  mov     qword ptr [rsp+1A0h+var_138], rax
0x1805246da  mov     rcx, rdi
0x1805246dd  mov     rax, [rdi+28h]
0x1805246e1  mov     qword ptr [rsp+1A0h+var_138+8], rax
0x1805246e6  mov     rax, [rdi+18h]
0x1805246ea  mov     [rsp+1A0h+var_128], rax
0x1805246ef  mov     rax, [rdi]
0x1805246f2  mov     rax, [rax+40h]
0x1805246f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805246fb  mov     ebx, eax
0x1805246fd  test    eax, eax
0x1805246ff  js      short loc_180524726
0x180524701  mov     dword ptr [rsi+0Ch], 1
0x180524708  mov     rcx, [rdi+28h]; hEvent
0x18052470c  call    cs:__imp_SetEvent
0x180524713  nop     dword ptr [rax+rax+00h]
0x180524718  mov     ecx, ebx
0x18052471a  mov     ebx, 8000FFFFh
0x18052471f  test    eax, eax
0x180524721  cmovz   ecx, ebx
0x180524724  mov     ebx, ecx
0x180524726  mov     eax, ebx
0x180524728  mov     rcx, [rbp+0A0h+var_30]
0x18052472c  xor     rcx, rsp; StackCookie
0x18052472f  call    __security_check_cookie
0x180524734  lea     r11, [rsp+1A0h+var_20]
0x18052473c  mov     rbx, [r11+40h]
0x180524740  mov     rsi, [r11+48h]
0x180524744  mov     rsp, r11
0x180524747  pop     r15
0x180524749  pop     r14
0x18052474b  pop     r12
0x18052474d  pop     rdi
0x18052474e  pop     rbp
0x18052474f  retn
0x180524751  call    ?GetQPCInUs@CVSyncServiceHelper@@SA_KXZ; CVSyncServiceHelper::GetQPCInUs(void)
0x180524756  mov     r9, rdi
0x180524759  mov     qword ptr [rsp+1A0h+dwMaximumSizeLow], rax
0x18052475e  lea     r8, aVsynchelperPI6; "VSyncHelper-%p-%I64x"
0x180524765  mov     edx, 0A0h; unsigned __int64
0x18052476a  lea     rcx, [rbp+0A0h+var_D0]; unsigned __int16 *
0x18052476e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180524773  xor     edx, edx; Val
0x180524775  lea     rcx, [rbp+0A0h+WndClass]; void *
0x180524779  lea     r8d, [rdx+48h]; Size
0x18052477d  call    memset_0
0x180524782  lea     rax, ?MsgWindowProc@CVSyncServiceHelper@@CA_JPEAUHWND__@@I_K_J@Z; CVSyncServiceHelper::MsgWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180524789  mov     [rbp+0A0h+WndClass.lpfnWndProc], rax
0x18052478d  lea     rcx, [rbp+0A0h+WndClass]; lpWndClass
0x180524791  lea     rax, [rbp+0A0h+var_D0]
0x180524795  mov     [rbp+0A0h+WndClass.lpszClassName], rax
0x180524799  call    cs:__imp_RegisterClassW
0x1805247a0  nop     dword ptr [rax+rax+00h]
0x1805247a5  mov     [rdi+20h], ax
0x1805247a9  test    ax, ax
0x1805247ac  jnz     loc_180524656
0x1805247b2  mov     ebx, 8000FFFFh
0x1805247b7  jmp     loc_180524726
0x1805247bc  mov     [rsp+1A0h+lpName], r12; lpName
0x1805247c1  xor     r9d, r9d; dwMaximumSizeHigh
0x1805247c4  xor     edx, edx; lpFileMappingAttributes
0x1805247c6  mov     [rsp+1A0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x1805247ca  mov     r8d, 8000004h; flProtect
0x1805247d0  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1805247d4  call    cs:__imp_CreateFileMappingW
0x1805247db  nop     dword ptr [rax+rax+00h]
0x1805247e0  mov     rcx, [rdi+30h]; hObject
0x1805247e4  mov     rbx, rax
0x1805247e7  test    rcx, rcx
0x1805247ea  jnz     loc_1805248A8
0x1805247f0  mov     [rdi+30h], rbx
0x1805247f4  test    rbx, rbx
0x1805247f7  jnz     loc_180524688
0x1805247fd  jmp     short loc_1805247B2
0x1805247ff  xor     r9d, r9d; lpName
0x180524802  xor     r8d, r8d; bInitialState
0x180524805  xor     edx, edx; bManualReset
0x180524807  xor     ecx, ecx; lpEventAttributes
0x180524809  call    cs:__imp_CreateEventW
0x180524810  nop     dword ptr [rax+rax+00h]
0x180524815  mov     rcx, [rdi+28h]; hObject
0x180524819  mov     rbx, rax
0x18052481c  test    rcx, rcx
0x18052481f  jnz     short loc_180524897
0x180524821  mov     [rdi+28h], rbx
0x180524825  test    rbx, rbx
0x180524828  jz      short loc_1805247B2
0x18052482a  jmp     loc_18052466A
0x18052482f  mov     [rsp+1A0h+lpParam], rdi; lpParam
0x180524834  xor     r9d, r9d; dwStyle
0x180524837  mov     [rsp+1A0h+hInstance], r12; hInstance
0x18052483c  xor     r8d, r8d; lpWindowName
0x18052483f  mov     [rsp+1A0h+hMenu], r12; hMenu
0x180524844  xor     ecx, ecx; dwExStyle
0x180524846  mov     [rsp+1A0h+hWndParent], r12; hWndParent
0x18052484b  mov     [rsp+1A0h+nHeight], r12d; nHeight
0x180524850  mov     [rsp+1A0h+nWidth], r12d; nWidth
0x180524855  mov     dword ptr [rsp+1A0h+lpName], r12d; Y
0x18052485a  movzx   edx, ax; lpClassName
0x18052485d  mov     [rsp+1A0h+dwMaximumSizeLow], r12d; X
0x180524862  call    cs:__imp_CreateWindowExW
0x180524869  nop     dword ptr [rax+rax+00h]
0x18052486e  mov     [rdi+18h], rax
0x180524872  test    rax, rax
0x180524875  jz      loc_1805247B2
0x18052487b  mov     r8, rdi; dwNewLong
0x18052487e  mov     edx, 0FFFFFFEBh; nIndex
0x180524883  mov     rcx, rax; hWnd
0x180524886  call    cs:__imp_SetWindowLongPtrW
0x18052488d  nop     dword ptr [rax+rax+00h]
0x180524892  jmp     loc_180524660
0x180524897  call    cs:__imp_CloseHandle
0x18052489e  nop     dword ptr [rax+rax+00h]
0x1805248a3  jmp     loc_180524821
0x1805248a8  call    cs:__imp_CloseHandle
0x1805248af  nop     dword ptr [rax+rax+00h]
0x1805248b4  jmp     loc_1805247F0
0x1805248b9  xor     r9d, r9d; dwFileOffsetLow
0x1805248bc  mov     qword ptr [rsp+1A0h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x1805248c1  xor     r8d, r8d; dwFileOffsetHigh
0x1805248c4  mov     rcx, rbx; hFileMappingObject
0x1805248c7  lea     edx, [r9+6]; dwDesiredAccess
0x1805248cb  call    cs:__imp_MapViewOfFile
0x1805248d2  nop     dword ptr [rax+rax+00h]
0x1805248d7  mov     rcx, [rdi+38h]; lpBaseAddress
0x1805248db  mov     rbx, rax
0x1805248de  test    rcx, rcx
0x1805248e1  jz      short loc_1805248EF
0x1805248e3  call    cs:__imp_UnmapViewOfFile
0x1805248ea  nop     dword ptr [rax+rax+00h]
0x1805248ef  mov     [rdi+38h], rbx
0x1805248f3  test    rbx, rbx
0x1805248f6  jz      loc_1805247B2
0x1805248fc  mov     r8, rsi; Size
0x1805248ff  xor     edx, edx; Val
0x180524901  mov     rcx, rbx; void *
0x180524904  call    memset_0
0x180524909  mov     dword ptr [rbx], 0CE00FAADh
0x18052490f  mov     dword ptr [rbx+4], 1
0x180524916  mov     [rbx+8], esi
0x180524919  jmp     loc_180524692
```
