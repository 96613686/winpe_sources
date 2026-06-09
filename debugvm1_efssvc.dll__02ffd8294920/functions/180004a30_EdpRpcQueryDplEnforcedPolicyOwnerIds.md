# EdpRpcQueryDplEnforcedPolicyOwnerIds

- ea: `0x180004a30`
- end: `0x180004ae8`
- name: `EdpRpcQueryDplEnforcedPolicyOwnerIds`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004a30`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllQueryDplEnforcedPolicyOwnerIds` at `0x180004a9e`
- `EFSCORE!EdpDllQueryDplEnforcedPolicyOwnerIds` at `0x180004a9e`

## pseudocode

```c
__int64 __fastcall EdpRpcQueryDplEnforcedPolicyOwnerIds(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  signed int v6; // eax
  __int64 v7; // rcx
  signed int DplEnforcedPolicyOwnerIds; // eax
  __int64 v9; // rcx
  _BYTE v11[112]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v11, 0, sizeof(v11));
  if ( a3 )
  {
    v6 = EdpBeginLocalOnlyRpcCall((__int64)v11);
    v5 = v6;
    if ( v6 >= 0 )
    {
      DplEnforcedPolicyOwnerIds = EdpDllQueryDplEnforcedPolicyOwnerIds(v11, a2, a3);
      v5 = DplEnforcedPolicyOwnerIds;
      if ( DplEnforcedPolicyOwnerIds < 0 )
        fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, DplEnforcedPolicyOwnerIds, 6, 83);
      EdpCleanupLocalOnlyRpcCall((__int64)v11);
    }
    else
    {
      fnEfsLogTrace1(v7, (__int64)EFS_API_ERROR, v6, 6, 73);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x180004a30  mov     [rsp+arg_0], rbx
0x180004a35  mov     [rsp+arg_8], rsi
0x180004a3a  push    rdi
0x180004a3b  sub     rsp, 0A0h
0x180004a42  mov     rsi, rdx
0x180004a45  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004a4a  xor     edx, edx; Val
0x180004a4c  mov     rdi, r8
0x180004a4f  lea     r8d, [rdx+70h]; Size
0x180004a53  call    memset_0
0x180004a58  test    rdi, rdi
0x180004a5b  jnz     short loc_180004A64
0x180004a5d  mov     ebx, 80004003h
0x180004a62  jmp     short loc_180004AD1
0x180004a64  lea     rcx, [rsp+0A8h+var_78]
0x180004a69  call    EdpBeginLocalOnlyRpcCall
0x180004a6e  mov     ebx, eax
0x180004a70  test    eax, eax
0x180004a72  jns     short loc_180004A93
0x180004a74  mov     r9d, 6
0x180004a7a  mov     [rsp+0A8h+var_88], 0B49h
0x180004a82  mov     r8d, eax
0x180004a85  lea     rdx, EFS_API_ERROR
0x180004a8c  call    fnEfsLogTrace1
0x180004a91  jmp     short loc_180004AD1
0x180004a93  mov     r8, rdi
0x180004a96  lea     rcx, [rsp+0A8h+var_78]
0x180004a9b  mov     rdx, rsi
0x180004a9e  call    cs:__imp_EdpDllQueryDplEnforcedPolicyOwnerIds
0x180004aa4  mov     ebx, eax
0x180004aa6  test    eax, eax
0x180004aa8  jns     short loc_180004AC7
0x180004aaa  mov     r9d, 6
0x180004ab0  mov     [rsp+0A8h+var_88], 0B53h
0x180004ab8  mov     r8d, eax
0x180004abb  lea     rdx, EFS_API_ERROR
0x180004ac2  call    fnEfsLogTrace1
0x180004ac7  lea     rcx, [rsp+0A8h+var_78]
0x180004acc  call    EdpCleanupLocalOnlyRpcCall
0x180004ad1  lea     r11, [rsp+0A8h+var_8]
0x180004ad9  mov     eax, ebx
0x180004adb  mov     rbx, [r11+10h]
0x180004adf  mov     rsi, [r11+18h]
0x180004ae3  mov     rsp, r11
0x180004ae6  pop     rdi
0x180004ae7  retn
```
