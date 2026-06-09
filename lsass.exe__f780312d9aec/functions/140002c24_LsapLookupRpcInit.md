# LsapLookupRpcInit

- ea: `0x140002c24`
- end: `0x140002d28`
- name: `LsapLookupRpcInit`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400031bc`

## callees

- `0x1400016c0`
- `0x140001720`
- `0x140002c24`
- `0x140002d30`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x140002c8b`
- `RPCRT4!I_RpcMapWin32Status` at `0x140002c8b`
- `RPCRT4!RpcServerRegisterIf3` at `0x140002d07`
- `RPCRT4!RpcServerRegisterIf3` at `0x140002d07`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140002c6b`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140002cbc`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140002c6b`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140002cbc`

## pseudocode

```c
int LsapLookupRpcInit()
{
  int result; // eax
  RPC_STATUS v1; // eax
  RPC_STATUS v2; // ebx
  RPC_STATUS v3; // ecx
  void *v4; // rbx
  RPC_STATUS v5; // edi
  void *SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF
  void *v7; // [rsp+58h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  v7 = 0;
  result = LsapMakePipeSD(&SecurityDescriptor);
  if ( result >= 0 )
  {
    v1 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0xAu, (RPC_WSTR)L"\\pipe\\lsass", SecurityDescriptor);
    v2 = 0;
    if ( v1 != 1740 )
      v2 = v1;
    LsapFreeLsaHeap(SecurityDescriptor);
    if ( v2 )
    {
      v3 = v2;
      return I_RpcMapWin32Status(v3);
    }
    result = LsapMakeLowBoxRpcSD(&v7);
    if ( result >= 0 )
    {
      v4 = v7;
      v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"lsapolicylookup", v7);
      if ( v5 )
      {
        LsapFreeLsaHeap(v4);
LABEL_10:
        v3 = v5;
        return I_RpcMapWin32Status(v3);
      }
      v5 = RpcServerRegisterIf3(qword_140007320, 0, 0, 49, 1234, 0x100000, LsaRpcIfCallbackFn, v4);
      LsapFreeLsaHeap(v4);
      if ( v5 )
        goto LABEL_10;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002c24  mov     rax, rsp
0x140002c27  mov     [rax+18h], rbx
0x140002c2b  push    rdi
0x140002c2c  sub     rsp, 40h
0x140002c30  lea     rcx, [rax+8]
0x140002c34  mov     qword ptr [rax+8], 0
0x140002c3c  mov     qword ptr [rax+10h], 0
0x140002c44  call    LsapMakePipeSD
0x140002c49  test    eax, eax
0x140002c4b  js      loc_140002D1D
0x140002c51  mov     r9, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x140002c56  lea     r8, Endpoint; "\\pipe\\lsass"
0x140002c5d  mov     edi, 0Ah
0x140002c62  lea     rcx, Protseq; "ncacn_np"
0x140002c69  mov     edx, edi; MaxCalls
0x140002c6b  call    cs:__imp_RpcServerUseProtseqEpW
0x140002c71  mov     rcx, [rsp+48h+SecurityDescriptor]
0x140002c76  xor     ebx, ebx
0x140002c78  cmp     eax, 6CCh
0x140002c7d  cmovnz  ebx, eax
0x140002c80  call    LsapFreeLsaHeap
0x140002c85  test    ebx, ebx
0x140002c87  jz      short loc_140002C96
0x140002c89  mov     ecx, ebx; Status
0x140002c8b  call    cs:__imp_I_RpcMapWin32Status
0x140002c91  jmp     loc_140002D1D
0x140002c96  lea     rcx, [rsp+48h+arg_8]
0x140002c9b  call    LsapMakeLowBoxRpcSD
0x140002ca0  test    eax, eax
0x140002ca2  js      short loc_140002D1D
0x140002ca4  mov     rbx, [rsp+48h+arg_8]
0x140002ca9  lea     r8, aLsapolicylooku; "lsapolicylookup"
0x140002cb0  mov     r9, rbx; SecurityDescriptor
0x140002cb3  lea     rcx, aNcalrpc; "ncalrpc"
0x140002cba  mov     edx, edi; MaxCalls
0x140002cbc  call    cs:__imp_RpcServerUseProtseqEpW
0x140002cc2  mov     edi, eax
0x140002cc4  test    eax, eax
0x140002cc6  jz      short loc_140002CD4
0x140002cc8  mov     rcx, rbx
0x140002ccb  call    LsapFreeLsaHeap
0x140002cd0  mov     ecx, edi
0x140002cd2  jmp     short loc_140002C8B
0x140002cd4  mov     [rsp+48h+var_10], rbx
0x140002cd9  lea     rax, LsaRpcIfCallbackFn
0x140002ce0  mov     [rsp+48h+var_18], rax
0x140002ce5  lea     rcx, qword_140007320
0x140002cec  mov     [rsp+48h+var_20], 100000h
0x140002cf4  mov     r9d, 31h ; '1'
0x140002cfa  xor     r8d, r8d
0x140002cfd  mov     [rsp+48h+var_28], 4D2h
0x140002d05  xor     edx, edx
0x140002d07  call    cs:__imp_RpcServerRegisterIf3
0x140002d0d  mov     rcx, rbx
0x140002d10  mov     edi, eax
0x140002d12  call    LsapFreeLsaHeap
0x140002d17  test    edi, edi
0x140002d19  jnz     short loc_140002CD0
0x140002d1b  xor     eax, eax
0x140002d1d  mov     rbx, [rsp+48h+arg_10]
0x140002d22  add     rsp, 40h
0x140002d26  pop     rdi
0x140002d27  retn
```
