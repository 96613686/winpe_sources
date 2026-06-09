# EdpRpcCredentialExists

- ea: `0x1800041a0`
- end: `0x180004283`
- name: `EdpRpcCredentialExists`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800041a0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllCredentialExists` at `0x180004232`
- `EFSCORE!EdpDllCredentialExists` at `0x180004232`

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
0x1800041a0  push    rbx
0x1800041a2  push    rbp
0x1800041a3  push    rsi
0x1800041a4  push    rdi
0x1800041a5  push    r14
0x1800041a7  sub     rsp, 0A0h
0x1800041ae  mov     r14, rdx
0x1800041b1  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800041b6  xor     edx, edx; Val
0x1800041b8  mov     rbp, r8
0x1800041bb  mov     rsi, r9
0x1800041be  lea     r8d, [rdx+70h]; Size
0x1800041c2  call    memset_0
0x1800041c7  test    rbp, rbp
0x1800041ca  jz      loc_18000426D
0x1800041d0  test    rsi, rsi
0x1800041d3  jz      loc_18000426D
0x1800041d9  mov     rdi, [rsp+0C8h+arg_20]
0x1800041e1  test    rdi, rdi
0x1800041e4  jnz     short loc_1800041F0
0x1800041e6  mov     ebx, 80004003h
0x1800041eb  jmp     loc_180004272
0x1800041f0  lea     rcx, [rsp+0C8h+var_98]
0x1800041f5  call    EdpBeginLocalOnlyRpcCall
0x1800041fa  mov     ebx, eax
0x1800041fc  test    eax, eax
0x1800041fe  jns     short loc_18000421F
0x180004200  mov     r9d, 6
0x180004206  mov     dword ptr [rsp+0C8h+var_A8], 0A7Dh
0x18000420e  mov     r8d, eax
0x180004211  lea     rdx, EFS_API_ERROR
0x180004218  call    fnEfsLogTrace1
0x18000421d  jmp     short loc_180004272
0x18000421f  mov     r9, rsi
0x180004222  mov     [rsp+0C8h+var_A8], rdi
0x180004227  mov     r8, rbp
0x18000422a  lea     rcx, [rsp+0C8h+var_98]
0x18000422f  mov     rdx, r14
0x180004232  call    cs:__imp_EdpDllCredentialExists
0x180004239  nop     dword ptr [rax+rax+00h]
0x18000423e  mov     ebx, eax
0x180004240  test    eax, eax
0x180004242  jns     short loc_180004261
0x180004244  mov     r9d, 6
0x18000424a  mov     dword ptr [rsp+0C8h+var_A8], 0A89h
0x180004252  mov     r8d, eax
0x180004255  lea     rdx, EFS_API_ERROR
0x18000425c  call    fnEfsLogTrace1
0x180004261  lea     rcx, [rsp+0C8h+var_98]
0x180004266  call    EdpCleanupLocalOnlyRpcCall
0x18000426b  jmp     short loc_180004272
0x18000426d  mov     ebx, 80070057h
0x180004272  mov     eax, ebx
0x180004274  add     rsp, 0A0h
0x18000427b  pop     r14
0x18000427d  pop     rdi
0x18000427e  pop     rsi
0x18000427f  pop     rbp
0x180004280  pop     rbx
0x180004281  retn
```
