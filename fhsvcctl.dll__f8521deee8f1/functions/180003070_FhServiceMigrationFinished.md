# FhServiceMigrationFinished

- ea: `0x180003070`
- end: `0x18000314a`
- name: `FhServiceMigrationFinished`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180003070`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800030dd`
- `RPCRT4!NdrClientCall3` at `0x1800030dd`

## pseudocode

```c
__int64 __fastcall FhServiceMigrationFinished(_QWORD *a1)
{
  int Pointer; // eax
  unsigned int v3; // ebx

  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 9u, 0, *a1, a1[1]).Pointer;
    v3 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(12);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003070  push    rbx
0x180003072  sub     rsp, 40h
0x180003076  test    rcx, rcx
0x180003079  jnz     short loc_1800030BA
0x18000307b  lea     rax, WPP_GLOBAL_Control
0x180003082  mov     rcx, cs:WPP_GLOBAL_Control
0x180003089  cmp     rcx, rax
0x18000308c  jz      short loc_1800030B0
0x18000308e  test    byte ptr [rcx+1Ch], 1
0x180003092  jz      short loc_1800030B0
0x180003094  mov     edx, 28h ; '('
0x180003099  lea     r9, aPipe; "Pipe"
0x1800030a0  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x1800030a7  mov     rcx, [rcx+10h]
0x1800030ab  call    WPP_SF_s
0x1800030b0  mov     eax, 80070057h
0x1800030b5  jmp     loc_180003144
0x1800030ba  mov     rax, [rcx+8]
0x1800030be  mov     [rsp+48h+arg_0], 0
0x1800030c7  mov     [rsp+48h+var_28], rax
0x1800030cc  mov     r9, [rcx]
0x1800030cf  xor     r8d, r8d; pReturnValue
0x1800030d2  lea     edx, [r8+9]; nProcNum
0x1800030d6  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800030dd  call    cs:__imp_NdrClientCall3
0x1800030e3  mov     rbx, rax
0x1800030e6  mov     [rsp+48h+arg_0], rax
0x1800030eb  mov     [rsp+48h+var_18], eax
0x1800030ef  jmp     short loc_180003103
0x1800030f1  test    eax, eax
0x1800030f3  jle     short loc_1800030FD
0x1800030f5  movzx   eax, ax
0x1800030f8  or      eax, 80070000h
0x1800030fd  mov     ebx, eax
0x1800030ff  mov     [rsp+48h+var_18], eax
0x180003103  test    ebx, ebx
0x180003105  jns     short loc_180003138
0x180003107  lea     rax, WPP_GLOBAL_Control
0x18000310e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003115  cmp     rcx, rax
0x180003118  jz      short loc_180003138
0x18000311a  test    byte ptr [rcx+1Ch], 1
0x18000311e  jz      short loc_180003138
0x180003120  mov     edx, 29h ; ')'
0x180003125  mov     r9d, ebx
0x180003128  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x18000312f  mov     rcx, [rcx+10h]
0x180003133  call    WPP_SF_d
0x180003138  mov     ecx, 0Ch
0x18000313d  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180003142  mov     eax, ebx
0x180003144  add     rsp, 40h
0x180003148  pop     rbx
0x180003149  retn
```
