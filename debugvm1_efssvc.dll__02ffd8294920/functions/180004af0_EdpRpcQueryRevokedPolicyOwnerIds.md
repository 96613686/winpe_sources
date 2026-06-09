# EdpRpcQueryRevokedPolicyOwnerIds

- ea: `0x180004af0`
- end: `0x180004b9f`
- name: `EdpRpcQueryRevokedPolicyOwnerIds`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004af0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllQueryRevokedPolicyOwnerIds` at `0x180004b5e`
- `EFSCORE!EdpDllQueryRevokedPolicyOwnerIds` at `0x180004b5e`

## pseudocode

```c
__int64 __fastcall EdpRpcQueryRevokedPolicyOwnerIds(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v7; // ebx
  signed int v8; // eax
  __int64 v9; // rcx
  signed int RevokedPolicyOwnerIds; // eax
  __int64 v11; // rcx
  _BYTE v13[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v13, 0, 0x70u);
  if ( a4 )
  {
    v8 = EdpBeginLocalOnlyRpcCall((__int64)v13);
    v7 = v8;
    if ( v8 >= 0 )
    {
      RevokedPolicyOwnerIds = EdpDllQueryRevokedPolicyOwnerIds(v13, a2, a3, a4);
      v7 = RevokedPolicyOwnerIds;
      if ( RevokedPolicyOwnerIds < 0 )
        fnEfsLogTrace1(v11, (__int64)EFS_API_ERROR, RevokedPolicyOwnerIds, 6, 22);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v8, 6, 11);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v7;
}

```

## disassembly

```asm
0x180004af0  push    rbx
0x180004af2  push    rbp
0x180004af3  push    rsi
0x180004af4  push    rdi
0x180004af5  sub     rsp, 0A8h
0x180004afc  mov     rbp, rdx
0x180004aff  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004b04  xor     edx, edx; Val
0x180004b06  mov     esi, r8d
0x180004b09  mov     rdi, r9
0x180004b0c  lea     r8d, [rdx+70h]; Size
0x180004b10  call    memset_0
0x180004b15  test    rdi, rdi
0x180004b18  jnz     short loc_180004B21
0x180004b1a  mov     ebx, 80004003h
0x180004b1f  jmp     short loc_180004B91
0x180004b21  lea     rcx, [rsp+0C8h+var_98]
0x180004b26  call    EdpBeginLocalOnlyRpcCall
0x180004b2b  mov     ebx, eax
0x180004b2d  test    eax, eax
0x180004b2f  jns     short loc_180004B50
0x180004b31  mov     r9d, 6
0x180004b37  mov     [rsp+0C8h+var_A8], 0B0Bh
0x180004b3f  mov     r8d, eax
0x180004b42  lea     rdx, EFS_API_ERROR
0x180004b49  call    fnEfsLogTrace1
0x180004b4e  jmp     short loc_180004B91
0x180004b50  mov     r9, rdi
0x180004b53  lea     rcx, [rsp+0C8h+var_98]
0x180004b58  mov     r8d, esi
0x180004b5b  mov     rdx, rbp
0x180004b5e  call    cs:__imp_EdpDllQueryRevokedPolicyOwnerIds
0x180004b64  mov     ebx, eax
0x180004b66  test    eax, eax
0x180004b68  jns     short loc_180004B87
0x180004b6a  mov     r9d, 6
0x180004b70  mov     [rsp+0C8h+var_A8], 0B16h
0x180004b78  mov     r8d, eax
0x180004b7b  lea     rdx, EFS_API_ERROR
0x180004b82  call    fnEfsLogTrace1
0x180004b87  lea     rcx, [rsp+0C8h+var_98]
0x180004b8c  call    EdpCleanupLocalOnlyRpcCall
0x180004b91  mov     eax, ebx
0x180004b93  add     rsp, 0A8h
0x180004b9a  pop     rdi
0x180004b9b  pop     rsi
0x180004b9c  pop     rbp
0x180004b9d  pop     rbx
0x180004b9e  retn
```
