# BaseRegUnLoadKey

- ea: `0x18001a1a0`
- end: `0x18001a2be`
- name: `BaseRegUnLoadKey`
- size: `286`
- prototype: `__int64 __fastcall(void **, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001a1a0`

## import_xrefs

- `ntdll!NtUnloadKey` at `0x18001a280`
- `ntdll!NtUnloadKey` at `0x18001a280`
- `ntdll!RtlNtStatusToDosError` at `0x18001a288`
- `ntdll!RtlNtStatusToDosError` at `0x18001a288`
- `RPCRT4!RpcRaiseException` at `0x18001a20d`
- `RPCRT4!RpcRaiseException` at `0x18001a216`
- `RPCRT4!RpcRaiseException` at `0x18001a22b`
- `RPCRT4!RpcRaiseException` at `0x18001a20d`
- `RPCRT4!RpcRaiseException` at `0x18001a216`
- `RPCRT4!RpcRaiseException` at `0x18001a22b`
- `RPCRT4!RpcImpersonateClient` at `0x18001a21f`
- `RPCRT4!RpcImpersonateClient` at `0x18001a21f`
- `RPCRT4!RpcRevertToSelf` at `0x18001a297`
- `RPCRT4!RpcRevertToSelf` at `0x18001a297`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a1f3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a1f3`

## pseudocode

```c
__int64 __fastcall BaseRegUnLoadKey(void **a1, struct _UNICODE_STRING *a2)
{
  ULONG v4; // ebx
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  void *v7; // rcx
  USHORT Length; // ax
  NTSTATUS v9; // eax
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+20h] [rbp-79h] BYREF
  int RpcCallAttributes; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v13[36]; // [rsp+54h] [rbp-45h] BYREF
  unsigned int v14; // [rsp+78h] [rbp-21h]

  if ( a1 )
  {
    memset_0(v13, 0, 0x74u);
    RpcCallAttributes = 3;
    v5 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v5 != 1746 )
    {
      if ( v5 )
        RpcRaiseException(v5);
      if ( v14 < 6 )
        RpcRaiseException(5);
    }
    v6 = RpcImpersonateClient(0);
    if ( v6 )
      RpcRaiseException(v6);
    v7 = *a1;
    *(&KeyObjectAttributes.Length + 1) = 0;
    *(&KeyObjectAttributes.Attributes + 1) = 0;
    if ( !v7 )
      goto LABEL_17;
    if ( a2 )
    {
      Length = a2->Length;
      if ( (a2->Length & 1) != 0 )
        goto LABEL_17;
      if ( Length )
      {
        if ( a2->Buffer )
        {
          a2->Length = Length - 2;
          goto LABEL_16;
        }
LABEL_17:
        v4 = 87;
        goto LABEL_18;
      }
    }
LABEL_16:
    KeyObjectAttributes.RootDirectory = v7;
    KeyObjectAttributes.Length = 48;
    *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
    KeyObjectAttributes.Attributes = 64;
    KeyObjectAttributes.ObjectName = a2;
    v9 = NtUnloadKey(&KeyObjectAttributes);
    v4 = RtlNtStatusToDosError(v9);
LABEL_18:
    RpcRevertToSelf();
    return v4;
  }
  return 87;
}

