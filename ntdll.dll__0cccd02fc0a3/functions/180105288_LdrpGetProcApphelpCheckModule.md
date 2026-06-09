# LdrpGetProcApphelpCheckModule

- ea: `0x180105288`
- end: `0x180105488`
- name: `LdrpGetProcApphelpCheckModule`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1801050f0`

## callees

- `0x18001d490`
- `0x18001eb80`
- `0x180023e20`
- `0x180024eb0`
- `0x18002c6f0`
- `0x1800bcba0`
- `0x1800bd96c`
- `0x180105288`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1801052b9`: `apphelp.dll`
- `0x1801053ac`: `Loading the shim engine DLL "%wZ" failed with status 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall LdrpGetProcApphelpCheckModule(_QWORD *a1)
{
  int Dll; // ebx
  __int64 v3; // rdx
  int ArgList; // eax
  __int64 v5; // rdx
  __int64 v7; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v8[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v9[4]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v10; // [rsp+68h] [rbp-98h]
  _WORD v11[128]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v12[16]; // [rsp+170h] [rbp+70h] BYREF

  v8[0] = 1572886;
  v8[1] = L"apphelp.dll";
  memset_thunk_772440563353939046(v12, 0, 0x80u);
  v7 = 0;
  memset_thunk_772440563353939046(v9, 0, 0x110u);
  v10 = v11;
  *(_DWORD *)v9 = 0x1000000;
  v11[0] = 0;
  if ( g_pfnApphelpCheckModuleProc )
  {
    Dll = 0;
    v3 = __ROR8__(g_pfnApphelpCheckModuleProc, 64 - (MEMORY[0x7FFE0330] & 0x3Fu)) ^ MEMORY[0x7FFE0330];
    *a1 = v3;
    if ( !v3 )
      return (unsigned int)-1073741823;
  }
  else
  {
    Dll = LdrpBuildSystem32FileName(v9, v8);
    if ( Dll >= 0 )
    {
      LdrpInitializeDllPath(0, 16385, v12);
      Dll = LdrpLoadDll(v9, (__int64)v12, 0, (__int64)&v7);
      LdrpReleaseDllPath(v12);
      if ( Dll >= 0 )
      {
        *(_DWORD *)(v7 + 104) |= 0x100u;
        g_pShimEngineModule = *(_QWORD *)(v7 + 48);
        ArgList = LdrpGetShimEngineInterface();
        Dll = ArgList;
        if ( ArgList >= 0 )
        {
          Dll = -1073741823;
          v5 = __ROR8__(g_pfnApphelpCheckModuleProc, 64 - (MEMORY[0x7FFE0330] & 0x3Fu)) ^ MEMORY[0x7FFE0330];
          *a1 = v5;
          if ( v5 )
            Dll = 0;
        }
        else
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrinit.c",
            4010,
            (int)"LdrpGetProcApphelpCheckModule",
            0,
            "Getting the shim engine exports failed with status 0x%08lx\n",
            ArgList);
        }
      }
      else
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          3999,
          (int)"LdrpGetProcApphelpCheckModule",
          0,
          "Loading the shim engine DLL \"%wZ\" failed with status 0x%08lx\n",
          (char)v9);
      }
    }
    if ( v11 != v10 )
      RtlpSysVolFree(v10);
  }
  return (unsigned int)Dll;
}

```

## disassembly

