# wil_QueryFeatureState

- ea: `0x14000b0ac`
- end: `0x14000b223`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140005fe0`

## callees

- `0x14000b0ac`
- `0x140015690`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b135`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b135`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b152`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b152`

## string_xrefs

- `0x14000b12e`: `ntdll.dll`
- `0x14000b148`: `RtlQueryFeatureConfiguration`

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
0x14000b0ac  mov     [rsp+arg_10], rbx
0x14000b0b1  mov     [rsp+arg_18], rbp
0x14000b0b6  push    rsi
0x14000b0b7  push    rdi
0x14000b0b8  push    r14
0x14000b0ba  sub     rsp, 50h
0x14000b0be  mov     rax, cs:__security_cookie
0x14000b0c5  xor     rax, rsp
0x14000b0c8  mov     [rsp+68h+var_20], rax
0x14000b0cd  mov     rdi, [rsp+68h+arg_20]
0x14000b0d5  mov     r14d, edx
0x14000b0d8  mov     rax, [rsp+68h+arg_28]
0x14000b0e0  mov     rsi, rcx
0x14000b0e3  test    rdi, rdi
0x14000b0e6  jz      short loc_14000B0EE
0x14000b0e8  mov     dword ptr [rdi], 0
0x14000b0ee  xor     ebp, ebp
0x14000b0f0  mov     [rsp+68h+var_38], 0
0x14000b0f9  test    r8d, r8d
0x14000b0fc  mov     ebx, 1
0x14000b101  mov     [rax], ebx
0x14000b103  setz    bpl
0x14000b107  xor     eax, eax
0x14000b109  mov     [rsp+68h+var_30], rax
0x14000b10e  mov     [rsp+68h+var_28], eax
0x14000b112  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000b119  test    rax, rax
0x14000b11c  jnz     loc_14000B1AA
0x14000b122  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b129  test    rax, rax
0x14000b12c  jnz     short loc_14000B148
0x14000b12e  lea     rcx, ModuleName; "ntdll.dll"
0x14000b135  call    cs:__imp_GetModuleHandleW
0x14000b13c  nop     dword ptr [rax+rax+00h]
0x14000b141  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b148  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000b14f  mov     rcx, rax; hModule
0x14000b152  call    cs:__imp_GetProcAddress
0x14000b159  nop     dword ptr [rax+rax+00h]
0x14000b15e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000b165  test    rax, rax
0x14000b168  jnz     short loc_14000B1AA
0x14000b16a  mov     r8d, 0C0000139h
0x14000b170  xor     ebx, ebx
0x14000b172  test    rdi, rdi
0x14000b175  jz      short loc_14000B185
0x14000b177  xor     ecx, ecx
0x14000b179  cmp     r8d, 80000022h
0x14000b180  setnz   cl
0x14000b183  mov     [rdi], ecx
0x14000b185  mov     eax, ebx
0x14000b187  mov     rcx, [rsp+68h+var_20]
0x14000b18c  xor     rcx, rsp; StackCookie
0x14000b18f  call    __security_check_cookie
0x14000b194  lea     r11, [rsp+68h+var_18]
0x14000b199  mov     rbx, [r11+30h]
0x14000b19d  mov     rbp, [r11+38h]
0x14000b1a1  mov     rsp, r11
0x14000b1a4  pop     r14
0x14000b1a6  pop     rdi
0x14000b1a7  pop     rsi
0x14000b1a8  retn
0x14000b1aa  lea     r9, [rsp+68h+var_30]
0x14000b1af  mov     edx, ebp
0x14000b1b1  lea     r8, [rsp+68h+var_38]
0x14000b1b6  mov     ecx, r14d
0x14000b1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b1be  mov     r8d, eax
0x14000b1c1  test    eax, eax
0x14000b1c3  jnz     short loc_14000B207
0x14000b1c5  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000b1c9  mov     ecx, edx
0x14000b1cb  mov     eax, [rsp+68h+var_28]
0x14000b1cf  mov     [rsi+0Ch], eax
0x14000b1d2  mov     eax, edx
0x14000b1d4  shr     eax, 0Eh
0x14000b1d7  shr     ecx, 4
0x14000b1da  and     eax, 3
0x14000b1dd  and     ecx, 3
0x14000b1e0  mov     [rsi+8], eax
0x14000b1e3  mov     [rsi], ecx
0x14000b1e5  mov     eax, edx
0x14000b1e7  mov     ecx, edx
0x14000b1e9  shr     eax, 6
0x14000b1ec  shr     ecx, 8
0x14000b1ef  and     eax, ebx
0x14000b1f1  and     cl, 3Fh
0x14000b1f4  shr     edx, 7
0x14000b1f7  and     edx, ebx
0x14000b1f9  mov     [rsi+4], cl
0x14000b1fc  mov     [rsi+10h], edx
0x14000b1ff  mov     [rsi+14h], eax
0x14000b202  jmp     loc_14000B172
0x14000b207  cmp     eax, 117h
0x14000b20c  jnz     loc_14000B170
0x14000b212  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000b216  shr     eax, 7
0x14000b219  and     eax, ebx
0x14000b21b  mov     [rsi+10h], eax
0x14000b21e  jmp     loc_14000B172
```
