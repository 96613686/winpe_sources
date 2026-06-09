# FhServiceUnblockBackup

- ea: `0x1800038e0`
- end: `0x1800039c2`
- name: `FhServiceUnblockBackup`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x1800038e0`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003955`
- `RPCRT4!NdrClientCall3` at `0x180003955`

## pseudocode

```c
__int64 __fastcall FhServiceUnblockBackup(_QWORD *a1)
{
  int Pointer; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+28h] [rbp-20h]

  if ( a1 )
  {
    v4 = 0;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 4u, 0, *a1, a1[1], v4).Pointer;
    v3 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(7);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800038e0  push    rbx
0x1800038e2  sub     rsp, 40h
0x1800038e6  test    rcx, rcx
0x1800038e9  jnz     short loc_18000392A
0x1800038eb  lea     rax, WPP_GLOBAL_Control
0x1800038f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038f9  cmp     rcx, rax
0x1800038fc  jz      short loc_180003920
0x1800038fe  test    byte ptr [rcx+1Ch], 1
0x180003902  jz      short loc_180003920
0x180003904  mov     edx, 1Dh
0x180003909  lea     r9, aPipe; "Pipe"
0x180003910  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180003917  mov     rcx, [rcx+10h]
0x18000391b  call    WPP_SF_s
0x180003920  mov     eax, 80070057h
0x180003925  jmp     loc_1800039BC
0x18000392a  mov     rax, [rcx+8]
0x18000392e  mov     [rsp+48h+arg_0], 0
0x180003937  mov     [rsp+48h+var_20], 0
0x18000393f  mov     [rsp+48h+var_28], rax
0x180003944  mov     r9, [rcx]
0x180003947  xor     r8d, r8d; pReturnValue
0x18000394a  lea     edx, [r8+4]; nProcNum
0x18000394e  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003955  call    cs:__imp_NdrClientCall3
0x18000395b  mov     rbx, rax
0x18000395e  mov     [rsp+48h+arg_0], rax
0x180003963  mov     [rsp+48h+var_18], eax
0x180003967  jmp     short loc_18000397B
0x180003969  test    eax, eax
0x18000396b  jle     short loc_180003975
0x18000396d  movzx   eax, ax
0x180003970  or      eax, 80070000h
0x180003975  mov     ebx, eax
0x180003977  mov     [rsp+48h+var_18], eax
0x18000397b  test    ebx, ebx
0x18000397d  jns     short loc_1800039B0
0x18000397f  lea     rax, WPP_GLOBAL_Control
0x180003986  mov     rcx, cs:WPP_GLOBAL_Control
0x18000398d  cmp     rcx, rax
0x180003990  jz      short loc_1800039B0
0x180003992  test    byte ptr [rcx+1Ch], 1
0x180003996  jz      short loc_1800039B0
0x180003998  mov     edx, 1Eh
0x18000399d  mov     r9d, ebx
0x1800039a0  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x1800039a7  mov     rcx, [rcx+10h]
0x1800039ab  call    WPP_SF_d
0x1800039b0  mov     ecx, 7
0x1800039b5  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x1800039ba  mov     eax, ebx
0x1800039bc  add     rsp, 40h
0x1800039c0  pop     rbx
0x1800039c1  retn
```
