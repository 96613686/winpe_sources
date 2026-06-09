# DwDeleteServerIpSecFilter

- ea: `0x180084db4`
- end: `0x180084f1d`
- name: `DwDeleteServerIpSecFilter`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014e40`

## callees

- `0x180084db4`
- `0x180085b20`
- `0x180085cb4`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x180084e66`
- `RPCRT4!UuidIsNil` at `0x180084eae`
- `RPCRT4!UuidIsNil` at `0x180084e66`
- `RPCRT4!UuidIsNil` at `0x180084eae`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180084ef1`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180084ef1`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084e84`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084ecc`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084e84`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084ecc`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180084e32`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180084e32`

## string_xrefs

- `0x180084dbc`: `DwDeleteServerIpSecFilter`
- `0x180084e44`: `FwpmFilterDelete0: dwStatus=0x%x`
- `0x180084e96`: `FwpmProviderContextDelete0 QM: dwStatus=0x%x`
- `0x180084ede`: `FwpmProviderContextDelete0 MM: dwStatus=0x%x`
- `0x180084f08`: `DwDeleteServerIpSecFilter: rc=0x%x`

## pseudocode

```c
__int64 DwDeleteServerIpSecFilter()
{
  DWORD v0; // ebx
  unsigned int i; // ebx
  RPC_STATUS Status; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  Status = 0;
  RasIpsecTrace("DwDeleteServerIpSecFilter");
  if ( (unsigned int)geServerEncryption < 4 || (unsigned int)(geServerEncryption - 4) <= 1 )
  {
    v0 = FwpmTransactionBegin0Wrapper();
    if ( v0 )
    {
      RasIpsecTrace("FwpmTransactionBegin0 failed with 0x%x");
    }
    else
    {
      for ( i = 0; i < gNumServerFilterIds; ++i )
      {
        if ( FwpmFilterDeleteByKey0(gFwpEngineHandle, (const GUID *)&gServerFilterIds[2 * i]) )
          RasIpsecTrace("FwpmFilterDelete0: dwStatus=0x%x");
      }
      if ( !UuidIsNil(&gServerQMPolicyGuid, &Status)
        && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, &gServerQMPolicyGuid) )
      {
        RasIpsecTrace("FwpmProviderContextDelete0 QM: dwStatus=0x%x");
      }
      if ( !UuidIsNil(&gServerMMPolicyGuid, &Status)
        && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, &gServerMMPolicyGuid) )
      {
        RasIpsecTrace("FwpmProviderContextDelete0 MM: dwStatus=0x%x");
      }
      v0 = FwpmTransactionCommit0(gFwpEngineHandle);
    }
    gNumServerFilterIds = 0;
  }
  RasIpsecTrace("DwDeleteServerIpSecFilter: rc=0x%x");
  return v0;
}

```

## disassembly

```asm
0x180084db4  push    rbx
0x180084db6  sub     rsp, 20h
0x180084dba  xor     ebx, ebx
0x180084dbc  lea     rcx, aDwdeleteserver_0; "DwDeleteServerIpSecFilter"
0x180084dc3  and     [rsp+28h+Status], ebx
0x180084dc7  call    RasIpsecTrace
0x180084dcc  mov     ecx, cs:geServerEncryption
0x180084dd2  test    ecx, ecx
0x180084dd4  jz      short loc_180084DF3
0x180084dd6  sub     ecx, 1
0x180084dd9  jz      short loc_180084DF3
0x180084ddb  sub     ecx, 1
0x180084dde  jz      short loc_180084DF3
0x180084de0  sub     ecx, 1
0x180084de3  jz      short loc_180084DF3
0x180084de5  sub     ecx, 1
0x180084de8  jz      short loc_180084DF3
0x180084dea  cmp     ecx, 1
0x180084ded  jnz     loc_180084F06
0x180084df3  call    FwpmTransactionBegin0Wrapper
0x180084df8  mov     ebx, eax
0x180084dfa  test    eax, eax
0x180084dfc  jz      short loc_180084E11
0x180084dfe  mov     edx, eax
0x180084e00  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x180084e07  call    RasIpsecTrace
0x180084e0c  jmp     loc_180084EFF
0x180084e11  xor     ebx, ebx
0x180084e13  cmp     cs:gNumServerFilterIds, ebx
0x180084e19  jbe     short loc_180084E5A
0x180084e1b  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084e22  lea     rax, gServerFilterIds
0x180084e29  mov     edx, ebx
0x180084e2b  shl     rdx, 4
0x180084e2f  add     rdx, rax; key
0x180084e32  call    cs:__imp_FwpmFilterDeleteByKey0
0x180084e39  nop     dword ptr [rax+rax+00h]
0x180084e3e  test    eax, eax
0x180084e40  jz      short loc_180084E50
0x180084e42  mov     edx, eax
0x180084e44  lea     rcx, aFwpmfilterdele; "FwpmFilterDelete0: dwStatus=0x%x"
0x180084e4b  call    RasIpsecTrace
0x180084e50  inc     ebx
0x180084e52  cmp     ebx, cs:gNumServerFilterIds
0x180084e58  jb      short loc_180084E1B
0x180084e5a  lea     rdx, [rsp+28h+Status]; Status
0x180084e5f  lea     rcx, gServerQMPolicyGuid; Uuid
0x180084e66  call    cs:__imp_UuidIsNil
0x180084e6d  nop     dword ptr [rax+rax+00h]
0x180084e72  test    eax, eax
0x180084e74  jnz     short loc_180084EA2
0x180084e76  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084e7d  lea     rdx, gServerQMPolicyGuid; key
0x180084e84  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x180084e8b  nop     dword ptr [rax+rax+00h]
0x180084e90  test    eax, eax
0x180084e92  jz      short loc_180084EA2
0x180084e94  mov     edx, eax
0x180084e96  lea     rcx, aFwpmproviderco_3; "FwpmProviderContextDelete0 QM: dwStatus"...
0x180084e9d  call    RasIpsecTrace
0x180084ea2  lea     rdx, [rsp+28h+Status]; Status
0x180084ea7  lea     rcx, gServerMMPolicyGuid; Uuid
0x180084eae  call    cs:__imp_UuidIsNil
0x180084eb5  nop     dword ptr [rax+rax+00h]
0x180084eba  test    eax, eax
0x180084ebc  jnz     short loc_180084EEA
0x180084ebe  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084ec5  lea     rdx, gServerMMPolicyGuid; key
0x180084ecc  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x180084ed3  nop     dword ptr [rax+rax+00h]
0x180084ed8  test    eax, eax
0x180084eda  jz      short loc_180084EEA
0x180084edc  mov     edx, eax
0x180084ede  lea     rcx, aFwpmproviderco_2; "FwpmProviderContextDelete0 MM: dwStatus"...
0x180084ee5  call    RasIpsecTrace
0x180084eea  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084ef1  call    cs:__imp_FwpmTransactionCommit0
0x180084ef8  nop     dword ptr [rax+rax+00h]
0x180084efd  mov     ebx, eax
0x180084eff  and     cs:gNumServerFilterIds, 0
0x180084f06  mov     edx, ebx
0x180084f08  lea     rcx, aDwdeleteserver; "DwDeleteServerIpSecFilter: rc=0x%x"
0x180084f0f  call    RasIpsecTrace
0x180084f14  mov     eax, ebx
0x180084f16  add     rsp, 20h
0x180084f1a  pop     rbx
0x180084f1b  retn
```
