# EdpRpcAllowFileAccessForProcess

- ea: `0x180003b80`
- end: `0x180003c29`
- name: `EdpRpcAllowFileAccessForProcess`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180003b80`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllAllowFileAccessForProcess` at `0x180003be8`
- `EFSCORE!EdpDllAllowFileAccessForProcess` at `0x180003be8`

## pseudocode

```c
__int64 __fastcall EdpRpcAllowFileAccessForProcess(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  _BYTE v13[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v13, 0, 0x70u);
  if ( a2 )
  {
    v8 = EdpBeginLocalOnlyRpcCall((__int64)v13);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v10 = EdpDllAllowFileAccessForProcess(a2, a3, a4);
      v7 = v10;
      if ( v10 < 0 )
        fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, v10, 6, 237);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v9, (unsigned int)EFS_API_ERROR, v8, 6, 227);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x180003b80  push    rbx
0x180003b82  push    rbp
0x180003b83  push    rsi
0x180003b84  push    rdi
0x180003b85  sub     rsp, 0A8h
0x180003b8c  mov     rdi, rdx
0x180003b8f  lea     rcx, [rsp+0C8h+var_98]; void *
0x180003b94  xor     edx, edx; Val
0x180003b96  mov     ebp, r8d
0x180003b99  mov     rsi, r9
0x180003b9c  lea     r8d, [rdx+70h]; Size
0x180003ba0  call    memset_0
0x180003ba5  test    rdi, rdi
0x180003ba8  jnz     short loc_180003BB1
0x180003baa  mov     ebx, 80070057h
0x180003baf  jmp     short loc_180003C1B
0x180003bb1  lea     rcx, [rsp+0C8h+var_98]
0x180003bb6  call    EdpBeginLocalOnlyRpcCall
0x180003bbb  mov     ebx, eax
0x180003bbd  test    eax, eax
0x180003bbf  jns     short loc_180003BE0
0x180003bc1  mov     r9d, 6
0x180003bc7  mov     [rsp+0C8h+var_A8], 10E3h
0x180003bcf  mov     r8d, eax
0x180003bd2  lea     rdx, EFS_API_ERROR
0x180003bd9  call    fnEfsLogTrace1
0x180003bde  jmp     short loc_180003C1B
0x180003be0  mov     r8, rsi
0x180003be3  mov     edx, ebp
0x180003be5  mov     rcx, rdi
0x180003be8  call    cs:__imp_EdpDllAllowFileAccessForProcess
0x180003bee  mov     ebx, eax
0x180003bf0  test    eax, eax
0x180003bf2  jns     short loc_180003C11
0x180003bf4  mov     r9d, 6
0x180003bfa  mov     [rsp+0C8h+var_A8], 10EDh
0x180003c02  mov     r8d, eax
0x180003c05  lea     rdx, EFS_API_ERROR
0x180003c0c  call    fnEfsLogTrace1
0x180003c11  lea     rcx, [rsp+0C8h+var_98]
0x180003c16  call    EdpCleanupLocalOnlyRpcCall
0x180003c1b  mov     eax, ebx
0x180003c1d  add     rsp, 0A8h
0x180003c24  pop     rdi
0x180003c25  pop     rsi
0x180003c26  pop     rbp
0x180003c27  pop     rbx
0x180003c28  retn
```
