# ObjectThread(void *)

- ea: `0x18001e170`
- end: `0x18001e31e`
- name: `?ObjectThread@@YAKPEAX@Z`
- size: `430`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18001e170`
- `0x180060e60`
- `0x18015e010`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x18001e312`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001e312`
- `KERNEL32!SetEvent` at `0x18001e20a`
- `KERNEL32!SetEvent` at `0x18001e265`
- `KERNEL32!SetEvent` at `0x18001e20a`
- `KERNEL32!SetEvent` at `0x18001e265`
- `KERNEL32!LeaveCriticalSection` at `0x18001e2d6`
- `KERNEL32!LeaveCriticalSection` at `0x18001e2f1`
- `KERNEL32!LeaveCriticalSection` at `0x18001e2d6`
- `KERNEL32!LeaveCriticalSection` at `0x18001e2f1`
- `KERNEL32!EnterCriticalSection` at `0x18001e278`
- `KERNEL32!EnterCriticalSection` at `0x18001e2ba`
- `KERNEL32!EnterCriticalSection` at `0x18001e278`
- `KERNEL32!EnterCriticalSection` at `0x18001e2ba`
- `KERNEL32!GetProcAddress` at `0x18001e19b`
- `KERNEL32!GetProcAddress` at `0x18001e19b`
- `KERNEL32!GetModuleHandleW` at `0x18001e180`
- `KERNEL32!GetModuleHandleW` at `0x18001e180`
- `USER32!DispatchMessageW` at `0x18001e2a7`
- `USER32!DispatchMessageW` at `0x18001e2a7`
- `USER32!PeekMessageW` at `0x18001e1fb`
- `USER32!PeekMessageW` at `0x18001e1fb`
- `USER32!TranslateMessage` at `0x18001e296`
- `USER32!TranslateMessage` at `0x18001e296`
- `USER32!GetMessageW` at `0x18001e228`
- `USER32!GetMessageW` at `0x18001e228`
- `ole32!CoUninitialize` at `0x18001e2fd`
- `ole32!CoUninitialize` at `0x18001e2fd`
- `ole32!CoInitializeEx` at `0x18001e1c3`
- `ole32!CoInitializeEx` at `0x18001e1c3`

## string_xrefs

- `0x18001e179`: `ole32.dll`

## pseudocode

```c
void __fastcall __noreturn ObjectThread(PVOID Parameter)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  WPARAM wParam; // rdi
  struct CUnknown *InstanceInternal; // rax
  void *v6; // rcx
  struct CUnknown *v7; // rbx
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  ModuleHandleW = GetModuleHandleW(L"ole32.dll");
  if ( !ModuleHandleW
    || (ProcAddress = GetProcAddress(ModuleHandleW, "CoInitializeEx")) == 0
    || ((int (__fastcall *)(_QWORD, __int64))ProcAddress)(0, 4) < 0 )
  {
    CoInitializeEx(0, 2u);
  }
  memset(&Msg, 0, sizeof(Msg));
  PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, 0, 0, 1u);
  SetEvent(Parameter);
  while ( 1 )
  {
    GetMessageW(&Msg, 0, 0, 0);
    if ( Msg.hwnd || Msg.message != 1024 )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
      EnterCriticalSection(&g_csObjectThread);
    }
    else
    {
      wParam = Msg.wParam;
      InstanceInternal = CFilterGraph::CreateInstanceInternal(
                           *(struct IUnknown **)(Msg.wParam + 8),
                           (int *)(Msg.wParam + 16),
                           0);
      v6 = *(void **)wParam;
      v7 = InstanceInternal;
      *(_QWORD *)(wParam + 24) = InstanceInternal;
      SetEvent(v6);
      EnterCriticalSection(&g_csObjectThread);
      if ( !v7 )
        --g_cFGObjects;
    }
    if ( !g_cFGObjects )
    {
      g_dwObjectThreadId = 0;
      LeaveCriticalSection(&g_csObjectThread);
      CoUninitialize();
      FreeLibraryAndExitThread(g_hInst, 0);
    }
    LeaveCriticalSection(&g_csObjectThread);
  }
}

