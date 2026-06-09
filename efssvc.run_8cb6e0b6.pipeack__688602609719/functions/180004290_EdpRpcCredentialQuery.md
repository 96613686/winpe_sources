# EdpRpcCredentialQuery

- ea: `0x180004290`
- end: `0x180004366`
- name: `EdpRpcCredentialQuery`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004290`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllCredentialQuery` at `0x18000431c`
- `EFSCORE!EdpDllCredentialQuery` at `0x18000431c`

## pseudocode

```c
__int64 __fastcall EdpRpcCredentialQuery(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // ebx
  signed int v9; // eax
  __int64 v10; // rcx
  signed int v11; // eax
  __int64 v12; // rcx
  _BYTE v14[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v14, 0, 0x70u);
  if ( a3 )
  {
    if ( a5 )
    {
      v9 = EdpBeginLocalOnlyRpcCall((__int64)v14);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v11 = EdpDllCredentialQuery(v14, a2, a3, a4, a5);
        v8 = v11;
        if ( v11 < 0 )
          fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 63);
        EdpCleanupLocalOnlyRpcCall((__int64)v14);
      }
      else
      {
        fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, v9, 6, 51);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x180004290  push    rbx
0x180004292  push    rbp
0x180004293  push    rsi
0x180004294  push    rdi
0x180004295  push    r14
0x180004297  sub     rsp, 0A0h
0x18000429e  mov     r14, rdx
0x1800042a1  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800042a6  xor     edx, edx; Val
0x1800042a8  mov     rsi, r8
0x1800042ab  mov     rbp, r9
0x1800042ae  lea     r8d, [rdx+70h]; Size
0x1800042b2  call    memset_0
0x1800042b7  test    rsi, rsi
0x1800042ba  jnz     short loc_1800042C6
0x1800042bc  mov     ebx, 80070057h
0x1800042c1  jmp     loc_180004355
0x1800042c6  mov     rdi, [rsp+0C8h+arg_20]
0x1800042ce  test    rdi, rdi
0x1800042d1  jnz     short loc_1800042DA
0x1800042d3  mov     ebx, 80004003h
0x1800042d8  jmp     short loc_180004355
0x1800042da  lea     rcx, [rsp+0C8h+var_98]
0x1800042df  call    EdpBeginLocalOnlyRpcCall
0x1800042e4  mov     ebx, eax
0x1800042e6  test    eax, eax
0x1800042e8  jns     short loc_180004309
0x1800042ea  mov     r9d, 6
0x1800042f0  mov     dword ptr [rsp+0C8h+var_A8], 0A33h
0x1800042f8  mov     r8d, eax
0x1800042fb  lea     rdx, EFS_API_ERROR
0x180004302  call    fnEfsLogTrace1
0x180004307  jmp     short loc_180004355
0x180004309  mov     r9, rbp
0x18000430c  mov     [rsp+0C8h+var_A8], rdi
0x180004311  mov     r8, rsi
0x180004314  lea     rcx, [rsp+0C8h+var_98]
0x180004319  mov     rdx, r14
0x18000431c  call    cs:__imp_EdpDllCredentialQuery
0x180004323  nop     dword ptr [rax+rax+00h]
0x180004328  mov     ebx, eax
0x18000432a  test    eax, eax
0x18000432c  jns     short loc_18000434B
0x18000432e  mov     r9d, 6
0x180004334  mov     dword ptr [rsp+0C8h+var_A8], 0A3Fh
0x18000433c  mov     r8d, eax
0x18000433f  lea     rdx, EFS_API_ERROR
0x180004346  call    fnEfsLogTrace1
0x18000434b  lea     rcx, [rsp+0C8h+var_98]
0x180004350  call    EdpCleanupLocalOnlyRpcCall
0x180004355  mov     eax, ebx
0x180004357  add     rsp, 0A0h
0x18000435e  pop     r14
0x180004360  pop     rdi
0x180004361  pop     rsi
0x180004362  pop     rbp
0x180004363  pop     rbx
0x180004364  retn
```
