# EdpRpcDplUserUnlockStart

- ea: `0x180004290`
- end: `0x180004369`
- name: `EdpRpcDplUserUnlockStart`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004290`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockStart` at `0x18000431f`
- `EFSCORE!EdpDllDplUserUnlockStart` at `0x18000431f`

## pseudocode

```c
__int64 __fastcall EdpRpcDplUserUnlockStart(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // ebx
  signed int v9; // eax
  __int64 v10; // rcx
  signed int v11; // eax
  __int64 v12; // rcx
  _BYTE v14[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v14, 0, 0x70u);
  if ( a2 && a3 )
  {
    if ( a5 )
    {
      v9 = EdpBeginLocalOnlyRpcCall((__int64)v14);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v11 = EdpDllDplUserUnlockStart(v14, a2, a3, a4, a5);
        v8 = v11;
        if ( v11 < 0 )
          fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 234);
        EdpCleanupLocalOnlyRpcCall((__int64)v14);
      }
      else
      {
        fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, v9, 6, 222);
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
0x18000429e  mov     rbp, rdx
0x1800042a1  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800042a6  xor     edx, edx; Val
0x1800042a8  mov     rsi, r8
0x1800042ab  mov     r14, r9
0x1800042ae  lea     r8d, [rdx+70h]; Size
0x1800042b2  call    memset_0
0x1800042b7  test    rbp, rbp
0x1800042ba  jz      loc_180004354
0x1800042c0  test    rsi, rsi
0x1800042c3  jz      loc_180004354
0x1800042c9  mov     rdi, [rsp+0C8h+arg_20]
0x1800042d1  test    rdi, rdi
0x1800042d4  jnz     short loc_1800042DD
0x1800042d6  mov     ebx, 80004003h
0x1800042db  jmp     short loc_180004359
0x1800042dd  lea     rcx, [rsp+0C8h+var_98]
0x1800042e2  call    EdpBeginLocalOnlyRpcCall
0x1800042e7  mov     ebx, eax
0x1800042e9  test    eax, eax
0x1800042eb  jns     short loc_18000430C
0x1800042ed  mov     r9d, 6
0x1800042f3  mov     dword ptr [rsp+0C8h+var_A8], 0DDEh
0x1800042fb  mov     r8d, eax
0x1800042fe  lea     rdx, EFS_API_ERROR
0x180004305  call    fnEfsLogTrace1
0x18000430a  jmp     short loc_180004359
0x18000430c  mov     r9, r14
0x18000430f  mov     [rsp+0C8h+var_A8], rdi
0x180004314  mov     r8, rsi
0x180004317  lea     rcx, [rsp+0C8h+var_98]
0x18000431c  mov     rdx, rbp
0x18000431f  call    cs:__imp_EdpDllDplUserUnlockStart
0x180004325  mov     ebx, eax
0x180004327  test    eax, eax
0x180004329  jns     short loc_180004348
0x18000432b  mov     r9d, 6
0x180004331  mov     dword ptr [rsp+0C8h+var_A8], 0DEAh
0x180004339  mov     r8d, eax
0x18000433c  lea     rdx, EFS_API_ERROR
0x180004343  call    fnEfsLogTrace1
0x180004348  lea     rcx, [rsp+0C8h+var_98]
0x18000434d  call    EdpCleanupLocalOnlyRpcCall
0x180004352  jmp     short loc_180004359
0x180004354  mov     ebx, 80070057h
0x180004359  mov     eax, ebx
0x18000435b  add     rsp, 0A0h
0x180004362  pop     r14
0x180004364  pop     rdi
0x180004365  pop     rsi
0x180004366  pop     rbp
0x180004367  pop     rbx
0x180004368  retn
```
