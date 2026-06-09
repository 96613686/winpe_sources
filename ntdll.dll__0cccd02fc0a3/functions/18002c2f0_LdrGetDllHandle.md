# LdrGetDllHandle

- ea: `0x18002c2f0`
- end: `0x18002c4a9`
- name: `LdrGetDllHandle`
- size: `441`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001eb80`
- `0x18002bbf0`
- `0x18002c2f0`
- `0x18002c6f0`
- `0x18002c970`
- `0x180054000`
- `0x18016f030`

## string_xrefs

- `0x18002c301`: `DLL name: %wZ\n`
- `0x18002c322`: `LdrGetDllHandleEx`
- `0x18002c357`: `LdrGetDllHandleEx`
- `0x18002c3de`: `LdrGetDllHandleEx`
- `0x18002c40c`: `LdrGetDllHandleEx`
- `0x18002c45f`: `DLL search path passed in externally: %ws\n`
- `0x18002c476`: `LdrpInitializeDllPath`

## pseudocode

```c
__int64 __fastcall LdrGetDllHandle(__int64 ArgList, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rbp
  int LoadedDll; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD v12[3]; // [rsp+30h] [rbp-A8h] BYREF
  int v13; // [rsp+48h] [rbp-90h]
  __int64 v14; // [rsp+50h] [rbp-88h]
  __int64 v15; // [rsp+E0h] [rbp+8h] BYREF

  v15 = 0;
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2312, (int)"LdrGetDllHandleEx", 3, "DLL name: %wZ\n", a3);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2313, (int)"LdrGetDllHandleEx", 5, "%wZ\n", a3);
  v7 = *(_QWORD *)(a3 + 8);
  memset_thunk_772440563353939046(v12, 0, 0x80u);
  if ( (ArgList & 1) != 0 || !ArgList )
  {
    v14 = v7;
    v13 = ArgList & 0xFFFFFFFE;
  }
  else
  {
    v12[0] = ArgList;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrutil.c",
      1552,
      (int)"LdrpInitializeDllPath",
      2,
      "DLL search path passed in externally: %ws\n",
      ArgList);
    LdrpLogDllStateEx2(v11, v7, ArgList, 5312);
  }
  if ( a4 )
  {
    LoadedDll = LdrpFindLoadedDll(a3, v12, &v15);
    if ( LoadedDll >= 0 )
    {
      v10 = v15;
      *a4 = *(_QWORD *)(v15 + 48);
      LdrpDereferenceModule(v10);
    }
  }
  else
  {
    LoadedDll = -1073741811;
  }
  LdrpReleaseDllPath(v12);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2361, (int)"LdrGetDllHandleEx", 4, "Status: 0x%08lx\n", LoadedDll);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2362, (int)"LdrGetDllHandleEx", 6, "%x\n", LoadedDll);
  return (unsigned int)LoadedDll;
}

```

## disassembly

```asm
0x18002c2f0  push    rbx
0x18002c2f2  push    rbp
0x18002c2f3  push    rsi
0x18002c2f4  push    rdi
0x18002c2f5  sub     rsp, 0B8h
0x18002c2fc  mov     qword ptr [rsp+0D8h+ArgList], r8; ArgList
0x18002c301  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18002c308  mov     rdi, r9
0x18002c30b  mov     [rsp+0D8h+Format], rax; Format
0x18002c310  mov     rsi, r8
0x18002c313  mov     [rsp+0D8h+arg_0], 0
0x18002c31f  mov     rbx, rcx
0x18002c322  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c329  mov     r9d, 3; int
0x18002c32f  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c336  mov     edx, 908h; int
0x18002c33b  call    LdrpLogInternal
0x18002c340  lea     rax, aWz_0; "%wZ\n"
0x18002c347  mov     qword ptr [rsp+0D8h+ArgList], rsi; ArgList
0x18002c34c  mov     r9d, 5; int
0x18002c352  mov     [rsp+0D8h+Format], rax; Format
0x18002c357  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c35e  mov     edx, 909h; int
0x18002c363  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c36a  call    LdrpLogInternal
0x18002c36f  mov     rbp, [rsi+8]
0x18002c373  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18002c378  xor     edx, edx; Val
0x18002c37a  mov     r8d, 80h; Size
0x18002c380  call    memset$thunk$772440563353939046
0x18002c385  test    bl, 1
0x18002c388  jz      loc_18002C456
0x18002c38e  and     ebx, 0FFFFFFFEh
0x18002c391  mov     [rsp+0D8h+var_88], rbp
0x18002c396  mov     [rsp+0D8h+var_90], ebx
0x18002c39a  test    rdi, rdi
0x18002c39d  jz      loc_18002C44C
0x18002c3a3  lea     r8, [rsp+0D8h+arg_0]
0x18002c3ab  mov     rcx, rsi
0x18002c3ae  lea     rdx, [rsp+0D8h+var_A8]
0x18002c3b3  call    LdrpFindLoadedDll
0x18002c3b8  mov     ebx, eax
0x18002c3ba  test    eax, eax
0x18002c3bc  jns     short loc_18002C433
0x18002c3be  lea     rcx, [rsp+0D8h+var_A8]
0x18002c3c3  call    LdrpReleaseDllPath
0x18002c3c8  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002c3cf  mov     dword ptr [rsp+0D8h+ArgList], ebx; ArgList
0x18002c3d3  mov     r9d, 4; int
0x18002c3d9  mov     [rsp+0D8h+Format], rax; Format
0x18002c3de  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c3e5  mov     edx, 939h; int
0x18002c3ea  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c3f1  call    LdrpLogInternal
0x18002c3f6  lea     rax, asc_180175AB4; "%x\n"
0x18002c3fd  mov     dword ptr [rsp+0D8h+ArgList], ebx; ArgList
0x18002c401  mov     r9d, 6; int
0x18002c407  mov     [rsp+0D8h+Format], rax; Format
0x18002c40c  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002c413  mov     edx, 93Ah; int
0x18002c418  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002c41f  call    LdrpLogInternal
0x18002c424  mov     eax, ebx
0x18002c426  add     rsp, 0B8h
0x18002c42d  pop     rdi
0x18002c42e  pop     rsi
0x18002c42f  pop     rbp
0x18002c430  pop     rbx
0x18002c431  retn
0x18002c433  mov     rcx, [rsp+0D8h+arg_0]
0x18002c43b  mov     rax, [rcx+30h]
0x18002c43f  mov     [rdi], rax
0x18002c442  call    LdrpDereferenceModule
0x18002c447  jmp     loc_18002C3BE
0x18002c44c  mov     ebx, 0C000000Dh
0x18002c451  jmp     loc_18002C3BE
0x18002c456  test    rbx, rbx
0x18002c459  jz      loc_18002C38E
0x18002c45f  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x18002c466  mov     qword ptr [rsp+0D8h+ArgList], rbx; ArgList
0x18002c46b  mov     r9d, 2; int
0x18002c471  mov     [rsp+0D8h+Format], rax; Format
0x18002c476  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x18002c47d  mov     [rsp+0D8h+var_A8], rbx
0x18002c482  mov     edx, 610h; int
0x18002c487  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18002c48e  call    LdrpLogInternal
0x18002c493  mov     r9d, 14C0h
0x18002c499  mov     r8, rbx
0x18002c49c  mov     rdx, rbp
0x18002c49f  call    LdrpLogDllStateEx2
0x18002c4a4  jmp     loc_18002C39A
```
