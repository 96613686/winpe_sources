# FhServiceMigrationStarting

- ea: `0x180003150`
- end: `0x18000322a`
- name: `FhServiceMigrationStarting`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180003150`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800031bd`
- `RPCRT4!NdrClientCall3` at `0x1800031bd`

## pseudocode

```c
__int64 __fastcall FhServiceMigrationStarting(_QWORD *a1)
{
  int Pointer; // eax
  unsigned int v3; // ebx

  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 8u, 0, *a1, a1[1]).Pointer;
    v3 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(11);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003150  push    rbx
0x180003152  sub     rsp, 40h
0x180003156  test    rcx, rcx
0x180003159  jnz     short loc_18000319A
0x18000315b  lea     rax, WPP_GLOBAL_Control
0x180003162  mov     rcx, cs:WPP_GLOBAL_Control
0x180003169  cmp     rcx, rax
0x18000316c  jz      short loc_180003190
0x18000316e  test    byte ptr [rcx+1Ch], 1
0x180003172  jz      short loc_180003190
0x180003174  mov     edx, 26h ; '&'
0x180003179  lea     r9, aPipe; "Pipe"
0x180003180  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180003187  mov     rcx, [rcx+10h]
0x18000318b  call    WPP_SF_s
0x180003190  mov     eax, 80070057h
0x180003195  jmp     loc_180003224
0x18000319a  mov     rax, [rcx+8]
0x18000319e  mov     [rsp+48h+arg_0], 0
0x1800031a7  mov     [rsp+48h+var_28], rax
0x1800031ac  mov     r9, [rcx]
0x1800031af  xor     r8d, r8d; pReturnValue
0x1800031b2  lea     edx, [r8+8]; nProcNum
0x1800031b6  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800031bd  call    cs:__imp_NdrClientCall3
0x1800031c3  mov     rbx, rax
0x1800031c6  mov     [rsp+48h+arg_0], rax
0x1800031cb  mov     [rsp+48h+var_18], eax
0x1800031cf  jmp     short loc_1800031E3
0x1800031d1  test    eax, eax
0x1800031d3  jle     short loc_1800031DD
0x1800031d5  movzx   eax, ax
0x1800031d8  or      eax, 80070000h
0x1800031dd  mov     ebx, eax
0x1800031df  mov     [rsp+48h+var_18], eax
0x1800031e3  test    ebx, ebx
0x1800031e5  jns     short loc_180003218
0x1800031e7  lea     rax, WPP_GLOBAL_Control
0x1800031ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031f5  cmp     rcx, rax
0x1800031f8  jz      short loc_180003218
0x1800031fa  test    byte ptr [rcx+1Ch], 1
0x1800031fe  jz      short loc_180003218
0x180003200  mov     edx, 27h ; '''
0x180003205  mov     r9d, ebx
0x180003208  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x18000320f  mov     rcx, [rcx+10h]
0x180003213  call    WPP_SF_d
0x180003218  mov     ecx, 0Bh
0x18000321d  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180003222  mov     eax, ebx
0x180003224  add     rsp, 40h
0x180003228  pop     rbx
0x180003229  retn
```
