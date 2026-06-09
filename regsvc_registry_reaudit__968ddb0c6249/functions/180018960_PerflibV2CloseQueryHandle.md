# PerflibV2CloseQueryHandle

- ea: `0x180018960`
- end: `0x180018a51`
- name: `PerflibV2CloseQueryHandle`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800163f4`
- `0x180016544`
- `0x180016574`
- `0x180018960`
- `0x180019178`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x1800189dd`
- `RPCRT4!RpcRaiseException` at `0x1800189e6`
- `RPCRT4!RpcRaiseException` at `0x1800189fb`
- `RPCRT4!RpcRaiseException` at `0x1800189dd`
- `RPCRT4!RpcRaiseException` at `0x1800189e6`
- `RPCRT4!RpcRaiseException` at `0x1800189fb`
- `RPCRT4!RpcImpersonateClient` at `0x1800189ef`
- `RPCRT4!RpcImpersonateClient` at `0x1800189ef`
- `RPCRT4!RpcRevertToSelf` at `0x180018a0c`
- `RPCRT4!RpcRevertToSelf` at `0x180018a0c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800189c2`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800189c2`

## pseudocode

```c
__int64 __fastcall PerflibV2CloseQueryHandle(struct _PERF_QUERY **a1)
{
  struct _PERF_QUERY *v1; // rdi
  unsigned int IsLocalQueryFromHandle; // ebx
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v7[36]; // [rsp+24h] [rbp-94h] BYREF
  unsigned int v8; // [rsp+48h] [rbp-70h]

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    IsLocalQueryFromHandle = PerflibciIsLocalQueryFromHandle(v1);
  else
    IsLocalQueryFromHandle = 87;
  if ( IsLocalQueryFromHandle )
  {
    if ( IsLocalQueryFromHandle == 13 )
    {
      PerflibciReleaseMutex(*(_QWORD *)v1);
      return 87;
    }
  }
  else
  {
    memset_0(v7, 0, 0x74u);
    RpcCallAttributes = 3;
    v3 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    if ( v3 != 1746 )
    {
      if ( v3 )
        RpcRaiseException(v3);
      if ( v8 < 6 )
        RpcRaiseException(5);
    }
    v4 = RpcImpersonateClient(0);
    if ( v4 )
      RpcRaiseException(v4);
    IsLocalQueryFromHandle = PerflibciCloseLocalQueryHandle(v1);
    RpcRevertToSelf();
    PerflibciFreeLocalQueryHandle(v1);
  }
  return IsLocalQueryFromHandle;
}

```

## disassembly

```asm
0x180018960  mov     [rsp+arg_8], rbx
0x180018965  push    rdi
0x180018966  sub     rsp, 0B0h
0x18001896d  mov     rax, cs:__security_cookie
0x180018974  xor     rax, rsp
0x180018977  mov     [rsp+0B8h+var_18], rax
0x18001897f  mov     rdi, [rcx]
0x180018982  mov     qword ptr [rcx], 0
0x180018989  test    rdi, rdi
0x18001898c  jz      short loc_18001899A
0x18001898e  mov     rcx, rdi
0x180018991  call    PerflibciIsLocalQueryFromHandle
0x180018996  mov     ebx, eax
0x180018998  jmp     short loc_18001899F
0x18001899a  mov     ebx, 57h ; 'W'
0x18001899f  test    ebx, ebx
0x1800189a1  jnz     short loc_180018A1C
0x1800189a3  xor     edx, edx; Val
0x1800189a5  lea     r8d, [rbx+74h]; Size
0x1800189a9  lea     rcx, [rsp+0B8h+var_94]; void *
0x1800189ae  call    memset_0
0x1800189b3  lea     rdx, [rsp+0B8h+RpcCallAttributes]; RpcCallAttributes
0x1800189b8  mov     [rsp+0B8h+RpcCallAttributes], 3
0x1800189c0  xor     ecx, ecx; ClientBinding
0x1800189c2  call    cs:__imp_RpcServerInqCallAttributesW
0x1800189c8  cmp     eax, 6D2h
0x1800189cd  jz      short loc_1800189ED
0x1800189cf  test    eax, eax
0x1800189d1  jnz     short loc_1800189E4
0x1800189d3  cmp     [rsp+0B8h+var_70], 6
0x1800189d8  jnb     short loc_1800189ED
0x1800189da  lea     ecx, [rbx+5]; exception
0x1800189dd  call    cs:__imp_RpcRaiseException
0x1800189e3  int     3; Trap to Debugger
0x1800189e4  mov     ecx, eax; exception
0x1800189e6  call    cs:__imp_RpcRaiseException
0x1800189ec  int     3; Trap to Debugger
0x1800189ed  xor     ecx, ecx; BindingHandle
0x1800189ef  call    cs:__imp_RpcImpersonateClient
0x1800189f5  test    eax, eax
0x1800189f7  jz      short loc_180018A02
0x1800189f9  mov     ecx, eax; exception
0x1800189fb  call    cs:__imp_RpcRaiseException
0x180018a01  int     3; Trap to Debugger
0x180018a02  mov     rcx, rdi; struct _PERF_QUERY *
0x180018a05  call    PerflibciCloseLocalQueryHandle
0x180018a0a  mov     ebx, eax
0x180018a0c  call    cs:__imp_RpcRevertToSelf
0x180018a12  mov     rcx, rdi; Block
0x180018a15  call    PerflibciFreeLocalQueryHandle
0x180018a1a  jmp     short loc_180018A2E
0x180018a1c  cmp     ebx, 0Dh
0x180018a1f  jnz     short loc_180018A2E
0x180018a21  mov     rcx, [rdi]
0x180018a24  call    PerflibciReleaseMutex
0x180018a29  mov     ebx, 57h ; 'W'
0x180018a2e  mov     eax, ebx
0x180018a30  mov     rcx, [rsp+0B8h+var_18]
0x180018a38  xor     rcx, rsp; StackCookie
0x180018a3b  call    __security_check_cookie
0x180018a40  mov     rbx, [rsp+0B8h+arg_8]
0x180018a48  add     rsp, 0B0h
0x180018a4f  pop     rdi
0x180018a50  retn
```
