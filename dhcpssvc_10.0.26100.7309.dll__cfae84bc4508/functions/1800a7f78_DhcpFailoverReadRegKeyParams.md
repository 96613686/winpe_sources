# DhcpFailoverReadRegKeyParams

- ea: `0x1800a7f78`
- end: `0x1800a8544`
- name: `DhcpFailoverReadRegKeyParams`
- size: `1484`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008474c`

## callees

- `0x1800524d4`
- `0x18008318c`
- `0x1800a7f78`
- `0x1800a85a8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800a8517`
- `ADVAPI32!RegCloseKey` at `0x1800a8517`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a8033`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a8033`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8076`
- `ADVAPI32!RegQueryValueExW` at `0x1800a80d0`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8111`
- `ADVAPI32!RegQueryValueExW` at `0x1800a816b`
- `ADVAPI32!RegQueryValueExW` at `0x1800a81ac`
- `ADVAPI32!RegQueryValueExW` at `0x1800a81f1`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8232`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8273`
- `ADVAPI32!RegQueryValueExW` at `0x1800a82b4`
- `ADVAPI32!RegQueryValueExW` at `0x1800a82f5`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8336`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8377`
- `ADVAPI32!RegQueryValueExW` at `0x1800a83cb`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8076`
- `ADVAPI32!RegQueryValueExW` at `0x1800a80d0`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8111`
- `ADVAPI32!RegQueryValueExW` at `0x1800a816b`
- `ADVAPI32!RegQueryValueExW` at `0x1800a81ac`
- `ADVAPI32!RegQueryValueExW` at `0x1800a81f1`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8232`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8273`
- `ADVAPI32!RegQueryValueExW` at `0x1800a82b4`
- `ADVAPI32!RegQueryValueExW` at `0x1800a82f5`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8336`
- `ADVAPI32!RegQueryValueExW` at `0x1800a8377`
- `ADVAPI32!RegQueryValueExW` at `0x1800a83cb`
- `KERNEL32!RegGetValueW` at `0x1800a8408`
- `KERNEL32!RegGetValueW` at `0x1800a847a`
- `KERNEL32!RegGetValueW` at `0x1800a8408`
- `KERNEL32!RegGetValueW` at `0x1800a847a`
- `KERNEL32!HeapAlloc` at `0x1800a8439`
- `KERNEL32!HeapAlloc` at `0x1800a84a8`
- `KERNEL32!HeapAlloc` at `0x1800a8439`
- `KERNEL32!HeapAlloc` at `0x1800a84a8`
- `KERNEL32!HeapFree` at `0x1800a8507`
- `KERNEL32!HeapFree` at `0x1800a8507`

## string_xrefs

