# LdrpInitShimEngine

- ea: `0x1800bfe70`
- end: `0x1800c0080`
- name: `LdrpInitShimEngine`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180050718`

## callees

- `0x18001861c`
- `0x18001d490`
- `0x18001eb80`
- `0x180023e10`
- `0x180024ea0`
- `0x18002b9f0`
- `0x18002c35c`
- `0x1800709e0`
- `0x1800bfe70`
- `0x1800c0e80`
- `0x1800c19c0`
- `0x1800c1c4c`
- `0x180162810`
- `0x18016f020`
- `0x18016f030`

## string_xrefs

- `0x1800bfea1`: `apphelp.dll`
- `0x1800bff7b`: `Loading the shim engine DLL failed with status 0x%08lx\n`
- `0x1800bff1b`: `Building shim engine DLL system32 filename failed with status 0x%08lx\n`

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
0x1800bfe70  push    rbp
0x1800bfe72  push    rbx
0x1800bfe73  push    rsi
0x1800bfe74  push    rdi
0x1800bfe75  lea     rbp, [rsp-308h]
0x1800bfe7d  sub     rsp, 408h
0x1800bfe84  mov     rax, cs:__security_cookie
0x1800bfe8b  xor     rax, rsp
0x1800bfe8e  mov     [rbp+320h+var_30], rax
0x1800bfe95  mov     rdi, rcx
0x1800bfe98  mov     [rsp+420h+var_3D8], 180016h
0x1800bfea1  lea     rax, aApphelpDll; "apphelp.dll"
0x1800bfea8  xor     edx, edx; Val
0x1800bfeaa  lea     rcx, [rbp+320h+var_2B0]; void *
0x1800bfeae  mov     [rsp+420h+var_3D0], rax
0x1800bfeb3  mov     r8d, 80h; Size
0x1800bfeb9  call    memset$thunk$772440563353939046
0x1800bfebe  xor     edx, edx; Val
0x1800bfec0  mov     [rsp+420h+var_3E0], 0
0x1800bfec9  mov     r8d, 110h; Size
0x1800bfecf  lea     rcx, [rsp+420h+var_3C0]; void *
0x1800bfed4  call    memset$thunk$772440563353939046
0x1800bfed9  lea     rax, [rsp+420h+var_3B0]
0x1800bfede  mov     dword ptr [rsp+420h+var_3C0], 1000000h
0x1800bfee6  mov     [rsp+420h+var_3B8], rax
0x1800bfeeb  lea     rdx, [rsp+420h+var_3D8]
0x1800bfef0  xor     eax, eax
0x1800bfef2  lea     rcx, [rsp+420h+var_3C0]
0x1800bfef7  xorps   xmm0, xmm0
0x1800bfefa  mov     [rsp+420h+var_3B0], ax
0x1800bfeff  movups  xmmword ptr [rsp+420h+SourceString], xmm0
0x1800bff04  mov     esi, 100h
0x1800bff09  call    LdrpBuildSystem32FileName
0x1800bff0e  test    eax, eax
0x1800bff10  jns     short loc_1800BFF42
0x1800bff12  mov     dword ptr [rsp+420h+ArgList], eax; ArgList
0x1800bff16  mov     edx, 0E81h; int
0x1800bff1b  lea     rax, aBuildingShimEn; "Building shim engine DLL system32 filen"...
0x1800bff22  xor     r9d, r9d; int
0x1800bff25  mov     [rsp+420h+Format], rax; Format
0x1800bff2a  lea     r8, aLdrpinitshimen; "LdrpInitShimEngine"
0x1800bff31  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bff38  call    LdrpLogInternal
0x1800bff3d  jmp     loc_1800C0050
0x1800bff42  lea     r8, [rbp+320h+var_2B0]
0x1800bff46  mov     edx, 4001h
0x1800bff4b  xor     ecx, ecx
0x1800bff4d  call    LdrpInitializeDllPath
0x1800bff52  lea     r9, [rsp+420h+var_3E0]
0x1800bff57  xor     r8d, r8d
0x1800bff5a  lea     rdx, [rbp+320h+var_2B0]
0x1800bff5e  lea     rcx, [rsp+420h+var_3C0]; ArgList
0x1800bff63  call    LdrpLoadDll
0x1800bff68  lea     rcx, [rbp+320h+var_2B0]
0x1800bff6c  mov     ebx, eax
0x1800bff6e  call    LdrpReleaseDllPath
0x1800bff73  test    ebx, ebx
0x1800bff75  jns     short loc_1800BFF89
0x1800bff77  mov     dword ptr [rsp+420h+ArgList], ebx
0x1800bff7b  lea     rax, aLoadingTheShim_1; "Loading the shim engine DLL failed with"...
0x1800bff82  mov     edx, 0E94h
0x1800bff87  jmp     short loc_1800BFF22
0x1800bff89  mov     rbx, [rsp+420h+var_3E0]
0x1800bff8e  mov     rcx, rbx
0x1800bff91  mov     eax, [rbx+68h]
0x1800bff94  or      eax, esi
0x1800bff96  mov     [rbx+68h], eax
0x1800bff99  mov     rax, [rbx+30h]
0x1800bff9d  mov     cs:g_pShimEngineModule, rax
0x1800bffa4  call    LdrpPinModule
0x1800bffa9  mov     rcx, rbx
0x1800bffac  call    LdrpDereferenceModule
0x1800bffb1  call    LdrpGetShimEngineInterface
0x1800bffb6  test    eax, eax
0x1800bffb8  jns     short loc_1800BFFCF
0x1800bffba  mov     dword ptr [rsp+420h+ArgList], eax
0x1800bffbe  mov     edx, 0EA2h
0x1800bffc3  lea     rax, aGettingTheShim; "Getting the shim engine exports failed "...
0x1800bffca  jmp     loc_1800BFF22
0x1800bffcf  mov     r9, cs:g_pfnSE_InitializeEngine
0x1800bffd6  lea     rax, [rbp+320h+var_230]
0x1800bffdd  mov     [rsp+420h+SourceString+8], rax
0x1800bffe2  mov     ecx, 40h ; '@'
0x1800bffe7  mov     dword ptr [rsp+420h+SourceString], 2000000h
0x1800bffef  mov     r8, rdi
0x1800bfff2  mov     eax, ds:7FFE0330h
0x1800bfff9  mov     edx, eax
0x1800bfffb  and     edx, 3Fh
0x1800bfffe  sub     ecx, edx
0x1800c0000  mov     rdx, cs:LdrpImageEntry
0x1800c0007  ror     r9, cl
0x1800c000a  add     rdx, 48h ; 'H'
0x1800c000e  xor     rax, r9
0x1800c0011  lea     rcx, [rsp+420h+SourceString]
0x1800c0016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c001b  test    eax, eax
0x1800c001d  js      short loc_1800C0050
0x1800c001f  mov     rcx, [rsp+420h+SourceString+8]; SourceString
0x1800c0024  call    LdrpLoadShimEngine
0x1800c0029  lea     rax, [rbp+320h+var_230]
0x1800c0030  cmp     [rsp+420h+SourceString+8], rax
0x1800c0035  jz      short loc_1800C0050
0x1800c0037  mov     rcx, gs:60h
0x1800c0040  xor     edx, edx
0x1800c0042  mov     r8, [rsp+420h+SourceString+8]
0x1800c0047  mov     rcx, [rcx+30h]
0x1800c004b  call    RtlFreeHeap_0
0x1800c0050  mov     rcx, [rsp+420h+var_3B8]
0x1800c0055  lea     rax, [rsp+420h+var_3B0]
0x1800c005a  cmp     rax, rcx
0x1800c005d  jz      short loc_1800C0064
0x1800c005f  call    RtlpSysVolFree
0x1800c0064  mov     rcx, [rbp+320h+var_30]
0x1800c006b  xor     rcx, rsp; StackCookie
0x1800c006e  call    __security_check_cookie
0x1800c0073  add     rsp, 408h
0x1800c007a  pop     rdi
0x1800c007b  pop     rsi
0x1800c007c  pop     rbx
0x1800c007d  pop     rbp
0x1800c007e  retn
```
