# EdpRpcIsConsumerProtectionEnforced

- ea: `0x180004b90`
- end: `0x180004c63`
- name: `EdpRpcIsConsumerProtectionEnforced`
- size: `211`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004b90`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EfsDllIsConsumerProtectionEnforced` at `0x180004c0b`
- `EFSCORE!EfsDllIsConsumerProtectionEnforced` at `0x180004c0b`

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
0x180004b90  mov     [rsp+arg_0], rbx
0x180004b95  mov     [rsp+arg_8], rsi
0x180004b9a  push    rdi
0x180004b9b  sub     rsp, 0A0h
0x180004ba2  mov     rsi, rdx
0x180004ba5  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004baa  xor     edx, edx; Val
0x180004bac  mov     rdi, r8
0x180004baf  lea     r8d, [rdx+70h]; Size
0x180004bb3  call    memset_0
0x180004bb8  test    rdi, rdi
0x180004bbb  jz      loc_180004C46
0x180004bc1  xor     eax, eax
0x180004bc3  mov     [rdi], eax
0x180004bc5  test    rsi, rsi
0x180004bc8  jnz     short loc_180004BD1
0x180004bca  mov     ebx, 80070057h
0x180004bcf  jmp     short loc_180004C4B
0x180004bd1  lea     rcx, [rsp+0A8h+var_78]
0x180004bd6  call    EdpBeginLocalOnlyRpcCall
0x180004bdb  mov     ebx, eax
0x180004bdd  test    eax, eax
0x180004bdf  jns     short loc_180004C00
0x180004be1  mov     r9d, 6
0x180004be7  mov     [rsp+0A8h+var_88], 1257h
0x180004bef  mov     r8d, eax
0x180004bf2  lea     rdx, EFS_API_ERROR
0x180004bf9  call    fnEfsLogTrace1
0x180004bfe  jmp     short loc_180004C4B
0x180004c00  mov     r8, rdi
0x180004c03  lea     rcx, [rsp+0A8h+var_78]
0x180004c08  mov     rdx, rsi
0x180004c0b  call    cs:__imp_EfsDllIsConsumerProtectionEnforced
0x180004c12  nop     dword ptr [rax+rax+00h]
0x180004c17  mov     ebx, eax
0x180004c19  test    eax, eax
0x180004c1b  jns     short loc_180004C3A
0x180004c1d  mov     r9d, 6
0x180004c23  mov     [rsp+0A8h+var_88], 125Fh
0x180004c2b  mov     r8d, eax
0x180004c2e  lea     rdx, EFS_API_ERROR
0x180004c35  call    fnEfsLogTrace1
0x180004c3a  lea     rcx, [rsp+0A8h+var_78]
0x180004c3f  call    EdpCleanupLocalOnlyRpcCall
0x180004c44  jmp     short loc_180004C4B
0x180004c46  mov     ebx, 80004003h
0x180004c4b  lea     r11, [rsp+0A8h+var_8]
0x180004c53  mov     eax, ebx
0x180004c55  mov     rbx, [r11+10h]
0x180004c59  mov     rsi, [r11+18h]
0x180004c5d  mov     rsp, r11
0x180004c60  pop     rdi
0x180004c61  retn
```
