# GetAppContainerInfo(void)

- ea: `0x1800c29fc`
- end: `0x1800c2ae5`
- name: `?GetAppContainerInfo@@YAXXZ`
- size: `233`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007ddd8`

## callees

- `0x1800c29fc`
- `0x180189008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2a95`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c2a32`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c2a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2a19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2a19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2ac4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2ac4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c2a7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c2a7c`

## pseudocode

```c
void GetAppContainerInfo(void)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  unsigned __int16 v2; // dx
  unsigned int dwAppContainer; // [rsp+40h] [rbp+8h] BYREF
  unsigned int dwSize; // [rsp+48h] [rbp+10h] BYREF
  void *hToken; // [rsp+50h] [rbp+18h] BYREF

  dwAppContainer = 0;
  dwSize = 0;
  hToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &hToken) )
  {
    if ( (BYTE8(xmmword_1801FAD10) & 0x20) == 0 )
      goto $Cleanup_6;
    LastError = GetLastError();
    v2 = 10;
    goto LABEL_7;
  }
  if ( !GetTokenInformation(hToken, TokenIsAppContainer, &dwAppContainer, 4u, &dwSize)
    && (BYTE8(xmmword_1801FAD10) & 0x20) != 0 )
  {
    LastError = GetLastError();
    v2 = 11;
LABEL_7:
    WPP_SF_d(0x305u, v2, WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids, LastError);
  }
$Cleanup_6:
  if ( hToken )
    CloseHandle(hToken);
  s_IsAppContainer = dwAppContainer != 0;
}

```

## disassembly

```asm
0x1800c29fc  sub     rsp, 38h
0x1800c2a00  mov     [rsp+38h+dwAppContainer], 0
0x1800c2a08  mov     [rsp+38h+dwSize], 0
0x1800c2a10  mov     [rsp+38h+hToken], 0
0x1800c2a19  call    cs:__imp_GetCurrentProcess
0x1800c2a20  nop     dword ptr [rax+rax+00h]
0x1800c2a25  lea     r8, [rsp+38h+hToken]; TokenHandle
0x1800c2a2a  mov     edx, 8; DesiredAccess
0x1800c2a2f  mov     rcx, rax; ProcessHandle
0x1800c2a32  call    cs:__imp_OpenProcessToken
0x1800c2a39  nop     dword ptr [rax+rax+00h]
0x1800c2a3e  test    eax, eax
0x1800c2a40  jnz     short loc_1800C2A5E
0x1800c2a42  test    byte ptr cs:xmmword_1801FAD10+8, 20h; __annotation("TMF:",
0x1800c2a49  jz      short $Cleanup_6
0x1800c2a4b  call    cs:__imp_GetLastError
0x1800c2a52  nop     dword ptr [rax+rax+00h]
0x1800c2a57  mov     edx, 0Ah
0x1800c2a5c  jmp     short loc_1800C2AA6
0x1800c2a5e  mov     rcx, [rsp+38h+hToken]; TokenHandle
0x1800c2a63  lea     rax, [rsp+38h+dwSize]
0x1800c2a68  mov     r9d, 4; TokenInformationLength
0x1800c2a6e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800c2a73  lea     r8, [rsp+38h+dwAppContainer]; TokenInformation
0x1800c2a78  lea     edx, [r9+19h]; TokenInformationClass
0x1800c2a7c  call    cs:__imp_GetTokenInformation
0x1800c2a83  nop     dword ptr [rax+rax+00h]
0x1800c2a88  test    eax, eax
0x1800c2a8a  jnz     short $Cleanup_6
0x1800c2a8c  test    byte ptr cs:xmmword_1801FAD10+8, 20h; __annotation("TMF:",
0x1800c2a93  jz      short $Cleanup_6
0x1800c2a95  call    cs:__imp_GetLastError
0x1800c2a9c  nop     dword ptr [rax+rax+00h]
0x1800c2aa1  mov     edx, 0Bh; id
0x1800c2aa6  mov     r9d, eax; _a1
0x1800c2aa9  lea     r8, WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids; TraceGuid
0x1800c2ab0  mov     ecx, 305h; LevelKeyword
0x1800c2ab5  call    WPP_SF_d
0x1800c2aba  mov     rcx, [rsp+38h+hToken]; hObject
0x1800c2abf  test    rcx, rcx
0x1800c2ac2  jz      short loc_1800C2AD0
0x1800c2ac4  call    cs:__imp_CloseHandle
0x1800c2acb  nop     dword ptr [rax+rax+00h]
0x1800c2ad0  xor     eax, eax
0x1800c2ad2  cmp     [rsp+38h+dwAppContainer], eax
0x1800c2ad6  setnz   al
0x1800c2ad9  mov     cs:s_IsAppContainer, eax
0x1800c2adf  add     rsp, 38h
0x1800c2ae3  retn
```
