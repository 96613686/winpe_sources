# FhServiceEnterMaintenanceMode

- ea: `0x180002db0`
- end: `0x180002f7f`
- name: `FhServiceEnterMaintenanceMode`
- size: `463`
- prototype: `__int64 __fastcall(_QWORD *, wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180002538`
- `0x1800025cc`
- `0x180002db0`
- `0x180003a00`
- `0x180004f20`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180002f46`
- `msvcrt!wcscpy_s` at `0x180002f46`
- `msvcrt!swprintf_s` at `0x180002edf`
- `msvcrt!swprintf_s` at `0x180002edf`
- `KERNEL32!LocalAlloc` at `0x180002ef3`
- `KERNEL32!LocalAlloc` at `0x180002ef3`
- `RPCRT4!NdrClientCall3` at `0x180002e53`
- `RPCRT4!NdrClientCall3` at `0x180002e53`

## pseudocode

```c
__int64 __fastcall FhServiceEnterMaintenanceMode(_QWORD *a1, wchar_t **a2)
{
  __int64 v4; // rax
  CLIENT_CALL_RETURN v5; // rbx
  rsize_t v6; // r14
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  _DWORD v9[2]; // [rsp+30h] [rbp-258h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+38h] [rbp-250h]
  wchar_t **v11; // [rsp+40h] [rbp-248h]
  wchar_t Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  v11 = a2;
  v9[0] = 0;
  if ( a1 )
  {
    v4 = a1[1];
    v10.Simple = 0;
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 6u, 0, *a1, v4, v9).Pointer;
    v10.Pointer = v5.Pointer;
    v9[1] = v5.Pointer;
    if ( SLODWORD(v5.Simple) >= 0 )
    {
      if ( a2 )
      {
        v6 = swprintf_s(Buffer, 0x105u, L"Global\\FhMaintenanceModeEvent-%x", v9[0]) + 1;
        v7 = (wchar_t *)LocalAlloc(0x40u, 2 * v6);
        v8 = v7;
        if ( v7 )
        {
          wcscpy_s(v7, v6, Buffer);
          *a2 = v8;
        }
        else
        {
          LODWORD(v5.Pointer) = -2147024882;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
              "outputEventName");
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
        LODWORD(v5.Pointer));
    }
    FileHistoryApiTelemetry::LogFHApiUsage(9);
    return LODWORD(v5.Pointer);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, "Pipe");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002db0  mov     [rsp+arg_10], rbx
