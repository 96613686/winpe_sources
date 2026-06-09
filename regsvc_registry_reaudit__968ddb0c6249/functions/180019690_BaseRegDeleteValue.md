# BaseRegDeleteValue

- ea: `0x180019690`
- end: `0x1800197a7`
- name: `BaseRegDeleteValue`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x180019690`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180019763`
- `ntdll!NtDeleteValueKey` at `0x180019763`
- `ntdll!RtlNtStatusToDosError` at `0x18001976b`
- `ntdll!RtlNtStatusToDosError` at `0x18001976b`
- `RPCRT4!RpcRaiseException` at `0x180019703`
- `RPCRT4!RpcRaiseException` at `0x18001970c`
- `RPCRT4!RpcRaiseException` at `0x180019721`
- `RPCRT4!RpcRaiseException` at `0x180019703`
- `RPCRT4!RpcRaiseException` at `0x18001970c`
- `RPCRT4!RpcRaiseException` at `0x180019721`
- `RPCRT4!RpcImpersonateClient` at `0x180019715`
- `RPCRT4!RpcImpersonateClient` at `0x180019715`
- `RPCRT4!RpcRevertToSelf` at `0x18001977a`
- `RPCRT4!RpcRevertToSelf` at `0x18001977a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800196e8`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800196e8`

## pseudocode

```c
__int64 __fastcall BaseRegDeleteValue(void **a1, struct _UNICODE_STRING *a2)
{
  ULONG v4; // ebx
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  __int16 Length; // ax
  void *v8; // rcx
  NTSTATUS v9; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v12[36]; // [rsp+24h] [rbp-94h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-70h]

  if ( a1 )
  {
    memset_0(v12, 0, 0x74u);
    RpcCallAttributes = 3;
    v5 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v5 != 1746 )
    {
      if ( v5 )
        RpcRaiseException(v5);
      if ( v13 < 6 )
        RpcRaiseException(5);
    }
    v6 = RpcImpersonateClient(0);
    if ( v6 )
      RpcRaiseException(v6);
    if ( !a2 || (Length = a2->Length, a2->Length < 2u) || (Length & 1) != 0 || !a2->Buffer )
    {
      if ( a2->Buffer || a2->Length != 2 || a2->MaximumLength )
      {
        v4 = 87;
        goto LABEL_20;
      }
      Length = 2;
    }
    v8 = *a1;
    a2->Length = Length - 2;
    v9 = NtDeleteValueKey(v8, a2);
    v4 = RtlNtStatusToDosError(v9);
LABEL_20:
    RpcRevertToSelf();
    return v4;
  }
  return 87;
}

```

## disassembly

```asm
0x180019690  mov     [rsp+arg_10], rbx
0x180019695  mov     [rsp+arg_18], rsi
0x18001969a  push    rdi
0x18001969b  sub     rsp, 0B0h
0x1800196a2  mov     rax, cs:__security_cookie
0x1800196a9  xor     rax, rsp
0x1800196ac  mov     [rsp+0B8h+var_18], rax
0x1800196b4  xor     esi, esi
0x1800196b6  mov     rbx, rdx
0x1800196b9  mov     rdi, rcx
0x1800196bc  test    rcx, rcx
0x1800196bf  jnz     short loc_1800196C9
0x1800196c1  lea     ebx, [rcx+57h]
0x1800196c4  jmp     loc_180019780
0x1800196c9  xor     edx, edx; Val
0x1800196cb  lea     rcx, [rsp+0B8h+var_94]; void *
0x1800196d0  lea     r8d, [rdx+74h]; Size
0x1800196d4  call    memset_0
0x1800196d9  lea     rdx, [rsp+0B8h+RpcCallAttributes]; RpcCallAttributes
0x1800196de  mov     [rsp+0B8h+RpcCallAttributes], 3
0x1800196e6  xor     ecx, ecx; ClientBinding
0x1800196e8  call    cs:__imp_RpcServerInqCallAttributesW
0x1800196ee  cmp     eax, 6D2h
0x1800196f3  jz      short loc_180019713
0x1800196f5  test    eax, eax
0x1800196f7  jnz     short loc_18001970A
0x1800196f9  cmp     [rsp+0B8h+var_70], 6
0x1800196fe  jnb     short loc_180019713
0x180019700  lea     ecx, [rax+5]; exception
0x180019703  call    cs:__imp_RpcRaiseException
0x180019709  int     3; Trap to Debugger
0x18001970a  mov     ecx, eax; exception
0x18001970c  call    cs:__imp_RpcRaiseException
0x180019712  int     3; Trap to Debugger
0x180019713  xor     ecx, ecx; BindingHandle
0x180019715  call    cs:__imp_RpcImpersonateClient
0x18001971b  test    eax, eax
0x18001971d  jz      short loc_180019728
0x18001971f  mov     ecx, eax; exception
0x180019721  call    cs:__imp_RpcRaiseException
0x180019727  int     3; Trap to Debugger
0x180019728  mov     edx, 2
0x18001972d  test    rbx, rbx
0x180019730  jz      short loc_180019744
0x180019732  movzx   eax, word ptr [rbx]
0x180019735  cmp     ax, dx
0x180019738  jb      short loc_180019744
0x18001973a  test    al, 1
0x18001973c  jnz     short loc_180019744
0x18001973e  cmp     [rbx+8], rsi
0x180019742  jnz     short loc_180019757
0x180019744  cmp     [rbx+8], rsi
0x180019748  jnz     short loc_180019775
0x18001974a  cmp     [rbx], dx
0x18001974d  jnz     short loc_180019775
0x18001974f  cmp     [rbx+2], si
0x180019753  jnz     short loc_180019775
0x180019755  mov     eax, edx
0x180019757  mov     rcx, [rdi]; KeyHandle
0x18001975a  sub     ax, dx
0x18001975d  mov     rdx, rbx; ValueName
0x180019760  mov     [rbx], ax
0x180019763  call    cs:__imp_NtDeleteValueKey
0x180019769  mov     ecx, eax; Status
0x18001976b  call    cs:__imp_RtlNtStatusToDosError
0x180019771  mov     ebx, eax
0x180019773  jmp     short loc_18001977A
0x180019775  mov     ebx, 57h ; 'W'
0x18001977a  call    cs:__imp_RpcRevertToSelf
0x180019780  mov     eax, ebx
0x180019782  mov     rcx, [rsp+0B8h+var_18]
0x18001978a  xor     rcx, rsp; StackCookie
0x18001978d  call    __security_check_cookie
0x180019792  lea     r11, [rsp+0B8h+var_8]
0x18001979a  mov     rbx, [r11+20h]
0x18001979e  mov     rsi, [r11+28h]
0x1800197a2  mov     rsp, r11
0x1800197a5  pop     rdi
0x1800197a6  retn
```
