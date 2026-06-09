# _ShellExecuteRegAppWorker(ushort const *,RRA_FLAGS,IUnknown *)

- ea: `0x14000bbc4`
- end: `0x14000bd7a`
- name: `?_ShellExecuteRegAppWorker@@YAJPEBGW4RRA_FLAGS@@PEAUIUnknown@@@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000baf4`

## callees

- `0x14000bbc4`
- `0x14000bd80`
- `0x14000c3a4`
- `0x14000c64c`
- `0x14000d750`
- `0x14000d7e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14000bd41`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14000bd41`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000bc5f`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000bc5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc83`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14000bcfc`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14000bcfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bc8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bc97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bc8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bc97`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x14000bbfc`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x14000bbfc`

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
    if ( (byte_140253B82 & 1) != 0 )
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
      if ( (byte_140253B82 & 1) != 0 )
      {
        v12 = RemovePathFromCommand(a1);
        ProcessId = GetProcessId(hProcess);
        McTemplateU0qz_EventWriteTransfer(v14, ShellTraceId_Explorer_ExecutingFromRunKey_Stop, ProcessId, v12);
      }
      CloseHandle(hProcess);
    }
    else if ( (byte_140253B82 & 1) != 0 )
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
0x14000bbc4  mov     [rsp-18h+arg_0], rbx
0x14000bbc9  mov     [rsp-18h+arg_8], rsi
0x14000bbce  push    rbp
0x14000bbcf  push    rdi
0x14000bbd0  push    r14
0x14000bbd2  mov     rbp, rsp
0x14000bbd5  sub     rsp, 60h
0x14000bbd9  mov     r14, r8
0x14000bbdc  mov     [rbp+ppszParameters], 0
0x14000bbe4  mov     esi, edx
0x14000bbe6  mov     [rbp+ppszApplication], 0
0x14000bbee  xor     r8d, r8d; ppszCommandLine
0x14000bbf1  lea     rdx, [rbp+ppszApplication]; ppszApplication
0x14000bbf5  lea     r9, [rbp+ppszParameters]; ppszParameters
0x14000bbf9  mov     rbx, rcx
0x14000bbfc  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x14000bc02  mov     edi, eax
0x14000bc04  test    eax, eax
0x14000bc06  js      loc_14000BC9D
0x14000bc0c  test    cs:byte_140253B82, 1
0x14000bc13  jnz     loc_14000BD5E
0x14000bc19  mov     rdx, [rbp+ppszParameters]; lpWideCharStr
0x14000bc1d  lea     rax, [rbp+hProcess]
0x14000bc21  mov     rcx, [rbp+ppszApplication]; pszPath
0x14000bc25  mov     r9d, 1
0x14000bc2b  mov     [rsp+60h+var_28], rax; __int64
0x14000bc30  xor     r8d, r8d
0x14000bc33  mov     [rsp+60h+punk], r14; punk
0x14000bc38  mov     [rbp+hProcess], 0
0x14000bc40  call    _ShellExecuteRunApp
0x14000bc45  mov     edi, eax
0x14000bc47  test    eax, eax
0x14000bc49  js      short loc_14000BCB4
0x14000bc4b  mov     rcx, [rbp+hProcess]; hProcess
0x14000bc4f  test    rcx, rcx
0x14000bc52  jz      short loc_14000BCB4
0x14000bc54  test    sil, 2
0x14000bc58  jz      short loc_14000BCD9
0x14000bc5a  mov     edx, 80h; dwPriorityClass
0x14000bc5f  call    cs:__imp_SetPriorityClass
0x14000bc65  mov     rdx, [rbp+hProcess]; void *
0x14000bc69  or      r8d, 0FFFFFFFFh; unsigned int
0x14000bc6d  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x14000bc72  test    cs:byte_140253B82, 1
0x14000bc79  jnz     loc_14000BD32
0x14000bc7f  mov     rcx, [rbp+hProcess]; hObject
0x14000bc83  call    cs:__imp_CloseHandle
0x14000bc89  mov     rcx, [rbp+ppszApplication]; pv
0x14000bc8d  call    cs:__imp_CoTaskMemFree
0x14000bc93  mov     rcx, [rbp+ppszParameters]; pv
0x14000bc97  call    cs:__imp_CoTaskMemFree
0x14000bc9d  lea     r11, [rsp+60h+var_s0]
0x14000bca2  mov     eax, edi
0x14000bca4  mov     rbx, [r11+20h]
0x14000bca8  mov     rsi, [r11+28h]
0x14000bcac  mov     rsp, r11
0x14000bcaf  pop     r14
0x14000bcb1  pop     rdi
0x14000bcb2  pop     rbp
0x14000bcb3  retn
0x14000bcb4  test    cs:byte_140253B82, 1
0x14000bcbb  jz      short loc_14000BC89
0x14000bcbd  mov     rcx, rbx; unsigned __int16 *
0x14000bcc0  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x14000bcc5  mov     r9, rax
0x14000bcc8  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x14000bccf  xor     r8d, r8d
0x14000bcd2  call    McTemplateU0qz_EventWriteTransfer
0x14000bcd7  jmp     short loc_14000BC89
0x14000bcd9  test    sil, 40h
0x14000bcdd  jz      short loc_14000BC72
0x14000bcdf  mov     rsi, [rbp+hProcess]
0x14000bce3  lea     rdx, _GUID_087471a8_0058_4321_9dd3_8289cf523f81; guidService
0x14000bcea  mov     r8, rdx; riid
0x14000bced  mov     [rbp+ppvOut], 0
0x14000bcf5  lea     r9, [rbp+ppvOut]; ppvOut
0x14000bcf9  mov     rcx, r14; punk
0x14000bcfc  call    cs:__imp_IUnknown_QueryService
0x14000bd02  test    eax, eax
0x14000bd04  js      loc_14000BC72
0x14000bd0a  mov     rcx, [rbp+ppvOut]
0x14000bd0e  mov     rdx, rsi
0x14000bd11  mov     rax, [rcx]
0x14000bd14  mov     rax, [rax+30h]
0x14000bd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd1d  mov     rcx, [rbp+ppvOut]
0x14000bd21  mov     rax, [rcx]
0x14000bd24  mov     rax, [rax+10h]
0x14000bd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd2d  jmp     loc_14000BC72
0x14000bd32  mov     rcx, rbx; unsigned __int16 *
0x14000bd35  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x14000bd3a  mov     rcx, [rbp+hProcess]; Process
0x14000bd3e  mov     rbx, rax
0x14000bd41  call    cs:__imp_GetProcessId
0x14000bd47  mov     r9, rbx
0x14000bd4a  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x14000bd51  mov     r8d, eax
0x14000bd54  call    McTemplateU0qz_EventWriteTransfer
0x14000bd59  jmp     loc_14000BC7F
0x14000bd5e  mov     rcx, rbx; unsigned __int16 *
0x14000bd61  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x14000bd66  mov     r8, rax
0x14000bd69  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Start
0x14000bd70  call    McTemplateU0z_EventWriteTransfer
0x14000bd75  jmp     loc_14000BC19
```
