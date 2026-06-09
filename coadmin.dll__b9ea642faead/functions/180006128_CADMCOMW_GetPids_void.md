# CADMCOMW::GetPids(void)

- ea: `0x180006128`
- end: `0x180006191`
- name: `?GetPids@CADMCOMW@@SAJXZ`
- size: `105`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a0b0`

## callees

- `0x180006128`
- `0x180009bd8`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180006130`
- `KERNEL32!GetCurrentProcessId` at `0x180006130`
- `IisRTL!PuDbgPrint` at `0x180006183`
- `IisRTL!PuDbgPrint` at `0x180006183`

## string_xrefs

- `0x18000616a`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180006171`: `_GetServicePid(RpcSs) failed hr=0x%08x.\n`
- `0x18000615f`: `CADMCOMW::GetPids`

## pseudocode

```c
__int64 CADMCOMW::GetPids(void)
{
  unsigned int v0; // ebx
  int ServicePid; // eax

  v0 = 0;
  CADMCOMW::sm_dwProcessIdThis = GetCurrentProcessId();
  if ( !CADMCOMW::sm_dwProcessIdRpcSs )
  {
    ServicePid = GetServicePid();
    v0 = ServicePid;
    if ( ServicePid < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        7592,
        "CADMCOMW::GetPids",
        "_GetServicePid(RpcSs) failed hr=0x%08x.\n",
        ServicePid);
  }
  return v0;
}

```

## disassembly

```asm
0x180006128  push    rbx
0x18000612a  sub     rsp, 30h
0x18000612e  xor     ebx, ebx
0x180006130  call    cs:__imp_GetCurrentProcessId
0x180006136  cmp     cs:?sm_dwProcessIdRpcSs@CADMCOMW@@2KA, ebx; ulong CADMCOMW::sm_dwProcessIdRpcSs
0x18000613c  mov     cs:?sm_dwProcessIdThis@CADMCOMW@@2KA, eax; ulong CADMCOMW::sm_dwProcessIdThis
0x180006142  jnz     short loc_180006189
0x180006144  call    _GetServicePid
0x180006149  mov     ebx, eax
0x18000614b  test    eax, eax
0x18000614d  jns     short loc_180006189
0x18000614f  test    byte ptr cs:g_dwDebugFlags, 3
0x180006156  jz      short loc_180006189
0x180006158  mov     rcx, cs:g_pDebug
0x18000615f  lea     r9, aCadmcomwGetpid; "CADMCOMW::GetPids"
0x180006166  mov     [rsp+38h+var_10], eax
0x18000616a  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180006171  lea     rax, aGetservicepidR; "_GetServicePid(RpcSs) failed hr=0x%08x."...
0x180006178  mov     r8d, 1DA8h
0x18000617e  mov     [rsp+38h+var_18], rax
0x180006183  call    cs:__imp_PuDbgPrint
0x180006189  mov     eax, ebx
0x18000618b  add     rsp, 30h
0x18000618f  pop     rbx
0x180006190  retn
```