```

## disassembly

```asm
0x18001e170  push    rbx
0x18001e172  sub     rsp, 60h
0x18001e176  mov     rbx, rcx
0x18001e179  lea     rcx, aOle32Dll_0; "ole32.dll"
0x18001e180  call    cs:__imp_GetModuleHandleW
0x18001e187  nop     dword ptr [rax+rax+00h]
0x18001e18c  test    rax, rax
0x18001e18f  jz      short loc_18001E1BC
0x18001e191  lea     rdx, aCoinitializeex; "CoInitializeEx"
0x18001e198  mov     rcx, rax; hModule
0x18001e19b  call    cs:__imp_GetProcAddress
0x18001e1a2  nop     dword ptr [rax+rax+00h]
0x18001e1a7  test    rax, rax
0x18001e1aa  jz      short loc_18001E1BC
0x18001e1ac  mov     edx, 4
0x18001e1b1  xor     ecx, ecx
0x18001e1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1b8  test    eax, eax
0x18001e1ba  jns     short loc_18001E1CF
0x18001e1bc  mov     edx, 2; dwCoInit
0x18001e1c1  xor     ecx, ecx; pvReserved
0x18001e1c3  call    cs:__imp_CoInitializeEx
0x18001e1ca  nop     dword ptr [rax+rax+00h]
0x18001e1cf  xorps   xmm0, xmm0
0x18001e1d2  mov     [rsp+68h+wRemoveMsg], 1; wRemoveMsg
0x18001e1da  xor     r9d, r9d; wMsgFilterMax
0x18001e1dd  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001e1e2  xor     r8d, r8d; wMsgFilterMin
0x18001e1e5  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18001e1ec  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x18001e1f1  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x18001e1f6  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x18001e1fb  call    cs:__imp_PeekMessageW
0x18001e202  nop     dword ptr [rax+rax+00h]
0x18001e207  mov     rcx, rbx; hEvent
0x18001e20a  call    cs:__imp_SetEvent
0x18001e211  nop     dword ptr [rax+rax+00h]
0x18001e216  mov     [rsp+68h+arg_0], rdi
0x18001e21b  xor     r9d, r9d; wMsgFilterMax
0x18001e21e  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001e223  xor     r8d, r8d; wMsgFilterMin
0x18001e226  xor     edx, edx; hWnd
0x18001e228  call    cs:__imp_GetMessageW
0x18001e22f  nop     dword ptr [rax+rax+00h]
0x18001e234  cmp     [rsp+68h+Msg.hwnd], 0
0x18001e23a  jnz     short loc_18001E291
0x18001e23c  cmp     [rsp+68h+Msg.message], 400h
0x18001e244  jnz     short loc_18001E291
0x18001e246  mov     rdi, [rsp+68h+Msg.wParam]
0x18001e24b  xor     r8d, r8d; bool
0x18001e24e  mov     rcx, [rdi+8]; struct IUnknown *
0x18001e252  lea     rdx, [rdi+10h]; int *
0x18001e256  call    ?CreateInstanceInternal@CFilterGraph@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ_N@Z; CFilterGraph::CreateInstanceInternal(IUnknown *,long *,bool)
0x18001e25b  mov     rcx, [rdi]; hEvent
0x18001e25e  mov     rbx, rax
0x18001e261  mov     [rdi+18h], rax
0x18001e265  call    cs:__imp_SetEvent
0x18001e26c  nop     dword ptr [rax+rax+00h]
0x18001e271  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e278  call    cs:__imp_EnterCriticalSection
0x18001e27f  nop     dword ptr [rax+rax+00h]
0x18001e284  test    rbx, rbx
0x18001e287  jnz     short loc_18001E2C6
0x18001e289  dec     cs:?g_cFGObjects@@3KA; ulong g_cFGObjects
0x18001e28f  jmp     short loc_18001E2C6
0x18001e291  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001e296  call    cs:__imp_TranslateMessage
0x18001e29d  nop     dword ptr [rax+rax+00h]
0x18001e2a2  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001e2a7  call    cs:__imp_DispatchMessageW
0x18001e2ae  nop     dword ptr [rax+rax+00h]
0x18001e2b3  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e2ba  call    cs:__imp_EnterCriticalSection
0x18001e2c1  nop     dword ptr [rax+rax+00h]
0x18001e2c6  cmp     cs:?g_cFGObjects@@3KA, 0; ulong g_cFGObjects
0x18001e2cd  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e2d4  jz      short loc_18001E2E7
0x18001e2d6  call    cs:__imp_LeaveCriticalSection
0x18001e2dd  nop     dword ptr [rax+rax+00h]
0x18001e2e2  jmp     loc_18001E21B
0x18001e2e7  mov     cs:?g_dwObjectThreadId@@3KA, 0; ulong g_dwObjectThreadId
0x18001e2f1  call    cs:__imp_LeaveCriticalSection
0x18001e2f8  nop     dword ptr [rax+rax+00h]
0x18001e2fd  call    cs:__imp_CoUninitialize
0x18001e304  nop     dword ptr [rax+rax+00h]
0x18001e309  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001e310  xor     edx, edx; dwExitCode
0x18001e312  call    cs:__imp_FreeLibraryAndExitThread
```
