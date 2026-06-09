# ShowSessionTooLongDialog(HWND__ *,int *,long *)

- ea: `0x14002c714`
- end: `0x14002c8de`
- name: `?ShowSessionTooLongDialog@@YAJPEAUHWND__@@PEAHPEAJ@Z`
- size: `458`
- prototype: `__int64 __fastcall(HWND, int *pnButton, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140022c68`

## callees

- `0x140002463`
- `0x140028a2c`
- `0x14002c714`
- `0x140034ce4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14002c75b`
- `KERNEL32!CreateEventW` at `0x14002c75b`
- `KERNEL32!CloseHandle` at `0x14002c8a0`
- `KERNEL32!CloseHandle` at `0x14002c8a0`
- `KERNEL32!GetLastError` at `0x14002c780`
- `KERNEL32!GetLastError` at `0x14002c794`
- `KERNEL32!GetLastError` at `0x14002c780`
- `KERNEL32!GetLastError` at `0x14002c794`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c84c`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c84c`

## string_xrefs

- `0x14002c86f`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall ShowSessionTooLongDialog(HWND a1, int *pnButton, int *a3)
{
  HANDLE EventW; // rax
  CEventLogger *v7; // rcx
  CEventLogger *v8; // rcx
  signed int LastError; // eax
  int v10; // ebx
  HRESULT v11; // eax
  CEventLogger *v12; // rcx
  void *v13; // rcx
  int pnRadioButton[4]; // [rsp+30h] [rbp-89h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-79h] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+138h] [rbp+7Fh] BYREF

  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pfVerificationFlagChecked = 0;
  pnRadioButton[0] = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v7 = _AtlModule;
  *((_QWORD *)_AtlModule + 108) = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_7;
  if ( !GetLastError() )
  {
    v10 = -2147467259;
LABEL_14:
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0xAD5u,
      L"ShowSessionTooLongDialog",
      v10);
    goto LABEL_9;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_14;
  v7 = _AtlModule;
LABEL_7:
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = a1;
  pTaskConfig.hInstance = (HINSTANCE)*((_QWORD *)v7 + 76);
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)SessionTooLongCallbackProc;
  pTaskConfig.dwFlags = 2569;
  pTaskConfig.dwCommonButtons = 6;
  pTaskConfig.pszWindowTitle = (PCWSTR)100;
  pTaskConfig.hMainIcon = 0;
  pTaskConfig.pszMainInstruction = (PCWSTR)605;
  pTaskConfig.pszContent = (PCWSTR)606;
  pTaskConfig.cButtons = 0;
  pTaskConfig.pButtons = 0;
  pTaskConfig.nDefaultButton = 7;
  memset(&pTaskConfig.pszVerificationText, 0, 48);
  pTaskConfig.lpCallbackData = (LONG_PTR)a3;
  FlashAndBeep(a1);
  v11 = TaskDialogIndirect(&pTaskConfig, pnButton, pnRadioButton, &pfVerificationFlagChecked);
  v10 = v11;
  if ( v11 >= 0 )
    goto LABEL_10;
  CEventLogger::LogError(
    v12,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    0xAFBu,
    L"ShowSessionTooLongDialog",
    v11);
LABEL_9:
  *pnButton = 7;
LABEL_10:
  v13 = (void *)*((_QWORD *)_AtlModule + 108);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)_AtlModule + 108) = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002c714  push    rbp
