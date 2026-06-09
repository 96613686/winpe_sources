# Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetTranscriptConfiguration(void *,tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *)

- ea: `0x18000acf4`
- end: `0x18000ad3d`
- name: `?GetTranscriptConfiguration@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJPEAXPEAUtagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION@@@Z`
- size: `73`
- prototype: `CLIENT_CALL_RETURN __fastcall(Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this, void *, struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a2b0`

## callees

- `0x18000acf4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ad17`
- `RPCRT4!NdrClientCall3` at `0x18000ad17`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetTranscriptConfiguration(
        Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this,
        void *a2,
        struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, a2, a3);
}

```

## disassembly

```asm
0x18000acf4  sub     rsp, 48h
0x18000acf8  mov     [rsp+48h+arg_0], 0
0x18000ad01  mov     [rsp+48h+var_28], r8
0x18000ad06  mov     r9, rdx
0x18000ad09  xor     r8d, r8d; pReturnValue
0x18000ad0c  lea     edx, [r8+0Fh]; nProcNum
0x18000ad10  lea     rcx, pProxyInfo; pProxyInfo
0x18000ad17  call    cs:__imp_NdrClientCall3
0x18000ad1d  mov     [rsp+48h+arg_0], rax
0x18000ad22  mov     [rsp+48h+var_18], eax
0x18000ad26  jmp     short loc_18000AD38
0x18000ad28  test    eax, eax
0x18000ad2a  jle     short loc_18000AD34
0x18000ad2c  movzx   eax, ax
0x18000ad2f  or      eax, 80070000h
0x18000ad34  mov     [rsp+48h+var_18], eax
0x18000ad38  add     rsp, 48h
0x18000ad3c  retn
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
