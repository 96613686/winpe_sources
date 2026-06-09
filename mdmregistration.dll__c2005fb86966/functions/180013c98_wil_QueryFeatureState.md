# wil_QueryFeatureState

- ea: `0x180013c98`
- end: `0x180013e0f`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008e78`

## callees

- `0x1800026d0`
- `0x180013c98`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013d3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013d3e`

## string_xrefs

- `0x180013d1a`: `ntdll.dll`
- `0x180013d34`: `RtlQueryFeatureConfiguration`

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
0x180013c98  mov     [rsp+arg_10], rbx
0x180013c9d  mov     [rsp+arg_18], rbp
0x180013ca2  push    rsi
0x180013ca3  push    rdi
0x180013ca4  push    r14
0x180013ca6  sub     rsp, 50h
0x180013caa  mov     rax, cs:__security_cookie
0x180013cb1  xor     rax, rsp
0x180013cb4  mov     [rsp+68h+var_20], rax
0x180013cb9  mov     rdi, [rsp+68h+arg_20]
0x180013cc1  mov     r14d, edx
0x180013cc4  mov     rax, [rsp+68h+arg_28]
0x180013ccc  mov     rsi, rcx
0x180013ccf  test    rdi, rdi
0x180013cd2  jz      short loc_180013CDA
0x180013cd4  mov     dword ptr [rdi], 0
0x180013cda  xor     ebp, ebp
0x180013cdc  mov     [rsp+68h+var_38], 0
0x180013ce5  test    r8d, r8d
0x180013ce8  mov     ebx, 1
0x180013ced  mov     [rax], ebx
0x180013cef  setz    bpl
0x180013cf3  xor     eax, eax
0x180013cf5  mov     [rsp+68h+var_30], rax
0x180013cfa  mov     [rsp+68h+var_28], eax
0x180013cfe  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180013d05  test    rax, rax
0x180013d08  jnz     loc_180013D96
0x180013d0e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013d15  test    rax, rax
0x180013d18  jnz     short loc_180013D34
0x180013d1a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180013d21  call    cs:__imp_GetModuleHandleW
0x180013d28  nop     dword ptr [rax+rax+00h]
0x180013d2d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013d34  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180013d3b  mov     rcx, rax; hModule
0x180013d3e  call    cs:__imp_GetProcAddress
0x180013d45  nop     dword ptr [rax+rax+00h]
0x180013d4a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180013d51  test    rax, rax
0x180013d54  jnz     short loc_180013D96
0x180013d56  mov     r8d, 0C0000139h
0x180013d5c  xor     ebx, ebx
0x180013d5e  test    rdi, rdi
0x180013d61  jz      short loc_180013D71
0x180013d63  xor     ecx, ecx
0x180013d65  cmp     r8d, 80000022h
0x180013d6c  setnz   cl
0x180013d6f  mov     [rdi], ecx
0x180013d71  mov     eax, ebx
0x180013d73  mov     rcx, [rsp+68h+var_20]
0x180013d78  xor     rcx, rsp; StackCookie
0x180013d7b  call    __security_check_cookie
0x180013d80  lea     r11, [rsp+68h+var_18]
0x180013d85  mov     rbx, [r11+30h]
0x180013d89  mov     rbp, [r11+38h]
0x180013d8d  mov     rsp, r11
0x180013d90  pop     r14
0x180013d92  pop     rdi
0x180013d93  pop     rsi
0x180013d94  retn
0x180013d96  lea     r9, [rsp+68h+var_30]
0x180013d9b  mov     edx, ebp
0x180013d9d  lea     r8, [rsp+68h+var_38]
0x180013da2  mov     ecx, r14d
0x180013da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013daa  mov     r8d, eax
0x180013dad  test    eax, eax
0x180013daf  jnz     short loc_180013DF3
0x180013db1  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180013db5  mov     ecx, edx
0x180013db7  mov     eax, [rsp+68h+var_28]
0x180013dbb  mov     [rsi+0Ch], eax
0x180013dbe  mov     eax, edx
0x180013dc0  shr     eax, 0Eh
0x180013dc3  shr     ecx, 4
0x180013dc6  and     eax, 3
0x180013dc9  and     ecx, 3
0x180013dcc  mov     [rsi+8], eax
0x180013dcf  mov     [rsi], ecx
0x180013dd1  mov     eax, edx
0x180013dd3  mov     ecx, edx
0x180013dd5  shr     eax, 6
0x180013dd8  shr     ecx, 8
0x180013ddb  and     eax, ebx
0x180013ddd  and     cl, 3Fh
0x180013de0  shr     edx, 7
0x180013de3  and     edx, ebx
0x180013de5  mov     [rsi+4], cl
0x180013de8  mov     [rsi+10h], edx
0x180013deb  mov     [rsi+14h], eax
0x180013dee  jmp     loc_180013D5E
0x180013df3  cmp     eax, 117h
0x180013df8  jnz     loc_180013D5C
0x180013dfe  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180013e02  shr     eax, 7
0x180013e05  and     eax, ebx
0x180013e07  mov     [rsi+10h], eax
0x180013e0a  jmp     loc_180013D5E
```
