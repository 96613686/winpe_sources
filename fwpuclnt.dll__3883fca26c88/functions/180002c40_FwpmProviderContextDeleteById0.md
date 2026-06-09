# FwpmProviderContextDeleteById0

- ea: `0x180002c40`
- end: `0x180002cd4`
- name: `FwpmProviderContextDeleteById0`
- size: `148`
- prototype: `DWORD __stdcall(HANDLE engineHandle, UINT64 id)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002c40`
- `0x1800034e0`
- `0x180004540`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002c86`
- `RPCRT4!NdrClientCall3` at `0x180002c86`

## string_xrefs

- `0x180002c54`: `FwpmProviderContextDeleteById0`
- `0x180002c96`: `FwppProxyProviderContextDeleteById`
- `0x180002cb5`: `BfeRpcProviderContextDeleteById`

## pseudocode

```c
DWORD __stdcall FwpmProviderContextDeleteById0(HANDLE engineHandle, UINT64 id)
{
  __int64 v3; // r8
  const char *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned int Pointer; // eax

  if ( !engineHandle )
  {
    v3 = 2150760476LL;
    v4 = "FwpmProviderContextDeleteById0";
LABEL_9:
    v6 = WfpReportSysErrorAsWinError(engineHandle, v4, v3);
    return WfpErrorToFwpErr(v6);
  }
  v5 = *((_QWORD *)engineHandle + 14);
  v6 = 0;
  if ( v5 )
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, UINT64))(g_pBfeDirectDispatchTable + 24))(0, v5, id);
    if ( Pointer )
    {
      v4 = "BfeRpcProviderContextDeleteById";
      goto LABEL_8;
    }
  }
  else
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x1Bu,
                              0,
                              *(_QWORD *)engineHandle,
                              *((_QWORD *)engineHandle + 1),
                              id).Pointer;
    if ( Pointer )
    {
      v4 = "FwppProxyProviderContextDeleteById";
LABEL_8:
      v3 = Pointer;
      goto LABEL_9;
    }
  }
  return WfpErrorToFwpErr(v6);
}

```

## disassembly

```asm
0x180002c40  push    rbx
0x180002c42  sub     rsp, 30h
0x180002c46  mov     r8, rdx
0x180002c49  test    rcx, rcx
0x180002c4c  jnz     short loc_180002C5D
0x180002c4e  mov     r8d, 8032001Ch
0x180002c54  lea     rdx, aFwpmproviderco_33; "FwpmProviderContextDeleteById0"
0x180002c5b  jmp     short loc_180002CBF
0x180002c5d  mov     rdx, [rcx+70h]
0x180002c61  xor     ebx, ebx
0x180002c63  test    rdx, rdx
0x180002c66  jnz     short loc_180002C9F
0x180002c68  mov     rax, [rcx+8]
0x180002c6c  lea     edx, [rbx+1Bh]; nProcNum
0x180002c6f  mov     r9, [rcx]
0x180002c72  lea     rcx, pProxyInfo; pProxyInfo
0x180002c79  mov     [rsp+38h+var_10], r8
0x180002c7e  xor     r8d, r8d; pReturnValue
0x180002c81  mov     [rsp+38h+var_18], rax
0x180002c86  call    cs:__imp_NdrClientCall3
0x180002c8d  nop     dword ptr [rax+rax+00h]
0x180002c92  test    eax, eax
0x180002c94  jz      short loc_180002CC7
0x180002c96  lea     rdx, aFwppproxyprovi; "FwppProxyProviderContextDeleteById"
0x180002c9d  jmp     short loc_180002CBC
0x180002c9f  mov     rax, cs:g_pBfeDirectDispatchTable
0x180002ca6  xor     ecx, ecx
0x180002ca8  mov     rax, [rax+18h]
0x180002cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb1  test    eax, eax
0x180002cb3  jz      short loc_180002CC7
0x180002cb5  lea     rdx, aBferpcprovider; "BfeRpcProviderContextDeleteById"
0x180002cbc  mov     r8d, eax
0x180002cbf  call    WfpReportSysErrorAsWinError
0x180002cc4  mov     rbx, rax
0x180002cc7  mov     rcx, rbx
0x180002cca  add     rsp, 30h
0x180002cce  pop     rbx
0x180002ccf  jmp     WfpErrorToFwpErr
```
