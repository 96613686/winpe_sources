# EdpRpcQueryDplEnforcedPolicyOwnerIds

- ea: `0x180004d30`
- end: `0x180004def`
- name: `EdpRpcQueryDplEnforcedPolicyOwnerIds`
- size: `191`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004d30`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllQueryDplEnforcedPolicyOwnerIds` at `0x180004d9e`
- `EFSCORE!EdpDllQueryDplEnforcedPolicyOwnerIds` at `0x180004d9e`

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
0x180004d30  mov     [rsp+arg_0], rbx
0x180004d35  mov     [rsp+arg_8], rsi
0x180004d3a  push    rdi
0x180004d3b  sub     rsp, 0A0h
0x180004d42  mov     rsi, rdx
0x180004d45  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004d4a  xor     edx, edx; Val
0x180004d4c  mov     rdi, r8
0x180004d4f  lea     r8d, [rdx+70h]; Size
0x180004d53  call    memset_0
0x180004d58  test    rdi, rdi
0x180004d5b  jnz     short loc_180004D64
0x180004d5d  mov     ebx, 80004003h
0x180004d62  jmp     short loc_180004DD7
0x180004d64  lea     rcx, [rsp+0A8h+var_78]
0x180004d69  call    EdpBeginLocalOnlyRpcCall
0x180004d6e  mov     ebx, eax
0x180004d70  test    eax, eax
0x180004d72  jns     short loc_180004D93
0x180004d74  mov     r9d, 6
0x180004d7a  mov     [rsp+0A8h+var_88], 0B49h
0x180004d82  mov     r8d, eax
0x180004d85  lea     rdx, EFS_API_ERROR
0x180004d8c  call    fnEfsLogTrace1
0x180004d91  jmp     short loc_180004DD7
0x180004d93  mov     r8, rdi
0x180004d96  lea     rcx, [rsp+0A8h+var_78]
0x180004d9b  mov     rdx, rsi
0x180004d9e  call    cs:__imp_EdpDllQueryDplEnforcedPolicyOwnerIds
0x180004da5  nop     dword ptr [rax+rax+00h]
0x180004daa  mov     ebx, eax
0x180004dac  test    eax, eax
0x180004dae  jns     short loc_180004DCD
0x180004db0  mov     r9d, 6
0x180004db6  mov     [rsp+0A8h+var_88], 0B53h
0x180004dbe  mov     r8d, eax
0x180004dc1  lea     rdx, EFS_API_ERROR
0x180004dc8  call    fnEfsLogTrace1
0x180004dcd  lea     rcx, [rsp+0A8h+var_78]
0x180004dd2  call    EdpCleanupLocalOnlyRpcCall
0x180004dd7  lea     r11, [rsp+0A8h+var_8]
0x180004ddf  mov     eax, ebx
0x180004de1  mov     rbx, [r11+10h]
0x180004de5  mov     rsi, [r11+18h]
0x180004de9  mov     rsp, r11
0x180004dec  pop     rdi
0x180004ded  retn
```
