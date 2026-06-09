# EdpRpcCredentialExists

- ea: `0x180003f20`
- end: `0x180003ff9`
- name: `EdpRpcCredentialExists`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180003f20`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllCredentialExists` at `0x180003faf`
- `EFSCORE!EdpDllCredentialExists` at `0x180003faf`

## pseudocode

```c
__int64 __fastcall EdpRpcCredentialExists(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // ebx
  signed int v9; // eax
  __int64 v10; // rcx
  signed int v11; // eax
  __int64 v12; // rcx
  _BYTE v14[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v14, 0, 0x70u);
  if ( a3 && a4 )
  {
    if ( a5 )
    {
      v9 = EdpBeginLocalOnlyRpcCall((__int64)v14);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v11 = EdpDllCredentialExists(v14, a2, a3, a4, a5);
        v8 = v11;
        if ( v11 < 0 )
          fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 137);
        EdpCleanupLocalOnlyRpcCall((__int64)v14);
      }
      else
      {
        fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, v9, 6, 125);
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
0x180003f20  push    rbx
0x180003f22  push    rbp
0x180003f23  push    rsi
0x180003f24  push    rdi
0x180003f25  push    r14
0x180003f27  sub     rsp, 0A0h
0x180003f2e  mov     r14, rdx
0x180003f31  lea     rcx, [rsp+0C8h+var_98]; void *
0x180003f36  xor     edx, edx; Val
0x180003f38  mov     rbp, r8
0x180003f3b  mov     rsi, r9
0x180003f3e  lea     r8d, [rdx+70h]; Size
0x180003f42  call    memset_0
0x180003f47  test    rbp, rbp
0x180003f4a  jz      loc_180003FE4
0x180003f50  test    rsi, rsi
0x180003f53  jz      loc_180003FE4
0x180003f59  mov     rdi, [rsp+0C8h+arg_20]
0x180003f61  test    rdi, rdi
0x180003f64  jnz     short loc_180003F6D
0x180003f66  mov     ebx, 80004003h
0x180003f6b  jmp     short loc_180003FE9
0x180003f6d  lea     rcx, [rsp+0C8h+var_98]
0x180003f72  call    EdpBeginLocalOnlyRpcCall
0x180003f77  mov     ebx, eax
0x180003f79  test    eax, eax
0x180003f7b  jns     short loc_180003F9C
0x180003f7d  mov     r9d, 6
0x180003f83  mov     dword ptr [rsp+0C8h+var_A8], 0A7Dh
0x180003f8b  mov     r8d, eax
0x180003f8e  lea     rdx, EFS_API_ERROR
0x180003f95  call    fnEfsLogTrace1
0x180003f9a  jmp     short loc_180003FE9
0x180003f9c  mov     r9, rsi
0x180003f9f  mov     [rsp+0C8h+var_A8], rdi
0x180003fa4  mov     r8, rbp
0x180003fa7  lea     rcx, [rsp+0C8h+var_98]
0x180003fac  mov     rdx, r14
0x180003faf  call    cs:__imp_EdpDllCredentialExists
0x180003fb5  mov     ebx, eax
0x180003fb7  test    eax, eax
0x180003fb9  jns     short loc_180003FD8
0x180003fbb  mov     r9d, 6
0x180003fc1  mov     dword ptr [rsp+0C8h+var_A8], 0A89h
0x180003fc9  mov     r8d, eax
0x180003fcc  lea     rdx, EFS_API_ERROR
0x180003fd3  call    fnEfsLogTrace1
0x180003fd8  lea     rcx, [rsp+0C8h+var_98]
0x180003fdd  call    EdpCleanupLocalOnlyRpcCall
0x180003fe2  jmp     short loc_180003FE9
0x180003fe4  mov     ebx, 80070057h
0x180003fe9  mov     eax, ebx
0x180003feb  add     rsp, 0A0h
0x180003ff2  pop     r14
0x180003ff4  pop     rdi
0x180003ff5  pop     rsi
0x180003ff6  pop     rbp
0x180003ff7  pop     rbx
0x180003ff8  retn
```
