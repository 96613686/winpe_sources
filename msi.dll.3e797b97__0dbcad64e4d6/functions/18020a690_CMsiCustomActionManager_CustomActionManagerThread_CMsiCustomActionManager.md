# CMsiCustomActionManager::CustomActionManagerThread(CMsiCustomActionManager *)

- ea: `0x18020a690`
- end: `0x18020a90f`
- name: `?CustomActionManagerThread@CMsiCustomActionManager@@CAKPEAV1@@Z`
- size: `639`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180027634`
- `0x180133afc`
- `0x1801629b4`
- `0x18020a690`
- `0x180259830`
- `0x180266010`

## import_xrefs

- `KERNEL32!ExitThread` at `0x18020a8f3`
- `KERNEL32!ExitThread` at `0x18020a8f3`
- `KERNEL32!CloseHandle` at `0x18020a850`
- `KERNEL32!CloseHandle` at `0x18020a863`
- `KERNEL32!CloseHandle` at `0x18020a850`
- `KERNEL32!CloseHandle` at `0x18020a863`
- `KERNEL32!GlobalAlloc` at `0x18020a6c0`
- `KERNEL32!GlobalAlloc` at `0x18020a6c0`
- `KERNEL32!SetEvent` at `0x18020a704`
- `KERNEL32!SetEvent` at `0x18020a7cf`
- `KERNEL32!SetEvent` at `0x18020a704`
- `KERNEL32!SetEvent` at `0x18020a7cf`
- `KERNEL32!CreateEventW` at `0x18020a6ea`
- `KERNEL32!CreateEventW` at `0x18020a6ea`
- `USER32!MsgWaitForMultipleObjects` at `0x18020a73d`
- `USER32!MsgWaitForMultipleObjects` at `0x18020a73d`
- `USER32!PeekMessageW` at `0x18020a773`
- `USER32!PeekMessageW` at `0x18020a773`
- `USER32!TranslateMessage` at `0x18020a797`
- `USER32!TranslateMessage` at `0x18020a797`
- `USER32!DispatchMessageW` at `0x18020a7a8`
- `USER32!DispatchMessageW` at `0x18020a7a8`

## string_xrefs

- `0x18020a839`: `Timeout in CA Manager thread.`
- `0x18020a7ee`: `Error in CA Manager thread.`
- `0x18020a8de`: `Custom Action Manager thread ending.`

## pseudocode

```c
void __fastcall __noreturn CMsiCustomActionManager::CustomActionManagerThread(__int64 Parameter)
{
  int v2; // r15d
  CMsiRemoteAPI *v3; // rax
  DWORD v4; // eax
  const char *v5; // r9
  unsigned int v6; // [rsp+50h] [rbp-68h]
  void *v7; // [rsp+58h] [rbp-60h]
  struct tagMSG Msg; // [rsp+60h] [rbp-58h] BYREF
  HANDLE pHandles; // [rsp+C8h] [rbp+10h] BYREF

  v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD))OLE32::CoInitializeEx)(0, 0);
  v3 = (CMsiRemoteAPI *)GlobalAlloc(0x40u, 0x108u);
  if ( v3 )
    v3 = CMsiRemoteAPI::CMsiRemoteAPI(v3);
  *(_QWORD *)(Parameter + 200) = v3;
  *(_QWORD *)(Parameter + 264) = CreateEventW(0, 0, 0, 0);
  SetEvent(*(HANDLE *)(Parameter + 208));
  pHandles = *(HANDLE *)(Parameter + 264);
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v4 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
        if ( v4 != 1 )
          break;
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message == 18 )
            goto LABEL_18;
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      if ( v4 )
        break;
      CMsiCustomActionManager::CreateAndRegisterInterface(Parameter, *(_DWORD *)(Parameter + 260));
      SetEvent(*(HANDLE *)(Parameter + 208));
    }
    if ( v4 == -1 )
      break;
    if ( v4 == 258 )
    {
      if ( g_dmDiagnosticMode )
      {
        v5 = "Timeout in CA Manager thread.";
LABEL_14:
        DebugString(10, 0, 0, v5, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v6, v7);
      }
LABEL_18:
      CloseHandle(*(HANDLE *)(Parameter + 264));
      CloseHandle(*(HANDLE *)(Parameter + 208));
      *(_QWORD *)(Parameter + 264) = 0;
      *(_QWORD *)(Parameter + 208) = 0;
      *(_QWORD *)(Parameter + 200) = 0;
      if ( v2 >= 0 )
        OLE32::CoUninitialize();
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          "Custom Action Manager thread ending.",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          v6,
          v7);
      ExitThread(0);
    }
  }
  if ( g_dmDiagnosticMode )
  {
    v5 = "Error in CA Manager thread.";
    goto LABEL_14;
  }
  goto LABEL_18;
}

