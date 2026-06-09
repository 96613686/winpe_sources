# FhServiceClosePipe

- ea: `0x180002c40`
- end: `0x180002da2`
- name: `FhServiceClosePipe`
- size: `354`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180003230`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180002c40`
- `0x180003a00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d80`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d80`
- `RPCRT4!RpcBindingFree` at `0x180002d36`
- `RPCRT4!RpcBindingFree` at `0x180002d36`
- `RPCRT4!NdrClientCall3` at `0x180002cbc`
- `RPCRT4!NdrClientCall3` at `0x180002cbc`

## pseudocode

```c
__int64 __fastcall FhServiceClosePipe(RPC_BINDING_HANDLE *Binding)
{
  int Pointer; // eax
  unsigned int v4; // ebx
  int v5; // eax

  if ( Binding )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo,
                              1u,
                              0,
                              *Binding,
                              Binding + 1).Pointer;
    v4 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    Binding[1] = 0;
    if ( *Binding )
    {
      v5 = RpcBindingFree(Binding);
      if ( v5 )
      {
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
        v4 = v5;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
            (unsigned int)v5);
      }
      *Binding = 0;
    }
    operator delete(Binding);
    FileHistoryApiTelemetry::LogFHApiUsage(2);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002c40  mov     [rsp+arg_10], rbx
0x180002c45  mov     [rsp+arg_18], rsi
0x180002c4a  mov     [rsp+arg_0], rcx
0x180002c4f  push    rdi
0x180002c50  sub     rsp, 40h
0x180002c54  mov     rdi, rcx
0x180002c57  test    rcx, rcx
0x180002c5a  jnz     short loc_180002C99
0x180002c5c  lea     rsi, WPP_GLOBAL_Control
0x180002c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c6a  cmp     rcx, rsi
0x180002c6d  jz      short loc_180002C8F
0x180002c6f  test    byte ptr [rcx+1Ch], 1
0x180002c73  jz      short loc_180002C8F
0x180002c75  lea     edx, [rdi+11h]
0x180002c78  lea     r9, aPipe; "Pipe"
0x180002c7f  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002c86  mov     rcx, [rcx+10h]
0x180002c8a  call    WPP_SF_s
0x180002c8f  mov     eax, 80070057h
0x180002c94  jmp     loc_180002D92
0x180002c99  mov     [rsp+48h+arg_8], 0
0x180002ca2  lea     rax, [rcx+8]
0x180002ca6  mov     [rsp+48h+var_28], rax
0x180002cab  mov     r9, [rcx]
0x180002cae  xor     r8d, r8d; pReturnValue
0x180002cb1  lea     edx, [r8+1]; nProcNum
0x180002cb5  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002cbc  call    cs:__imp_NdrClientCall3
0x180002cc2  mov     rbx, rax
0x180002cc5  mov     [rsp+48h+arg_8], rax
0x180002cca  mov     [rsp+48h+var_18], eax
0x180002cce  jmp     short loc_180002CE7
0x180002cd0  test    eax, eax
0x180002cd2  jle     short loc_180002CDC
0x180002cd4  movzx   eax, ax
0x180002cd7  or      eax, 80070000h
0x180002cdc  mov     ebx, eax
0x180002cde  mov     [rsp+48h+var_18], eax
0x180002ce2  mov     rdi, [rsp+48h+arg_0]
0x180002ce7  test    ebx, ebx
0x180002ce9  jns     short loc_180002D1E
0x180002ceb  lea     rsi, WPP_GLOBAL_Control
0x180002cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cf9  cmp     rcx, rsi
0x180002cfc  jz      short loc_180002D25
0x180002cfe  test    byte ptr [rcx+1Ch], 1
0x180002d02  jz      short loc_180002D25
0x180002d04  mov     edx, 12h
0x180002d09  mov     r9d, ebx
0x180002d0c  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002d13  mov     rcx, [rcx+10h]
0x180002d17  call    WPP_SF_d
0x180002d1c  jmp     short loc_180002D25
0x180002d1e  lea     rsi, WPP_GLOBAL_Control
0x180002d25  mov     qword ptr [rdi+8], 0
0x180002d2d  cmp     qword ptr [rdi], 0
0x180002d31  jz      short loc_180002D7D
0x180002d33  mov     rcx, rdi; Binding
0x180002d36  call    cs:__imp_RpcBindingFree
0x180002d3c  test    eax, eax
0x180002d3e  jz      short loc_180002D76
0x180002d40  jle     short loc_180002D4A
0x180002d42  movzx   eax, ax
0x180002d45  or      eax, 80070000h
0x180002d4a  mov     ebx, eax
0x180002d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d53  cmp     rcx, rsi
0x180002d56  jz      short loc_180002D76
0x180002d58  test    byte ptr [rcx+1Ch], 1
0x180002d5c  jz      short loc_180002D76
0x180002d5e  mov     edx, 13h
0x180002d63  mov     r9d, eax
0x180002d66  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002d6d  mov     rcx, [rcx+10h]
0x180002d71  call    WPP_SF_d
0x180002d76  mov     qword ptr [rdi], 0
0x180002d7d  mov     rcx, rdi
0x180002d80  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d86  mov     ecx, 2
0x180002d8b  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180002d90  mov     eax, ebx
0x180002d92  mov     rbx, [rsp+48h+arg_10]
0x180002d97  mov     rsi, [rsp+48h+arg_18]
0x180002d9c  add     rsp, 40h
0x180002da0  pop     rdi
0x180002da1  retn
```
