# CMsiCustomActionManager::CustomActionManagerThread(CMsiCustomActionManager *)

- ea: `0x180201420`
- end: `0x18020165c`
- name: `?CustomActionManagerThread@CMsiCustomActionManager@@CAKPEAV1@@Z`
- size: `572`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000a150`
- `0x18012dd10`
- `0x18015cd14`
- `0x180201420`
- `0x18024f4dc`
- `0x18025c010`

## import_xrefs

- `KERNEL32!ExitThread` at `0x180201647`
- `KERNEL32!ExitThread` at `0x180201647`
- `KERNEL32!CloseHandle` at `0x1802015b0`
- `KERNEL32!CloseHandle` at `0x1802015bd`
- `KERNEL32!CloseHandle` at `0x1802015b0`
- `KERNEL32!CloseHandle` at `0x1802015bd`
- `KERNEL32!GlobalAlloc` at `0x180201450`
- `KERNEL32!GlobalAlloc` at `0x180201450`
- `KERNEL32!SetEvent` at `0x180201488`
- `KERNEL32!SetEvent` at `0x180201535`
- `KERNEL32!SetEvent` at `0x180201488`
- `KERNEL32!SetEvent` at `0x180201535`
- `KERNEL32!CreateEventW` at `0x180201474`
- `KERNEL32!CreateEventW` at `0x180201474`
- `USER32!MsgWaitForMultipleObjects` at `0x1802014bb`
- `USER32!MsgWaitForMultipleObjects` at `0x1802014bb`
- `USER32!PeekMessageW` at `0x1802014eb`
- `USER32!PeekMessageW` at `0x1802014eb`
- `USER32!TranslateMessage` at `0x180201509`
- `USER32!TranslateMessage` at `0x180201509`
- `USER32!DispatchMessageW` at `0x180201514`
- `USER32!DispatchMessageW` at `0x180201514`

## string_xrefs

- `0x18020154e`: `Error in CA Manager thread.`
- `0x180201632`: `Custom Action Manager thread ending.`
- `0x180201599`: `Timeout in CA Manager thread.`

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
0x180201420  push    rsi
0x180201422  push    rdi
0x180201423  push    r14
0x180201425  push    r15
0x180201427  sub     rsp, 98h
0x18020142e  mov     rsi, rcx
0x180201431  xor     r14d, r14d
0x180201434  xor     edx, edx
0x180201436  xor     ecx, ecx
0x180201438  mov     rax, cs:?CoInitializeEx@OLE32@@3P6AJPEAXK@ZEA; long (*OLE32::CoInitializeEx)(void *,ulong)
0x18020143f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201444  mov     r15d, eax
0x180201447  mov     edx, 108h; dwBytes
0x18020144c  lea     ecx, [r14+40h]; uFlags
0x180201450  call    cs:__imp_GlobalAlloc
0x180201456  test    rax, rax
0x180201459  jz      short loc_180201463
0x18020145b  mov     rcx, rax; this
0x18020145e  call    ??0CMsiRemoteAPI@@QEAA@XZ; CMsiRemoteAPI::CMsiRemoteAPI(void)
0x180201463  mov     [rsi+0C8h], rax
0x18020146a  xor     r9d, r9d; lpName
0x18020146d  xor     r8d, r8d; bInitialState
0x180201470  xor     edx, edx; bManualReset
0x180201472  xor     ecx, ecx; lpEventAttributes
0x180201474  call    cs:__imp_CreateEventW
0x18020147a  mov     [rsi+108h], rax
0x180201481  mov     rcx, [rsi+0D0h]; hEvent
0x180201488  call    cs:__imp_SetEvent
0x18020148e  mov     rax, [rsi+108h]
0x180201495  mov     [rsp+0B8h+pHandles], rax
0x18020149d  mov     edi, 1
0x1802014a2  mov     [rsp+0B8h+dwWakeMask], 1CFFh; dwWakeMask
0x1802014aa  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1802014ae  xor     r8d, r8d; fWaitAll
0x1802014b1  lea     rdx, [rsp+0B8h+pHandles]; pHandles
0x1802014b9  mov     ecx, edi; nCount
0x1802014bb  call    cs:__imp_MsgWaitForMultipleObjects
0x1802014c1  cmp     eax, edi
0x1802014c3  jnz     short loc_18020151C
0x1802014c5  xorps   xmm0, xmm0
0x1802014c8  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x1802014cd  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x1802014d2  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x1802014da  mov     [rsp+0B8h+dwWakeMask], edi; wRemoveMsg
0x1802014de  xor     r9d, r9d; wMsgFilterMax
0x1802014e1  xor     r8d, r8d; wMsgFilterMin
0x1802014e4  xor     edx, edx; hWnd
0x1802014e6  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x1802014eb  call    cs:__imp_PeekMessageW
0x1802014f1  test    eax, eax
0x1802014f3  jz      loc_1802015F7
0x1802014f9  cmp     [rsp+0B8h+Msg.message], 12h
0x1802014fe  jz      loc_1802015A2
0x180201504  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180201509  call    cs:__imp_TranslateMessage
0x18020150f  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180201514  call    cs:__imp_DispatchMessageW
0x18020151a  jmp     short loc_1802014DA
0x18020151c  test    eax, eax
0x18020151e  jnz     short loc_180201540
0x180201520  mov     edx, [rsi+104h]
0x180201526  mov     rcx, rsi
0x180201529  call    ?CreateAndRegisterInterface@CMsiCustomActionManager@@AEAAKW4icacCustomActionContext@@@Z; CMsiCustomActionManager::CreateAndRegisterInterface(icacCustomActionContext)
0x18020152e  mov     rcx, [rsi+0D0h]; hEvent
0x180201535  call    cs:__imp_SetEvent
0x18020153b  jmp     loc_1802015F7
0x180201540  cmp     eax, 0FFFFFFFFh
0x180201543  jnz     short loc_180201589
0x180201545  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18020154c  jz      short loc_1802015A2
0x18020154e  lea     r9, aErrorInCaManag; "Error in CA Manager thread."
0x180201555  lea     rdi, aNull_0; "(NULL)"
0x18020155c  mov     [rsp+0B8h+var_70], rdi; char *
0x180201561  mov     [rsp+0B8h+var_78], rdi; char *
0x180201566  mov     [rsp+0B8h+var_80], rdi; char *
0x18020156b  mov     [rsp+0B8h+var_88], rdi; char *
0x180201570  mov     [rsp+0B8h+var_90], rdi; char *
0x180201575  mov     qword ptr [rsp+0B8h+dwWakeMask], rdi; char *
0x18020157a  xor     edx, edx; unsigned __int16
0x18020157c  xor     r8d, r8d; int
0x18020157f  lea     ecx, [rdx+0Ah]; int
0x180201582  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180201587  jmp     short loc_1802015A9
0x180201589  cmp     eax, 102h
0x18020158e  jnz     short loc_1802015F7
0x180201590  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180201597  jz      short loc_1802015A2
0x180201599  lea     r9, aTimeoutInCaMan; "Timeout in CA Manager thread."
0x1802015a0  jmp     short loc_180201555
0x1802015a2  lea     rdi, aNull_0; "(NULL)"
0x1802015a9  mov     rcx, [rsi+108h]; hObject
0x1802015b0  call    cs:__imp_CloseHandle
0x1802015b6  mov     rcx, [rsi+0D0h]; hObject
0x1802015bd  call    cs:__imp_CloseHandle
0x1802015c3  mov     qword ptr [rsi+108h], 0
0x1802015ce  mov     qword ptr [rsi+0D0h], 0
0x1802015d9  mov     qword ptr [rsi+0C8h], 0
0x1802015e4  test    r15d, r15d
0x1802015e7  js      short loc_1802015F5
0x1802015e9  mov     rax, cs:?CoUninitialize@OLE32@@3P6AXXZEA; void (*OLE32::CoUninitialize)(void)
0x1802015f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802015f5  jmp     short loc_180201609
0x1802015f7  jmp     loc_1802014A2
0x1802015fc  mov     r14d, 643h
0x180201602  lea     rdi, aNull_0; "(NULL)"
0x180201609  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180201610  jz      short loc_180201644
0x180201612  xor     edx, edx; unsigned __int16
0x180201614  mov     [rsp+0B8h+var_70], rdi; char *
0x180201619  mov     [rsp+0B8h+var_78], rdi; char *
0x18020161e  mov     [rsp+0B8h+var_80], rdi; char *
0x180201623  mov     [rsp+0B8h+var_88], rdi; char *
0x180201628  mov     [rsp+0B8h+var_90], rdi; char *
0x18020162d  mov     qword ptr [rsp+0B8h+dwWakeMask], rdi; char *
0x180201632  lea     r9, aCustomActionMa; "Custom Action Manager thread ending."
0x180201639  xor     r8d, r8d; int
0x18020163c  lea     ecx, [rdx+9]; int
0x18020163f  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180201644  mov     ecx, r14d; dwExitCode
0x180201647  call    cs:__imp_ExitThread
0x18020164e  add     rsp, 98h
0x180201655  pop     r15
0x180201657  pop     r14
0x180201659  pop     rdi
0x18020165a  pop     rsi
0x18020165b  retn
0x18025b22e  push    rbp
0x18025b230  sub     rsp, 60h
0x18025b234  mov     rbp, rdx
0x18025b237  call    ?InstallEngineExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; InstallEngineExceptionFilter(_EXCEPTION_POINTERS *)
0x18025b23c  nop
0x18025b23d  add     rsp, 60h
0x18025b241  pop     rbp
0x18025b242  retn
```
