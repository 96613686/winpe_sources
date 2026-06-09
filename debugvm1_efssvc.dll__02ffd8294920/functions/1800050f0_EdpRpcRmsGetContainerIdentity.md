# EdpRpcRmsGetContainerIdentity

- ea: `0x1800050f0`
- end: `0x1800051ad`
- name: `EdpRpcRmsGetContainerIdentity`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x1800050f0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllRmsGetContainerIdentity` at `0x18000515c`
- `EFSCORE!EdpDllRmsGetContainerIdentity` at `0x18000515c`

## pseudocode

```c
__int64 __fastcall EdpRpcRmsGetContainerIdentity(__int64 a1, __int64 a2, __int64 a3)
{
  signed int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  signed int ContainerIdentity; // eax
  __int64 v9; // rcx
  _BYTE v11[112]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v11, 0, sizeof(v11));
  if ( a2 && a3 )
  {
    v5 = EdpBeginLocalOnlyRpcCall((__int64)v11);
    v7 = v5;
    if ( v5 >= 0 )
    {
      ContainerIdentity = EdpDllRmsGetContainerIdentity(v11, a2, a3);
      v7 = ContainerIdentity;
      if ( ContainerIdentity < 0 )
        fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, ContainerIdentity, 6, 99);
      EdpCleanupLocalOnlyRpcCall((__int64)v11);
    }
    else
    {
      fnEfsLogTrace1(v6, (__int64)EFS_API_ERROR, v5, 6, 89);
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
0x1800050f0  mov     [rsp+arg_0], rbx
0x1800050f5  mov     [rsp+arg_8], rsi
0x1800050fa  push    rdi
0x1800050fb  sub     rsp, 0A0h
0x180005102  mov     rsi, rdx
0x180005105  lea     rcx, [rsp+0A8h+var_78]; void *
0x18000510a  xor     edx, edx; Val
0x18000510c  mov     rdi, r8
0x18000510f  lea     r8d, [rdx+70h]; Size
0x180005113  call    memset_0
0x180005118  test    rsi, rsi
0x18000511b  jz      short loc_180005191
0x18000511d  test    rdi, rdi
0x180005120  jz      short loc_180005191
0x180005122  lea     rcx, [rsp+0A8h+var_78]
0x180005127  call    EdpBeginLocalOnlyRpcCall
0x18000512c  mov     ebx, eax
0x18000512e  test    eax, eax
0x180005130  jns     short loc_180005151
0x180005132  mov     r9d, 6
0x180005138  mov     [rsp+0A8h+var_88], 1059h
0x180005140  mov     r8d, eax
0x180005143  lea     rdx, EFS_API_ERROR
0x18000514a  call    fnEfsLogTrace1
0x18000514f  jmp     short loc_180005196
0x180005151  mov     r8, rdi
0x180005154  lea     rcx, [rsp+0A8h+var_78]
0x180005159  mov     rdx, rsi
0x18000515c  call    cs:__imp_EdpDllRmsGetContainerIdentity
0x180005162  mov     ebx, eax
0x180005164  test    eax, eax
0x180005166  jns     short loc_180005185
0x180005168  mov     r9d, 6
0x18000516e  mov     [rsp+0A8h+var_88], 1063h
0x180005176  mov     r8d, eax
0x180005179  lea     rdx, EFS_API_ERROR
0x180005180  call    fnEfsLogTrace1
0x180005185  lea     rcx, [rsp+0A8h+var_78]
0x18000518a  call    EdpCleanupLocalOnlyRpcCall
0x18000518f  jmp     short loc_180005196
0x180005191  mov     ebx, 80070057h
0x180005196  lea     r11, [rsp+0A8h+var_8]
0x18000519e  mov     eax, ebx
0x1800051a0  mov     rbx, [r11+10h]
0x1800051a4  mov     rsi, [r11+18h]
0x1800051a8  mov     rsp, r11
0x1800051ab  pop     rdi
0x1800051ac  retn
```
