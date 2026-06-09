# EdpRpcRmsContainerizeFile

- ea: `0x180004f30`
- end: `0x18000501c`
- name: `EdpRpcRmsContainerizeFile`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004f30`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllRmsContainerizeFile` at `0x180004fd0`
- `EFSCORE!EdpDllRmsContainerizeFile` at `0x180004fd0`

## pseudocode

```c
__int64 __fastcall EdpRpcRmsContainerizeFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // ecx
  _BYTE v15[168]; // [rsp+30h] [rbp-A8h] BYREF

  memset_0(v15, 0, 0x70u);
  if ( a2 && a3 && a5 && a6 )
  {
    v9 = EdpBeginLocalOnlyRpcCall((__int64)v15);
    v11 = v9;
    if ( v9 >= 0 )
    {
      v12 = EdpDllRmsContainerizeFile(v15, a2, a3, a4, a5, a6);
      v11 = v12;
      if ( v12 < 0 )
        fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, v12, 6, 35);
      EdpCleanupLocalOnlyRpcCall((__int64)v15);
    }
    else
    {
      fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 22);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x180004f30  push    rbx
0x180004f32  push    rbp
0x180004f33  push    rsi
0x180004f34  push    rdi
0x180004f35  push    r14
0x180004f37  push    r15
0x180004f39  sub     rsp, 0A8h
0x180004f40  mov     r14, rdx
0x180004f43  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180004f48  xor     edx, edx; Val
0x180004f4a  mov     rbp, r8
0x180004f4d  mov     r15, r9
0x180004f50  lea     r8d, [rdx+70h]; Size
0x180004f54  call    memset_0
0x180004f59  test    r14, r14
0x180004f5c  jz      loc_180005005
0x180004f62  test    rbp, rbp
0x180004f65  jz      loc_180005005
0x180004f6b  mov     rdi, [rsp+0D8h+arg_20]
0x180004f73  test    rdi, rdi
0x180004f76  jz      loc_180005005
0x180004f7c  mov     rsi, [rsp+0D8h+arg_28]
0x180004f84  test    rsi, rsi
0x180004f87  jz      short loc_180005005
0x180004f89  lea     rcx, [rsp+0D8h+var_A8]
0x180004f8e  call    EdpBeginLocalOnlyRpcCall
0x180004f93  mov     ebx, eax
0x180004f95  test    eax, eax
0x180004f97  jns     short loc_180004FB8
0x180004f99  mov     r9d, 6
0x180004f9f  mov     dword ptr [rsp+0D8h+var_B8], 1016h
0x180004fa7  mov     r8d, eax
0x180004faa  lea     rdx, EFS_API_ERROR
0x180004fb1  call    fnEfsLogTrace1
0x180004fb6  jmp     short loc_18000500A
0x180004fb8  mov     [rsp+0D8h+var_B0], rsi
0x180004fbd  lea     rcx, [rsp+0D8h+var_A8]
0x180004fc2  mov     r9, r15
0x180004fc5  mov     [rsp+0D8h+var_B8], rdi
0x180004fca  mov     r8, rbp
0x180004fcd  mov     rdx, r14
0x180004fd0  call    cs:__imp_EdpDllRmsContainerizeFile
0x180004fd6  mov     ebx, eax
0x180004fd8  test    eax, eax
0x180004fda  jns     short loc_180004FF9
0x180004fdc  mov     r9d, 6
0x180004fe2  mov     dword ptr [rsp+0D8h+var_B8], 1023h
0x180004fea  mov     r8d, eax
0x180004fed  lea     rdx, EFS_API_ERROR
0x180004ff4  call    fnEfsLogTrace1
0x180004ff9  lea     rcx, [rsp+0D8h+var_A8]
0x180004ffe  call    EdpCleanupLocalOnlyRpcCall
0x180005003  jmp     short loc_18000500A
0x180005005  mov     ebx, 80070057h
0x18000500a  mov     eax, ebx
0x18000500c  add     rsp, 0A8h
0x180005013  pop     r15
0x180005015  pop     r14
0x180005017  pop     rdi
0x180005018  pop     rsi
0x180005019  pop     rbp
0x18000501a  pop     rbx
0x18000501b  retn
```
