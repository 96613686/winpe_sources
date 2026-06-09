# DwDeleteServerIpSecFilter

- ea: `0x18007fa7c`
- end: `0x18007fbc3`
- name: `DwDeleteServerIpSecFilter`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014a90`

## callees

- `0x18007fa7c`
- `0x180080264`
- `0x1800803a8`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x18007fb28`
- `RPCRT4!UuidIsNil` at `0x18007fb64`
- `RPCRT4!UuidIsNil` at `0x18007fb28`
- `RPCRT4!UuidIsNil` at `0x18007fb64`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007fb9b`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007fb9b`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007fb40`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007fb7c`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007fb40`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007fb7c`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18007fafa`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18007fafa`

## string_xrefs

- `0x18007fa84`: `DwDeleteServerIpSecFilter`
- `0x18007fb06`: `FwpmFilterDelete0: dwStatus=0x%x`
- `0x18007fb4c`: `FwpmProviderContextDelete0 QM: dwStatus=0x%x`
- `0x18007fb88`: `FwpmProviderContextDelete0 MM: dwStatus=0x%x`
- `0x18007fbaf`: `DwDeleteServerIpSecFilter: rc=0x%x`

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
0x18007fa7c  push    rbx
0x18007fa7e  sub     rsp, 20h
0x18007fa82  xor     ebx, ebx
0x18007fa84  lea     rcx, aDwdeleteserver_0; "DwDeleteServerIpSecFilter"
0x18007fa8b  mov     [rsp+28h+Status], ebx
0x18007fa8f  call    RasIpsecTrace
0x18007fa94  mov     ecx, cs:geServerEncryption
0x18007fa9a  test    ecx, ecx
0x18007fa9c  jz      short loc_18007FABB
0x18007fa9e  sub     ecx, 1
0x18007faa1  jz      short loc_18007FABB
0x18007faa3  sub     ecx, 1
0x18007faa6  jz      short loc_18007FABB
0x18007faa8  sub     ecx, 1
0x18007faab  jz      short loc_18007FABB
0x18007faad  sub     ecx, 1
0x18007fab0  jz      short loc_18007FABB
0x18007fab2  cmp     ecx, 1
0x18007fab5  jnz     loc_18007FBAD
0x18007fabb  call    FwpmTransactionBegin0Wrapper
0x18007fac0  mov     ebx, eax
0x18007fac2  test    eax, eax
0x18007fac4  jz      short loc_18007FAD9
0x18007fac6  mov     edx, eax
0x18007fac8  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18007facf  call    RasIpsecTrace
0x18007fad4  jmp     loc_18007FBA3
0x18007fad9  xor     ebx, ebx
0x18007fadb  cmp     cs:gNumServerFilterIds, ebx
0x18007fae1  jbe     short loc_18007FB1C
0x18007fae3  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007faea  lea     rax, gServerFilterIds
0x18007faf1  mov     edx, ebx
0x18007faf3  shl     rdx, 4
0x18007faf7  add     rdx, rax; key
0x18007fafa  call    cs:__imp_FwpmFilterDeleteByKey0
0x18007fb00  test    eax, eax
0x18007fb02  jz      short loc_18007FB12
0x18007fb04  mov     edx, eax
0x18007fb06  lea     rcx, aFwpmfilterdele; "FwpmFilterDelete0: dwStatus=0x%x"
0x18007fb0d  call    RasIpsecTrace
0x18007fb12  inc     ebx
0x18007fb14  cmp     ebx, cs:gNumServerFilterIds
0x18007fb1a  jb      short loc_18007FAE3
0x18007fb1c  lea     rdx, [rsp+28h+Status]; Status
0x18007fb21  lea     rcx, gServerQMPolicyGuid; Uuid
0x18007fb28  call    cs:__imp_UuidIsNil
0x18007fb2e  test    eax, eax
0x18007fb30  jnz     short loc_18007FB58
0x18007fb32  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007fb39  lea     rdx, gServerQMPolicyGuid; key
0x18007fb40  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18007fb46  test    eax, eax
0x18007fb48  jz      short loc_18007FB58
0x18007fb4a  mov     edx, eax
0x18007fb4c  lea     rcx, aFwpmproviderco_3; "FwpmProviderContextDelete0 QM: dwStatus"...
0x18007fb53  call    RasIpsecTrace
0x18007fb58  lea     rdx, [rsp+28h+Status]; Status
0x18007fb5d  lea     rcx, gServerMMPolicyGuid; Uuid
0x18007fb64  call    cs:__imp_UuidIsNil
0x18007fb6a  test    eax, eax
0x18007fb6c  jnz     short loc_18007FB94
0x18007fb6e  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007fb75  lea     rdx, gServerMMPolicyGuid; key
0x18007fb7c  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18007fb82  test    eax, eax
0x18007fb84  jz      short loc_18007FB94
0x18007fb86  mov     edx, eax
0x18007fb88  lea     rcx, aFwpmproviderco_2; "FwpmProviderContextDelete0 MM: dwStatus"...
0x18007fb8f  call    RasIpsecTrace
0x18007fb94  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007fb9b  call    cs:__imp_FwpmTransactionCommit0
0x18007fba1  mov     ebx, eax
0x18007fba3  mov     cs:gNumServerFilterIds, 0
0x18007fbad  mov     edx, ebx
0x18007fbaf  lea     rcx, aDwdeleteserver; "DwDeleteServerIpSecFilter: rc=0x%x"
0x18007fbb6  call    RasIpsecTrace
0x18007fbbb  mov     eax, ebx
0x18007fbbd  add     rsp, 20h
0x18007fbc1  pop     rbx
0x18007fbc2  retn
```
