# wil_QueryFeatureState

- ea: `0x1800127d4`
- end: `0x18001293a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ab34`

## callees

- `0x1800127d4`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012859`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012859`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012870`

## string_xrefs

- `0x180012852`: `ntdll.dll`
- `0x180012866`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v12; // r8d
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v17 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v18 = 0;
  v19 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v12 = -1073741511;
LABEL_8:
      v8 = 0;
      goto LABEL_9;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v17, &v18);
  v12 = v14;
  if ( v14 )
  {
    if ( v14 != 279 )
      goto LABEL_8;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v18) >> 7) & 1;
  }
  else
  {
    v15 = HIDWORD(v18);
    v16 = HIDWORD(v18);
    *(_DWORD *)(a1 + 12) = v19;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v16 >> 14;
    *(_DWORD *)a1 = (v16 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v15) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v15 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v15 >> 6) & 1;
  }
LABEL_9:
  if ( a5 )
    *a5 = v12 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x1800127d4  mov     [rsp+arg_10], rbx
0x1800127d9  mov     [rsp+arg_18], rbp
0x1800127de  push    rsi
0x1800127df  push    rdi
0x1800127e0  push    r14
0x1800127e2  sub     rsp, 50h
0x1800127e6  mov     rax, cs:__security_cookie
0x1800127ed  xor     rax, rsp
0x1800127f0  mov     [rsp+68h+var_20], rax
0x1800127f5  mov     rdi, [rsp+68h+arg_20]
0x1800127fd  mov     r14d, edx
0x180012800  mov     rax, [rsp+68h+arg_28]
0x180012808  mov     rsi, rcx
0x18001280b  test    rdi, rdi
0x18001280e  jz      short loc_180012816
0x180012810  mov     dword ptr [rdi], 0
0x180012816  xor     ebp, ebp
0x180012818  mov     [rsp+68h+var_38], 0
0x180012821  test    r8d, r8d
0x180012824  mov     ebx, 1
0x180012829  mov     [rax], ebx
0x18001282b  setz    bpl
0x18001282f  xor     eax, eax
0x180012831  mov     [rsp+68h+var_30], rax
0x180012836  mov     [rsp+68h+var_28], eax
0x18001283a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180012841  test    rax, rax
0x180012844  jnz     short loc_1800128C1
0x180012846  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001284d  test    rax, rax
0x180012850  jnz     short loc_180012866
0x180012852  lea     rcx, ModuleName; "ntdll.dll"
0x180012859  call    cs:__imp_GetModuleHandleW
0x18001285f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012866  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001286d  mov     rcx, rax; hModule
0x180012870  call    cs:__imp_GetProcAddress
0x180012876  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001287d  test    rax, rax
0x180012880  jnz     short loc_1800128C1
0x180012882  mov     r8d, 0C0000139h
0x180012888  xor     ebx, ebx
0x18001288a  test    rdi, rdi
0x18001288d  jz      short loc_18001289D
0x18001288f  xor     ecx, ecx
0x180012891  cmp     r8d, 80000022h
0x180012898  setnz   cl
0x18001289b  mov     [rdi], ecx
0x18001289d  mov     eax, ebx
0x18001289f  mov     rcx, [rsp+68h+var_20]
0x1800128a4  xor     rcx, rsp; StackCookie
0x1800128a7  call    __security_check_cookie
0x1800128ac  lea     r11, [rsp+68h+var_18]
0x1800128b1  mov     rbx, [r11+30h]
0x1800128b5  mov     rbp, [r11+38h]
0x1800128b9  mov     rsp, r11
0x1800128bc  pop     r14
0x1800128be  pop     rdi
0x1800128bf  pop     rsi
0x1800128c0  retn
0x1800128c1  lea     r9, [rsp+68h+var_30]
0x1800128c6  mov     edx, ebp
0x1800128c8  lea     r8, [rsp+68h+var_38]
0x1800128cd  mov     ecx, r14d
0x1800128d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d5  mov     r8d, eax
0x1800128d8  test    eax, eax
0x1800128da  jnz     short loc_18001291E
0x1800128dc  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800128e0  mov     ecx, edx
0x1800128e2  mov     eax, [rsp+68h+var_28]
0x1800128e6  mov     [rsi+0Ch], eax
0x1800128e9  mov     eax, edx
0x1800128eb  shr     eax, 0Eh
0x1800128ee  shr     ecx, 4
0x1800128f1  and     eax, 3
0x1800128f4  and     ecx, 3
0x1800128f7  mov     [rsi+8], eax
0x1800128fa  mov     [rsi], ecx
0x1800128fc  mov     eax, edx
0x1800128fe  mov     ecx, edx
0x180012900  shr     eax, 6
0x180012903  shr     ecx, 8
0x180012906  and     eax, ebx
0x180012908  and     cl, 3Fh
0x18001290b  shr     edx, 7
0x18001290e  and     edx, ebx
0x180012910  mov     [rsi+4], cl
0x180012913  mov     [rsi+10h], edx
0x180012916  mov     [rsi+14h], eax
0x180012919  jmp     loc_18001288A
0x18001291e  cmp     eax, 117h
0x180012923  jnz     loc_180012888
0x180012929  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001292d  shr     eax, 7
0x180012930  and     eax, ebx
0x180012932  mov     [rsi+10h], eax
0x180012935  jmp     loc_18001288A
```
