# wil_QueryFeatureState

- ea: `0x140009c78`
- end: `0x140009def`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400058d4`

## callees

- `0x140009c78`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009d01`
- `KERNEL32!GetModuleHandleW` at `0x140009d01`
- `KERNEL32!GetProcAddress` at `0x140009d1e`
- `KERNEL32!GetProcAddress` at `0x140009d1e`

## string_xrefs

- `0x140009cfa`: `ntdll.dll`
- `0x140009d14`: `RtlQueryFeatureConfiguration`

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
0x140009c78  mov     [rsp+arg_10], rbx
0x140009c7d  mov     [rsp+arg_18], rbp
0x140009c82  push    rsi
0x140009c83  push    rdi
0x140009c84  push    r14
0x140009c86  sub     rsp, 50h
0x140009c8a  mov     rax, cs:__security_cookie
0x140009c91  xor     rax, rsp
0x140009c94  mov     [rsp+68h+var_20], rax
0x140009c99  mov     rdi, [rsp+68h+arg_20]
0x140009ca1  mov     r14d, edx
0x140009ca4  mov     rax, [rsp+68h+arg_28]
0x140009cac  mov     rsi, rcx
0x140009caf  test    rdi, rdi
0x140009cb2  jz      short loc_140009CBA
0x140009cb4  mov     dword ptr [rdi], 0
0x140009cba  xor     ebp, ebp
0x140009cbc  mov     [rsp+68h+var_38], 0
0x140009cc5  test    r8d, r8d
0x140009cc8  mov     ebx, 1
0x140009ccd  mov     [rax], ebx
0x140009ccf  setz    bpl
0x140009cd3  xor     eax, eax
0x140009cd5  mov     [rsp+68h+var_30], rax
0x140009cda  mov     [rsp+68h+var_28], eax
0x140009cde  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140009ce5  test    rax, rax
0x140009ce8  jnz     loc_140009D76
0x140009cee  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009cf5  test    rax, rax
0x140009cf8  jnz     short loc_140009D14
0x140009cfa  lea     rcx, ModuleName; "ntdll.dll"
0x140009d01  call    cs:__imp_GetModuleHandleW
0x140009d08  nop     dword ptr [rax+rax+00h]
0x140009d0d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009d14  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x140009d1b  mov     rcx, rax; hModule
0x140009d1e  call    cs:__imp_GetProcAddress
0x140009d25  nop     dword ptr [rax+rax+00h]
0x140009d2a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x140009d31  test    rax, rax
0x140009d34  jnz     short loc_140009D76
0x140009d36  mov     r8d, 0C0000139h
0x140009d3c  xor     ebx, ebx
0x140009d3e  test    rdi, rdi
0x140009d41  jz      short loc_140009D51
0x140009d43  xor     ecx, ecx
0x140009d45  cmp     r8d, 80000022h
0x140009d4c  setnz   cl
0x140009d4f  mov     [rdi], ecx
0x140009d51  mov     eax, ebx
0x140009d53  mov     rcx, [rsp+68h+var_20]
0x140009d58  xor     rcx, rsp; StackCookie
0x140009d5b  call    __security_check_cookie
0x140009d60  lea     r11, [rsp+68h+var_18]
0x140009d65  mov     rbx, [r11+30h]
0x140009d69  mov     rbp, [r11+38h]
0x140009d6d  mov     rsp, r11
0x140009d70  pop     r14
0x140009d72  pop     rdi
0x140009d73  pop     rsi
0x140009d74  retn
0x140009d76  lea     r9, [rsp+68h+var_30]
0x140009d7b  mov     edx, ebp
0x140009d7d  lea     r8, [rsp+68h+var_38]
0x140009d82  mov     ecx, r14d
0x140009d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d8a  mov     r8d, eax
0x140009d8d  test    eax, eax
0x140009d8f  jnz     short loc_140009DD3
0x140009d91  mov     edx, dword ptr [rsp+68h+var_30+4]
0x140009d95  mov     ecx, edx
0x140009d97  mov     eax, [rsp+68h+var_28]
0x140009d9b  mov     [rsi+0Ch], eax
0x140009d9e  mov     eax, edx
0x140009da0  shr     eax, 0Eh
0x140009da3  shr     ecx, 4
0x140009da6  and     eax, 3
0x140009da9  and     ecx, 3
0x140009dac  mov     [rsi+8], eax
0x140009daf  mov     [rsi], ecx
0x140009db1  mov     eax, edx
0x140009db3  mov     ecx, edx
0x140009db5  shr     eax, 6
0x140009db8  shr     ecx, 8
0x140009dbb  and     eax, ebx
0x140009dbd  and     cl, 3Fh
0x140009dc0  shr     edx, 7
0x140009dc3  and     edx, ebx
0x140009dc5  mov     [rsi+4], cl
0x140009dc8  mov     [rsi+10h], edx
0x140009dcb  mov     [rsi+14h], eax
0x140009dce  jmp     loc_140009D3E
0x140009dd3  cmp     eax, 117h
0x140009dd8  jnz     loc_140009D3C
0x140009dde  mov     eax, dword ptr [rsp+68h+var_30+4]
0x140009de2  shr     eax, 7
0x140009de5  and     eax, ebx
0x140009de7  mov     [rsi+10h], eax
0x140009dea  jmp     loc_140009D3E
```
