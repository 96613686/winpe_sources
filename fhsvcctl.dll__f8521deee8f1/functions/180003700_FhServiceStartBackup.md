# FhServiceStartBackup

- ea: `0x180003700`
- end: `0x1800037e6`
- name: `FhServiceStartBackup`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180003700`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003779`
- `RPCRT4!NdrClientCall3` at `0x180003779`

## pseudocode

```c
__int64 __fastcall FhServiceStartBackup(_QWORD *a1, int a2)
{
  int Pointer; // eax
  unsigned int v4; // ebx
  int v5; // [rsp+28h] [rbp-30h]

  if ( a1 )
  {
    v5 = 3;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo,
                              2u,
                              0,
                              *a1,
                              a1[1],
                              v5,
                              a2).Pointer;
    v4 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(3);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003700  push    rbx
0x180003702  sub     rsp, 50h
0x180003706  test    rcx, rcx
0x180003709  jnz     short loc_18000374A
0x18000370b  lea     rax, WPP_GLOBAL_Control
0x180003712  mov     rcx, cs:WPP_GLOBAL_Control
0x180003719  cmp     rcx, rax
0x18000371c  jz      short loc_180003740
0x18000371e  test    byte ptr [rcx+1Ch], 1
0x180003722  jz      short loc_180003740
0x180003724  mov     edx, 14h
0x180003729  lea     r9, aPipe; "Pipe"
0x180003730  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180003737  mov     rcx, [rcx+10h]
0x18000373b  call    WPP_SF_s
0x180003740  mov     eax, 80070057h
0x180003745  jmp     loc_1800037E0
0x18000374a  mov     rax, [rcx+8]
0x18000374e  mov     [rsp+58h+arg_0], 0
0x180003757  mov     [rsp+58h+var_28], edx
0x18000375b  mov     [rsp+58h+var_30], 3
0x180003763  mov     [rsp+58h+var_38], rax
0x180003768  mov     r9, [rcx]
0x18000376b  xor     r8d, r8d; pReturnValue
0x18000376e  lea     edx, [r8+2]; nProcNum
0x180003772  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003779  call    cs:__imp_NdrClientCall3
0x18000377f  mov     rbx, rax
0x180003782  mov     [rsp+58h+arg_0], rax
0x180003787  mov     [rsp+58h+var_18], eax
0x18000378b  jmp     short loc_18000379F
0x18000378d  test    eax, eax
0x18000378f  jle     short loc_180003799
0x180003791  movzx   eax, ax
0x180003794  or      eax, 80070000h
0x180003799  mov     ebx, eax
0x18000379b  mov     [rsp+58h+var_18], eax
0x18000379f  test    ebx, ebx
0x1800037a1  jns     short loc_1800037D4
0x1800037a3  lea     rax, WPP_GLOBAL_Control
0x1800037aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037b1  cmp     rcx, rax
0x1800037b4  jz      short loc_1800037D4
0x1800037b6  test    byte ptr [rcx+1Ch], 1
0x1800037ba  jz      short loc_1800037D4
0x1800037bc  mov     edx, 15h
0x1800037c1  mov     r9d, ebx
0x1800037c4  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x1800037cb  mov     rcx, [rcx+10h]
0x1800037cf  call    WPP_SF_d
0x1800037d4  mov     ecx, 3
0x1800037d9  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x1800037de  mov     eax, ebx
0x1800037e0  add     rsp, 50h
0x1800037e4  pop     rbx
0x1800037e5  retn
```
