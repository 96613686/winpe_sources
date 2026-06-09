# BaseRegDeleteKeyEx

- ea: `0x1800195b0`
- end: `0x180019684`
- name: `BaseRegDeleteKeyEx`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800195b0`
- `0x18001c648`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180019621`
- `RPCRT4!RpcRaiseException` at `0x18001962a`
- `RPCRT4!RpcRaiseException` at `0x18001963f`
- `RPCRT4!RpcRaiseException` at `0x180019621`
- `RPCRT4!RpcRaiseException` at `0x18001962a`
- `RPCRT4!RpcRaiseException` at `0x18001963f`
- `RPCRT4!RpcImpersonateClient` at `0x180019633`
- `RPCRT4!RpcImpersonateClient` at `0x180019633`
- `RPCRT4!RpcRevertToSelf` at `0x180019659`
- `RPCRT4!RpcRevertToSelf` at `0x180019659`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019606`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019606`

## pseudocode

```c
__int64 __fastcall BaseRegDeleteKeyEx(_QWORD *a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v8; // ebx
  RPC_STATUS v9; // eax
  RPC_STATUS v10; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v13[36]; // [rsp+34h] [rbp-A4h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-80h]

  if ( a1 )
  {
    memset_0(v13, 0, 0x74u);
    RpcCallAttributes = 3;
    v9 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v9 != 1746 )
    {
      if ( v9 )
        RpcRaiseException(v9);
      if ( v14 < 6 )
        RpcRaiseException(5);
    }
    v10 = RpcImpersonateClient(0);
    if ( v10 )
      RpcRaiseException(v10);
    v8 = BaseRegDeleteKeyExInternal(*a1, a2, a3, a4);
    RpcRevertToSelf();
  }
  else
  {
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x1800195b0  mov     [rsp+arg_18], rbx
0x1800195b5  push    rbp
0x1800195b6  push    rsi
0x1800195b7  push    rdi
0x1800195b8  sub     rsp, 0C0h
0x1800195bf  mov     rax, cs:__security_cookie
0x1800195c6  xor     rax, rsp
0x1800195c9  mov     [rsp+0D8h+var_28], rax
0x1800195d1  mov     edi, r9d
0x1800195d4  mov     ebp, r8d
0x1800195d7  mov     rsi, rdx
0x1800195da  mov     rbx, rcx
0x1800195dd  test    rcx, rcx
0x1800195e0  jnz     short loc_1800195E7
0x1800195e2  lea     ebx, [rcx+57h]
0x1800195e5  jmp     short loc_18001965F
0x1800195e7  xor     edx, edx; Val
0x1800195e9  lea     rcx, [rsp+0D8h+var_A4]; void *
0x1800195ee  lea     r8d, [rdx+74h]; Size
0x1800195f2  call    memset_0
0x1800195f7  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x1800195fc  mov     [rsp+0D8h+RpcCallAttributes], 3
0x180019604  xor     ecx, ecx; ClientBinding
0x180019606  call    cs:__imp_RpcServerInqCallAttributesW
0x18001960c  cmp     eax, 6D2h
0x180019611  jz      short loc_180019631
0x180019613  test    eax, eax
0x180019615  jnz     short loc_180019628
0x180019617  cmp     [rsp+0D8h+var_80], 6
0x18001961c  jnb     short loc_180019631
0x18001961e  lea     ecx, [rax+5]; exception
0x180019621  call    cs:__imp_RpcRaiseException
0x180019627  int     3; Trap to Debugger
0x180019628  mov     ecx, eax; exception
0x18001962a  call    cs:__imp_RpcRaiseException
0x180019630  int     3; Trap to Debugger
0x180019631  xor     ecx, ecx; BindingHandle
0x180019633  call    cs:__imp_RpcImpersonateClient
0x180019639  test    eax, eax
0x18001963b  jz      short loc_180019646
0x18001963d  mov     ecx, eax; exception
0x18001963f  call    cs:__imp_RpcRaiseException
0x180019645  int     3; Trap to Debugger
0x180019646  mov     rcx, [rbx]
0x180019649  mov     r9d, edi
0x18001964c  mov     r8d, ebp
0x18001964f  mov     rdx, rsi
0x180019652  call    BaseRegDeleteKeyExInternal
0x180019657  mov     ebx, eax
0x180019659  call    cs:__imp_RpcRevertToSelf
0x18001965f  mov     eax, ebx
0x180019661  mov     rcx, [rsp+0D8h+var_28]
0x180019669  xor     rcx, rsp; StackCookie
0x18001966c  call    __security_check_cookie
0x180019671  mov     rbx, [rsp+0D8h+arg_18]
0x180019679  add     rsp, 0C0h
0x180019680  pop     rdi
0x180019681  pop     rsi
0x180019682  pop     rbp
0x180019683  retn
```
