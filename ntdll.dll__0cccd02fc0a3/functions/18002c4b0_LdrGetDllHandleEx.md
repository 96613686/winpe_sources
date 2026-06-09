# LdrGetDllHandleEx

- ea: `0x18002c4b0`
- end: `0x18002c6e5`
- name: `LdrGetDllHandleEx`
- size: `565`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800010fc`
- `0x1800400b0`

## callees

- `0x18001eb80`
- `0x18002bbf0`
- `0x18002c4b0`
- `0x18002c6f0`
- `0x18002c970`
- `0x18002d05c`
- `0x1800501dc`
- `0x180054000`
- `0x18016f030`

## string_xrefs

- `0x18002c4c4`: `DLL name: %wZ\n`
- `0x18002c4e4`: `LdrGetDllHandleEx`
- `0x18002c519`: `LdrGetDllHandleEx`
- `0x18002c60d`: `LdrGetDllHandleEx`
- `0x18002c63b`: `LdrGetDllHandleEx`
- `0x18002c691`: `DLL search path passed in externally: %ws\n`
- `0x18002c6a8`: `LdrpInitializeDllPath`

## pseudocode

```c
__int64 __fastcall LdrGetDllHandleEx(int a1, __int64 a2, __int64 a3, __int64 ArgList, _QWORD *a5)
{
  __int64 v8; // rbp
  char v9; // si
  int v10; // ebx
  int v11; // esi
  _QWORD *v12; // r14
  int LoadedDll; // edi
  __int64 v14; // rbp
  int Count; // eax
  __int64 v17; // rcx
  _QWORD v18[3]; // [rsp+30h] [rbp-98h] BYREF
  int v19; // [rsp+48h] [rbp-80h]
  __int64 v20; // [rsp+50h] [rbp-78h]
  __int64 v21; // [rsp+D8h] [rbp+10h] BYREF

  v21 = 0;
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2312, (int)"LdrGetDllHandleEx", 3, "DLL name: %wZ\n", ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2313, (int)"LdrGetDllHandleEx", 5, "%wZ\n", ArgList);
  v8 = *(_QWORD *)(ArgList + 8);
  memset_thunk_772440563353939046(v18, 0, 0x80u);
  if ( (a2 & 1) != 0 || !a2 )
  {
    v20 = v8;
    v19 = a2 & 0xFFFFFFFE;
  }
  else
  {
    v18[0] = a2;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrutil.c",
      1552,
      (int)"LdrpInitializeDllPath",
      2,
      "DLL search path passed in externally: %ws\n",
      a2);
    LdrpLogDllStateEx2(v17, v8, a2, 5312);
  }
  if ( (a1 & 0xFFFFFFF8) != 0 || (v9 = a1, v10 = a1 & 2, (v11 = v9 & 1) != 0) && v10 )
  {
    LoadedDll = -1073741811;
    goto LABEL_15;
  }
  v12 = a5;
  if ( !a5 && !v10 )
  {
    LoadedDll = -1073741811;
    goto LABEL_15;
  }
  LoadedDll = LdrpFindLoadedDll(ArgList, v18, &v21);
  if ( LoadedDll >= 0 )
  {
    v14 = v21;
    if ( v10 )
    {
      Count = LdrpPinModule(v21);
    }
    else
    {
      if ( v11 )
        goto LABEL_12;
      Count = LdrpIncrementModuleLoadCount(v21);
    }
    LoadedDll = Count;
    if ( Count < 0 )
    {
LABEL_14:
      LdrpDereferenceModule(v14);
      goto LABEL_15;
    }
LABEL_12:
    if ( v12 )
      *v12 = *(_QWORD *)(v14 + 48);
    goto LABEL_14;
  }
LABEL_15:
  LdrpReleaseDllPath(v18);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2361, (int)"LdrGetDllHandleEx", 4, "Status: 0x%08lx\n", LoadedDll);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2362, (int)"LdrGetDllHandleEx", 6, "%x\n", LoadedDll);
  return (unsigned int)LoadedDll;
}

