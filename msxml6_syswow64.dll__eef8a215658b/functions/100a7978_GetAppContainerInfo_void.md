# GetAppContainerInfo(void)

- ea: `0x100a7978`
- end: `0x100a7a14`
- name: `?GetAppContainerInfo@@YGXXZ`
- size: `156`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100a7cbb`

## callees

- `0x100a7978`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a79ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a79dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a79ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a79dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x100a7991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x100a7991`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a7998`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a7998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a79ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a79ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a79ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a79ca`

## pseudocode

```c
void __stdcall GetAppContainerInfo()
{
  HANDLE CurrentProcess; // eax
  DWORD v1; // [esp-4h] [ebp-14h]
  DWORD LastError; // [esp-4h] [ebp-14h]
  unsigned int dwSize; // [esp+4h] [ebp-Ch] BYREF
  unsigned int dwAppContainer; // [esp+8h] [ebp-8h] BYREF
  void *hToken; // [esp+Ch] [ebp-4h] BYREF

  dwAppContainer = 0;
  dwSize = 0;
  hToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hToken) )
  {
    if ( !GetTokenInformation(hToken, TokenIsAppContainer, &dwAppContainer, 4u, &dwSize) && (byte_10185758 & 0x20) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_q(0x305u, 0xBu, WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids, LastError);
    }
  }
  else if ( (byte_10185758 & 0x20) != 0 )
  {
    v1 = GetLastError();
    WPP_SF_q(0x305u, 0xAu, WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids, v1);
  }
  if ( hToken )
    CloseHandle(hToken);
  s_IsAppContainer = dwAppContainer != 0;
}

```

## disassembly

```asm
0x100a7978  mov     edi, edi
0x100a797a  push    ebp
0x100a797b  mov     ebp, esp
0x100a797d  sub     esp, 10h
0x100a7980  xor     eax, eax
0x100a7982  mov     [ebp+dwAppContainer], eax
0x100a7985  mov     [ebp+dwSize], eax
0x100a7988  mov     [ebp+hToken], eax
0x100a798b  lea     eax, [ebp+hToken]
0x100a798e  push    eax; TokenHandle
0x100a798f  push    8; DesiredAccess
0x100a7991  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x100a7997  push    eax; ProcessHandle
0x100a7998  call    ds:__imp__OpenProcessToken@12; OpenProcessToken(x,x,x)
0x100a799e  test    eax, eax
0x100a79a0  jnz     short loc_100A79BB
0x100a79a2  test    byte_10185758, 20h; __annotation("TMF:",
0x100a79a9  jz      short Cleanup_13
0x100a79ab  call    ds:__imp__GetLastError@0; GetLastError()
0x100a79b1  push    eax
0x100a79b2  push    offset _WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids
0x100a79b7  push    0Ah
0x100a79b9  jmp     short loc_100A79EB
0x100a79bb  lea     eax, [ebp+dwSize]
0x100a79be  push    eax; ReturnLength
0x100a79bf  push    4; TokenInformationLength
0x100a79c1  lea     eax, [ebp+dwAppContainer]
0x100a79c4  push    eax; TokenInformation
0x100a79c5  push    1Dh; TokenInformationClass
0x100a79c7  push    [ebp+hToken]; TokenHandle
0x100a79ca  call    ds:__imp__GetTokenInformation@20; GetTokenInformation(x,x,x,x,x)
0x100a79d0  test    eax, eax
0x100a79d2  jnz     short Cleanup_13
0x100a79d4  test    byte_10185758, 20h; __annotation("TMF:",
0x100a79db  jz      short Cleanup_13
0x100a79dd  call    ds:__imp__GetLastError@0; GetLastError()
0x100a79e3  push    eax; _a1
0x100a79e4  push    offset _WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids; TraceGuid
0x100a79e9  push    0Bh
0x100a79eb  pop     edx; id
0x100a79ec  mov     ecx, 305h; LevelKeyword
0x100a79f1  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x100a79f6  cmp     [ebp+hToken], 0
0x100a79fa  jz      short loc_100A7A05
0x100a79fc  push    [ebp+hToken]; hObject
0x100a79ff  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a7a05  xor     eax, eax
0x100a7a07  cmp     [ebp+dwAppContainer], eax
0x100a7a0a  setnz   al
0x100a7a0d  mov     s_IsAppContainer, eax
0x100a7a12  leave
0x100a7a13  retn
```
