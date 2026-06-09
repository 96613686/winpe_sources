# FwpmCalloutDeleteByKey0

- ea: `0x180002660`
- end: `0x1800026f4`
- name: `FwpmCalloutDeleteByKey0`
- size: `148`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002660`
- `0x1800034e0`
- `0x180004540`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800026a6`
- `RPCRT4!NdrClientCall3` at `0x1800026a6`

## string_xrefs

- `0x180002674`: `FwpmCalloutDeleteByKey0`
- `0x1800026b6`: `FwppProxyCalloutDeleteByKey`
- `0x1800026d5`: `BfeRpcCalloutDeleteByKey`

## pseudocode

```c
DWORD __stdcall FwpmCalloutDeleteByKey0(HANDLE engineHandle, const GUID *key)
{
  __int64 v3; // r8
  const char *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned int Pointer; // eax

  if ( !engineHandle )
  {
    v3 = 2150760476LL;
    v4 = "FwpmCalloutDeleteByKey0";
LABEL_9:
    v6 = WfpReportSysErrorAsWinError(engineHandle, v4, v3);
    return WfpErrorToFwpErr(v6);
  }
  v5 = *((_QWORD *)engineHandle + 14);
  v6 = 0;
  if ( v5 )
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, const GUID *))(g_pBfeDirectDispatchTable + 56))(0, v5, key);
    if ( Pointer )
    {
      v4 = "BfeRpcCalloutDeleteByKey";
      goto LABEL_8;
    }
  }
  else
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x3Bu,
                              0,
                              *(_QWORD *)engineHandle,
                              *((_QWORD *)engineHandle + 1),
                              key).Pointer;
    if ( Pointer )
    {
      v4 = "FwppProxyCalloutDeleteByKey";
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
0x180002660  push    rbx
0x180002662  sub     rsp, 30h
0x180002666  mov     r8, rdx
0x180002669  test    rcx, rcx
0x18000266c  jnz     short loc_18000267D
0x18000266e  mov     r8d, 8032001Ch
0x180002674  lea     rdx, aFwpmcalloutdel_1; "FwpmCalloutDeleteByKey0"
0x18000267b  jmp     short loc_1800026DF
0x18000267d  mov     rdx, [rcx+70h]
0x180002681  xor     ebx, ebx
0x180002683  test    rdx, rdx
0x180002686  jnz     short loc_1800026BF
0x180002688  mov     rax, [rcx+8]
0x18000268c  lea     edx, [rbx+3Bh]; nProcNum
0x18000268f  mov     r9, [rcx]
0x180002692  lea     rcx, pProxyInfo; pProxyInfo
0x180002699  mov     [rsp+38h+var_10], r8
0x18000269e  xor     r8d, r8d; pReturnValue
0x1800026a1  mov     [rsp+38h+var_18], rax
0x1800026a6  call    cs:__imp_NdrClientCall3
0x1800026ad  nop     dword ptr [rax+rax+00h]
0x1800026b2  test    eax, eax
0x1800026b4  jz      short loc_1800026E7
0x1800026b6  lea     rdx, aFwppproxycallo_5; "FwppProxyCalloutDeleteByKey"
0x1800026bd  jmp     short loc_1800026DC
0x1800026bf  mov     rax, cs:g_pBfeDirectDispatchTable
0x1800026c6  xor     ecx, ecx
0x1800026c8  mov     rax, [rax+38h]
0x1800026cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d1  test    eax, eax
0x1800026d3  jz      short loc_1800026E7
0x1800026d5  lea     rdx, aBferpccalloutd_0; "BfeRpcCalloutDeleteByKey"
0x1800026dc  mov     r8d, eax
0x1800026df  call    WfpReportSysErrorAsWinError
0x1800026e4  mov     rbx, rax
0x1800026e7  mov     rcx, rbx
0x1800026ea  add     rsp, 30h
0x1800026ee  pop     rbx
0x1800026ef  jmp     WfpErrorToFwpErr
```
