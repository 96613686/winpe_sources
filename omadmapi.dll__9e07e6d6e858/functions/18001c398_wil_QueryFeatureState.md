# wil_QueryFeatureState

- ea: `0x18001c398`
- end: `0x18001c50f`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ded4`

## callees

- `0x1800031b0`
- `0x18001c398`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c421`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c421`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c43e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c43e`

## string_xrefs

- `0x18001c41a`: `ntdll.dll`
- `0x18001c434`: `RtlQueryFeatureConfiguration`

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
0x18001c398  mov     [rsp+arg_10], rbx
0x18001c39d  mov     [rsp+arg_18], rbp
0x18001c3a2  push    rsi
0x18001c3a3  push    rdi
0x18001c3a4  push    r14
0x18001c3a6  sub     rsp, 50h
0x18001c3aa  mov     rax, cs:__security_cookie
0x18001c3b1  xor     rax, rsp
0x18001c3b4  mov     [rsp+68h+var_20], rax
0x18001c3b9  mov     rdi, [rsp+68h+arg_20]
0x18001c3c1  mov     r14d, edx
0x18001c3c4  mov     rax, [rsp+68h+arg_28]
0x18001c3cc  mov     rsi, rcx
0x18001c3cf  test    rdi, rdi
0x18001c3d2  jz      short loc_18001C3DA
0x18001c3d4  mov     dword ptr [rdi], 0
0x18001c3da  xor     ebp, ebp
0x18001c3dc  mov     [rsp+68h+var_38], 0
0x18001c3e5  test    r8d, r8d
0x18001c3e8  mov     ebx, 1
0x18001c3ed  mov     [rax], ebx
0x18001c3ef  setz    bpl
0x18001c3f3  xor     eax, eax
0x18001c3f5  mov     [rsp+68h+var_30], rax
0x18001c3fa  mov     [rsp+68h+var_28], eax
0x18001c3fe  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001c405  test    rax, rax
0x18001c408  jnz     loc_18001C496
0x18001c40e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c415  test    rax, rax
0x18001c418  jnz     short loc_18001C434
0x18001c41a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001c421  call    cs:__imp_GetModuleHandleW
0x18001c428  nop     dword ptr [rax+rax+00h]
0x18001c42d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c434  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001c43b  mov     rcx, rax; hModule
0x18001c43e  call    cs:__imp_GetProcAddress
0x18001c445  nop     dword ptr [rax+rax+00h]
0x18001c44a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001c451  test    rax, rax
0x18001c454  jnz     short loc_18001C496
0x18001c456  mov     r8d, 0C0000139h
0x18001c45c  xor     ebx, ebx
0x18001c45e  test    rdi, rdi
0x18001c461  jz      short loc_18001C471
0x18001c463  xor     ecx, ecx
0x18001c465  cmp     r8d, 80000022h
0x18001c46c  setnz   cl
0x18001c46f  mov     [rdi], ecx
0x18001c471  mov     eax, ebx
0x18001c473  mov     rcx, [rsp+68h+var_20]
0x18001c478  xor     rcx, rsp; StackCookie
0x18001c47b  call    __security_check_cookie
0x18001c480  lea     r11, [rsp+68h+var_18]
0x18001c485  mov     rbx, [r11+30h]
0x18001c489  mov     rbp, [r11+38h]
0x18001c48d  mov     rsp, r11
0x18001c490  pop     r14
0x18001c492  pop     rdi
0x18001c493  pop     rsi
0x18001c494  retn
0x18001c496  lea     r9, [rsp+68h+var_30]
0x18001c49b  mov     edx, ebp
0x18001c49d  lea     r8, [rsp+68h+var_38]
0x18001c4a2  mov     ecx, r14d
0x18001c4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4aa  mov     r8d, eax
0x18001c4ad  test    eax, eax
0x18001c4af  jnz     short loc_18001C4F3
0x18001c4b1  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001c4b5  mov     ecx, edx
0x18001c4b7  mov     eax, [rsp+68h+var_28]
0x18001c4bb  mov     [rsi+0Ch], eax
0x18001c4be  mov     eax, edx
0x18001c4c0  shr     eax, 0Eh
0x18001c4c3  shr     ecx, 4
0x18001c4c6  and     eax, 3
0x18001c4c9  and     ecx, 3
0x18001c4cc  mov     [rsi+8], eax
0x18001c4cf  mov     [rsi], ecx
0x18001c4d1  mov     eax, edx
0x18001c4d3  mov     ecx, edx
0x18001c4d5  shr     eax, 6
0x18001c4d8  shr     ecx, 8
0x18001c4db  and     eax, ebx
0x18001c4dd  and     cl, 3Fh
0x18001c4e0  shr     edx, 7
0x18001c4e3  and     edx, ebx
0x18001c4e5  mov     [rsi+4], cl
0x18001c4e8  mov     [rsi+10h], edx
0x18001c4eb  mov     [rsi+14h], eax
0x18001c4ee  jmp     loc_18001C45E
0x18001c4f3  cmp     eax, 117h
0x18001c4f8  jnz     loc_18001C45C
0x18001c4fe  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001c502  shr     eax, 7
0x18001c505  and     eax, ebx
0x18001c507  mov     [rsi+10h], eax
0x18001c50a  jmp     loc_18001C45E
```
