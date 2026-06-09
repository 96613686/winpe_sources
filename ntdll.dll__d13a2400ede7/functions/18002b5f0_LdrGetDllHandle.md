# LdrGetDllHandle

- ea: `0x18002b5f0`
- end: `0x18002b7a9`
- name: `LdrGetDllHandle`
- size: `441`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001eb80`
- `0x18002aef0`
- `0x18002b5f0`
- `0x18002b9f0`
- `0x18002bc70`
- `0x1800709e0`
- `0x18016f030`

## string_xrefs

- `0x18002b601`: `DLL name: %wZ\n`
- `0x18002b622`: `LdrGetDllHandleEx`
- `0x18002b657`: `LdrGetDllHandleEx`
- `0x18002b6de`: `LdrGetDllHandleEx`
- `0x18002b70c`: `LdrGetDllHandleEx`
- `0x18002b75f`: `DLL search path passed in externally: %ws\n`
- `0x18002b776`: `LdrpInitializeDllPath`

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
0x18002b5f0  push    rbx
0x18002b5f2  push    rbp
0x18002b5f3  push    rsi
0x18002b5f4  push    rdi
0x18002b5f5  sub     rsp, 0B8h
0x18002b5fc  mov     qword ptr [rsp+0D8h+ArgList], r8; ArgList
0x18002b601  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18002b608  mov     rdi, r9
0x18002b60b  mov     [rsp+0D8h+Format], rax; Format
0x18002b610  mov     rsi, r8
0x18002b613  mov     [rsp+0D8h+arg_0], 0
0x18002b61f  mov     rbx, rcx
0x18002b622  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b629  mov     r9d, 3; int
0x18002b62f  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b636  mov     edx, 908h; int
0x18002b63b  call    LdrpLogInternal
0x18002b640  lea     rax, aWz_0; "%wZ\n"
0x18002b647  mov     qword ptr [rsp+0D8h+ArgList], rsi; ArgList
0x18002b64c  mov     r9d, 5; int
0x18002b652  mov     [rsp+0D8h+Format], rax; Format
0x18002b657  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b65e  mov     edx, 909h; int
0x18002b663  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b66a  call    LdrpLogInternal
0x18002b66f  mov     rbp, [rsi+8]
0x18002b673  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18002b678  xor     edx, edx; Val
0x18002b67a  mov     r8d, 80h; Size
0x18002b680  call    memset$thunk$772440563353939046
0x18002b685  test    bl, 1
0x18002b688  jz      loc_18002B756
0x18002b68e  and     ebx, 0FFFFFFFEh
0x18002b691  mov     [rsp+0D8h+var_88], rbp
0x18002b696  mov     [rsp+0D8h+var_90], ebx
0x18002b69a  test    rdi, rdi
0x18002b69d  jz      loc_18002B74C
0x18002b6a3  lea     r8, [rsp+0D8h+arg_0]
0x18002b6ab  mov     rcx, rsi
0x18002b6ae  lea     rdx, [rsp+0D8h+var_A8]
0x18002b6b3  call    LdrpFindLoadedDll
0x18002b6b8  mov     ebx, eax
0x18002b6ba  test    eax, eax
0x18002b6bc  jns     short loc_18002B733
0x18002b6be  lea     rcx, [rsp+0D8h+var_A8]
0x18002b6c3  call    LdrpReleaseDllPath
0x18002b6c8  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002b6cf  mov     dword ptr [rsp+0D8h+ArgList], ebx; ArgList
0x18002b6d3  mov     r9d, 4; int
0x18002b6d9  mov     [rsp+0D8h+Format], rax; Format
0x18002b6de  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b6e5  mov     edx, 939h; int
0x18002b6ea  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b6f1  call    LdrpLogInternal
0x18002b6f6  lea     rax, asc_180175AB4; "%x\n"
0x18002b6fd  mov     dword ptr [rsp+0D8h+ArgList], ebx; ArgList
0x18002b701  mov     r9d, 6; int
0x18002b707  mov     [rsp+0D8h+Format], rax; Format
0x18002b70c  lea     r8, aLdrgetdllhandl_3; "LdrGetDllHandleEx"
0x18002b713  mov     edx, 93Ah; int
0x18002b718  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18002b71f  call    LdrpLogInternal
0x18002b724  mov     eax, ebx
0x18002b726  add     rsp, 0B8h
0x18002b72d  pop     rdi
0x18002b72e  pop     rsi
0x18002b72f  pop     rbp
0x18002b730  pop     rbx
0x18002b731  retn
0x18002b733  mov     rcx, [rsp+0D8h+arg_0]
0x18002b73b  mov     rax, [rcx+30h]
0x18002b73f  mov     [rdi], rax
0x18002b742  call    LdrpDereferenceModule
0x18002b747  jmp     loc_18002B6BE
0x18002b74c  mov     ebx, 0C000000Dh
0x18002b751  jmp     loc_18002B6BE
0x18002b756  test    rbx, rbx
0x18002b759  jz      loc_18002B68E
0x18002b75f  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x18002b766  mov     qword ptr [rsp+0D8h+ArgList], rbx; ArgList
0x18002b76b  mov     r9d, 2; int
0x18002b771  mov     [rsp+0D8h+Format], rax; Format
0x18002b776  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x18002b77d  mov     [rsp+0D8h+var_A8], rbx
0x18002b782  mov     edx, 610h; int
0x18002b787  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18002b78e  call    LdrpLogInternal
0x18002b793  mov     r9d, 14C0h
0x18002b799  mov     r8, rbx
0x18002b79c  mov     rdx, rbp
0x18002b79f  call    LdrpLogDllStateEx2
0x18002b7a4  jmp     loc_18002B69A
```
