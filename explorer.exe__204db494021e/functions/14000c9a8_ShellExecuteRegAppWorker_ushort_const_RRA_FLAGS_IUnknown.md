# _ShellExecuteRegAppWorker(ushort const *,RRA_FLAGS,IUnknown *)

- ea: `0x14000c9a8`
- end: `0x14000cb91`
- name: `?_ShellExecuteRegAppWorker@@YAJPEBGW4RRA_FLAGS@@PEAUIUnknown@@@Z`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c8cc`

## callees

- `0x14000b9e0`
- `0x14000ba70`
- `0x14000c9a8`
- `0x14000cb98`
- `0x14000d230`
- `0x14000d530`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000ca51`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000ca51`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14000cb52`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14000cb52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ca7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ca7b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14000cb07`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14000cb07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ca8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ca9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ca8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ca9b`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x14000c9e0`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x14000c9e0`

## pseudocode

```c
__int64 __fastcall _ShellExecuteRegAppWorker(const WCHAR *a1, char a2, IUnknown *a3)
{
  HRESULT v6; // edi
  HWND v7; // rcx
  const unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  HANDLE v11; // rsi
  const unsigned __int16 *v12; // rbx
  DWORD ProcessId; // eax
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+28h] [rbp-38h]
  void *ppvOut; // [rsp+40h] [rbp-20h] BYREF
  PWSTR ppszApplication; // [rsp+48h] [rbp-18h] BYREF
  PWSTR ppszParameters; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hProcess; // [rsp+98h] [rbp+38h] BYREF

  ppszParameters = 0;
  ppszApplication = 0;
  v6 = SHEvaluateSystemCommandTemplate(a1, &ppszApplication, 0, &ppszParameters);
  if ( v6 >= 0 )
  {
    if ( (byte_14024FCC2 & 1) != 0 )
    {
      v15 = RemovePathFromCommand(a1);
      McTemplateU0z_EventWriteTransfer(v16, ShellTraceId_Explorer_ExecutingFromRunKey_Start, v15);
    }
    hProcess = 0;
    v6 = ShellExecuteRunApp(ppszApplication, ppszParameters, v17, v18, a3, (__int64)&hProcess);
    if ( v6 >= 0 && hProcess )
    {
      if ( (a2 & 2) != 0 )
      {
        SetPriorityClass(hProcess, 0x80u);
        SHProcessMessagesUntilEvent(v7, hProcess, 0xFFFFFFFF);
      }
      else if ( (a2 & 0x40) != 0 )
      {
        v11 = hProcess;
        ppvOut = 0;
        if ( IUnknown_QueryService(
               a3,
               &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
               &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
               &ppvOut) >= 0 )
        {
          (*(void (__fastcall **)(void *, HANDLE))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v11);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
        }
      }
      if ( (byte_14024FCC2 & 1) != 0 )
      {
        v12 = RemovePathFromCommand(a1);
        ProcessId = GetProcessId(hProcess);
        McTemplateU0qz_EventWriteTransfer(v14, ShellTraceId_Explorer_ExecutingFromRunKey_Stop, ProcessId, v12);
      }
      CloseHandle(hProcess);
    }
    else if ( (byte_14024FCC2 & 1) != 0 )
    {
      v9 = RemovePathFromCommand(a1);
      McTemplateU0qz_EventWriteTransfer(v10, ShellTraceId_Explorer_ExecutingFromRunKey_Stop, 0, v9);
    }
    CoTaskMemFree(ppszApplication);
    CoTaskMemFree(ppszParameters);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000c9a8  mov     [rsp-18h+arg_0], rbx
0x14000c9ad  mov     [rsp-18h+arg_8], rsi
0x14000c9b2  push    rbp
0x14000c9b3  push    rdi
0x14000c9b4  push    r14
0x14000c9b6  mov     rbp, rsp
0x14000c9b9  sub     rsp, 60h
0x14000c9bd  mov     r14, r8
0x14000c9c0  mov     [rbp+ppszParameters], 0
0x14000c9c8  mov     esi, edx
0x14000c9ca  mov     [rbp+ppszApplication], 0
0x14000c9d2  xor     r8d, r8d; ppszCommandLine
0x14000c9d5  lea     rdx, [rbp+ppszApplication]; ppszApplication
0x14000c9d9  lea     r9, [rbp+ppszParameters]; ppszParameters
0x14000c9dd  mov     rbx, rcx
0x14000c9e0  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x14000c9e7  nop     dword ptr [rax+rax+00h]
0x14000c9ec  mov     edi, eax
0x14000c9ee  test    eax, eax
0x14000c9f0  js      loc_14000CAA7
0x14000c9f6  test    cs:byte_14024FCC2, 1
0x14000c9fd  jnz     loc_14000CB75
0x14000ca03  mov     rdx, [rbp+ppszParameters]; lpWideCharStr
0x14000ca07  lea     rax, [rbp+hProcess]
0x14000ca0b  mov     rcx, [rbp+ppszApplication]; pszPath
0x14000ca0f  mov     r9d, 1
0x14000ca15  mov     [rsp+60h+var_28], rax; __int64
0x14000ca1a  xor     r8d, r8d
0x14000ca1d  mov     [rsp+60h+punk], r14; punk
0x14000ca22  mov     [rbp+hProcess], 0
0x14000ca2a  call    _ShellExecuteRunApp
0x14000ca2f  mov     edi, eax
0x14000ca31  test    eax, eax
0x14000ca33  js      loc_14000CABF
0x14000ca39  mov     rcx, [rbp+hProcess]; hProcess
0x14000ca3d  test    rcx, rcx
0x14000ca40  jz      short loc_14000CABF
0x14000ca42  test    sil, 2
0x14000ca46  jz      loc_14000CAE4
0x14000ca4c  mov     edx, 80h; dwPriorityClass
0x14000ca51  call    cs:__imp_SetPriorityClass
0x14000ca58  nop     dword ptr [rax+rax+00h]
0x14000ca5d  mov     rdx, [rbp+hProcess]; void *
0x14000ca61  or      r8d, 0FFFFFFFFh; unsigned int
0x14000ca65  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x14000ca6a  test    cs:byte_14024FCC2, 1
0x14000ca71  jnz     loc_14000CB43
0x14000ca77  mov     rcx, [rbp+hProcess]; hObject
0x14000ca7b  call    cs:__imp_CloseHandle
0x14000ca82  nop     dword ptr [rax+rax+00h]
0x14000ca87  mov     rcx, [rbp+ppszApplication]; pv
0x14000ca8b  call    cs:__imp_CoTaskMemFree
0x14000ca92  nop     dword ptr [rax+rax+00h]
0x14000ca97  mov     rcx, [rbp+ppszParameters]; pv
0x14000ca9b  call    cs:__imp_CoTaskMemFree
0x14000caa2  nop     dword ptr [rax+rax+00h]
0x14000caa7  lea     r11, [rsp+60h+var_s0]
0x14000caac  mov     eax, edi
0x14000caae  mov     rbx, [r11+20h]
0x14000cab2  mov     rsi, [r11+28h]
0x14000cab6  mov     rsp, r11
0x14000cab9  pop     r14
0x14000cabb  pop     rdi
0x14000cabc  pop     rbp
0x14000cabd  retn
0x14000cabf  test    cs:byte_14024FCC2, 1
0x14000cac6  jz      short loc_14000CA87
0x14000cac8  mov     rcx, rbx; unsigned __int16 *
0x14000cacb  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x14000cad0  mov     r9, rax
0x14000cad3  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x14000cada  xor     r8d, r8d
0x14000cadd  call    McTemplateU0qz_EventWriteTransfer
0x14000cae2  jmp     short loc_14000CA87
0x14000cae4  test    sil, 40h
0x14000cae8  jz      short loc_14000CA6A
0x14000caea  mov     rsi, [rbp+hProcess]
0x14000caee  lea     rdx, _GUID_087471a8_0058_4321_9dd3_8289cf523f81; guidService
0x14000caf5  mov     r8, rdx; riid
0x14000caf8  mov     [rbp+ppvOut], 0
0x14000cb00  lea     r9, [rbp+ppvOut]; ppvOut
0x14000cb04  mov     rcx, r14; punk
0x14000cb07  call    cs:__imp_IUnknown_QueryService
0x14000cb0e  nop     dword ptr [rax+rax+00h]
0x14000cb13  test    eax, eax
0x14000cb15  js      loc_14000CA6A
0x14000cb1b  mov     rcx, [rbp+ppvOut]
0x14000cb1f  mov     rdx, rsi
0x14000cb22  mov     rax, [rcx]
0x14000cb25  mov     rax, [rax+30h]
0x14000cb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb2e  mov     rcx, [rbp+ppvOut]
0x14000cb32  mov     rax, [rcx]
0x14000cb35  mov     rax, [rax+10h]
0x14000cb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb3e  jmp     loc_14000CA6A
0x14000cb43  mov     rcx, rbx; unsigned __int16 *
0x14000cb46  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x14000cb4b  mov     rcx, [rbp+hProcess]; Process
0x14000cb4f  mov     rbx, rax
0x14000cb52  call    cs:__imp_GetProcessId
0x14000cb59  nop     dword ptr [rax+rax+00h]
0x14000cb5e  mov     r9, rbx
0x14000cb61  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x14000cb68  mov     r8d, eax
0x14000cb6b  call    McTemplateU0qz_EventWriteTransfer
0x14000cb70  jmp     loc_14000CA77
0x14000cb75  mov     rcx, rbx; unsigned __int16 *
0x14000cb78  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x14000cb7d  mov     r8, rax
0x14000cb80  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Start
0x14000cb87  call    McTemplateU0z_EventWriteTransfer
0x14000cb8c  jmp     loc_14000CA03
```
