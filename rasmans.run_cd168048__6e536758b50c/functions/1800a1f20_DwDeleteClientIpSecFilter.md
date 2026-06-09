# DwDeleteClientIpSecFilter

- ea: `0x1800a1f20`
- end: `0x1800a210d`
- name: `DwDeleteClientIpSecFilter`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003b900`

## callees

- `0x1800a1f20`
- `0x1800a2930`
- `0x1800a29c0`
- `0x1800a2b38`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x1800a1ff3`
- `RPCRT4!UuidIsNil` at `0x1800a2034`
- `RPCRT4!UuidIsNil` at `0x1800a1ff3`
- `RPCRT4!UuidIsNil` at `0x1800a2034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a20ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a20d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a20ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a20d9`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800a1fc5`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800a1fc5`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a2073`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a2073`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a200e`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a204e`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a200e`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a204e`

## string_xrefs

- `0x1800a2020`: `FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x`
- `0x1800a1fd7`: `FwpmFilterDeleteByKey0: dwStatus=0x%x`
- `0x1800a20ee`: `DwDeleteClientIpSecFilter: dwStatus=0x%x`
- `0x1800a2060`: `FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x`

## pseudocode

```c
__int64 __fastcall DwDeleteClientIpSecFilter(__int128 *a1)
{
  __int64 ServerNode; // rax
  __int64 v2; // rbx
  DWORD v3; // esi
  unsigned int v4; // eax
  int v5; // ecx
  int v6; // ecx
  unsigned int v7; // edi
  unsigned int i; // edi
  __int64 v10; // rdi
  __int64 v11; // rax
  _QWORD *v12; // rcx
  void *v13; // rcx
  __int128 v14; // [rsp+20h] [rbp-28h] BYREF
  int v15; // [rsp+30h] [rbp-18h]
  RPC_STATUS Status; // [rsp+50h] [rbp+8h] BYREF

  v14 = *a1;
  Status = 0;
  v15 = *((_DWORD *)a1 + 4);
  ServerNode = FindServerNode(a1, &v14);
  v2 = ServerNode;
  if ( ServerNode )
  {
    v4 = *(_DWORD *)(ServerNode + 52);
    v3 = 0;
    if ( v4 > 1 )
    {
      *(_DWORD *)(v2 + 52) = v4 - 1;
LABEL_33:
      RasIpsecTrace("DwDeleteClientIpSecFilter: dwStatus=0x%x");
      return v3;
    }
    v5 = *(_DWORD *)(v2 + 76);
    if ( !v5 || (v6 = v5 - 1) == 0 || (unsigned int)(v6 - 1) <= 1 )
    {
      v7 = FwpmTransactionBegin0Wrapper();
      if ( v7 )
      {
        RasIpsecTrace("FwpmTransactionBegin0 failed with 0x%x");
        return v7;
      }
      for ( i = 0; i < *(_DWORD *)(v2 + 48); ++i )
      {
        if ( FwpmFilterDeleteByKey0(gFwpEngineHandle, (const GUID *)(*(_QWORD *)(v2 + 32) + 16LL * i)) )
          RasIpsecTrace("FwpmFilterDeleteByKey0: dwStatus=0x%x");
      }
      if ( !UuidIsNil((UUID *)(v2 + 16), &Status)
        && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, (const GUID *)(v2 + 16)) )
      {
        RasIpsecTrace("FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x");
      }
      if ( !UuidIsNil((UUID *)v2, &Status) && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, (const GUID *)v2) )
        RasIpsecTrace("FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x");
      v3 = FwpmTransactionCommit0(gFwpEngineHandle);
    }
    --*(_DWORD *)(v2 + 52);
    v10 = gpIpSecSrvList;
    if ( gpIpSecSrvList )
    {
      if ( v2 == gpIpSecSrvList )
      {
        v10 = *(_QWORD *)(gpIpSecSrvList + 80);
LABEL_29:
        v13 = *(void **)(v2 + 32);
        if ( v13 )
          LocalFree(v13);
        LocalFree((HLOCAL)v2);
        goto LABEL_32;
      }
      v11 = gpIpSecSrvList;
      if ( *(_QWORD *)(gpIpSecSrvList + 80) )
      {
        while ( 1 )
        {
          v12 = (_QWORD *)(v11 + 80);
          v11 = *(_QWORD *)(v11 + 80);
          if ( v11 == v2 )
            break;
          if ( !*(_QWORD *)(v11 + 80) )
            goto LABEL_32;
        }
        *v12 = *(_QWORD *)(v11 + 80);
        goto LABEL_29;
      }
    }
LABEL_32:
    gpIpSecSrvList = v10;
    goto LABEL_33;
  }
  return 87;
}

```

