# EdpRpcDplUserUnlockComplete

- ea: `0x1800041d0`
- end: `0x180004284`
- name: `EdpRpcDplUserUnlockComplete`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x1800041d0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockComplete` at `0x18000423c`
- `EFSCORE!EdpDllDplUserUnlockComplete` at `0x18000423c`

## pseudocode

```c
__int64 __fastcall EdpRpcDplUserUnlockComplete(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ecx
  _BYTE v13[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v13, 0, 0x70u);
  if ( a2 && a4 )
  {
    v7 = EdpBeginLocalOnlyRpcCall((__int64)v13);
    v9 = v7;
    if ( v7 >= 0 )
    {
      v10 = EdpDllDplUserUnlockComplete(v13, a2, a3, a4);
      v9 = v10;
      if ( v10 < 0 )
        fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, v10, 6, 49);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 38);
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
0x1800041d0  push    rbx
0x1800041d2  push    rbp
0x1800041d3  push    rsi
0x1800041d4  push    rdi
0x1800041d5  sub     rsp, 0A8h
0x1800041dc  mov     rsi, rdx
0x1800041df  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800041e4  xor     edx, edx; Val
0x1800041e6  mov     ebp, r8d
0x1800041e9  mov     rdi, r9
0x1800041ec  lea     r8d, [rdx+70h]; Size
0x1800041f0  call    memset_0
0x1800041f5  test    rsi, rsi
0x1800041f8  jz      short loc_180004271
0x1800041fa  test    rdi, rdi
0x1800041fd  jz      short loc_180004271
0x1800041ff  lea     rcx, [rsp+0C8h+var_98]
0x180004204  call    EdpBeginLocalOnlyRpcCall
0x180004209  mov     ebx, eax
0x18000420b  test    eax, eax
0x18000420d  jns     short loc_18000422E
0x18000420f  mov     r9d, 6
0x180004215  mov     [rsp+0C8h+var_A8], 0E26h
0x18000421d  mov     r8d, eax
0x180004220  lea     rdx, EFS_API_ERROR
0x180004227  call    fnEfsLogTrace1
0x18000422c  jmp     short loc_180004276
0x18000422e  mov     r9, rdi
0x180004231  lea     rcx, [rsp+0C8h+var_98]
0x180004236  mov     r8d, ebp
0x180004239  mov     rdx, rsi
0x18000423c  call    cs:__imp_EdpDllDplUserUnlockComplete
0x180004242  mov     ebx, eax
0x180004244  test    eax, eax
0x180004246  jns     short loc_180004265
0x180004248  mov     r9d, 6
0x18000424e  mov     [rsp+0C8h+var_A8], 0E31h
0x180004256  mov     r8d, eax
0x180004259  lea     rdx, EFS_API_ERROR
0x180004260  call    fnEfsLogTrace1
0x180004265  lea     rcx, [rsp+0C8h+var_98]
0x18000426a  call    EdpCleanupLocalOnlyRpcCall
0x18000426f  jmp     short loc_180004276
0x180004271  mov     ebx, 80070057h
0x180004276  mov     eax, ebx
0x180004278  add     rsp, 0A8h
0x18000427f  pop     rdi
0x180004280  pop     rsi
0x180004281  pop     rbp
0x180004282  pop     rbx
0x180004283  retn
```
