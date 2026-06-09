# LdrpInitShimEngine

- ea: `0x1800bbb90`
- end: `0x1800bbda0`
- name: `LdrpInitShimEngine`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800d6508`

## callees

- `0x18001861c`
- `0x18001d490`
- `0x18001eb80`
- `0x180023e20`
- `0x180024eb0`
- `0x18002c6f0`
- `0x18002d05c`
- `0x180054000`
- `0x1800bbb90`
- `0x1800bcba0`
- `0x1800bd6e0`
- `0x1800bd96c`
- `0x180162000`
- `0x18016f020`
- `0x18016f030`

## string_xrefs

- `0x1800bbbc1`: `apphelp.dll`
- `0x1800bbc9b`: `Loading the shim engine DLL failed with status 0x%08lx\n`
- `0x1800bbc3b`: `Building shim engine DLL system32 filename failed with status 0x%08lx\n`

## pseudocode

```c
_WORD *__fastcall LdrpInitShimEngine(__int64 a1)
{
  int ArgList; // eax
  int Dll; // ebx
  __int64 v4; // rbx
  __int64 v5; // rcx
  int ShimEngineInterface; // eax
  _WORD *result; // rax
  PCWSTR SourceString[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v10[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v11[4]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v12; // [rsp+68h] [rbp-98h]
  _WORD v13[128]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[128]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v15[512]; // [rsp+1F0h] [rbp+F0h] BYREF

  v10[0] = 1572886;
  v10[1] = L"apphelp.dll";
  memset_thunk_772440563353939046(v14, 0, 0x80u);
  v9 = 0;
  memset_thunk_772440563353939046(v11, 0, 0x110u);
  *(_DWORD *)v11 = 0x1000000;
  v12 = v13;
  v13[0] = 0;
  *(_OWORD *)SourceString = 0;
  ArgList = LdrpBuildSystem32FileName(v11, v10);
  if ( ArgList >= 0 )
  {
    LdrpInitializeDllPath(0, 16385, v14);
    Dll = LdrpLoadDll(v11, (__int64)v14, 0, (__int64)&v9);
    LdrpReleaseDllPath(v14);
    if ( Dll >= 0 )
    {
      v4 = v9;
      v5 = v9;
      *(_DWORD *)(v9 + 104) |= 0x100u;
      g_pShimEngineModule = *(_QWORD *)(v5 + 48);
      LdrpPinModule(v5);
      LdrpDereferenceModule(v4);
      ShimEngineInterface = LdrpGetShimEngineInterface();
      if ( ShimEngineInterface >= 0 )
      {
        SourceString[1] = (PCWSTR)v15;
        LODWORD(SourceString[0]) = 0x2000000;
        if ( ((int (__fastcall *)(PCWSTR *, __int64, __int64))(__ROR8__(
                                                                 g_pfnSE_InitializeEngine,
                                                                 64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                                             ^ MEMORY[0x7FFE0330]))(
               SourceString,
               LdrpImageEntry + 72,
               a1) >= 0 )
        {
          LdrpLoadShimEngine(SourceString[1]);
          if ( (_BYTE *)SourceString[1] != v15 )
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, SourceString[1]);
        }
      }
      else
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          3746,
          (int)"LdrpInitShimEngine",
          0,
          "Getting the shim engine exports failed with status 0x%08lx\n",
          ShimEngineInterface);
      }
    }
    else
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        3732,
        (int)"LdrpInitShimEngine",
        0,
        "Loading the shim engine DLL failed with status 0x%08lx\n",
        Dll);
    }
  }
  else
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      3713,
      (int)"LdrpInitShimEngine",
      0,
      "Building shim engine DLL system32 filename failed with status 0x%08lx\n",
      ArgList);
  }
  result = v13;
  if ( v13 != v12 )
    return (_WORD *)RtlpSysVolFree(v12);
  return result;
}

