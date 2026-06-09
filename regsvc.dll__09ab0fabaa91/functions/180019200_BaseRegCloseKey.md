# BaseRegCloseKey

- ea: `0x180019200`
- end: `0x180019289`
- name: `BaseRegCloseKey`
- size: `137`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180016cd0`
- `0x180019200`
- `0x18001acf4`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001921d`
- `RPCRT4!RpcImpersonateClient` at `0x18001921d`
- `RPCRT4!RpcRevertToSelf` at `0x18001925d`
- `RPCRT4!RpcRevertToSelf` at `0x18001925d`

## pseudocode

```c
__int64 __fastcall BaseRegCloseKey(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned int v3; // edi
  RPC_STATUS v4; // ebp

  v1 = *a1;
  if ( *a1 )
  {
    v4 = RpcImpersonateClient(0);
    if ( (*(_BYTE *)(v1 + 8) & 1) != 0 )
      goto LABEL_4;
    if ( (*(_BYTE *)(v1 + 8) & 2) != 0 )
      _InterlockedDecrement(&RestrictedHandlesQuota);
    if ( *(HANDLE *)v1 == RestrictedUserHandle )
    {
LABEL_4:
      *(_QWORD *)v1 = 0;
      v3 = 0;
    }
    else
    {
      v3 = BaseRegCloseKeyInternal(v1);
    }
    if ( !v4 )
      RpcRevertToSelf();
  }
  else
  {
    v3 = 87;
  }
  if ( *a1 && !*(_QWORD *)v1 )
  {
    RegSvcContextFree(v1);
    *a1 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180019200  push    rbx
0x180019202  push    rbp
0x180019203  push    rsi
0x180019204  push    rdi
0x180019205  sub     rsp, 28h
0x180019209  mov     rbx, [rcx]
0x18001920c  mov     rsi, rcx
0x18001920f  test    rbx, rbx
0x180019212  jnz     short loc_18001921B
0x180019214  mov     edi, 57h ; 'W'
0x180019219  jmp     short loc_180019263
0x18001921b  xor     ecx, ecx; BindingHandle
0x18001921d  call    cs:__imp_RpcImpersonateClient
0x180019223  test    byte ptr [rbx+8], 1
0x180019227  mov     ebp, eax
0x180019229  jz      short loc_180019236
0x18001922b  mov     qword ptr [rbx], 0
0x180019232  xor     edi, edi
0x180019234  jmp     short loc_180019259
0x180019236  test    byte ptr [rbx+8], 2
0x18001923a  jz      short loc_180019243
0x18001923c  lock dec cs:RestrictedHandlesQuota
0x180019243  mov     rax, cs:RestrictedUserHandle
0x18001924a  cmp     [rbx], rax
0x18001924d  jz      short loc_18001922B
0x18001924f  mov     rcx, rbx
0x180019252  call    BaseRegCloseKeyInternal
0x180019257  mov     edi, eax
0x180019259  test    ebp, ebp
0x18001925b  jnz     short loc_180019263
0x18001925d  call    cs:__imp_RpcRevertToSelf
0x180019263  cmp     qword ptr [rsi], 0
0x180019267  jz      short loc_18001927E
0x180019269  cmp     qword ptr [rbx], 0
0x18001926d  jnz     short loc_18001927E
0x18001926f  mov     rcx, rbx
0x180019272  call    RegSvcContextFree
0x180019277  mov     qword ptr [rsi], 0
0x18001927e  mov     eax, edi
0x180019280  add     rsp, 28h
0x180019284  pop     rdi
0x180019285  pop     rsi
0x180019286  pop     rbp
0x180019287  pop     rbx
0x180019288  retn
```
