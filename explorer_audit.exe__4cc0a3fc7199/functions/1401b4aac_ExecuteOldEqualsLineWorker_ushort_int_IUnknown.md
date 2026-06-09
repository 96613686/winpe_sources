# _ExecuteOldEqualsLineWorker(ushort *,int,IUnknown *)

- ea: `0x1401b4aac`
- end: `0x1401b4c7a`
- name: `?_ExecuteOldEqualsLineWorker@@YAHPEAGHPEAUIUnknown@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, int, struct IUnknown *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000af28`

## callees

- `0x14000bd80`
- `0x14000c64c`
- `0x14000d750`
- `0x14000d7e0`
- `0x140081c20`
- `0x1401040e0`
- `0x1401b4aac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1401b4b9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1401b4b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b4c17`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b4c17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b4c34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b4c34`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1401b4aee`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1401b4aee`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1401b4be9`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1401b4be9`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1401b4b00`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1401b4b00`

## pseudocode

```c
__int64 __fastcall _ExecuteOldEqualsLineWorker(unsigned __int16 *pszPath, int a2, struct IUnknown *a3)
{
  unsigned int v5; // r14d
  int i; // ebp
  unsigned __int16 v8; // cx
  LPCWSTR v9; // rdi
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  HMODULE ModuleHandleA; // rsi
  const unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rbx
  DWORD ProcessId; // eax
  __int64 v17; // rcx
  UINT fuStyle; // [rsp+20h] [rbp-288h]
  int v20; // [rsp+28h] [rbp-280h]
  HANDLE Process[2]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-258h] BYREF

  v5 = 0;
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    for ( i = GetSystemMetrics(67); !i; pszPath = (unsigned __int16 *)(v9 + 1) )
    {
      v8 = *pszPath;
      v9 = pszPath;
      while ( v8 && v8 != 32 && v8 != 44 )
        v8 = *++v9;
      if ( *v9 )
        *v9 = 0;
      else
        i = 1;
      if ( *pszPath )
      {
        Process[0] = 0;
        if ( (byte_140253B82 & 1) != 0 )
        {
          v10 = RemovePathFromCommand(pszPath);
          McTemplateU0z_EventWriteTransfer(v11, &ShellTraceId_Explorer_ExecutingFromRunKey_Start, v10);
        }
        if ( (int)ShellExecuteRunApp(pszPath, 0, Buffer, a2, fuStyle, v20, a3, Process) >= 0 )
        {
          IUnknown_WaitForSteadyState(a3, Process[0]);
          if ( (byte_140253B82 & 1) != 0 )
          {
            v15 = RemovePathFromCommand(pszPath);
            ProcessId = GetProcessId(Process[0]);
            McTemplateU0qz_EventWriteTransfer(v17, &ShellTraceId_Explorer_ExecutingFromRunKey_Stop, ProcessId, v15);
          }
          CloseHandle(Process[0]);
          v5 = 1;
        }
        else
        {
          ModuleHandleA = GetModuleHandleA("explorer.exe");
          if ( (byte_140253B82 & 1) != 0 )
          {
            v13 = RemovePathFromCommand(pszPath);
            McTemplateU0qz_EventWriteTransfer(v14, &ShellTraceId_Explorer_ExecutingFromRunKey_Stop, 0, v13);
          }
          if ( ModuleHandleA )
          {
            v20 = (int)pszPath;
            ShellMessageBoxW(ModuleHandleA, 0, (LPCWSTR)0x203, (LPCWSTR)0x20C, 0x1030u);
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1401b4aac  mov     [rsp+arg_18], rbx
0x1401b4ab1  push    rbp
0x1401b4ab2  push    rsi
0x1401b4ab3  push    rdi
0x1401b4ab4  push    r12
0x1401b4ab6  push    r13
0x1401b4ab8  push    r14
0x1401b4aba  push    r15
0x1401b4abc  sub     rsp, 270h
0x1401b4ac3  mov     rax, cs:__security_cookie
0x1401b4aca  xor     rax, rsp
0x1401b4acd  mov     [rsp+2A8h+var_48], rax
0x1401b4ad5  mov     r12d, edx
0x1401b4ad8  mov     rbx, rcx
0x1401b4adb  xor     r13d, r13d
0x1401b4ade  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x1401b4ae3  mov     edx, 104h; uSize
0x1401b4ae8  mov     r14d, r13d
0x1401b4aeb  mov     r15, r8
0x1401b4aee  call    cs:__imp_GetWindowsDirectoryW
0x1401b4af4  test    eax, eax
0x1401b4af6  jz      loc_1401B4C4C
0x1401b4afc  lea     ecx, [r13+43h]; nIndex
0x1401b4b00  call    cs:__imp_GetSystemMetrics
0x1401b4b06  mov     ebp, eax
0x1401b4b08  test    eax, eax
0x1401b4b0a  jnz     loc_1401B4C4C
0x1401b4b10  movzx   ecx, word ptr [rbx]
0x1401b4b13  mov     rdi, rbx
0x1401b4b16  jmp     short loc_1401B4B2B
0x1401b4b18  cmp     cx, 20h ; ' '
0x1401b4b1c  jz      short loc_1401B4B30
0x1401b4b1e  cmp     cx, 2Ch ; ','
0x1401b4b22  jz      short loc_1401B4B30
0x1401b4b24  add     rdi, 2
0x1401b4b28  movzx   ecx, word ptr [rdi]
0x1401b4b2b  test    cx, cx
0x1401b4b2e  jnz     short loc_1401B4B18
0x1401b4b30  cmp     [rdi], r13w
0x1401b4b34  jnz     short loc_1401B4B3D
0x1401b4b36  mov     ebp, 1
0x1401b4b3b  jmp     short loc_1401B4B41
0x1401b4b3d  mov     [rdi], r13w
0x1401b4b41  cmp     [rbx], r13w
0x1401b4b45  jz      loc_1401B4C40
0x1401b4b4b  test    cs:byte_140253B82, 1
0x1401b4b52  mov     [rsp+2A8h+Process], r13
0x1401b4b57  jz      short loc_1401B4B70
0x1401b4b59  mov     rcx, rbx; unsigned __int16 *
0x1401b4b5c  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x1401b4b61  mov     r8, rax
0x1401b4b64  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Start
0x1401b4b6b  call    McTemplateU0z_EventWriteTransfer
0x1401b4b70  lea     rax, [rsp+2A8h+Process]
0x1401b4b75  mov     r9d, r12d
0x1401b4b78  mov     [rsp+2A8h+var_270], rax; __int64
0x1401b4b7d  lea     r8, [rsp+2A8h+Buffer]
0x1401b4b82  xor     edx, edx; lpWideCharStr
0x1401b4b84  mov     [rsp+2A8h+punk], r15; punk
0x1401b4b89  mov     rcx, rbx; pszPath
0x1401b4b8c  call    _ShellExecuteRunApp
0x1401b4b91  test    eax, eax
0x1401b4b93  jns     short loc_1401B4BF1
0x1401b4b95  lea     rcx, aExplorerExe_1; "explorer.exe"
0x1401b4b9c  call    cs:__imp_GetModuleHandleA
0x1401b4ba2  test    cs:byte_140253B82, 1
0x1401b4ba9  mov     rsi, rax
0x1401b4bac  jz      short loc_1401B4BC8
0x1401b4bae  mov     rcx, rbx; unsigned __int16 *
0x1401b4bb1  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x1401b4bb6  mov     r9, rax
0x1401b4bb9  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x1401b4bc0  xor     r8d, r8d
0x1401b4bc3  call    McTemplateU0qz_EventWriteTransfer
0x1401b4bc8  test    rsi, rsi
0x1401b4bcb  jz      short loc_1401B4C40
0x1401b4bcd  mov     r9d, 20Ch; lpcTitle
0x1401b4bd3  mov     [rsp+2A8h+var_280], rbx
0x1401b4bd8  xor     edx, edx; hWnd
0x1401b4bda  mov     [rsp+2A8h+fuStyle], 1030h; fuStyle
0x1401b4be2  mov     rcx, rsi; hAppInst
0x1401b4be5  lea     r8d, [r9-9]; lpcText
0x1401b4be9  call    cs:__imp_ShellMessageBoxW
0x1401b4bef  jmp     short loc_1401B4C40
0x1401b4bf1  mov     rdx, [rsp+2A8h+Process]
0x1401b4bf6  mov     rcx, r15
0x1401b4bf9  call    IUnknown_WaitForSteadyState
0x1401b4bfe  test    cs:byte_140253B82, 1
0x1401b4c05  jz      short loc_1401B4C2F
0x1401b4c07  mov     rcx, rbx; unsigned __int16 *
0x1401b4c0a  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x1401b4c0f  mov     rcx, [rsp+2A8h+Process]; Process
0x1401b4c14  mov     rbx, rax
0x1401b4c17  call    cs:__imp_GetProcessId
0x1401b4c1d  mov     r9, rbx
0x1401b4c20  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x1401b4c27  mov     r8d, eax
0x1401b4c2a  call    McTemplateU0qz_EventWriteTransfer
0x1401b4c2f  mov     rcx, [rsp+2A8h+Process]; hObject
0x1401b4c34  call    cs:__imp_CloseHandle
0x1401b4c3a  mov     r14d, 1
0x1401b4c40  lea     rbx, [rdi+2]
0x1401b4c44  test    ebp, ebp
0x1401b4c46  jz      loc_1401B4B10
0x1401b4c4c  mov     eax, r14d
0x1401b4c4f  mov     rcx, [rsp+2A8h+var_48]
0x1401b4c57  xor     rcx, rsp; StackCookie
0x1401b4c5a  call    __security_check_cookie
0x1401b4c5f  mov     rbx, [rsp+2A8h+arg_18]
0x1401b4c67  add     rsp, 270h
0x1401b4c6e  pop     r15
0x1401b4c70  pop     r14
0x1401b4c72  pop     r13
0x1401b4c74  pop     r12
0x1401b4c76  pop     rdi
0x1401b4c77  pop     rsi
0x1401b4c78  pop     rbp
0x1401b4c79  retn
```
