# EdpRpcDplUserUnlockStart

- ea: `0x180004540`
- end: `0x180004623`
- name: `EdpRpcDplUserUnlockStart`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004540`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockStart` at `0x1800045d2`
- `EFSCORE!EdpDllDplUserUnlockStart` at `0x1800045d2`

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
0x180004540  push    rbx
0x180004542  push    rbp
0x180004543  push    rsi
0x180004544  push    rdi
0x180004545  push    r14
0x180004547  sub     rsp, 0A0h
0x18000454e  mov     rbp, rdx
0x180004551  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004556  xor     edx, edx; Val
0x180004558  mov     rsi, r8
0x18000455b  mov     r14, r9
0x18000455e  lea     r8d, [rdx+70h]; Size
0x180004562  call    memset_0
0x180004567  test    rbp, rbp
0x18000456a  jz      loc_18000460D
0x180004570  test    rsi, rsi
0x180004573  jz      loc_18000460D
0x180004579  mov     rdi, [rsp+0C8h+arg_20]
0x180004581  test    rdi, rdi
0x180004584  jnz     short loc_180004590
0x180004586  mov     ebx, 80004003h
0x18000458b  jmp     loc_180004612
0x180004590  lea     rcx, [rsp+0C8h+var_98]
0x180004595  call    EdpBeginLocalOnlyRpcCall
0x18000459a  mov     ebx, eax
0x18000459c  test    eax, eax
0x18000459e  jns     short loc_1800045BF
0x1800045a0  mov     r9d, 6
0x1800045a6  mov     dword ptr [rsp+0C8h+var_A8], 0DDEh
0x1800045ae  mov     r8d, eax
0x1800045b1  lea     rdx, EFS_API_ERROR
0x1800045b8  call    fnEfsLogTrace1
0x1800045bd  jmp     short loc_180004612
0x1800045bf  mov     r9, r14
0x1800045c2  mov     [rsp+0C8h+var_A8], rdi
0x1800045c7  mov     r8, rsi
0x1800045ca  lea     rcx, [rsp+0C8h+var_98]
0x1800045cf  mov     rdx, rbp
0x1800045d2  call    cs:__imp_EdpDllDplUserUnlockStart
0x1800045d9  nop     dword ptr [rax+rax+00h]
0x1800045de  mov     ebx, eax
0x1800045e0  test    eax, eax
0x1800045e2  jns     short loc_180004601
0x1800045e4  mov     r9d, 6
0x1800045ea  mov     dword ptr [rsp+0C8h+var_A8], 0DEAh
0x1800045f2  mov     r8d, eax
0x1800045f5  lea     rdx, EFS_API_ERROR
0x1800045fc  call    fnEfsLogTrace1
0x180004601  lea     rcx, [rsp+0C8h+var_98]
0x180004606  call    EdpCleanupLocalOnlyRpcCall
0x18000460b  jmp     short loc_180004612
0x18000460d  mov     ebx, 80070057h
0x180004612  mov     eax, ebx
0x180004614  add     rsp, 0A0h
0x18000461b  pop     r14
0x18000461d  pop     rdi
0x18000461e  pop     rsi
0x18000461f  pop     rbp
0x180004620  pop     rbx
0x180004621  retn
```
