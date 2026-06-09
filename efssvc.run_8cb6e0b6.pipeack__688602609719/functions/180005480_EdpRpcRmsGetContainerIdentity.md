# EdpRpcRmsGetContainerIdentity

- ea: `0x180005480`
- end: `0x180005544`
- name: `EdpRpcRmsGetContainerIdentity`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180005480`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllRmsGetContainerIdentity` at `0x1800054ec`
- `EFSCORE!EdpDllRmsGetContainerIdentity` at `0x1800054ec`

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
0x180005480  mov     [rsp+arg_0], rbx
0x180005485  mov     [rsp+arg_8], rsi
0x18000548a  push    rdi
0x18000548b  sub     rsp, 0A0h
0x180005492  mov     rsi, rdx
0x180005495  lea     rcx, [rsp+0A8h+var_78]; void *
0x18000549a  xor     edx, edx; Val
0x18000549c  mov     rdi, r8
0x18000549f  lea     r8d, [rdx+70h]; Size
0x1800054a3  call    memset_0
0x1800054a8  test    rsi, rsi
0x1800054ab  jz      short loc_180005527
0x1800054ad  test    rdi, rdi
0x1800054b0  jz      short loc_180005527
0x1800054b2  lea     rcx, [rsp+0A8h+var_78]
0x1800054b7  call    EdpBeginLocalOnlyRpcCall
0x1800054bc  mov     ebx, eax
0x1800054be  test    eax, eax
0x1800054c0  jns     short loc_1800054E1
0x1800054c2  mov     r9d, 6
0x1800054c8  mov     [rsp+0A8h+var_88], 1059h
0x1800054d0  mov     r8d, eax
0x1800054d3  lea     rdx, EFS_API_ERROR
0x1800054da  call    fnEfsLogTrace1
0x1800054df  jmp     short loc_18000552C
0x1800054e1  mov     r8, rdi
0x1800054e4  lea     rcx, [rsp+0A8h+var_78]
0x1800054e9  mov     rdx, rsi
0x1800054ec  call    cs:__imp_EdpDllRmsGetContainerIdentity
0x1800054f3  nop     dword ptr [rax+rax+00h]
0x1800054f8  mov     ebx, eax
0x1800054fa  test    eax, eax
0x1800054fc  jns     short loc_18000551B
0x1800054fe  mov     r9d, 6
0x180005504  mov     [rsp+0A8h+var_88], 1063h
0x18000550c  mov     r8d, eax
0x18000550f  lea     rdx, EFS_API_ERROR
0x180005516  call    fnEfsLogTrace1
0x18000551b  lea     rcx, [rsp+0A8h+var_78]
0x180005520  call    EdpCleanupLocalOnlyRpcCall
0x180005525  jmp     short loc_18000552C
0x180005527  mov     ebx, 80070057h
0x18000552c  lea     r11, [rsp+0A8h+var_8]
0x180005534  mov     eax, ebx
0x180005536  mov     rbx, [r11+10h]
0x18000553a  mov     rsi, [r11+18h]
0x18000553e  mov     rsp, r11
0x180005541  pop     rdi
0x180005542  retn
```
