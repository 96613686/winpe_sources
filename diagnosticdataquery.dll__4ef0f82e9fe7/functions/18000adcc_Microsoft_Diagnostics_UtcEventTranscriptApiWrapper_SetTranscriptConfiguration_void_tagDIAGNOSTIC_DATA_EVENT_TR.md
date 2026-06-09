# Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::SetTranscriptConfiguration(void *,tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION const *)

- ea: `0x18000adcc`
- end: `0x18000ae15`
- name: `?SetTranscriptConfiguration@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJPEAXPEBUtagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION@@@Z`
- size: `73`
- prototype: `CLIENT_CALL_RETURN __fastcall(Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this, void *, const struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a4b0`

## callees

- `0x18000adcc`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000adef`
- `RPCRT4!NdrClientCall3` at `0x18000adef`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::SetTranscriptConfiguration(
        Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *this,
        void *a2,
        const struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xEu, 0, a2, a3);
}

```

## disassembly

```asm
0x18000adcc  sub     rsp, 48h
0x18000add0  mov     [rsp+48h+arg_0], 0
0x18000add9  mov     [rsp+48h+var_28], r8
0x18000adde  mov     r9, rdx
0x18000ade1  xor     r8d, r8d; pReturnValue
0x18000ade4  lea     edx, [r8+0Eh]; nProcNum
0x18000ade8  lea     rcx, pProxyInfo; pProxyInfo
0x18000adef  call    cs:__imp_NdrClientCall3
0x18000adf5  mov     [rsp+48h+arg_0], rax
0x18000adfa  mov     [rsp+48h+var_18], eax
0x18000adfe  jmp     short loc_18000AE10
0x18000ae00  test    eax, eax
0x18000ae02  jle     short loc_18000AE0C
0x18000ae04  movzx   eax, ax
0x18000ae07  or      eax, 80070000h
0x18000ae0c  mov     [rsp+48h+var_18], eax
0x18000ae10  add     rsp, 48h
0x18000ae14  retn
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
