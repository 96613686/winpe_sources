# CTray::MainThreadProc(void *)

- ea: `0x14011d370`
- end: `0x14011d471`
- name: `?MainThreadProc@CTray@@KAKPEAX@Z`
- size: `257`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000d890`
- `0x14001b2bc`
- `0x14001b4b4`
- `0x140061110`
- `0x140084000`
- `0x1401040e0`
- `0x14011d370`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14011d3de`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14011d3de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14011d3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14011d3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14011d388`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14011d388`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14011d456`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14011d456`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x14011d396`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x14011d433`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x14011d396`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x14011d433`
- `USER32!ChangeWindowMessageFilterEx` at `0x14011d3f4`
- `USER32!ChangeWindowMessageFilterEx` at `0x14011d3f4`
- `USER32!LoadAcceleratorsW` at `0x14011d3b3`
- `USER32!LoadAcceleratorsW` at `0x14011d3b3`
- `ole32!OleUninitialize` at `0x14011d447`
- `ole32!OleUninitialize` at `0x14011d447`

## pseudocode

```c
__int64 __fastcall CTray::MainThreadProc(PVOID Parameter)
{
  HANDLE CurrentThread; // rax
  __int64 v3; // r8
  __int64 v4; // rcx

  dword_1402527B8 = GetCurrentThreadId();
  SHChangeNotifyRegisterThread(SCNRT_ENABLE);
  if ( *((_QWORD *)Parameter + 1) )
  {
    *((_QWORD *)Parameter + 30) = LoadAcceleratorsW(g_hinstCabinet, (LPCWSTR)0xFB);
    CTray::_RegisterGlobalHotkeys((CTray *)Parameter);
    CTray::_RegisterTouchpadActions((CTray *)Parameter);
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 1);
    ChangeWindowMessageFilterEx(*((HWND *)Parameter + 1), 0x4F2u, 1u, 0);
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        &Explorer_StartMenu_Ready_Info,
        v3,
        1);
    CTray::_MessageLoop((CTray *)Parameter);
  }
  SHChangeNotifyRegisterThread(SCNRT_DISABLE);
  ClassFactory_Stop();
  if ( *((int *)Parameter + 264) >= 0 )
    OleUninitialize();
  if ( *((int *)Parameter + 265) >= 0 )
    RoUninitialize(v4);
  return 0;
}

```

## disassembly

```asm
0x14011d370  push    rbx
0x14011d372  sub     rsp, 50h
0x14011d376  mov     rax, cs:__security_cookie
0x14011d37d  xor     rax, rsp
0x14011d380  mov     [rsp+58h+var_18], rax
0x14011d385  mov     rbx, rcx
0x14011d388  call    cs:__imp_GetCurrentThreadId
0x14011d38e  xor     ecx, ecx; status
0x14011d390  mov     cs:dword_1402527B8, eax
0x14011d396  call    cs:__imp_SHChangeNotifyRegisterThread
0x14011d39c  cmp     qword ptr [rbx+8], 0
0x14011d3a1  jz      loc_14011D42E
0x14011d3a7  mov     rcx, cs:g_hinstCabinet; hInstance
0x14011d3ae  mov     edx, 0FBh; lpTableName
0x14011d3b3  call    cs:__imp_LoadAcceleratorsW
0x14011d3b9  mov     rcx, rbx; this
0x14011d3bc  mov     [rbx+0F0h], rax
0x14011d3c3  call    ?_RegisterGlobalHotkeys@CTray@@IEAAXXZ; CTray::_RegisterGlobalHotkeys(void)
0x14011d3c8  mov     rcx, rbx; this
0x14011d3cb  call    ?_RegisterTouchpadActions@CTray@@IEAAXXZ; CTray::_RegisterTouchpadActions(void)
0x14011d3d0  call    cs:__imp_GetCurrentThread
0x14011d3d6  mov     rcx, rax; hThread
0x14011d3d9  mov     edx, 1; nPriority
0x14011d3de  call    cs:__imp_SetThreadPriority
0x14011d3e4  mov     rcx, [rbx+8]; hwnd
0x14011d3e8  xor     r9d, r9d; pChangeFilterStruct
0x14011d3eb  mov     edx, 4F2h; message
0x14011d3f0  lea     r8d, [r9+1]; action
0x14011d3f4  call    cs:__imp_ChangeWindowMessageFilterEx
0x14011d3fa  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x14011d401  jz      short loc_14011D426
0x14011d403  lea     rax, [rsp+58h+var_28]
0x14011d408  mov     r9d, 1
0x14011d40e  lea     rdx, Explorer_StartMenu_Ready_Info
0x14011d415  mov     [rsp+58h+var_38], rax
0x14011d41a  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14011d421  call    McGenEventWrite_EventWriteTransfer
0x14011d426  mov     rcx, rbx; this
0x14011d429  call    ?_MessageLoop@CTray@@IEAAXXZ; CTray::_MessageLoop(void)
0x14011d42e  mov     ecx, 1; status
0x14011d433  call    cs:__imp_SHChangeNotifyRegisterThread
0x14011d439  call    ?ClassFactory_Stop@@YAXXZ; ClassFactory_Stop(void)
0x14011d43e  cmp     dword ptr [rbx+420h], 0
0x14011d445  jl      short loc_14011D44D
0x14011d447  call    cs:__imp_OleUninitialize
0x14011d44d  cmp     dword ptr [rbx+424h], 0
0x14011d454  jl      short loc_14011D45C
0x14011d456  call    cs:__imp_RoUninitialize
0x14011d45c  xor     eax, eax
0x14011d45e  mov     rcx, [rsp+58h+var_18]
0x14011d463  xor     rcx, rsp; StackCookie
0x14011d466  call    __security_check_cookie
0x14011d46b  add     rsp, 50h
0x14011d46f  pop     rbx
0x14011d470  retn
```