0x180002db5  push    rsi
0x180002db6  push    rdi
0x180002db7  push    r14
0x180002db9  sub     rsp, 270h
0x180002dc0  mov     rax, cs:__security_cookie
0x180002dc7  xor     rax, rsp
0x180002dca  mov     [rsp+288h+var_28], rax
0x180002dd2  mov     rdi, rdx
0x180002dd5  mov     [rsp+288h+var_248], rdx
0x180002dda  mov     [rsp+288h+var_258], 0
0x180002de2  test    rcx, rcx
0x180002de5  jnz     short loc_180002E26
0x180002de7  lea     rax, WPP_GLOBAL_Control
0x180002dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df5  cmp     rcx, rax
0x180002df8  jz      short loc_180002E1C
0x180002dfa  test    byte ptr [rcx+1Ch], 1
0x180002dfe  jz      short loc_180002E1C
0x180002e00  mov     edx, 21h ; '!'
0x180002e05  lea     r9, aPipe; "Pipe"
0x180002e0c  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002e13  mov     rcx, [rcx+10h]
0x180002e17  call    WPP_SF_s
0x180002e1c  mov     eax, 80070057h
0x180002e21  jmp     loc_180002F5B
0x180002e26  mov     rax, [rcx+8]
0x180002e2a  mov     [rsp+288h+var_250], 0
0x180002e33  lea     rdx, [rsp+288h+var_258]
0x180002e38  mov     [rsp+288h+var_260], rdx
0x180002e3d  mov     [rsp+288h+var_268], rax
0x180002e42  mov     r9, [rcx]
0x180002e45  xor     r8d, r8d; pReturnValue
0x180002e48  lea     edx, [r8+6]; nProcNum
0x180002e4c  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002e53  call    cs:__imp_NdrClientCall3
0x180002e59  mov     rbx, rax
0x180002e5c  mov     [rsp+288h+var_250], rax
0x180002e61  mov     [rsp+288h+var_254], eax
0x180002e65  jmp     short loc_180002E7E
0x180002e67  test    eax, eax
0x180002e69  jle     short loc_180002E73
0x180002e6b  movzx   eax, ax
0x180002e6e  or      eax, 80070000h
0x180002e73  mov     ebx, eax
0x180002e75  mov     [rsp+288h+var_254], eax
0x180002e79  mov     rdi, [rsp+288h+var_248]
0x180002e7e  test    ebx, ebx
0x180002e80  jns     short loc_180002EC0
0x180002e82  lea     rax, WPP_GLOBAL_Control
0x180002e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e90  cmp     rcx, rax
0x180002e93  jz      loc_180002F4F
0x180002e99  test    byte ptr [rcx+1Ch], 1
0x180002e9d  jz      loc_180002F4F
0x180002ea3  mov     edx, 22h ; '"'
0x180002ea8  mov     r9d, ebx
0x180002eab  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002eb2  mov     rcx, [rcx+10h]
0x180002eb6  call    WPP_SF_d
0x180002ebb  jmp     loc_180002F4F
0x180002ec0  test    rdi, rdi
0x180002ec3  jz      loc_180002F4F
0x180002ec9  mov     r9d, [rsp+288h+var_258]
0x180002ece  lea     r8, aGlobalFhmainte; "Global\\FhMaintenanceModeEvent-%x"
0x180002ed5  mov     edx, 105h; BufferCount
0x180002eda  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180002edf  call    cs:__imp_swprintf_s
0x180002ee5  inc     eax
0x180002ee7  movsxd  r14, eax
0x180002eea  lea     rdx, [r14+r14]; uBytes
0x180002eee  mov     ecx, 40h ; '@'; uFlags
0x180002ef3  call    cs:__imp_LocalAlloc
0x180002ef9  mov     rsi, rax
0x180002efc  test    rax, rax
0x180002eff  jnz     short loc_180002F3B
0x180002f01  mov     ebx, 8007000Eh
0x180002f06  lea     rax, WPP_GLOBAL_Control
0x180002f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f14  cmp     rcx, rax
0x180002f17  jz      short loc_180002F4F
0x180002f19  test    byte ptr [rcx+1Ch], 1
0x180002f1d  jz      short loc_180002F4F
0x180002f1f  lea     edx, [rsi+23h]
0x180002f22  lea     r9, aOutputeventnam; "outputEventName"
0x180002f29  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x180002f30  mov     rcx, [rcx+10h]
0x180002f34  call    WPP_SF_s
0x180002f39  jmp     short loc_180002F4F
0x180002f3b  lea     r8, [rsp+288h+Buffer]; Source
0x180002f40  mov     rdx, r14; SizeInWords
0x180002f43  mov     rcx, rsi; Destination
0x180002f46  call    cs:__imp_wcscpy_s
0x180002f4c  mov     [rdi], rsi
0x180002f4f  mov     ecx, 9
0x180002f54  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x180002f59  mov     eax, ebx
0x180002f5b  mov     rcx, [rsp+288h+var_28]
0x180002f63  xor     rcx, rsp; StackCookie
0x180002f66  call    __security_check_cookie
0x180002f6b  mov     rbx, [rsp+288h+arg_10]
0x180002f73  add     rsp, 270h
0x180002f7a  pop     r14
0x180002f7c  pop     rdi
0x180002f7d  pop     rsi
0x180002f7e  retn
```
