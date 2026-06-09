# CpuInfo::ReloadCpuInfoImpl(void)

- ea: `0x1800c6de4`
- end: `0x1800c701e`
- name: `?ReloadCpuInfoImpl@CpuInfo@@AEAAXXZ`
- size: `570`
- prototype: `void __fastcall(CpuInfo *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18007d590`
- `0x1800c6d00`

## callees

- `0x1800c6c50`
- `0x1800c6de4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6e74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6e74`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6e8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6e8e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c6e5c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c6e5c`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c6e19`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c6e19`

## string_xrefs

- `0x1800c6e55`: `kernel32.dll`

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
    byte_1801EB85C = 0;
    byte_1801EB864 = 0;
    byte_1801EB874 = 0;
    if ( !byte_1801F0488 )
    {
      LibraryW = LoadLibraryW(L"kernel32.dll");
      v8 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "GetEnabledXStateFeatures");
        if ( ProcAddress )
          qword_1801F0480 = ProcAddress();
        FreeLibrary(v8);
      }
      v5 = byte_1801EB864;
      v6 = byte_1801EB85C;
      byte_1801F0488 = 1;
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
      v25 = byte_1801EB88C;
      v24 = byte_1801EB87C;
    }
    else
    {
      _RAX = 7;
      __asm { cpuid }
      v24 = (_RBX & 0x20) != 0;
      v25 = (qword_1801F0480 & 0xE0) != 0 && (_RCX & 2) != 0;
    }
    v26 = byte_1801EB844 && (DisabledFeaturesFromRegistry & 1) == 0;
    byte_1801EB844 = v26;
    v27 = byte_1801EB84C && (DisabledFeaturesFromRegistry & 2) == 0;
    byte_1801EB84C = v27;
    v28 = byte_1801EB854 && (DisabledFeaturesFromRegistry & 4) == 0;
    byte_1801EB854 = v28;
    v29 = v6 && (DisabledFeaturesFromRegistry & 8) == 0;
    byte_1801EB85C = v29;
    v30 = v5 && (DisabledFeaturesFromRegistry & 0x10) == 0;
    byte_1801EB864 = v30;
    v31 = byte_1801EB86C && (DisabledFeaturesFromRegistry & 0x20) == 0;
    byte_1801EB86C = v31;
    v32 = (qword_1801F0480 & 4) != 0 && (DisabledFeaturesFromRegistry & 0x40) == 0;
    byte_1801EB874 = v32;
    v33 = v24 && (DisabledFeaturesFromRegistry & 0x80u) == 0;
    byte_1801EB87C = v33;
    v34 = (qword_1801F0480 & 0xE0) != 0 && (DisabledFeaturesFromRegistry & 0x100) == 0;
    byte_1801EB884 = v34;
    if ( !v25 || (DisabledFeaturesFromRegistry & 0x200) != 0 )
      v3 = 0;
    byte_1801EB88C = v3;
  }
}

```

## disassembly

