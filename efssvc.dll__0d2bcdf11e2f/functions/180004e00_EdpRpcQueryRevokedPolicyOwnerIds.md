# EdpRpcQueryRevokedPolicyOwnerIds

- ea: `0x180004e00`
- end: `0x180004eb6`
- name: `EdpRpcQueryRevokedPolicyOwnerIds`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004e00`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllQueryRevokedPolicyOwnerIds` at `0x180004e6e`
- `EFSCORE!EdpDllQueryRevokedPolicyOwnerIds` at `0x180004e6e`

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
0x180004e00  push    rbx
0x180004e02  push    rbp
0x180004e03  push    rsi
0x180004e04  push    rdi
0x180004e05  sub     rsp, 0A8h
0x180004e0c  mov     rbp, rdx
0x180004e0f  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004e14  xor     edx, edx; Val
0x180004e16  mov     esi, r8d
0x180004e19  mov     rdi, r9
0x180004e1c  lea     r8d, [rdx+70h]; Size
0x180004e20  call    memset_0
0x180004e25  test    rdi, rdi
0x180004e28  jnz     short loc_180004E31
0x180004e2a  mov     ebx, 80004003h
0x180004e2f  jmp     short loc_180004EA7
0x180004e31  lea     rcx, [rsp+0C8h+var_98]
0x180004e36  call    EdpBeginLocalOnlyRpcCall
0x180004e3b  mov     ebx, eax
0x180004e3d  test    eax, eax
0x180004e3f  jns     short loc_180004E60
0x180004e41  mov     r9d, 6
0x180004e47  mov     [rsp+0C8h+var_A8], 0B0Bh
0x180004e4f  mov     r8d, eax
0x180004e52  lea     rdx, EFS_API_ERROR
0x180004e59  call    fnEfsLogTrace1
0x180004e5e  jmp     short loc_180004EA7
0x180004e60  mov     r9, rdi
0x180004e63  lea     rcx, [rsp+0C8h+var_98]
0x180004e68  mov     r8d, esi
0x180004e6b  mov     rdx, rbp
0x180004e6e  call    cs:__imp_EdpDllQueryRevokedPolicyOwnerIds
0x180004e75  nop     dword ptr [rax+rax+00h]
0x180004e7a  mov     ebx, eax
0x180004e7c  test    eax, eax
0x180004e7e  jns     short loc_180004E9D
0x180004e80  mov     r9d, 6
0x180004e86  mov     [rsp+0C8h+var_A8], 0B16h
0x180004e8e  mov     r8d, eax
0x180004e91  lea     rdx, EFS_API_ERROR
0x180004e98  call    fnEfsLogTrace1
0x180004e9d  lea     rcx, [rsp+0C8h+var_98]
0x180004ea2  call    EdpCleanupLocalOnlyRpcCall
0x180004ea7  mov     eax, ebx
0x180004ea9  add     rsp, 0A8h
0x180004eb0  pop     rdi
0x180004eb1  pop     rsi
0x180004eb2  pop     rbp
0x180004eb3  pop     rbx
0x180004eb4  retn
```
