# PerflibV2EnumerateCounterSetInstances

- ea: `0x180005c60`
- end: `0x180005d8c`
- name: `PerflibV2EnumerateCounterSetInstances`
- size: `300`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int128 *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180002810`
- `0x180005c60`
- `0x180007740`
- `0x180008042`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180005d18`
- `RPCRT4!RpcRaiseException` at `0x180005d21`
- `RPCRT4!RpcRaiseException` at `0x180005d36`
- `RPCRT4!RpcRaiseException` at `0x180005d18`
- `RPCRT4!RpcRaiseException` at `0x180005d21`
- `RPCRT4!RpcRaiseException` at `0x180005d36`
- `RPCRT4!RpcImpersonateClient` at `0x180005d2a`
- `RPCRT4!RpcImpersonateClient` at `0x180005d2a`
- `RPCRT4!RpcRevertToSelf` at `0x180005d5d`
- `RPCRT4!RpcRevertToSelf` at `0x180005d5d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180005cfb`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180005cfb`

## pseudocode

```c
__int64 __fastcall PerflibV2EnumerateCounterSetInstances(
        __int64 a1,
        unsigned __int16 *a2,
        __int128 *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int8 *a7)
{
  DWORD v10; // ebx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v15[36]; // [rsp+34h] [rbp-B4h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-90h]

  if ( a6 )
    *a6 = 0;
  if ( !a5 )
    return 87;
  *a5 = 0;
  if ( a4 )
  {
    if ( !a7 )
      return 87;
    a7[a4 - 1] = 0;
    *a7 = 0;
  }
  memset_0(v15, 0, 0x74u);
  RpcCallAttributes = 3;
  v11 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
  if ( v11 != 1746 )
  {
    if ( v11 )
      RpcRaiseException(v11);
    if ( v16 < 6 )
      RpcRaiseException(5);
  }
  v12 = RpcImpersonateClient(0);
  if ( v12 )
    RpcRaiseException(v12);
  v10 = PerflibciLocalEnumerateCounterSetInstances(a2, a3, a7, a4, a6);
  if ( !v10 )
    *a5 = *a6;
  RpcRevertToSelf();
  return v10;
}

```

## disassembly

```asm
0x180005c60  mov     [rsp+arg_0], rbx
0x180005c65  push    rbp
0x180005c66  push    rsi
0x180005c67  push    rdi
0x180005c68  push    r14
0x180005c6a  push    r15
0x180005c6c  sub     rsp, 0C0h
0x180005c73  mov     rax, cs:__security_cookie
0x180005c7a  xor     rax, rsp
0x180005c7d  mov     [rsp+0E8h+var_38], rax
0x180005c85  mov     rsi, [rsp+0E8h+arg_28]
0x180005c8d  mov     ebp, r9d
0x180005c90  mov     rdi, [rsp+0E8h+arg_20]
0x180005c98  mov     r15, r8
0x180005c9b  mov     rbx, [rsp+0E8h+arg_30]
0x180005ca3  mov     r14, rdx
0x180005ca6  test    rsi, rsi
0x180005ca9  jz      short loc_180005CB1
0x180005cab  mov     dword ptr [rsi], 0
0x180005cb1  test    rdi, rdi
0x180005cb4  jnz     short loc_180005CC0
0x180005cb6  mov     ebx, 57h ; 'W'
0x180005cbb  jmp     loc_180005D63
0x180005cc0  mov     dword ptr [rdi], 0
0x180005cc6  test    ebp, ebp
0x180005cc8  jz      short loc_180005CDA
0x180005cca  test    rbx, rbx
0x180005ccd  jz      short loc_180005CB6
0x180005ccf  lea     eax, [r9-1]
0x180005cd3  mov     byte ptr [rax+rbx], 0
0x180005cd7  mov     byte ptr [rbx], 0
0x180005cda  xor     edx, edx; Val
0x180005cdc  lea     rcx, [rsp+0E8h+var_B4]; void *
0x180005ce1  mov     r8d, 74h ; 't'; Size
0x180005ce7  call    memset_0
0x180005cec  lea     rdx, [rsp+0E8h+RpcCallAttributes]; RpcCallAttributes
0x180005cf1  mov     [rsp+0E8h+RpcCallAttributes], 3
0x180005cf9  xor     ecx, ecx; ClientBinding
0x180005cfb  call    cs:__imp_RpcServerInqCallAttributesW
0x180005d01  cmp     eax, 6D2h
0x180005d06  jz      short loc_180005D28
0x180005d08  test    eax, eax
0x180005d0a  jnz     short loc_180005D1F
0x180005d0c  cmp     [rsp+0E8h+var_90], 6
0x180005d11  jnb     short loc_180005D28
0x180005d13  mov     ecx, 5; exception
0x180005d18  call    cs:__imp_RpcRaiseException
0x180005d1e  int     3; Trap to Debugger
0x180005d1f  mov     ecx, eax; exception
0x180005d21  call    cs:__imp_RpcRaiseException
0x180005d27  int     3; Trap to Debugger
0x180005d28  xor     ecx, ecx; BindingHandle
0x180005d2a  call    cs:__imp_RpcImpersonateClient
0x180005d30  test    eax, eax
0x180005d32  jz      short loc_180005D3D
0x180005d34  mov     ecx, eax; exception
0x180005d36  call    cs:__imp_RpcRaiseException
0x180005d3c  int     3; Trap to Debugger
0x180005d3d  mov     r9d, ebp; unsigned int
0x180005d40  mov     [rsp+0E8h+var_C8], rsi; unsigned int *
0x180005d45  mov     r8, rbx; unsigned __int8 *
0x180005d48  mov     rdx, r15; Buf1
0x180005d4b  mov     rcx, r14; unsigned __int16 *
0x180005d4e  call    PerflibciLocalEnumerateCounterSetInstances
0x180005d53  mov     ebx, eax
0x180005d55  test    eax, eax
0x180005d57  jnz     short loc_180005D5D
0x180005d59  mov     ecx, [rsi]
0x180005d5b  mov     [rdi], ecx
0x180005d5d  call    cs:__imp_RpcRevertToSelf
0x180005d63  mov     eax, ebx
0x180005d65  mov     rcx, [rsp+0E8h+var_38]
0x180005d6d  xor     rcx, rsp; StackCookie
0x180005d70  call    __security_check_cookie
0x180005d75  mov     rbx, [rsp+0E8h+arg_0]
0x180005d7d  add     rsp, 0C0h
0x180005d84  pop     r15
0x180005d86  pop     r14
0x180005d88  pop     rdi
0x180005d89  pop     rsi
0x180005d8a  pop     rbp
0x180005d8b  retn
```