## disassembly

```asm
0x1800a1f20  mov     rax, rsp
0x1800a1f23  mov     [rax+10h], rbx
0x1800a1f27  mov     [rax+18h], rsi
0x1800a1f2b  push    rdi
0x1800a1f2c  sub     rsp, 40h
0x1800a1f30  movaps  xmm0, xmmword ptr [rcx]
0x1800a1f33  lea     rdx, [rsp+48h+var_28]
0x1800a1f38  movaps  xmmword ptr [rax-28h], xmm0
0x1800a1f3c  mov     dword ptr [rax+8], 0
0x1800a1f43  mov     eax, [rcx+10h]
0x1800a1f46  mov     [rsp+48h+var_18], eax
0x1800a1f4a  call    FindServerNode
0x1800a1f4f  mov     rbx, rax
0x1800a1f52  test    rax, rax
0x1800a1f55  jnz     short loc_1800A1F5F
0x1800a1f57  lea     esi, [rax+57h]
0x1800a1f5a  jmp     loc_1800A20FA
0x1800a1f5f  mov     eax, [rax+34h]
0x1800a1f62  xor     esi, esi
0x1800a1f64  cmp     eax, 1
0x1800a1f67  jbe     short loc_1800A1F73
0x1800a1f69  dec     eax
0x1800a1f6b  mov     [rbx+34h], eax
0x1800a1f6e  jmp     loc_1800A20EC
0x1800a1f73  mov     ecx, [rbx+4Ch]
0x1800a1f76  test    ecx, ecx
0x1800a1f78  jz      short loc_1800A1F8D
0x1800a1f7a  sub     ecx, 1
0x1800a1f7d  jz      short loc_1800A1F8D
0x1800a1f7f  sub     ecx, 1
0x1800a1f82  jz      short loc_1800A1F8D
0x1800a1f84  cmp     ecx, 1
0x1800a1f87  jnz     loc_1800A2081
0x1800a1f8d  call    FwpmTransactionBegin0Wrapper
0x1800a1f92  mov     edi, eax
0x1800a1f94  test    eax, eax
0x1800a1f96  jz      short loc_1800A1FAD
0x1800a1f98  mov     edx, eax
0x1800a1f9a  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x1800a1fa1  call    RasIpsecTrace
0x1800a1fa6  mov     eax, edi
0x1800a1fa8  jmp     loc_1800A20FC
0x1800a1fad  xor     edi, edi
0x1800a1faf  cmp     [rbx+30h], esi
0x1800a1fb2  jbe     short loc_1800A1FEA
0x1800a1fb4  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a1fbb  mov     edx, edi
0x1800a1fbd  shl     rdx, 4
0x1800a1fc1  add     rdx, [rbx+20h]; key
0x1800a1fc5  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800a1fcc  nop     dword ptr [rax+rax+00h]
0x1800a1fd1  test    eax, eax
0x1800a1fd3  jz      short loc_1800A1FE3
0x1800a1fd5  mov     edx, eax
0x1800a1fd7  lea     rcx, aFwpmfilterdele_0; "FwpmFilterDeleteByKey0: dwStatus=0x%x"
0x1800a1fde  call    RasIpsecTrace
0x1800a1fe3  inc     edi
0x1800a1fe5  cmp     edi, [rbx+30h]
0x1800a1fe8  jb      short loc_1800A1FB4
0x1800a1fea  lea     rdx, [rsp+48h+Status]; Status
0x1800a1fef  lea     rcx, [rbx+10h]; Uuid
0x1800a1ff3  call    cs:__imp_UuidIsNil
0x1800a1ffa  nop     dword ptr [rax+rax+00h]
0x1800a1fff  test    eax, eax
0x1800a2001  jnz     short loc_1800A202C
0x1800a2003  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a200a  lea     rdx, [rbx+10h]; key
0x1800a200e  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x1800a2015  nop     dword ptr [rax+rax+00h]
0x1800a201a  test    eax, eax
0x1800a201c  jz      short loc_1800A202C
0x1800a201e  mov     edx, eax
0x1800a2020  lea     rcx, aFwpmproviderco_4; "FwpmProviderContextDeleteByKey0 QM: dwS"...
0x1800a2027  call    RasIpsecTrace
0x1800a202c  lea     rdx, [rsp+48h+Status]; Status
0x1800a2031  mov     rcx, rbx; Uuid
0x1800a2034  call    cs:__imp_UuidIsNil
0x1800a203b  nop     dword ptr [rax+rax+00h]
0x1800a2040  test    eax, eax
0x1800a2042  jnz     short loc_1800A206C
0x1800a2044  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a204b  mov     rdx, rbx; key
0x1800a204e  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x1800a2055  nop     dword ptr [rax+rax+00h]
0x1800a205a  test    eax, eax
0x1800a205c  jz      short loc_1800A206C
0x1800a205e  mov     edx, eax
0x1800a2060  lea     rcx, aFwpmproviderco_0; "FwpmProviderContextDeleteByKey0 MM: dwS"...
0x1800a2067  call    RasIpsecTrace
0x1800a206c  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a2073  call    cs:__imp_FwpmTransactionCommit0
0x1800a207a  nop     dword ptr [rax+rax+00h]
0x1800a207f  mov     esi, eax
0x1800a2081  dec     dword ptr [rbx+34h]
0x1800a2084  mov     rdi, cs:gpIpSecSrvList
0x1800a208b  test    rdi, rdi
0x1800a208e  jz      short loc_1800A20E5
0x1800a2090  cmp     rbx, rdi
0x1800a2093  jnz     short loc_1800A209B
0x1800a2095  mov     rdi, [rdi+50h]
0x1800a2099  jmp     short loc_1800A20C1
0x1800a209b  cmp     qword ptr [rdi+50h], 0
0x1800a20a0  mov     rax, rdi
0x1800a20a3  jz      short loc_1800A20E5
0x1800a20a5  lea     rcx, [rax+50h]
0x1800a20a9  mov     rax, [rcx]
0x1800a20ac  cmp     rax, rbx
0x1800a20af  jz      short loc_1800A20BA
0x1800a20b1  cmp     qword ptr [rax+50h], 0
0x1800a20b6  jnz     short loc_1800A20A5
0x1800a20b8  jmp     short loc_1800A20E5
0x1800a20ba  mov     rax, [rax+50h]
0x1800a20be  mov     [rcx], rax
0x1800a20c1  mov     rcx, [rbx+20h]; hMem
0x1800a20c5  test    rcx, rcx
0x1800a20c8  jz      short loc_1800A20D6
0x1800a20ca  call    cs:__imp_LocalFree
0x1800a20d1  nop     dword ptr [rax+rax+00h]
0x1800a20d6  mov     rcx, rbx; hMem
0x1800a20d9  call    cs:__imp_LocalFree
0x1800a20e0  nop     dword ptr [rax+rax+00h]
0x1800a20e5  mov     cs:gpIpSecSrvList, rdi
0x1800a20ec  mov     edx, esi
0x1800a20ee  lea     rcx, aDwdeleteclient; "DwDeleteClientIpSecFilter: dwStatus=0x%"...
0x1800a20f5  call    RasIpsecTrace
0x1800a20fa  mov     eax, esi
0x1800a20fc  mov     rbx, [rsp+48h+arg_8]
0x1800a2101  mov     rsi, [rsp+48h+arg_10]
0x1800a2106  add     rsp, 40h
0x1800a210a  pop     rdi
0x1800a210b  retn
```
