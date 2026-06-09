# Microsoft::Windows::MDM::OmadmClient::Utilities::CreateProcessAsUserWrapper(ushort const *,ushort const *)

- ea: `0x1400526c0`
- end: `0x1400528c4`
- name: `?CreateProcessAsUserWrapper@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBG0@Z`
- size: `516`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::Utilities *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x1400526c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005271f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005271f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052776`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14005270f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14005270f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140052766`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140052766`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14005282e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14005282e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140052749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140052749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400527a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052854`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400527a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052854`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052891`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::CreateProcessAsUserWrapper(
        Microsoft::Windows::MDM::OmadmClient::Utilities *this,
        const unsigned __int16 *a2,
        WCHAR *a3)
{
  int result; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(a2, Dst, 0x104u) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xBu, 1, &TokenHandle) )
    goto LABEL_5;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  StartupInfo.cb = 104;
  if ( !CreateProcessAsUserW(TokenHandle, Dst, a3, 0, 0, 0, 0x1000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
LABEL_5:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v8;
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1400526c0  mov     [rsp-8+arg_0], rbx
0x1400526c5  mov     [rsp-8+arg_18], rdi
0x1400526ca  push    rbp
0x1400526cb  lea     rbp, [rsp-210h]
0x1400526d3  sub     rsp, 310h
0x1400526da  mov     rax, cs:__security_cookie
0x1400526e1  xor     rax, rsp
0x1400526e4  mov     [rbp+210h+var_10], rax
0x1400526eb  mov     rdi, r8
0x1400526ee  lea     rcx, [rbp+210h+Dst]; void *
0x1400526f2  mov     rbx, rdx
0x1400526f5  mov     r8d, 208h; Size
0x1400526fb  xor     edx, edx; Val
0x1400526fd  call    memset_0
0x140052702  mov     r8d, 104h; nSize
0x140052708  lea     rdx, [rbp+210h+Dst]; lpDst
0x14005270c  mov     rcx, rbx; lpSrc
0x14005270f  call    cs:__imp_ExpandEnvironmentStringsW
0x140052716  nop     dword ptr [rax+rax+00h]
0x14005271b  test    eax, eax
0x14005271d  jnz     short loc_140052740
0x14005271f  call    cs:__imp_GetLastError
0x140052726  nop     dword ptr [rax+rax+00h]
0x14005272b  test    eax, eax
0x14005272d  jle     loc_14005289F
0x140052733  movzx   eax, ax
0x140052736  or      eax, 80070000h
0x14005273b  jmp     loc_14005289F
0x140052740  mov     [rsp+310h+TokenHandle], 0
0x140052749  call    cs:__imp_GetCurrentThread
0x140052750  nop     dword ptr [rax+rax+00h]
0x140052755  mov     edx, 0Bh; DesiredAccess
0x14005275a  lea     r9, [rsp+310h+TokenHandle]; TokenHandle
0x14005275f  mov     rcx, rax; ThreadHandle
0x140052762  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x140052766  call    cs:__imp_OpenThreadToken
0x14005276d  nop     dword ptr [rax+rax+00h]
0x140052772  test    eax, eax
0x140052774  jnz     short loc_1400527B3
0x140052776  call    cs:__imp_GetLastError
0x14005277d  nop     dword ptr [rax+rax+00h]
0x140052782  mov     ebx, eax
0x140052784  test    eax, eax
0x140052786  jle     short loc_140052791
0x140052788  movzx   ebx, ax
0x14005278b  or      ebx, 80070000h
0x140052791  mov     rcx, [rsp+310h+TokenHandle]; hObject
0x140052796  lea     rdx, [rcx-1]
0x14005279a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14005279e  ja      short loc_1400527AC
0x1400527a0  call    cs:__imp_CloseHandle
0x1400527a7  nop     dword ptr [rax+rax+00h]
0x1400527ac  mov     eax, ebx
0x1400527ae  jmp     loc_14005289F
0x1400527b3  xor     eax, eax
0x1400527b5  lea     rcx, [rbp+210h+StartupInfo]; void *
0x1400527b9  xorps   xmm0, xmm0
0x1400527bc  mov     qword ptr [rsp+310h+ProcessInformation.dwProcessId], rax
0x1400527c1  xor     edx, edx; Val
0x1400527c3  movups  xmmword ptr [rsp+310h+ProcessInformation.hProcess], xmm0
0x1400527c8  lea     ebx, [rax+68h]
0x1400527cb  mov     r8d, ebx; Size
0x1400527ce  call    memset_0
0x1400527d3  mov     rcx, [rsp+310h+TokenHandle]; hToken
0x1400527d8  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x1400527df  mov     [rbp+210h+StartupInfo.lpDesktop], rax
0x1400527e3  lea     rdx, [rbp+210h+Dst]; lpApplicationName
0x1400527e7  lea     rax, [rsp+310h+ProcessInformation]
0x1400527ec  mov     [rbp+210h+StartupInfo.cb], ebx
0x1400527ef  mov     [rsp+310h+lpProcessInformation], rax; lpProcessInformation
0x1400527f4  xor     r9d, r9d; lpProcessAttributes
0x1400527f7  lea     rax, [rbp+210h+StartupInfo]
0x1400527fb  mov     r8, rdi; lpCommandLine
0x1400527fe  mov     [rsp+310h+lpStartupInfo], rax; lpStartupInfo
0x140052803  mov     [rsp+310h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14005280c  mov     [rsp+310h+lpEnvironment], 0; lpEnvironment
0x140052815  mov     [rsp+310h+dwCreationFlags], 1000000h; dwCreationFlags
0x14005281d  mov     [rsp+310h+bInheritHandles], 0; bInheritHandles
0x140052825  mov     [rsp+310h+lpThreadAttributes], 0; lpThreadAttributes
0x14005282e  call    cs:__imp_CreateProcessAsUserW
0x140052835  nop     dword ptr [rax+rax+00h]
0x14005283a  mov     rcx, [rsp+310h+ProcessInformation.hProcess]; hObject
0x14005283f  test    eax, eax
0x140052841  jnz     short loc_140052865
0x140052843  call    cs:__imp_CloseHandle
0x14005284a  nop     dword ptr [rax+rax+00h]
0x14005284f  mov     rcx, [rsp+310h+ProcessInformation.hThread]; hObject
0x140052854  call    cs:__imp_CloseHandle
0x14005285b  nop     dword ptr [rax+rax+00h]
0x140052860  jmp     loc_140052776
0x140052865  call    cs:__imp_CloseHandle
0x14005286c  nop     dword ptr [rax+rax+00h]
0x140052871  mov     rcx, [rsp+310h+ProcessInformation.hThread]; hObject
0x140052876  call    cs:__imp_CloseHandle
0x14005287d  nop     dword ptr [rax+rax+00h]
0x140052882  mov     rcx, [rsp+310h+TokenHandle]; hObject
0x140052887  lea     rax, [rcx-1]
0x14005288b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005288f  ja      short loc_14005289D
0x140052891  call    cs:__imp_CloseHandle
0x140052898  nop     dword ptr [rax+rax+00h]
0x14005289d  xor     eax, eax
0x14005289f  mov     rcx, [rbp+210h+var_10]
0x1400528a6  xor     rcx, rsp; StackCookie
0x1400528a9  call    __security_check_cookie
0x1400528ae  lea     r11, [rsp+310h+var_s0]
0x1400528b6  mov     rbx, [r11+10h]
0x1400528ba  mov     rdi, [r11+28h]
0x1400528be  mov     rsp, r11
0x1400528c1  pop     rbp
0x1400528c2  retn
```
