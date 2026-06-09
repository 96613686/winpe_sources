# FhServiceClearProtectionState

- ea: `0x180002b50`
- end: `0x180002c33`
- name: `FhServiceClearProtectionState`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD *, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180002b50`
- `0x180003a00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002bc6`
- `RPCRT4!NdrClientCall3` at `0x180002bc6`

## pseudocode

```c
__int64 __fastcall FhServiceClearProtectionState(_QWORD *a1, int a2, int a3)
{
  int Pointer; // eax
  unsigned int v5; // ebx

  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo,
                              5u,
                              0,
                              *a1,
                              a1[1],
                              a2,
                              a3).Pointer;
    v5 = Pointer;
    if ( Pointer < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        (unsigned int)Pointer);
    }
    FileHistoryApiTelemetry::LogFHApiUsage(8);
    return v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002b50  push    rbx
0x180002b52  sub     rsp, 50h
0x180002b56  test    rcx, rcx
0x180002b59  jnz     short loc_180002B9A
0x180002b5b  lea     rax, WPP_GLOBAL_Control
0x180002b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b69  cmp     rcx, rax
0x180002b6c  jz      short loc_180002B90
0x180002b6e  test    byte ptr [rcx+1Ch], 1
0x180002b72  jz      short loc_180002B90
0x180002b74  mov     edx, 1Fh
0x180002b79  lea     r9, aPipe; "Pipe"
0x180002b80  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002b87  mov     rcx, [rcx+10h]
0x180002b8b  call    WPP_SF_s
0x180002b90  mov     eax, 80070057h
0x180002b95  jmp     loc_180002C2D
0x180002b9a  mov     rax, [rcx+8]
0x180002b9e  mov     [rsp+58h+arg_0], 0
0x180002ba7  mov     [rsp+58h+var_28], r8d
0x180002bac  mov     [rsp+58h+var_30], edx
0x180002bb0  mov     [rsp+58h+var_38], rax
0x180002bb5  mov     r9, [rcx]
0x180002bb8  xor     r8d, r8d; pReturnValue
0x180002bbb  lea     edx, [r8+5]; nProcNum
0x180002bbf  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002bc6  call    cs:__imp_NdrClientCall3
0x180002bcc  mov     rbx, rax
0x180002bcf  mov     [rsp+58h+arg_0], rax
0x180002bd4  mov     [rsp+58h+var_18], eax
0x180002bd8  jmp     short loc_180002BEC
0x180002bda  test    eax, eax
0x180002bdc  jle     short loc_180002BE6
0x180002bde  movzx   eax, ax
0x180002be1  or      eax, 80070000h
0x180002be6  mov     ebx, eax
0x180002be8  mov     [rsp+58h+var_18], eax
0x180002bec  test    ebx, ebx
0x180002bee  jns     short loc_180002C21
0x180002bf0  lea     rax, WPP_GLOBAL_Control
0x180002bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bfe  cmp     rcx, rax
0x180002c01  jz      short loc_180002C21
0x180002c03  test    byte ptr [rcx+1Ch], 1
0x180002c07  jz      short loc_180002C21
0x180002c09  mov     edx, 20h ; ' '
0x180002c0e  mov     r9d, ebx
0x180002c11  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002c18  mov     rcx, [rcx+10h]
0x180002c1c  call    WPP_SF_d
0x180002c21  mov     ecx, 8
0x180002c26  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180002c2b  mov     eax, ebx
0x180002c2d  add     rsp, 50h
0x180002c31  pop     rbx
0x180002c32  retn
```
