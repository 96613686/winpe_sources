# wil_QueryFeatureState

- ea: `0x14000f0d4`
- end: `0x14000f24b`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000f734`

## callees

- `0x1400020b0`
- `0x14000f0d4`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f17a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f17a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f15d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f15d`

## string_xrefs

- `0x14000f156`: `ntdll.dll`
- `0x14000f170`: `RtlQueryFeatureConfiguration`

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
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x14000f0d4  mov     [rsp+arg_10], rbx
0x14000f0d9  mov     [rsp+arg_18], rbp
0x14000f0de  push    rsi
0x14000f0df  push    rdi
0x14000f0e0  push    r14
0x14000f0e2  sub     rsp, 50h
0x14000f0e6  mov     rax, cs:__security_cookie
0x14000f0ed  xor     rax, rsp
0x14000f0f0  mov     [rsp+68h+var_20], rax
0x14000f0f5  mov     rdi, [rsp+68h+arg_20]
0x14000f0fd  mov     r14d, edx
0x14000f100  mov     rax, [rsp+68h+arg_28]
0x14000f108  mov     rsi, rcx
0x14000f10b  test    rdi, rdi
0x14000f10e  jz      short loc_14000F116
0x14000f110  mov     dword ptr [rdi], 0
0x14000f116  xor     ebp, ebp
0x14000f118  mov     [rsp+68h+var_38], 0
0x14000f121  test    r8d, r8d
0x14000f124  mov     ebx, 1
0x14000f129  mov     [rax], ebx
0x14000f12b  setz    bpl
0x14000f12f  xor     eax, eax
0x14000f131  mov     [rsp+68h+var_30], rax
0x14000f136  mov     [rsp+68h+var_28], eax
0x14000f13a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000f141  test    rax, rax
0x14000f144  jnz     loc_14000F1D2
0x14000f14a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000f151  test    rax, rax
0x14000f154  jnz     short loc_14000F170
0x14000f156  lea     rcx, ModuleName; "ntdll.dll"
0x14000f15d  call    cs:__imp_GetModuleHandleW
0x14000f164  nop     dword ptr [rax+rax+00h]
0x14000f169  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000f170  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000f177  mov     rcx, rax; hModule
0x14000f17a  call    cs:__imp_GetProcAddress
0x14000f181  nop     dword ptr [rax+rax+00h]
0x14000f186  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000f18d  test    rax, rax
0x14000f190  jnz     short loc_14000F1D2
0x14000f192  mov     r8d, 0C0000139h
0x14000f198  xor     ebx, ebx
0x14000f19a  test    rdi, rdi
0x14000f19d  jz      short loc_14000F1AD
0x14000f19f  xor     ecx, ecx
0x14000f1a1  cmp     r8d, 80000022h
0x14000f1a8  setnz   cl
0x14000f1ab  mov     [rdi], ecx
0x14000f1ad  mov     eax, ebx
0x14000f1af  mov     rcx, [rsp+68h+var_20]
0x14000f1b4  xor     rcx, rsp; StackCookie
0x14000f1b7  call    __security_check_cookie
0x14000f1bc  lea     r11, [rsp+68h+var_18]
0x14000f1c1  mov     rbx, [r11+30h]
0x14000f1c5  mov     rbp, [r11+38h]
0x14000f1c9  mov     rsp, r11
0x14000f1cc  pop     r14
0x14000f1ce  pop     rdi
0x14000f1cf  pop     rsi
0x14000f1d0  retn
0x14000f1d2  lea     r9, [rsp+68h+var_30]
0x14000f1d7  mov     edx, ebp
0x14000f1d9  lea     r8, [rsp+68h+var_38]
0x14000f1de  mov     ecx, r14d
0x14000f1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1e6  mov     r8d, eax
0x14000f1e9  test    eax, eax
0x14000f1eb  jnz     short loc_14000F22F
0x14000f1ed  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000f1f1  mov     ecx, edx
0x14000f1f3  mov     eax, [rsp+68h+var_28]
0x14000f1f7  mov     [rsi+0Ch], eax
0x14000f1fa  mov     eax, edx
0x14000f1fc  shr     eax, 0Eh
0x14000f1ff  shr     ecx, 4
0x14000f202  and     eax, 3
0x14000f205  and     ecx, 3
0x14000f208  mov     [rsi+8], eax
0x14000f20b  mov     [rsi], ecx
0x14000f20d  mov     eax, edx
0x14000f20f  mov     ecx, edx
0x14000f211  shr     eax, 6
0x14000f214  shr     ecx, 8
0x14000f217  and     eax, ebx
0x14000f219  and     cl, 3Fh
0x14000f21c  shr     edx, 7
0x14000f21f  and     edx, ebx
0x14000f221  mov     [rsi+4], cl
0x14000f224  mov     [rsi+10h], edx
0x14000f227  mov     [rsi+14h], eax
0x14000f22a  jmp     loc_14000F19A
0x14000f22f  cmp     eax, 117h
0x14000f234  jnz     loc_14000F198
0x14000f23a  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000f23e  shr     eax, 7
0x14000f241  and     eax, ebx
0x14000f243  mov     [rsi+10h], eax
0x14000f246  jmp     loc_14000F19A
```
