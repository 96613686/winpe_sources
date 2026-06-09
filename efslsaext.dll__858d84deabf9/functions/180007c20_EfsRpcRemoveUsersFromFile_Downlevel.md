# EfsRpcRemoveUsersFromFile_Downlevel

- ea: `0x180007c20`
- end: `0x180007cf5`
- name: `EfsRpcRemoveUsersFromFile_Downlevel`
- size: `213`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, struct _ENCRYPTION_CERTIFICATE_HASH_LIST *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007c20`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000c21c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ccd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ccd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cdc`
- `RPCRT4!RpcImpersonateClient` at `0x180007c86`
- `RPCRT4!RpcImpersonateClient` at `0x180007c86`
- `RPCRT4!RpcRevertToSelf` at `0x180007cc0`
- `RPCRT4!RpcRevertToSelf` at `0x180007cc0`

## pseudocode

```c
__int64 __fastcall EfsRpcRemoveUsersFromFile_Downlevel(
        void *a1,
        unsigned __int16 *a2,
        struct _ENCRYPTION_CERTIFICATE_HASH_LIST *a3)
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
            LocalFileName = CEfsClientBase::EfsRemoveUsersClient((CEfsClientBase *)&v11, a2, a3);
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
0x180007c20  push    rbp
0x180007c22  push    rbx
0x180007c23  push    rsi
0x180007c24  push    r14
0x180007c26  mov     rbp, rsp
0x180007c29  sub     rsp, 48h
0x180007c2d  mov     rsi, rdx
0x180007c30  mov     [rbp+var_28], 0
0x180007c37  xor     eax, eax
0x180007c39  mov     [rbp+lpMem], 0
0x180007c41  lea     rdx, [rbp+var_28]
0x180007c45  mov     [rbp+arg_18], ax
0x180007c49  mov     r14, r8
0x180007c4c  call    EfsRpcpValidateClientCall
0x180007c51  test    eax, eax
0x180007c53  jnz     loc_180007CE4
0x180007c59  cmp     [rbp+var_28], eax
0x180007c5c  jz      loc_180007CE4
0x180007c62  lea     r9, [rbp+arg_18]
0x180007c66  mov     rcx, rsi; unsigned __int16 *
0x180007c69  lea     r8, [rbp+lpMem]
0x180007c6d  call    EfsGetLocalFileName
0x180007c72  mov     ebx, eax
0x180007c74  test    eax, eax
0x180007c76  jnz     short loc_180007CC6
0x180007c78  cmp     [rbp+arg_18], 1
0x180007c7d  jnz     short loc_180007C84
0x180007c7f  lea     ebx, [rax+5]
0x180007c82  jmp     short loc_180007CC6
0x180007c84  xor     ecx, ecx; BindingHandle
0x180007c86  call    cs:__imp_RpcImpersonateClient
0x180007c8c  mov     ebx, eax
0x180007c8e  test    eax, eax
0x180007c90  jnz     short loc_180007CC6
0x180007c92  mov     rcx, [rbp+lpMem]
0x180007c96  call    EfsEnsureLocalPath
0x180007c9b  mov     ebx, eax
0x180007c9d  test    eax, eax
0x180007c9f  jnz     short loc_180007CC0
0x180007ca1  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x180007ca8  mov     [rbp+var_10], ebx
0x180007cab  mov     r8, r14; struct _ENCRYPTION_CERTIFICATE_HASH_LIST *
0x180007cae  mov     [rbp+var_18], rax
0x180007cb2  mov     rdx, rsi; unsigned __int16 *
0x180007cb5  lea     rcx, [rbp+var_18]; this
0x180007cb9  call    ?EfsRemoveUsersClient@CEfsClientBase@@QEAAKPEBGPEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@@Z; CEfsClientBase::EfsRemoveUsersClient(ushort const *,_ENCRYPTION_CERTIFICATE_HASH_LIST *)
0x180007cbe  mov     ebx, eax
0x180007cc0  call    cs:__imp_RpcRevertToSelf
0x180007cc6  cmp     [rbp+lpMem], 0
0x180007ccb  jz      short loc_180007CE9
0x180007ccd  call    cs:__imp_GetProcessHeap
0x180007cd3  mov     r8, [rbp+lpMem]; lpMem
0x180007cd7  xor     edx, edx; dwFlags
0x180007cd9  mov     rcx, rax; hHeap
0x180007cdc  call    cs:__imp_HeapFree
0x180007ce2  jmp     short loc_180007CE9
0x180007ce4  mov     ebx, 5
0x180007ce9  mov     eax, ebx
0x180007ceb  add     rsp, 48h
0x180007cef  pop     r14
0x180007cf1  pop     rsi
0x180007cf2  pop     rbx
0x180007cf3  pop     rbp
0x180007cf4  retn
```
