# CpuInfo::ReloadCpuInfoImpl(void)

- ea: `0x18001d258`
- end: `0x18001d492`
- name: `?ReloadCpuInfoImpl@CpuInfo@@AEAAXXZ`
- size: `570`
- prototype: `void __fastcall(CpuInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a180`

## callees

- `0x18001d1a8`
- `0x18001d258`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d2e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d2e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d302`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d302`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x18001d28d`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x18001d28d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d2d0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d2d0`

## string_xrefs

- `0x18001d2c9`: `kernel32.dll`

## pseudocode

```c
void __fastcall CpuInfo::ReloadCpuInfoImpl(CpuInfo *this)
{
  __int16 DisabledFeaturesFromRegistry; // si
  __int64 v2; // rbx
  char v3; // di
  DWORD v4; // ecx
  char v5; // r8
  char v6; // r9
  HMODULE LibraryW; // rax
  HMODULE v8; // rbx
  __int64 (*ProcAddress)(void); // rax
  char v24; // bl
  char v25; // cl
  bool v26; // al
  bool v27; // al
  bool v28; // al
  bool v29; // al
  bool v30; // al
  bool v31; // al
  bool v32; // al
  bool v33; // al
  bool v34; // al

  DisabledFeaturesFromRegistry = LoadDisabledFeaturesFromRegistry();
  if ( (~DisabledFeaturesFromRegistry & 0x3FF) != 0 )
  {
    v2 = 0;
    v3 = 1;
    do
    {
      v4 = CpuInfo::s_cpuInfo[2 * v2 + 2];
      if ( v4 != -1 )
        LOBYTE(CpuInfo::s_cpuInfo[2 * v2 + 1]) = IsProcessorFeaturePresent(v4);
      ++v2;
    }
    while ( v2 != 10 );
    v5 = 0;
    v6 = 0;
    byte_180044CAC = 0;
    byte_180044CB4 = 0;
    byte_180044CC4 = 0;
    if ( !byte_180044CF0 )
    {
      LibraryW = LoadLibraryW(L"kernel32.dll");
      v8 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "GetEnabledXStateFeatures");
        if ( ProcAddress )
          qword_180044CE8 = ProcAddress();
        FreeLibrary(v8);
      }
      v5 = byte_180044CB4;
      v6 = byte_180044CAC;
      byte_180044CF0 = 1;
    }
    _RAX = 0;
    __asm { cpuid }
    if ( (int)_RAX >= 1 )
    {
      _RAX = 1;
      __asm { cpuid }
      v6 = (_RCX & 0x80000) != 0;
      v5 = (_RCX & 0x100000) != 0;
    }
    if ( (int)_RAX < 7 )
    {
      v25 = byte_180044CDC;
      v24 = byte_180044CCC;
    }
    else
    {
      _RAX = 7;
      __asm { cpuid }
      v24 = (_RBX & 0x20) != 0;
      v25 = (qword_180044CE8 & 0xE0) != 0 && (_RCX & 2) != 0;
    }
    v26 = byte_180044C94 && (DisabledFeaturesFromRegistry & 1) == 0;
    byte_180044C94 = v26;
    v27 = byte_180044C9C && (DisabledFeaturesFromRegistry & 2) == 0;
    byte_180044C9C = v27;
    v28 = byte_180044CA4 && (DisabledFeaturesFromRegistry & 4) == 0;
    byte_180044CA4 = v28;
    v29 = v6 && (DisabledFeaturesFromRegistry & 8) == 0;
    byte_180044CAC = v29;
    v30 = v5 && (DisabledFeaturesFromRegistry & 0x10) == 0;
    byte_180044CB4 = v30;
    v31 = byte_180044CBC && (DisabledFeaturesFromRegistry & 0x20) == 0;
    byte_180044CBC = v31;
    v32 = (qword_180044CE8 & 4) != 0 && (DisabledFeaturesFromRegistry & 0x40) == 0;
    byte_180044CC4 = v32;
    v33 = v24 && (DisabledFeaturesFromRegistry & 0x80u) == 0;
    byte_180044CCC = v33;
    v34 = (qword_180044CE8 & 0xE0) != 0 && (DisabledFeaturesFromRegistry & 0x100) == 0;
    byte_180044CD4 = v34;
    if ( !v25 || (DisabledFeaturesFromRegistry & 0x200) != 0 )
      v3 = 0;
    byte_180044CDC = v3;
  }
}

```

