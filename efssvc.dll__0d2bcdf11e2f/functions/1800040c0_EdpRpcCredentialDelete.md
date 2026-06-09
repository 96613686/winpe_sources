# EdpRpcCredentialDelete

- ea: `0x1800040c0`
- end: `0x180004190`
- name: `EdpRpcCredentialDelete`
- size: `208`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800040c0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllCredentialDelete` at `0x180004148`
- `EFSCORE!EdpDllCredentialDelete` at `0x180004148`

## pseudocode

```c
__int64 __fastcall EdpRpcCredentialDelete(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  unsigned int v9; // ebx
  signed int v10; // eax
  __int64 v11; // rcx
  signed int v12; // eax
  __int64 v13; // rcx
  _BYTE v15[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v15, 0, 0x70u);
  if ( a2 )
  {
    v10 = EdpBeginLocalOnlyRpcCall((__int64)v15);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v12 = EdpDllCredentialDelete(v15, a2, a3, a4, a5, a6);
      v9 = v12;
      if ( v12 < 0 )
        fnEfsLogTrace1(v13, (__int64)EFS_API_ERROR, v12, 6, 213);
      EdpCleanupLocalOnlyRpcCall((__int64)v15);
    }
    else
    {
      fnEfsLogTrace1(v11, (__int64)EFS_API_ERROR, v10, 6, 200);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x1800040c0  push    rbx
0x1800040c2  push    rbp
0x1800040c3  push    rsi
0x1800040c4  push    rdi
0x1800040c5  sub     rsp, 0A8h
0x1800040cc  mov     edi, edx
0x1800040ce  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800040d3  xor     edx, edx; Val
0x1800040d5  mov     rbp, r8
0x1800040d8  mov     rsi, r9
0x1800040db  lea     r8d, [rdx+70h]; Size
0x1800040df  call    memset_0
0x1800040e4  test    edi, edi
0x1800040e6  jnz     short loc_1800040F2
0x1800040e8  mov     ebx, 80070057h
0x1800040ed  jmp     loc_180004181
0x1800040f2  lea     rcx, [rsp+0C8h+var_98]
0x1800040f7  call    EdpBeginLocalOnlyRpcCall
0x1800040fc  mov     ebx, eax
0x1800040fe  test    eax, eax
0x180004100  jns     short loc_180004121
0x180004102  mov     r9d, 6
0x180004108  mov     dword ptr [rsp+0C8h+var_A8], 0AC8h
0x180004110  mov     r8d, eax
0x180004113  lea     rdx, EFS_API_ERROR
0x18000411a  call    fnEfsLogTrace1
0x18000411f  jmp     short loc_180004181
0x180004121  mov     rax, [rsp+0C8h+arg_28]
0x180004129  lea     rcx, [rsp+0C8h+var_98]
0x18000412e  mov     [rsp+0C8h+var_A0], rax
0x180004133  mov     r9, rsi
0x180004136  mov     rax, [rsp+0C8h+arg_20]
0x18000413e  mov     r8, rbp
0x180004141  mov     edx, edi
0x180004143  mov     [rsp+0C8h+var_A8], rax
0x180004148  call    cs:__imp_EdpDllCredentialDelete
0x18000414f  nop     dword ptr [rax+rax+00h]
0x180004154  mov     ebx, eax
0x180004156  test    eax, eax
0x180004158  jns     short loc_180004177
0x18000415a  mov     r9d, 6
0x180004160  mov     dword ptr [rsp+0C8h+var_A8], 0AD5h
0x180004168  mov     r8d, eax
0x18000416b  lea     rdx, EFS_API_ERROR
0x180004172  call    fnEfsLogTrace1
0x180004177  lea     rcx, [rsp+0C8h+var_98]
0x18000417c  call    EdpCleanupLocalOnlyRpcCall
0x180004181  mov     eax, ebx
0x180004183  add     rsp, 0A8h
0x18000418a  pop     rdi
0x18000418b  pop     rsi
0x18000418c  pop     rbp
0x18000418d  pop     rbx
0x18000418e  retn
```
