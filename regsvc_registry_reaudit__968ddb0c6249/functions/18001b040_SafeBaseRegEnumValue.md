# SafeBaseRegEnumValue

- ea: `0x18001b040`
- end: `0x18001b1d3`
- name: `SafeBaseRegEnumValue`
- size: `403`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001b040`
- `0x18001c734`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001b159`
- `RPCRT4!RpcRaiseException` at `0x18001b162`
- `RPCRT4!RpcRaiseException` at `0x18001b177`
- `RPCRT4!RpcRaiseException` at `0x18001b159`
- `RPCRT4!RpcRaiseException` at `0x18001b162`
- `RPCRT4!RpcRaiseException` at `0x18001b177`
- `RPCRT4!RpcImpersonateClient` at `0x18001b16b`
- `RPCRT4!RpcImpersonateClient` at `0x18001b16b`
- `RPCRT4!RpcRevertToSelf` at `0x18001b1a0`
- `RPCRT4!RpcRevertToSelf` at `0x18001b1a0`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b13e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b13e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b0fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b0fb`

## pseudocode

```c
__int64 __fastcall SafeBaseRegEnumValue(
        HKEY *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  HLOCAL v11; // rax
  unsigned int v12; // ebx
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // eax
  int RpcCallAttributes; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v17[36]; // [rsp+44h] [rbp-D4h] BYREF
  unsigned int v18; // [rsp+68h] [rbp-B0h]

  if ( !a1
    || !a3
    || !*(_QWORD *)(a3 + 8)
    || (*(_BYTE *)(a3 + 2) & 1) != 0
    || !a4
    || *(_WORD *)a4
    || *(_WORD *)(a4 + 2)
    || *(_QWORD *)(a4 + 8)
    || a6 && !a7 )
  {
    return 87;
  }
  else
  {
    v11 = LocalAlloc(0x40u, *(unsigned __int16 *)(a3 + 2));
    *(_QWORD *)(a4 + 8) = v11;
    if ( v11 )
    {
      *(_WORD *)a4 = 0;
      *(_WORD *)(a4 + 2) = *(_WORD *)(a3 + 2);
      memset_0(v17, 0, 0x74u);
      RpcCallAttributes = 3;
      v13 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
      if ( v13 != 1746 )
      {
        if ( v13 )
          RpcRaiseException(v13);
        if ( v18 < 6 )
          RpcRaiseException(5);
      }
      v14 = RpcImpersonateClient(0);
      if ( v14 )
        RpcRaiseException(v14);
      v12 = BaseRegEnumValueOld(*a1, a6, a7, a8);
      RpcRevertToSelf();
    }
    else
    {
      return 14;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18001b040  push    rbx
0x18001b042  push    rbp
0x18001b043  push    rsi
0x18001b044  push    rdi
0x18001b045  push    r12
0x18001b047  push    r13
0x18001b049  push    r14
0x18001b04b  push    r15
0x18001b04d  sub     rsp, 0D8h
0x18001b054  mov     rax, cs:__security_cookie
0x18001b05b  xor     rax, rsp
0x18001b05e  mov     [rsp+118h+var_58], rax
0x18001b066  mov     r12, [rsp+118h+arg_20]
0x18001b06e  xor     eax, eax
0x18001b070  mov     rsi, [rsp+118h+arg_28]
0x18001b078  mov     rbx, r9
0x18001b07b  mov     rbp, [rsp+118h+arg_30]
0x18001b083  mov     rdi, r8
0x18001b086  mov     r13, [rsp+118h+arg_38]
0x18001b08e  mov     r15d, edx
0x18001b091  mov     r14, rcx
0x18001b094  test    rcx, rcx
0x18001b097  jz      loc_18001B1A8
0x18001b09d  test    r8, r8
0x18001b0a0  jz      loc_18001B1A8
0x18001b0a6  cmp     [r8+8], rax
0x18001b0aa  jz      loc_18001B1A8
0x18001b0b0  test    byte ptr [r8+2], 1
0x18001b0b5  jnz     loc_18001B1A8
0x18001b0bb  test    rbx, rbx
0x18001b0be  jz      loc_18001B1A8
0x18001b0c4  cmp     [r9], ax
0x18001b0c8  jnz     loc_18001B1A8
0x18001b0ce  cmp     [r9+2], ax
0x18001b0d3  jnz     loc_18001B1A8
0x18001b0d9  cmp     [r9+8], rax
0x18001b0dd  jnz     loc_18001B1A8
0x18001b0e3  test    rsi, rsi
0x18001b0e6  jz      short loc_18001B0F1
0x18001b0e8  test    rbp, rbp
0x18001b0eb  jz      loc_18001B1A8
0x18001b0f1  movzx   edx, word ptr [r8+2]; uBytes
0x18001b0f6  mov     ecx, 40h ; '@'; uFlags
0x18001b0fb  call    cs:__imp_LocalAlloc
0x18001b101  mov     [rbx+8], rax
0x18001b105  test    rax, rax
0x18001b108  jnz     short loc_18001B112
0x18001b10a  lea     ebx, [rax+0Eh]
0x18001b10d  jmp     loc_18001B1AD
0x18001b112  xor     eax, eax
0x18001b114  lea     rcx, [rsp+118h+var_D4]; void *
0x18001b119  xor     edx, edx; Val
0x18001b11b  mov     [rbx], ax
0x18001b11e  movzx   eax, word ptr [rdi+2]
0x18001b122  mov     [rbx+2], ax
0x18001b126  lea     r8d, [rdx+74h]; Size
0x18001b12a  call    memset_0
0x18001b12f  lea     rdx, [rsp+118h+RpcCallAttributes]; RpcCallAttributes
0x18001b134  mov     [rsp+118h+RpcCallAttributes], 3
0x18001b13c  xor     ecx, ecx; ClientBinding
0x18001b13e  call    cs:__imp_RpcServerInqCallAttributesW
0x18001b144  cmp     eax, 6D2h
0x18001b149  jz      short loc_18001B169
0x18001b14b  test    eax, eax
0x18001b14d  jnz     short loc_18001B160
0x18001b14f  cmp     [rsp+118h+var_B0], 6
0x18001b154  jnb     short loc_18001B169
0x18001b156  lea     ecx, [rax+5]; exception
0x18001b159  call    cs:__imp_RpcRaiseException
0x18001b15f  int     3; Trap to Debugger
0x18001b160  mov     ecx, eax; exception
0x18001b162  call    cs:__imp_RpcRaiseException
0x18001b168  int     3; Trap to Debugger
0x18001b169  xor     ecx, ecx; BindingHandle
0x18001b16b  call    cs:__imp_RpcImpersonateClient
0x18001b171  test    eax, eax
0x18001b173  jz      short loc_18001B17E
0x18001b175  mov     ecx, eax; exception
0x18001b177  call    cs:__imp_RpcRaiseException
0x18001b17d  int     3; Trap to Debugger
0x18001b17e  mov     rcx, [r14]; HKEY
0x18001b181  mov     r9, r12
0x18001b184  mov     [rsp+118h+var_E8], r13; unsigned int *
0x18001b189  mov     r8, rbx
0x18001b18c  mov     [rsp+118h+var_F0], rbp; unsigned int *
0x18001b191  mov     edx, r15d
0x18001b194  mov     [rsp+118h+var_F8], rsi; unsigned __int8 *
0x18001b199  call    BaseRegEnumValueOld
0x18001b19e  mov     ebx, eax
0x18001b1a0  call    cs:__imp_RpcRevertToSelf
0x18001b1a6  jmp     short loc_18001B1AD
0x18001b1a8  mov     ebx, 57h ; 'W'
0x18001b1ad  mov     eax, ebx
0x18001b1af  mov     rcx, [rsp+118h+var_58]
0x18001b1b7  xor     rcx, rsp; StackCookie
0x18001b1ba  call    __security_check_cookie
0x18001b1bf  add     rsp, 0D8h
0x18001b1c6  pop     r15
0x18001b1c8  pop     r14
0x18001b1ca  pop     r13
0x18001b1cc  pop     r12
0x18001b1ce  pop     rdi
0x18001b1cf  pop     rsi
0x18001b1d0  pop     rbp
0x18001b1d1  pop     rbx
0x18001b1d2  retn
```