```

## disassembly

```asm
0x1800bbb90  push    rbp
0x1800bbb92  push    rbx
0x1800bbb93  push    rsi
0x1800bbb94  push    rdi
0x1800bbb95  lea     rbp, [rsp-308h]
0x1800bbb9d  sub     rsp, 408h
0x1800bbba4  mov     rax, cs:__security_cookie
0x1800bbbab  xor     rax, rsp
0x1800bbbae  mov     [rbp+320h+var_30], rax
0x1800bbbb5  mov     rdi, rcx
0x1800bbbb8  mov     [rsp+420h+var_3D8], 180016h
0x1800bbbc1  lea     rax, aApphelpDll; "apphelp.dll"
0x1800bbbc8  xor     edx, edx; Val
0x1800bbbca  lea     rcx, [rbp+320h+var_2B0]; void *
0x1800bbbce  mov     [rsp+420h+var_3D0], rax
0x1800bbbd3  mov     r8d, 80h; Size
0x1800bbbd9  call    memset$thunk$772440563353939046
0x1800bbbde  xor     edx, edx; Val
0x1800bbbe0  mov     [rsp+420h+var_3E0], 0
0x1800bbbe9  mov     r8d, 110h; Size
0x1800bbbef  lea     rcx, [rsp+420h+var_3C0]; void *
0x1800bbbf4  call    memset$thunk$772440563353939046
0x1800bbbf9  lea     rax, [rsp+420h+var_3B0]
0x1800bbbfe  mov     dword ptr [rsp+420h+var_3C0], 1000000h
0x1800bbc06  mov     [rsp+420h+var_3B8], rax
0x1800bbc0b  lea     rdx, [rsp+420h+var_3D8]
0x1800bbc10  xor     eax, eax
0x1800bbc12  lea     rcx, [rsp+420h+var_3C0]
0x1800bbc17  xorps   xmm0, xmm0
0x1800bbc1a  mov     [rsp+420h+var_3B0], ax
0x1800bbc1f  movups  xmmword ptr [rsp+420h+SourceString], xmm0
0x1800bbc24  mov     esi, 100h
0x1800bbc29  call    LdrpBuildSystem32FileName
0x1800bbc2e  test    eax, eax
0x1800bbc30  jns     short loc_1800BBC62
0x1800bbc32  mov     dword ptr [rsp+420h+ArgList], eax; ArgList
0x1800bbc36  mov     edx, 0E81h; int
0x1800bbc3b  lea     rax, aBuildingShimEn; "Building shim engine DLL system32 filen"...
0x1800bbc42  xor     r9d, r9d; int
0x1800bbc45  mov     [rsp+420h+Format], rax; Format
0x1800bbc4a  lea     r8, aLdrpinitshimen; "LdrpInitShimEngine"
0x1800bbc51  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bbc58  call    LdrpLogInternal
0x1800bbc5d  jmp     loc_1800BBD70
0x1800bbc62  lea     r8, [rbp+320h+var_2B0]
0x1800bbc66  mov     edx, 4001h
0x1800bbc6b  xor     ecx, ecx
0x1800bbc6d  call    LdrpInitializeDllPath
0x1800bbc72  lea     r9, [rsp+420h+var_3E0]
0x1800bbc77  xor     r8d, r8d
0x1800bbc7a  lea     rdx, [rbp+320h+var_2B0]
0x1800bbc7e  lea     rcx, [rsp+420h+var_3C0]; ArgList
0x1800bbc83  call    LdrpLoadDll
0x1800bbc88  lea     rcx, [rbp+320h+var_2B0]
0x1800bbc8c  mov     ebx, eax
0x1800bbc8e  call    LdrpReleaseDllPath
0x1800bbc93  test    ebx, ebx
0x1800bbc95  jns     short loc_1800BBCA9
0x1800bbc97  mov     dword ptr [rsp+420h+ArgList], ebx
0x1800bbc9b  lea     rax, aLoadingTheShim_1; "Loading the shim engine DLL failed with"...
0x1800bbca2  mov     edx, 0E94h
0x1800bbca7  jmp     short loc_1800BBC42
0x1800bbca9  mov     rbx, [rsp+420h+var_3E0]
0x1800bbcae  mov     rcx, rbx
0x1800bbcb1  mov     eax, [rbx+68h]
0x1800bbcb4  or      eax, esi
0x1800bbcb6  mov     [rbx+68h], eax
0x1800bbcb9  mov     rax, [rbx+30h]
0x1800bbcbd  mov     cs:g_pShimEngineModule, rax
0x1800bbcc4  call    LdrpPinModule
0x1800bbcc9  mov     rcx, rbx
0x1800bbccc  call    LdrpDereferenceModule
0x1800bbcd1  call    LdrpGetShimEngineInterface
0x1800bbcd6  test    eax, eax
0x1800bbcd8  jns     short loc_1800BBCEF
0x1800bbcda  mov     dword ptr [rsp+420h+ArgList], eax
0x1800bbcde  mov     edx, 0EA2h
0x1800bbce3  lea     rax, aGettingTheShim; "Getting the shim engine exports failed "...
0x1800bbcea  jmp     loc_1800BBC42
0x1800bbcef  mov     r9, cs:g_pfnSE_InitializeEngine
0x1800bbcf6  lea     rax, [rbp+320h+var_230]
0x1800bbcfd  mov     [rsp+420h+SourceString+8], rax
0x1800bbd02  mov     ecx, 40h ; '@'
0x1800bbd07  mov     dword ptr [rsp+420h+SourceString], 2000000h
0x1800bbd0f  mov     r8, rdi
0x1800bbd12  mov     eax, ds:7FFE0330h
0x1800bbd19  mov     edx, eax
0x1800bbd1b  and     edx, 3Fh
0x1800bbd1e  sub     ecx, edx
0x1800bbd20  mov     rdx, cs:LdrpImageEntry
0x1800bbd27  ror     r9, cl
0x1800bbd2a  add     rdx, 48h ; 'H'
0x1800bbd2e  xor     rax, r9
0x1800bbd31  lea     rcx, [rsp+420h+SourceString]
0x1800bbd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd3b  test    eax, eax
0x1800bbd3d  js      short loc_1800BBD70
0x1800bbd3f  mov     rcx, [rsp+420h+SourceString+8]; SourceString
0x1800bbd44  call    LdrpLoadShimEngine
0x1800bbd49  lea     rax, [rbp+320h+var_230]
0x1800bbd50  cmp     [rsp+420h+SourceString+8], rax
0x1800bbd55  jz      short loc_1800BBD70
0x1800bbd57  mov     rcx, gs:60h
0x1800bbd60  xor     edx, edx
0x1800bbd62  mov     r8, [rsp+420h+SourceString+8]
0x1800bbd67  mov     rcx, [rcx+30h]
0x1800bbd6b  call    RtlFreeHeap_0
0x1800bbd70  mov     rcx, [rsp+420h+var_3B8]
0x1800bbd75  lea     rax, [rsp+420h+var_3B0]
0x1800bbd7a  cmp     rax, rcx
0x1800bbd7d  jz      short loc_1800BBD84
0x1800bbd7f  call    RtlpSysVolFree
0x1800bbd84  mov     rcx, [rbp+320h+var_30]
0x1800bbd8b  xor     rcx, rsp; StackCookie
0x1800bbd8e  call    __security_check_cookie
0x1800bbd93  add     rsp, 408h
0x1800bbd9a  pop     rdi
0x1800bbd9b  pop     rsi
0x1800bbd9c  pop     rbx
0x1800bbd9d  pop     rbp
0x1800bbd9e  retn
```
