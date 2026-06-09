# RemoteRasGetDevConfig

- ea: `0x180024788`
- end: `0x1800247ae`
- name: `RemoteRasGetDevConfig`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800190c0`

## callees

- `0x180023c60`
- `0x180024788`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180027838`
- `RPCRT4!I_RpcExceptionFilter` at `0x180027838`

## pseudocode

```c
__int64 __fastcall RemoteRasGetDevConfig(_QWORD *a1, int a2, int a3, int a4, __int64 a5)
{
  return (unsigned int)RasRpcGetDevConfig(*a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180024788  sub     rsp, 48h
0x18002478c  mov     rax, [rsp+48h+arg_20]
0x180024791  mov     [rsp+48h+var_28], rax
0x180024796  mov     rcx, [rcx]
0x180024799  call    RasRpcGetDevConfig
0x18002479e  mov     [rsp+48h+var_18], eax
0x1800247a2  mov     eax, [rsp+48h+var_18]
0x1800247a6  jmp     short $+2
0x1800247a8  add     rsp, 48h
0x1800247ac  retn
0x180027824  push    rbp
0x180027826  sub     rsp, 30h
0x18002782a  mov     rbp, rdx
0x18002782d  mov     rax, [rcx]
0x180027830  mov     ecx, [rax]
0x180027832  mov     [rbp+30h], ecx
0x180027835  mov     ecx, [rbp+30h]; ExceptionCode
0x180027838  call    cs:__imp_I_RpcExceptionFilter
0x18002783f  nop     dword ptr [rax+rax+00h]
0x180027844  nop
0x180027845  add     rsp, 30h
0x180027849  pop     rbp
0x18002784a  retn
```
