# EdpRpcCredentialDelete

- ea: `0x180003e50`
- end: `0x180003f19`
- name: `EdpRpcCredentialDelete`
- size: `201`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180003e50`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllCredentialDelete` at `0x180003ed8`
- `EFSCORE!EdpDllCredentialDelete` at `0x180003ed8`

## pseudocode

```c
__int64 __fastcall EdpRpcCredentialDelete(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
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
        fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, v12, 6, 213);
      EdpCleanupLocalOnlyRpcCall((__int64)v15);
    }
    else
    {
      fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, v10, 6, 200);
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
0x180003e50  push    rbx
0x180003e52  push    rbp
0x180003e53  push    rsi
0x180003e54  push    rdi
0x180003e55  sub     rsp, 0A8h
0x180003e5c  mov     edi, edx
0x180003e5e  lea     rcx, [rsp+0C8h+var_98]; void *
0x180003e63  xor     edx, edx; Val
0x180003e65  mov     rbp, r8
0x180003e68  mov     rsi, r9
0x180003e6b  lea     r8d, [rdx+70h]; Size
0x180003e6f  call    memset_0
0x180003e74  test    edi, edi
0x180003e76  jnz     short loc_180003E82
0x180003e78  mov     ebx, 80070057h
0x180003e7d  jmp     loc_180003F0B
0x180003e82  lea     rcx, [rsp+0C8h+var_98]
0x180003e87  call    EdpBeginLocalOnlyRpcCall
0x180003e8c  mov     ebx, eax
0x180003e8e  test    eax, eax
0x180003e90  jns     short loc_180003EB1
0x180003e92  mov     r9d, 6
0x180003e98  mov     dword ptr [rsp+0C8h+var_A8], 0AC8h
0x180003ea0  mov     r8d, eax
0x180003ea3  lea     rdx, EFS_API_ERROR
0x180003eaa  call    fnEfsLogTrace1
0x180003eaf  jmp     short loc_180003F0B
0x180003eb1  mov     rax, [rsp+0C8h+arg_28]
0x180003eb9  lea     rcx, [rsp+0C8h+var_98]
0x180003ebe  mov     [rsp+0C8h+var_A0], rax
0x180003ec3  mov     r9, rsi
0x180003ec6  mov     rax, [rsp+0C8h+arg_20]
0x180003ece  mov     r8, rbp
0x180003ed1  mov     edx, edi
0x180003ed3  mov     [rsp+0C8h+var_A8], rax
0x180003ed8  call    cs:__imp_EdpDllCredentialDelete
0x180003ede  mov     ebx, eax
0x180003ee0  test    eax, eax
0x180003ee2  jns     short loc_180003F01
0x180003ee4  mov     r9d, 6
0x180003eea  mov     dword ptr [rsp+0C8h+var_A8], 0AD5h
0x180003ef2  mov     r8d, eax
0x180003ef5  lea     rdx, EFS_API_ERROR
0x180003efc  call    fnEfsLogTrace1
0x180003f01  lea     rcx, [rsp+0C8h+var_98]
0x180003f06  call    EdpCleanupLocalOnlyRpcCall
0x180003f0b  mov     eax, ebx
0x180003f0d  add     rsp, 0A8h
0x180003f14  pop     rdi
0x180003f15  pop     rsi
0x180003f16  pop     rbp
0x180003f17  pop     rbx
0x180003f18  retn
```
