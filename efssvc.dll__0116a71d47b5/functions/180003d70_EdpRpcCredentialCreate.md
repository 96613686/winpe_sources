# EdpRpcCredentialCreate

- ea: `0x180003d70`
- end: `0x180003e3f`
- name: `EdpRpcCredentialCreate`
- size: `207`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180003d70`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllCredentialCreate` at `0x180003dfc`
- `EFSCORE!EdpDllCredentialCreate` at `0x180003dfc`

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
0x180003d70  push    rbx
0x180003d72  push    rbp
0x180003d73  push    rsi
0x180003d74  push    rdi
0x180003d75  push    r14
0x180003d77  sub     rsp, 0A0h
0x180003d7e  mov     r14, rdx
0x180003d81  lea     rcx, [rsp+0C8h+var_98]; void *
0x180003d86  xor     edx, edx; Val
0x180003d88  mov     rsi, r8
0x180003d8b  mov     rbp, r9
0x180003d8e  lea     r8d, [rdx+70h]; Size
0x180003d92  call    memset_0
0x180003d97  test    rsi, rsi
0x180003d9a  jnz     short loc_180003DA6
0x180003d9c  mov     ebx, 80070057h
0x180003da1  jmp     loc_180003E2F
0x180003da6  mov     rdi, [rsp+0C8h+arg_20]
0x180003dae  test    rdi, rdi
0x180003db1  jnz     short loc_180003DBA
0x180003db3  mov     ebx, 80004003h
0x180003db8  jmp     short loc_180003E2F
0x180003dba  lea     rcx, [rsp+0C8h+var_98]
0x180003dbf  call    EdpBeginLocalOnlyRpcCall
0x180003dc4  mov     ebx, eax
0x180003dc6  test    eax, eax
0x180003dc8  jns     short loc_180003DE9
0x180003dca  mov     r9d, 6
0x180003dd0  mov     dword ptr [rsp+0C8h+var_A8], 9EEh
0x180003dd8  mov     r8d, eax
0x180003ddb  lea     rdx, EFS_API_ERROR
0x180003de2  call    fnEfsLogTrace1
0x180003de7  jmp     short loc_180003E2F
0x180003de9  mov     r9, rbp
0x180003dec  mov     [rsp+0C8h+var_A8], rdi
0x180003df1  mov     r8, rsi
0x180003df4  lea     rcx, [rsp+0C8h+var_98]
0x180003df9  mov     rdx, r14
0x180003dfc  call    cs:__imp_EdpDllCredentialCreate
0x180003e02  mov     ebx, eax
0x180003e04  test    eax, eax
0x180003e06  jns     short loc_180003E25
0x180003e08  mov     r9d, 6
0x180003e0e  mov     dword ptr [rsp+0C8h+var_A8], 9FAh
0x180003e16  mov     r8d, eax
0x180003e19  lea     rdx, EFS_API_ERROR
0x180003e20  call    fnEfsLogTrace1
0x180003e25  lea     rcx, [rsp+0C8h+var_98]
0x180003e2a  call    EdpCleanupLocalOnlyRpcCall
0x180003e2f  mov     eax, ebx
0x180003e31  add     rsp, 0A0h
0x180003e38  pop     r14
0x180003e3a  pop     rdi
0x180003e3b  pop     rsi
0x180003e3c  pop     rbp
0x180003e3d  pop     rbx
0x180003e3e  retn
```
