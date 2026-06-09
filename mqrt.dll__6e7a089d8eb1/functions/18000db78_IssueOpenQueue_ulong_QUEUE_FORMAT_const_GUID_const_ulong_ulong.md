# IssueOpenQueue(ulong,QUEUE_FORMAT * const,_GUID const &,ulong,ulong)

- ea: `0x18000db78`
- end: `0x18000dc41`
- name: `?IssueOpenQueue@@YAJKQEAUQUEUE_FORMAT@@AEBU_GUID@@KK@Z`
- size: `201`
- prototype: `__int64 __fastcall(unsigned int, struct QUEUE_FORMAT *const, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc48`

## callees

- `0x1800087f8`
- `0x18000db78`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dbd2`
- `RPCRT4!NdrClientCall3` at `0x18000dbd2`
- `KERNEL32!TlsGetValue` at `0x18000db94`
- `KERNEL32!TlsGetValue` at `0x18000db94`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall IssueOpenQueue(
        int a1,
        struct QUEUE_FORMAT *const a2,
        const struct _GUID *a3,
        int a4,
        unsigned int a5)
{
  LPVOID Value; // rax
  int v11; // [rsp+20h] [rbp-68h]
  int v12; // [rsp+38h] [rbp-50h]

  Value = TlsGetValue(g_hBindIndex);
  v12 = a4;
  v11 = a1;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, Value, v11, a2, a3, v12, a5);
}

```

## disassembly

```asm
0x18000db78  push    rbx
0x18000db7a  push    rsi
0x18000db7b  push    rdi
0x18000db7c  push    r14
0x18000db7e  sub     rsp, 68h
0x18000db82  mov     ebx, r9d
0x18000db85  mov     rdi, r8
0x18000db88  mov     rsi, rdx
0x18000db8b  mov     r14d, ecx
0x18000db8e  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000db94  call    cs:__imp_TlsGetValue
0x18000db9a  mov     [rsp+88h+var_30], 0
0x18000dba3  mov     r9d, [rsp+88h+arg_20]
0x18000dbab  mov     [rsp+88h+var_48], r9d
0x18000dbb0  mov     [rsp+88h+var_50], ebx
0x18000dbb4  mov     [rsp+88h+var_58], rdi
0x18000dbb9  mov     [rsp+88h+var_60], rsi
0x18000dbbe  mov     [rsp+88h+var_68], r14d
0x18000dbc3  mov     r9, rax
0x18000dbc6  xor     r8d, r8d; pReturnValue
0x18000dbc9  xor     edx, edx; nProcNum
0x18000dbcb  lea     rcx, pProxyInfo; pProxyInfo
0x18000dbd2  call    cs:__imp_NdrClientCall3
0x18000dbd8  mov     [rsp+88h+var_30], rax
0x18000dbdd  mov     [rsp+88h+var_38], eax
0x18000dbe1  jmp     short loc_18000DC37
0x18000dbe3  mov     ebx, eax
0x18000dbe5  test    eax, eax
0x18000dbe7  jle     short loc_18000DBF2
0x18000dbe9  movzx   ebx, ax
0x18000dbec  or      ebx, 80070000h
0x18000dbf2  mov     [rsp+88h+var_38], ebx
0x18000dbf6  lea     rax, WPP_GLOBAL_Control
0x18000dbfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc04  cmp     rcx, rax
0x18000dc07  jz      short loc_18000DC27
0x18000dc09  test    byte ptr [rcx+1Ch], 1
0x18000dc0d  jz      short loc_18000DC27
0x18000dc0f  mov     edx, 0Ah
0x18000dc14  mov     r9d, ebx
0x18000dc17  lea     r8, WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids
0x18000dc1e  mov     rcx, [rcx+10h]
0x18000dc22  call    WPP_SF_d
0x18000dc27  mov     eax, 0C00E000Bh
0x18000dc2c  test    ebx, ebx
0x18000dc2e  cmovns  ebx, eax
0x18000dc31  mov     eax, ebx
0x18000dc33  mov     [rsp+88h+var_38], ebx
0x18000dc37  add     rsp, 68h
0x18000dc3b  pop     r14
0x18000dc3d  pop     rdi
0x18000dc3e  pop     rsi
0x18000dc3f  pop     rbx
0x18000dc40  retn
0x18002457c  push    rbp
0x18002457e  sub     rsp, 50h
0x180024582  mov     rbp, rdx
0x180024585  mov     rcx, [rcx]
0x180024588  mov     ecx, [rcx]; ExceptionCode
0x18002458a  call    cs:__imp_I_RpcExceptionFilter
0x180024590  nop
0x180024591  add     rsp, 50h
0x180024595  pop     rbp
0x180024596  retn
```
