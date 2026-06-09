# EdpRpcIsConsumerProtectionEnforced

- ea: `0x1800048b0`
- end: `0x180004978`
- name: `EdpRpcIsConsumerProtectionEnforced`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x1800048b0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EfsDllIsConsumerProtectionEnforced` at `0x180004927`
- `EFSCORE!EfsDllIsConsumerProtectionEnforced` at `0x180004927`

## pseudocode

```c
__int64 __fastcall EdpRpcIsConsumerProtectionEnforced(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  signed int v6; // eax
  __int64 v7; // rcx
  signed int IsConsumerProtectionEnforced; // eax
  __int64 v9; // rcx
  _BYTE v11[112]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v11, 0, sizeof(v11));
  if ( a3 )
  {
    *a3 = 0;
    if ( a2 )
    {
      v6 = EdpBeginLocalOnlyRpcCall((__int64)v11);
      v5 = v6;
      if ( v6 >= 0 )
      {
        IsConsumerProtectionEnforced = EfsDllIsConsumerProtectionEnforced(v11, a2, a3);
        v5 = IsConsumerProtectionEnforced;
        if ( IsConsumerProtectionEnforced < 0 )
          fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, IsConsumerProtectionEnforced, 6, 95);
        EdpCleanupLocalOnlyRpcCall((__int64)v11);
      }
      else
      {
        fnEfsLogTrace1(v7, (__int64)EFS_API_ERROR, v6, 6, 87);
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x1800048b0  mov     [rsp+arg_0], rbx
0x1800048b5  mov     [rsp+arg_8], rsi
0x1800048ba  push    rdi
0x1800048bb  sub     rsp, 0A0h
0x1800048c2  mov     rsi, rdx
0x1800048c5  lea     rcx, [rsp+0A8h+var_78]; void *
0x1800048ca  xor     edx, edx; Val
0x1800048cc  mov     rdi, r8
0x1800048cf  lea     r8d, [rdx+70h]; Size
0x1800048d3  call    memset_0
0x1800048d8  test    rdi, rdi
0x1800048db  jz      short loc_18000495C
0x1800048dd  xor     eax, eax
0x1800048df  mov     [rdi], eax
0x1800048e1  test    rsi, rsi
0x1800048e4  jnz     short loc_1800048ED
0x1800048e6  mov     ebx, 80070057h
0x1800048eb  jmp     short loc_180004961
0x1800048ed  lea     rcx, [rsp+0A8h+var_78]
0x1800048f2  call    EdpBeginLocalOnlyRpcCall
0x1800048f7  mov     ebx, eax
0x1800048f9  test    eax, eax
0x1800048fb  jns     short loc_18000491C
0x1800048fd  mov     r9d, 6
0x180004903  mov     [rsp+0A8h+var_88], 1257h
0x18000490b  mov     r8d, eax
0x18000490e  lea     rdx, EFS_API_ERROR
0x180004915  call    fnEfsLogTrace1
0x18000491a  jmp     short loc_180004961
0x18000491c  mov     r8, rdi
0x18000491f  lea     rcx, [rsp+0A8h+var_78]
0x180004924  mov     rdx, rsi
0x180004927  call    cs:__imp_EfsDllIsConsumerProtectionEnforced
0x18000492d  mov     ebx, eax
0x18000492f  test    eax, eax
0x180004931  jns     short loc_180004950
0x180004933  mov     r9d, 6
0x180004939  mov     [rsp+0A8h+var_88], 125Fh
0x180004941  mov     r8d, eax
0x180004944  lea     rdx, EFS_API_ERROR
0x18000494b  call    fnEfsLogTrace1
0x180004950  lea     rcx, [rsp+0A8h+var_78]
0x180004955  call    EdpCleanupLocalOnlyRpcCall
0x18000495a  jmp     short loc_180004961
0x18000495c  mov     ebx, 80004003h
0x180004961  lea     r11, [rsp+0A8h+var_8]
0x180004969  mov     eax, ebx
0x18000496b  mov     rbx, [r11+10h]
0x18000496f  mov     rsi, [r11+18h]
0x180004973  mov     rsp, r11
0x180004976  pop     rdi
0x180004977  retn
```
