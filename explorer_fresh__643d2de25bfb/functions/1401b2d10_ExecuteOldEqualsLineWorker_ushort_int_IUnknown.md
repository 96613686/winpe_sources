# _ExecuteOldEqualsLineWorker(ushort *,int,IUnknown *)

- ea: `0x1401b2d10`
- end: `0x1401b2f07`
- name: `?_ExecuteOldEqualsLineWorker@@YAHPEAGHPEAUIUnknown@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, int, struct IUnknown *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000bc14`

## callees

- `0x14000b9e0`
- `0x14000ba70`
- `0x14000cb98`
- `0x14000d530`
- `0x140087d20`
- `0x14010e160`
- `0x1401b2d10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1401b2e0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1401b2e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b2e97`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b2e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b2eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b2eba`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1401b2d52`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1401b2d52`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1401b2e63`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1401b2e63`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1401b2d6a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1401b2d6a`

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
        if ( (byte_14024FCC2 & 1) != 0 )
        {
          v10 = RemovePathFromCommand(pszPath);
          McTemplateU0z_EventWriteTransfer(v11, ShellTraceId_Explorer_ExecutingFromRunKey_Start, v10);
        }
        if ( (int)ShellExecuteRunApp(pszPath, 0, Buffer, a2, fuStyle, v20, a3, Process) >= 0 )
        {
          IUnknown_WaitForSteadyState(a3, Process[0]);
          if ( (byte_14024FCC2 & 1) != 0 )
          {
            v15 = RemovePathFromCommand(pszPath);
            ProcessId = GetProcessId(Process[0]);
            McTemplateU0qz_EventWriteTransfer(v17, ShellTraceId_Explorer_ExecutingFromRunKey_Stop, ProcessId, v15);
          }
          CloseHandle(Process[0]);
          v5 = 1;
        }
        else
        {
          ModuleHandleA = GetModuleHandleA("explorer.exe");
          if ( (byte_14024FCC2 & 1) != 0 )
          {
            v13 = RemovePathFromCommand(pszPath);
            McTemplateU0qz_EventWriteTransfer(v14, ShellTraceId_Explorer_ExecutingFromRunKey_Stop, 0, v13);
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
0x1401b2d10  mov     [rsp+arg_18], rbx
0x1401b2d15  push    rbp
0x1401b2d16  push    rsi
0x1401b2d17  push    rdi
0x1401b2d18  push    r12
0x1401b2d1a  push    r13
0x1401b2d1c  push    r14
0x1401b2d1e  push    r15
0x1401b2d20  sub     rsp, 270h
0x1401b2d27  mov     rax, cs:__security_cookie
0x1401b2d2e  xor     rax, rsp
0x1401b2d31  mov     [rsp+2A8h+var_48], rax
0x1401b2d39  mov     r12d, edx
0x1401b2d3c  mov     rbx, rcx
0x1401b2d3f  xor     r13d, r13d
0x1401b2d42  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x1401b2d47  mov     edx, 104h; uSize
0x1401b2d4c  mov     r14d, r13d
0x1401b2d4f  mov     r15, r8
0x1401b2d52  call    cs:__imp_GetWindowsDirectoryW
0x1401b2d59  nop     dword ptr [rax+rax+00h]
0x1401b2d5e  test    eax, eax
0x1401b2d60  jz      loc_1401B2ED8
0x1401b2d66  lea     ecx, [r13+43h]; nIndex
0x1401b2d6a  call    cs:__imp_GetSystemMetrics
0x1401b2d71  nop     dword ptr [rax+rax+00h]
0x1401b2d76  mov     ebp, eax
0x1401b2d78  test    eax, eax
0x1401b2d7a  jnz     loc_1401B2ED8
0x1401b2d80  movzx   ecx, word ptr [rbx]
0x1401b2d83  mov     rdi, rbx
0x1401b2d86  jmp     short loc_1401B2D9B
0x1401b2d88  cmp     cx, 20h ; ' '
0x1401b2d8c  jz      short loc_1401B2DA0
0x1401b2d8e  cmp     cx, 2Ch ; ','
0x1401b2d92  jz      short loc_1401B2DA0
0x1401b2d94  add     rdi, 2
0x1401b2d98  movzx   ecx, word ptr [rdi]
0x1401b2d9b  test    cx, cx
0x1401b2d9e  jnz     short loc_1401B2D88
0x1401b2da0  cmp     [rdi], r13w
0x1401b2da4  jnz     short loc_1401B2DAD
0x1401b2da6  mov     ebp, 1
0x1401b2dab  jmp     short loc_1401B2DB1
0x1401b2dad  mov     [rdi], r13w
0x1401b2db1  cmp     [rbx], r13w
0x1401b2db5  jz      loc_1401B2ECC
0x1401b2dbb  test    cs:byte_14024FCC2, 1
0x1401b2dc2  mov     [rsp+2A8h+Process], r13
0x1401b2dc7  jz      short loc_1401B2DE0
0x1401b2dc9  mov     rcx, rbx; unsigned __int16 *
0x1401b2dcc  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x1401b2dd1  mov     r8, rax
0x1401b2dd4  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Start
0x1401b2ddb  call    McTemplateU0z_EventWriteTransfer
0x1401b2de0  lea     rax, [rsp+2A8h+Process]
0x1401b2de5  mov     r9d, r12d
0x1401b2de8  mov     [rsp+2A8h+var_270], rax; __int64
0x1401b2ded  lea     r8, [rsp+2A8h+Buffer]
0x1401b2df2  xor     edx, edx; lpWideCharStr
0x1401b2df4  mov     [rsp+2A8h+punk], r15; punk
0x1401b2df9  mov     rcx, rbx; pszPath
0x1401b2dfc  call    _ShellExecuteRunApp
0x1401b2e01  test    eax, eax
0x1401b2e03  jns     short loc_1401B2E71
0x1401b2e05  lea     rcx, aExplorerExe_1; "explorer.exe"
0x1401b2e0c  call    cs:__imp_GetModuleHandleA
0x1401b2e13  nop     dword ptr [rax+rax+00h]
0x1401b2e18  test    cs:byte_14024FCC2, 1
0x1401b2e1f  mov     rsi, rax
0x1401b2e22  jz      short loc_1401B2E3E
0x1401b2e24  mov     rcx, rbx; unsigned __int16 *
0x1401b2e27  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x1401b2e2c  mov     r9, rax
0x1401b2e2f  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x1401b2e36  xor     r8d, r8d
0x1401b2e39  call    McTemplateU0qz_EventWriteTransfer
0x1401b2e3e  test    rsi, rsi
0x1401b2e41  jz      loc_1401B2ECC
0x1401b2e47  mov     r9d, 20Ch; lpcTitle
0x1401b2e4d  mov     [rsp+2A8h+var_280], rbx
0x1401b2e52  xor     edx, edx; hWnd
0x1401b2e54  mov     [rsp+2A8h+fuStyle], 1030h; fuStyle
0x1401b2e5c  mov     rcx, rsi; hAppInst
0x1401b2e5f  lea     r8d, [r9-9]; lpcText
0x1401b2e63  call    cs:__imp_ShellMessageBoxW
0x1401b2e6a  nop     dword ptr [rax+rax+00h]
0x1401b2e6f  jmp     short loc_1401B2ECC
0x1401b2e71  mov     rdx, [rsp+2A8h+Process]
0x1401b2e76  mov     rcx, r15
0x1401b2e79  call    IUnknown_WaitForSteadyState
0x1401b2e7e  test    cs:byte_14024FCC2, 1
0x1401b2e85  jz      short loc_1401B2EB5
0x1401b2e87  mov     rcx, rbx; unsigned __int16 *
0x1401b2e8a  call    ?RemovePathFromCommand@@YAPEBGPEBG@Z; RemovePathFromCommand(ushort const *)
0x1401b2e8f  mov     rcx, [rsp+2A8h+Process]; Process
0x1401b2e94  mov     rbx, rax
0x1401b2e97  call    cs:__imp_GetProcessId
0x1401b2e9e  nop     dword ptr [rax+rax+00h]
0x1401b2ea3  mov     r9, rbx
0x1401b2ea6  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKey_Stop
0x1401b2ead  mov     r8d, eax
0x1401b2eb0  call    McTemplateU0qz_EventWriteTransfer
0x1401b2eb5  mov     rcx, [rsp+2A8h+Process]; hObject
0x1401b2eba  call    cs:__imp_CloseHandle
0x1401b2ec1  nop     dword ptr [rax+rax+00h]
0x1401b2ec6  mov     r14d, 1
0x1401b2ecc  lea     rbx, [rdi+2]
0x1401b2ed0  test    ebp, ebp
0x1401b2ed2  jz      loc_1401B2D80
0x1401b2ed8  mov     eax, r14d
0x1401b2edb  mov     rcx, [rsp+2A8h+var_48]
0x1401b2ee3  xor     rcx, rsp; StackCookie
0x1401b2ee6  call    __security_check_cookie
0x1401b2eeb  mov     rbx, [rsp+2A8h+arg_18]
0x1401b2ef3  add     rsp, 270h
0x1401b2efa  pop     r15
0x1401b2efc  pop     r14
0x1401b2efe  pop     r13
0x1401b2f00  pop     r12
0x1401b2f02  pop     rdi
0x1401b2f03  pop     rsi
0x1401b2f04  pop     rbp
0x1401b2f05  retn
```