0x14002c716  push    rbx
0x14002c717  push    rsi
0x14002c718  push    rdi
0x14002c719  push    r14
0x14002c71b  push    r15
0x14002c71d  lea     rbp, [rsp-2Fh]
0x14002c722  sub     rsp, 0E8h
0x14002c729  mov     r14, r8
0x14002c72c  mov     rdi, rdx
0x14002c72f  mov     rsi, rcx
0x14002c732  xor     edx, edx; Val
0x14002c734  mov     r8d, 0A0h; Size
0x14002c73a  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x14002c73e  call    memset_0
0x14002c743  xor     r15d, r15d
0x14002c746  xor     r9d, r9d; lpName
0x14002c749  xor     r8d, r8d; bInitialState
0x14002c74c  mov     [rbp+57h+pfVerificationFlagChecked], r15d
0x14002c750  xor     ecx, ecx; lpEventAttributes
0x14002c752  mov     [rsp+110h+pnRadioButton], r15d
0x14002c757  lea     edx, [r15+1]; bManualReset
0x14002c75b  call    cs:__imp_CreateEventW
0x14002c762  nop     dword ptr [rax+rax+00h]
0x14002c767  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c76e  mov     [rcx+360h], rax
0x14002c775  inc     rax
0x14002c778  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002c77e  jnz     short loc_14002C7BE
0x14002c780  call    cs:__imp_GetLastError
0x14002c787  nop     dword ptr [rax+rax+00h]
0x14002c78c  test    eax, eax
0x14002c78e  jz      loc_14002C8CD
0x14002c794  call    cs:__imp_GetLastError
0x14002c79b  nop     dword ptr [rax+rax+00h]
0x14002c7a0  mov     ebx, eax
0x14002c7a2  test    eax, eax
0x14002c7a4  jle     short loc_14002C7AF
0x14002c7a6  movzx   ebx, ax
0x14002c7a9  or      ebx, 80070000h
0x14002c7af  test    ebx, ebx
0x14002c7b1  js      loc_14002C8D2
0x14002c7b7  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c7be  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x14002c7c5  mov     [rbp+57h+pTaskConfig.hwndParent], rsi
0x14002c7c9  mov     rax, [rcx+260h]
0x14002c7d0  mov     rcx, rsi; HWND
0x14002c7d3  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x14002c7d7  lea     rax, ?SessionTooLongCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; SessionTooLongCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14002c7de  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x14002c7e2  mov     [rbp+57h+pTaskConfig.dwFlags], 0A09h
0x14002c7e9  mov     [rbp+57h+pTaskConfig.dwCommonButtons], 6
0x14002c7f0  mov     [rbp+57h+pTaskConfig.pszWindowTitle], 64h ; 'd'
0x14002c7f8  mov     qword ptr [rbp+57h+pTaskConfig.24h], r15
0x14002c7fc  mov     [rbp+57h+pTaskConfig.pszMainInstruction], 25Dh
0x14002c804  mov     [rbp+57h+pTaskConfig.pszContent], 25Eh
0x14002c80c  mov     [rbp+57h+pTaskConfig.cButtons], r15d
0x14002c810  mov     [rbp+57h+pTaskConfig.pButtons], r15
0x14002c814  mov     [rbp+57h+pTaskConfig.nDefaultButton], 7
0x14002c81b  mov     [rbp+57h+pTaskConfig.pszVerificationText], r15
0x14002c81f  mov     [rbp+57h+pTaskConfig.pszExpandedInformation], r15
0x14002c823  mov     [rbp+57h+pTaskConfig.pszExpandedControlText], r15
0x14002c827  mov     [rbp+57h+pTaskConfig.pszCollapsedControlText], r15
0x14002c82b  mov     qword ptr [rbp+57h+pTaskConfig.7Ch], r15
0x14002c82f  mov     [rbp+57h+pTaskConfig.pszFooter], r15
0x14002c833  mov     [rbp+57h+pTaskConfig.lpCallbackData], r14
0x14002c837  call    ?FlashAndBeep@@YAXPEAUHWND__@@@Z; FlashAndBeep(HWND__ *)
0x14002c83c  lea     r9, [rbp+57h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x14002c840  mov     rdx, rdi; pnButton
0x14002c843  lea     r8, [rsp+110h+pnRadioButton]; pnRadioButton
0x14002c848  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x14002c84c  call    cs:__imp_TaskDialogIndirect
0x14002c853  nop     dword ptr [rax+rax+00h]
0x14002c858  mov     ebx, eax
0x14002c85a  test    eax, eax
0x14002c85c  jns     short loc_14002C88D
0x14002c85e  mov     [rsp+110h+var_E8], eax; unsigned int
0x14002c862  mov     r9d, 0AFBh; unsigned int
0x14002c868  lea     rax, aShowsessiontoo; "ShowSessionTooLongDialog"
0x14002c86f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002c876  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x14002c87b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002c882  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002c887  mov     dword ptr [rdi], 7
0x14002c88d  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c894  mov     rcx, [rax+360h]; hObject
0x14002c89b  test    rcx, rcx
0x14002c89e  jz      short loc_14002C8BA
0x14002c8a0  call    cs:__imp_CloseHandle
0x14002c8a7  nop     dword ptr [rax+rax+00h]
0x14002c8ac  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c8b3  mov     [rax+360h], r15
0x14002c8ba  mov     eax, ebx
0x14002c8bc  add     rsp, 0E8h
0x14002c8c3  pop     r15
0x14002c8c5  pop     r14
0x14002c8c7  pop     rdi
0x14002c8c8  pop     rsi
0x14002c8c9  pop     rbx
0x14002c8ca  pop     rbp
0x14002c8cb  retn
0x14002c8cd  mov     ebx, 80004005h
0x14002c8d2  mov     [rsp+110h+var_E8], ebx
0x14002c8d6  mov     r9d, 0AD5h
0x14002c8dc  jmp     short loc_14002C868
```
