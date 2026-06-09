# LdrpInitializeKernel32Functions

- ea: `0x18002631c`
- end: `0x18002660a`
- name: `LdrpInitializeKernel32Functions`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800d6508`

## callees

- `0x18001b9b0`
- `0x18001d4b0`
- `0x18001eb80`
- `0x1800248a0`
- `0x18002631c`
- `0x180028620`
- `0x180029fc0`
- `0x180052930`
- `0x180162000`
- `0x18016f020`
- `0x18016f030`

## string_xrefs

- `0x18002659c`: `Loading Windows subsystem DLL "%wZ" failed with status 0x%08lx\n`
- `0x1800265e0`: `Locating procedure "%Z" in Windows subsystem DLL "%wZ" failed with status 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall LdrpInitializeKernel32Functions(_QWORD *a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rdi
  int ProcedureAddressForCaller; // eax
  int ArgList; // eax
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (*v11)(void); // [rsp+58h] [rbp-A8h] BYREF
  __m128i v12; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v13; // [rsp+70h] [rbp-90h] BYREF
  __int64 retaddr; // [rsp+1B8h] [rbp+B8h]

  v11 = 0;
  v10 = 0;
  v9 = 0;
  memset_thunk_772440563353939046(&v12, 0, 0x110u);
  v8 = 0;
  v12.m128i_i64[1] = (__int64)&v13;
  *a1 = 0;
  v13 = 0;
  v12.m128i_i32[0] = 0x1000000;
  LdrpAppendUnicodeStringToFilenameBuffer(&v12, &LdrpKernel32DllName);
  if ( (int)LdrpFindLoadedDllInternal(&v12, 0, (__int64)&v10, &v8, 32) >= 0 )
  {
    v4 = *(_QWORD *)(v10 + 48);
    v9 = v4;
    if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x20000000) == 0 )
      goto LABEL_6;
LABEL_8:
    v3 = LdrLoadDll(16385, 0, (__int64)LdrpKernelbaseDllName, &v9);
    if ( v3 < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        2253,
        (int)"LdrpInitializeKernel32Functions",
        0,
        "Loading Windows subsystem DLL \"%wZ\" failed with status 0x%08lx\n",
        (char)LdrpKernelbaseDllName);
    }
    else
    {
      v3 = LdrpCodeAuthzInitialize();
      if ( (int)(v3 + 0x80000000) < 0 || v3 == -1073741515 )
      {
        ProcedureAddressForCaller = LdrGetProcedureAddressForCaller(
                                      v9,
                                      (unsigned int)&qword_180170300,
                                      0,
                                      (unsigned int)&v11,
                                      0,
                                      retaddr);
        v3 = ProcedureAddressForCaller;
        if ( ProcedureAddressForCaller < 0 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrinit.c",
            2287,
            (int)"LdrpInitializeKernel32Functions",
            0,
            "Finding KernelbasePostInit failed with status 0x%08lx\n",
            ProcedureAddressForCaller);
        }
        else
        {
          ArgList = v11();
          v3 = ArgList;
          if ( ArgList < 0 )
            LdrpLogInternal(
              (int)"minkernel\\ldr\\ldrinit.c",
              2296,
              (int)"LdrpInitializeKernel32Functions",
              0,
              "Calling KernelbasePostInit failed with status 0x%08lx\n",
              ArgList);
        }
      }
      else
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          2269,
          (int)"LdrpInitializeKernel32Functions",
          0,
          "LdrpCodeAuthzInitialize failed with status 0x%08lx\n",
          v3);
      }
    }
    return (unsigned int)v3;
  }
  v2 = LdrLoadDll(16385, 0, (__int64)&LdrpKernel32DllName, &v9);
  v3 = v2;
  if ( v2 == -1073741515 )
    goto LABEL_8;
  if ( v2 < 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      2165,
      (int)"LdrpInitializeKernel32Functions",
      0,
      "Loading Windows subsystem DLL \"%wZ\" failed with status 0x%08lx\n",
      (char)&LdrpKernel32DllName);
    return (unsigned int)v3;
  }
  LODWORD(v4) = v9;
LABEL_6:
  v3 = LdrGetProcedureAddressForCaller(
         v4,
         (unsigned int)::ArgList,
         0,
         (unsigned int)&Kernel32ThreadInitThunkFunction,
         0,
         retaddr);
  if ( v3 < 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      2188,
      (int)"LdrpInitializeKernel32Functions",
      0,
      "Locating procedure \"%Z\" in Windows subsystem DLL \"%wZ\" failed with status 0x%08lx\n",
      (char)::ArgList);
    return (unsigned int)v3;
  }
  LdrGetProcedureAddressForCaller(v4, (unsigned int)&qword_180170310, 0, (_DWORD)a1, 0, retaddr);
  v3 = LdrpSnapKernelBaseExtensions();
  if ( v3 >= 0 )
    goto LABEL_8;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002631c  push    rbp
