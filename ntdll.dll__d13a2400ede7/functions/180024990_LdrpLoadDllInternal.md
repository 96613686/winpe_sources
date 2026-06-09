# LdrpLoadDllInternal

- ea: `0x180024990`
- end: `0x180024e8d`
- name: `LdrpLoadDllInternal`
- size: `1277`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x180022a90`
- `0x180023e10`
- `0x18015bec8`

## callees

- `0x18001eb80`
- `0x180024990`
- `0x1800254d0`
- `0x180025688`
- `0x1800259ec`
- `0x180025a40`
- `0x180025abc`
- `0x180025b20`
- `0x180025d80`
- `0x180025ec0`
- `0x180025f40`
- `0x180025f78`
- `0x180025fb4`
- `0x180026110`
- `0x18002c35c`
- `0x18006d190`
- `0x18006e930`
- `0x1800709e0`
- `0x1800b7654`
- `0x1800bfb90`
- `0x1800c0568`
- `0x1800c358c`
- `0x1800fbfb0`
- `0x180102e44`

## string_xrefs

- `0x1800249bb`: `DLL name: %wZ\n`
- `0x1800249cd`: `LdrpLoadDllInternal`
- `0x1800249fc`: `LdrpLoadDllInternal`
- `0x180024a8f`: `LdrpLoadDllInternal`
- `0x180024abf`: `LdrpLoadDllInternal`
- `0x180024d2b`: `LdrpLoadDllInternal`
- `0x180024e4c`: `LdrpLoadDllInternal`

## pseudocode

```c
__int64 __fastcall LdrpLoadDllInternal(
        __int64 ArgList,
        int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        int *a8,
        __int64 a9,
        char a10)
{
  __int64 *v13; // r12
  __int64 v14; // r15
  int v15; // eax
  int *v16; // rbx
  __int64 v17; // r14
  char v19; // bl
  int v20; // eax
  __int64 *v21; // rsi
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int LoadedDllByHandle; // r15d
  char v28; // [rsp+98h] [rbp+20h]

  a10 = 0;
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 1669, (int)"LdrpLoadDllInternal", 3, "DLL name: %wZ\n", ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 1670, (int)"LdrpLoadDllInternal", 5, "%wZ\n", ArgList);
  v13 = a7;
  *a7 = 0;
  a7 = 0;
  v14 = a6;
  if ( a4 != 9 )
  {
    v15 = LdrpFastpthReloadedDll(ArgList, a3, a6, v13);
    if ( (int)(v15 + 0x80000000) < 0 || v15 == -1073740608 )
    {
      v16 = a8;
      *a8 = v15;
      v17 = a5;
      goto LABEL_4;
    }
  }
  if ( (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 )
  {
    v19 = 1;
    v28 = 1;
  }
  else
  {
    v19 = 0;
    v28 = 0;
    LdrpDrainWorkQueue(0);
  }
  if ( a4 == 9 )
  {
    LoadedDllByHandle = LdrpFindLoadedDllByHandle(a9, &a5, 0);
    v17 = a5;
    if ( LoadedDllByHandle >= 0 )
    {
      if ( *(_DWORD *)(a5 + 304) == 4 )
      {
        LoadedDllByHandle = -1073740628;
      }
      else
      {
        LoadedDllByHandle = LdrpQueryCurrentPatch(*(_QWORD *)(a5 + 48), &a10);
        if ( LoadedDllByHandle >= 0 && a10 )
        {
          v14 = v17;
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrapi.c",
            1794,
            (int)"LdrpLoadDllInternal",
            2,
            "Loading patch image for the following base image: %wZ\n",
            v17 + 88);
          goto LABEL_11;
        }
      }
    }
    if ( *(_QWORD *)(ArgList + 8) )
      LdrpFreeUnicodeString(ArgList);
    v16 = a8;
    *a8 = LoadedDllByHandle;
    if ( !v28 )
      goto LABEL_49;
    goto LABEL_4;
  }
  v17 = a5;
LABEL_11:
  LdrpThreadTokenSetMainThreadToken();
  if ( !v14 || v19 || *(_DWORD *)(*(_QWORD *)(v14 + 152) + 24LL) )
  {
    LdrpDetectDetour();
    v16 = a8;
    v20 = LdrpFindOrPrepareLoadingModule(ArgList, a2, a3, a4, v17, (__int64)&a7, (__int64)a8);
    if ( v20 == -1073741515 )
    {
      v21 = a7;
      LdrpProcessWork(a7[22]);
      goto LABEL_16;
    }
    if ( v20 != -1073741267 && v20 < 0 )
    {
      *v16 = v20;
      v21 = a7;
      goto LABEL_16;
    }
  }
  else
  {
    v16 = a8;
    *a8 = -1073741515;
  }
  v21 = a7;
