# EfsRpcQueryRecoveryAgents_Downlevel

- ea: `0x180007a30`
- end: `0x180007b05`
- name: `EfsRpcQueryRecoveryAgents_Downlevel`
- size: `213`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, struct _ENCRYPTION_CERTIFICATE_HASH_LIST **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x180007a30`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000bd78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007add`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aec`
- `RPCRT4!RpcImpersonateClient` at `0x180007a96`
- `RPCRT4!RpcImpersonateClient` at `0x180007a96`
- `RPCRT4!RpcRevertToSelf` at `0x180007ad0`
- `RPCRT4!RpcRevertToSelf` at `0x180007ad0`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryRecoveryAgents_Downlevel(
        void *a1,
        unsigned __int16 *a2,
        struct _ENCRYPTION_CERTIFICATE_HASH_LIST **a3)
{
  __int64 v5; // rdx
  unsigned int LocalFileName; // ebx
  HANDLE ProcessHeap; // rax
  int v9; // [rsp+20h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-20h] BYREF
  void **v11; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+38h] [rbp-10h]
  __int16 v13; // [rsp+88h] [rbp+40h] BYREF

  v9 = 0;
  lpMem = 0;
  v13 = 0;
  if ( (unsigned int)EfsRpcpValidateClientCall(a1, &v9) || !v9 )
  {
    return 5;
  }
  else
  {
    LocalFileName = EfsGetLocalFileName(a2, v5, (unsigned __int16 **)&lpMem, &v13);
    if ( !LocalFileName )
    {
      if ( v13 == 1 )
      {
        LocalFileName = 5;
      }
      else
      {
        LocalFileName = RpcImpersonateClient(0);
        if ( !LocalFileName )
        {
          LocalFileName = EfsEnsureLocalPath((const WCHAR *)lpMem);
          if ( !LocalFileName )
          {
            v12 = 0;
            v11 = &CEfsClient::`vftable';
            LocalFileName = CEfsClientBase::EfsQueryRecoveryAgentsClient((CEfsClientBase *)&v11, a2, a3);
          }
          RpcRevertToSelf();
        }
      }
    }
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return LocalFileName;
}

```

## disassembly

```asm
0x180007a30  push    rbp
0x180007a32  push    rbx
0x180007a33  push    rsi
0x180007a34  push    r14
0x180007a36  mov     rbp, rsp
0x180007a39  sub     rsp, 48h
0x180007a3d  mov     rsi, rdx
0x180007a40  mov     [rbp+var_28], 0
0x180007a47  xor     eax, eax
0x180007a49  mov     [rbp+lpMem], 0
0x180007a51  lea     rdx, [rbp+var_28]
0x180007a55  mov     [rbp+arg_18], ax
0x180007a59  mov     r14, r8
0x180007a5c  call    EfsRpcpValidateClientCall
0x180007a61  test    eax, eax
0x180007a63  jnz     loc_180007AF4
0x180007a69  cmp     [rbp+var_28], eax
0x180007a6c  jz      loc_180007AF4
0x180007a72  lea     r9, [rbp+arg_18]
0x180007a76  mov     rcx, rsi; unsigned __int16 *
0x180007a79  lea     r8, [rbp+lpMem]
0x180007a7d  call    EfsGetLocalFileName
0x180007a82  mov     ebx, eax
0x180007a84  test    eax, eax
0x180007a86  jnz     short loc_180007AD6
0x180007a88  cmp     [rbp+arg_18], 1
0x180007a8d  jnz     short loc_180007A94
0x180007a8f  lea     ebx, [rax+5]
0x180007a92  jmp     short loc_180007AD6
0x180007a94  xor     ecx, ecx; BindingHandle
0x180007a96  call    cs:__imp_RpcImpersonateClient
0x180007a9c  mov     ebx, eax
0x180007a9e  test    eax, eax
0x180007aa0  jnz     short loc_180007AD6
0x180007aa2  mov     rcx, [rbp+lpMem]
0x180007aa6  call    EfsEnsureLocalPath
0x180007aab  mov     ebx, eax
0x180007aad  test    eax, eax
0x180007aaf  jnz     short loc_180007AD0
0x180007ab1  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x180007ab8  mov     [rbp+var_10], ebx
0x180007abb  mov     r8, r14; struct _ENCRYPTION_CERTIFICATE_HASH_LIST **
0x180007abe  mov     [rbp+var_18], rax
0x180007ac2  mov     rdx, rsi; unsigned __int16 *
0x180007ac5  lea     rcx, [rbp+var_18]; this
0x180007ac9  call    ?EfsQueryRecoveryAgentsClient@CEfsClientBase@@QEAAKPEBGPEAPEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@@Z; CEfsClientBase::EfsQueryRecoveryAgentsClient(ushort const *,_ENCRYPTION_CERTIFICATE_HASH_LIST * *)
0x180007ace  mov     ebx, eax
0x180007ad0  call    cs:__imp_RpcRevertToSelf
0x180007ad6  cmp     [rbp+lpMem], 0
0x180007adb  jz      short loc_180007AF9
0x180007add  call    cs:__imp_GetProcessHeap
0x180007ae3  mov     r8, [rbp+lpMem]; lpMem
0x180007ae7  xor     edx, edx; dwFlags
0x180007ae9  mov     rcx, rax; hHeap
0x180007aec  call    cs:__imp_HeapFree
0x180007af2  jmp     short loc_180007AF9
0x180007af4  mov     ebx, 5
0x180007af9  mov     eax, ebx
0x180007afb  add     rsp, 48h
0x180007aff  pop     r14
0x180007b01  pop     rsi
0x180007b02  pop     rbx
0x180007b03  pop     rbp
0x180007b04  retn
```
