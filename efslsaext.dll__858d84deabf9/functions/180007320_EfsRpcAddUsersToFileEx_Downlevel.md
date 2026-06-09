# EfsRpcAddUsersToFileEx_Downlevel

- ea: `0x180007320`
- end: `0x1800073f9`
- name: `EfsRpcAddUsersToFileEx_Downlevel`
- size: `217`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180007400`

## callees

- `0x180007320`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000af80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073e0`
- `RPCRT4!RpcImpersonateClient` at `0x180007386`
- `RPCRT4!RpcImpersonateClient` at `0x180007386`
- `RPCRT4!RpcRevertToSelf` at `0x1800073c4`
- `RPCRT4!RpcRevertToSelf` at `0x1800073c4`

## pseudocode

```c
__int64 __fastcall EfsRpcAddUsersToFileEx_Downlevel(void *a1)
{
  EfsRpcpValidateClientCall(a1);
  return 5;
}

```

## disassembly

```asm
0x180007320  push    rbp
0x180007322  push    rbx
0x180007323  push    rsi
0x180007324  push    r14
0x180007326  mov     rbp, rsp
0x180007329  sub     rsp, 48h
0x18000732d  mov     r14d, edx
0x180007330  mov     [rbp+var_24], 0
0x180007337  xor     eax, eax
0x180007339  mov     [rbp+lpMem], 0
0x180007341  lea     rdx, [rbp+var_24]
0x180007345  mov     [rbp+var_28], ax
0x180007349  mov     rsi, r9
0x18000734c  call    EfsRpcpValidateClientCall
0x180007351  test    eax, eax
0x180007353  jnz     loc_1800073E8
0x180007359  cmp     [rbp+var_24], eax
0x18000735c  jz      loc_1800073E8
0x180007362  lea     r9, [rbp+var_28]
0x180007366  mov     rcx, rsi; unsigned __int16 *
0x180007369  lea     r8, [rbp+lpMem]
0x18000736d  call    EfsGetLocalFileName
0x180007372  mov     ebx, eax
0x180007374  test    eax, eax
0x180007376  jnz     short loc_1800073CA
0x180007378  cmp     [rbp+var_28], 1
0x18000737d  jnz     short loc_180007384
0x18000737f  lea     ebx, [rax+5]
0x180007382  jmp     short loc_1800073CA
0x180007384  xor     ecx, ecx; BindingHandle
0x180007386  call    cs:__imp_RpcImpersonateClient
0x18000738c  mov     ebx, eax
0x18000738e  test    eax, eax
0x180007390  jnz     short loc_1800073CA
0x180007392  mov     rcx, [rbp+lpMem]
0x180007396  call    EfsEnsureLocalPath
0x18000739b  mov     ebx, eax
0x18000739d  test    eax, eax
0x18000739f  jnz     short loc_1800073C4
0x1800073a1  mov     r8, [rbp+arg_20]; struct _ENCRYPTION_CERTIFICATE_LIST *
0x1800073a5  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x1800073ac  mov     r9d, r14d; unsigned int
0x1800073af  mov     [rbp+var_18], rax
0x1800073b3  mov     rdx, rsi; unsigned __int16 *
0x1800073b6  mov     [rbp+var_10], ebx
0x1800073b9  lea     rcx, [rbp+var_18]; this
0x1800073bd  call    ?EfsAddUsersClientEx@CEfsClientBase@@QEAAKPEBGPEAU_ENCRYPTION_CERTIFICATE_LIST@@K@Z; CEfsClientBase::EfsAddUsersClientEx(ushort const *,_ENCRYPTION_CERTIFICATE_LIST *,ulong)
0x1800073c2  mov     ebx, eax
0x1800073c4  call    cs:__imp_RpcRevertToSelf
0x1800073ca  cmp     [rbp+lpMem], 0
0x1800073cf  jz      short loc_1800073ED
0x1800073d1  call    cs:__imp_GetProcessHeap
0x1800073d7  mov     r8, [rbp+lpMem]; lpMem
0x1800073db  xor     edx, edx; dwFlags
0x1800073dd  mov     rcx, rax; hHeap
0x1800073e0  call    cs:__imp_HeapFree
0x1800073e6  jmp     short loc_1800073ED
0x1800073e8  mov     ebx, 5
0x1800073ed  mov     eax, ebx
0x1800073ef  add     rsp, 48h
0x1800073f3  pop     r14
0x1800073f5  pop     rsi
0x1800073f6  pop     rbx
0x1800073f7  pop     rbp
0x1800073f8  retn
```