```

## disassembly

```asm
0x18002c4b0  mov     [rsp+arg_10], rbx
0x18002c4b5  push    rbp
0x18002c4b6  push    rsi
0x18002c4b7  push    rdi
0x18002c4b8  sub     rsp, 0B0h
0x18002c4bf  mov     qword ptr [rsp+0C8h+ArgList], r9; ArgList
0x18002c4c4  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18002c4cb  mov     rdi, r9
0x18002c4ce  mov     [rsp+0C8h+Format], rax; Format
0x18002c4d3  mov     rsi, rdx
0x18002c4d6  mov     [rsp+0C8h+arg_8], 0
0x18002c4e2  mov     ebx, ecx
0x18002c4e4  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c4eb  mov     r9d, 3; int
0x18002c4f1  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c4f8  mov     edx, 908h; int
0x18002c4fd  call    LdrpLogInternal
0x18002c502  lea     rax, aWz_0; "%wZ\n"
0x18002c509  mov     qword ptr [rsp+0C8h+ArgList], rdi; ArgList
0x18002c50e  mov     r9d, 5; int
0x18002c514  mov     [rsp+0C8h+Format], rax; Format
0x18002c519  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c520  mov     edx, 909h; int
0x18002c525  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c52c  call    LdrpLogInternal
0x18002c531  mov     rbp, [rdi+8]
0x18002c535  lea     rcx, [rsp+0C8h+var_98]; void *
0x18002c53a  xor     edx, edx; Val
0x18002c53c  mov     r8d, 80h; Size
0x18002c542  call    memset$thunk$772440563353939046
0x18002c547  test    sil, 1
0x18002c54b  jz      loc_18002C688
0x18002c551  and     esi, 0FFFFFFFEh
0x18002c554  mov     [rsp+0C8h+var_78], rbp
0x18002c559  mov     [rsp+0C8h+var_80], esi
0x18002c55d  test    ebx, 0FFFFFFF8h
0x18002c563  jnz     loc_18002C6DB
0x18002c569  mov     esi, ebx
0x18002c56b  and     ebx, 2
0x18002c56e  and     esi, 1
0x18002c571  jz      short loc_18002C57B
0x18002c573  test    ebx, ebx
0x18002c575  jnz     loc_18002C6DB
0x18002c57b  mov     [rsp+0C8h+arg_0], r14
0x18002c583  mov     r14, [rsp+0C8h+arg_20]
0x18002c58b  test    r14, r14
0x18002c58e  jz      loc_18002C669
0x18002c594  lea     r8, [rsp+0C8h+arg_8]
0x18002c59c  mov     rcx, rdi
0x18002c59f  lea     rdx, [rsp+0C8h+var_98]
0x18002c5a4  call    LdrpFindLoadedDll
0x18002c5a9  mov     edi, eax
0x18002c5ab  test    eax, eax
0x18002c5ad  js      short loc_18002C5E5
0x18002c5af  mov     rbp, [rsp+0C8h+arg_8]
0x18002c5b7  test    ebx, ebx
0x18002c5b9  jnz     loc_18002C67B
0x18002c5bf  test    esi, esi
0x18002c5c1  jnz     short loc_18002C5D1
0x18002c5c3  mov     rcx, rbp
0x18002c5c6  call    LdrpIncrementModuleLoadCount
0x18002c5cb  mov     edi, eax
0x18002c5cd  test    eax, eax
0x18002c5cf  js      short loc_18002C5DD
0x18002c5d1  test    r14, r14
0x18002c5d4  jz      short loc_18002C5DD
0x18002c5d6  mov     rax, [rbp+30h]
0x18002c5da  mov     [r14], rax
0x18002c5dd  mov     rcx, rbp
0x18002c5e0  call    LdrpDereferenceModule
0x18002c5e5  mov     r14, [rsp+0C8h+arg_0]
0x18002c5ed  lea     rcx, [rsp+0C8h+var_98]
0x18002c5f2  call    LdrpReleaseDllPath
0x18002c5f7  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002c5fe  mov     dword ptr [rsp+0C8h+ArgList], edi; ArgList
0x18002c602  mov     r9d, 4; int
0x18002c608  mov     [rsp+0C8h+Format], rax; Format
0x18002c60d  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c614  mov     edx, 939h; int
0x18002c619  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c620  call    LdrpLogInternal
0x18002c625  lea     rax, asc_180175AB4; "%x\n"
0x18002c62c  mov     dword ptr [rsp+0C8h+ArgList], edi; ArgList
0x18002c630  mov     r9d, 6; int
0x18002c636  mov     [rsp+0C8h+Format], rax; Format
0x18002c63b  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c642  mov     edx, 93Ah; int
0x18002c647  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c64e  call    LdrpLogInternal
0x18002c653  mov     rbx, [rsp+0C8h+arg_10]
0x18002c65b  mov     eax, edi
0x18002c65d  add     rsp, 0B0h
0x18002c664  pop     rdi
0x18002c665  pop     rsi
0x18002c666  pop     rbp
0x18002c667  retn
0x18002c669  test    ebx, ebx
0x18002c66b  jnz     loc_18002C594
0x18002c671  mov     edi, 0C000000Dh
0x18002c676  jmp     loc_18002C5E5
0x18002c67b  mov     rcx, rbp
0x18002c67e  call    LdrpPinModule
0x18002c683  jmp     loc_18002C5CB
0x18002c688  test    rsi, rsi
0x18002c68b  jz      loc_18002C551
0x18002c691  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x18002c698  mov     qword ptr [rsp+0C8h+ArgList], rsi; ArgList
0x18002c69d  mov     r9d, 2; int
0x18002c6a3  mov     [rsp+0C8h+Format], rax; Format
0x18002c6a8  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x18002c6af  mov     [rsp+0C8h+var_98], rsi
0x18002c6b4  mov     edx, 610h; int
0x18002c6b9  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18002c6c0  call    LdrpLogInternal
0x18002c6c5  mov     r9d, 14C0h
0x18002c6cb  mov     r8, rsi
0x18002c6ce  mov     rdx, rbp
0x18002c6d1  call    LdrpLogDllStateEx2
0x18002c6d6  jmp     loc_18002C55D
0x18002c6db  mov     edi, 0C000000Dh
0x18002c6e0  jmp     loc_18002C5ED
```
