# LdrpGetProcApphelpCheckModule

- ea: `0x1801060b8`
- end: `0x1801062b8`
- name: `LdrpGetProcApphelpCheckModule`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180105f20`

## callees

- `0x18001d490`
- `0x18001eb80`
- `0x180023e10`
- `0x180024ea0`
- `0x18002b9f0`
- `0x1800c0e80`
- `0x1800c1c4c`
- `0x1801060b8`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1801060e9`: `apphelp.dll`
- `0x1801061dc`: `Loading the shim engine DLL "%wZ" failed with status 0x%08lx\n`

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
0x1801060b8  push    rbp
0x1801060ba  push    rbx
0x1801060bb  push    rsi
0x1801060bc  push    rdi
0x1801060bd  lea     rbp, [rsp-108h]
0x1801060c5  sub     rsp, 208h
0x1801060cc  mov     rax, cs:__security_cookie
0x1801060d3  xor     rax, rsp
0x1801060d6  mov     [rbp+120h+var_30], rax
0x1801060dd  mov     rdi, rcx
0x1801060e0  mov     [rsp+220h+var_1D8], 180016h
0x1801060e9  lea     rax, aApphelpDll; "apphelp.dll"
0x1801060f0  xor     edx, edx; Val
0x1801060f2  lea     rcx, [rbp+120h+var_B0]; void *
0x1801060f6  mov     [rsp+220h+var_1D0], rax
0x1801060fb  mov     r8d, 80h; Size
0x180106101  call    memset$thunk$772440563353939046
0x180106106  xor     edx, edx; Val
0x180106108  mov     [rsp+220h+var_1E0], 0
0x180106111  mov     r8d, 110h; Size
0x180106117  lea     rcx, [rsp+220h+var_1C0]; void *
0x18010611c  call    memset$thunk$772440563353939046
0x180106121  mov     r8, cs:g_pfnApphelpCheckModuleProc
0x180106128  lea     rax, [rsp+220h+var_1B0]
0x18010612d  mov     [rsp+220h+var_1B8], rax
0x180106132  mov     esi, 100h
0x180106137  xor     eax, eax
0x180106139  mov     dword ptr [rsp+220h+var_1C0], 1000000h
0x180106141  mov     [rsp+220h+var_1B0], ax
0x180106146  test    r8, r8
0x180106149  jz      short loc_180106179
0x18010614b  mov     edx, ds:7FFE0330h
0x180106152  mov     ecx, 40h ; '@'
0x180106157  mov     eax, edx
0x180106159  mov     ebx, 0
0x18010615e  and     eax, 3Fh
0x180106161  sub     ecx, eax
0x180106163  mov     eax, 0C0000001h
0x180106168  ror     r8, cl
0x18010616b  xor     rdx, r8
0x18010616e  mov     [rdi], rdx
0x180106171  cmovz   ebx, eax
0x180106174  jmp     loc_18010629A
0x180106179  lea     rdx, [rsp+220h+var_1D8]
0x18010617e  lea     rcx, [rsp+220h+var_1C0]
0x180106183  call    LdrpBuildSystem32FileName
0x180106188  mov     ebx, eax
0x18010618a  test    eax, eax
0x18010618c  js      loc_180106286
0x180106192  lea     r8, [rbp+120h+var_B0]
0x180106196  mov     edx, 4001h
0x18010619b  xor     ecx, ecx
0x18010619d  call    LdrpInitializeDllPath
0x1801061a2  lea     r9, [rsp+220h+var_1E0]
0x1801061a7  xor     r8d, r8d
0x1801061aa  lea     rdx, [rbp+120h+var_B0]
0x1801061ae  lea     rcx, [rsp+220h+var_1C0]; ArgList
0x1801061b3  call    LdrpLoadDll
0x1801061b8  lea     rcx, [rbp+120h+var_B0]
0x1801061bc  mov     ebx, eax
0x1801061be  call    LdrpReleaseDllPath
0x1801061c3  test    ebx, ebx
0x1801061c5  jns     short loc_180106201
0x1801061c7  lea     rax, [rsp+220h+var_1C0]
0x1801061cc  mov     [rsp+220h+var_1F0], ebx
0x1801061d0  mov     qword ptr [rsp+220h+ArgList], rax; ArgList
0x1801061d5  lea     r8, aLdrpgetprocapp; "LdrpGetProcApphelpCheckModule"
0x1801061dc  lea     rax, aLoadingTheShim; "Loading the shim engine DLL \"%wZ\" fai"...
0x1801061e3  xor     r9d, r9d; int
0x1801061e6  mov     edx, 0F9Fh; int
0x1801061eb  mov     [rsp+220h+Format], rax; Format
0x1801061f0  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1801061f7  call    LdrpLogInternal
0x1801061fc  jmp     loc_180106286
0x180106201  mov     rcx, [rsp+220h+var_1E0]
0x180106206  mov     eax, [rcx+68h]
0x180106209  or      eax, esi
0x18010620b  mov     [rcx+68h], eax
0x18010620e  mov     rax, [rsp+220h+var_1E0]
0x180106213  mov     rcx, [rax+30h]
0x180106217  mov     cs:g_pShimEngineModule, rcx
0x18010621e  call    LdrpGetShimEngineInterface
0x180106223  mov     ebx, eax
0x180106225  test    eax, eax
0x180106227  jns     short loc_180106256
0x180106229  mov     dword ptr [rsp+220h+ArgList], eax; ArgList
0x18010622d  lea     r8, aLdrpgetprocapp; "LdrpGetProcApphelpCheckModule"
0x180106234  lea     rax, aGettingTheShim; "Getting the shim engine exports failed "...
0x18010623b  xor     r9d, r9d; int
0x18010623e  mov     edx, 0FAAh; int
0x180106243  mov     [rsp+220h+Format], rax; Format
0x180106248  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18010624f  call    LdrpLogInternal
0x180106254  jmp     short loc_180106286
0x180106256  mov     edx, ds:7FFE0330h
0x18010625d  mov     ecx, 40h ; '@'
0x180106262  mov     eax, edx
0x180106264  mov     ebx, 0C0000001h
0x180106269  and     eax, 3Fh
0x18010626c  sub     ecx, eax
0x18010626e  mov     rax, cs:g_pfnApphelpCheckModuleProc
0x180106275  ror     rax, cl
0x180106278  xor     rdx, rax
0x18010627b  mov     eax, 0
0x180106280  mov     [rdi], rdx
0x180106283  cmovnz  ebx, eax
0x180106286  mov     rcx, [rsp+220h+var_1B8]
0x18010628b  lea     rax, [rsp+220h+var_1B0]
0x180106290  cmp     rax, rcx
0x180106293  jz      short loc_18010629A
0x180106295  call    RtlpSysVolFree
0x18010629a  mov     eax, ebx
0x18010629c  mov     rcx, [rbp+120h+var_30]
0x1801062a3  xor     rcx, rsp; StackCookie
0x1801062a6  call    __security_check_cookie
0x1801062ab  add     rsp, 208h
0x1801062b2  pop     rdi
0x1801062b3  pop     rsi
0x1801062b4  pop     rbx
0x1801062b5  pop     rbp
0x1801062b6  retn
```
