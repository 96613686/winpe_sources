# Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticSessionAccessLevel(void *,tagDdqAccessLevel *)

- ea: `0x18000aca4`
- end: `0x18000aced`
- name: `?GetDiagnosticSessionAccessLevel@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEAAJPEAXPEAW4tagDdqAccessLevel@@@Z`
- size: `73`
- prototype: `CLIENT_CALL_RETURN __fastcall(Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this, void *, enum tagDdqAccessLevel *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a1d0`

## callees

- `0x18000aca4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000acc7`
- `RPCRT4!NdrClientCall3` at `0x18000acc7`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticSessionAccessLevel(
        Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this,
        void *a2,
        enum tagDdqAccessLevel *a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x10u, 0, a2, a3);
}

```

## disassembly

```asm
0x18000aca4  sub     rsp, 48h
0x18000aca8  mov     [rsp+48h+arg_0], 0
0x18000acb1  mov     [rsp+48h+var_28], r8
0x18000acb6  mov     r9, rdx
0x18000acb9  xor     r8d, r8d; pReturnValue
0x18000acbc  lea     edx, [r8+10h]; nProcNum
0x18000acc0  lea     rcx, pProxyInfo; pProxyInfo
0x18000acc7  call    cs:__imp_NdrClientCall3
0x18000accd  mov     [rsp+48h+arg_0], rax
0x18000acd2  mov     [rsp+48h+var_18], eax
0x18000acd6  jmp     short loc_18000ACE8
0x18000acd8  test    eax, eax
0x18000acda  jle     short loc_18000ACE4
0x18000acdc  movzx   eax, ax
0x18000acdf  or      eax, 80070000h
0x18000ace4  mov     [rsp+48h+var_18], eax
0x18000ace8  add     rsp, 48h
0x18000acec  retn
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
