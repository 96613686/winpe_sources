# EdpRpcDplUserCredentialsSet

- ea: `0x180004380`
- end: `0x18000445c`
- name: `EdpRpcDplUserCredentialsSet`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004380`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllDplUserCredentialsSet` at `0x18000440d`
- `EFSCORE!EdpDllDplUserCredentialsSet` at `0x18000440d`

## pseudocode

```c
__int64 __fastcall EdpRpcDplUserCredentialsSet(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  signed int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  signed int v11; // eax
  __int64 v12; // rcx
  _BYTE v14[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v14, 0, 0x70u);
  if ( a2 && a3 && a4 - 1 <= 3 )
  {
    v8 = EdpBeginLocalOnlyRpcCall((__int64)v14);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v11 = EdpDllDplUserCredentialsSet(v14, a2, a3, a4, a5);
      v10 = v11;
      if ( v11 < 0 )
        fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 154);
      EdpCleanupLocalOnlyRpcCall((__int64)v14);
    }
    else
    {
      fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v8, 6, 142);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x180004380  push    rbx
0x180004382  push    rbp
0x180004383  push    rsi
0x180004384  push    rdi
0x180004385  sub     rsp, 0A8h
0x18000438c  mov     rbp, rdx
0x18000438f  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004394  xor     edx, edx; Val
0x180004396  mov     rdi, r8
0x180004399  mov     esi, r9d
0x18000439c  lea     r8d, [rdx+70h]; Size
0x1800043a0  call    memset_0
0x1800043a5  test    rbp, rbp
0x1800043a8  jz      loc_180004448
0x1800043ae  test    rdi, rdi
0x1800043b1  jz      loc_180004448
0x1800043b7  lea     eax, [rsi-1]
0x1800043ba  cmp     eax, 3
0x1800043bd  ja      loc_180004448
0x1800043c3  lea     rcx, [rsp+0C8h+var_98]
0x1800043c8  call    EdpBeginLocalOnlyRpcCall
0x1800043cd  mov     ebx, eax
0x1800043cf  test    eax, eax
0x1800043d1  jns     short loc_1800043F2
0x1800043d3  mov     r9d, 6
0x1800043d9  mov     dword ptr [rsp+0C8h+var_A8], 0D8Eh
0x1800043e1  mov     r8d, eax
0x1800043e4  lea     rdx, EFS_API_ERROR
0x1800043eb  call    fnEfsLogTrace1
0x1800043f0  jmp     short loc_18000444D
0x1800043f2  mov     rax, [rsp+0C8h+arg_20]
0x1800043fa  lea     rcx, [rsp+0C8h+var_98]
0x1800043ff  mov     r9d, esi
0x180004402  mov     [rsp+0C8h+var_A8], rax
0x180004407  mov     r8, rdi
0x18000440a  mov     rdx, rbp
0x18000440d  call    cs:__imp_EdpDllDplUserCredentialsSet
0x180004414  nop     dword ptr [rax+rax+00h]
0x180004419  mov     ebx, eax
0x18000441b  test    eax, eax
0x18000441d  jns     short loc_18000443C
0x18000441f  mov     r9d, 6
0x180004425  mov     dword ptr [rsp+0C8h+var_A8], 0D9Ah
0x18000442d  mov     r8d, eax
0x180004430  lea     rdx, EFS_API_ERROR
0x180004437  call    fnEfsLogTrace1
0x18000443c  lea     rcx, [rsp+0C8h+var_98]
0x180004441  call    EdpCleanupLocalOnlyRpcCall
0x180004446  jmp     short loc_18000444D
0x180004448  mov     ebx, 80070057h
0x18000444d  mov     eax, ebx
0x18000444f  add     rsp, 0A8h
0x180004456  pop     rdi
0x180004457  pop     rsi
0x180004458  pop     rbp
0x180004459  pop     rbx
0x18000445a  retn
```
