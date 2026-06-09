# FhServiceExitMaintenanceMode

- ea: `0x180002f90`
- end: `0x18000306a`
- name: `FhServiceExitMaintenanceMode`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180002f90`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002ffd`
- `RPCRT4!NdrClientCall3` at `0x180002ffd`

## pseudocode

```c
__int64 __fastcall FhServiceExitMaintenanceMode(_QWORD *a1)
{
  int Pointer; // eax
  unsigned int v3; // ebx

  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 7u, 0, *a1, a1[1]).Pointer;
    v3 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(10);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002f90  push    rbx
0x180002f92  sub     rsp, 40h
0x180002f96  test    rcx, rcx
0x180002f99  jnz     short loc_180002FDA
0x180002f9b  lea     rax, WPP_GLOBAL_Control
0x180002fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fa9  cmp     rcx, rax
0x180002fac  jz      short loc_180002FD0
0x180002fae  test    byte ptr [rcx+1Ch], 1
0x180002fb2  jz      short loc_180002FD0
0x180002fb4  mov     edx, 24h ; '$'
0x180002fb9  lea     r9, aPipe; "Pipe"
0x180002fc0  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002fc7  mov     rcx, [rcx+10h]
0x180002fcb  call    WPP_SF_s
0x180002fd0  mov     eax, 80070057h
0x180002fd5  jmp     loc_180003064
0x180002fda  mov     rax, [rcx+8]
0x180002fde  mov     [rsp+48h+arg_0], 0
0x180002fe7  mov     [rsp+48h+var_28], rax
0x180002fec  mov     r9, [rcx]
0x180002fef  xor     r8d, r8d; pReturnValue
0x180002ff2  lea     edx, [r8+7]; nProcNum
0x180002ff6  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002ffd  call    cs:__imp_NdrClientCall3
0x180003003  mov     rbx, rax
0x180003006  mov     [rsp+48h+arg_0], rax
0x18000300b  mov     [rsp+48h+var_18], eax
0x18000300f  jmp     short loc_180003023
0x180003011  test    eax, eax
0x180003013  jle     short loc_18000301D
0x180003015  movzx   eax, ax
0x180003018  or      eax, 80070000h
0x18000301d  mov     ebx, eax
0x18000301f  mov     [rsp+48h+var_18], eax
0x180003023  test    ebx, ebx
0x180003025  jns     short loc_180003058
0x180003027  lea     rax, WPP_GLOBAL_Control
0x18000302e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003035  cmp     rcx, rax
0x180003038  jz      short loc_180003058
0x18000303a  test    byte ptr [rcx+1Ch], 1
0x18000303e  jz      short loc_180003058
0x180003040  mov     edx, 25h ; '%'
0x180003045  mov     r9d, ebx
0x180003048  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x18000304f  mov     rcx, [rcx+10h]
0x180003053  call    WPP_SF_d
0x180003058  mov     ecx, 0Ah
0x18000305d  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180003062  mov     eax, ebx
0x180003064  add     rsp, 40h
0x180003068  pop     rbx
0x180003069  retn
```
