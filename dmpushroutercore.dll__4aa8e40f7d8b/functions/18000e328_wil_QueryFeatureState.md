# wil_QueryFeatureState

- ea: `0x18000e328`
- end: `0x18000e48e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009c14`

## callees

- `0x1800039f0`
- `0x18000e328`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e3ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e3ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3c4`

## string_xrefs

- `0x18000e3a6`: `ntdll.dll`
- `0x18000e3ba`: `RtlQueryFeatureConfiguration`

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
0x18000e328  mov     [rsp+arg_10], rbx
0x18000e32d  mov     [rsp+arg_18], rbp
0x18000e332  push    rsi
0x18000e333  push    rdi
0x18000e334  push    r14
0x18000e336  sub     rsp, 50h
0x18000e33a  mov     rax, cs:__security_cookie
0x18000e341  xor     rax, rsp
0x18000e344  mov     [rsp+68h+var_20], rax
0x18000e349  mov     rdi, [rsp+68h+arg_20]
0x18000e351  mov     r14d, edx
0x18000e354  mov     rax, [rsp+68h+arg_28]
0x18000e35c  mov     rsi, rcx
0x18000e35f  test    rdi, rdi
0x18000e362  jz      short loc_18000E36A
0x18000e364  mov     dword ptr [rdi], 0
0x18000e36a  xor     ebp, ebp
0x18000e36c  mov     [rsp+68h+var_38], 0
0x18000e375  test    r8d, r8d
0x18000e378  mov     ebx, 1
0x18000e37d  mov     [rax], ebx
0x18000e37f  setz    bpl
0x18000e383  xor     eax, eax
0x18000e385  mov     [rsp+68h+var_30], rax
0x18000e38a  mov     [rsp+68h+var_28], eax
0x18000e38e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e395  test    rax, rax
0x18000e398  jnz     short loc_18000E415
0x18000e39a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e3a1  test    rax, rax
0x18000e3a4  jnz     short loc_18000E3BA
0x18000e3a6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e3ad  call    cs:__imp_GetModuleHandleW
0x18000e3b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e3ba  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e3c1  mov     rcx, rax; hModule
0x18000e3c4  call    cs:__imp_GetProcAddress
0x18000e3ca  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e3d1  test    rax, rax
0x18000e3d4  jnz     short loc_18000E415
0x18000e3d6  mov     r8d, 0C0000139h
0x18000e3dc  xor     ebx, ebx
0x18000e3de  test    rdi, rdi
0x18000e3e1  jz      short loc_18000E3F1
0x18000e3e3  xor     ecx, ecx
0x18000e3e5  cmp     r8d, 80000022h
0x18000e3ec  setnz   cl
0x18000e3ef  mov     [rdi], ecx
0x18000e3f1  mov     eax, ebx
0x18000e3f3  mov     rcx, [rsp+68h+var_20]
0x18000e3f8  xor     rcx, rsp; StackCookie
0x18000e3fb  call    __security_check_cookie
0x18000e400  lea     r11, [rsp+68h+var_18]
0x18000e405  mov     rbx, [r11+30h]
0x18000e409  mov     rbp, [r11+38h]
0x18000e40d  mov     rsp, r11
0x18000e410  pop     r14
0x18000e412  pop     rdi
0x18000e413  pop     rsi
0x18000e414  retn
0x18000e415  lea     r9, [rsp+68h+var_30]
0x18000e41a  mov     edx, ebp
0x18000e41c  lea     r8, [rsp+68h+var_38]
0x18000e421  mov     ecx, r14d
0x18000e424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e429  mov     r8d, eax
0x18000e42c  test    eax, eax
0x18000e42e  jnz     short loc_18000E472
0x18000e430  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000e434  mov     ecx, edx
0x18000e436  mov     eax, [rsp+68h+var_28]
0x18000e43a  mov     [rsi+0Ch], eax
0x18000e43d  mov     eax, edx
0x18000e43f  shr     eax, 0Eh
0x18000e442  shr     ecx, 4
0x18000e445  and     eax, 3
0x18000e448  and     ecx, 3
0x18000e44b  mov     [rsi+8], eax
0x18000e44e  mov     [rsi], ecx
0x18000e450  mov     eax, edx
0x18000e452  mov     ecx, edx
0x18000e454  shr     eax, 6
0x18000e457  shr     ecx, 8
0x18000e45a  and     eax, ebx
0x18000e45c  and     cl, 3Fh
0x18000e45f  shr     edx, 7
0x18000e462  and     edx, ebx
0x18000e464  mov     [rsi+4], cl
0x18000e467  mov     [rsi+10h], edx
0x18000e46a  mov     [rsi+14h], eax
0x18000e46d  jmp     loc_18000E3DE
0x18000e472  cmp     eax, 117h
0x18000e477  jnz     loc_18000E3DC
0x18000e47d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000e481  shr     eax, 7
0x18000e484  and     eax, ebx
0x18000e486  mov     [rsi+10h], eax
0x18000e489  jmp     loc_18000E3DE
```
