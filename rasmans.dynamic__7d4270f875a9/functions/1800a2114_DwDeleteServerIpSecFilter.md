# DwDeleteServerIpSecFilter

- ea: `0x1800a2114`
- end: `0x1800a2280`
- name: `DwDeleteServerIpSecFilter`
- size: `364`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e560`
- `0x18003ba54`
- `0x18003f69c`

## callees

- `0x1800a2114`
- `0x1800a29c0`
- `0x1800a2b38`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x1800a21c6`
- `RPCRT4!UuidIsNil` at `0x1800a220e`
- `RPCRT4!UuidIsNil` at `0x1800a21c6`
- `RPCRT4!UuidIsNil` at `0x1800a220e`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800a2192`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800a2192`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a2251`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a2251`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a21e4`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a222c`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a21e4`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a222c`

## string_xrefs

- `0x1800a211c`: `DwDeleteServerIpSecFilter`
- `0x1800a21f6`: `FwpmProviderContextDelete0 QM: dwStatus=0x%x`
- `0x1800a21a4`: `FwpmFilterDelete0: dwStatus=0x%x`
- `0x1800a226b`: `DwDeleteServerIpSecFilter: rc=0x%x`
- `0x1800a223e`: `FwpmProviderContextDelete0 MM: dwStatus=0x%x`

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
0x1800a2114  push    rbx
0x1800a2116  sub     rsp, 20h
0x1800a211a  xor     ebx, ebx
0x1800a211c  lea     rcx, aDwdeleteserver_0; "DwDeleteServerIpSecFilter"
0x1800a2123  mov     [rsp+28h+Status], ebx
0x1800a2127  call    RasIpsecTrace
0x1800a212c  mov     ecx, cs:geServerEncryption
0x1800a2132  test    ecx, ecx
0x1800a2134  jz      short loc_1800A2153
0x1800a2136  sub     ecx, 1
0x1800a2139  jz      short loc_1800A2153
0x1800a213b  sub     ecx, 1
0x1800a213e  jz      short loc_1800A2153
0x1800a2140  sub     ecx, 1
0x1800a2143  jz      short loc_1800A2153
0x1800a2145  sub     ecx, 1
0x1800a2148  jz      short loc_1800A2153
0x1800a214a  cmp     ecx, 1
0x1800a214d  jnz     loc_1800A2269
0x1800a2153  call    FwpmTransactionBegin0Wrapper
0x1800a2158  mov     ebx, eax
0x1800a215a  test    eax, eax
0x1800a215c  jz      short loc_1800A2171
0x1800a215e  mov     edx, eax
0x1800a2160  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x1800a2167  call    RasIpsecTrace
0x1800a216c  jmp     loc_1800A225F
0x1800a2171  xor     ebx, ebx
0x1800a2173  cmp     cs:gNumServerFilterIds, ebx
0x1800a2179  jbe     short loc_1800A21BA
0x1800a217b  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a2182  lea     rax, gServerFilterIds
0x1800a2189  mov     edx, ebx
0x1800a218b  shl     rdx, 4
0x1800a218f  add     rdx, rax; key
0x1800a2192  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800a2199  nop     dword ptr [rax+rax+00h]
0x1800a219e  test    eax, eax
0x1800a21a0  jz      short loc_1800A21B0
0x1800a21a2  mov     edx, eax
0x1800a21a4  lea     rcx, aFwpmfilterdele; "FwpmFilterDelete0: dwStatus=0x%x"
0x1800a21ab  call    RasIpsecTrace
0x1800a21b0  inc     ebx
0x1800a21b2  cmp     ebx, cs:gNumServerFilterIds
0x1800a21b8  jb      short loc_1800A217B
0x1800a21ba  lea     rdx, [rsp+28h+Status]; Status
0x1800a21bf  lea     rcx, gServerQMPolicyGuid; Uuid
0x1800a21c6  call    cs:__imp_UuidIsNil
0x1800a21cd  nop     dword ptr [rax+rax+00h]
0x1800a21d2  test    eax, eax
0x1800a21d4  jnz     short loc_1800A2202
0x1800a21d6  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a21dd  lea     rdx, gServerQMPolicyGuid; key
0x1800a21e4  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x1800a21eb  nop     dword ptr [rax+rax+00h]
0x1800a21f0  test    eax, eax
0x1800a21f2  jz      short loc_1800A2202
0x1800a21f4  mov     edx, eax
0x1800a21f6  lea     rcx, aFwpmproviderco_3; "FwpmProviderContextDelete0 QM: dwStatus"...
0x1800a21fd  call    RasIpsecTrace
0x1800a2202  lea     rdx, [rsp+28h+Status]; Status
0x1800a2207  lea     rcx, gServerMMPolicyGuid; Uuid
0x1800a220e  call    cs:__imp_UuidIsNil
0x1800a2215  nop     dword ptr [rax+rax+00h]
0x1800a221a  test    eax, eax
0x1800a221c  jnz     short loc_1800A224A
0x1800a221e  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a2225  lea     rdx, gServerMMPolicyGuid; key
0x1800a222c  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x1800a2233  nop     dword ptr [rax+rax+00h]
0x1800a2238  test    eax, eax
0x1800a223a  jz      short loc_1800A224A
0x1800a223c  mov     edx, eax
0x1800a223e  lea     rcx, aFwpmproviderco_2; "FwpmProviderContextDelete0 MM: dwStatus"...
0x1800a2245  call    RasIpsecTrace
0x1800a224a  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a2251  call    cs:__imp_FwpmTransactionCommit0
0x1800a2258  nop     dword ptr [rax+rax+00h]
0x1800a225d  mov     ebx, eax
0x1800a225f  mov     cs:gNumServerFilterIds, 0
0x1800a2269  mov     edx, ebx
0x1800a226b  lea     rcx, aDwdeleteserver; "DwDeleteServerIpSecFilter: rc=0x%x"
0x1800a2272  call    RasIpsecTrace
0x1800a2277  mov     eax, ebx
0x1800a2279  add     rsp, 20h
0x1800a227d  pop     rbx
0x1800a227e  retn
```
