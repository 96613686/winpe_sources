# PerflibV2EnumerateCounterSet

- ea: `0x180018a60`
- end: `0x180018b88`
- name: `PerflibV2EnumerateCounterSet`
- size: `296`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x18000e054`
- `0x180018a60`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180018b15`
- `RPCRT4!RpcRaiseException` at `0x180018b2a`
- `RPCRT4!RpcRaiseException` at `0x180018b3f`
- `RPCRT4!RpcRaiseException` at `0x180018b15`
- `RPCRT4!RpcRaiseException` at `0x180018b2a`
- `RPCRT4!RpcRaiseException` at `0x180018b3f`
- `RPCRT4!RpcImpersonateClient` at `0x180018b33`
- `RPCRT4!RpcImpersonateClient` at `0x180018b33`
- `RPCRT4!RpcRevertToSelf` at `0x180018b5d`
- `RPCRT4!RpcRevertToSelf` at `0x180018b5d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018afa`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180018afa`

## pseudocode

```c
__int64 __fastcall PerflibV2EnumerateCounterSet(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5,
        void *a6)
{
  unsigned int v7; // ebx
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE v12[36]; // [rsp+24h] [rbp-A4h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-80h]

  if ( a5 )
    *a5 = 0;
  if ( !a4 )
    return 87;
  *a4 = 0;
  if ( !a2 )
    return 87;
  if ( !a6 )
  {
    if ( !a3 )
      goto LABEL_9;
    return 87;
  }
  if ( a3 > 0xFFFFFFF )
    return 534;
  memset_0(a6, 0, 16LL * a3);
LABEL_9:
  memset_0(v12, 0, 0x74u);
  RpcCallAttributes = 3;
  v8 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
  if ( v8 != 1746 )
  {
    if ( v8 )
      RpcRaiseException(v8);
    if ( v13 < 6 )
      RpcRaiseException(5);
  }
  v9 = RpcImpersonateClient(0);
  if ( v9 )
    RpcRaiseException(v9);
  v7 = PerflibciLocalEnumerateCounterSet(a6);
  if ( !v7 )
    *a4 = *a5;
  RpcRevertToSelf();
  return v7;
}

```

## disassembly

```asm
0x180018a60  mov     [rsp+arg_0], rbx
0x180018a65  push    rbp
0x180018a66  push    rsi
0x180018a67  push    rdi
0x180018a68  sub     rsp, 0B0h
0x180018a6f  mov     rax, cs:__security_cookie
0x180018a76  xor     rax, rsp
0x180018a79  mov     [rsp+0C8h+var_28], rax
0x180018a81  mov     rdi, [rsp+0C8h+arg_20]
0x180018a89  mov     rsi, r9
0x180018a8c  mov     rbp, [rsp+0C8h+arg_28]
0x180018a94  mov     ebx, r8d
0x180018a97  test    rdi, rdi
0x180018a9a  jz      short loc_180018AA2
0x180018a9c  mov     dword ptr [rdi], 0
0x180018aa2  test    rsi, rsi
0x180018aa5  jz      short loc_180018B21
0x180018aa7  mov     dword ptr [r9], 0
0x180018aae  test    rdx, rdx
0x180018ab1  jz      short loc_180018B21
0x180018ab3  test    rbp, rbp
0x180018ab6  jz      short loc_180018B1C
0x180018ab8  cmp     ebx, 0FFFFFFFh
0x180018abe  jbe     short loc_180018ACA
0x180018ac0  mov     ebx, 216h
0x180018ac5  jmp     loc_180018B63
0x180018aca  mov     r8, rbx
0x180018acd  xor     edx, edx; Val
0x180018acf  shl     r8, 4; Size
0x180018ad3  mov     rcx, rbp; void *
0x180018ad6  call    memset_0
0x180018adb  xor     edx, edx; Val
0x180018add  lea     rcx, [rsp+0C8h+var_A4]; void *
0x180018ae2  lea     r8d, [rdx+74h]; Size
0x180018ae6  call    memset_0
0x180018aeb  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180018af0  mov     [rsp+0C8h+RpcCallAttributes], 3
0x180018af8  xor     ecx, ecx; ClientBinding
0x180018afa  call    cs:__imp_RpcServerInqCallAttributesW
0x180018b00  cmp     eax, 6D2h
0x180018b05  jz      short loc_180018B31
0x180018b07  test    eax, eax
0x180018b09  jnz     short loc_180018B28
0x180018b0b  cmp     [rsp+0C8h+var_80], 6
0x180018b10  jnb     short loc_180018B31
0x180018b12  lea     ecx, [rax+5]; exception
0x180018b15  call    cs:__imp_RpcRaiseException
0x180018b1b  int     3; Trap to Debugger
0x180018b1c  test    r8d, r8d
0x180018b1f  jz      short loc_180018ADB
0x180018b21  mov     ebx, 57h ; 'W'
0x180018b26  jmp     short loc_180018B63
0x180018b28  mov     ecx, eax; exception
0x180018b2a  call    cs:__imp_RpcRaiseException
0x180018b30  int     3; Trap to Debugger
0x180018b31  xor     ecx, ecx; BindingHandle
0x180018b33  call    cs:__imp_RpcImpersonateClient
0x180018b39  test    eax, eax
0x180018b3b  jz      short loc_180018B46
0x180018b3d  mov     ecx, eax; exception
0x180018b3f  call    cs:__imp_RpcRaiseException
0x180018b45  int     3; Trap to Debugger
0x180018b46  mov     r8, rdi
0x180018b49  mov     edx, ebx
0x180018b4b  mov     rcx, rbp; void *
0x180018b4e  call    PerflibciLocalEnumerateCounterSet
0x180018b53  mov     ebx, eax
0x180018b55  test    eax, eax
0x180018b57  jnz     short loc_180018B5D
0x180018b59  mov     ecx, [rdi]
0x180018b5b  mov     [rsi], ecx
0x180018b5d  call    cs:__imp_RpcRevertToSelf
0x180018b63  mov     eax, ebx
0x180018b65  mov     rcx, [rsp+0C8h+var_28]
0x180018b6d  xor     rcx, rsp; StackCookie
0x180018b70  call    __security_check_cookie
0x180018b75  mov     rbx, [rsp+0C8h+arg_0]
0x180018b7d  add     rsp, 0B0h
0x180018b84  pop     rdi
0x180018b85  pop     rsi
0x180018b86  pop     rbp
0x180018b87  retn
```
