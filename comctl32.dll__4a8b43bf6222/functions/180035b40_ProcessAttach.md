# _ProcessAttach

- ea: `0x180035b40`
- end: `0x180035c44`
- name: `_ProcessAttach`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800356d8`

## callees

- `0x1800190a4`
- `0x18001923c`
- `0x1800357c0`
- `0x1800358c0`
- `0x180035b40`
- `0x180090020`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180035c0e`
- `ntdll!NtQueryInformationProcess` at `0x180035c0e`
- `KERNEL32!GetProcAddress` at `0x180035b97`
- `KERNEL32!GetProcAddress` at `0x180035b97`
- `KERNEL32!GetModuleHandleW` at `0x180035b6d`
- `KERNEL32!GetModuleHandleW` at `0x180035b82`
- `KERNEL32!GetModuleHandleW` at `0x180035b6d`
- `KERNEL32!GetModuleHandleW` at `0x180035b82`
- `KERNEL32!GetCurrentProcess` at `0x180035bed`
- `KERNEL32!GetCurrentProcess` at `0x180035bed`
- `KERNEL32!GetCurrentProcessId` at `0x180035ba5`
- `KERNEL32!GetCurrentProcessId` at `0x180035ba5`
- `KERNEL32!GetACP` at `0x180035b4d`
- `KERNEL32!GetACP` at `0x180035b4d`
- `KERNEL32!InitializeCriticalSection` at `0x180035b60`
- `KERNEL32!InitializeCriticalSection` at `0x180035b60`

## string_xrefs

- `0x180035b66`: `LPK.DLL`
- `0x180035b8d`: `ProcessIdToSessionId`

## pseudocode

```c
__int64 __fastcall ProcessAttach(HINSTANCE a1)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rbx
  DWORD CurrentProcessId; // eax
  BOOL v4; // eax
  HANDLE CurrentProcess; // rax
  INITCOMMONCONTROLSEX ProcessInformation; // [rsp+40h] [rbp+8h] BYREF

  g_hinst = a1;
  g_uiACP = GetACP();
  InitializeCriticalSection(&g_csDll);
  GetModuleHandleW(L"LPK.DLL");
  ProcessInformation.dwSize = 0;
  ModuleHandleW = GetModuleHandleW(L"KERNEL32");
  v4 = 0;
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "ProcessIdToSessionId");
    if ( ProcAddress )
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( ((unsigned int (__fastcall *)(_QWORD, INITCOMMONCONTROLSEX *))ProcAddress)(
             CurrentProcessId,
             &ProcessInformation) )
      {
        if ( ProcessInformation.dwSize )
          v4 = 1;
      }
    }
  }
  g_bRemoteSession = v4;
  InitGlobalMetrics(0);
  InitGlobalColors();
  InitIme();
  ProcessInformation.dwSize = 0;
  CurrentProcess = GetCurrentProcess();
  if ( NtQueryInformationProcess(CurrentProcess, ProcessWx86Information, &ProcessInformation, 4u, 0) >= 0
    && ProcessInformation.dwSize )
  {
    ProcessInformation.dwSize = 8;
    ProcessInformation.dwICC = 255;
    InitCommonControlsEx(&ProcessInformation);
  }
  return 1;
}

```

## disassembly

```asm
0x180035b40  push    rbx
0x180035b42  sub     rsp, 30h
0x180035b46  mov     cs:g_hinst, rcx
0x180035b4d  call    cs:__imp_GetACP
0x180035b53  lea     rcx, g_csDll; lpCriticalSection
0x180035b5a  mov     cs:g_uiACP, eax
0x180035b60  call    cs:__imp_InitializeCriticalSection
0x180035b66  lea     rcx, aLpkDll; "LPK.DLL"
0x180035b6d  call    cs:__imp_GetModuleHandleW
0x180035b73  lea     rcx, aKernel32; "KERNEL32"
0x180035b7a  mov     [rsp+38h+ProcessInformation], 0
0x180035b82  call    cs:__imp_GetModuleHandleW
0x180035b88  test    rax, rax
0x180035b8b  jz      short loc_180035BCC
0x180035b8d  lea     rdx, aProcessidtoses; "ProcessIdToSessionId"
0x180035b94  mov     rcx, rax; hModule
0x180035b97  call    cs:__imp_GetProcAddress
0x180035b9d  mov     rbx, rax
0x180035ba0  test    rax, rax
0x180035ba3  jz      short loc_180035BCC
0x180035ba5  call    cs:__imp_GetCurrentProcessId
0x180035bab  mov     ecx, eax
0x180035bad  lea     rdx, [rsp+38h+ProcessInformation]
0x180035bb2  mov     rax, rbx
0x180035bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bba  test    eax, eax
0x180035bbc  jz      short loc_180035BCC
0x180035bbe  cmp     [rsp+38h+ProcessInformation], 0
0x180035bc3  jz      short loc_180035BCC
0x180035bc5  mov     eax, 1
0x180035bca  jmp     short loc_180035BCE
0x180035bcc  xor     eax, eax
0x180035bce  xor     ecx, ecx
0x180035bd0  mov     cs:g_bRemoteSession, eax
0x180035bd6  call    InitGlobalMetrics
0x180035bdb  call    InitGlobalColors
0x180035be0  call    InitIme
0x180035be5  mov     [rsp+38h+ProcessInformation], 0
0x180035bed  call    cs:__imp_GetCurrentProcess
0x180035bf3  mov     r9d, 4; ProcessInformationLength
0x180035bf9  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180035c02  mov     rcx, rax; ProcessHandle
0x180035c05  lea     r8, [rsp+38h+ProcessInformation]; ProcessInformation
0x180035c0a  lea     edx, [r9+0Fh]; ProcessInformationClass
0x180035c0e  call    cs:__imp_NtQueryInformationProcess
0x180035c14  test    eax, eax
0x180035c16  js      short loc_180035C39
0x180035c18  cmp     [rsp+38h+ProcessInformation], 0
0x180035c1d  jz      short loc_180035C39
0x180035c1f  lea     rcx, [rsp+38h+ProcessInformation]; picce
0x180035c24  mov     [rsp+38h+ProcessInformation], 8
0x180035c2c  mov     [rsp+38h+arg_4], 0FFh
0x180035c34  call    InitCommonControlsEx
0x180035c39  mov     eax, 1
0x180035c3e  add     rsp, 30h
0x180035c42  pop     rbx
0x180035c43  retn
```
