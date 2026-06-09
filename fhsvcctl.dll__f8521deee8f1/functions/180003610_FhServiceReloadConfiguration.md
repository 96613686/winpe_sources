# FhServiceReloadConfiguration

- ea: `0x180003610`
- end: `0x1800036fa`
- name: `FhServiceReloadConfiguration`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180003610`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000368d`
- `RPCRT4!NdrClientCall3` at `0x18000368d`

## pseudocode

```c
__int64 __fastcall FhServiceReloadConfiguration(_QWORD *a1)
{
  int Pointer; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+30h] [rbp-28h]

  if ( a1 )
  {
    v5 = 1;
    v4 = 1;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo,
                              2u,
                              0,
                              *a1,
                              a1[1],
                              v4,
                              v5).Pointer;
    v3 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(5);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003610  push    rbx
0x180003612  sub     rsp, 50h
0x180003616  test    rcx, rcx
0x180003619  jnz     short loc_18000365A
0x18000361b  lea     rax, WPP_GLOBAL_Control
0x180003622  mov     rcx, cs:WPP_GLOBAL_Control
0x180003629  cmp     rcx, rax
0x18000362c  jz      short loc_180003650
0x18000362e  test    byte ptr [rcx+1Ch], 1
0x180003632  jz      short loc_180003650
0x180003634  mov     edx, 18h
0x180003639  lea     r9, aPipe; "Pipe"
0x180003640  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180003647  mov     rcx, [rcx+10h]
0x18000364b  call    WPP_SF_s
0x180003650  mov     eax, 80070057h
0x180003655  jmp     loc_1800036F4
0x18000365a  mov     rax, [rcx+8]
0x18000365e  mov     [rsp+58h+arg_0], 0
0x180003667  mov     [rsp+58h+var_28], 1
0x18000366f  mov     [rsp+58h+var_30], 1
0x180003677  mov     [rsp+58h+var_38], rax
0x18000367c  mov     r9, [rcx]
0x18000367f  xor     r8d, r8d; pReturnValue
0x180003682  lea     edx, [r8+2]; nProcNum
0x180003686  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000368d  call    cs:__imp_NdrClientCall3
0x180003693  mov     rbx, rax
0x180003696  mov     [rsp+58h+arg_0], rax
0x18000369b  mov     [rsp+58h+var_18], eax
0x18000369f  jmp     short loc_1800036B3
0x1800036a1  test    eax, eax
0x1800036a3  jle     short loc_1800036AD
0x1800036a5  movzx   eax, ax
0x1800036a8  or      eax, 80070000h
0x1800036ad  mov     ebx, eax
0x1800036af  mov     [rsp+58h+var_18], eax
0x1800036b3  test    ebx, ebx
0x1800036b5  jns     short loc_1800036E8
0x1800036b7  lea     rax, WPP_GLOBAL_Control
0x1800036be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036c5  cmp     rcx, rax
0x1800036c8  jz      short loc_1800036E8
0x1800036ca  test    byte ptr [rcx+1Ch], 1
0x1800036ce  jz      short loc_1800036E8
0x1800036d0  mov     edx, 19h
0x1800036d5  mov     r9d, ebx
0x1800036d8  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x1800036df  mov     rcx, [rcx+10h]
0x1800036e3  call    WPP_SF_d
0x1800036e8  mov     ecx, 5
0x1800036ed  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x1800036f2  mov     eax, ebx
0x1800036f4  add     rsp, 50h
0x1800036f8  pop     rbx
0x1800036f9  retn
```
