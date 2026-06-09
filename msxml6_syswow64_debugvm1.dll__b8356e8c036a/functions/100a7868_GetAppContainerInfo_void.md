# GetAppContainerInfo(void)

- ea: `0x100a7868`
- end: `0x100a7904`
- name: `?GetAppContainerInfo@@YGXXZ`
- size: `156`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100a7bab`

## callees

- `0x100a7868`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a789b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a78cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a789b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a78cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x100a7881`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x100a7881`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a7888`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a7888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a78ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a78ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a78ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a78ba`

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
    if ( !GetTokenInformation(hToken, TokenIsAppContainer, &dwAppContainer, 4u, &dwSize) && (byte_10185798 & 0x20) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_q(0x305u, 0xBu, WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids, LastError);
    }
  }
  else if ( (byte_10185798 & 0x20) != 0 )
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
0x100a7868  mov     edi, edi
0x100a786a  push    ebp
0x100a786b  mov     ebp, esp
0x100a786d  sub     esp, 10h
0x100a7870  xor     eax, eax
0x100a7872  mov     [ebp+dwAppContainer], eax
0x100a7875  mov     [ebp+dwSize], eax
0x100a7878  mov     [ebp+hToken], eax
0x100a787b  lea     eax, [ebp+hToken]
0x100a787e  push    eax; TokenHandle
0x100a787f  push    8; DesiredAccess
0x100a7881  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x100a7887  push    eax; ProcessHandle
0x100a7888  call    ds:__imp__OpenProcessToken@12; OpenProcessToken(x,x,x)
0x100a788e  test    eax, eax
0x100a7890  jnz     short loc_100A78AB
0x100a7892  test    byte_10185798, 20h; __annotation("TMF:",
0x100a7899  jz      short Cleanup_13
0x100a789b  call    ds:__imp__GetLastError@0; GetLastError()
0x100a78a1  push    eax
0x100a78a2  push    offset _WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids
0x100a78a7  push    0Ah
0x100a78a9  jmp     short loc_100A78DB
0x100a78ab  lea     eax, [ebp+dwSize]
0x100a78ae  push    eax; ReturnLength
0x100a78af  push    4; TokenInformationLength
0x100a78b1  lea     eax, [ebp+dwAppContainer]
0x100a78b4  push    eax; TokenInformation
0x100a78b5  push    1Dh; TokenInformationClass
0x100a78b7  push    [ebp+hToken]; TokenHandle
0x100a78ba  call    ds:__imp__GetTokenInformation@20; GetTokenInformation(x,x,x,x,x)
0x100a78c0  test    eax, eax
0x100a78c2  jnz     short Cleanup_13
0x100a78c4  test    byte_10185798, 20h; __annotation("TMF:",
0x100a78cb  jz      short Cleanup_13
0x100a78cd  call    ds:__imp__GetLastError@0; GetLastError()
0x100a78d3  push    eax; _a1
0x100a78d4  push    offset _WPP_d5491922dd0e3cd152d4fc2ca0233173_Traceguids; TraceGuid
0x100a78d9  push    0Bh
0x100a78db  pop     edx; id
0x100a78dc  mov     ecx, 305h; LevelKeyword
0x100a78e1  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x100a78e6  cmp     [ebp+hToken], 0
0x100a78ea  jz      short loc_100A78F5
0x100a78ec  push    [ebp+hToken]; hObject
0x100a78ef  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a78f5  xor     eax, eax
0x100a78f7  cmp     [ebp+dwAppContainer], eax
0x100a78fa  setnz   al
0x100a78fd  mov     s_IsAppContainer, eax
0x100a7902  leave
0x100a7903  retn
```
