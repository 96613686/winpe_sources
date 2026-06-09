# CNetCenterLUA::StartNetprofmService(void)

- ea: `0x18001adb0`
- end: `0x18001ae69`
- name: `?StartNetprofmService@CNetCenterLUA@@UEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CNetCenterLUA *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180010e9c`
- `0x18001adb0`
- `0x18001e564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae13`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ae36`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ae48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ae36`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ae48`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001ae09`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001ae09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001add3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001add3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001adf1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001adf1`

## string_xrefs

- `0x18001adca`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CNetCenterLUA::StartNetprofmService(CNetCenterLUA *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  unsigned int Error; // ebx
  signed int LastError; // eax

  EnableNetprofm();
  v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"netprofm", 0x10u);
    v4 = v3;
    if ( v3 )
    {
      Error = 0;
      if ( !StartServiceW(v3, 0, 0) )
      {
        LastError = GetLastError();
        Error = LastError;
        if ( LastError == 1056 )
        {
          Error = 0;
        }
        else if ( LastError > 0 )
        {
          Error = (unsigned __int16)LastError | 0x80070000;
        }
      }
      CloseServiceHandle(v4);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x18001adb0  mov     [rsp+arg_0], rbx
0x18001adb5  mov     [rsp+arg_8], rsi
0x18001adba  push    rdi
0x18001adbb  sub     rsp, 20h
0x18001adbf  call    ?EnableNetprofm@@YAJXZ; EnableNetprofm(void)
0x18001adc4  mov     r8d, 1; dwDesiredAccess
0x18001adca  lea     rdx, DatabaseName; "ServicesActive"
0x18001add1  xor     ecx, ecx; lpMachineName
0x18001add3  call    cs:__imp_OpenSCManagerW
0x18001add9  mov     rdi, rax
0x18001addc  test    rax, rax
0x18001addf  jz      short loc_18001AE50
0x18001ade1  mov     r8d, 10h; dwDesiredAccess
0x18001ade7  lea     rdx, ServiceName; "netprofm"
0x18001adee  mov     rcx, rax; hSCManager
0x18001adf1  call    cs:__imp_OpenServiceW
0x18001adf7  mov     rsi, rax
0x18001adfa  test    rax, rax
0x18001adfd  jz      short loc_18001AE3E
0x18001adff  xor     r8d, r8d; lpServiceArgVectors
0x18001ae02  xor     edx, edx; dwNumServiceArgs
0x18001ae04  mov     rcx, rax; hService
0x18001ae07  xor     ebx, ebx
0x18001ae09  call    cs:__imp_StartServiceW
0x18001ae0f  test    eax, eax
0x18001ae11  jnz     short loc_18001AE33
0x18001ae13  call    cs:__imp_GetLastError
0x18001ae19  mov     ebx, eax
0x18001ae1b  cmp     eax, 420h
0x18001ae20  jnz     short loc_18001AE26
0x18001ae22  xor     ebx, ebx
0x18001ae24  jmp     short loc_18001AE33
0x18001ae26  test    eax, eax
0x18001ae28  jle     short loc_18001AE33
0x18001ae2a  movzx   ebx, ax
0x18001ae2d  or      ebx, 80070000h
0x18001ae33  mov     rcx, rsi; hSCObject
0x18001ae36  call    cs:__imp_CloseServiceHandle
0x18001ae3c  jmp     short loc_18001AE45
0x18001ae3e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ae43  mov     ebx, eax
0x18001ae45  mov     rcx, rdi; hSCObject
0x18001ae48  call    cs:__imp_CloseServiceHandle
0x18001ae4e  jmp     short loc_18001AE57
0x18001ae50  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ae55  mov     ebx, eax
0x18001ae57  mov     rsi, [rsp+28h+arg_8]
0x18001ae5c  mov     eax, ebx
0x18001ae5e  mov     rbx, [rsp+28h+arg_0]
0x18001ae63  add     rsp, 20h
0x18001ae67  pop     rdi
0x18001ae68  retn
```