```

## disassembly

```asm
0x18020a690  push    rsi
0x18020a692  push    rdi
0x18020a693  push    r14
0x18020a695  push    r15
0x18020a697  sub     rsp, 98h
0x18020a69e  mov     rsi, rcx
0x18020a6a1  xor     r14d, r14d
0x18020a6a4  xor     edx, edx
0x18020a6a6  xor     ecx, ecx
0x18020a6a8  mov     rax, cs:?CoInitializeEx@OLE32@@3P6AJPEAXK@ZEA; long (*OLE32::CoInitializeEx)(void *,ulong)
0x18020a6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a6b4  mov     r15d, eax
0x18020a6b7  mov     edx, 108h; dwBytes
0x18020a6bc  lea     ecx, [r14+40h]; uFlags
0x18020a6c0  call    cs:__imp_GlobalAlloc
0x18020a6c7  nop     dword ptr [rax+rax+00h]
0x18020a6cc  test    rax, rax
0x18020a6cf  jz      short loc_18020A6D9
0x18020a6d1  mov     rcx, rax; this
0x18020a6d4  call    ??0CMsiRemoteAPI@@QEAA@XZ; CMsiRemoteAPI::CMsiRemoteAPI(void)
0x18020a6d9  mov     [rsi+0C8h], rax
0x18020a6e0  xor     r9d, r9d; lpName
0x18020a6e3  xor     r8d, r8d; bInitialState
0x18020a6e6  xor     edx, edx; bManualReset
0x18020a6e8  xor     ecx, ecx; lpEventAttributes
0x18020a6ea  call    cs:__imp_CreateEventW
0x18020a6f1  nop     dword ptr [rax+rax+00h]
0x18020a6f6  mov     [rsi+108h], rax
0x18020a6fd  mov     rcx, [rsi+0D0h]; hEvent
0x18020a704  call    cs:__imp_SetEvent
0x18020a70b  nop     dword ptr [rax+rax+00h]
0x18020a710  mov     rax, [rsi+108h]
0x18020a717  mov     [rsp+0B8h+pHandles], rax
0x18020a71f  mov     edi, 1
0x18020a724  mov     [rsp+0B8h+dwWakeMask], 1CFFh; dwWakeMask
0x18020a72c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18020a730  xor     r8d, r8d; fWaitAll
0x18020a733  lea     rdx, [rsp+0B8h+pHandles]; pHandles
0x18020a73b  mov     ecx, edi; nCount
0x18020a73d  call    cs:__imp_MsgWaitForMultipleObjects
0x18020a744  nop     dword ptr [rax+rax+00h]
0x18020a749  cmp     eax, edi
0x18020a74b  jnz     short loc_18020A7B6
0x18020a74d  xorps   xmm0, xmm0
0x18020a750  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x18020a755  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x18020a75a  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x18020a762  mov     [rsp+0B8h+dwWakeMask], edi; wRemoveMsg
0x18020a766  xor     r9d, r9d; wMsgFilterMax
0x18020a769  xor     r8d, r8d; wMsgFilterMin
0x18020a76c  xor     edx, edx; hWnd
0x18020a76e  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18020a773  call    cs:__imp_PeekMessageW
0x18020a77a  nop     dword ptr [rax+rax+00h]
0x18020a77f  test    eax, eax
0x18020a781  jz      loc_18020A8A3
0x18020a787  cmp     [rsp+0B8h+Msg.message], 12h
0x18020a78c  jz      loc_18020A842
0x18020a792  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18020a797  call    cs:__imp_TranslateMessage
0x18020a79e  nop     dword ptr [rax+rax+00h]
0x18020a7a3  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18020a7a8  call    cs:__imp_DispatchMessageW
0x18020a7af  nop     dword ptr [rax+rax+00h]
0x18020a7b4  jmp     short loc_18020A762
0x18020a7b6  test    eax, eax
0x18020a7b8  jnz     short loc_18020A7E0
0x18020a7ba  mov     edx, [rsi+104h]
0x18020a7c0  mov     rcx, rsi
0x18020a7c3  call    ?CreateAndRegisterInterface@CMsiCustomActionManager@@AEAAKW4icacCustomActionContext@@@Z; CMsiCustomActionManager::CreateAndRegisterInterface(icacCustomActionContext)
0x18020a7c8  mov     rcx, [rsi+0D0h]; hEvent
0x18020a7cf  call    cs:__imp_SetEvent
0x18020a7d6  nop     dword ptr [rax+rax+00h]
0x18020a7db  jmp     loc_18020A8A3
0x18020a7e0  cmp     eax, 0FFFFFFFFh
0x18020a7e3  jnz     short loc_18020A829
0x18020a7e5  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18020a7ec  jz      short loc_18020A842
0x18020a7ee  lea     r9, aErrorInCaManag; "Error in CA Manager thread."
0x18020a7f5  lea     rdi, aNull_0; "(NULL)"
0x18020a7fc  mov     [rsp+0B8h+var_70], rdi; char *
0x18020a801  mov     [rsp+0B8h+var_78], rdi; char *
0x18020a806  mov     [rsp+0B8h+var_80], rdi; char *
0x18020a80b  mov     [rsp+0B8h+var_88], rdi; char *
0x18020a810  mov     [rsp+0B8h+var_90], rdi; char *
0x18020a815  mov     qword ptr [rsp+0B8h+dwWakeMask], rdi; char *
0x18020a81a  xor     edx, edx; unsigned __int16
0x18020a81c  xor     r8d, r8d; int
0x18020a81f  lea     ecx, [rdx+0Ah]; int
0x18020a822  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18020a827  jmp     short loc_18020A849
0x18020a829  cmp     eax, 102h
0x18020a82e  jnz     short loc_18020A8A3
0x18020a830  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18020a837  jz      short loc_18020A842
0x18020a839  lea     r9, aTimeoutInCaMan; "Timeout in CA Manager thread."
0x18020a840  jmp     short loc_18020A7F5
0x18020a842  lea     rdi, aNull_0; "(NULL)"
0x18020a849  mov     rcx, [rsi+108h]; hObject
0x18020a850  call    cs:__imp_CloseHandle
0x18020a857  nop     dword ptr [rax+rax+00h]
0x18020a85c  mov     rcx, [rsi+0D0h]; hObject
0x18020a863  call    cs:__imp_CloseHandle
0x18020a86a  nop     dword ptr [rax+rax+00h]
0x18020a86f  mov     qword ptr [rsi+108h], 0
0x18020a87a  mov     qword ptr [rsi+0D0h], 0
0x18020a885  mov     qword ptr [rsi+0C8h], 0
0x18020a890  test    r15d, r15d
0x18020a893  js      short loc_18020A8A1
0x18020a895  mov     rax, cs:?CoUninitialize@OLE32@@3P6AXXZEA; void (*OLE32::CoUninitialize)(void)
0x18020a89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a8a1  jmp     short loc_18020A8B5
0x18020a8a3  jmp     loc_18020A724
0x18020a8a8  mov     r14d, 643h
0x18020a8ae  lea     rdi, aNull_0; "(NULL)"
0x18020a8b5  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18020a8bc  jz      short loc_18020A8F0
0x18020a8be  xor     edx, edx; unsigned __int16
0x18020a8c0  mov     [rsp+0B8h+var_70], rdi; char *
0x18020a8c5  mov     [rsp+0B8h+var_78], rdi; char *
0x18020a8ca  mov     [rsp+0B8h+var_80], rdi; char *
0x18020a8cf  mov     [rsp+0B8h+var_88], rdi; char *
0x18020a8d4  mov     [rsp+0B8h+var_90], rdi; char *
0x18020a8d9  mov     qword ptr [rsp+0B8h+dwWakeMask], rdi; char *
0x18020a8de  lea     r9, aCustomActionMa; "Custom Action Manager thread ending."
0x18020a8e5  xor     r8d, r8d; int
0x18020a8e8  lea     ecx, [rdx+9]; int
0x18020a8eb  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18020a8f0  mov     ecx, r14d; dwExitCode
0x18020a8f3  call    cs:__imp_ExitThread
0x18020a900  add     rsp, 98h
0x18020a907  pop     r15
0x18020a909  pop     r14
0x18020a90b  pop     rdi
0x18020a90c  pop     rsi
0x18020a90d  retn
0x18026592e  push    rbp
0x180265930  sub     rsp, 60h
0x180265934  mov     rbp, rdx
0x180265937  call    ?InstallEngineExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; InstallEngineExceptionFilter(_EXCEPTION_POINTERS *)
0x18026593c  nop
0x18026593d  add     rsp, 60h
0x180265941  pop     rbp
0x180265942  retn
```
