# LdrpInitializeKernel32Functions

- ea: `0x18002630c`
- end: `0x1800265fa`
- name: `LdrpInitializeKernel32Functions`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180050718`

## callees

- `0x18001b9b0`
- `0x18001d4b0`
- `0x18001eb80`
- `0x180024890`
- `0x18002630c`
- `0x180028510`
- `0x180029eb0`
- `0x18006f310`
- `0x180162810`
- `0x18016f020`
- `0x18016f030`

## string_xrefs

- `0x18002658c`: `Loading Windows subsystem DLL "%wZ" failed with status 0x%08lx\n`
- `0x1800265d0`: `Locating procedure "%Z" in Windows subsystem DLL "%wZ" failed with status 0x%08lx\n`

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
0x18002630c  push    rbp
0x18002630e  push    rbx
0x18002630f  push    rsi
0x180026310  push    rdi
0x180026311  push    r12
0x180026313  push    r15
0x180026315  lea     rbp, [rsp-88h]
0x18002631d  sub     rsp, 188h
0x180026324  mov     rax, cs:__security_cookie
0x18002632b  xor     rax, rsp
0x18002632e  mov     [rbp+0B0h+var_40], rax
0x180026332  mov     rsi, rcx
0x180026335  mov     [rsp+1B0h+var_158], 0
0x18002633e  lea     rcx, [rsp+1B0h+var_150]; void *
0x180026343  mov     [rsp+1B0h+var_160], 0
0x18002634c  xor     edx, edx; Val
0x18002634e  mov     [rsp+1B0h+var_168], 0
0x180026357  mov     r8d, 110h; Size
0x18002635d  call    memset$thunk$772440563353939046
0x180026362  lea     rax, [rsp+1B0h+var_140]
0x180026367  mov     [rsp+1B0h+var_170], 0
0x18002636f  mov     [rsp+1B0h+var_148], rax
0x180026374  lea     r15, LdrpKernel32DllName
0x18002637b  xor     eax, eax
0x18002637d  mov     qword ptr [rsi], 0
0x180026384  mov     rdx, r15
0x180026387  mov     [rsp+1B0h+var_140], ax
0x18002638c  lea     rcx, [rsp+1B0h+var_150]
0x180026391  mov     dword ptr [rsp+1B0h+var_150], 1000000h
0x180026399  call    LdrpAppendUnicodeStringToFilenameBuffer
0x18002639e  lea     r9, [rsp+1B0h+var_170]
0x1800263a3  mov     dword ptr [rsp+1B0h+Format], 20h ; ' '; int
0x1800263ab  lea     r8, [rsp+1B0h+var_160]
0x1800263b0  xor     edx, edx
0x1800263b2  lea     rcx, [rsp+1B0h+var_150]; ArgList
0x1800263b7  call    LdrpFindLoadedDllInternal
0x1800263bc  test    eax, eax
0x1800263be  jns     short loc_1800263F0
0x1800263c0  lea     r9, [rsp+1B0h+var_168]
0x1800263c5  mov     r8, r15
0x1800263c8  xor     edx, edx
0x1800263ca  mov     ecx, 4001h
0x1800263cf  call    LdrLoadDll
0x1800263d4  mov     ebx, eax
0x1800263d6  cmp     eax, 0C0000135h
0x1800263db  jz      loc_180026486
0x1800263e1  test    eax, eax
0x1800263e3  js      loc_1800265B0
0x1800263e9  mov     rdi, [rsp+1B0h+var_168]
0x1800263ee  jmp     short loc_180026414
0x1800263f0  mov     rax, [rsp+1B0h+var_160]
0x1800263f5  mov     rdi, [rax+30h]
0x1800263f9  mov     rax, gs:60h
0x180026402  mov     [rsp+1B0h+var_168], rdi
0x180026407  mov     rcx, [rax+20h]
0x18002640b  test    dword ptr [rcx+8], 20000000h
0x180026412  jnz     short loc_180026486
0x180026414  mov     rax, [rbp+0B8h]
0x18002641b  lea     r12, ArgList
0x180026422  mov     qword ptr [rsp+1B0h+ArgList], rax
0x180026427  lea     r9, Kernel32ThreadInitThunkFunction
0x18002642e  mov     rdx, r12
0x180026431  mov     dword ptr [rsp+1B0h+Format], 0
0x180026439  xor     r8d, r8d
0x18002643c  mov     rcx, rdi
0x18002643f  call    LdrGetProcedureAddressForCaller
0x180026444  mov     ebx, eax
0x180026446  test    eax, eax
0x180026448  js      loc_1800265C0
0x18002644e  mov     rax, [rbp+0B8h]
0x180026455  lea     rdx, qword_180170310
0x18002645c  mov     qword ptr [rsp+1B0h+ArgList], rax
0x180026461  mov     r9, rsi
0x180026464  xor     r8d, r8d
0x180026467  mov     dword ptr [rsp+1B0h+Format], 0
0x18002646f  mov     rcx, rdi
0x180026472  call    LdrGetProcedureAddressForCaller
0x180026477  call    LdrpSnapKernelBaseExtensions
0x18002647c  mov     ebx, eax
0x18002647e  test    eax, eax
0x180026480  js      loc_180026541
0x180026486  lea     rdi, LdrpKernelbaseDllName
0x18002648d  xor     edx, edx
0x18002648f  mov     r8, rdi
0x180026492  lea     r9, [rsp+1B0h+var_168]
0x180026497  mov     ecx, 4001h
0x18002649c  call    LdrLoadDll
0x1800264a1  mov     ebx, eax
0x1800264a3  test    eax, eax
0x1800264a5  js      loc_18002657E
0x1800264ab  call    LdrpCodeAuthzInitialize
0x1800264b0  mov     ecx, 80000000h
0x1800264b5  mov     ebx, eax
0x1800264b7  add     eax, ecx
0x1800264b9  test    ecx, eax
0x1800264bb  jz      loc_180026560
0x1800264c1  mov     rax, [rbp+0B8h]
0x1800264c8  lea     r9, [rsp+1B0h+var_158]
0x1800264cd  mov     rcx, [rsp+1B0h+var_168]
0x1800264d2  lea     rdx, qword_180170300
0x1800264d9  mov     qword ptr [rsp+1B0h+ArgList], rax
0x1800264de  xor     r8d, r8d
0x1800264e1  mov     dword ptr [rsp+1B0h+Format], 0
0x1800264e9  call    LdrGetProcedureAddressForCaller
0x1800264ee  mov     ebx, eax
0x1800264f0  test    eax, eax
0x1800264f2  js      short loc_180026516
0x1800264f4  mov     rax, [rsp+1B0h+var_158]
0x1800264f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264fe  mov     ebx, eax
0x180026500  test    eax, eax
0x180026502  jns     short loc_180026541
0x180026504  mov     dword ptr [rsp+1B0h+ArgList], eax
0x180026508  mov     edx, 8F8h
0x18002650d  lea     rax, aCallingKernelb; "Calling KernelbasePostInit failed with "...
0x180026514  jmp     short loc_180026526
0x180026516  mov     dword ptr [rsp+1B0h+ArgList], eax; ArgList
0x18002651a  mov     edx, 8EFh; int
0x18002651f  lea     rax, aFindingKernelb; "Finding KernelbasePostInit failed with "...
0x180026526  xor     r9d, r9d; int
0x180026529  mov     [rsp+1B0h+Format], rax; Format
0x18002652e  lea     r8, aLdrpinitialize_6; "LdrpInitializeKernel32Functions"
0x180026535  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18002653c  call    LdrpLogInternal
0x180026541  mov     eax, ebx
0x180026543  mov     rcx, [rbp+0B0h+var_40]
0x180026547  xor     rcx, rsp; StackCookie
0x18002654a  call    __security_check_cookie
0x18002654f  add     rsp, 188h
0x180026556  pop     r15
0x180026558  pop     r12
0x18002655a  pop     rdi
0x18002655b  pop     rsi
0x18002655c  pop     rbx
0x18002655d  pop     rbp
0x18002655e  retn
0x180026560  cmp     ebx, 0C0000135h
0x180026566  jz      loc_1800264C1
0x18002656c  mov     dword ptr [rsp+1B0h+ArgList], ebx
0x180026570  lea     rax, aLdrpcodeauthzi; "LdrpCodeAuthzInitialize failed with sta"...
0x180026577  mov     edx, 8DDh
0x18002657c  jmp     short loc_180026526
0x18002657e  mov     dword ptr [rsp+1B0h+var_180], eax
0x180026582  mov     edx, 8CDh; int
0x180026587  mov     qword ptr [rsp+1B0h+ArgList], rdi; ArgList
0x18002658c  lea     rax, aLoadingWindows; "Loading Windows subsystem DLL \"%wZ\" f"...
0x180026593  xor     r9d, r9d; int
0x180026596  lea     r8, aLdrpinitialize_6; "LdrpInitializeKernel32Functions"
0x18002659d  mov     [rsp+1B0h+Format], rax; Format
0x1800265a2  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800265a9  call    LdrpLogInternal
0x1800265ae  jmp     short loc_180026541
0x1800265b0  mov     dword ptr [rsp+1B0h+var_180], eax
0x1800265b4  mov     edx, 875h
0x1800265b9  mov     qword ptr [rsp+1B0h+ArgList], r15
0x1800265be  jmp     short loc_18002658C
0x1800265c0  mov     [rsp+1B0h+var_178], eax
0x1800265c4  lea     r8, aLdrpinitialize_6; "LdrpInitializeKernel32Functions"
0x1800265cb  mov     [rsp+1B0h+var_180], r15
0x1800265d0  lea     rax, aLocatingProced; "Locating procedure \"%Z\" in Windows su"...
0x1800265d7  mov     qword ptr [rsp+1B0h+ArgList], r12; ArgList
0x1800265dc  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800265e3  xor     r9d, r9d; int
0x1800265e6  mov     [rsp+1B0h+Format], rax; Format
0x1800265eb  mov     edx, 88Ch; int
0x1800265f0  call    LdrpLogInternal
0x1800265f5  jmp     loc_180026541
```
