# EdpRpcCredentialCreate

- ea: `0x180003fe0`
- end: `0x1800040b6`
- name: `EdpRpcCredentialCreate`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180003fe0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllCredentialCreate` at `0x18000406c`
- `EFSCORE!EdpDllCredentialCreate` at `0x18000406c`

## pseudocode

```c
__int64 __fastcall EdpRpcCredentialCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
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
        v11 = EdpDllCredentialCreate(v14, a2, a3, a4, a5);
        v8 = v11;
        if ( v11 < 0 )
          fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 250);
        EdpCleanupLocalOnlyRpcCall((__int64)v14);
      }
      else
      {
        fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 238);
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
0x180003fe0  push    rbx
0x180003fe2  push    rbp
0x180003fe3  push    rsi
0x180003fe4  push    rdi
0x180003fe5  push    r14
0x180003fe7  sub     rsp, 0A0h
0x180003fee  mov     r14, rdx
0x180003ff1  lea     rcx, [rsp+0C8h+var_98]; void *
0x180003ff6  xor     edx, edx; Val
0x180003ff8  mov     rsi, r8
0x180003ffb  mov     rbp, r9
0x180003ffe  lea     r8d, [rdx+70h]; Size
0x180004002  call    memset_0
0x180004007  test    rsi, rsi
0x18000400a  jnz     short loc_180004016
0x18000400c  mov     ebx, 80070057h
0x180004011  jmp     loc_1800040A5
0x180004016  mov     rdi, [rsp+0C8h+arg_20]
0x18000401e  test    rdi, rdi
0x180004021  jnz     short loc_18000402A
0x180004023  mov     ebx, 80004003h
0x180004028  jmp     short loc_1800040A5
0x18000402a  lea     rcx, [rsp+0C8h+var_98]
0x18000402f  call    EdpBeginLocalOnlyRpcCall
0x180004034  mov     ebx, eax
0x180004036  test    eax, eax
0x180004038  jns     short loc_180004059
0x18000403a  mov     r9d, 6
0x180004040  mov     dword ptr [rsp+0C8h+var_A8], 9EEh
0x180004048  mov     r8d, eax
0x18000404b  lea     rdx, EFS_API_ERROR
0x180004052  call    fnEfsLogTrace1
0x180004057  jmp     short loc_1800040A5
0x180004059  mov     r9, rbp
0x18000405c  mov     [rsp+0C8h+var_A8], rdi
0x180004061  mov     r8, rsi
0x180004064  lea     rcx, [rsp+0C8h+var_98]
0x180004069  mov     rdx, r14
0x18000406c  call    cs:__imp_EdpDllCredentialCreate
0x180004073  nop     dword ptr [rax+rax+00h]
0x180004078  mov     ebx, eax
0x18000407a  test    eax, eax
0x18000407c  jns     short loc_18000409B
0x18000407e  mov     r9d, 6
0x180004084  mov     dword ptr [rsp+0C8h+var_A8], 9FAh
0x18000408c  mov     r8d, eax
0x18000408f  lea     rdx, EFS_API_ERROR
0x180004096  call    fnEfsLogTrace1
0x18000409b  lea     rcx, [rsp+0C8h+var_98]
0x1800040a0  call    EdpCleanupLocalOnlyRpcCall
0x1800040a5  mov     eax, ebx
0x1800040a7  add     rsp, 0A0h
0x1800040ae  pop     r14
0x1800040b0  pop     rdi
0x1800040b1  pop     rsi
0x1800040b2  pop     rbp
0x1800040b3  pop     rbx
0x1800040b4  retn
```
