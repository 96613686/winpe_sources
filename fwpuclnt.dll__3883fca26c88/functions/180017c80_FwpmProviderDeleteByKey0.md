# FwpmProviderDeleteByKey0

- ea: `0x180017c80`
- end: `0x180017d14`
- name: `FwpmProviderDeleteByKey0`
- size: `148`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800034e0`
- `0x180004540`
- `0x180017c80`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180017cc6`
- `RPCRT4!NdrClientCall3` at `0x180017cc6`

## string_xrefs

- `0x180017c94`: `FwpmProviderDeleteByKey0`
- `0x180017cd6`: `FwppProxyProviderDeleteByKey`
- `0x180017cf5`: `BfeRpcProviderDeleteByKey`

## pseudocode

```c
DWORD __stdcall FwpmProviderDeleteByKey0(HANDLE engineHandle, const GUID *key)
{
  __int64 v3; // r8
  const char *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned int Pointer; // eax

  if ( !engineHandle )
  {
    v3 = 2150760476LL;
    v4 = "FwpmProviderDeleteByKey0";
LABEL_9:
    v6 = WfpReportSysErrorAsWinError(engineHandle, v4, v3);
    return WfpErrorToFwpErr(v6);
  }
  v5 = *((_QWORD *)engineHandle + 14);
  v6 = 0;
  if ( v5 )
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, const GUID *))(g_pBfeDirectDispatchTable + 72))(0, v5, key);
    if ( Pointer )
    {
      v4 = "BfeRpcProviderDeleteByKey";
      goto LABEL_8;
    }
  }
  else
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x10u,
                              0,
                              *(_QWORD *)engineHandle,
                              *((_QWORD *)engineHandle + 1),
                              key).Pointer;
    if ( Pointer )
    {
      v4 = "FwppProxyProviderDeleteByKey";
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
0x180017c80  push    rbx
0x180017c82  sub     rsp, 30h
0x180017c86  mov     r8, rdx
0x180017c89  test    rcx, rcx
0x180017c8c  jnz     short loc_180017C9D
0x180017c8e  mov     r8d, 8032001Ch
0x180017c94  lea     rdx, aFwpmproviderde_1; "FwpmProviderDeleteByKey0"
0x180017c9b  jmp     short loc_180017CFF
0x180017c9d  mov     rdx, [rcx+70h]
0x180017ca1  xor     ebx, ebx
0x180017ca3  test    rdx, rdx
0x180017ca6  jnz     short loc_180017CDF
0x180017ca8  mov     rax, [rcx+8]
0x180017cac  lea     edx, [rbx+10h]; nProcNum
0x180017caf  mov     r9, [rcx]
0x180017cb2  lea     rcx, pProxyInfo; pProxyInfo
0x180017cb9  mov     [rsp+38h+var_10], r8
0x180017cbe  xor     r8d, r8d; pReturnValue
0x180017cc1  mov     [rsp+38h+var_18], rax
0x180017cc6  call    cs:__imp_NdrClientCall3
0x180017ccd  nop     dword ptr [rax+rax+00h]
0x180017cd2  test    eax, eax
0x180017cd4  jz      short loc_180017D07
0x180017cd6  lea     rdx, aFwppproxyprovi_0; "FwppProxyProviderDeleteByKey"
0x180017cdd  jmp     short loc_180017CFC
0x180017cdf  mov     rax, cs:g_pBfeDirectDispatchTable
0x180017ce6  xor     ecx, ecx
0x180017ce8  mov     rax, [rax+48h]
0x180017cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf1  test    eax, eax
0x180017cf3  jz      short loc_180017D07
0x180017cf5  lea     rdx, aBferpcprovider_1; "BfeRpcProviderDeleteByKey"
0x180017cfc  mov     r8d, eax
0x180017cff  call    WfpReportSysErrorAsWinError
0x180017d04  mov     rbx, rax
0x180017d07  mov     rcx, rbx
0x180017d0a  add     rsp, 30h
0x180017d0e  pop     rbx
0x180017d0f  jmp     WfpErrorToFwpErr
```
