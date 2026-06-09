# EfsEnforceClientAuthentication

- ea: `0x18000b308`
- end: `0x18000b3c3`
- name: `EfsEnforceClientAuthentication`
- size: `187`
- prototype: `__int64()`
- caller_count: `23`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800036a0`
- `0x180004980`
- `0x180004bb0`
- `0x180004e20`
- `0x1800051c0`
- `0x1800054b0`
- `0x1800055b0`
- `0x180005850`
- `0x1800058a0`
- `0x180005bc0`
- `0x180005ef0`
- `0x1800063c0`
- `0x1800065a0`
- `0x180006710`
- `0x1800068a0`
- `0x180006a00`
- `0x180006bb0`
- `0x180006d70`
- `0x180006df0`
- `0x180007140`
- `0x180007290`
- `0x180007330`
- `0x1800074d0`

## callees

- `0x180003604`
- `0x18000b308`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000b33c`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000b33c`

## pseudocode

```c
__int64 EfsEnforceClientAuthentication()
{
  RPC_STATUS v0; // eax
  int v1; // ecx
  unsigned int v2; // ebx
  unsigned int v4; // [rsp+40h] [rbp+8h] BYREF
  RPC_AUTHZ_HANDLE v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  v4 = 0;
  v0 = RpcBindingInqAuthClientW(0, &v5, 0, &v4, 0, 0);
  if ( v0 )
  {
    if ( !dword_180017888 )
    {
      fnEfsLogTrace1(v1, (unsigned int)EFS_CLI_AUTH_INSECURE, v0, 21, 42);
      dword_180017888 = 1;
    }
    return 5;
  }
  else if ( v4 == 6 )
  {
    return 0;
  }
  else
  {
    v2 = 5;
    if ( !dword_180017888 )
    {
      fnEfsLogTrace1(v1, (unsigned int)EFS_CLI_AUTH_INSECURE, 5, 21, 42);
      dword_180017888 = 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000b308  mov     rax, rsp
0x18000b30b  push    rbx
0x18000b30c  sub     rsp, 30h
0x18000b310  mov     qword ptr [rax-10h], 0
0x18000b318  lea     r9, [rax+8]; AuthnLevel
0x18000b31c  xor     r8d, r8d; ServerPrincName
0x18000b31f  mov     qword ptr [rax-18h], 0
0x18000b327  lea     rdx, [rax+10h]; Privs
0x18000b32b  mov     qword ptr [rax+10h], 0
0x18000b333  xor     ecx, ecx; ClientBinding
0x18000b335  mov     dword ptr [rax+8], 0
0x18000b33c  call    cs:__imp_RpcBindingInqAuthClientW
0x18000b342  test    eax, eax
0x18000b344  jz      short loc_18000B37D
0x18000b346  cmp     cs:dword_180017888, 0
0x18000b34d  jnz     short loc_18000B376
0x18000b34f  mov     r9d, 15h
0x18000b355  mov     [rsp+38h+var_18], 62Ah
0x18000b35d  mov     r8d, eax
0x18000b360  lea     rdx, EFS_CLI_AUTH_INSECURE
0x18000b367  call    fnEfsLogTrace1
0x18000b36c  mov     cs:dword_180017888, 1
0x18000b376  mov     ebx, 5
0x18000b37b  jmp     short loc_18000B3BB
0x18000b37d  cmp     [rsp+38h+arg_0], 6
0x18000b382  jz      short loc_18000B3B9
0x18000b384  cmp     cs:dword_180017888, 0
0x18000b38b  mov     ebx, 5
0x18000b390  jnz     short loc_18000B3BB
0x18000b392  lea     r9d, [rbx+10h]
0x18000b396  mov     [rsp+38h+var_18], 62Ah
0x18000b39e  mov     r8d, ebx
0x18000b3a1  lea     rdx, EFS_CLI_AUTH_INSECURE
0x18000b3a8  call    fnEfsLogTrace1
0x18000b3ad  mov     cs:dword_180017888, 1
0x18000b3b7  jmp     short loc_18000B3BB
0x18000b3b9  xor     ebx, ebx
0x18000b3bb  mov     eax, ebx
0x18000b3bd  add     rsp, 30h
0x18000b3c1  pop     rbx
0x18000b3c2  retn
```
