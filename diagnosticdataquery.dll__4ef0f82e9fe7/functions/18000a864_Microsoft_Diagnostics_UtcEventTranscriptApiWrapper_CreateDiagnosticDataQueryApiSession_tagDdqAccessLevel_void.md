# Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::CreateDiagnosticDataQueryApiSession(tagDdqAccessLevel,void * *)

- ea: `0x18000a864`
- end: `0x18000a8b2`
- name: `?CreateDiagnosticDataQueryApiSession@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJW4tagDdqAccessLevel@@PEAPEAX@Z`
- size: `78`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008ed0`

## callees

- `0x18000a864`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a88c`
- `RPCRT4!NdrClientCall3` at `0x18000a88c`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::CreateDiagnosticDataQueryApiSession(
        __int64 a1,
        int a2,
        __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, *(_QWORD *)(a1 + 8), a2, a3);
}

```

## disassembly

```asm
0x18000a864  sub     rsp, 48h
0x18000a868  mov     [rsp+48h+arg_18], 0
0x18000a871  mov     [rsp+48h+var_20], r8
0x18000a876  mov     [rsp+48h+var_28], edx
0x18000a87a  mov     r9, [rcx+8]
0x18000a87e  xor     r8d, r8d; pReturnValue
0x18000a881  lea     edx, [r8+1]; nProcNum
0x18000a885  lea     rcx, pProxyInfo; pProxyInfo
0x18000a88c  call    cs:__imp_NdrClientCall3
0x18000a892  mov     [rsp+48h+arg_18], rax
0x18000a897  mov     [rsp+48h+var_18], eax
0x18000a89b  jmp     short loc_18000A8AD
0x18000a89d  test    eax, eax
0x18000a89f  jle     short loc_18000A8A9
0x18000a8a1  movzx   eax, ax
0x18000a8a4  or      eax, 80070000h
0x18000a8a9  mov     [rsp+48h+var_18], eax
0x18000a8ad  add     rsp, 48h
0x18000a8b1  retn
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
