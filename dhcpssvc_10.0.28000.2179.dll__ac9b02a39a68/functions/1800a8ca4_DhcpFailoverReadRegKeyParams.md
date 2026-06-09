# DhcpFailoverReadRegKeyParams

- ea: `0x1800a8ca4`
- end: `0x1800a9250`
- name: `DhcpFailoverReadRegKeyParams`
- size: `1452`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180084600`

## callees

- `0x1800521dc`
- `0x180083044`
- `0x1800a8ca4`
- `0x1800a92b4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800a922d`
- `ADVAPI32!RegCloseKey` at `0x1800a922d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a8d52`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a8d52`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8d95`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8dee`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8e2f`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8e89`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8eca`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8f0f`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8f50`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8f91`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8fd2`
- `ADVAPI32!RegQueryValueExW` at `0x1800a9013`
- `ADVAPI32!RegQueryValueExW` at `0x1800a9054`
- `ADVAPI32!RegQueryValueExW` at `0x1800a9095`
- `ADVAPI32!RegQueryValueExW` at `0x1800a90e8`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8d95`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8dee`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8e2f`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8e89`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8eca`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8f0f`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8f50`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8f91`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8fd2`
- `ADVAPI32!RegQueryValueExW` at `0x1800a9013`
- `ADVAPI32!RegQueryValueExW` at `0x1800a9054`
- `ADVAPI32!RegQueryValueExW` at `0x1800a9095`
- `ADVAPI32!RegQueryValueExW` at `0x1800a90e8`
- `KERNEL32!RegGetValueW` at `0x1800a9125`
- `KERNEL32!RegGetValueW` at `0x1800a9194`
- `KERNEL32!RegGetValueW` at `0x1800a9125`
- `KERNEL32!RegGetValueW` at `0x1800a9194`
- `KERNEL32!HeapAlloc` at `0x1800a9158`
- `KERNEL32!HeapAlloc` at `0x1800a91c0`
- `KERNEL32!HeapAlloc` at `0x1800a9158`
- `KERNEL32!HeapAlloc` at `0x1800a91c0`
- `KERNEL32!HeapFree` at `0x1800a921d`
- `KERNEL32!HeapFree` at `0x1800a921d`

## string_xrefs