```

## disassembly

```asm
0x18001a1a0  mov     [rsp-8+arg_10], rbx
0x18001a1a5  push    rbp
0x18001a1a6  push    rsi
0x18001a1a7  push    rdi
0x18001a1a8  lea     rbp, [rsp-47h]
0x18001a1ad  sub     rsp, 0E0h
0x18001a1b4  mov     rax, cs:__security_cookie
0x18001a1bb  xor     rax, rsp
0x18001a1be  mov     [rbp+57h+var_20], rax
0x18001a1c2  xor     esi, esi
0x18001a1c4  mov     rbx, rdx
0x18001a1c7  mov     rdi, rcx
0x18001a1ca  test    rcx, rcx
0x18001a1cd  jnz     short loc_18001A1D7
0x18001a1cf  lea     ebx, [rcx+57h]
0x18001a1d2  jmp     loc_18001A29D
0x18001a1d7  xor     edx, edx; Val
0x18001a1d9  lea     rcx, [rbp+57h+var_9C]; void *
0x18001a1dd  lea     r8d, [rdx+74h]; Size
0x18001a1e1  call    memset_0
0x18001a1e6  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18001a1ea  mov     [rbp+57h+RpcCallAttributes], 3
0x18001a1f1  xor     ecx, ecx; ClientBinding
0x18001a1f3  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a1f9  cmp     eax, 6D2h
0x18001a1fe  jz      short loc_18001A21D
0x18001a200  test    eax, eax
0x18001a202  jnz     short loc_18001A214
0x18001a204  cmp     [rbp+57h+var_78], 6
0x18001a208  jnb     short loc_18001A21D
0x18001a20a  lea     ecx, [rax+5]; exception
0x18001a20d  call    cs:__imp_RpcRaiseException
0x18001a213  int     3; Trap to Debugger
0x18001a214  mov     ecx, eax; exception
0x18001a216  call    cs:__imp_RpcRaiseException
0x18001a21c  int     3; Trap to Debugger
0x18001a21d  xor     ecx, ecx; BindingHandle
0x18001a21f  call    cs:__imp_RpcImpersonateClient
0x18001a225  test    eax, eax
0x18001a227  jz      short loc_18001A232
0x18001a229  mov     ecx, eax; exception
0x18001a22b  call    cs:__imp_RpcRaiseException
0x18001a231  int     3; Trap to Debugger
0x18001a232  mov     rcx, [rdi]
0x18001a235  mov     dword ptr [rbp+57h+KeyObjectAttributes+4], esi
0x18001a238  mov     dword ptr [rbp+57h+KeyObjectAttributes+1Ch], esi
0x18001a23b  test    rcx, rcx
0x18001a23e  jz      short loc_18001A292
0x18001a240  test    rbx, rbx
0x18001a243  jz      short loc_18001A25E
0x18001a245  movzx   eax, word ptr [rbx]
0x18001a248  test    al, 1
0x18001a24a  jnz     short loc_18001A292
0x18001a24c  test    ax, ax
0x18001a24f  jz      short loc_18001A25E
0x18001a251  cmp     [rbx+8], rsi
0x18001a255  jz      short loc_18001A292
0x18001a257  sub     ax, 2
0x18001a25b  mov     [rbx], ax
0x18001a25e  mov     [rbp+57h+KeyObjectAttributes.RootDirectory], rcx
0x18001a262  xorps   xmm0, xmm0
0x18001a265  lea     rcx, [rbp+57h+KeyObjectAttributes]; KeyObjectAttributes
0x18001a269  mov     [rbp+57h+KeyObjectAttributes.Length], 30h ; '0'
0x18001a270  movdqu  xmmword ptr [rbp+57h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x18001a275  mov     [rbp+57h+KeyObjectAttributes.Attributes], 40h ; '@'
0x18001a27c  mov     [rbp+57h+KeyObjectAttributes.ObjectName], rbx
0x18001a280  call    cs:__imp_NtUnloadKey
0x18001a286  mov     ecx, eax; Status
0x18001a288  call    cs:__imp_RtlNtStatusToDosError
0x18001a28e  mov     ebx, eax
0x18001a290  jmp     short loc_18001A297
0x18001a292  mov     ebx, 57h ; 'W'
0x18001a297  call    cs:__imp_RpcRevertToSelf
0x18001a29d  mov     eax, ebx
0x18001a29f  mov     rcx, [rbp+57h+var_20]
0x18001a2a3  xor     rcx, rsp; StackCookie
0x18001a2a6  call    __security_check_cookie
0x18001a2ab  mov     rbx, [rsp+0F0h+arg_10]
0x18001a2b3  add     rsp, 0E0h
0x18001a2ba  pop     rdi
0x18001a2bb  pop     rsi
0x18001a2bc  pop     rbp
0x18001a2bd  retn
```
