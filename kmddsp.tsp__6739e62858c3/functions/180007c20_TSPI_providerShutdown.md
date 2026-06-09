# TSPI_providerShutdown

- ea: `0x180007c20`
- end: `0x180007d93`
- name: `TSPI_providerShutdown`
- size: `371`
- prototype: `LONG __stdcall(DWORD dwTSPIVersion, DWORD dwPermanentProviderID)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001400`
- `0x180002600`
- `0x1800029dc`
- `0x180007c20`
- `0x180007df8`

## import_xrefs

- `KERNEL32!DefineDosDeviceA` at `0x180007d28`
- `KERNEL32!DefineDosDeviceA` at `0x180007d28`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180007cbc`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180007cbc`
- `KERNEL32!CancelIo` at `0x180007c66`
- `KERNEL32!CancelIo` at `0x180007c79`
- `KERNEL32!CancelIo` at `0x180007c66`
- `KERNEL32!CancelIo` at `0x180007c79`
- `KERNEL32!LocalFree` at `0x180007d55`
- `KERNEL32!LocalFree` at `0x180007d68`
- `KERNEL32!LocalFree` at `0x180007d55`
- `KERNEL32!LocalFree` at `0x180007d68`
- `KERNEL32!CloseHandle` at `0x180007c8c`
- `KERNEL32!CloseHandle` at `0x180007cfd`
- `KERNEL32!CloseHandle` at `0x180007d10`
- `KERNEL32!CloseHandle` at `0x180007d3e`
- `KERNEL32!CloseHandle` at `0x180007c8c`
- `KERNEL32!CloseHandle` at `0x180007cfd`
- `KERNEL32!CloseHandle` at `0x180007d10`
- `KERNEL32!CloseHandle` at `0x180007d3e`
- `KERNEL32!WaitForSingleObject` at `0x180007cea`
- `KERNEL32!WaitForSingleObject` at `0x180007cea`

## string_xrefs

- `0x180007c98`: `providerShutdown: Calling PostQueuedCompletionStatus`
- `0x180007ccc`: `providerShutdown: PostQueuedCompletionStatus failed`

## pseudocode

```c
LONG __stdcall TSPI_providerShutdown(DWORD dwTSPIVersion, DWORD dwPermanentProviderID)
{
  CHAR DeviceName[16]; // [rsp+20h] [rbp-28h] BYREF

  strcpy(DeviceName, "NDISTAPI");
  TspLog(8, "providerShutdown: perfProvID(%x)", dwPermanentProviderID);
  CancelIo(ghDriverSync);
  CancelIo(ghDriverAsync);
  CloseHandle(ghDriverSync);
  TspLog(2, "providerShutdown: Calling PostQueuedCompletionStatus");
  if ( PostQueuedCompletionStatus(ghCompletionPort, 0, 0, &gOverlappedTerminate) )
    WaitForSingleObject(*(HANDLE *)gpAsyncEventsThreadInfo, 0xFFFFFFFF);
  else
    TspLog(1, "providerShutdown: PostQueuedCompletionStatus failed");
  CloseHandle(ghDriverAsync);
  CloseHandle(ghCompletionPort);
  DefineDosDeviceA(2u, DeviceName, 0);
  CloseHandle(*(HANDLE *)gpAsyncEventsThreadInfo);
  LocalFree(*((HLOCAL *)gpAsyncEventsThreadInfo + 1));
  LocalFree(gpAsyncEventsThreadInfo);
  UninitAllocator();
  UninitializeMapper();
  return 0;
}

```

## disassembly