0x18002631e  push    rbx
0x18002631f  push    rsi
0x180026320  push    rdi
0x180026321  push    r12
0x180026323  push    r15
0x180026325  lea     rbp, [rsp-88h]
0x18002632d  sub     rsp, 188h
0x180026334  mov     rax, cs:__security_cookie
0x18002633b  xor     rax, rsp
0x18002633e  mov     [rbp+0B0h+var_40], rax
0x180026342  mov     rsi, rcx
0x180026345  mov     [rsp+1B0h+var_158], 0
0x18002634e  lea     rcx, [rsp+1B0h+var_150]; void *
0x180026353  mov     [rsp+1B0h+var_160], 0
0x18002635c  xor     edx, edx; Val
0x18002635e  mov     [rsp+1B0h+var_168], 0
0x180026367  mov     r8d, 110h; Size
0x18002636d  call    memset$thunk$772440563353939046
0x180026372  lea     rax, [rsp+1B0h+var_140]
0x180026377  mov     [rsp+1B0h+var_170], 0
0x18002637f  mov     [rsp+1B0h+var_148], rax
0x180026384  lea     r15, LdrpKernel32DllName
0x18002638b  xor     eax, eax
0x18002638d  mov     qword ptr [rsi], 0
0x180026394  mov     rdx, r15
0x180026397  mov     [rsp+1B0h+var_140], ax
0x18002639c  lea     rcx, [rsp+1B0h+var_150]
0x1800263a1  mov     dword ptr [rsp+1B0h+var_150], 1000000h
0x1800263a9  call    LdrpAppendUnicodeStringToFilenameBuffer
0x1800263ae  lea     r9, [rsp+1B0h+var_170]
0x1800263b3  mov     dword ptr [rsp+1B0h+Format], 20h ; ' '; int
0x1800263bb  lea     r8, [rsp+1B0h+var_160]
0x1800263c0  xor     edx, edx
0x1800263c2  lea     rcx, [rsp+1B0h+var_150]; ArgList
0x1800263c7  call    LdrpFindLoadedDllInternal
0x1800263cc  test    eax, eax
0x1800263ce  jns     short loc_180026400
0x1800263d0  lea     r9, [rsp+1B0h+var_168]
0x1800263d5  mov     r8, r15
0x1800263d8  xor     edx, edx
0x1800263da  mov     ecx, 4001h
0x1800263df  call    LdrLoadDll
0x1800263e4  mov     ebx, eax
0x1800263e6  cmp     eax, 0C0000135h
0x1800263eb  jz      loc_180026496
0x1800263f1  test    eax, eax
0x1800263f3  js      loc_1800265C0
0x1800263f9  mov     rdi, [rsp+1B0h+var_168]
0x1800263fe  jmp     short loc_180026424
0x180026400  mov     rax, [rsp+1B0h+var_160]
0x180026405  mov     rdi, [rax+30h]
0x180026409  mov     rax, gs:60h
0x180026412  mov     [rsp+1B0h+var_168], rdi
0x180026417  mov     rcx, [rax+20h]
0x18002641b  test    dword ptr [rcx+8], 20000000h
0x180026422  jnz     short loc_180026496
0x180026424  mov     rax, [rbp+0B8h]
0x18002642b  lea     r12, ArgList
0x180026432  mov     qword ptr [rsp+1B0h+ArgList], rax
0x180026437  lea     r9, Kernel32ThreadInitThunkFunction
0x18002643e  mov     rdx, r12
0x180026441  mov     dword ptr [rsp+1B0h+Format], 0
0x180026449  xor     r8d, r8d
0x18002644c  mov     rcx, rdi
0x18002644f  call    LdrGetProcedureAddressForCaller
0x180026454  mov     ebx, eax
0x180026456  test    eax, eax
0x180026458  js      loc_1800265D0
0x18002645e  mov     rax, [rbp+0B8h]
0x180026465  lea     rdx, qword_180170310
0x18002646c  mov     qword ptr [rsp+1B0h+ArgList], rax
0x180026471  mov     r9, rsi
0x180026474  xor     r8d, r8d
0x180026477  mov     dword ptr [rsp+1B0h+Format], 0
0x18002647f  mov     rcx, rdi
0x180026482  call    LdrGetProcedureAddressForCaller
0x180026487  call    LdrpSnapKernelBaseExtensions
0x18002648c  mov     ebx, eax
0x18002648e  test    eax, eax
0x180026490  js      loc_180026551
0x180026496  lea     rdi, LdrpKernelbaseDllName
0x18002649d  xor     edx, edx
0x18002649f  mov     r8, rdi
0x1800264a2  lea     r9, [rsp+1B0h+var_168]
0x1800264a7  mov     ecx, 4001h
0x1800264ac  call    LdrLoadDll
0x1800264b1  mov     ebx, eax
0x1800264b3  test    eax, eax
0x1800264b5  js      loc_18002658E
0x1800264bb  call    LdrpCodeAuthzInitialize
0x1800264c0  mov     ecx, 80000000h
0x1800264c5  mov     ebx, eax
0x1800264c7  add     eax, ecx
0x1800264c9  test    ecx, eax
0x1800264cb  jz      loc_180026570
0x1800264d1  mov     rax, [rbp+0B8h]
0x1800264d8  lea     r9, [rsp+1B0h+var_158]
0x1800264dd  mov     rcx, [rsp+1B0h+var_168]
0x1800264e2  lea     rdx, qword_180170300
0x1800264e9  mov     qword ptr [rsp+1B0h+ArgList], rax
0x1800264ee  xor     r8d, r8d
0x1800264f1  mov     dword ptr [rsp+1B0h+Format], 0
0x1800264f9  call    LdrGetProcedureAddressForCaller
0x1800264fe  mov     ebx, eax
0x180026500  test    eax, eax
0x180026502  js      short loc_180026526
0x180026504  mov     rax, [rsp+1B0h+var_158]
0x180026509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002650e  mov     ebx, eax
0x180026510  test    eax, eax
0x180026512  jns     short loc_180026551
0x180026514  mov     dword ptr [rsp+1B0h+ArgList], eax
0x180026518  mov     edx, 8F8h
0x18002651d  lea     rax, aCallingKernelb; "Calling KernelbasePostInit failed with "...
0x180026524  jmp     short loc_180026536
0x180026526  mov     dword ptr [rsp+1B0h+ArgList], eax; ArgList
0x18002652a  mov     edx, 8EFh; int
0x18002652f  lea     rax, aFindingKernelb; "Finding KernelbasePostInit failed with "...
0x180026536  xor     r9d, r9d; int
0x180026539  mov     [rsp+1B0h+Format], rax; Format
0x18002653e  lea     r8, aLdrpinitialize_6; "LdrpInitializeKernel32Functions"
0x180026545  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18002654c  call    LdrpLogInternal
0x180026551  mov     eax, ebx
0x180026553  mov     rcx, [rbp+0B0h+var_40]
0x180026557  xor     rcx, rsp; StackCookie
0x18002655a  call    __security_check_cookie
0x18002655f  add     rsp, 188h
0x180026566  pop     r15
0x180026568  pop     r12
0x18002656a  pop     rdi
0x18002656b  pop     rsi
0x18002656c  pop     rbx
0x18002656d  pop     rbp
0x18002656e  retn
0x180026570  cmp     ebx, 0C0000135h
0x180026576  jz      loc_1800264D1
0x18002657c  mov     dword ptr [rsp+1B0h+ArgList], ebx
0x180026580  lea     rax, aLdrpcodeauthzi; "LdrpCodeAuthzInitialize failed with sta"...
0x180026587  mov     edx, 8DDh
0x18002658c  jmp     short loc_180026536
0x18002658e  mov     dword ptr [rsp+1B0h+var_180], eax
0x180026592  mov     edx, 8CDh; int
0x180026597  mov     qword ptr [rsp+1B0h+ArgList], rdi; ArgList
0x18002659c  lea     rax, aLoadingWindows; "Loading Windows subsystem DLL \"%wZ\" f"...
0x1800265a3  xor     r9d, r9d; int
0x1800265a6  lea     r8, aLdrpinitialize_6; "LdrpInitializeKernel32Functions"
0x1800265ad  mov     [rsp+1B0h+Format], rax; Format
0x1800265b2  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800265b9  call    LdrpLogInternal
0x1800265be  jmp     short loc_180026551
0x1800265c0  mov     dword ptr [rsp+1B0h+var_180], eax
0x1800265c4  mov     edx, 875h
0x1800265c9  mov     qword ptr [rsp+1B0h+ArgList], r15
0x1800265ce  jmp     short loc_18002659C
0x1800265d0  mov     [rsp+1B0h+var_178], eax
0x1800265d4  lea     r8, aLdrpinitialize_6; "LdrpInitializeKernel32Functions"
0x1800265db  mov     [rsp+1B0h+var_180], r15
0x1800265e0  lea     rax, aLocatingProced; "Locating procedure \"%Z\" in Windows su"...
0x1800265e7  mov     qword ptr [rsp+1B0h+ArgList], r12; ArgList
0x1800265ec  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800265f3  xor     r9d, r9d; int
0x1800265f6  mov     [rsp+1B0h+Format], rax; Format
0x1800265fb  mov     edx, 88Ch; int
0x180026600  call    LdrpLogInternal
0x180026605  jmp     loc_180026551
```
