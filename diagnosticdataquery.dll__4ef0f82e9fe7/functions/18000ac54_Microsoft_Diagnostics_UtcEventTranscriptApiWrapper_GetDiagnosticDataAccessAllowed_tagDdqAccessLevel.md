# Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticDataAccessAllowed(tagDdqAccessLevel *)

- ea: `0x18000ac54`
- end: `0x18000ac9c`
- name: `?GetDiagnosticDataAccessAllowed@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEAAJPEAW4tagDdqAccessLevel@@@Z`
- size: `72`
- prototype: `CLIENT_CALL_RETURN __fastcall(Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this, enum tagDdqAccessLevel *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009370`

## callees

- `0x18000ac54`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ac76`
- `RPCRT4!NdrClientCall3` at `0x18000ac76`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticDataAccessAllowed(
        Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this,
        enum tagDdqAccessLevel *a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, *((_QWORD *)this + 1), a2);
}

```

## disassembly

```asm
0x18000ac54  sub     rsp, 48h
0x18000ac58  mov     [rsp+48h+arg_10], 0
0x18000ac61  mov     [rsp+48h+var_28], rdx
0x18000ac66  mov     r9, [rcx+8]
0x18000ac6a  xor     r8d, r8d; pReturnValue
0x18000ac6d  xor     edx, edx; nProcNum
0x18000ac6f  lea     rcx, pProxyInfo; pProxyInfo
0x18000ac76  call    cs:__imp_NdrClientCall3
0x18000ac7c  mov     [rsp+48h+arg_10], rax
0x18000ac81  mov     [rsp+48h+var_18], eax
0x18000ac85  jmp     short loc_18000AC97
0x18000ac87  test    eax, eax
0x18000ac89  jle     short loc_18000AC93
0x18000ac8b  movzx   eax, ax
0x18000ac8e  or      eax, 80070000h
0x18000ac93  mov     [rsp+48h+var_18], eax
0x18000ac97  add     rsp, 48h
0x18000ac9b  retn
0x18000bfa8  push    rbp
0x18000bfaa  sub     rsp, 30h
0x18000bfae  mov     rbp, rdx
0x18000bfb1  mov     rcx, [rcx]
0x18000bfb4  mov     ecx, [rcx]; ExceptionCode
0x18000bfb6  call    cs:__imp_RpcExceptionFilter
0x18000bfbc  nop
0x18000bfbd  add     rsp, 30h
0x18000bfc1  pop     rbp
0x18000bfc2  retn
```
