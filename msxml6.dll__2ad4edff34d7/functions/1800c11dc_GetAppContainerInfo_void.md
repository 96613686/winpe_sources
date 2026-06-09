# GetAppContainerInfo(void)

- ea: `0x1800c11dc`
- end: `0x1800c12a0`
- name: `?GetAppContainerInfo@@YAXXZ`
- size: `196`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080468`

## callees

- `0x1800c11dc`
- `0x180185008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c121f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c125d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c121f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c125d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c120c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c120c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c11f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c11f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1286`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c124a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c124a`

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
    if ( (BYTE8(xmmword_1801F6C10) & 0x20) == 0 )
      goto $Cleanup_6;
    LastError = GetLastError();
    v2 = 10;
    goto LABEL_7;
  }
  if ( !GetTokenInformation(hToken, TokenIsAppContainer, &dwAppContainer, 4u, &dwSize)
    && (BYTE8(xmmword_1801F6C10) & 0x20) != 0 )
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
0x1800c11dc  sub     rsp, 38h
0x1800c11e0  mov     [rsp+38h+dwAppContainer], 0
0x1800c11e8  mov     [rsp+38h+dwSize], 0
0x1800c11f0  mov     [rsp+38h+hToken], 0
0x1800c11f9  call    cs:__imp_GetCurrentProcess
0x1800c11ff  lea     r8, [rsp+38h+hToken]; TokenHandle
0x1800c1204  mov     edx, 8; DesiredAccess
0x1800c1209  mov     rcx, rax; ProcessHandle
0x1800c120c  call    cs:__imp_OpenProcessToken
0x1800c1212  test    eax, eax
0x1800c1214  jnz     short loc_1800C122C
0x1800c1216  test    byte ptr cs:xmmword_1801F6C10+8, 20h; __annotation("TMF:",
0x1800c121d  jz      short $Cleanup_6
0x1800c121f  call    cs:__imp_GetLastError
0x1800c1225  mov     edx, 0Ah
0x1800c122a  jmp     short loc_1800C1268
0x1800c122c  mov     rcx, [rsp+38h+hToken]; TokenHandle
0x1800c1231  lea     rax, [rsp+38h+dwSize]
0x1800c1236  mov     r9d, 4; TokenInformationLength
0x1800c123c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800c1241  lea     r8, [rsp+38h+dwAppContainer]; TokenInformation
0x1800c1246  lea     edx, [r9+19h]; TokenInformationClass
0x1800c124a  call    cs:__imp_GetTokenInformation
0x1800c1250  test    eax, eax
0x1800c1252  jnz     short $Cleanup_6
0x1800c1254  test    byte ptr cs:xmmword_1801F6C10+8, 20h; __annotation("TMF:",
0x1800c125b  jz      short $Cleanup_6
0x1800c125d  call    cs:__imp_GetLastError
0x1800c1263  mov     edx, 0Bh; id
0x1800c1268  mov     r9d, eax; _a1
0x1800c126b  lea     r8, WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids; TraceGuid
0x1800c1272  mov     ecx, 305h; LevelKeyword
0x1800c1277  call    WPP_SF_d
0x1800c127c  mov     rcx, [rsp+38h+hToken]; hObject
0x1800c1281  test    rcx, rcx
0x1800c1284  jz      short loc_1800C128C
0x1800c1286  call    cs:__imp_CloseHandle
0x1800c128c  xor     eax, eax
0x1800c128e  cmp     [rsp+38h+dwAppContainer], eax
0x1800c1292  setnz   al
0x1800c1295  mov     cs:s_IsAppContainer, eax
0x1800c129b  add     rsp, 38h
0x1800c129f  retn
```