```asm
0x180105288  push    rbp
0x18010528a  push    rbx
0x18010528b  push    rsi
0x18010528c  push    rdi
0x18010528d  lea     rbp, [rsp-108h]
0x180105295  sub     rsp, 208h
0x18010529c  mov     rax, cs:__security_cookie
0x1801052a3  xor     rax, rsp
0x1801052a6  mov     [rbp+120h+var_30], rax
0x1801052ad  mov     rdi, rcx
0x1801052b0  mov     [rsp+220h+var_1D8], 180016h
0x1801052b9  lea     rax, aApphelpDll; "apphelp.dll"
0x1801052c0  xor     edx, edx; Val
0x1801052c2  lea     rcx, [rbp+120h+var_B0]; void *
0x1801052c6  mov     [rsp+220h+var_1D0], rax
0x1801052cb  mov     r8d, 80h; Size
0x1801052d1  call    memset$thunk$772440563353939046
0x1801052d6  xor     edx, edx; Val
0x1801052d8  mov     [rsp+220h+var_1E0], 0
0x1801052e1  mov     r8d, 110h; Size
0x1801052e7  lea     rcx, [rsp+220h+var_1C0]; void *
0x1801052ec  call    memset$thunk$772440563353939046
0x1801052f1  mov     r8, cs:g_pfnApphelpCheckModuleProc
0x1801052f8  lea     rax, [rsp+220h+var_1B0]
0x1801052fd  mov     [rsp+220h+var_1B8], rax
0x180105302  mov     esi, 100h
0x180105307  xor     eax, eax
0x180105309  mov     dword ptr [rsp+220h+var_1C0], 1000000h
0x180105311  mov     [rsp+220h+var_1B0], ax
0x180105316  test    r8, r8
0x180105319  jz      short loc_180105349
0x18010531b  mov     edx, ds:7FFE0330h
0x180105322  mov     ecx, 40h ; '@'
0x180105327  mov     eax, edx
0x180105329  mov     ebx, 0
0x18010532e  and     eax, 3Fh
0x180105331  sub     ecx, eax
0x180105333  mov     eax, 0C0000001h
0x180105338  ror     r8, cl
0x18010533b  xor     rdx, r8
0x18010533e  mov     [rdi], rdx
0x180105341  cmovz   ebx, eax
0x180105344  jmp     loc_18010546A
0x180105349  lea     rdx, [rsp+220h+var_1D8]
0x18010534e  lea     rcx, [rsp+220h+var_1C0]
0x180105353  call    LdrpBuildSystem32FileName
0x180105358  mov     ebx, eax
0x18010535a  test    eax, eax
0x18010535c  js      loc_180105456
0x180105362  lea     r8, [rbp+120h+var_B0]
0x180105366  mov     edx, 4001h
0x18010536b  xor     ecx, ecx
0x18010536d  call    LdrpInitializeDllPath
0x180105372  lea     r9, [rsp+220h+var_1E0]
0x180105377  xor     r8d, r8d
0x18010537a  lea     rdx, [rbp+120h+var_B0]
0x18010537e  lea     rcx, [rsp+220h+var_1C0]; ArgList
0x180105383  call    LdrpLoadDll
0x180105388  lea     rcx, [rbp+120h+var_B0]
0x18010538c  mov     ebx, eax
0x18010538e  call    LdrpReleaseDllPath
0x180105393  test    ebx, ebx
0x180105395  jns     short loc_1801053D1
0x180105397  lea     rax, [rsp+220h+var_1C0]
0x18010539c  mov     [rsp+220h+var_1F0], ebx
0x1801053a0  mov     qword ptr [rsp+220h+ArgList], rax; ArgList
0x1801053a5  lea     r8, aLdrpgetprocapp; "LdrpGetProcApphelpCheckModule"
0x1801053ac  lea     rax, aLoadingTheShim; "Loading the shim engine DLL \"%wZ\" fai"...
0x1801053b3  xor     r9d, r9d; int
0x1801053b6  mov     edx, 0F9Fh; int
0x1801053bb  mov     [rsp+220h+Format], rax; Format
0x1801053c0  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1801053c7  call    LdrpLogInternal
0x1801053cc  jmp     loc_180105456
0x1801053d1  mov     rcx, [rsp+220h+var_1E0]
0x1801053d6  mov     eax, [rcx+68h]
0x1801053d9  or      eax, esi
0x1801053db  mov     [rcx+68h], eax
0x1801053de  mov     rax, [rsp+220h+var_1E0]
0x1801053e3  mov     rcx, [rax+30h]
0x1801053e7  mov     cs:g_pShimEngineModule, rcx
0x1801053ee  call    LdrpGetShimEngineInterface
0x1801053f3  mov     ebx, eax
0x1801053f5  test    eax, eax
0x1801053f7  jns     short loc_180105426
0x1801053f9  mov     dword ptr [rsp+220h+ArgList], eax; ArgList
0x1801053fd  lea     r8, aLdrpgetprocapp; "LdrpGetProcApphelpCheckModule"
0x180105404  lea     rax, aGettingTheShim; "Getting the shim engine exports failed "...
0x18010540b  xor     r9d, r9d; int
0x18010540e  mov     edx, 0FAAh; int
0x180105413  mov     [rsp+220h+Format], rax; Format
0x180105418  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18010541f  call    LdrpLogInternal
0x180105424  jmp     short loc_180105456
0x180105426  mov     edx, ds:7FFE0330h
0x18010542d  mov     ecx, 40h ; '@'
0x180105432  mov     eax, edx
0x180105434  mov     ebx, 0C0000001h
0x180105439  and     eax, 3Fh
0x18010543c  sub     ecx, eax
0x18010543e  mov     rax, cs:g_pfnApphelpCheckModuleProc
0x180105445  ror     rax, cl
0x180105448  xor     rdx, rax
0x18010544b  mov     eax, 0
0x180105450  mov     [rdi], rdx
0x180105453  cmovnz  ebx, eax
0x180105456  mov     rcx, [rsp+220h+var_1B8]
0x18010545b  lea     rax, [rsp+220h+var_1B0]
0x180105460  cmp     rax, rcx
0x180105463  jz      short loc_18010546A
0x180105465  call    RtlpSysVolFree
0x18010546a  mov     eax, ebx
0x18010546c  mov     rcx, [rbp+120h+var_30]
0x180105473  xor     rcx, rsp; StackCookie
0x180105476  call    __security_check_cookie
0x18010547b  add     rsp, 208h
0x180105482  pop     rdi
0x180105483  pop     rsi
0x180105484  pop     rbx
0x180105485  pop     rbp
0x180105486  retn
```
