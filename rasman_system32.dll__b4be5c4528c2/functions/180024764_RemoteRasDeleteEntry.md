# RemoteRasDeleteEntry

- ea: `0x180024764`
- end: `0x180024780`
- name: `RemoteRasDeleteEntry`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800238c0`

## callees

- `0x180023b40`
- `0x180024764`

## pseudocode

```c
__int64 __fastcall RemoteRasDeleteEntry(_QWORD *a1)
{
  return (unsigned int)RasRpcDeleteEntry(*a1);
}

```

## disassembly

```asm
0x180024764  sub     rsp, 38h
0x180024768  mov     rcx, [rcx]
0x18002476b  call    RasRpcDeleteEntry
0x180024770  mov     [rsp+38h+var_18], eax
0x180024774  mov     eax, [rsp+38h+var_18]
0x180024778  jmp     short $+2
0x18002477a  add     rsp, 38h
0x18002477e  retn
0x1800277f6  push    rbp
0x1800277f8  sub     rsp, 20h
0x1800277fc  mov     rbp, rdx
0x1800277ff  mov     rax, [rcx]
0x180027802  mov     ecx, [rax]
0x180027804  mov     [rbp+20h], ecx
0x180027807  mov     ecx, [rbp+20h]; ExceptionCode
0x18002780a  call    cs:__imp_I_RpcExceptionFilter
0x180027811  nop     dword ptr [rax+rax+00h]
0x180027816  nop
0x180027817  add     rsp, 20h
0x18002781b  pop     rbp
0x18002781c  retn
```