```asm
0x180007c20  sub     rsp, 48h
0x180007c24  mov     rax, cs:__security_cookie
0x180007c2b  xor     rax, rsp
0x180007c2e  mov     [rsp+48h+var_18], rax
0x180007c33  movsd   xmm0, qword ptr cs:aNdistapi_0; "NDISTAPI"
0x180007c3b  mov     r8d, edx
0x180007c3e  mov     al, byte ptr cs:aNdistapi_0+8; ""
0x180007c44  lea     rdx, aProvidershutdo; "providerShutdown: perfProvID(%x)"
0x180007c4b  mov     ecx, 8
0x180007c50  movsd   qword ptr [rsp+48h+DeviceName], xmm0
0x180007c56  mov     [rsp+48h+var_20], al
0x180007c5a  call    TspLog
0x180007c5f  mov     rcx, cs:ghDriverSync; hFile
0x180007c66  call    cs:__imp_CancelIo
0x180007c6d  nop     dword ptr [rax+rax+00h]
0x180007c72  mov     rcx, cs:ghDriverAsync; hFile
0x180007c79  call    cs:__imp_CancelIo
0x180007c80  nop     dword ptr [rax+rax+00h]
0x180007c85  mov     rcx, cs:ghDriverSync; hObject
0x180007c8c  call    cs:__imp_CloseHandle
0x180007c93  nop     dword ptr [rax+rax+00h]
0x180007c98  lea     rdx, aProvidershutdo_2; "providerShutdown: Calling PostQueuedCom"...
0x180007c9f  mov     ecx, 2
0x180007ca4  call    TspLog
0x180007ca9  mov     rcx, cs:ghCompletionPort; CompletionPort
0x180007cb0  lea     r9, gOverlappedTerminate; lpOverlapped
0x180007cb7  xor     r8d, r8d; dwCompletionKey
0x180007cba  xor     edx, edx; dwNumberOfBytesTransferred
0x180007cbc  call    cs:__imp_PostQueuedCompletionStatus
0x180007cc3  nop     dword ptr [rax+rax+00h]
0x180007cc8  test    eax, eax
0x180007cca  jnz     short loc_180007CDD
0x180007ccc  lea     rdx, aProvidershutdo_1; "providerShutdown: PostQueuedCompletionS"...
0x180007cd3  lea     ecx, [rax+1]
0x180007cd6  call    TspLog
0x180007cdb  jmp     short loc_180007CF6
0x180007cdd  mov     rcx, cs:gpAsyncEventsThreadInfo
0x180007ce4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007ce7  mov     rcx, [rcx]; hHandle
0x180007cea  call    cs:__imp_WaitForSingleObject
0x180007cf1  nop     dword ptr [rax+rax+00h]
0x180007cf6  mov     rcx, cs:ghDriverAsync; hObject
0x180007cfd  call    cs:__imp_CloseHandle
0x180007d04  nop     dword ptr [rax+rax+00h]
0x180007d09  mov     rcx, cs:ghCompletionPort; hObject
0x180007d10  call    cs:__imp_CloseHandle
0x180007d17  nop     dword ptr [rax+rax+00h]
0x180007d1c  xor     r8d, r8d; lpTargetPath
0x180007d1f  lea     rdx, [rsp+48h+DeviceName]; lpDeviceName
0x180007d24  lea     ecx, [r8+2]; dwFlags
0x180007d28  call    cs:__imp_DefineDosDeviceA
0x180007d2f  nop     dword ptr [rax+rax+00h]
0x180007d34  mov     rcx, cs:gpAsyncEventsThreadInfo
0x180007d3b  mov     rcx, [rcx]; hObject
0x180007d3e  call    cs:__imp_CloseHandle
0x180007d45  nop     dword ptr [rax+rax+00h]
0x180007d4a  mov     rcx, cs:gpAsyncEventsThreadInfo
0x180007d51  mov     rcx, [rcx+8]; hMem
0x180007d55  call    cs:__imp_LocalFree
0x180007d5c  nop     dword ptr [rax+rax+00h]
0x180007d61  mov     rcx, cs:gpAsyncEventsThreadInfo; hMem
0x180007d68  call    cs:__imp_LocalFree
0x180007d6f  nop     dword ptr [rax+rax+00h]
0x180007d74  call    UninitAllocator
0x180007d79  call    UninitializeMapper
0x180007d7e  xor     eax, eax
0x180007d80  mov     rcx, [rsp+48h+var_18]
0x180007d85  xor     rcx, rsp; StackCookie
0x180007d88  call    __security_check_cookie
0x180007d8d  add     rsp, 48h
0x180007d91  retn
```
