# EdpRpcRmsContainerizeFile

- ea: `0x1800052b0`
- end: `0x1800053a7`
- name: `EdpRpcRmsContainerizeFile`
- size: `247`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800052b0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllRmsContainerizeFile` at `0x180005354`
- `EFSCORE!EdpDllRmsContainerizeFile` at `0x180005354`

## pseudocode

```c
__int64 __fastcall EdpRpcRmsContainerizeFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  signed int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  signed int v12; // eax
  __int64 v13; // rcx
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
        fnEfsLogTrace1(v13, (__int64)EFS_API_ERROR, v12, 6, 35);
      EdpCleanupLocalOnlyRpcCall((__int64)v15);
    }
    else
    {
      fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, v9, 6, 22);
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
0x1800052b0  push    rbx
0x1800052b2  push    rbp
0x1800052b3  push    rsi
0x1800052b4  push    rdi
0x1800052b5  push    r14
0x1800052b7  push    r15
0x1800052b9  sub     rsp, 0A8h
0x1800052c0  mov     r14, rdx
0x1800052c3  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800052c8  xor     edx, edx; Val
0x1800052ca  mov     rbp, r8
0x1800052cd  mov     r15, r9
0x1800052d0  lea     r8d, [rdx+70h]; Size
0x1800052d4  call    memset_0
0x1800052d9  test    r14, r14
0x1800052dc  jz      loc_18000538F
0x1800052e2  test    rbp, rbp
0x1800052e5  jz      loc_18000538F
0x1800052eb  mov     rdi, [rsp+0D8h+arg_20]
0x1800052f3  test    rdi, rdi
0x1800052f6  jz      loc_18000538F
0x1800052fc  mov     rsi, [rsp+0D8h+arg_28]
0x180005304  test    rsi, rsi
0x180005307  jz      loc_18000538F
0x18000530d  lea     rcx, [rsp+0D8h+var_A8]
0x180005312  call    EdpBeginLocalOnlyRpcCall
0x180005317  mov     ebx, eax
0x180005319  test    eax, eax
0x18000531b  jns     short loc_18000533C
0x18000531d  mov     r9d, 6
0x180005323  mov     dword ptr [rsp+0D8h+var_B8], 1016h
0x18000532b  mov     r8d, eax
0x18000532e  lea     rdx, EFS_API_ERROR
0x180005335  call    fnEfsLogTrace1
0x18000533a  jmp     short loc_180005394
0x18000533c  mov     [rsp+0D8h+var_B0], rsi
0x180005341  lea     rcx, [rsp+0D8h+var_A8]
0x180005346  mov     r9, r15
0x180005349  mov     [rsp+0D8h+var_B8], rdi
0x18000534e  mov     r8, rbp
0x180005351  mov     rdx, r14
0x180005354  call    cs:__imp_EdpDllRmsContainerizeFile
0x18000535b  nop     dword ptr [rax+rax+00h]
0x180005360  mov     ebx, eax
0x180005362  test    eax, eax
0x180005364  jns     short loc_180005383
0x180005366  mov     r9d, 6
0x18000536c  mov     dword ptr [rsp+0D8h+var_B8], 1023h
0x180005374  mov     r8d, eax
0x180005377  lea     rdx, EFS_API_ERROR
0x18000537e  call    fnEfsLogTrace1
0x180005383  lea     rcx, [rsp+0D8h+var_A8]
0x180005388  call    EdpCleanupLocalOnlyRpcCall
0x18000538d  jmp     short loc_180005394
0x18000538f  mov     ebx, 80070057h
0x180005394  mov     eax, ebx
0x180005396  add     rsp, 0A8h
0x18000539d  pop     r15
0x18000539f  pop     r14
0x1800053a1  pop     rdi
0x1800053a2  pop     rsi
0x1800053a3  pop     rbp
0x1800053a4  pop     rbx
0x1800053a5  retn
```
