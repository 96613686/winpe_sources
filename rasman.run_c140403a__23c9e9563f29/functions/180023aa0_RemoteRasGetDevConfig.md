# RemoteRasGetDevConfig

- ea: `0x180023aa0`
- end: `0x180023ac5`
- name: `RemoteRasGetDevConfig`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800186d0`

## callees

- `0x180023060`
- `0x180023aa0`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180026842`
- `RPCRT4!I_RpcExceptionFilter` at `0x180026842`

## pseudocode

```c
__int64 __fastcall RemoteRasGetDevConfig(_QWORD *a1, int a2, int a3, int a4, __int64 a5)
{
  return (unsigned int)RasRpcGetDevConfig(*a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180023aa0  sub     rsp, 48h
0x180023aa4  mov     rax, [rsp+48h+arg_20]
0x180023aa9  mov     [rsp+48h+var_28], rax
0x180023aae  mov     rcx, [rcx]
0x180023ab1  call    RasRpcGetDevConfig
0x180023ab6  mov     [rsp+48h+var_18], eax
0x180023aba  mov     eax, [rsp+48h+var_18]
0x180023abe  jmp     short $+2
0x180023ac0  add     rsp, 48h
0x180023ac4  retn
0x18002682e  push    rbp
0x180026830  sub     rsp, 30h
0x180026834  mov     rbp, rdx
0x180026837  mov     rax, [rcx]
0x18002683a  mov     ecx, [rax]
0x18002683c  mov     [rbp+30h], ecx
0x18002683f  mov     ecx, [rbp+30h]; ExceptionCode
0x180026842  call    cs:__imp_I_RpcExceptionFilter
0x180026848  nop
0x180026849  add     rsp, 30h
0x18002684d  pop     rbp
0x18002684e  retn
```
