# FhServiceStopBackup

- ea: `0x1800037f0`
- end: `0x1800038ce`
- name: `FhServiceStopBackup`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x1800037f0`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003861`
- `RPCRT4!NdrClientCall3` at `0x180003861`

## pseudocode

```c
__int64 __fastcall FhServiceStopBackup(_QWORD *a1, int a2)
{
  int Pointer; // eax
  unsigned int v4; // ebx

  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 3u, 0, *a1, a1[1], a2).Pointer;
    v4 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(4);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800037f0  push    rbx
0x1800037f2  sub     rsp, 40h
0x1800037f6  test    rcx, rcx
0x1800037f9  jnz     short loc_18000383A
0x1800037fb  lea     rax, WPP_GLOBAL_Control
0x180003802  mov     rcx, cs:WPP_GLOBAL_Control
0x180003809  cmp     rcx, rax
0x18000380c  jz      short loc_180003830
0x18000380e  test    byte ptr [rcx+1Ch], 1
0x180003812  jz      short loc_180003830
0x180003814  mov     edx, 16h
0x180003819  lea     r9, aPipe; "Pipe"
0x180003820  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180003827  mov     rcx, [rcx+10h]
0x18000382b  call    WPP_SF_s
0x180003830  mov     eax, 80070057h
0x180003835  jmp     loc_1800038C8
0x18000383a  mov     rax, [rcx+8]
0x18000383e  mov     [rsp+48h+arg_0], 0
0x180003847  mov     [rsp+48h+var_20], edx
0x18000384b  mov     [rsp+48h+var_28], rax
0x180003850  mov     r9, [rcx]
0x180003853  xor     r8d, r8d; pReturnValue
0x180003856  lea     edx, [r8+3]; nProcNum
0x18000385a  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003861  call    cs:__imp_NdrClientCall3
0x180003867  mov     rbx, rax
0x18000386a  mov     [rsp+48h+arg_0], rax
0x18000386f  mov     [rsp+48h+var_18], eax
0x180003873  jmp     short loc_180003887
0x180003875  test    eax, eax
0x180003877  jle     short loc_180003881
0x180003879  movzx   eax, ax
0x18000387c  or      eax, 80070000h
0x180003881  mov     ebx, eax
0x180003883  mov     [rsp+48h+var_18], eax
0x180003887  test    ebx, ebx
0x180003889  jns     short loc_1800038BC
0x18000388b  lea     rax, WPP_GLOBAL_Control
0x180003892  mov     rcx, cs:WPP_GLOBAL_Control
0x180003899  cmp     rcx, rax
0x18000389c  jz      short loc_1800038BC
0x18000389e  test    byte ptr [rcx+1Ch], 1
0x1800038a2  jz      short loc_1800038BC
0x1800038a4  mov     edx, 17h
0x1800038a9  mov     r9d, ebx
0x1800038ac  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x1800038b3  mov     rcx, [rcx+10h]
0x1800038b7  call    WPP_SF_d
0x1800038bc  mov     ecx, 4
0x1800038c1  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x1800038c6  mov     eax, ebx
0x1800038c8  add     rsp, 40h
0x1800038cc  pop     rbx
0x1800038cd  retn
```
