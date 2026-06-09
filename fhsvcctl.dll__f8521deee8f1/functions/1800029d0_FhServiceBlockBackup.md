# FhServiceBlockBackup

- ea: `0x1800029d0`
- end: `0x180002b42`
- name: `FhServiceBlockBackup`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x1800029d0`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002a4f`
- `RPCRT4!NdrClientCall3` at `0x180002ad1`
- `RPCRT4!NdrClientCall3` at `0x180002a4f`
- `RPCRT4!NdrClientCall3` at `0x180002ad1`

## pseudocode

```c
__int64 __fastcall FhServiceBlockBackup(_QWORD *a1)
{
  int Pointer; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  CLIENT_CALL_RETURN v6; // [rsp+28h] [rbp-20h]

  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 4u, 0, *a1, a1[1], 1).Pointer;
    if ( Pointer >= 0 )
    {
      LODWORD(v6.Pointer) = 0;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo,
                                3u,
                                0,
                                *a1,
                                a1[1],
                                v6.Simple,
                                Pointer).Pointer;
      if ( Pointer >= 0 )
        goto LABEL_15;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v5 = 28;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v5 = 27;
    }
    WPP_SF_d(v4[2], v5, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, (unsigned int)Pointer);
LABEL_15:
    FileHistoryApiTelemetry::LogFHApiUsage(6);
    return (unsigned int)Pointer;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp+arg_10], rbx
0x1800029d5  mov     [rsp+arg_0], rcx
0x1800029da  push    rdi
0x1800029db  sub     rsp, 40h
0x1800029df  mov     rdi, rcx
0x1800029e2  test    rcx, rcx
0x1800029e5  jnz     short loc_180002A24
0x1800029e7  lea     rax, WPP_GLOBAL_Control
0x1800029ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029f5  cmp     rcx, rax
0x1800029f8  jz      short loc_180002A1A
0x1800029fa  test    byte ptr [rcx+1Ch], 1
0x1800029fe  jz      short loc_180002A1A
0x180002a00  lea     edx, [rdi+1Ah]
0x180002a03  lea     r9, aPipe; "Pipe"
0x180002a0a  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002a11  mov     rcx, [rcx+10h]
0x180002a15  call    WPP_SF_s
0x180002a1a  mov     eax, 80070057h
0x180002a1f  jmp     loc_180002B37
0x180002a24  mov     rax, [rcx+8]
0x180002a28  mov     [rsp+48h+arg_8], 0
0x180002a31  mov     dword ptr [rsp+48h+var_20], 1
0x180002a39  mov     [rsp+48h+var_28], rax
0x180002a3e  mov     r9, [rcx]
0x180002a41  xor     r8d, r8d; pReturnValue
0x180002a44  lea     edx, [r8+4]; nProcNum
0x180002a48  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002a4f  call    cs:__imp_NdrClientCall3
0x180002a55  mov     rbx, rax
0x180002a58  mov     [rsp+48h+arg_8], rax
0x180002a5d  mov     [rsp+48h+var_18], eax
0x180002a61  jmp     short loc_180002A7A
0x180002a63  test    eax, eax
0x180002a65  jle     short loc_180002A6F
0x180002a67  movzx   eax, ax
0x180002a6a  or      eax, 80070000h
0x180002a6f  mov     ebx, eax
0x180002a71  mov     [rsp+48h+var_18], eax
0x180002a75  mov     rdi, [rsp+48h+arg_0]
0x180002a7a  test    ebx, ebx
0x180002a7c  jns     short loc_180002AA6
0x180002a7e  lea     rax, WPP_GLOBAL_Control
0x180002a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a8c  cmp     rcx, rax
0x180002a8f  jz      loc_180002B2B
0x180002a95  test    byte ptr [rcx+1Ch], 1
0x180002a99  jz      loc_180002B2B
0x180002a9f  mov     edx, 1Bh
0x180002aa4  jmp     short loc_180002B18
0x180002aa6  mov     rax, [rdi+8]
0x180002aaa  mov     [rsp+48h+arg_0], 0
0x180002ab3  mov     dword ptr [rsp+48h+var_20], 0
0x180002abb  mov     [rsp+48h+var_28], rax
0x180002ac0  mov     r9, [rdi]
0x180002ac3  xor     r8d, r8d; pReturnValue
0x180002ac6  lea     edx, [r8+3]; nProcNum
0x180002aca  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002ad1  call    cs:__imp_NdrClientCall3
0x180002ad7  mov     [rsp+48h+arg_0], rax
0x180002adc  mov     ebx, eax
0x180002ade  mov     [rsp+48h+var_18], eax
0x180002ae2  jmp     short loc_180002AF6
0x180002ae4  test    eax, eax
0x180002ae6  jle     short loc_180002AF0
0x180002ae8  movzx   eax, ax
0x180002aeb  or      eax, 80070000h
0x180002af0  mov     ebx, eax
0x180002af2  mov     [rsp+48h+var_18], eax
0x180002af6  test    ebx, ebx
0x180002af8  jns     short loc_180002B2B
0x180002afa  lea     rax, WPP_GLOBAL_Control
0x180002b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b08  cmp     rcx, rax
0x180002b0b  jz      short loc_180002B2B
0x180002b0d  test    byte ptr [rcx+1Ch], 1
0x180002b11  jz      short loc_180002B2B
0x180002b13  mov     edx, 1Ch
0x180002b18  mov     r9d, ebx
0x180002b1b  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002b22  mov     rcx, [rcx+10h]
0x180002b26  call    WPP_SF_d
0x180002b2b  mov     ecx, 6
0x180002b30  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180002b35  mov     eax, ebx
0x180002b37  mov     rbx, [rsp+48h+arg_10]
0x180002b3c  add     rsp, 40h
0x180002b40  pop     rdi
0x180002b41  retn
```
