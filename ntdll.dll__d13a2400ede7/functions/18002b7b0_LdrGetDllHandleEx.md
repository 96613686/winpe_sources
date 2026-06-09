# LdrGetDllHandleEx

- ea: `0x18002b7b0`
- end: `0x18002b9e5`
- name: `LdrGetDllHandleEx`
- size: `565`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800010fc`
- `0x18004d990`

## callees

- `0x18001eb80`
- `0x18002aef0`
- `0x18002b7b0`
- `0x18002b9f0`
- `0x18002bc70`
- `0x18002c35c`
- `0x18006cbbc`
- `0x1800709e0`
- `0x18016f030`

## string_xrefs

- `0x18002b7c4`: `DLL name: %wZ\n`
- `0x18002b7e4`: `LdrGetDllHandleEx`
- `0x18002b819`: `LdrGetDllHandleEx`
- `0x18002b90d`: `LdrGetDllHandleEx`
- `0x18002b93b`: `LdrGetDllHandleEx`
- `0x18002b991`: `DLL search path passed in externally: %ws\n`
- `0x18002b9a8`: `LdrpInitializeDllPath`

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
0x18002b7b0  mov     [rsp+arg_10], rbx
0x18002b7b5  push    rbp
0x18002b7b6  push    rsi
0x18002b7b7  push    rdi
0x18002b7b8  sub     rsp, 0B0h
0x18002b7bf  mov     qword ptr [rsp+0C8h+ArgList], r9; ArgList
0x18002b7c4  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18002b7cb  mov     rdi, r9
0x18002b7ce  mov     [rsp+0C8h+Format], rax; Format
0x18002b7d3  mov     rsi, rdx
0x18002b7d6  mov     [rsp+0C8h+arg_8], 0
0x18002b7e2  mov     ebx, ecx
0x18002b7e4  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b7eb  mov     r9d, 3; int
0x18002b7f1  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b7f8  mov     edx, 908h; int
0x18002b7fd  call    LdrpLogInternal
0x18002b802  lea     rax, aWz_0; "%wZ\n"
0x18002b809  mov     qword ptr [rsp+0C8h+ArgList], rdi; ArgList
0x18002b80e  mov     r9d, 5; int
0x18002b814  mov     [rsp+0C8h+Format], rax; Format
0x18002b819  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b820  mov     edx, 909h; int
0x18002b825  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b82c  call    LdrpLogInternal
0x18002b831  mov     rbp, [rdi+8]
0x18002b835  lea     rcx, [rsp+0C8h+var_98]; void *
0x18002b83a  xor     edx, edx; Val
0x18002b83c  mov     r8d, 80h; Size
0x18002b842  call    memset$thunk$772440563353939046
0x18002b847  test    sil, 1
0x18002b84b  jz      loc_18002B988
0x18002b851  and     esi, 0FFFFFFFEh
0x18002b854  mov     [rsp+0C8h+var_78], rbp
0x18002b859  mov     [rsp+0C8h+var_80], esi
0x18002b85d  test    ebx, 0FFFFFFF8h
0x18002b863  jnz     loc_18002B9DB
0x18002b869  mov     esi, ebx
0x18002b86b  and     ebx, 2
0x18002b86e  and     esi, 1
0x18002b871  jz      short loc_18002B87B
0x18002b873  test    ebx, ebx
0x18002b875  jnz     loc_18002B9DB
0x18002b87b  mov     [rsp+0C8h+arg_0], r14
0x18002b883  mov     r14, [rsp+0C8h+arg_20]
0x18002b88b  test    r14, r14
0x18002b88e  jz      loc_18002B969
0x18002b894  lea     r8, [rsp+0C8h+arg_8]
0x18002b89c  mov     rcx, rdi
0x18002b89f  lea     rdx, [rsp+0C8h+var_98]
0x18002b8a4  call    LdrpFindLoadedDll
0x18002b8a9  mov     edi, eax
0x18002b8ab  test    eax, eax
0x18002b8ad  js      short loc_18002B8E5
0x18002b8af  mov     rbp, [rsp+0C8h+arg_8]
0x18002b8b7  test    ebx, ebx
0x18002b8b9  jnz     loc_18002B97B
0x18002b8bf  test    esi, esi
0x18002b8c1  jnz     short loc_18002B8D1
0x18002b8c3  mov     rcx, rbp
0x18002b8c6  call    LdrpIncrementModuleLoadCount
0x18002b8cb  mov     edi, eax
0x18002b8cd  test    eax, eax
0x18002b8cf  js      short loc_18002B8DD
0x18002b8d1  test    r14, r14
0x18002b8d4  jz      short loc_18002B8DD
0x18002b8d6  mov     rax, [rbp+30h]
0x18002b8da  mov     [r14], rax
0x18002b8dd  mov     rcx, rbp
0x18002b8e0  call    LdrpDereferenceModule
0x18002b8e5  mov     r14, [rsp+0C8h+arg_0]
0x18002b8ed  lea     rcx, [rsp+0C8h+var_98]
0x18002b8f2  call    LdrpReleaseDllPath
0x18002b8f7  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002b8fe  mov     dword ptr [rsp+0C8h+ArgList], edi; ArgList
0x18002b902  mov     r9d, 4; int
0x18002b908  mov     [rsp+0C8h+Format], rax; Format
0x18002b90d  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b914  mov     edx, 939h; int
0x18002b919  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b920  call    LdrpLogInternal
0x18002b925  lea     rax, asc_180175AB4; "%x\n"
0x18002b92c  mov     dword ptr [rsp+0C8h+ArgList], edi; ArgList
0x18002b930  mov     r9d, 6; int
0x18002b936  mov     [rsp+0C8h+Format], rax; Format
0x18002b93b  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b942  mov     edx, 93Ah; int
0x18002b947  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b94e  call    LdrpLogInternal
0x18002b953  mov     rbx, [rsp+0C8h+arg_10]
0x18002b95b  mov     eax, edi
0x18002b95d  add     rsp, 0B0h
0x18002b964  pop     rdi
0x18002b965  pop     rsi
0x18002b966  pop     rbp
0x18002b967  retn
0x18002b969  test    ebx, ebx
0x18002b96b  jnz     loc_18002B894
0x18002b971  mov     edi, 0C000000Dh
0x18002b976  jmp     loc_18002B8E5
0x18002b97b  mov     rcx, rbp
0x18002b97e  call    LdrpPinModule
0x18002b983  jmp     loc_18002B8CB
0x18002b988  test    rsi, rsi
0x18002b98b  jz      loc_18002B851
0x18002b991  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x18002b998  mov     qword ptr [rsp+0C8h+ArgList], rsi; ArgList
0x18002b99d  mov     r9d, 2; int
0x18002b9a3  mov     [rsp+0C8h+Format], rax; Format
0x18002b9a8  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x18002b9af  mov     [rsp+0C8h+var_98], rsi
0x18002b9b4  mov     edx, 610h; int
0x18002b9b9  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18002b9c0  call    LdrpLogInternal
0x18002b9c5  mov     r9d, 14C0h
0x18002b9cb  mov     r8, rsi
0x18002b9ce  mov     rdx, rbp
0x18002b9d1  call    LdrpLogDllStateEx2
0x18002b9d6  jmp     loc_18002B85D
0x18002b9db  mov     edi, 0C000000Dh
0x18002b9e0  jmp     loc_18002B8ED
```
