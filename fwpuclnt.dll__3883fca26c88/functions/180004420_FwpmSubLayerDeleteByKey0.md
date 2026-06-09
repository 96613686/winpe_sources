# FwpmSubLayerDeleteByKey0

- ea: `0x180004420`
- end: `0x1800044b6`
- name: `FwpmSubLayerDeleteByKey0`
- size: `150`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800034e0`
- `0x180004420`
- `0x180004540`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004457`
- `RPCRT4!NdrClientCall3` at `0x180004457`

## string_xrefs

- `0x18000447a`: `FwpmSubLayerDeleteByKey0`
- `0x180004483`: `FwppProxySubLayerDeleteByKey`
- `0x1800044a2`: `BfeRpcSubLayerDeleteByKey`

## pseudocode

```c
DWORD __stdcall FwpmSubLayerDeleteByKey0(HANDLE engineHandle, const GUID *key)
{
  __int64 v3; // rdx
  unsigned int Pointer; // eax
  __int64 v6; // r8
  const char *v7; // rdx
  __int64 v8; // rbx

  if ( !engineHandle )
  {
    v6 = 2150760476LL;
    v7 = "FwpmSubLayerDeleteByKey0";
LABEL_11:
    v8 = WfpReportSysErrorAsWinError(engineHandle, v7, v6);
    return WfpErrorToFwpErr(v8);
  }
  v3 = *((_QWORD *)engineHandle + 14);
  if ( v3 )
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, const GUID *))(g_pBfeDirectDispatchTable + 80))(0, v3, key);
    if ( !Pointer )
      return WfpErrorToFwpErr(0);
    v7 = "BfeRpcSubLayerDeleteByKey";
    goto LABEL_10;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x28u,
                            0,
                            *(_QWORD *)engineHandle,
                            *((_QWORD *)engineHandle + 1),
                            key).Pointer;
  if ( Pointer )
  {
    v7 = "FwppProxySubLayerDeleteByKey";
LABEL_10:
    v6 = Pointer;
    goto LABEL_11;
  }
  return WfpErrorToFwpErr(0);
}

```

## disassembly

```asm
0x180004420  push    rbx
0x180004422  sub     rsp, 30h
0x180004426  mov     r8, rdx
0x180004429  test    rcx, rcx
0x18000442c  jz      short loc_180004474
0x18000442e  mov     rdx, [rcx+70h]
0x180004432  xor     ebx, ebx
0x180004434  test    rdx, rdx
0x180004437  jnz     short loc_18000448C
0x180004439  mov     rax, [rcx+8]
0x18000443d  lea     edx, [rbx+28h]; nProcNum
0x180004440  mov     r9, [rcx]
0x180004443  lea     rcx, pProxyInfo; pProxyInfo
0x18000444a  mov     [rsp+38h+var_10], r8
0x18000444f  xor     r8d, r8d; pReturnValue
0x180004452  mov     [rsp+38h+var_18], rax
0x180004457  call    cs:__imp_NdrClientCall3
0x18000445e  nop     dword ptr [rax+rax+00h]
0x180004463  test    eax, eax
0x180004465  jnz     short loc_180004483
0x180004467  mov     rcx, rbx
0x18000446a  add     rsp, 30h
0x18000446e  pop     rbx
0x18000446f  jmp     WfpErrorToFwpErr
0x180004474  mov     r8d, 8032001Ch
0x18000447a  lea     rdx, aFwpmsublayerde_1; "FwpmSubLayerDeleteByKey0"
0x180004481  jmp     short loc_1800044AC
0x180004483  lea     rdx, aFwppproxysubla_5; "FwppProxySubLayerDeleteByKey"
0x18000448a  jmp     short loc_1800044A9
0x18000448c  mov     rax, cs:g_pBfeDirectDispatchTable
0x180004493  xor     ecx, ecx
0x180004495  mov     rax, [rax+50h]
0x180004499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449e  test    eax, eax
0x1800044a0  jz      short loc_180004467
0x1800044a2  lea     rdx, aBferpcsublayer; "BfeRpcSubLayerDeleteByKey"
0x1800044a9  mov     r8d, eax
0x1800044ac  call    WfpReportSysErrorAsWinError
0x1800044b1  mov     rbx, rax
0x1800044b4  jmp     short loc_180004467
```
