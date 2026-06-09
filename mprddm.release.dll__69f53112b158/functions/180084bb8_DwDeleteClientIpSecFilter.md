# DwDeleteClientIpSecFilter

- ea: `0x180084bb8`
- end: `0x180084dad`
- name: `DwDeleteClientIpSecFilter`
- size: `501`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180041670`

## callees

- `0x180084bb8`
- `0x180085a90`
- `0x180085b20`
- `0x180085cb4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180084d62`
- `KERNEL32!LocalFree` at `0x180084d71`
- `KERNEL32!LocalFree` at `0x180084d62`
- `KERNEL32!LocalFree` at `0x180084d71`
- `RPCRT4!UuidIsNil` at `0x180084c8d`
- `RPCRT4!UuidIsNil` at `0x180084cce`
- `RPCRT4!UuidIsNil` at `0x180084c8d`
- `RPCRT4!UuidIsNil` at `0x180084cce`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180084d0d`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180084d0d`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084ca8`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084ce8`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084ca8`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180084ce8`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180084c5f`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180084c5f`

## string_xrefs

- `0x180084c71`: `FwpmFilterDeleteByKey0: dwStatus=0x%x`
- `0x180084cba`: `FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x`
- `0x180084cfa`: `FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x`
- `0x180084d89`: `DwDeleteClientIpSecFilter: dwStatus=0x%x`

## pseudocode

```c
__int64 __fastcall DwDeleteClientIpSecFilter(__int128 *a1)
{
  __int64 v1; // rbx
  DWORD v2; // ebp
  __int64 ServerNode; // rax
  __int64 v4; // rdi
  unsigned int v5; // eax
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // esi
  unsigned int i; // esi
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  void *v14; // rcx
  __int128 v15; // [rsp+20h] [rbp-28h] BYREF
  int v16; // [rsp+30h] [rbp-18h]
  RPC_STATUS Status; // [rsp+50h] [rbp+8h] BYREF

  v15 = *a1;
  v1 = 0;
  Status = 0;
  v2 = 0;
  v16 = *((_DWORD *)a1 + 4);
  ServerNode = FindServerNode(a1, &v15);
  v4 = ServerNode;
  if ( ServerNode )
  {
    v5 = *(_DWORD *)(ServerNode + 52);
    if ( v5 <= 1 )
    {
      v6 = *(_DWORD *)(v4 + 76);
      if ( !v6 || (v7 = v6 - 1) == 0 || (unsigned int)(v7 - 1) <= 1 )
      {
        v8 = FwpmTransactionBegin0Wrapper();
        if ( v8 )
        {
          RasIpsecTrace("FwpmTransactionBegin0 failed with 0x%x");
          return v8;
        }
        for ( i = 0; i < *(_DWORD *)(v4 + 48); ++i )
        {
          if ( FwpmFilterDeleteByKey0(gFwpEngineHandle, (const GUID *)(*(_QWORD *)(v4 + 32) + 16LL * i)) )
            RasIpsecTrace("FwpmFilterDeleteByKey0: dwStatus=0x%x");
        }
        if ( !UuidIsNil((UUID *)(v4 + 16), &Status)
          && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, (const GUID *)(v4 + 16)) )
        {
          RasIpsecTrace("FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x");
        }
        if ( !UuidIsNil((UUID *)v4, &Status) && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, (const GUID *)v4) )
          RasIpsecTrace("FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x");
        v2 = FwpmTransactionCommit0(gFwpEngineHandle);
      }
      --*(_DWORD *)(v4 + 52);
      v11 = gpIpSecSrvList;
      if ( gpIpSecSrvList )
      {
        if ( v4 == gpIpSecSrvList )
        {
          v11 = *(_QWORD *)(gpIpSecSrvList + 80);
LABEL_30:
          v14 = *(void **)(v4 + 32);
          if ( v14 )
            LocalFree(v14);
          LocalFree((HLOCAL)v4);
        }
        else
        {
          v12 = *(_QWORD *)(gpIpSecSrvList + 80);
          v13 = gpIpSecSrvList;
          while ( v12 )
          {
            if ( v12 == v4 )
            {
              *(_QWORD *)(v13 + 80) = *(_QWORD *)(v12 + 80);
              goto LABEL_30;
            }
            v13 = v12;
            v12 = *(_QWORD *)(v12 + 80);
          }
        }
        v1 = v11;
      }
      gpIpSecSrvList = v1;
    }
    else
    {
      *(_DWORD *)(v4 + 52) = v5 - 1;
    }
    RasIpsecTrace("DwDeleteClientIpSecFilter: dwStatus=0x%x");
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x180084bb8  mov     rax, rsp
0x180084bbb  mov     [rax+10h], rbx
0x180084bbf  mov     [rax+18h], rbp
0x180084bc3  mov     [rax+20h], rsi
0x180084bc7  push    rdi
0x180084bc8  sub     rsp, 40h
0x180084bcc  movaps  xmm0, xmmword ptr [rcx]
0x180084bcf  lea     rdx, [rsp+48h+var_28]
0x180084bd4  movaps  xmmword ptr [rax-28h], xmm0
0x180084bd8  xor     ebx, ebx
0x180084bda  mov     [rax+8], ebx
0x180084bdd  mov     ebp, ebx
0x180084bdf  mov     eax, [rcx+10h]
0x180084be2  mov     [rsp+48h+var_18], eax
0x180084be6  call    FindServerNode
0x180084beb  mov     rdi, rax
0x180084bee  test    rax, rax
0x180084bf1  jnz     short loc_180084BFB
0x180084bf3  lea     ebp, [rbx+57h]
0x180084bf6  jmp     loc_180084D95
0x180084bfb  mov     eax, [rax+34h]
0x180084bfe  cmp     eax, 1
0x180084c01  jbe     short loc_180084C0D
0x180084c03  dec     eax
0x180084c05  mov     [rdi+34h], eax
0x180084c08  jmp     loc_180084D87
0x180084c0d  mov     ecx, [rdi+4Ch]
0x180084c10  test    ecx, ecx
0x180084c12  jz      short loc_180084C27
0x180084c14  sub     ecx, 1
0x180084c17  jz      short loc_180084C27
0x180084c19  sub     ecx, 1
0x180084c1c  jz      short loc_180084C27
0x180084c1e  cmp     ecx, 1
0x180084c21  jnz     loc_180084D1B
0x180084c27  call    FwpmTransactionBegin0Wrapper
0x180084c2c  mov     esi, eax
0x180084c2e  test    eax, eax
0x180084c30  jz      short loc_180084C47
0x180084c32  mov     edx, eax
0x180084c34  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x180084c3b  call    RasIpsecTrace
0x180084c40  mov     eax, esi
0x180084c42  jmp     loc_180084D97
0x180084c47  mov     esi, ebx
0x180084c49  cmp     [rdi+30h], ebx
0x180084c4c  jbe     short loc_180084C84
0x180084c4e  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084c55  mov     edx, esi
0x180084c57  shl     rdx, 4
0x180084c5b  add     rdx, [rdi+20h]; key
0x180084c5f  call    cs:__imp_FwpmFilterDeleteByKey0
0x180084c66  nop     dword ptr [rax+rax+00h]
0x180084c6b  test    eax, eax
0x180084c6d  jz      short loc_180084C7D
0x180084c6f  mov     edx, eax
0x180084c71  lea     rcx, aFwpmfilterdele_0; "FwpmFilterDeleteByKey0: dwStatus=0x%x"
0x180084c78  call    RasIpsecTrace
0x180084c7d  inc     esi
0x180084c7f  cmp     esi, [rdi+30h]
0x180084c82  jb      short loc_180084C4E
0x180084c84  lea     rdx, [rsp+48h+Status]; Status
0x180084c89  lea     rcx, [rdi+10h]; Uuid
0x180084c8d  call    cs:__imp_UuidIsNil
0x180084c94  nop     dword ptr [rax+rax+00h]
0x180084c99  test    eax, eax
0x180084c9b  jnz     short loc_180084CC6
0x180084c9d  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084ca4  lea     rdx, [rdi+10h]; key
0x180084ca8  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x180084caf  nop     dword ptr [rax+rax+00h]
0x180084cb4  test    eax, eax
0x180084cb6  jz      short loc_180084CC6
0x180084cb8  mov     edx, eax
0x180084cba  lea     rcx, aFwpmproviderco_4; "FwpmProviderContextDeleteByKey0 QM: dwS"...
0x180084cc1  call    RasIpsecTrace
0x180084cc6  lea     rdx, [rsp+48h+Status]; Status
0x180084ccb  mov     rcx, rdi; Uuid
0x180084cce  call    cs:__imp_UuidIsNil
0x180084cd5  nop     dword ptr [rax+rax+00h]
0x180084cda  test    eax, eax
0x180084cdc  jnz     short loc_180084D06
0x180084cde  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084ce5  mov     rdx, rdi; key
0x180084ce8  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x180084cef  nop     dword ptr [rax+rax+00h]
0x180084cf4  test    eax, eax
0x180084cf6  jz      short loc_180084D06
0x180084cf8  mov     edx, eax
0x180084cfa  lea     rcx, aFwpmproviderco_0; "FwpmProviderContextDeleteByKey0 MM: dwS"...
0x180084d01  call    RasIpsecTrace
0x180084d06  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180084d0d  call    cs:__imp_FwpmTransactionCommit0
0x180084d14  nop     dword ptr [rax+rax+00h]
0x180084d19  mov     ebp, eax
0x180084d1b  dec     dword ptr [rdi+34h]
0x180084d1e  mov     rsi, cs:gpIpSecSrvList
0x180084d25  test    rsi, rsi
0x180084d28  jz      short loc_180084D80
0x180084d2a  cmp     rdi, rsi
0x180084d2d  jnz     short loc_180084D35
0x180084d2f  mov     rsi, [rsi+50h]
0x180084d33  jmp     short loc_180084D59
0x180084d35  mov     rax, [rsi+50h]
0x180084d39  mov     rcx, rsi
0x180084d3c  jmp     short loc_180084D4A
0x180084d3e  cmp     rax, rdi
0x180084d41  jz      short loc_180084D51
0x180084d43  mov     rcx, rax
0x180084d46  mov     rax, [rax+50h]
0x180084d4a  test    rax, rax
0x180084d4d  jnz     short loc_180084D3E
0x180084d4f  jmp     short loc_180084D7D
0x180084d51  mov     rax, [rax+50h]
0x180084d55  mov     [rcx+50h], rax
0x180084d59  mov     rcx, [rdi+20h]; hMem
0x180084d5d  test    rcx, rcx
0x180084d60  jz      short loc_180084D6E
0x180084d62  call    cs:__imp_LocalFree
0x180084d69  nop     dword ptr [rax+rax+00h]
0x180084d6e  mov     rcx, rdi; hMem
0x180084d71  call    cs:__imp_LocalFree
0x180084d78  nop     dword ptr [rax+rax+00h]
0x180084d7d  mov     rbx, rsi
0x180084d80  mov     cs:gpIpSecSrvList, rbx
0x180084d87  mov     edx, ebp
0x180084d89  lea     rcx, aDwdeleteclient; "DwDeleteClientIpSecFilter: dwStatus=0x%"...
0x180084d90  call    RasIpsecTrace
0x180084d95  mov     eax, ebp
0x180084d97  mov     rbx, [rsp+48h+arg_8]
0x180084d9c  mov     rbp, [rsp+48h+arg_10]
0x180084da1  mov     rsi, [rsp+48h+arg_18]
0x180084da6  add     rsp, 40h
0x180084daa  pop     rdi
0x180084dab  retn
```
