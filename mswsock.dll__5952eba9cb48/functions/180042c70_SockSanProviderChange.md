# SockSanProviderChange

- ea: `0x180042c70`
- end: `0x180042da3`
- name: `SockSanProviderChange`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x18000ed0c`
- `0x18001e5a4`
- `0x18002324c`
- `0x18003e820`
- `0x18004270c`
- `0x180042c70`
- `0x180044380`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180042d59`
- `ntdll!NtDeviceIoControlFile` at `0x180042d59`
- `WS2_32!WSAProviderConfigChange` at `0x180042c9b`
- `WS2_32!WSAProviderConfigChange` at `0x180042c9b`
- `WS2_32!__imp_WSAGetLastError` at `0x180042cab`
- `WS2_32!__imp_WSAGetLastError` at `0x180042cab`

## pseudocode

```c
__int64 SockSanProviderChange()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  HANDLE v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  SockAcquireRwLockExclusive();
  if ( !SockSanProviderChangeHandle
    || WSAProviderConfigChange(&SockSanProviderChangeHandle, &SockSanProviderChangeOvlp, 0) && WSAGetLastError() != 997 )
  {
    _InterlockedDecrement(&SockAsyncThreadReferenceCount);
    return SockReleaseRwLockExclusive(v1, v0, v2, v3);
  }
  if ( SockSanEnabled || (SockSanInitialize(), SockSanEnabled) )
  {
    v4 = SockSanHelperHandle;
    if ( !SockSanHelperHandle )
    {
      if ( (int)SockpSanRegister() < 0 )
        return SockReleaseRwLockExclusive(v1, v0, v2, v3);
      v4 = SockSanHelperHandle;
    }
    IoStatusBlock = 0;
    if ( v4 == SockSanServiceHelper )
    {
      NtDeviceIoControlFile(SockSanServiceHelper, 0, 0, 0, &IoStatusBlock, 0x1210Bu, 0, 0, 0, 0);
    }
    else
    {
      SockSanServiceHelper = v4;
      NtDeviceIoControlFile(v4, 0, 0, 0, &IoStatusBlock, 0x12107u, 0, 0, 0, 0);
    }
    SockReleaseRwLockExclusive(v6, v5, v7, v8);
    if ( !(unsigned int)SockpGetProtocolInfoArray() )
    {
      if ( !SockSanAddressNotifyContext )
        SockSanEnableActiveUpdates();
      SockAcquireRwLockExclusive();
      SockSanGetTcpipCatalogId();
      SockpSanUpdateProviderConfig();
    }
  }
  return SockReleaseRwLockExclusive(v1, v0, v2, v3);
}

```

## disassembly

```asm
0x180042c70  push    rbx
0x180042c72  sub     rsp, 60h
0x180042c76  call    SockAcquireRwLockExclusive
0x180042c7b  xor     ebx, ebx
0x180042c7d  cmp     cs:SockSanProviderChangeHandle, rbx
0x180042c84  jz      loc_180042D92
0x180042c8a  xor     r8d, r8d; lpCompletionRoutine
0x180042c8d  lea     rdx, SockSanProviderChangeOvlp; lpOverlapped
0x180042c94  lea     rcx, SockSanProviderChangeHandle; lpNotificationHandle
0x180042c9b  call    cs:__imp_WSAProviderConfigChange
0x180042ca2  nop     dword ptr [rax+rax+00h]
0x180042ca7  test    eax, eax
0x180042ca9  jz      short loc_180042CC2
0x180042cab  call    cs:__imp_WSAGetLastError
0x180042cb2  nop     dword ptr [rax+rax+00h]
0x180042cb7  cmp     eax, 3E5h
0x180042cbc  jnz     loc_180042D92
0x180042cc2  cmp     cs:SockSanEnabled, ebx
0x180042cc8  jnz     short loc_180042CDB
0x180042cca  call    SockSanInitialize
0x180042ccf  cmp     cs:SockSanEnabled, ebx
0x180042cd5  jz      loc_180042D99
0x180042cdb  mov     rcx, cs:SockSanHelperHandle
0x180042ce2  test    rcx, rcx
0x180042ce5  jnz     short loc_180042CFB
0x180042ce7  call    SockpSanRegister
0x180042cec  test    eax, eax
0x180042cee  js      loc_180042D99
0x180042cf4  mov     rcx, cs:SockSanHelperHandle
0x180042cfb  mov     rax, cs:SockSanServiceHelper
0x180042d02  xor     r9d, r9d; ApcContext
0x180042d05  mov     [rsp+68h+OutputBufferLength], ebx; OutputBufferLength
0x180042d09  xor     r8d, r8d; ApcRoutine
0x180042d0c  mov     [rsp+68h+OutputBuffer], rbx; OutputBuffer
0x180042d11  xor     edx, edx; Event
0x180042d13  mov     [rsp+68h+InputBufferLength], ebx; InputBufferLength
0x180042d17  xorps   xmm0, xmm0
0x180042d1a  mov     [rsp+68h+InputBuffer], rbx; InputBuffer
0x180042d1f  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180042d24  cmp     rcx, rax
0x180042d27  jz      short loc_180042D44
0x180042d29  lea     rax, [rsp+68h+var_18]
0x180042d2e  mov     [rsp+68h+IoControlCode], 12107h
0x180042d36  mov     [rsp+68h+IoStatusBlock], rax
0x180042d3b  mov     cs:SockSanServiceHelper, rcx
0x180042d42  jmp     short loc_180042D59
0x180042d44  lea     rcx, [rsp+68h+var_18]
0x180042d49  mov     [rsp+68h+IoControlCode], 1210Bh; IoControlCode
0x180042d51  mov     [rsp+68h+IoStatusBlock], rcx; IoStatusBlock
0x180042d56  mov     rcx, rax; FileHandle
0x180042d59  call    cs:__imp_NtDeviceIoControlFile
0x180042d60  nop     dword ptr [rax+rax+00h]
0x180042d65  call    SockReleaseRwLockExclusive
0x180042d6a  call    SockpGetProtocolInfoArray
0x180042d6f  test    eax, eax
0x180042d71  jnz     short loc_180042D99
0x180042d73  cmp     cs:SockSanAddressNotifyContext, rbx
0x180042d7a  jnz     short loc_180042D81
0x180042d7c  call    SockSanEnableActiveUpdates
0x180042d81  call    SockAcquireRwLockExclusive
0x180042d86  call    SockSanGetTcpipCatalogId
0x180042d8b  call    SockpSanUpdateProviderConfig
0x180042d90  jmp     short loc_180042D99
0x180042d92  lock dec cs:SockAsyncThreadReferenceCount
0x180042d99  add     rsp, 60h
0x180042d9d  pop     rbx
0x180042d9e  jmp     SockReleaseRwLockExclusive
```