LABEL_16:
  LdrpDrainWorkQueue(1);
  if ( LdrpMainThreadToken )
    LdrpThreadTokenUnsetMainThreadToken();
  if ( v21 )
  {
    v22 = LdrpHandleReplacedModule(v21);
    *v13 = v22;
    if ( v21 != (__int64 *)v22 )
    {
      LdrpFreeReplacedModule();
      v21 = (__int64 *)*v13;
      a7 = v21;
      if ( *((_DWORD *)v21 + 67) == 9 && a4 != 9 )
        *v16 = -1073740608;
    }
    if ( v21[22] )
    {
      LdrpCondenseGraph(v21[19]);
      *(_QWORD *)(v21[22] + 200) = 0;
    }
    if ( *v16 >= 0 )
    {
      v23 = LdrpPrepareModuleForExecution(v21, v16);
      *v16 = v23;
      if ( v23 >= 0 )
      {
        v24 = LdrpBuildForwarderLink(v14, v21);
        *v16 = v24;
        if ( v24 >= 0 && !LdrInitState )
          LdrpPinModule(v21);
      }
      if ( a4 == 9 && *(_QWORD *)(v17 + 296) != v21[6] )
      {
        if ( *((_DWORD *)v21 + 76) == 4 || *(_DWORD *)(v17 + 304) == 4 )
        {
          *v16 = -1073741502;
        }
        else
        {
          v25 = LdrpApplyPatchImage(v21);
          *v16 = v25;
          if ( v25 < 0 )
            LdrpLogInternal(
              (int)"minkernel\\ldr\\ldrapi.c",
              1995,
              (int)"LdrpLoadDllInternal",
              0,
              "Applying patch \"%wZ\" failed\n",
              (_BYTE)v21 + 72);
        }
      }
    }
    LdrpFreeLoadContextOfNode(v21[19], v16);
    if ( *v16 < 0 && (a4 != 9 || *((_DWORD *)v21 + 76) != 2) )
    {
      *v13 = 0;
      LdrpDecrementModuleLoadCountEx(v21, 0);
      LdrpDereferenceModule(v21);
    }
  }
  else
  {
    *v16 = -1073741801;
  }
  if ( !v28 )
LABEL_49:
    LdrpDropLastInProgressCount();
LABEL_4:
  if ( a4 == 9 && v17 )
    LdrpDereferenceModule(v17);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2120, (int)"LdrpLoadDllInternal", 4, "Status: 0x%08lx\n", *v16);
  return LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 2121, (int)"LdrpLoadDllInternal", 6, "%x\n", *v16);
}