```asm
0x1800c6de4  push    rbx
0x1800c6de6  push    rbp
0x1800c6de7  push    rsi
0x1800c6de8  push    rdi
0x1800c6de9  sub     rsp, 38h
0x1800c6ded  call    ?LoadDisabledFeaturesFromRegistry@@YAIXZ; LoadDisabledFeaturesFromRegistry(void)
0x1800c6df2  mov     ecx, eax
0x1800c6df4  mov     esi, eax
0x1800c6df6  not     ecx
0x1800c6df8  test    ecx, 3FFh
0x1800c6dfe  jz      loc_1800C7015
0x1800c6e04  xor     ebx, ebx
0x1800c6e06  lea     rbp, ?s_cpuInfo@CpuInfo@@0V1@A; CpuInfo CpuInfo::s_cpuInfo
0x1800c6e0d  lea     edi, [rbx+1]
0x1800c6e10  mov     ecx, [rbp+rbx*8+8]; ProcessorFeature
0x1800c6e14  cmp     ecx, 0FFFFFFFFh
0x1800c6e17  jz      short loc_1800C6E28
0x1800c6e19  call    cs:__imp_IsProcessorFeaturePresent
0x1800c6e1f  test    eax, eax
0x1800c6e21  setnz   al
0x1800c6e24  mov     [rbp+rbx*8+4], al
0x1800c6e28  add     rbx, rdi
0x1800c6e2b  cmp     rbx, 0Ah
0x1800c6e2f  jnz     short loc_1800C6E10
0x1800c6e31  xor     r8b, r8b
0x1800c6e34  xor     r9b, r9b
0x1800c6e37  cmp     cs:byte_1801F0488, r8b
0x1800c6e3e  mov     cs:byte_1801EB85C, r9b
0x1800c6e45  mov     cs:byte_1801EB864, r8b
0x1800c6e4c  mov     cs:byte_1801EB874, r8b
0x1800c6e53  jnz     short loc_1800C6EA9
0x1800c6e55  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800c6e5c  call    cs:__imp_LoadLibraryW
0x1800c6e62  mov     rbx, rax
0x1800c6e65  test    rax, rax
0x1800c6e68  jz      short loc_1800C6E94
0x1800c6e6a  lea     rdx, aGetenabledxsta; "GetEnabledXStateFeatures"
0x1800c6e71  mov     rcx, rax; hModule
0x1800c6e74  call    cs:__imp_GetProcAddress
0x1800c6e7a  test    rax, rax
0x1800c6e7d  jz      short loc_1800C6E8B
0x1800c6e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e84  mov     cs:qword_1801F0480, rax
0x1800c6e8b  mov     rcx, rbx; hLibModule
0x1800c6e8e  call    cs:__imp_FreeLibrary
0x1800c6e94  mov     r8b, cs:byte_1801EB864
0x1800c6e9b  mov     r9b, cs:byte_1801EB85C
0x1800c6ea2  mov     cs:byte_1801F0488, dil
0x1800c6ea9  mov     r10, cs:qword_1801F0480
0x1800c6eb0  mov     r11b, r10b
0x1800c6eb3  shr     r11b, 2
0x1800c6eb7  and     r11b, dil
0x1800c6eba  and     r10d, 0E0h
0x1800c6ec1  setnz   bpl
0x1800c6ec5  xor     eax, eax
0x1800c6ec7  xor     ecx, ecx
0x1800c6ec9  cpuid
0x1800c6ecb  cmp     eax, edi
0x1800c6ecd  jl      short loc_1800C6EE9
0x1800c6ecf  xor     ecx, ecx
0x1800c6ed1  mov     eax, edi
0x1800c6ed3  cpuid
0x1800c6ed5  mov     r9d, ecx
0x1800c6ed8  mov     r8d, ecx
0x1800c6edb  shr     r9d, 13h
0x1800c6edf  and     r9b, dil
0x1800c6ee2  shr     r8d, 14h
0x1800c6ee6  and     r8b, dil
0x1800c6ee9  cmp     eax, 7
0x1800c6eec  jl      short loc_1800C6F10
0x1800c6eee  xor     ecx, ecx
0x1800c6ef0  mov     eax, 7
0x1800c6ef5  cpuid
0x1800c6ef7  shr     ebx, 5
0x1800c6efa  and     bl, dil
0x1800c6efd  test    r10, r10
0x1800c6f00  jz      short loc_1800C6F0C
0x1800c6f02  test    cl, 2
0x1800c6f05  jz      short loc_1800C6F0C
0x1800c6f07  mov     cl, dil
0x1800c6f0a  jmp     short loc_1800C6F1C
0x1800c6f0c  xor     cl, cl
0x1800c6f0e  jmp     short loc_1800C6F1C
0x1800c6f10  mov     cl, cs:byte_1801EB88C
0x1800c6f16  mov     bl, cs:byte_1801EB87C
0x1800c6f1c  cmp     cs:byte_1801EB844, 0
0x1800c6f23  jz      short loc_1800C6F2F
0x1800c6f25  test    dil, sil
0x1800c6f28  jnz     short loc_1800C6F2F
0x1800c6f2a  mov     al, dil
0x1800c6f2d  jmp     short loc_1800C6F31
0x1800c6f2f  xor     al, al
0x1800c6f31  cmp     cs:byte_1801EB84C, 0
0x1800c6f38  mov     cs:byte_1801EB844, al
0x1800c6f3e  jz      short loc_1800C6F4B
0x1800c6f40  test    sil, 2
0x1800c6f44  jnz     short loc_1800C6F4B
0x1800c6f46  mov     al, dil
0x1800c6f49  jmp     short loc_1800C6F4D
0x1800c6f4b  xor     al, al
0x1800c6f4d  cmp     cs:byte_1801EB854, 0
0x1800c6f54  mov     cs:byte_1801EB84C, al
0x1800c6f5a  jz      short loc_1800C6F67
0x1800c6f5c  test    sil, 4
0x1800c6f60  jnz     short loc_1800C6F67
0x1800c6f62  mov     al, dil
0x1800c6f65  jmp     short loc_1800C6F69
0x1800c6f67  xor     al, al
0x1800c6f69  mov     cs:byte_1801EB854, al
0x1800c6f6f  test    r9b, r9b
0x1800c6f72  jz      short loc_1800C6F7F
0x1800c6f74  test    sil, 8
0x1800c6f78  jnz     short loc_1800C6F7F
0x1800c6f7a  mov     al, dil
0x1800c6f7d  jmp     short loc_1800C6F81
0x1800c6f7f  xor     al, al
0x1800c6f81  mov     cs:byte_1801EB85C, al
0x1800c6f87  test    r8b, r8b
0x1800c6f8a  jz      short loc_1800C6F97
0x1800c6f8c  test    sil, 10h
0x1800c6f90  jnz     short loc_1800C6F97
0x1800c6f92  mov     al, dil
0x1800c6f95  jmp     short loc_1800C6F99
0x1800c6f97  xor     al, al
0x1800c6f99  cmp     cs:byte_1801EB86C, 0
0x1800c6fa0  mov     cs:byte_1801EB864, al
0x1800c6fa6  jz      short loc_1800C6FB3
0x1800c6fa8  test    sil, 20h
0x1800c6fac  jnz     short loc_1800C6FB3
0x1800c6fae  mov     al, dil
0x1800c6fb1  jmp     short loc_1800C6FB5
0x1800c6fb3  xor     al, al
0x1800c6fb5  mov     cs:byte_1801EB86C, al
0x1800c6fbb  test    r11b, r11b
0x1800c6fbe  jz      short loc_1800C6FCB
0x1800c6fc0  test    sil, 40h
0x1800c6fc4  jnz     short loc_1800C6FCB
0x1800c6fc6  mov     al, dil
0x1800c6fc9  jmp     short loc_1800C6FCD
0x1800c6fcb  xor     al, al
0x1800c6fcd  mov     cs:byte_1801EB874, al
0x1800c6fd3  test    bl, bl
0x1800c6fd5  jz      short loc_1800C6FE1
0x1800c6fd7  test    sil, sil
0x1800c6fda  js      short loc_1800C6FE1
0x1800c6fdc  mov     al, dil
0x1800c6fdf  jmp     short loc_1800C6FE3
0x1800c6fe1  xor     al, al
0x1800c6fe3  mov     cs:byte_1801EB87C, al
0x1800c6fe9  test    bpl, bpl
0x1800c6fec  jz      short loc_1800C6FF9
0x1800c6fee  bt      esi, 8
0x1800c6ff2  jb      short loc_1800C6FF9
0x1800c6ff4  mov     al, dil
0x1800c6ff7  jmp     short loc_1800C6FFB
0x1800c6ff9  xor     al, al
0x1800c6ffb  mov     cs:byte_1801EB884, al
0x1800c7001  test    cl, cl
0x1800c7003  jz      short loc_1800C700B
0x1800c7005  bt      esi, 9
0x1800c7009  jnb     short loc_1800C700E
0x1800c700b  xor     dil, dil
0x1800c700e  mov     cs:byte_1801EB88C, dil
0x1800c7015  add     rsp, 38h
0x1800c7019  pop     rdi
0x1800c701a  pop     rsi
0x1800c701b  pop     rbp
0x1800c701c  pop     rbx
0x1800c701d  retn
```
