# wil_QueryFeatureState

- ea: `0x14000df74`
- end: `0x14000e0eb`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140009040`

## callees

- `0x140003450`
- `0x14000df74`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e01a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e01a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000dffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000dffd`

## string_xrefs

- `0x14000dff6`: `ntdll.dll`
- `0x14000e010`: `RtlQueryFeatureConfiguration`

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
0x14000df74  mov     [rsp+arg_10], rbx
0x14000df79  mov     [rsp+arg_18], rbp
0x14000df7e  push    rsi
0x14000df7f  push    rdi
0x14000df80  push    r14
0x14000df82  sub     rsp, 50h
0x14000df86  mov     rax, cs:__security_cookie
0x14000df8d  xor     rax, rsp
0x14000df90  mov     [rsp+68h+var_20], rax
0x14000df95  mov     rdi, [rsp+68h+arg_20]
0x14000df9d  mov     r14d, edx
0x14000dfa0  mov     rax, [rsp+68h+arg_28]
0x14000dfa8  mov     rsi, rcx
0x14000dfab  test    rdi, rdi
0x14000dfae  jz      short loc_14000DFB6
0x14000dfb0  mov     dword ptr [rdi], 0
0x14000dfb6  xor     ebp, ebp
0x14000dfb8  mov     [rsp+68h+var_38], 0
0x14000dfc1  test    r8d, r8d
0x14000dfc4  mov     ebx, 1
0x14000dfc9  mov     [rax], ebx
0x14000dfcb  setz    bpl
0x14000dfcf  xor     eax, eax
0x14000dfd1  mov     [rsp+68h+var_30], rax
0x14000dfd6  mov     [rsp+68h+var_28], eax
0x14000dfda  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000dfe1  test    rax, rax
0x14000dfe4  jnz     loc_14000E072
0x14000dfea  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000dff1  test    rax, rax
0x14000dff4  jnz     short loc_14000E010
0x14000dff6  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000dffd  call    cs:__imp_GetModuleHandleW
0x14000e004  nop     dword ptr [rax+rax+00h]
0x14000e009  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e010  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000e017  mov     rcx, rax; hModule
0x14000e01a  call    cs:__imp_GetProcAddress
0x14000e021  nop     dword ptr [rax+rax+00h]
0x14000e026  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000e02d  test    rax, rax
0x14000e030  jnz     short loc_14000E072
0x14000e032  mov     r8d, 0C0000139h
0x14000e038  xor     ebx, ebx
0x14000e03a  test    rdi, rdi
0x14000e03d  jz      short loc_14000E04D
0x14000e03f  xor     ecx, ecx
0x14000e041  cmp     r8d, 80000022h
0x14000e048  setnz   cl
0x14000e04b  mov     [rdi], ecx
0x14000e04d  mov     eax, ebx
0x14000e04f  mov     rcx, [rsp+68h+var_20]
0x14000e054  xor     rcx, rsp; StackCookie
0x14000e057  call    __security_check_cookie
0x14000e05c  lea     r11, [rsp+68h+var_18]
0x14000e061  mov     rbx, [r11+30h]
0x14000e065  mov     rbp, [r11+38h]
0x14000e069  mov     rsp, r11
0x14000e06c  pop     r14
0x14000e06e  pop     rdi
0x14000e06f  pop     rsi
0x14000e070  retn
0x14000e072  lea     r9, [rsp+68h+var_30]
0x14000e077  mov     edx, ebp
0x14000e079  lea     r8, [rsp+68h+var_38]
0x14000e07e  mov     ecx, r14d
0x14000e081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e086  mov     r8d, eax
0x14000e089  test    eax, eax
0x14000e08b  jnz     short loc_14000E0CF
0x14000e08d  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000e091  mov     ecx, edx
0x14000e093  mov     eax, [rsp+68h+var_28]
0x14000e097  mov     [rsi+0Ch], eax
0x14000e09a  mov     eax, edx
0x14000e09c  shr     eax, 0Eh
0x14000e09f  shr     ecx, 4
0x14000e0a2  and     eax, 3
0x14000e0a5  and     ecx, 3
0x14000e0a8  mov     [rsi+8], eax
0x14000e0ab  mov     [rsi], ecx
0x14000e0ad  mov     eax, edx
0x14000e0af  mov     ecx, edx
0x14000e0b1  shr     eax, 6
0x14000e0b4  shr     ecx, 8
0x14000e0b7  and     eax, ebx
0x14000e0b9  and     cl, 3Fh
0x14000e0bc  shr     edx, 7
0x14000e0bf  and     edx, ebx
0x14000e0c1  mov     [rsi+4], cl
0x14000e0c4  mov     [rsi+10h], edx
0x14000e0c7  mov     [rsi+14h], eax
0x14000e0ca  jmp     loc_14000E03A
0x14000e0cf  cmp     eax, 117h
0x14000e0d4  jnz     loc_14000E038
0x14000e0da  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000e0de  shr     eax, 7
0x14000e0e1  and     eax, ebx
0x14000e0e3  mov     [rsi+10h], eax
0x14000e0e6  jmp     loc_14000E03A
```
