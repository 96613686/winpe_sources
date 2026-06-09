# DwDeleteClientIpSecFilter

- ea: `0x18007f8b8`
- end: `0x18007fa74`
- name: `DwDeleteClientIpSecFilter`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003fe00`

## callees

- `0x18007f8b8`
- `0x1800801e0`
- `0x180080264`
- `0x1800803a8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18007fa3e`
- `KERNEL32!LocalFree` at `0x18007fa47`
- `KERNEL32!LocalFree` at `0x18007fa3e`
- `KERNEL32!LocalFree` at `0x18007fa47`
- `RPCRT4!UuidIsNil` at `0x18007f985`
- `RPCRT4!UuidIsNil` at `0x18007f9ba`
- `RPCRT4!UuidIsNil` at `0x18007f985`
- `RPCRT4!UuidIsNil` at `0x18007f9ba`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007f9ed`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007f9ed`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007f99a`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007f9ce`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007f99a`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18007f9ce`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18007f95d`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18007f95d`

## string_xrefs

- `0x18007f969`: `FwpmFilterDeleteByKey0: dwStatus=0x%x`
- `0x18007f9a6`: `FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x`
- `0x18007f9da`: `FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x`
- `0x18007fa56`: `DwDeleteClientIpSecFilter: dwStatus=0x%x`

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
0x18007f8b8  mov     rax, rsp
0x18007f8bb  mov     [rax+10h], rbx
0x18007f8bf  mov     [rax+18h], rsi
0x18007f8c3  push    rdi
0x18007f8c4  sub     rsp, 40h
0x18007f8c8  movaps  xmm0, xmmword ptr [rcx]
0x18007f8cb  lea     rdx, [rsp+48h+var_28]
0x18007f8d0  movaps  xmmword ptr [rax-28h], xmm0
0x18007f8d4  mov     dword ptr [rax+8], 0
0x18007f8db  mov     eax, [rcx+10h]
0x18007f8de  mov     [rsp+48h+var_18], eax
0x18007f8e2  call    FindServerNode
0x18007f8e7  mov     rbx, rax
0x18007f8ea  test    rax, rax
0x18007f8ed  jnz     short loc_18007F8F7
0x18007f8ef  lea     esi, [rax+57h]
0x18007f8f2  jmp     loc_18007FA62
0x18007f8f7  mov     eax, [rax+34h]
0x18007f8fa  xor     esi, esi
0x18007f8fc  cmp     eax, 1
0x18007f8ff  jbe     short loc_18007F90B
0x18007f901  dec     eax
0x18007f903  mov     [rbx+34h], eax
0x18007f906  jmp     loc_18007FA54
0x18007f90b  mov     ecx, [rbx+4Ch]
0x18007f90e  test    ecx, ecx
0x18007f910  jz      short loc_18007F925
0x18007f912  sub     ecx, 1
0x18007f915  jz      short loc_18007F925
0x18007f917  sub     ecx, 1
0x18007f91a  jz      short loc_18007F925
0x18007f91c  cmp     ecx, 1
0x18007f91f  jnz     loc_18007F9F5
0x18007f925  call    FwpmTransactionBegin0Wrapper
0x18007f92a  mov     edi, eax
0x18007f92c  test    eax, eax
0x18007f92e  jz      short loc_18007F945
0x18007f930  mov     edx, eax
0x18007f932  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18007f939  call    RasIpsecTrace
0x18007f93e  mov     eax, edi
0x18007f940  jmp     loc_18007FA64
0x18007f945  xor     edi, edi
0x18007f947  cmp     [rbx+30h], esi
0x18007f94a  jbe     short loc_18007F97C
0x18007f94c  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007f953  mov     edx, edi
0x18007f955  shl     rdx, 4
0x18007f959  add     rdx, [rbx+20h]; key
0x18007f95d  call    cs:__imp_FwpmFilterDeleteByKey0
0x18007f963  test    eax, eax
0x18007f965  jz      short loc_18007F975
0x18007f967  mov     edx, eax
0x18007f969  lea     rcx, aFwpmfilterdele_0; "FwpmFilterDeleteByKey0: dwStatus=0x%x"
0x18007f970  call    RasIpsecTrace
0x18007f975  inc     edi
0x18007f977  cmp     edi, [rbx+30h]
0x18007f97a  jb      short loc_18007F94C
0x18007f97c  lea     rdx, [rsp+48h+Status]; Status
0x18007f981  lea     rcx, [rbx+10h]; Uuid
0x18007f985  call    cs:__imp_UuidIsNil
0x18007f98b  test    eax, eax
0x18007f98d  jnz     short loc_18007F9B2
0x18007f98f  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007f996  lea     rdx, [rbx+10h]; key
0x18007f99a  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18007f9a0  test    eax, eax
0x18007f9a2  jz      short loc_18007F9B2
0x18007f9a4  mov     edx, eax
0x18007f9a6  lea     rcx, aFwpmproviderco_4; "FwpmProviderContextDeleteByKey0 QM: dwS"...
0x18007f9ad  call    RasIpsecTrace
0x18007f9b2  lea     rdx, [rsp+48h+Status]; Status
0x18007f9b7  mov     rcx, rbx; Uuid
0x18007f9ba  call    cs:__imp_UuidIsNil
0x18007f9c0  test    eax, eax
0x18007f9c2  jnz     short loc_18007F9E6
0x18007f9c4  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007f9cb  mov     rdx, rbx; key
0x18007f9ce  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18007f9d4  test    eax, eax
0x18007f9d6  jz      short loc_18007F9E6
0x18007f9d8  mov     edx, eax
0x18007f9da  lea     rcx, aFwpmproviderco_0; "FwpmProviderContextDeleteByKey0 MM: dwS"...
0x18007f9e1  call    RasIpsecTrace
0x18007f9e6  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007f9ed  call    cs:__imp_FwpmTransactionCommit0
0x18007f9f3  mov     esi, eax
0x18007f9f5  dec     dword ptr [rbx+34h]
0x18007f9f8  mov     rdi, cs:gpIpSecSrvList
0x18007f9ff  test    rdi, rdi
0x18007fa02  jz      short loc_18007FA4D
0x18007fa04  cmp     rbx, rdi
0x18007fa07  jnz     short loc_18007FA0F
0x18007fa09  mov     rdi, [rdi+50h]
0x18007fa0d  jmp     short loc_18007FA35
0x18007fa0f  cmp     qword ptr [rdi+50h], 0
0x18007fa14  mov     rax, rdi
0x18007fa17  jz      short loc_18007FA4D
0x18007fa19  lea     rcx, [rax+50h]
0x18007fa1d  mov     rax, [rcx]
0x18007fa20  cmp     rax, rbx
0x18007fa23  jz      short loc_18007FA2E
0x18007fa25  cmp     qword ptr [rax+50h], 0
0x18007fa2a  jnz     short loc_18007FA19
0x18007fa2c  jmp     short loc_18007FA4D
0x18007fa2e  mov     rax, [rax+50h]
0x18007fa32  mov     [rcx], rax
0x18007fa35  mov     rcx, [rbx+20h]; hMem
0x18007fa39  test    rcx, rcx
0x18007fa3c  jz      short loc_18007FA44
0x18007fa3e  call    cs:__imp_LocalFree
0x18007fa44  mov     rcx, rbx; hMem
0x18007fa47  call    cs:__imp_LocalFree
0x18007fa4d  mov     cs:gpIpSecSrvList, rdi
0x18007fa54  mov     edx, esi
0x18007fa56  lea     rcx, aDwdeleteclient; "DwDeleteClientIpSecFilter: dwStatus=0x%"...
0x18007fa5d  call    RasIpsecTrace
0x18007fa62  mov     eax, esi
0x18007fa64  mov     rbx, [rsp+48h+arg_8]
0x18007fa69  mov     rsi, [rsp+48h+arg_10]
0x18007fa6e  add     rsp, 40h
0x18007fa72  pop     rdi
0x18007fa73  retn
```
