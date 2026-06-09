# SockSanProviderAddressUpdate

- ea: `0x180042bc8`
- end: `0x180042c68`
- name: `SockSanProviderAddressUpdate`
- size: `160`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017810`
- `0x180018ea0`
- `0x18001c860`
- `0x180023398`
- `0x180025530`
- `0x18003b008`
- `0x18004270c`
- `0x180042970`
- `0x18004e9dc`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x18000ed0c`
- `0x18002324c`
- `0x18003e820`
- `0x18003eb24`
- `0x180042bc8`
- `0x18004eda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042c24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042c24`

## pseudocode

```c
__int64 SockSanProviderAddressUpdate()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9

  SockAcquireRwLockExclusive();
  if ( !SockWspStartupCount )
    return SockReleaseRwLockExclusive(v1, v0, v2, v3);
  v1 = 259;
  if ( SockSanAddressNotifyStatusBlock == 259
    && (SockSanAddressNotifyStatusBlockV6 == 259 || !dword_180063524)
    && SockSanEnabled != 2 )
  {
    return SockReleaseRwLockExclusive(v1, v0, v2, v3);
  }
  if ( qword_180064748 || SockSanEnabled == 2 && !WaitForSingleObject(SockSanSCAutostartEvent, 0) )
  {
    SockReleaseRwLockExclusive(v1, v0, v2, v3);
    result = SockpGetProtocolInfoArray();
    if ( (_DWORD)result )
      return result;
    SockAcquireRwLockExclusive();
    SockSanGetTcpipCatalogId();
    SockpSanUpdateProviderConfig();
  }
  else
  {
    SockpSanUpdateSubnetMap();
  }
  SockReleaseRwLockExclusive(v6, v5, v7, v8);
  return SockSanScanListenSocksForProviderChange();
}

```

## disassembly

```asm
0x180042bc8  sub     rsp, 28h
0x180042bcc  call    SockAcquireRwLockExclusive
0x180042bd1  cmp     cs:SockWspStartupCount, 0
0x180042bd8  jz      short loc_180042C03
0x180042bda  mov     eax, cs:SockSanEnabled
0x180042be0  mov     ecx, 103h
0x180042be5  cmp     cs:SockSanAddressNotifyStatusBlock, ecx
0x180042beb  jnz     short loc_180042C0C
0x180042bed  cmp     cs:SockSanAddressNotifyStatusBlockV6, ecx
0x180042bf3  jz      short loc_180042BFE
0x180042bf5  cmp     cs:dword_180063524, 0
0x180042bfc  jnz     short loc_180042C0C
0x180042bfe  cmp     eax, 2
0x180042c01  jz      short loc_180042C0C
0x180042c03  add     rsp, 28h
0x180042c07  jmp     SockReleaseRwLockExclusive
0x180042c0c  cmp     cs:qword_180064748, 0
0x180042c14  jnz     short loc_180042C3B
0x180042c16  cmp     eax, 2
0x180042c19  jnz     short loc_180042C34
0x180042c1b  mov     rcx, cs:SockSanSCAutostartEvent; hHandle
0x180042c22  xor     edx, edx; dwMilliseconds
0x180042c24  call    cs:__imp_WaitForSingleObject
0x180042c2b  nop     dword ptr [rax+rax+00h]
0x180042c30  test    eax, eax
0x180042c32  jz      short loc_180042C3B
0x180042c34  call    SockpSanUpdateSubnetMap
0x180042c39  jmp     short loc_180042C58
0x180042c3b  call    SockReleaseRwLockExclusive
0x180042c40  call    SockpGetProtocolInfoArray
0x180042c45  test    eax, eax
0x180042c47  jnz     short loc_180042C62
0x180042c49  call    SockAcquireRwLockExclusive
0x180042c4e  call    SockSanGetTcpipCatalogId
0x180042c53  call    SockpSanUpdateProviderConfig
0x180042c58  call    SockReleaseRwLockExclusive
0x180042c5d  call    SockSanScanListenSocksForProviderChange
0x180042c62  add     rsp, 28h
0x180042c66  retn
```
