# EfsRpcQueryUsersOnFile_Downlevel

- ea: `0x180007b10`
- end: `0x180007be5`
- name: `EfsRpcQueryUsersOnFile_Downlevel`
- size: `213`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, struct _ENCRYPTION_CERTIFICATE_HASH_LIST **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007b10`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000bfc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bcc`
- `RPCRT4!RpcImpersonateClient` at `0x180007b76`
- `RPCRT4!RpcImpersonateClient` at `0x180007b76`
- `RPCRT4!RpcRevertToSelf` at `0x180007bb0`
- `RPCRT4!RpcRevertToSelf` at `0x180007bb0`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryUsersOnFile_Downlevel(
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
            LocalFileName = CEfsClientBase::EfsQueryUsersClient((CEfsClientBase *)&v11, a2, a3);
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
0x180007b10  push    rbp
0x180007b12  push    rbx
0x180007b13  push    rsi
0x180007b14  push    r14
0x180007b16  mov     rbp, rsp
0x180007b19  sub     rsp, 48h
0x180007b1d  mov     rsi, rdx
0x180007b20  mov     [rbp+var_28], 0
0x180007b27  xor     eax, eax
0x180007b29  mov     [rbp+lpMem], 0
0x180007b31  lea     rdx, [rbp+var_28]
0x180007b35  mov     [rbp+arg_18], ax
0x180007b39  mov     r14, r8
0x180007b3c  call    EfsRpcpValidateClientCall
0x180007b41  test    eax, eax
0x180007b43  jnz     loc_180007BD4
0x180007b49  cmp     [rbp+var_28], eax
0x180007b4c  jz      loc_180007BD4
0x180007b52  lea     r9, [rbp+arg_18]
0x180007b56  mov     rcx, rsi; unsigned __int16 *
0x180007b59  lea     r8, [rbp+lpMem]
0x180007b5d  call    EfsGetLocalFileName
0x180007b62  mov     ebx, eax
0x180007b64  test    eax, eax
0x180007b66  jnz     short loc_180007BB6
0x180007b68  cmp     [rbp+arg_18], 1
0x180007b6d  jnz     short loc_180007B74
0x180007b6f  lea     ebx, [rax+5]
0x180007b72  jmp     short loc_180007BB6
0x180007b74  xor     ecx, ecx; BindingHandle
0x180007b76  call    cs:__imp_RpcImpersonateClient
0x180007b7c  mov     ebx, eax
0x180007b7e  test    eax, eax
0x180007b80  jnz     short loc_180007BB6
0x180007b82  mov     rcx, [rbp+lpMem]
0x180007b86  call    EfsEnsureLocalPath
0x180007b8b  mov     ebx, eax
0x180007b8d  test    eax, eax
0x180007b8f  jnz     short loc_180007BB0
0x180007b91  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x180007b98  mov     [rbp+var_10], ebx
0x180007b9b  mov     r8, r14; struct _ENCRYPTION_CERTIFICATE_HASH_LIST **
0x180007b9e  mov     [rbp+var_18], rax
0x180007ba2  mov     rdx, rsi; unsigned __int16 *
0x180007ba5  lea     rcx, [rbp+var_18]; this
0x180007ba9  call    ?EfsQueryUsersClient@CEfsClientBase@@QEAAKPEBGPEAPEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@@Z; CEfsClientBase::EfsQueryUsersClient(ushort const *,_ENCRYPTION_CERTIFICATE_HASH_LIST * *)
0x180007bae  mov     ebx, eax
0x180007bb0  call    cs:__imp_RpcRevertToSelf
0x180007bb6  cmp     [rbp+lpMem], 0
0x180007bbb  jz      short loc_180007BD9
0x180007bbd  call    cs:__imp_GetProcessHeap
0x180007bc3  mov     r8, [rbp+lpMem]; lpMem
0x180007bc7  xor     edx, edx; dwFlags
0x180007bc9  mov     rcx, rax; hHeap
0x180007bcc  call    cs:__imp_HeapFree
0x180007bd2  jmp     short loc_180007BD9
0x180007bd4  mov     ebx, 5
0x180007bd9  mov     eax, ebx
0x180007bdb  add     rsp, 48h
0x180007bdf  pop     r14
0x180007be1  pop     rsi
0x180007be2  pop     rbx
0x180007be3  pop     rbp
0x180007be4  retn
```
