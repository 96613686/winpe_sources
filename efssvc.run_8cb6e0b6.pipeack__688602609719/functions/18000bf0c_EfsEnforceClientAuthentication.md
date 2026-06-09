# EfsEnforceClientAuthentication

- ea: `0x18000bf0c`
- end: `0x18000bfce`
- name: `EfsEnforceClientAuthentication`
- size: `194`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003864`
- `0x180004c70`
- `0x180004ec0`
- `0x180005180`
- `0x180005550`
- `0x1800058a0`
- `0x1800059a0`
- `0x180005cb0`
- `0x180005d00`
- `0x1800060c0`
- `0x180006460`
- `0x1800069d0`
- `0x180006bf0`
- `0x180006d80`
- `0x180006f40`
- `0x1800070d0`
- `0x1800072b0`
- `0x1800074a0`
- `0x180007530`
- `0x1800078e0`
- `0x180007a70`
- `0x180007b30`
- `0x180007d10`

## callees

- `0x1800037b8`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000bf40`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000bf40`

## pseudocode

```c
__int64 EfsEnforceClientAuthentication()
{
  RPC_STATUS v0; // eax
  __int64 v1; // rcx
  unsigned int v2; // ebx
  unsigned int v4; // [rsp+40h] [rbp+8h] BYREF
  RPC_AUTHZ_HANDLE v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  v4 = 0;
  v0 = RpcBindingInqAuthClientW(0, &v5, 0, &v4, 0, 0);
  if ( v0 )
  {
    if ( !dword_180018888 )
    {
      fnEfsLogTrace1(v1, (__int64)EFS_CLI_AUTH_INSECURE, v0, 21, 42);
      dword_180018888 = 1;
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
    if ( !dword_180018888 )
    {
      fnEfsLogTrace1(v1, (__int64)EFS_CLI_AUTH_INSECURE, 5u, 21, 42);
      dword_180018888 = 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000bf0c  mov     rax, rsp
0x18000bf0f  push    rbx
0x18000bf10  sub     rsp, 30h
0x18000bf14  mov     qword ptr [rax-10h], 0
0x18000bf1c  lea     r9, [rax+8]; AuthnLevel
0x18000bf20  xor     r8d, r8d; ServerPrincName
0x18000bf23  mov     qword ptr [rax-18h], 0
0x18000bf2b  lea     rdx, [rax+10h]; Privs
0x18000bf2f  mov     qword ptr [rax+10h], 0
0x18000bf37  xor     ecx, ecx; ClientBinding
0x18000bf39  mov     dword ptr [rax+8], 0
0x18000bf40  call    cs:__imp_RpcBindingInqAuthClientW
0x18000bf47  nop     dword ptr [rax+rax+00h]
0x18000bf4c  test    eax, eax
0x18000bf4e  jz      short loc_18000BF87
0x18000bf50  cmp     cs:dword_180018888, 0
0x18000bf57  jnz     short loc_18000BF80
0x18000bf59  mov     r9d, 15h
0x18000bf5f  mov     [rsp+38h+var_18], 62Ah
0x18000bf67  mov     r8d, eax
0x18000bf6a  lea     rdx, EFS_CLI_AUTH_INSECURE
0x18000bf71  call    fnEfsLogTrace1
0x18000bf76  mov     cs:dword_180018888, 1
0x18000bf80  mov     ebx, 5
0x18000bf85  jmp     short loc_18000BFC5
0x18000bf87  cmp     [rsp+38h+arg_0], 6
0x18000bf8c  jz      short loc_18000BFC3
0x18000bf8e  cmp     cs:dword_180018888, 0
0x18000bf95  mov     ebx, 5
0x18000bf9a  jnz     short loc_18000BFC5
0x18000bf9c  lea     r9d, [rbx+10h]
0x18000bfa0  mov     [rsp+38h+var_18], 62Ah
0x18000bfa8  mov     r8d, ebx
0x18000bfab  lea     rdx, EFS_CLI_AUTH_INSECURE
0x18000bfb2  call    fnEfsLogTrace1
0x18000bfb7  mov     cs:dword_180018888, 1
0x18000bfc1  jmp     short loc_18000BFC5
0x18000bfc3  xor     ebx, ebx
0x18000bfc5  mov     eax, ebx
0x18000bfc7  add     rsp, 30h
0x18000bfcb  pop     rbx
0x18000bfcc  retn
```