- `0x1800a7fa8`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x1800a832f`: `DhcpFailoverEnableCommInt`

## pseudocode

```c
LSTATUS DhcpFailoverReadRegKeyParams()
{
  WCHAR *v0; // rsi
  LSTATUS ValueW; // ebx
  LSTATUS v2; // eax
  int v3; // edi
  wchar_t *v4; // rax
  __int64 v5; // rcx
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
  v0 = 0;
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
  if ( ValueW )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverConnectionRetryTime", 0, &Type, &gFailoverConnRetryTime, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  if ( !*(_DWORD *)&gFailoverConnRetryTime )
    *(_DWORD *)&gFailoverConnRetryTime = 60;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverMaxUnAckedLeaseUpds", 0, &Type, &gFailoverMaxUnackedBndUpds, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"DhcpFailoverMaxBndRecordPerPacket", 0, &Type, &gFailoverMaxBndRecordsperPacket, &cbData);
  ValueW = v2;
  if ( v2 )
  {
    if ( v2 != 2 )
      goto LABEL_35;
  }
  else if ( *(_DWORD *)&gFailoverMaxBndRecordsperPacket > 0x10u )
  {
    *(_DWORD *)&gFailoverMaxBndRecordsperPacket = 16;
  }
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverReceiveTimer", 0, &Type, &gFailoverRecvTimerVal, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(
             hKey,
             L"DhcpFailoverAddrRebalacingTimeInt",
             0,
             &Type,
             &gFailoverAddressRebalanceIntv,
             &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 2;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverPort", 0, &Type, &gDhcpFailoverPort, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverTestHook", 0, &Type, &isDhcpFailoverTestEnv, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverLeaseDbQMaxSize", 0, &Type, &gFailoverLeaseDbQMaxSize, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverFreePacketPoolSize", 0, &Type, &gFailoverFreePacketPoolSize, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpMsgSyncDeltaTime", 0, &Type, &gMessageSyncDeltaTime, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverEnableCommInt", 0, &Type, &gFailoverEnableCommInt, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverStartUpTimer", 0, &Type, &gDhcpFailoverStartUpTime, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    goto LABEL_35;
  if ( !*(_DWORD *)&gMessageSyncDeltaTime )
    *(_DWORD *)&gMessageSyncDeltaTime = 60;
  cbData = 4;
  ValueW = RegQueryValueExW(hKey, L"DhcpFailoverMaxAddressAllocation", 0, &Type, &gFailoverAddressAllocation, &cbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
LABEL_35:
    v3 = ValueW;
    if ( !v0 )
      goto LABEL_37;
    goto LABEL_36;
  }
  ValueW = RegGetValueW(hKey, 0, L"DhcpFailoverCryptoAlgorithm", 2u, 0, 0, &cbData);
  if ( ValueW == 2 || !cbData )
  {
    cbData = 14;
    v3 = 8;
    v4 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, 0xEu);
    v0 = v4;
    if ( !v4 )
      goto LABEL_27;
    StringCbPrintfW(v4, cbData, L"SHA256");
LABEL_32:
    ValueW = DhcpValidateAlgorithmProvider(v0);
    if ( ValueW && (Microsoft_Windows_DHCP_ServerEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(v5, &InvalidAlgorithmProvider, v0);
    goto LABEL_35;
  }
  if ( ValueW )
    goto LABEL_35;
  v3 = 8;
  v0 = (WCHAR *)HeapAlloc(gDhcpHeap, 8u, cbData);
  if ( !v0 )
  {
LABEL_27:
    ValueW = 8;
    goto LABEL_37;
  }
  ValueW = RegGetValueW(hKey, 0, L"DhcpFailoverCryptoAlgorithm", 2u, 0, v0, &cbData);
  v3 = ValueW;
  if ( (ValueW & 0xFFFFFFFD) == 0 )
    goto LABEL_32;
LABEL_36:
  HeapFree(gDhcpHeap, 0, v0);
LABEL_37:
  result = RegCloseKey(hKey);
  if ( result == 2 )
    result = 0;
  if ( ValueW )
    return v3;
  return result;
}

```

## disassembly

```asm
0x1800a7f78  mov     [rsp-28h+arg_18], rbx
0x1800a7f7d  push    rbp
0x1800a7f7e  push    rsi
0x1800a7f7f  push    rdi
0x1800a7f80  push    r14
0x1800a7f82  push    r15
0x1800a7f84  mov     rbp, rsp
0x1800a7f87  sub     rsp, 40h
0x1800a7f8b  xor     r14d, r14d
0x1800a7f8e  mov     cs:gFailoverLeaseDbQMaxSize, 61A80h
0x1800a7f98  mov     eax, 287h
0x1800a7f9d  mov     [rbp+Type], r14d
0x1800a7fa1  mov     cs:gDhcpFailoverPort, ax
0x1800a7fa8  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x1800a7faf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a7fb6  mov     [rbp+cbData], r14d
0x1800a7fba  lea     r9d, [r14+0Fh]; samDesired
0x1800a7fbe  mov     [rbp+hKey], rcx
0x1800a7fc2  lea     rax, [rbp+hKey]
0x1800a7fc6  mov     cs:gFailoverConnRetryTime, r9d
0x1800a7fcd  xor     r8d, r8d; ulOptions
0x1800a7fd0  mov     cs:gFailoverFreePacketPoolSize, 0C00h
0x1800a7fda  mov     esi, r14d
0x1800a7fdd  mov     cs:gFailoverRecvTimerVal, 0B4h
0x1800a7fe7  mov     cs:gFailoverAddressRebalanceIntv, 12Ch
0x1800a7ff1  mov     cs:gFailoverMaxUnackedBndUpds, 0C8h
0x1800a7ffb  mov     cs:gFailoverMaxBndRecordsperPacket, 10h
0x1800a8005  mov     cs:isDhcpFailoverTestEnv, r14d
0x1800a800c  mov     cs:gMessageSyncDeltaTime, 3Ch ; '<'
0x1800a8016  mov     cs:gFailoverAddressAllocation, 3E8h
0x1800a8020  mov     cs:gFailoverEnableCommInt, r14d
0x1800a8027  mov     cs:gHAlgorithm, r14
0x1800a802e  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a8033  call    cs:__imp_RegOpenKeyExW
0x1800a803a  nop     dword ptr [rax+rax+00h]
0x1800a803f  mov     ebx, eax
0x1800a8041  test    eax, eax
0x1800a8043  jnz     loc_1800A84F4
0x1800a8049  mov     rcx, [rbp+hKey]; hKey
0x1800a804d  lea     edi, [rax+4]
0x1800a8050  lea     rax, [rbp+cbData]
0x1800a8054  mov     [rbp+cbData], edi
0x1800a8057  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a805c  lea     r9, [rbp+Type]; lpType
0x1800a8060  lea     rax, gFailoverConnRetryTime
0x1800a8067  xor     r8d, r8d; lpReserved
0x1800a806a  lea     rdx, aDhcpfailoverco; "DhcpFailoverConnectionRetryTime"
0x1800a8071  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8076  call    cs:__imp_RegQueryValueExW
0x1800a807d  nop     dword ptr [rax+rax+00h]
0x1800a8082  mov     r15d, 0FFFFFFFDh
0x1800a8088  mov     ebx, eax
0x1800a808a  test    r15d, eax
0x1800a808d  jnz     loc_1800A84F4
0x1800a8093  cmp     cs:gFailoverConnRetryTime, r14d
0x1800a809a  jnz     short loc_1800A80A6
0x1800a809c  mov     cs:gFailoverConnRetryTime, 3Ch ; '<'
0x1800a80a6  mov     rcx, [rbp+hKey]; hKey
0x1800a80aa  lea     rax, [rbp+cbData]
0x1800a80ae  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a80b3  lea     r9, [rbp+Type]; lpType
0x1800a80b7  lea     rax, gFailoverMaxUnackedBndUpds
0x1800a80be  mov     [rbp+cbData], edi
0x1800a80c1  xor     r8d, r8d; lpReserved
0x1800a80c4  mov     [rsp+40h+phkResult], rax; lpData
0x1800a80c9  lea     rdx, aDhcpfailoverma_1; "DhcpFailoverMaxUnAckedLeaseUpds"
0x1800a80d0  call    cs:__imp_RegQueryValueExW
0x1800a80d7  nop     dword ptr [rax+rax+00h]
0x1800a80dc  mov     ebx, eax
0x1800a80de  test    r15d, eax
0x1800a80e1  jnz     loc_1800A84F4
0x1800a80e7  mov     rcx, [rbp+hKey]; hKey
0x1800a80eb  lea     rax, [rbp+cbData]
0x1800a80ef  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a80f4  lea     r9, [rbp+Type]; lpType
0x1800a80f8  lea     rax, gFailoverMaxBndRecordsperPacket
0x1800a80ff  mov     [rbp+cbData], edi
0x1800a8102  xor     r8d, r8d; lpReserved
0x1800a8105  mov     [rsp+40h+phkResult], rax; lpData
0x1800a810a  lea     rdx, aDhcpfailoverma; "DhcpFailoverMaxBndRecordPerPacket"
0x1800a8111  call    cs:__imp_RegQueryValueExW
0x1800a8118  nop     dword ptr [rax+rax+00h]
0x1800a811d  mov     ebx, eax
0x1800a811f  test    eax, eax
0x1800a8121  jz      short loc_1800A812E
0x1800a8123  cmp     eax, 2
0x1800a8126  jnz     loc_1800A84F4
0x1800a812c  jmp     short loc_1800A8141
0x1800a812e  cmp     cs:gFailoverMaxBndRecordsperPacket, 10h
0x1800a8135  jbe     short loc_1800A8141
0x1800a8137  mov     cs:gFailoverMaxBndRecordsperPacket, 10h
0x1800a8141  mov     rcx, [rbp+hKey]; hKey
0x1800a8145  lea     rax, [rbp+cbData]
0x1800a8149  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a814e  lea     r9, [rbp+Type]; lpType
0x1800a8152  lea     rax, gFailoverRecvTimerVal
0x1800a8159  mov     [rbp+cbData], edi
0x1800a815c  xor     r8d, r8d; lpReserved
0x1800a815f  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8164  lea     rdx, aDhcpfailoverre_0; "DhcpFailoverReceiveTimer"
0x1800a816b  call    cs:__imp_RegQueryValueExW
0x1800a8172  nop     dword ptr [rax+rax+00h]
0x1800a8177  mov     ebx, eax
0x1800a8179  test    r15d, eax
0x1800a817c  jnz     loc_1800A84F4
0x1800a8182  mov     rcx, [rbp+hKey]; hKey
0x1800a8186  lea     rax, [rbp+cbData]
0x1800a818a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a818f  lea     r9, [rbp+Type]; lpType
0x1800a8193  lea     rax, gFailoverAddressRebalanceIntv
0x1800a819a  mov     [rbp+cbData], edi
0x1800a819d  xor     r8d, r8d; lpReserved
0x1800a81a0  mov     [rsp+40h+phkResult], rax; lpData
0x1800a81a5  lea     rdx, aDhcpfailoverad; "DhcpFailoverAddrRebalacingTimeInt"
0x1800a81ac  call    cs:__imp_RegQueryValueExW
0x1800a81b3  nop     dword ptr [rax+rax+00h]
0x1800a81b8  mov     ebx, eax
0x1800a81ba  test    r15d, eax
0x1800a81bd  jnz     loc_1800A84F4
0x1800a81c3  mov     rcx, [rbp+hKey]; hKey
0x1800a81c7  lea     rax, [rbp+cbData]
0x1800a81cb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a81d0  lea     r9, [rbp+Type]; lpType
0x1800a81d4  lea     rax, gDhcpFailoverPort
0x1800a81db  mov     [rbp+cbData], 2
0x1800a81e2  xor     r8d, r8d; lpReserved
0x1800a81e5  mov     [rsp+40h+phkResult], rax; lpData
0x1800a81ea  lea     rdx, aDhcpfailoverpo; "DhcpFailoverPort"
0x1800a81f1  call    cs:__imp_RegQueryValueExW
0x1800a81f8  nop     dword ptr [rax+rax+00h]
0x1800a81fd  mov     ebx, eax
0x1800a81ff  test    r15d, eax
0x1800a8202  jnz     loc_1800A84F4
0x1800a8208  mov     rcx, [rbp+hKey]; hKey
0x1800a820c  lea     rax, [rbp+cbData]
0x1800a8210  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8215  lea     r9, [rbp+Type]; lpType
0x1800a8219  lea     rax, isDhcpFailoverTestEnv
0x1800a8220  mov     [rbp+cbData], edi
0x1800a8223  xor     r8d, r8d; lpReserved
0x1800a8226  mov     [rsp+40h+phkResult], rax; lpData
0x1800a822b  lea     rdx, aDhcpfailoverte; "DhcpFailoverTestHook"
0x1800a8232  call    cs:__imp_RegQueryValueExW
0x1800a8239  nop     dword ptr [rax+rax+00h]
0x1800a823e  mov     ebx, eax
0x1800a8240  test    r15d, eax
0x1800a8243  jnz     loc_1800A84F4
0x1800a8249  mov     rcx, [rbp+hKey]; hKey
0x1800a824d  lea     rax, [rbp+cbData]
0x1800a8251  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8256  lea     r9, [rbp+Type]; lpType
0x1800a825a  lea     rax, gFailoverLeaseDbQMaxSize
0x1800a8261  mov     [rbp+cbData], edi
0x1800a8264  xor     r8d, r8d; lpReserved
0x1800a8267  mov     [rsp+40h+phkResult], rax; lpData
0x1800a826c  lea     rdx, aDhcpfailoverle; "DhcpFailoverLeaseDbQMaxSize"
0x1800a8273  call    cs:__imp_RegQueryValueExW
0x1800a827a  nop     dword ptr [rax+rax+00h]
0x1800a827f  mov     ebx, eax
0x1800a8281  test    r15d, eax
0x1800a8284  jnz     loc_1800A84F4
0x1800a828a  mov     rcx, [rbp+hKey]; hKey
0x1800a828e  lea     rax, [rbp+cbData]
0x1800a8292  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8297  lea     r9, [rbp+Type]; lpType
0x1800a829b  lea     rax, gFailoverFreePacketPoolSize
0x1800a82a2  mov     [rbp+cbData], edi
0x1800a82a5  xor     r8d, r8d; lpReserved
0x1800a82a8  mov     [rsp+40h+phkResult], rax; lpData
0x1800a82ad  lea     rdx, aDhcpfailoverfr; "DhcpFailoverFreePacketPoolSize"
0x1800a82b4  call    cs:__imp_RegQueryValueExW
0x1800a82bb  nop     dword ptr [rax+rax+00h]
0x1800a82c0  mov     ebx, eax
0x1800a82c2  test    r15d, eax
0x1800a82c5  jnz     loc_1800A84F4
0x1800a82cb  mov     rcx, [rbp+hKey]; hKey
0x1800a82cf  lea     rax, [rbp+cbData]
0x1800a82d3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a82d8  lea     r9, [rbp+Type]; lpType
0x1800a82dc  lea     rax, gMessageSyncDeltaTime
0x1800a82e3  mov     [rbp+cbData], edi
0x1800a82e6  xor     r8d, r8d; lpReserved
0x1800a82e9  mov     [rsp+40h+phkResult], rax; lpData
0x1800a82ee  lea     rdx, aDhcpmsgsyncdel; "DhcpMsgSyncDeltaTime"
0x1800a82f5  call    cs:__imp_RegQueryValueExW
0x1800a82fc  nop     dword ptr [rax+rax+00h]
0x1800a8301  mov     ebx, eax
0x1800a8303  test    r15d, eax
0x1800a8306  jnz     loc_1800A84F4
0x1800a830c  mov     rcx, [rbp+hKey]; hKey
0x1800a8310  lea     rax, [rbp+cbData]
0x1800a8314  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a8319  lea     r9, [rbp+Type]; lpType
0x1800a831d  lea     rax, gFailoverEnableCommInt
0x1800a8324  mov     [rbp+cbData], edi
0x1800a8327  xor     r8d, r8d; lpReserved
0x1800a832a  mov     [rsp+40h+phkResult], rax; lpData
0x1800a832f  lea     rdx, aDhcpfailoveren; "DhcpFailoverEnableCommInt"
0x1800a8336  call    cs:__imp_RegQueryValueExW
0x1800a833d  nop     dword ptr [rax+rax+00h]
0x1800a8342  mov     ebx, eax
0x1800a8344  test    r15d, eax
0x1800a8347  jnz     loc_1800A84F4
0x1800a834d  mov     rcx, [rbp+hKey]; hKey
0x1800a8351  lea     rax, [rbp+cbData]
0x1800a8355  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a835a  lea     r9, [rbp+Type]; lpType
0x1800a835e  lea     rax, gDhcpFailoverStartUpTime
0x1800a8365  mov     [rbp+cbData], edi
0x1800a8368  xor     r8d, r8d; lpReserved
0x1800a836b  mov     [rsp+40h+phkResult], rax; lpData
0x1800a8370  lea     rdx, aDhcpfailoverst; "DhcpFailoverStartUpTimer"
0x1800a8377  call    cs:__imp_RegQueryValueExW
0x1800a837e  nop     dword ptr [rax+rax+00h]
0x1800a8383  mov     ebx, eax
0x1800a8385  test    r15d, eax
0x1800a8388  jnz     loc_1800A84F4
0x1800a838e  cmp     cs:gMessageSyncDeltaTime, r14d
0x1800a8395  jnz     short loc_1800A83A1
0x1800a8397  mov     cs:gMessageSyncDeltaTime, 3Ch ; '<'
0x1800a83a1  mov     rcx, [rbp+hKey]; hKey
0x1800a83a5  lea     rax, [rbp+cbData]
0x1800a83a9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a83ae  lea     r9, [rbp+Type]; lpType
0x1800a83b2  lea     rax, gFailoverAddressAllocation
0x1800a83b9  mov     [rbp+cbData], edi
0x1800a83bc  xor     r8d, r8d; lpReserved
0x1800a83bf  mov     [rsp+40h+phkResult], rax; lpData
0x1800a83c4  lea     rdx, aDhcpfailoverma_0; "DhcpFailoverMaxAddressAllocation"
0x1800a83cb  call    cs:__imp_RegQueryValueExW
0x1800a83d2  nop     dword ptr [rax+rax+00h]
0x1800a83d7  mov     ebx, eax
0x1800a83d9  test    r15d, eax
0x1800a83dc  jnz     loc_1800A84F4
0x1800a83e2  mov     rcx, [rbp+hKey]; hkey
0x1800a83e6  lea     rax, [rbp+cbData]
0x1800a83ea  mov     [rsp+40h+pcbData], rax; pcbData
0x1800a83ef  lea     r8, Value; "DhcpFailoverCryptoAlgorithm"
0x1800a83f6  mov     [rsp+40h+lpcbData], r14; pvData
0x1800a83fb  mov     r9d, 2; dwFlags
0x1800a8401  xor     edx, edx; lpSubKey
0x1800a8403  mov     [rsp+40h+phkResult], r14; pdwType
0x1800a8408  call    cs:__imp_RegGetValueW
0x1800a840f  nop     dword ptr [rax+rax+00h]
0x1800a8414  mov     ebx, eax
0x1800a8416  cmp     eax, 2
0x1800a8419  jz      short loc_1800A8491
0x1800a841b  mov     eax, [rbp+cbData]
0x1800a841e  test    eax, eax
0x1800a8420  jz      short loc_1800A8491
0x1800a8422  test    ebx, ebx
0x1800a8424  jnz     loc_1800A84F4
0x1800a842a  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a8431  lea     edi, [rbx+8]
0x1800a8434  mov     edx, edi; dwFlags
0x1800a8436  mov     r8d, eax; dwBytes
0x1800a8439  call    cs:__imp_HeapAlloc
0x1800a8440  nop     dword ptr [rax+rax+00h]
0x1800a8445  mov     rsi, rax
0x1800a8448  test    rax, rax
0x1800a844b  jnz     short loc_1800A8454
0x1800a844d  mov     ebx, edi
0x1800a844f  jmp     loc_1800A8513
0x1800a8454  mov     rcx, [rbp+hKey]; hkey
0x1800a8458  lea     rax, [rbp+cbData]
0x1800a845c  mov     [rsp+40h+pcbData], rax; pcbData
0x1800a8461  lea     r8, Value; "DhcpFailoverCryptoAlgorithm"
0x1800a8468  mov     [rsp+40h+lpcbData], rsi; pvData
0x1800a846d  mov     r9d, 2; dwFlags
0x1800a8473  xor     edx, edx; lpSubKey
0x1800a8475  mov     [rsp+40h+phkResult], r14; pdwType
0x1800a847a  call    cs:__imp_RegGetValueW
0x1800a8481  nop     dword ptr [rax+rax+00h]
0x1800a8486  mov     ebx, eax
0x1800a8488  mov     edi, eax
0x1800a848a  test    r15d, eax
0x1800a848d  jz      short loc_1800A84CE
0x1800a848f  jmp     short loc_1800A84FB
0x1800a8491  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a8498  mov     r8d, 0Eh; dwBytes
0x1800a849e  mov     [rbp+cbData], r8d
0x1800a84a2  lea     edi, [r8-6]
0x1800a84a6  mov     edx, edi; dwFlags
0x1800a84a8  call    cs:__imp_HeapAlloc
0x1800a84af  nop     dword ptr [rax+rax+00h]
0x1800a84b4  mov     rsi, rax
0x1800a84b7  test    rax, rax
0x1800a84ba  jz      short loc_1800A844D
0x1800a84bc  mov     edx, [rbp+cbData]; cbDest
0x1800a84bf  lea     r8, aSha256; "SHA256"
0x1800a84c6  mov     rcx, rax; pszDest
0x1800a84c9  call    StringCbPrintfW
0x1800a84ce  mov     rcx, rsi; pszAlgId
0x1800a84d1  call    DhcpValidateAlgorithmProvider
0x1800a84d6  mov     ebx, eax
0x1800a84d8  test    eax, eax
0x1800a84da  jz      short loc_1800A84F4
0x1800a84dc  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 40h
0x1800a84e3  jz      short loc_1800A84F4
0x1800a84e5  mov     r8, rsi
  ... truncated ...
```
