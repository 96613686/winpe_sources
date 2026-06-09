# SafeBaseRegGetKeySecurity

- ea: `0x18001b1e0`
- end: `0x18001b314`
- name: `SafeBaseRegGetKeySecurity`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001b1e0`
- `0x18001ca9c`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001b2b5`
- `RPCRT4!RpcRaiseException` at `0x18001b2be`
- `RPCRT4!RpcRaiseException` at `0x18001b2d3`
- `RPCRT4!RpcRaiseException` at `0x18001b2b5`
- `RPCRT4!RpcRaiseException` at `0x18001b2be`
- `RPCRT4!RpcRaiseException` at `0x18001b2d3`
- `RPCRT4!RpcImpersonateClient` at `0x18001b2c7`
- `RPCRT4!RpcImpersonateClient` at `0x18001b2c7`
- `RPCRT4!RpcRevertToSelf` at `0x18001b2e9`
- `RPCRT4!RpcRevertToSelf` at `0x18001b2e9`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b29a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b29a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b258`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b258`

## pseudocode

```c
__int64 __fastcall SafeBaseRegGetKeySecurity(HANDLE *a1, SECURITY_INFORMATION a2, __int64 a3, __int64 a4)
{
  HLOCAL v8; // rax
  ULONG KeySecurityOldInternal; // ebx
  RPC_STATUS v10; // eax
  RPC_STATUS v11; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v14[36]; // [rsp+24h] [rbp-B4h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-90h]

  if ( !a1 || !a3 || *(_DWORD *)(a3 + 12) || !a4 || *(_DWORD *)(a4 + 8) || *(_DWORD *)(a4 + 12) || *(_QWORD *)a4 )
  {
    return 87;
  }
  else
  {
    v8 = LocalAlloc(0x40u, *(unsigned int *)(a3 + 8));
    *(_QWORD *)a4 = v8;
    if ( v8 )
    {
      *(_QWORD *)(a4 + 8) = *(unsigned int *)(a3 + 8);
      memset_0(v14, 0, 0x74u);
      RpcCallAttributes = 3;
      v10 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
      if ( v10 != 1746 )
      {
        if ( v10 )
          RpcRaiseException(v10);
        if ( v15 < 6 )
          RpcRaiseException(5);
      }
      v11 = RpcImpersonateClient(0);
      if ( v11 )
        RpcRaiseException(v11);
      KeySecurityOldInternal = BaseRegGetKeySecurityOldInternal(*a1, a2, a4);
      RpcRevertToSelf();
    }
    else
    {
      return 14;
    }
  }
  return KeySecurityOldInternal;
}

```

## disassembly

```asm
0x18001b1e0  push    rbx
0x18001b1e2  push    rbp
0x18001b1e3  push    rsi
0x18001b1e4  push    rdi
0x18001b1e5  sub     rsp, 0B8h
0x18001b1ec  mov     rax, cs:__security_cookie
0x18001b1f3  xor     rax, rsp
0x18001b1f6  mov     [rsp+0D8h+var_38], rax
0x18001b1fe  mov     rbx, r9
0x18001b201  mov     rdi, r8
0x18001b204  mov     ebp, edx
0x18001b206  mov     rsi, rcx
0x18001b209  test    rcx, rcx
0x18001b20c  jz      loc_18001B2F1
0x18001b212  test    r8, r8
0x18001b215  jz      loc_18001B2F1
0x18001b21b  cmp     dword ptr [r8+0Ch], 0
0x18001b220  jnz     loc_18001B2F1
0x18001b226  test    rbx, rbx
0x18001b229  jz      loc_18001B2F1
0x18001b22f  cmp     dword ptr [r9+8], 0
0x18001b234  jnz     loc_18001B2F1
0x18001b23a  cmp     dword ptr [r9+0Ch], 0
0x18001b23f  jnz     loc_18001B2F1
0x18001b245  cmp     qword ptr [r9], 0
0x18001b249  jnz     loc_18001B2F1
0x18001b24f  mov     edx, [r8+8]; uBytes
0x18001b253  mov     ecx, 40h ; '@'; uFlags
0x18001b258  call    cs:__imp_LocalAlloc
0x18001b25e  mov     [rbx], rax
0x18001b261  test    rax, rax
0x18001b264  jnz     short loc_18001B26E
0x18001b266  lea     ebx, [rax+0Eh]
0x18001b269  jmp     loc_18001B2F6
0x18001b26e  mov     eax, [rdi+8]
0x18001b271  lea     rcx, [rsp+0D8h+var_B4]; void *
0x18001b276  xor     edx, edx; Val
0x18001b278  mov     [rbx+8], eax
0x18001b27b  mov     dword ptr [rbx+0Ch], 0
0x18001b282  lea     r8d, [rdx+74h]; Size
0x18001b286  call    memset_0
0x18001b28b  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x18001b290  mov     [rsp+0D8h+RpcCallAttributes], 3
0x18001b298  xor     ecx, ecx; ClientBinding
0x18001b29a  call    cs:__imp_RpcServerInqCallAttributesW
0x18001b2a0  cmp     eax, 6D2h
0x18001b2a5  jz      short loc_18001B2C5
0x18001b2a7  test    eax, eax
0x18001b2a9  jnz     short loc_18001B2BC
0x18001b2ab  cmp     [rsp+0D8h+var_90], 6
0x18001b2b0  jnb     short loc_18001B2C5
0x18001b2b2  lea     ecx, [rax+5]; exception
0x18001b2b5  call    cs:__imp_RpcRaiseException
0x18001b2bb  int     3; Trap to Debugger
0x18001b2bc  mov     ecx, eax; exception
0x18001b2be  call    cs:__imp_RpcRaiseException
0x18001b2c4  int     3; Trap to Debugger
0x18001b2c5  xor     ecx, ecx; BindingHandle
0x18001b2c7  call    cs:__imp_RpcImpersonateClient
0x18001b2cd  test    eax, eax
0x18001b2cf  jz      short loc_18001B2DA
0x18001b2d1  mov     ecx, eax; exception
0x18001b2d3  call    cs:__imp_RpcRaiseException
0x18001b2d9  int     3; Trap to Debugger
0x18001b2da  mov     rcx, [rsi]; Handle
0x18001b2dd  mov     r8, rbx
0x18001b2e0  mov     edx, ebp; SecurityInformation
0x18001b2e2  call    BaseRegGetKeySecurityOldInternal
0x18001b2e7  mov     ebx, eax
0x18001b2e9  call    cs:__imp_RpcRevertToSelf
0x18001b2ef  jmp     short loc_18001B2F6
0x18001b2f1  mov     ebx, 57h ; 'W'
0x18001b2f6  mov     eax, ebx
0x18001b2f8  mov     rcx, [rsp+0D8h+var_38]
0x18001b300  xor     rcx, rsp; StackCookie
0x18001b303  call    __security_check_cookie
0x18001b308  add     rsp, 0B8h
0x18001b30f  pop     rdi
0x18001b310  pop     rsi
0x18001b311  pop     rbp
0x18001b312  pop     rbx
0x18001b313  retn
```
