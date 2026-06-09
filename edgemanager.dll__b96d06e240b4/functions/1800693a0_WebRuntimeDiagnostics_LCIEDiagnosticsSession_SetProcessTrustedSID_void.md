# WebRuntimeDiagnostics::LCIEDiagnosticsSession::SetProcessTrustedSID(void *)

- ea: `0x1800693a0`
- end: `0x1800694a1`
- name: `?SetProcessTrustedSID@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJPEAX@Z`
- size: `257`
- prototype: `int(WebRuntimeDiagnostics::LCIEDiagnosticsSession *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800689a4`

## callees

- `0x18002b530`
- `0x18002c5b0`
- `0x1800693a0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z` at `0x180069449`
- `iertutil!__imp_?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z` at `0x180069449`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800693d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800693d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006945f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006945f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069453`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069453`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069428`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069428`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069412`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069412`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::SetProcessTrustedSID(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *this,
        void *a2)
{
  int v2; // ebx
  __int64 v3; // r8
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-29h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-19h] BYREF
  PSID TokenInformation[10]; // [rsp+50h] [rbp-9h] BYREF

  TokenHandle = 0;
  if ( !OpenProcessToken(a2, 8u, &TokenHandle) )
    goto LABEL_8;
  ReturnLength = 0;
  v2 = -2147467259;
  memset_0(TokenInformation, 0, 0x4Cu);
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
    {
      v3 = -1;
      do
        ++v3;
      while ( StringSid[v3] );
      IEConfiguration_SetString(268435506, StringSid);
      LocalFree(StringSid);
      v2 = 0;
    }
  }
  CloseHandle(TokenHandle);
  if ( v2 < 0 )
  {
LABEL_8:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800693a0  mov     [rsp-8+arg_0], rbx
0x1800693a5  mov     [rsp-8+arg_10], rsi
0x1800693aa  push    rbp
0x1800693ab  lea     rbp, [rsp-57h]
0x1800693b0  sub     rsp, 0B0h
0x1800693b7  mov     rax, cs:__security_cookie
0x1800693be  xor     rax, rsp
0x1800693c1  mov     [rbp+57h+var_10], rax
0x1800693c5  xor     esi, esi
0x1800693c7  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800693cb  mov     rcx, rdx; ProcessHandle
0x1800693ce  mov     [rbp+57h+TokenHandle], rsi
0x1800693d2  lea     edx, [rsi+8]; DesiredAccess
0x1800693d5  call    cs:__imp_OpenProcessToken
0x1800693db  test    eax, eax
0x1800693dd  jz      loc_180069469
0x1800693e3  xor     edx, edx; Val
0x1800693e5  mov     [rbp+57h+var_80], esi
0x1800693e8  lea     r8d, [rsi+4Ch]; Size
0x1800693ec  mov     ebx, 80004005h
0x1800693f1  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800693f5  call    memset_0
0x1800693fa  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800693fe  lea     rax, [rbp+57h+var_80]
0x180069402  lea     r9d, [rsi+4Ch]; TokenInformationLength
0x180069406  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18006940b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006940f  lea     edx, [rsi+1Fh]; TokenInformationClass
0x180069412  call    cs:__imp_GetTokenInformation
0x180069418  test    eax, eax
0x18006941a  jz      short loc_18006945B
0x18006941c  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180069420  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180069424  mov     [rbp+57h+StringSid], rsi
0x180069428  call    cs:__imp_ConvertSidToStringSidW
0x18006942e  test    eax, eax
0x180069430  jz      short loc_18006945B
0x180069432  mov     rdx, [rbp+57h+StringSid]
0x180069436  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006943a  inc     r8
0x18006943d  cmp     [rdx+r8*2], si
0x180069442  jnz     short loc_18006943A
0x180069444  mov     ecx, 10000032h
0x180069449  call    cs:__imp_?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z; IEConfiguration_SetString(IEConfigurationID,ushort *,ulong)
0x18006944f  mov     rcx, [rbp+57h+StringSid]; hMem
0x180069453  call    cs:__imp_LocalFree
0x180069459  mov     ebx, esi
0x18006945b  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18006945f  call    cs:__imp_CloseHandle
0x180069465  test    ebx, ebx
0x180069467  jns     short loc_18006947E
0x180069469  call    cs:__imp_GetLastError
0x18006946f  mov     ebx, eax
0x180069471  test    eax, eax
0x180069473  jle     short loc_18006947E
0x180069475  movzx   ebx, ax
0x180069478  or      ebx, 80070000h
0x18006947e  mov     eax, ebx
0x180069480  mov     rcx, [rbp+57h+var_10]
0x180069484  xor     rcx, rsp; StackCookie
0x180069487  call    __security_check_cookie
0x18006948c  lea     r11, [rsp+0B0h+var_s0]
0x180069494  mov     rbx, [r11+10h]
0x180069498  mov     rsi, [r11+20h]
0x18006949c  mov     rsp, r11
0x18006949f  pop     rbp
0x1800694a0  retn
```
