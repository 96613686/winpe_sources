# EdpRpcDplUserCredentialsSet

- ea: `0x1800040f0`
- end: `0x1800041c1`
- name: `EdpRpcDplUserCredentialsSet`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x1800040f0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllDplUserCredentialsSet` at `0x180004179`
- `EFSCORE!EdpDllDplUserCredentialsSet` at `0x180004179`

## pseudocode

```c
__int64 __fastcall EdpRpcDplUserCredentialsSet(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  signed int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  signed int v11; // eax
  __int64 v12; // rcx
  _BYTE v14[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v14, 0, 0x70u);
  if ( a2 && a3 && a4 - 1 <= 3 )
  {
    v8 = EdpBeginLocalOnlyRpcCall((__int64)v14);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v11 = EdpDllDplUserCredentialsSet(v14, a2, a3, a4, a5);
      v10 = v11;
      if ( v11 < 0 )
        fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 154);
      EdpCleanupLocalOnlyRpcCall((__int64)v14);
    }
    else
    {
      fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v8, 6, 142);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x1800040f0  push    rbx
0x1800040f2  push    rbp
0x1800040f3  push    rsi
0x1800040f4  push    rdi
0x1800040f5  sub     rsp, 0A8h
0x1800040fc  mov     rbp, rdx
0x1800040ff  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004104  xor     edx, edx; Val
0x180004106  mov     rdi, r8
0x180004109  mov     esi, r9d
0x18000410c  lea     r8d, [rdx+70h]; Size
0x180004110  call    memset_0
0x180004115  test    rbp, rbp
0x180004118  jz      loc_1800041AE
0x18000411e  test    rdi, rdi
0x180004121  jz      loc_1800041AE
0x180004127  lea     eax, [rsi-1]
0x18000412a  cmp     eax, 3
0x18000412d  ja      short loc_1800041AE
0x18000412f  lea     rcx, [rsp+0C8h+var_98]
0x180004134  call    EdpBeginLocalOnlyRpcCall
0x180004139  mov     ebx, eax
0x18000413b  test    eax, eax
0x18000413d  jns     short loc_18000415E
0x18000413f  mov     r9d, 6
0x180004145  mov     dword ptr [rsp+0C8h+var_A8], 0D8Eh
0x18000414d  mov     r8d, eax
0x180004150  lea     rdx, EFS_API_ERROR
0x180004157  call    fnEfsLogTrace1
0x18000415c  jmp     short loc_1800041B3
0x18000415e  mov     rax, [rsp+0C8h+arg_20]
0x180004166  lea     rcx, [rsp+0C8h+var_98]
0x18000416b  mov     r9d, esi
0x18000416e  mov     [rsp+0C8h+var_A8], rax
0x180004173  mov     r8, rdi
0x180004176  mov     rdx, rbp
0x180004179  call    cs:__imp_EdpDllDplUserCredentialsSet
0x18000417f  mov     ebx, eax
0x180004181  test    eax, eax
0x180004183  jns     short loc_1800041A2
0x180004185  mov     r9d, 6
0x18000418b  mov     dword ptr [rsp+0C8h+var_A8], 0D9Ah
0x180004193  mov     r8d, eax
0x180004196  lea     rdx, EFS_API_ERROR
0x18000419d  call    fnEfsLogTrace1
0x1800041a2  lea     rcx, [rsp+0C8h+var_98]
0x1800041a7  call    EdpCleanupLocalOnlyRpcCall
0x1800041ac  jmp     short loc_1800041B3
0x1800041ae  mov     ebx, 80070057h
0x1800041b3  mov     eax, ebx
0x1800041b5  add     rsp, 0A8h
0x1800041bc  pop     rdi
0x1800041bd  pop     rsi
0x1800041be  pop     rbp
0x1800041bf  pop     rbx
0x1800041c0  retn
```
