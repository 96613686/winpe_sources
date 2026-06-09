# PerflibSecurityCallbackFn

- ea: `0x180008560`
- end: `0x1800085f8`
- name: `PerflibSecurityCallbackFn`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007740`
- `0x180008042`
- `0x180008560`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800085d0`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800085d0`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000859f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000859f`

## pseudocode

```c
RPC_STATUS __fastcall PerflibSecurityCallbackFn(__int64 a1, void *a2)
{
  RPC_STATUS result; // eax
  __int64 RpcCallAttributes; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v5[32]; // [rsp+28h] [rbp-90h] BYREF
  unsigned int v6; // [rsp+48h] [rbp-70h]
  int v7; // [rsp+4Ch] [rbp-6Ch]
  int v8; // [rsp+50h] [rbp-68h]

  memset_0(v5, 0, 0x70u);
  RpcCallAttributes = 3;
  result = RpcServerInqCallAttributesW(a2, &RpcCallAttributes);
  if ( !result )
  {
    if ( !v7 || v6 < 6 || v8 )
    {
      return 5;
    }
    else
    {
      RtlRunOnceExecuteOnce(qword_18002B570, PerfpInitializeCallback, 0, 0);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008560  push    rbx
0x180008562  sub     rsp, 0B0h
0x180008569  mov     rax, cs:__security_cookie
0x180008570  xor     rax, rsp
0x180008573  mov     [rsp+0B8h+var_18], rax
0x18000857b  mov     rbx, rdx
0x18000857e  lea     rcx, [rsp+0B8h+var_90]; void *
0x180008583  xor     edx, edx; Val
0x180008585  lea     r8d, [rdx+70h]; Size
0x180008589  call    memset_0
0x18000858e  lea     rdx, [rsp+0B8h+RpcCallAttributes]; RpcCallAttributes
0x180008593  mov     [rsp+0B8h+RpcCallAttributes], 3
0x18000859c  mov     rcx, rbx; ClientBinding
0x18000859f  call    cs:__imp_RpcServerInqCallAttributesW
0x1800085a5  test    eax, eax
0x1800085a7  jnz     short loc_1800085DF
0x1800085a9  cmp     [rsp+0B8h+var_6C], eax
0x1800085ad  jz      short loc_1800085DA
0x1800085af  cmp     [rsp+0B8h+var_70], 6
0x1800085b4  jb      short loc_1800085DA
0x1800085b6  cmp     [rsp+0B8h+var_68], eax
0x1800085ba  jnz     short loc_1800085DA
0x1800085bc  xor     r9d, r9d
0x1800085bf  lea     rdx, PerfpInitializeCallback
0x1800085c6  xor     r8d, r8d
0x1800085c9  lea     rcx, qword_18002B570
0x1800085d0  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800085d6  xor     eax, eax
0x1800085d8  jmp     short loc_1800085DF
0x1800085da  mov     eax, 5
0x1800085df  mov     rcx, [rsp+0B8h+var_18]
0x1800085e7  xor     rcx, rsp; StackCookie
0x1800085ea  call    __security_check_cookie
0x1800085ef  add     rsp, 0B0h
0x1800085f6  pop     rbx
0x1800085f7  retn
```