```

## disassembly

```asm
0x180024990  mov     rax, rsp
0x180024993  mov     [rax+10h], rdx
0x180024997  mov     [rax+8], rcx
0x18002499b  push    rbx
0x18002499c  push    rsi
0x18002499d  push    rdi
0x18002499e  push    r12
0x1800249a0  push    r13
0x1800249a2  push    r14
0x1800249a4  push    r15
0x1800249a6  sub     rsp, 40h
0x1800249aa  mov     edi, r9d
0x1800249ad  mov     r13d, r8d
0x1800249b0  mov     rsi, rcx
0x1800249b3  mov     byte ptr [rax+50h], 0
0x1800249b7  mov     [rax-50h], rcx
0x1800249bb  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800249c2  mov     [rsp+78h+Format], rax; Format
0x1800249c7  mov     r9d, 3; int
0x1800249cd  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x1800249d4  mov     edx, 685h; int
0x1800249d9  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800249e0  call    LdrpLogInternal
0x1800249e5  mov     qword ptr [rsp+78h+ArgList], rsi; ArgList
0x1800249ea  lea     rax, aWz_0; "%wZ\n"
0x1800249f1  mov     [rsp+78h+Format], rax; Format
0x1800249f6  mov     r9d, 5; int
0x1800249fc  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024a03  mov     edx, 686h; int
0x180024a08  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024a0f  call    LdrpLogInternal
0x180024a14  xor     eax, eax
0x180024a16  mov     r12, [rsp+78h+arg_30]
0x180024a1e  mov     [r12], rax
0x180024a22  mov     [rsp+78h+arg_30], rax
0x180024a2a  mov     r15, [rsp+78h+arg_28]
0x180024a32  cmp     edi, 9
0x180024a35  jz      loc_180024AF3
0x180024a3b  mov     r9, r12
0x180024a3e  mov     r8, r15
0x180024a41  mov     edx, r13d
0x180024a44  mov     rcx, rsi
0x180024a47  call    LdrpFastpthReloadedDll
0x180024a4c  mov     edx, 80000000h
0x180024a51  lea     ecx, [rax+rdx]
0x180024a54  test    edx, ecx
0x180024a56  jz      loc_180024AE8
0x180024a5c  mov     rbx, [rsp+78h+arg_38]
0x180024a64  mov     [rbx], eax
0x180024a66  mov     r14, [rsp+78h+arg_20]
0x180024a6e  cmp     edi, 9
0x180024a71  jz      loc_180024E69
0x180024a77  mov     eax, [rbx]
0x180024a79  mov     dword ptr [rsp+78h+ArgList], eax; ArgList
0x180024a7d  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180024a84  mov     [rsp+78h+Format], rax; Format
0x180024a89  mov     r9d, 4; int
0x180024a8f  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024a96  mov     edx, 848h; int
0x180024a9b  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024aa2  call    LdrpLogInternal
0x180024aa7  mov     eax, [rbx]
0x180024aa9  mov     dword ptr [rsp+78h+ArgList], eax; ArgList
0x180024aad  lea     rax, asc_180175AB4; "%x\n"
0x180024ab4  mov     [rsp+78h+Format], rax; Format
0x180024ab9  mov     r9d, 6; int
0x180024abf  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024ac6  mov     edx, 849h; int
0x180024acb  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024ad2  call    LdrpLogInternal
0x180024ad7  add     rsp, 40h
0x180024adb  pop     r15
0x180024add  pop     r14
0x180024adf  pop     r13
0x180024ae1  pop     r12
0x180024ae3  pop     rdi
0x180024ae4  pop     rsi
0x180024ae5  pop     rbx
0x180024ae6  retn
0x180024ae8  cmp     eax, 0C00004C0h
0x180024aed  jz      loc_180024A5C
0x180024af3  mov     rax, gs:30h
0x180024afc  mov     ecx, 1000h
0x180024b01  test    [rax+17EEh], cx
0x180024b08  jnz     loc_180024E7F
0x180024b0e  xor     bl, bl
0x180024b10  mov     [rsp+78h+arg_18], bl
0x180024b17  xor     ecx, ecx
0x180024b19  call    LdrpDrainWorkQueue
0x180024b1e  cmp     edi, 9
0x180024b21  jz      loc_180024DAC
0x180024b27  mov     r14, [rsp+78h+arg_20]
0x180024b2f  call    LdrpThreadTokenSetMainThreadToken
0x180024b34  nop
0x180024b35  test    r15, r15
0x180024b38  jz      short loc_180024B4F
0x180024b3a  test    bl, bl
0x180024b3c  jnz     short loc_180024B4F
0x180024b3e  mov     rax, [r15+98h]
0x180024b45  cmp     dword ptr [rax+18h], 0
0x180024b49  jz      loc_180024CA2
0x180024b4f  call    LdrpDetectDetour
0x180024b54  mov     rbx, [rsp+78h+arg_38]
0x180024b5c  mov     [rsp+78h+var_48], rbx
0x180024b61  lea     rax, [rsp+78h+arg_30]
0x180024b69  mov     qword ptr [rsp+78h+ArgList], rax
0x180024b6e  mov     [rsp+78h+Format], r14
0x180024b73  mov     r9d, edi
0x180024b76  mov     r8d, r13d
0x180024b79  mov     rdx, [rsp+78h+arg_8]
0x180024b81  mov     rcx, rsi
0x180024b84  call    LdrpFindOrPrepareLoadingModule
0x180024b89  cmp     eax, 0C0000135h
0x180024b8e  jnz     loc_180024C88
0x180024b94  mov     dl, 1
0x180024b96  mov     rsi, [rsp+78h+arg_30]
0x180024b9e  mov     rcx, [rsi+0B0h]; ArgList
0x180024ba5  call    LdrpProcessWork
0x180024baa  mov     ecx, 1
0x180024baf  call    LdrpDrainWorkQueue
0x180024bb4  mov     rax, cs:LdrpMainThreadToken
0x180024bbb  test    rax, rax
0x180024bbe  jz      short loc_180024BC5
0x180024bc0  call    LdrpThreadTokenUnsetMainThreadToken
0x180024bc5  test    rsi, rsi
0x180024bc8  jz      loc_180024CBD
0x180024bce  mov     rcx, rsi
0x180024bd1  call    LdrpHandleReplacedModule
0x180024bd6  mov     [r12], rax
0x180024bda  cmp     rsi, rax
0x180024bdd  jnz     loc_180024D48
0x180024be3  cmp     qword ptr [rsi+0B0h], 0
0x180024beb  jz      short loc_180024C0B
0x180024bed  mov     rcx, [rsi+98h]
0x180024bf4  call    LdrpCondenseGraph
0x180024bf9  mov     rax, [rsi+0B0h]
0x180024c00  mov     qword ptr [rax+0C8h], 0
0x180024c0b  cmp     dword ptr [rbx], 0
0x180024c0e  jl      short loc_180024C48
0x180024c10  mov     rdx, rbx
0x180024c13  mov     rcx, rsi
0x180024c16  call    LdrpPrepareModuleForExecution
0x180024c1b  mov     [rbx], eax
0x180024c1d  test    eax, eax
0x180024c1f  js      short loc_180024C3F
0x180024c21  mov     rdx, rsi
0x180024c24  mov     rcx, r15
0x180024c27  call    LdrpBuildForwarderLink
0x180024c2c  mov     [rbx], eax
0x180024c2e  test    eax, eax
0x180024c30  js      short loc_180024C3F
0x180024c32  cmp     cs:LdrInitState, 0
0x180024c39  jz      loc_180024CC8
0x180024c3f  cmp     edi, 9
0x180024c42  jz      loc_180024CD5
0x180024c48  mov     rdx, rbx
0x180024c4b  mov     rcx, [rsi+98h]
0x180024c52  call    LdrpFreeLoadContextOfNode
0x180024c57  cmp     dword ptr [rbx], 0
0x180024c5a  jge     loc_180024D94
0x180024c60  cmp     edi, 9
0x180024c63  jz      loc_180024D7A
0x180024c69  mov     qword ptr [r12], 0
0x180024c71  xor     edx, edx
0x180024c73  mov     rcx, rsi
0x180024c76  call    LdrpDecrementModuleLoadCountEx
0x180024c7b  mov     rcx, rsi
0x180024c7e  call    LdrpDereferenceModule
0x180024c83  jmp     loc_180024D94
0x180024c88  cmp     eax, 0C000022Dh
0x180024c8d  jz      short loc_180024CB0
0x180024c8f  test    eax, eax
0x180024c91  jns     short loc_180024CB0
0x180024c93  mov     [rbx], eax
0x180024c95  mov     rsi, [rsp+78h+arg_30]
0x180024c9d  jmp     loc_180024BAA
0x180024ca2  mov     rbx, [rsp+78h+arg_38]
0x180024caa  mov     dword ptr [rbx], 0C0000135h
0x180024cb0  mov     rsi, [rsp+78h+arg_30]
0x180024cb8  jmp     loc_180024BAA
0x180024cbd  mov     dword ptr [rbx], 0C0000017h
0x180024cc3  jmp     loc_180024D94
0x180024cc8  mov     rcx, rsi
0x180024ccb  call    LdrpPinModule
0x180024cd0  jmp     loc_180024C3F
0x180024cd5  mov     rax, [rsi+30h]
0x180024cd9  cmp     [r14+128h], rax
0x180024ce0  jz      loc_180024C48
0x180024ce6  cmp     dword ptr [rsi+130h], 4
0x180024ced  jz      loc_180024D89
0x180024cf3  cmp     dword ptr [r14+130h], 4
0x180024cfb  jz      loc_180024D89
0x180024d01  mov     rcx, rsi
0x180024d04  call    LdrpApplyPatchImage
0x180024d09  mov     [rbx], eax
0x180024d0b  test    eax, eax
0x180024d0d  jns     loc_180024C48
0x180024d13  lea     rax, [rsi+48h]
0x180024d17  mov     qword ptr [rsp+78h+ArgList], rax; ArgList
0x180024d1c  lea     rax, aApplyingPatchW; "Applying patch \"%wZ\" failed\n"
0x180024d23  mov     [rsp+78h+Format], rax; Format
0x180024d28  xor     r9d, r9d; int
0x180024d2b  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024d32  mov     edx, 7CBh; int
0x180024d37  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024d3e  call    LdrpLogInternal
0x180024d43  jmp     loc_180024C48
0x180024d48  call    LdrpFreeReplacedModule
0x180024d4d  mov     rsi, [r12]
0x180024d51  mov     [rsp+78h+arg_30], rsi
0x180024d59  cmp     dword ptr [rsi+10Ch], 9
0x180024d60  jnz     loc_180024BE3
0x180024d66  cmp     edi, 9
0x180024d69  jz      loc_180024BE3
0x180024d6f  mov     dword ptr [rbx], 0C00004C0h
0x180024d75  jmp     loc_180024BE3
0x180024d7a  cmp     dword ptr [rsi+130h], 2
0x180024d81  jnz     loc_180024C69
0x180024d87  jmp     short loc_180024D94
0x180024d89  mov     dword ptr [rbx], 0C0000142h
0x180024d8f  jmp     loc_180024C48
0x180024d94  cmp     [rsp+78h+arg_18], 0
0x180024d9c  jnz     loc_180024A6E
0x180024da2  call    LdrpDropLastInProgressCount
0x180024da7  jmp     loc_180024A6E
0x180024dac  xor     r8d, r8d
0x180024daf  lea     rdx, [rsp+78h+arg_20]
0x180024db7  mov     rcx, [rsp+78h+arg_40]
0x180024dbf  call    LdrpFindLoadedDllByHandle
0x180024dc4  mov     r15d, eax
0x180024dc7  mov     r14, [rsp+78h+arg_20]
0x180024dcf  test    eax, eax
0x180024dd1  js      short loc_180024DE3
0x180024dd3  cmp     dword ptr [r14+130h], 4
0x180024ddb  jnz     short loc_180024E0C
0x180024ddd  mov     r15d, 0C00004ACh
0x180024de3  cmp     qword ptr [rsi+8], 0
0x180024de8  jz      short loc_180024DF2
0x180024dea  mov     rcx, rsi
0x180024ded  call    LdrpFreeUnicodeString
0x180024df2  mov     rbx, [rsp+78h+arg_38]
0x180024dfa  mov     [rbx], r15d
0x180024dfd  cmp     [rsp+78h+arg_18], 0
0x180024e05  jz      short loc_180024DA2
0x180024e07  jmp     loc_180024A6E
0x180024e0c  lea     rdx, [rsp+78h+arg_48]
0x180024e14  mov     rcx, [r14+30h]
0x180024e18  call    LdrpQueryCurrentPatch
0x180024e1d  mov     r15d, eax
0x180024e20  test    eax, eax
0x180024e22  js      short loc_180024DE3
0x180024e24  cmp     [rsp+78h+arg_48], 0
0x180024e2c  jz      short loc_180024DE3
0x180024e2e  mov     r15, r14
0x180024e31  lea     rax, [r14+58h]
0x180024e35  mov     qword ptr [rsp+78h+ArgList], rax; ArgList
0x180024e3a  lea     rax, aLoadingPatchIm_0; "Loading patch image for the following b"...
0x180024e41  mov     [rsp+78h+Format], rax; Format
0x180024e46  mov     r9d, 2; int
0x180024e4c  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024e53  mov     edx, 702h; int
0x180024e58  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024e5f  call    LdrpLogInternal
0x180024e64  jmp     loc_180024B2F
0x180024e69  test    r14, r14
0x180024e6c  jz      loc_180024A77
0x180024e72  mov     rcx, r14
0x180024e75  call    LdrpDereferenceModule
0x180024e7a  jmp     loc_180024A77
0x180024e7f  mov     bl, 1
0x180024e81  mov     [rsp+78h+arg_18], bl
0x180024e88  jmp     loc_180024B1E
0x180165fc0  push    rbp
0x180165fc2  sub     rsp, 40h
0x180165fc6  mov     rbp, rdx
0x180165fc9  test    cl, cl
0x180165fcb  jz      short loc_18016600F
0x180165fcd  mov     rax, [rbp+0B8h]
0x180165fd4  mov     dword ptr [rax], 0C0000005h
0x180165fda  mov     edx, 14ABh
0x180165fdf  mov     r9, [rbp+80h]
0x180165fe6  xor     r8d, r8d
0x180165fe9  mov     ecx, 0C0000005h
0x180165fee  call    LdrpLogError
0x180165ff3  mov     ecx, 1
0x180165ff8  call    LdrpDrainWorkQueue
0x180165ffd  mov     rax, cs:LdrpMainThreadToken
0x180166004  test    rax, rax
0x180166007  jz      short loc_18016600F
0x180166009  call    LdrpThreadTokenUnsetMainThreadToken
0x18016600e  nop
0x18016600f  cmp     byte ptr [rbp+98h], 0
0x180166016  jnz     short loc_18016601E
0x180166018  call    LdrpDropLastInProgressCount
0x18016601d  nop
0x18016601e  add     rsp, 40h
0x180166022  pop     rbp
0x180166023  retn
```
