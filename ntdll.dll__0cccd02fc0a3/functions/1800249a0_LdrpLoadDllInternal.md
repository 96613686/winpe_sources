# LdrpLoadDllInternal

- ea: `0x1800249a0`
- end: `0x180024e9d`
- name: `LdrpLoadDllInternal`
- size: `1277`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x180022aa0`
- `0x180023e20`
- `0x18015b538`

## callees

- `0x18001eb80`
- `0x1800249a0`
- `0x1800254e0`
- `0x180025698`
- `0x1800259fc`
- `0x180025a50`
- `0x180025acc`
- `0x180025b30`
- `0x180025d90`
- `0x180025ed0`
- `0x180025f50`
- `0x180025f88`
- `0x180025fc4`
- `0x180026120`
- `0x18002d05c`
- `0x1800507b0`
- `0x180051f50`
- `0x180054000`
- `0x1800acb14`
- `0x1800bb8b0`
- `0x1800bc288`
- `0x1800bf2ac`
- `0x1800d55f4`
- `0x1800fb270`

## string_xrefs

- `0x1800249cb`: `DLL name: %wZ\n`
- `0x1800249dd`: `LdrpLoadDllInternal`
- `0x180024a0c`: `LdrpLoadDllInternal`
- `0x180024a9f`: `LdrpLoadDllInternal`
- `0x180024acf`: `LdrpLoadDllInternal`
- `0x180024d3b`: `LdrpLoadDllInternal`
- `0x180024e5c`: `LdrpLoadDllInternal`

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
0x1800249a0  mov     rax, rsp
0x1800249a3  mov     [rax+10h], rdx
0x1800249a7  mov     [rax+8], rcx
0x1800249ab  push    rbx
0x1800249ac  push    rsi
0x1800249ad  push    rdi
0x1800249ae  push    r12
0x1800249b0  push    r13
0x1800249b2  push    r14
0x1800249b4  push    r15
0x1800249b6  sub     rsp, 40h
0x1800249ba  mov     edi, r9d
0x1800249bd  mov     r13d, r8d
0x1800249c0  mov     rsi, rcx
0x1800249c3  mov     byte ptr [rax+50h], 0
0x1800249c7  mov     [rax-50h], rcx
0x1800249cb  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800249d2  mov     [rsp+78h+Format], rax; Format
0x1800249d7  mov     r9d, 3; int
0x1800249dd  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x1800249e4  mov     edx, 685h; int
0x1800249e9  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800249f0  call    LdrpLogInternal
0x1800249f5  mov     qword ptr [rsp+78h+ArgList], rsi; ArgList
0x1800249fa  lea     rax, aWz_0; "%wZ\n"
0x180024a01  mov     [rsp+78h+Format], rax; Format
0x180024a06  mov     r9d, 5; int
0x180024a0c  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024a13  mov     edx, 686h; int
0x180024a18  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024a1f  call    LdrpLogInternal
0x180024a24  xor     eax, eax
0x180024a26  mov     r12, [rsp+78h+arg_30]
0x180024a2e  mov     [r12], rax
0x180024a32  mov     [rsp+78h+arg_30], rax
0x180024a3a  mov     r15, [rsp+78h+arg_28]
0x180024a42  cmp     edi, 9
0x180024a45  jz      loc_180024B03
0x180024a4b  mov     r9, r12
0x180024a4e  mov     r8, r15
0x180024a51  mov     edx, r13d
0x180024a54  mov     rcx, rsi
0x180024a57  call    LdrpFastpthReloadedDll
0x180024a5c  mov     edx, 80000000h
0x180024a61  lea     ecx, [rax+rdx]
0x180024a64  test    edx, ecx
0x180024a66  jz      loc_180024AF8
0x180024a6c  mov     rbx, [rsp+78h+arg_38]
0x180024a74  mov     [rbx], eax
0x180024a76  mov     r14, [rsp+78h+arg_20]
0x180024a7e  cmp     edi, 9
0x180024a81  jz      loc_180024E79
0x180024a87  mov     eax, [rbx]
0x180024a89  mov     dword ptr [rsp+78h+ArgList], eax; ArgList
0x180024a8d  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180024a94  mov     [rsp+78h+Format], rax; Format
0x180024a99  mov     r9d, 4; int
0x180024a9f  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024aa6  mov     edx, 848h; int
0x180024aab  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024ab2  call    LdrpLogInternal
0x180024ab7  mov     eax, [rbx]
0x180024ab9  mov     dword ptr [rsp+78h+ArgList], eax; ArgList
0x180024abd  lea     rax, asc_180175AB4; "%x\n"
0x180024ac4  mov     [rsp+78h+Format], rax; Format
0x180024ac9  mov     r9d, 6; int
0x180024acf  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024ad6  mov     edx, 849h; int
0x180024adb  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024ae2  call    LdrpLogInternal
0x180024ae7  add     rsp, 40h
0x180024aeb  pop     r15
0x180024aed  pop     r14
0x180024aef  pop     r13
0x180024af1  pop     r12
0x180024af3  pop     rdi
0x180024af4  pop     rsi
0x180024af5  pop     rbx
0x180024af6  retn
0x180024af8  cmp     eax, 0C00004C0h
0x180024afd  jz      loc_180024A6C
0x180024b03  mov     rax, gs:30h
0x180024b0c  mov     ecx, 1000h
0x180024b11  test    [rax+17EEh], cx
0x180024b18  jnz     loc_180024E8F
0x180024b1e  xor     bl, bl
0x180024b20  mov     [rsp+78h+arg_18], bl
0x180024b27  xor     ecx, ecx
0x180024b29  call    LdrpDrainWorkQueue
0x180024b2e  cmp     edi, 9
0x180024b31  jz      loc_180024DBC
0x180024b37  mov     r14, [rsp+78h+arg_20]
0x180024b3f  call    LdrpThreadTokenSetMainThreadToken
0x180024b44  nop
0x180024b45  test    r15, r15
0x180024b48  jz      short loc_180024B5F
0x180024b4a  test    bl, bl
0x180024b4c  jnz     short loc_180024B5F
0x180024b4e  mov     rax, [r15+98h]
0x180024b55  cmp     dword ptr [rax+18h], 0
0x180024b59  jz      loc_180024CB2
0x180024b5f  call    LdrpDetectDetour
0x180024b64  mov     rbx, [rsp+78h+arg_38]
0x180024b6c  mov     [rsp+78h+var_48], rbx
0x180024b71  lea     rax, [rsp+78h+arg_30]
0x180024b79  mov     qword ptr [rsp+78h+ArgList], rax
0x180024b7e  mov     [rsp+78h+Format], r14
0x180024b83  mov     r9d, edi
0x180024b86  mov     r8d, r13d
0x180024b89  mov     rdx, [rsp+78h+arg_8]
0x180024b91  mov     rcx, rsi
0x180024b94  call    LdrpFindOrPrepareLoadingModule
0x180024b99  cmp     eax, 0C0000135h
0x180024b9e  jnz     loc_180024C98
0x180024ba4  mov     dl, 1
0x180024ba6  mov     rsi, [rsp+78h+arg_30]
0x180024bae  mov     rcx, [rsi+0B0h]; ArgList
0x180024bb5  call    LdrpProcessWork
0x180024bba  mov     ecx, 1
0x180024bbf  call    LdrpDrainWorkQueue
0x180024bc4  mov     rax, cs:LdrpMainThreadToken
0x180024bcb  test    rax, rax
0x180024bce  jz      short loc_180024BD5
0x180024bd0  call    LdrpThreadTokenUnsetMainThreadToken
0x180024bd5  test    rsi, rsi
0x180024bd8  jz      loc_180024CCD
0x180024bde  mov     rcx, rsi
0x180024be1  call    LdrpHandleReplacedModule
0x180024be6  mov     [r12], rax
0x180024bea  cmp     rsi, rax
0x180024bed  jnz     loc_180024D58
0x180024bf3  cmp     qword ptr [rsi+0B0h], 0
0x180024bfb  jz      short loc_180024C1B
0x180024bfd  mov     rcx, [rsi+98h]
0x180024c04  call    LdrpCondenseGraph
0x180024c09  mov     rax, [rsi+0B0h]
0x180024c10  mov     qword ptr [rax+0C8h], 0
0x180024c1b  cmp     dword ptr [rbx], 0
0x180024c1e  jl      short loc_180024C58
0x180024c20  mov     rdx, rbx
0x180024c23  mov     rcx, rsi
0x180024c26  call    LdrpPrepareModuleForExecution
0x180024c2b  mov     [rbx], eax
0x180024c2d  test    eax, eax
0x180024c2f  js      short loc_180024C4F
0x180024c31  mov     rdx, rsi
0x180024c34  mov     rcx, r15
0x180024c37  call    LdrpBuildForwarderLink
0x180024c3c  mov     [rbx], eax
0x180024c3e  test    eax, eax
0x180024c40  js      short loc_180024C4F
0x180024c42  cmp     cs:LdrInitState, 0
0x180024c49  jz      loc_180024CD8
0x180024c4f  cmp     edi, 9
0x180024c52  jz      loc_180024CE5
0x180024c58  mov     rdx, rbx
0x180024c5b  mov     rcx, [rsi+98h]
0x180024c62  call    LdrpFreeLoadContextOfNode
0x180024c67  cmp     dword ptr [rbx], 0
0x180024c6a  jge     loc_180024DA4
0x180024c70  cmp     edi, 9
0x180024c73  jz      loc_180024D8A
0x180024c79  mov     qword ptr [r12], 0
0x180024c81  xor     edx, edx
0x180024c83  mov     rcx, rsi
0x180024c86  call    LdrpDecrementModuleLoadCountEx
0x180024c8b  mov     rcx, rsi
0x180024c8e  call    LdrpDereferenceModule
0x180024c93  jmp     loc_180024DA4
0x180024c98  cmp     eax, 0C000022Dh
0x180024c9d  jz      short loc_180024CC0
0x180024c9f  test    eax, eax
0x180024ca1  jns     short loc_180024CC0
0x180024ca3  mov     [rbx], eax
0x180024ca5  mov     rsi, [rsp+78h+arg_30]
0x180024cad  jmp     loc_180024BBA
0x180024cb2  mov     rbx, [rsp+78h+arg_38]
0x180024cba  mov     dword ptr [rbx], 0C0000135h
0x180024cc0  mov     rsi, [rsp+78h+arg_30]
0x180024cc8  jmp     loc_180024BBA
0x180024ccd  mov     dword ptr [rbx], 0C0000017h
0x180024cd3  jmp     loc_180024DA4
0x180024cd8  mov     rcx, rsi
0x180024cdb  call    LdrpPinModule
0x180024ce0  jmp     loc_180024C4F
0x180024ce5  mov     rax, [rsi+30h]
0x180024ce9  cmp     [r14+128h], rax
0x180024cf0  jz      loc_180024C58
0x180024cf6  cmp     dword ptr [rsi+130h], 4
0x180024cfd  jz      loc_180024D99
0x180024d03  cmp     dword ptr [r14+130h], 4
0x180024d0b  jz      loc_180024D99
0x180024d11  mov     rcx, rsi
0x180024d14  call    LdrpApplyPatchImage
0x180024d19  mov     [rbx], eax
0x180024d1b  test    eax, eax
0x180024d1d  jns     loc_180024C58
0x180024d23  lea     rax, [rsi+48h]
0x180024d27  mov     qword ptr [rsp+78h+ArgList], rax; ArgList
0x180024d2c  lea     rax, aApplyingPatchW; "Applying patch \"%wZ\" failed\n"
0x180024d33  mov     [rsp+78h+Format], rax; Format
0x180024d38  xor     r9d, r9d; int
0x180024d3b  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024d42  mov     edx, 7CBh; int
0x180024d47  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024d4e  call    LdrpLogInternal
0x180024d53  jmp     loc_180024C58
0x180024d58  call    LdrpFreeReplacedModule
0x180024d5d  mov     rsi, [r12]
0x180024d61  mov     [rsp+78h+arg_30], rsi
0x180024d69  cmp     dword ptr [rsi+10Ch], 9
0x180024d70  jnz     loc_180024BF3
0x180024d76  cmp     edi, 9
0x180024d79  jz      loc_180024BF3
0x180024d7f  mov     dword ptr [rbx], 0C00004C0h
0x180024d85  jmp     loc_180024BF3
0x180024d8a  cmp     dword ptr [rsi+130h], 2
0x180024d91  jnz     loc_180024C79
0x180024d97  jmp     short loc_180024DA4
0x180024d99  mov     dword ptr [rbx], 0C0000142h
0x180024d9f  jmp     loc_180024C58
0x180024da4  cmp     [rsp+78h+arg_18], 0
0x180024dac  jnz     loc_180024A7E
0x180024db2  call    LdrpDropLastInProgressCount
0x180024db7  jmp     loc_180024A7E
0x180024dbc  xor     r8d, r8d
0x180024dbf  lea     rdx, [rsp+78h+arg_20]
0x180024dc7  mov     rcx, [rsp+78h+arg_40]
0x180024dcf  call    LdrpFindLoadedDllByHandle
0x180024dd4  mov     r15d, eax
0x180024dd7  mov     r14, [rsp+78h+arg_20]
0x180024ddf  test    eax, eax
0x180024de1  js      short loc_180024DF3
0x180024de3  cmp     dword ptr [r14+130h], 4
0x180024deb  jnz     short loc_180024E1C
0x180024ded  mov     r15d, 0C00004ACh
0x180024df3  cmp     qword ptr [rsi+8], 0
0x180024df8  jz      short loc_180024E02
0x180024dfa  mov     rcx, rsi
0x180024dfd  call    LdrpFreeUnicodeString
0x180024e02  mov     rbx, [rsp+78h+arg_38]
0x180024e0a  mov     [rbx], r15d
0x180024e0d  cmp     [rsp+78h+arg_18], 0
0x180024e15  jz      short loc_180024DB2
0x180024e17  jmp     loc_180024A7E
0x180024e1c  lea     rdx, [rsp+78h+arg_48]
0x180024e24  mov     rcx, [r14+30h]
0x180024e28  call    LdrpQueryCurrentPatch
0x180024e2d  mov     r15d, eax
0x180024e30  test    eax, eax
0x180024e32  js      short loc_180024DF3
0x180024e34  cmp     [rsp+78h+arg_48], 0
0x180024e3c  jz      short loc_180024DF3
0x180024e3e  mov     r15, r14
0x180024e41  lea     rax, [r14+58h]
0x180024e45  mov     qword ptr [rsp+78h+ArgList], rax; ArgList
0x180024e4a  lea     rax, aLoadingPatchIm_0; "Loading patch image for the following b"...
0x180024e51  mov     [rsp+78h+Format], rax; Format
0x180024e56  mov     r9d, 2; int
0x180024e5c  lea     r8, aLdrploaddllint; "LdrpLoadDllInternal"
0x180024e63  mov     edx, 702h; int
0x180024e68  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x180024e6f  call    LdrpLogInternal
0x180024e74  jmp     loc_180024B3F
0x180024e79  test    r14, r14
0x180024e7c  jz      loc_180024A87
0x180024e82  mov     rcx, r14
0x180024e85  call    LdrpDereferenceModule
0x180024e8a  jmp     loc_180024A87
0x180024e8f  mov     bl, 1
0x180024e91  mov     [rsp+78h+arg_18], bl
0x180024e98  jmp     loc_180024B2E
0x1801657c0  push    rbp
0x1801657c2  sub     rsp, 40h
0x1801657c6  mov     rbp, rdx
0x1801657c9  test    cl, cl
0x1801657cb  jz      short loc_18016580F
0x1801657cd  mov     rax, [rbp+0B8h]
0x1801657d4  mov     dword ptr [rax], 0C0000005h
0x1801657da  mov     edx, 14ABh
0x1801657df  mov     r9, [rbp+80h]
0x1801657e6  xor     r8d, r8d
0x1801657e9  mov     ecx, 0C0000005h
0x1801657ee  call    LdrpLogError
0x1801657f3  mov     ecx, 1
0x1801657f8  call    LdrpDrainWorkQueue
0x1801657fd  mov     rax, cs:LdrpMainThreadToken
0x180165804  test    rax, rax
0x180165807  jz      short loc_18016580F
0x180165809  call    LdrpThreadTokenUnsetMainThreadToken
0x18016580e  nop
0x18016580f  cmp     byte ptr [rbp+98h], 0
0x180165816  jnz     short loc_18016581E
0x180165818  call    LdrpDropLastInProgressCount
0x18016581d  nop
0x18016581e  add     rsp, 40h
0x180165822  pop     rbp
0x180165823  retn
```
