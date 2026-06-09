# EfsRpcDecryptFileSrv_Downlevel

- ea: `0x180007460`
- end: `0x180007582`
- name: `EfsRpcDecryptFileSrv_Downlevel`
- size: `290`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007460`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000b1e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007556`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007565`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007565`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007539`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007539`
- `RPCRT4!RpcImpersonateClient` at `0x1800074d2`
- `RPCRT4!RpcImpersonateClient` at `0x1800074d2`
- `RPCRT4!RpcRevertToSelf` at `0x180007549`
- `RPCRT4!RpcRevertToSelf` at `0x180007549`

## pseudocode

```c
__int64 __fastcall EfsRpcDecryptFileSrv_Downlevel(void *a1)
{
  EfsRpcpValidateClientCall(a1);
  return 5;
}

```

## disassembly

```asm
0x180007460  push    rbp
0x180007462  push    rbx
0x180007463  push    rsi
0x180007464  push    r13
0x180007466  push    r14
0x180007468  push    r15
0x18000746a  mov     rbp, rsp
0x18000746d  sub     rsp, 48h
0x180007471  mov     r14, rdx
0x180007474  mov     [rbp+var_28], 0
0x18000747b  xor     eax, eax
0x18000747d  mov     [rbp+lpMem], 0
0x180007485  lea     rdx, [rbp+var_28]
0x180007489  mov     [rbp+arg_18], ax
0x18000748d  mov     r15d, r8d
0x180007490  call    EfsRpcpValidateClientCall
0x180007495  test    eax, eax
0x180007497  jnz     loc_18000756D
0x18000749d  cmp     [rbp+var_28], eax
0x1800074a0  jz      loc_18000756D
0x1800074a6  lea     r9, [rbp+arg_18]
0x1800074aa  mov     rcx, r14; unsigned __int16 *
0x1800074ad  lea     r8, [rbp+lpMem]
0x1800074b1  call    EfsGetLocalFileName
0x1800074b6  mov     ebx, eax
0x1800074b8  test    eax, eax
0x1800074ba  jnz     loc_18000754F
0x1800074c0  lea     r13d, [rax+1]
0x1800074c4  cmp     [rbp+arg_18], r13w
0x1800074c9  jnz     short loc_1800074D0
0x1800074cb  lea     ebx, [rax+5]
0x1800074ce  jmp     short loc_18000754F
0x1800074d0  xor     ecx, ecx; BindingHandle
0x1800074d2  call    cs:__imp_RpcImpersonateClient
0x1800074d8  mov     ebx, eax
0x1800074da  test    eax, eax
0x1800074dc  jnz     short loc_18000754F
0x1800074de  mov     rcx, [rbp+lpMem]
0x1800074e2  call    EfsEnsureLocalPath
0x1800074e7  mov     ebx, eax
0x1800074e9  test    eax, eax
0x1800074eb  jnz     short loc_180007549
0x1800074ed  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x1800074f4  mov     [rbp+var_10], ebx
0x1800074f7  mov     [rbp+var_18], rax
0x1800074fb  xor     esi, esi
0x1800074fd  mov     r8d, r15d; unsigned int
0x180007500  lea     rcx, [rbp+var_18]; this
0x180007504  mov     rdx, r14; unsigned __int16 *
0x180007507  call    ?EfsDecryptFileClient@CEfsClientBase@@QEAAKPEBGK@Z; CEfsClientBase::EfsDecryptFileClient(ushort const *,ulong)
0x18000750c  mov     ebx, eax
0x18000750e  test    eax, eax
0x180007510  jz      short loc_180007549
0x180007512  add     eax, 0FFFFF954h
0x180007517  cmp     eax, 2Dh ; '-'
0x18000751a  ja      short loc_18000752C
0x18000751c  mov     rcx, 2000000CC201h
0x180007526  bt      rcx, rax
0x18000752a  jb      short loc_180007534
0x18000752c  cmp     ebx, 5B4h
0x180007532  jnz     short loc_180007549
0x180007534  mov     ecx, 12Ch; dwMilliseconds
0x180007539  call    cs:__imp_Sleep
0x18000753f  mov     eax, esi
0x180007541  add     esi, r13d
0x180007544  cmp     eax, 3
0x180007547  jb      short loc_1800074FD
0x180007549  call    cs:__imp_RpcRevertToSelf
0x18000754f  cmp     [rbp+lpMem], 0
0x180007554  jz      short loc_180007572
0x180007556  call    cs:__imp_GetProcessHeap
0x18000755c  mov     r8, [rbp+lpMem]; lpMem
0x180007560  xor     edx, edx; dwFlags
0x180007562  mov     rcx, rax; hHeap
0x180007565  call    cs:__imp_HeapFree
0x18000756b  jmp     short loc_180007572
0x18000756d  mov     ebx, 5
0x180007572  mov     eax, ebx
0x180007574  add     rsp, 48h
0x180007578  pop     r15
0x18000757a  pop     r14
0x18000757c  pop     r13
0x18000757e  pop     rsi
0x18000757f  pop     rbx
0x180007580  pop     rbp
0x180007581  retn
```