- `0x1800a8ccd`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x1800a904d`: `DhcpFailoverEnableCommInt`

## pseudocode

```c
LSTATUS DhcpFailoverReadRegKeyParams()
{
  LSTATUS ValueW; // ebx
  LSTATUS v1; // eax
  void *v2; // rdi
  wchar_t *v3; // rax
  __int64 v4; // rcx
  LSTATUS result; // eax
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF

  *(_DWORD *)&gFailoverLeaseDbQMaxSize = 400000;
  Type = 0;
  *(_WORD *)&gDhcpFailoverPort = 647;
  cbData = 0;
  hKey = HKEY_LOCAL_MACHINE;
  *(_DWORD *)&gFailoverConnRetryTime = 15;
  *(_DWORD *)&gFailoverFreePacketPoolSize = 3072;
  *(_DWORD *)&gFailoverRecvTimerVal = 180;
  *(_DWORD *)&gFailoverAddressRebalanceIntv = 300;
  *(_DWORD *)&gFailoverMaxUnackedBndUpds = 200;
  *(_DWORD *)&gFailoverMaxBndRecordsperPacket = 16;
  *(_DWORD *)&isDhcpFailoverTestEnv = 0;
  *(_DWORD *)&gMessageSyncDeltaTime = 60;
  *(_DWORD *)&gFailoverAddressAllocation = 1000;
  *(_DWORD *)&gFailoverEnableCommInt = 0;
  gHAlgorithm = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\DHCPServer\\Parameters",
             0,
             0xFu,
             &hKey);
  if ( !ValueW )
  {
    cbData = 4;
    ValueW = RegQueryValueExW(hKey, L"DhcpFailoverConnectionRetryTime", 0, &Type, &gFailoverConnRetryTime, &cbData);
    if ( (ValueW & 0xFFFFFFFD) == 0 )
    {
      if ( !*(_DWORD *)&gFailoverConnRetryTime )
        *(_DWORD *)&gFailoverConnRetryTime = 60;
      cbData = 4;
      ValueW = RegQueryValueExW(
                 hKey,
                 L"DhcpFailoverMaxUnAckedLeaseUpds",
                 0,
                 &Type,
                 &gFailoverMaxUnackedBndUpds,
                 &cbData);
      if ( (ValueW & 0xFFFFFFFD) == 0 )
      {
        cbData = 4;
        v1 = RegQueryValueExW(
               hKey,
               L"DhcpFailoverMaxBndRecordPerPacket",
               0,
               &Type,
               &gFailoverMaxBndRecordsperPacket,
               &cbData);
        ValueW = v1;
        if ( v1 )
        {
          if ( v1 != 2 )
            goto LABEL_36;
        }
        else if ( *(_DWORD *)&gFailoverMaxBndRecordsperPacket > 0x10u )
        {
          *(_DWORD *)&gFailoverMaxBndRecordsperPacket = 16;
        }
        cbData = 4;
        ValueW = RegQueryValueExW(hKey, L"DhcpFailoverReceiveTimer", 0, &Type, &gFailoverRecvTimerVal, &cbData);
        if ( (ValueW & 0xFFFFFFFD) == 0 )
        {
          cbData = 4;
          ValueW = RegQueryValueExW(
                     hKey,
                     L"DhcpFailoverAddrRebalacingTimeInt",
                     0,
                     &Type,
                     &gFailoverAddressRebalanceIntv,
                     &cbData);
          if ( (ValueW & 0xFFFFFFFD) == 0 )
          {
            cbData = 2;
            ValueW = RegQueryValueExW(hKey, L"DhcpFailoverPort", 0, &Type, &gDhcpFailoverPort, &cbData);
            if ( (ValueW & 0xFFFFFFFD) == 0 )
            {
              cbData = 4;
              ValueW = RegQueryValueExW(hKey, L"DhcpFailoverTestHook", 0, &Type, &isDhcpFailoverTestEnv, &cbData);
              if ( (ValueW & 0xFFFFFFFD) == 0 )
              {
                cbData = 4;
                ValueW = RegQueryValueExW(
                           hKey,
                           L"DhcpFailoverLeaseDbQMaxSize",
                           0,
                           &Type,
                           &gFailoverLeaseDbQMaxSize,
                           &cbData);
                if ( (ValueW & 0xFFFFFFFD) == 0 )
                {
                  cbData = 4;
                  ValueW = RegQueryValueExW(
                             hKey,
                             L"DhcpFailoverFreePacketPoolSize",
                             0,
                             &Type,
                             &gFailoverFreePacketPoolSize,
                             &cbData);
                  if ( (ValueW & 0xFFFFFFFD) == 0 )
                  {
                    cbData = 4;
                    ValueW = RegQueryValueExW(hKey, L"DhcpMsgSyncDeltaTime", 0, &Type, &gMessageSyncDeltaTime, &cbData);
                    if ( (ValueW & 0xFFFFFFFD) == 0 )
                    {
                      cbData = 4;
                      ValueW = RegQueryValueExW(
                                 hKey,
                                 L"DhcpFailoverEnableCommInt",
                                 0,
                                 &Type,
                                 &gFailoverEnableCommInt,
                                 &cbData);
                      if ( (ValueW & 0xFFFFFFFD) == 0 )
                      {
                        cbData = 4;
                        ValueW = RegQueryValueExW(
                                   hKey,
                                   L"DhcpFailoverStartUpTimer",
                                   0,
                                   &Type,
                                   &gDhcpFailoverStartUpTime,
                                   &cbData);
                        if ( (ValueW & 0xFFFFFFFD) == 0 )
                        {
                          if ( !*(_DWORD *)&gMessageSyncDeltaTime )
                            *(_DWORD *)&gMessageSyncDeltaTime = 60;
                          cbData = 4;
                          ValueW = RegQueryValueExW(
                                     hKey,
                                     L"DhcpFailoverMaxAddressAllocation",
                                     0,
                                     &Type,
                                     &gFailoverAddressAllocation,
                                     &cbData);
                          if ( (ValueW & 0xFFFFFFFD) == 0 )
                          {
                            ValueW = RegGetValueW(hKey, 0, L"DhcpFailoverCryptoAlgorithm", 2u, 0, 0, &cbData);
                            if ( ValueW == 2 || !cbData )
                            {
                              cbData = 14;
                              ValueW = 8;
                              v3 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, 0xEu);
                              v2 = v3;
                              if ( !v3 )
                                goto LABEL_36;
                              StringCbPrintfW(v3, cbData, L"SHA256");
                            }
                            else
                            {
                              if ( ValueW )
                                goto LABEL_36;
                              ValueW = 8;
                              v2 = HeapAlloc(gDhcpHeap, 8u, cbData);
                              if ( !v2 )
                                goto LABEL_36;
                              ValueW = RegGetValueW(hKey, 0, L"DhcpFailoverCryptoAlgorithm", 2u, 0, v2, &cbData);
                              if ( (ValueW & 0xFFFFFFFD) != 0 )
                              {
LABEL_35:
                                HeapFree(gDhcpHeap, 0, v2);
                                goto LABEL_36;
                              }
                            }
                            ValueW = DhcpValidateAlgorithmProvider((LPCWSTR)v2);
                            if ( ValueW && (Microsoft_Windows_DHCP_ServerEnableBits & 0x40) != 0 )
                              McTemplateU0z_EventWriteTransfer(v4, &InvalidAlgorithmProvider, v2);
                            if ( v2 )
                              goto LABEL_35;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_36:
  result = RegCloseKey(hKey);
  if ( result == 2 )
    result = 0;
  if ( ValueW )
    return ValueW;
  return result;
}

```

## disassembly

```asm
0x1800a8ca4  push    rbp
0x1800a8ca6  push    rbx
0x1800a8ca7  push    rsi
0x1800a8ca8  push    rdi
0x1800a8ca9  push    r14
0x1800a8cab  mov     rbp, rsp
0x1800a8cae  sub     rsp, 40h
0x1800a8cb2  xor     esi, esi
0x1800a8cb4  mov     cs:gFailoverLeaseDbQMaxSize, 61A80h
0x1800a8cbe  mov     eax, 287h
0x1800a8cc3  mov     [rbp+Type], esi
0x1800a8cc6  mov     cs:gDhcpFailoverPort, ax
0x1800a8ccd  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x1800a8cd4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a8cdb  mov     [rbp+cbData], esi
0x1800a8cde  lea     r9d, [rsi+0Fh]; samDesired
0x1800a8ce2  mov     [rbp+hKey], rcx
0x1800a8ce6  lea     rax, [rbp+hKey]
0x1800a8cea  mov     cs:gFailoverConnRetryTime, r9d
0x1800a8cf1  xor     r8d, r8d; ulOptions
0x1800a8cf4  mov     cs:gFailoverFreePacketPoolSize, 0C00h
0x1800a8cfe  mov     cs:gFailoverRecvTimerVal, 0B4h
0x1800a8d08  mov     cs:gFailoverAddressRebalanceIntv, 12Ch
0x1800a8d12  mov     cs:gFailoverMaxUnackedBndUpds, 0C8h
0x1800a8d1c  mov     cs:gFailoverMaxBndRecordsperPacket, 10h
0x1800a8d26  mov     cs:isDhcpFailoverTestEnv, esi
0x1800a8d2c  mov     cs:gMessageSyncDeltaTime, 3Ch ; '<'
0x1800a8d36  mov     cs:gFailoverAddressAllocation, 3E8h
0x1800a8d40  mov     cs:gFailoverEnableCommInt, esi
0x1800a8d46  mov     cs:gHAlgorithm, rsi
0x1800a8d4d  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a8d52  call    cs:__imp_RegOpenKeyExW
0x1800a8d59  nop     dword ptr [rax+rax+00h]
0x1800a8d5e  mov     ebx, eax
0x1800a8d60  test    eax, eax
0x1800a8d62  jnz     loc_1800A9229
0x1800a8d68  mov     rcx, [rbp+hKey]; hKey
0x1800a8d6c  lea     rax, [rbp+cbData]
0x1800a8d70  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8d75  lea     edi, [rsi+4]
0x1800a8d78  lea     rax, gFailoverConnRetryTime
0x1800a8d7f  mov     [rbp+cbData], edi
0x1800a8d82  lea     r9, [rbp+Type]; lpType
0x1800a8d86  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8d8b  xor     r8d, r8d; lpReserved
0x1800a8d8e  lea     rdx, aDhcpfailoverco; "DhcpFailoverConnectionRetryTime"
0x1800a8d95  call    cs:__imp_RegQueryValueExW
0x1800a8d9c  nop     dword ptr [rax+rax+00h]
0x1800a8da1  mov     r14d, 0FFFFFFFDh
0x1800a8da7  mov     ebx, eax
0x1800a8da9  test    r14d, eax
0x1800a8dac  jnz     loc_1800A9229
0x1800a8db2  cmp     cs:gFailoverConnRetryTime, esi
0x1800a8db8  jnz     short loc_1800A8DC4
0x1800a8dba  mov     cs:gFailoverConnRetryTime, 3Ch ; '<'
0x1800a8dc4  mov     rcx, [rbp+hKey]; hKey
0x1800a8dc8  lea     rax, [rbp+cbData]
0x1800a8dcc  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8dd1  lea     r9, [rbp+Type]; lpType
0x1800a8dd5  lea     rax, gFailoverMaxUnackedBndUpds
0x1800a8ddc  mov     [rbp+cbData], edi
0x1800a8ddf  xor     r8d, r8d; lpReserved
0x1800a8de2  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8de7  lea     rdx, aDhcpfailoverma_1; "DhcpFailoverMaxUnAckedLeaseUpds"
0x1800a8dee  call    cs:__imp_RegQueryValueExW
0x1800a8df5  nop     dword ptr [rax+rax+00h]
0x1800a8dfa  mov     ebx, eax
0x1800a8dfc  test    r14d, eax
0x1800a8dff  jnz     loc_1800A9229
0x1800a8e05  mov     rcx, [rbp+hKey]; hKey
0x1800a8e09  lea     rax, [rbp+cbData]
0x1800a8e0d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8e12  lea     r9, [rbp+Type]; lpType
0x1800a8e16  lea     rax, gFailoverMaxBndRecordsperPacket
0x1800a8e1d  mov     [rbp+cbData], edi
0x1800a8e20  xor     r8d, r8d; lpReserved
0x1800a8e23  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8e28  lea     rdx, aDhcpfailoverma; "DhcpFailoverMaxBndRecordPerPacket"
0x1800a8e2f  call    cs:__imp_RegQueryValueExW
0x1800a8e36  nop     dword ptr [rax+rax+00h]
0x1800a8e3b  mov     ebx, eax
0x1800a8e3d  test    eax, eax
0x1800a8e3f  jz      short loc_1800A8E4C
0x1800a8e41  cmp     eax, 2
0x1800a8e44  jnz     loc_1800A9229
0x1800a8e4a  jmp     short loc_1800A8E5F
0x1800a8e4c  cmp     cs:gFailoverMaxBndRecordsperPacket, 10h
0x1800a8e53  jbe     short loc_1800A8E5F
0x1800a8e55  mov     cs:gFailoverMaxBndRecordsperPacket, 10h
0x1800a8e5f  mov     rcx, [rbp+hKey]; hKey
0x1800a8e63  lea     rax, [rbp+cbData]
0x1800a8e67  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8e6c  lea     r9, [rbp+Type]; lpType
0x1800a8e70  lea     rax, gFailoverRecvTimerVal
0x1800a8e77  mov     [rbp+cbData], edi
0x1800a8e7a  xor     r8d, r8d; lpReserved
0x1800a8e7d  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8e82  lea     rdx, aDhcpfailoverre_0; "DhcpFailoverReceiveTimer"
0x1800a8e89  call    cs:__imp_RegQueryValueExW
0x1800a8e90  nop     dword ptr [rax+rax+00h]
0x1800a8e95  mov     ebx, eax
0x1800a8e97  test    r14d, eax
0x1800a8e9a  jnz     loc_1800A9229
0x1800a8ea0  mov     rcx, [rbp+hKey]; hKey
0x1800a8ea4  lea     rax, [rbp+cbData]
0x1800a8ea8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8ead  lea     r9, [rbp+Type]; lpType
0x1800a8eb1  lea     rax, gFailoverAddressRebalanceIntv
0x1800a8eb8  mov     [rbp+cbData], edi
0x1800a8ebb  xor     r8d, r8d; lpReserved
0x1800a8ebe  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8ec3  lea     rdx, aDhcpfailoverad; "DhcpFailoverAddrRebalacingTimeInt"
0x1800a8eca  call    cs:__imp_RegQueryValueExW
0x1800a8ed1  nop     dword ptr [rax+rax+00h]
0x1800a8ed6  mov     ebx, eax
0x1800a8ed8  test    r14d, eax
0x1800a8edb  jnz     loc_1800A9229
0x1800a8ee1  mov     rcx, [rbp+hKey]; hKey
0x1800a8ee5  lea     rax, [rbp+cbData]
0x1800a8ee9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8eee  lea     r9, [rbp+Type]; lpType
0x1800a8ef2  lea     rax, gDhcpFailoverPort
0x1800a8ef9  mov     [rbp+cbData], 2
0x1800a8f00  xor     r8d, r8d; lpReserved
0x1800a8f03  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8f08  lea     rdx, aDhcpfailoverpo; "DhcpFailoverPort"
0x1800a8f0f  call    cs:__imp_RegQueryValueExW
0x1800a8f16  nop     dword ptr [rax+rax+00h]
0x1800a8f1b  mov     ebx, eax
0x1800a8f1d  test    r14d, eax
0x1800a8f20  jnz     loc_1800A9229
0x1800a8f26  mov     rcx, [rbp+hKey]; hKey
0x1800a8f2a  lea     rax, [rbp+cbData]
0x1800a8f2e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8f33  lea     r9, [rbp+Type]; lpType
0x1800a8f37  lea     rax, isDhcpFailoverTestEnv
0x1800a8f3e  mov     [rbp+cbData], edi
0x1800a8f41  xor     r8d, r8d; lpReserved
0x1800a8f44  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8f49  lea     rdx, aDhcpfailoverte; "DhcpFailoverTestHook"
0x1800a8f50  call    cs:__imp_RegQueryValueExW
0x1800a8f57  nop     dword ptr [rax+rax+00h]
0x1800a8f5c  mov     ebx, eax
0x1800a8f5e  test    r14d, eax
0x1800a8f61  jnz     loc_1800A9229
0x1800a8f67  mov     rcx, [rbp+hKey]; hKey
0x1800a8f6b  lea     rax, [rbp+cbData]
0x1800a8f6f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8f74  lea     r9, [rbp+Type]; lpType
0x1800a8f78  lea     rax, gFailoverLeaseDbQMaxSize
0x1800a8f7f  mov     [rbp+cbData], edi
0x1800a8f82  xor     r8d, r8d; lpReserved
0x1800a8f85  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8f8a  lea     rdx, aDhcpfailoverle; "DhcpFailoverLeaseDbQMaxSize"
0x1800a8f91  call    cs:__imp_RegQueryValueExW
0x1800a8f98  nop     dword ptr [rax+rax+00h]
0x1800a8f9d  mov     ebx, eax
0x1800a8f9f  test    r14d, eax
0x1800a8fa2  jnz     loc_1800A9229
0x1800a8fa8  mov     rcx, [rbp+hKey]; hKey
0x1800a8fac  lea     rax, [rbp+cbData]
0x1800a8fb0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8fb5  lea     r9, [rbp+Type]; lpType
0x1800a8fb9  lea     rax, gFailoverFreePacketPoolSize
0x1800a8fc0  mov     [rbp+cbData], edi
0x1800a8fc3  xor     r8d, r8d; lpReserved
0x1800a8fc6  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8fcb  lea     rdx, aDhcpfailoverfr; "DhcpFailoverFreePacketPoolSize"
0x1800a8fd2  call    cs:__imp_RegQueryValueExW
0x1800a8fd9  nop     dword ptr [rax+rax+00h]
0x1800a8fde  mov     ebx, eax
0x1800a8fe0  test    r14d, eax
0x1800a8fe3  jnz     loc_1800A9229
0x1800a8fe9  mov     rcx, [rbp+hKey]; hKey
0x1800a8fed  lea     rax, [rbp+cbData]
0x1800a8ff1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8ff6  lea     r9, [rbp+Type]; lpType
0x1800a8ffa  lea     rax, gMessageSyncDeltaTime
0x1800a9001  mov     [rbp+cbData], edi
0x1800a9004  xor     r8d, r8d; lpReserved
0x1800a9007  mov     [rsp+40h+phkResult], rax; lpData
0x1800a900c  lea     rdx, aDhcpmsgsyncdel; "DhcpMsgSyncDeltaTime"
0x1800a9013  call    cs:__imp_RegQueryValueExW
0x1800a901a  nop     dword ptr [rax+rax+00h]
0x1800a901f  mov     ebx, eax
0x1800a9021  test    r14d, eax
0x1800a9024  jnz     loc_1800A9229
0x1800a902a  mov     rcx, [rbp+hKey]; hKey
0x1800a902e  lea     rax, [rbp+cbData]
0x1800a9032  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a9037  lea     r9, [rbp+Type]; lpType
0x1800a903b  lea     rax, gFailoverEnableCommInt
0x1800a9042  mov     [rbp+cbData], edi
0x1800a9045  xor     r8d, r8d; lpReserved
0x1800a9048  mov     [rsp+40h+phkResult], rax; lpData
0x1800a904d  lea     rdx, aDhcpfailoveren; "DhcpFailoverEnableCommInt"
0x1800a9054  call    cs:__imp_RegQueryValueExW
0x1800a905b  nop     dword ptr [rax+rax+00h]
0x1800a9060  mov     ebx, eax
0x1800a9062  test    r14d, eax
0x1800a9065  jnz     loc_1800A9229
0x1800a906b  mov     rcx, [rbp+hKey]; hKey
0x1800a906f  lea     rax, [rbp+cbData]
0x1800a9073  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a9078  lea     r9, [rbp+Type]; lpType
0x1800a907c  lea     rax, gDhcpFailoverStartUpTime
0x1800a9083  mov     [rbp+cbData], edi
0x1800a9086  xor     r8d, r8d; lpReserved
0x1800a9089  mov     [rsp+40h+phkResult], rax; lpData
0x1800a908e  lea     rdx, aDhcpfailoverst; "DhcpFailoverStartUpTimer"
0x1800a9095  call    cs:__imp_RegQueryValueExW
0x1800a909c  nop     dword ptr [rax+rax+00h]
0x1800a90a1  mov     ebx, eax
0x1800a90a3  test    r14d, eax
0x1800a90a6  jnz     loc_1800A9229
0x1800a90ac  cmp     cs:gMessageSyncDeltaTime, esi
0x1800a90b2  jnz     short loc_1800A90BE
0x1800a90b4  mov     cs:gMessageSyncDeltaTime, 3Ch ; '<'
0x1800a90be  mov     rcx, [rbp+hKey]; hKey
0x1800a90c2  lea     rax, [rbp+cbData]
0x1800a90c6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a90cb  lea     r9, [rbp+Type]; lpType
0x1800a90cf  lea     rax, gFailoverAddressAllocation
0x1800a90d6  mov     [rbp+cbData], edi
0x1800a90d9  xor     r8d, r8d; lpReserved
0x1800a90dc  mov     [rsp+40h+phkResult], rax; lpData
0x1800a90e1  lea     rdx, aDhcpfailoverma_0; "DhcpFailoverMaxAddressAllocation"
0x1800a90e8  call    cs:__imp_RegQueryValueExW
0x1800a90ef  nop     dword ptr [rax+rax+00h]
0x1800a90f4  mov     ebx, eax
0x1800a90f6  test    r14d, eax
0x1800a90f9  jnz     loc_1800A9229
0x1800a90ff  mov     rcx, [rbp+hKey]; hkey
0x1800a9103  lea     rax, [rbp+cbData]
0x1800a9107  mov     [rsp+40h+pcbData], rax; pcbData
0x1800a910c  lea     r8, Value; "DhcpFailoverCryptoAlgorithm"
0x1800a9113  mov     [rsp+40h+lpcbData], rsi; pvData
0x1800a9118  mov     r9d, 2; dwFlags
0x1800a911e  xor     edx, edx; lpSubKey
0x1800a9120  mov     [rsp+40h+phkResult], rsi; pdwType
0x1800a9125  call    cs:__imp_RegGetValueW
0x1800a912c  nop     dword ptr [rax+rax+00h]
0x1800a9131  mov     ebx, eax
0x1800a9133  cmp     eax, 2
0x1800a9136  jz      short loc_1800A91A9
0x1800a9138  mov     eax, [rbp+cbData]
0x1800a913b  test    eax, eax
0x1800a913d  jz      short loc_1800A91A9
0x1800a913f  test    ebx, ebx
0x1800a9141  jnz     loc_1800A9229
0x1800a9147  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a914e  mov     ebx, 8
0x1800a9153  mov     edx, ebx; dwFlags
0x1800a9155  mov     r8d, eax; dwBytes
0x1800a9158  call    cs:__imp_HeapAlloc
0x1800a915f  nop     dword ptr [rax+rax+00h]
0x1800a9164  mov     rdi, rax
0x1800a9167  test    rax, rax
0x1800a916a  jz      loc_1800A9229
0x1800a9170  mov     rcx, [rbp+hKey]; hkey
0x1800a9174  lea     rax, [rbp+cbData]
0x1800a9178  mov     [rsp+40h+pcbData], rax; pcbData
0x1800a917d  lea     r9d, [rbx-6]; dwFlags
0x1800a9181  mov     [rsp+40h+lpcbData], rdi; pvData
0x1800a9186  lea     r8, Value; "DhcpFailoverCryptoAlgorithm"
0x1800a918d  xor     edx, edx; lpSubKey
0x1800a918f  mov     [rsp+40h+phkResult], rsi; pdwType
0x1800a9194  call    cs:__imp_RegGetValueW
0x1800a919b  nop     dword ptr [rax+rax+00h]
0x1800a91a0  mov     ebx, eax
0x1800a91a2  test    r14d, eax
0x1800a91a5  jz      short loc_1800A91E6
0x1800a91a7  jmp     short loc_1800A9211
0x1800a91a9  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a91b0  mov     r8d, 0Eh; dwBytes
0x1800a91b6  mov     [rbp+cbData], r8d
0x1800a91ba  lea     ebx, [r8-6]
0x1800a91be  mov     edx, ebx; dwFlags
0x1800a91c0  call    cs:__imp_HeapAlloc
0x1800a91c7  nop     dword ptr [rax+rax+00h]
0x1800a91cc  mov     rdi, rax
0x1800a91cf  test    rax, rax
0x1800a91d2  jz      short loc_1800A9229
0x1800a91d4  mov     edx, [rbp+cbData]; cbDest
0x1800a91d7  lea     r8, aSha256; "SHA256"
0x1800a91de  mov     rcx, rax; pszDest
0x1800a91e1  call    StringCbPrintfW
0x1800a91e6  mov     rcx, rdi; pszAlgId
0x1800a91e9  call    DhcpValidateAlgorithmProvider
0x1800a91ee  mov     ebx, eax
0x1800a91f0  test    eax, eax
0x1800a91f2  jz      short loc_1800A920C
0x1800a91f4  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 40h
0x1800a91fb  jz      short loc_1800A920C
0x1800a91fd  mov     r8, rdi
0x1800a9200  lea     rdx, InvalidAlgorithmProvider
0x1800a9207  call    McTemplateU0z_EventWriteTransfer
0x1800a920c  test    rdi, rdi
0x1800a920f  jz      short loc_1800A9229
0x1800a9211  mov     rcx, cs:gDhcpHeap; hHeap
  ... truncated ...
```
