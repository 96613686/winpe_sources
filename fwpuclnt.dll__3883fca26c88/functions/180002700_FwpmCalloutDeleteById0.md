# FwpmCalloutDeleteById0

- ea: `0x180002700`
- end: `0x180002794`
- name: `FwpmCalloutDeleteById0`
- size: `148`
- prototype: `DWORD __stdcall(HANDLE engineHandle, UINT32 id)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002700`
- `0x1800034e0`
- `0x180004540`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002746`
- `RPCRT4!NdrClientCall3` at `0x180002746`

## string_xrefs

- `0x180002714`: `FwpmCalloutDeleteById0`
- `0x180002756`: `FwppProxyCalloutDeleteById`
- `0x180002775`: `BfeRpcCalloutDeleteById`

## pseudocode

```c
DWORD __stdcall FwpmCalloutDeleteById0(HANDLE engineHandle, UINT32 id)
{
  __int64 v2; // r8
  __int64 v3; // r8
  const char *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned int Pointer; // eax

  v2 = id;
  if ( !engineHandle )
  {
    v3 = 2150760476LL;
    v4 = "FwpmCalloutDeleteById0";
LABEL_9:
    v6 = WfpReportSysErrorAsWinError(engineHandle, v4, v3);
    return WfpErrorToFwpErr(v6);
  }
  v5 = *((_QWORD *)engineHandle + 14);
  v6 = 0;
  if ( v5 )
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(g_pBfeDirectDispatchTable + 32))(0, v5, v2);
    if ( Pointer )
    {
      v4 = "BfeRpcCalloutDeleteById";
      goto LABEL_8;
    }
  }
  else
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x3Au,
                              0,
                              *(_QWORD *)engineHandle,
                              *((_QWORD *)engineHandle + 1),
                              v2).Pointer;
    if ( Pointer )
    {
      v4 = "FwppProxyCalloutDeleteById";
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
0x180002700  push    rbx
0x180002702  sub     rsp, 30h
0x180002706  mov     r8d, edx
0x180002709  test    rcx, rcx
0x18000270c  jnz     short loc_18000271D
0x18000270e  mov     r8d, 8032001Ch
0x180002714  lea     rdx, aFwpmcalloutdel_2; "FwpmCalloutDeleteById0"
0x18000271b  jmp     short loc_18000277F
0x18000271d  mov     rdx, [rcx+70h]
0x180002721  xor     ebx, ebx
0x180002723  test    rdx, rdx
0x180002726  jnz     short loc_18000275F
0x180002728  mov     rax, [rcx+8]
0x18000272c  lea     edx, [rbx+3Ah]; nProcNum
0x18000272f  mov     r9, [rcx]
0x180002732  lea     rcx, pProxyInfo; pProxyInfo
0x180002739  mov     [rsp+38h+var_10], r8
0x18000273e  xor     r8d, r8d; pReturnValue
0x180002741  mov     [rsp+38h+var_18], rax
0x180002746  call    cs:__imp_NdrClientCall3
0x18000274d  nop     dword ptr [rax+rax+00h]
0x180002752  test    eax, eax
0x180002754  jz      short loc_180002787
0x180002756  lea     rdx, aFwppproxycallo_1; "FwppProxyCalloutDeleteById"
0x18000275d  jmp     short loc_18000277C
0x18000275f  mov     rax, cs:g_pBfeDirectDispatchTable
0x180002766  xor     ecx, ecx
0x180002768  mov     rax, [rax+20h]
0x18000276c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002771  test    eax, eax
0x180002773  jz      short loc_180002787
0x180002775  lea     rdx, aBferpccalloutd; "BfeRpcCalloutDeleteById"
0x18000277c  mov     r8d, eax
0x18000277f  call    WfpReportSysErrorAsWinError
0x180002784  mov     rbx, rax
0x180002787  mov     rcx, rbx
0x18000278a  add     rsp, 30h
0x18000278e  pop     rbx
0x18000278f  jmp     WfpErrorToFwpErr
```