## disassembly

```asm
0x18001d258  push    rbx
0x18001d25a  push    rbp
0x18001d25b  push    rsi
0x18001d25c  push    rdi
0x18001d25d  sub     rsp, 38h
0x18001d261  call    ?LoadDisabledFeaturesFromRegistry@@YAIXZ; LoadDisabledFeaturesFromRegistry(void)
0x18001d266  mov     ecx, eax
0x18001d268  mov     esi, eax
0x18001d26a  not     ecx
0x18001d26c  test    ecx, 3FFh
0x18001d272  jz      loc_18001D489
0x18001d278  xor     ebx, ebx
0x18001d27a  lea     rbp, ?s_cpuInfo@CpuInfo@@0V1@A; CpuInfo CpuInfo::s_cpuInfo
0x18001d281  lea     edi, [rbx+1]
0x18001d284  mov     ecx, [rbp+rbx*8+8]; ProcessorFeature
0x18001d288  cmp     ecx, 0FFFFFFFFh
0x18001d28b  jz      short loc_18001D29C
0x18001d28d  call    cs:__imp_IsProcessorFeaturePresent
0x18001d293  test    eax, eax
0x18001d295  setnz   al
0x18001d298  mov     [rbp+rbx*8+4], al
0x18001d29c  add     rbx, rdi
0x18001d29f  cmp     rbx, 0Ah
0x18001d2a3  jnz     short loc_18001D284
0x18001d2a5  xor     r8b, r8b
0x18001d2a8  xor     r9b, r9b
0x18001d2ab  cmp     cs:byte_180044CF0, r8b
0x18001d2b2  mov     cs:byte_180044CAC, r9b
0x18001d2b9  mov     cs:byte_180044CB4, r8b
0x18001d2c0  mov     cs:byte_180044CC4, r8b
0x18001d2c7  jnz     short loc_18001D31D
0x18001d2c9  lea     rcx, LibFileName; "kernel32.dll"
0x18001d2d0  call    cs:__imp_LoadLibraryW
0x18001d2d6  mov     rbx, rax
0x18001d2d9  test    rax, rax
0x18001d2dc  jz      short loc_18001D308
0x18001d2de  lea     rdx, aGetenabledxsta; "GetEnabledXStateFeatures"
0x18001d2e5  mov     rcx, rax; hModule
0x18001d2e8  call    cs:__imp_GetProcAddress
0x18001d2ee  test    rax, rax
0x18001d2f1  jz      short loc_18001D2FF
0x18001d2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f8  mov     cs:qword_180044CE8, rax
0x18001d2ff  mov     rcx, rbx; hLibModule
0x18001d302  call    cs:__imp_FreeLibrary
0x18001d308  mov     r8b, cs:byte_180044CB4
0x18001d30f  mov     r9b, cs:byte_180044CAC
0x18001d316  mov     cs:byte_180044CF0, dil
0x18001d31d  mov     r10, cs:qword_180044CE8
0x18001d324  mov     r11b, r10b
0x18001d327  shr     r11b, 2
0x18001d32b  and     r11b, dil
0x18001d32e  and     r10d, 0E0h
0x18001d335  setnz   bpl
0x18001d339  xor     eax, eax
0x18001d33b  xor     ecx, ecx
0x18001d33d  cpuid
0x18001d33f  cmp     eax, edi
0x18001d341  jl      short loc_18001D35D
0x18001d343  xor     ecx, ecx
0x18001d345  mov     eax, edi
0x18001d347  cpuid
0x18001d349  mov     r9d, ecx
0x18001d34c  mov     r8d, ecx
0x18001d34f  shr     r9d, 13h
0x18001d353  and     r9b, dil
0x18001d356  shr     r8d, 14h
0x18001d35a  and     r8b, dil
0x18001d35d  cmp     eax, 7
0x18001d360  jl      short loc_18001D384
0x18001d362  xor     ecx, ecx
0x18001d364  mov     eax, 7
0x18001d369  cpuid
0x18001d36b  shr     ebx, 5
0x18001d36e  and     bl, dil
0x18001d371  test    r10, r10
0x18001d374  jz      short loc_18001D380
0x18001d376  test    cl, 2
0x18001d379  jz      short loc_18001D380
0x18001d37b  mov     cl, dil
0x18001d37e  jmp     short loc_18001D390
0x18001d380  xor     cl, cl
0x18001d382  jmp     short loc_18001D390
0x18001d384  mov     cl, cs:byte_180044CDC
0x18001d38a  mov     bl, cs:byte_180044CCC
0x18001d390  cmp     cs:byte_180044C94, 0
0x18001d397  jz      short loc_18001D3A3
0x18001d399  test    dil, sil
0x18001d39c  jnz     short loc_18001D3A3
0x18001d39e  mov     al, dil
0x18001d3a1  jmp     short loc_18001D3A5
0x18001d3a3  xor     al, al
0x18001d3a5  cmp     cs:byte_180044C9C, 0
0x18001d3ac  mov     cs:byte_180044C94, al
0x18001d3b2  jz      short loc_18001D3BF
0x18001d3b4  test    sil, 2
0x18001d3b8  jnz     short loc_18001D3BF
0x18001d3ba  mov     al, dil
0x18001d3bd  jmp     short loc_18001D3C1
0x18001d3bf  xor     al, al
0x18001d3c1  cmp     cs:byte_180044CA4, 0
0x18001d3c8  mov     cs:byte_180044C9C, al
0x18001d3ce  jz      short loc_18001D3DB
0x18001d3d0  test    sil, 4
0x18001d3d4  jnz     short loc_18001D3DB
0x18001d3d6  mov     al, dil
0x18001d3d9  jmp     short loc_18001D3DD
0x18001d3db  xor     al, al
0x18001d3dd  mov     cs:byte_180044CA4, al
0x18001d3e3  test    r9b, r9b
0x18001d3e6  jz      short loc_18001D3F3
0x18001d3e8  test    sil, 8
0x18001d3ec  jnz     short loc_18001D3F3
0x18001d3ee  mov     al, dil
0x18001d3f1  jmp     short loc_18001D3F5
0x18001d3f3  xor     al, al
0x18001d3f5  mov     cs:byte_180044CAC, al
0x18001d3fb  test    r8b, r8b
0x18001d3fe  jz      short loc_18001D40B
0x18001d400  test    sil, 10h
0x18001d404  jnz     short loc_18001D40B
0x18001d406  mov     al, dil
0x18001d409  jmp     short loc_18001D40D
0x18001d40b  xor     al, al
0x18001d40d  cmp     cs:byte_180044CBC, 0
0x18001d414  mov     cs:byte_180044CB4, al
0x18001d41a  jz      short loc_18001D427
0x18001d41c  test    sil, 20h
0x18001d420  jnz     short loc_18001D427
0x18001d422  mov     al, dil
0x18001d425  jmp     short loc_18001D429
0x18001d427  xor     al, al
0x18001d429  mov     cs:byte_180044CBC, al
0x18001d42f  test    r11b, r11b
0x18001d432  jz      short loc_18001D43F
0x18001d434  test    sil, 40h
0x18001d438  jnz     short loc_18001D43F
0x18001d43a  mov     al, dil
0x18001d43d  jmp     short loc_18001D441
0x18001d43f  xor     al, al
0x18001d441  mov     cs:byte_180044CC4, al
0x18001d447  test    bl, bl
0x18001d449  jz      short loc_18001D455
0x18001d44b  test    sil, sil
0x18001d44e  js      short loc_18001D455
0x18001d450  mov     al, dil
0x18001d453  jmp     short loc_18001D457
0x18001d455  xor     al, al
0x18001d457  mov     cs:byte_180044CCC, al
0x18001d45d  test    bpl, bpl
0x18001d460  jz      short loc_18001D46D
0x18001d462  bt      esi, 8
0x18001d466  jb      short loc_18001D46D
0x18001d468  mov     al, dil
0x18001d46b  jmp     short loc_18001D46F
0x18001d46d  xor     al, al
0x18001d46f  mov     cs:byte_180044CD4, al
0x18001d475  test    cl, cl
0x18001d477  jz      short loc_18001D47F
0x18001d479  bt      esi, 9
0x18001d47d  jnb     short loc_18001D482
0x18001d47f  xor     dil, dil
0x18001d482  mov     cs:byte_180044CDC, dil
0x18001d489  add     rsp, 38h
0x18001d48d  pop     rdi
0x18001d48e  pop     rsi
0x18001d48f  pop     rbp
0x18001d490  pop     rbx
0x18001d491  retn
```
