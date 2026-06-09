# EdpRpcCredentialQuery

- ea: `0x180004000`
- end: `0x1800040cf`
- name: `EdpRpcCredentialQuery`
- size: `207`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004000`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllCredentialQuery` at `0x18000408c`
- `EFSCORE!EdpDllCredentialQuery` at `0x18000408c`

## pseudocode

```c
__int64 __fastcall EdpRpcCredentialQuery(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
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
          fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 63);
        EdpCleanupLocalOnlyRpcCall((__int64)v14);
      }
      else
      {
        fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 51);
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
0x180004000  push    rbx
0x180004002  push    rbp
0x180004003  push    rsi
0x180004004  push    rdi
0x180004005  push    r14
0x180004007  sub     rsp, 0A0h
0x18000400e  mov     r14, rdx
0x180004011  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004016  xor     edx, edx; Val
0x180004018  mov     rsi, r8
0x18000401b  mov     rbp, r9
0x18000401e  lea     r8d, [rdx+70h]; Size
0x180004022  call    memset_0
0x180004027  test    rsi, rsi
0x18000402a  jnz     short loc_180004036
0x18000402c  mov     ebx, 80070057h
0x180004031  jmp     loc_1800040BF
0x180004036  mov     rdi, [rsp+0C8h+arg_20]
0x18000403e  test    rdi, rdi
0x180004041  jnz     short loc_18000404A
0x180004043  mov     ebx, 80004003h
0x180004048  jmp     short loc_1800040BF
0x18000404a  lea     rcx, [rsp+0C8h+var_98]
0x18000404f  call    EdpBeginLocalOnlyRpcCall
0x180004054  mov     ebx, eax
0x180004056  test    eax, eax
0x180004058  jns     short loc_180004079
0x18000405a  mov     r9d, 6
0x180004060  mov     dword ptr [rsp+0C8h+var_A8], 0A33h
0x180004068  mov     r8d, eax
0x18000406b  lea     rdx, EFS_API_ERROR
0x180004072  call    fnEfsLogTrace1
0x180004077  jmp     short loc_1800040BF
0x180004079  mov     r9, rbp
0x18000407c  mov     [rsp+0C8h+var_A8], rdi
0x180004081  mov     r8, rsi
0x180004084  lea     rcx, [rsp+0C8h+var_98]
0x180004089  mov     rdx, r14
0x18000408c  call    cs:__imp_EdpDllCredentialQuery
0x180004092  mov     ebx, eax
0x180004094  test    eax, eax
0x180004096  jns     short loc_1800040B5
0x180004098  mov     r9d, 6
0x18000409e  mov     dword ptr [rsp+0C8h+var_A8], 0A3Fh
0x1800040a6  mov     r8d, eax
0x1800040a9  lea     rdx, EFS_API_ERROR
0x1800040b0  call    fnEfsLogTrace1
0x1800040b5  lea     rcx, [rsp+0C8h+var_98]
0x1800040ba  call    EdpCleanupLocalOnlyRpcCall
0x1800040bf  mov     eax, ebx
0x1800040c1  add     rsp, 0A0h
0x1800040c8  pop     r14
0x1800040ca  pop     rdi
0x1800040cb  pop     rsi
0x1800040cc  pop     rbp
0x1800040cd  pop     rbx
0x1800040ce  retn
```
