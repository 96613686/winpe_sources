# wil_QueryFeatureState

- ea: `0x18001196c`
- end: `0x180011ad2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000fafc`

## callees

- `0x18001196c`
- `0x180012040`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011a08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011a08`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800119f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800119f1`

## string_xrefs

- `0x1800119ea`: `ntdll.dll`
- `0x1800119fe`: `RtlQueryFeatureConfiguration`

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
0x18001196c  mov     [rsp+arg_10], rbx
0x180011971  mov     [rsp+arg_18], rbp
0x180011976  push    rsi
0x180011977  push    rdi
0x180011978  push    r14
0x18001197a  sub     rsp, 50h
0x18001197e  mov     rax, cs:__security_cookie
0x180011985  xor     rax, rsp
0x180011988  mov     [rsp+68h+var_20], rax
0x18001198d  mov     rdi, [rsp+68h+arg_20]
0x180011995  mov     r14d, edx
0x180011998  mov     rax, [rsp+68h+arg_28]
0x1800119a0  mov     rsi, rcx
0x1800119a3  test    rdi, rdi
0x1800119a6  jz      short loc_1800119AE
0x1800119a8  mov     dword ptr [rdi], 0
0x1800119ae  xor     ebp, ebp
0x1800119b0  mov     [rsp+68h+var_38], 0
0x1800119b9  test    r8d, r8d
0x1800119bc  mov     ebx, 1
0x1800119c1  mov     [rax], ebx
0x1800119c3  setz    bpl
0x1800119c7  xor     eax, eax
0x1800119c9  mov     [rsp+68h+var_30], rax
0x1800119ce  mov     [rsp+68h+var_28], eax
0x1800119d2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800119d9  test    rax, rax
0x1800119dc  jnz     short loc_180011A59
0x1800119de  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800119e5  test    rax, rax
0x1800119e8  jnz     short loc_1800119FE
0x1800119ea  lea     rcx, ModuleName; "ntdll.dll"
0x1800119f1  call    cs:__imp_GetModuleHandleW
0x1800119f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800119fe  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180011a05  mov     rcx, rax; hModule
0x180011a08  call    cs:__imp_GetProcAddress
0x180011a0e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180011a15  test    rax, rax
0x180011a18  jnz     short loc_180011A59
0x180011a1a  mov     r8d, 0C0000139h
0x180011a20  xor     ebx, ebx
0x180011a22  test    rdi, rdi
0x180011a25  jz      short loc_180011A35
0x180011a27  xor     ecx, ecx
0x180011a29  cmp     r8d, 80000022h
0x180011a30  setnz   cl
0x180011a33  mov     [rdi], ecx
0x180011a35  mov     eax, ebx
0x180011a37  mov     rcx, [rsp+68h+var_20]
0x180011a3c  xor     rcx, rsp; StackCookie
0x180011a3f  call    __security_check_cookie
0x180011a44  lea     r11, [rsp+68h+var_18]
0x180011a49  mov     rbx, [r11+30h]
0x180011a4d  mov     rbp, [r11+38h]
0x180011a51  mov     rsp, r11
0x180011a54  pop     r14
0x180011a56  pop     rdi
0x180011a57  pop     rsi
0x180011a58  retn
0x180011a59  lea     r9, [rsp+68h+var_30]
0x180011a5e  mov     edx, ebp
0x180011a60  lea     r8, [rsp+68h+var_38]
0x180011a65  mov     ecx, r14d
0x180011a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6d  mov     r8d, eax
0x180011a70  test    eax, eax
0x180011a72  jnz     short loc_180011AB6
0x180011a74  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180011a78  mov     ecx, edx
0x180011a7a  mov     eax, [rsp+68h+var_28]
0x180011a7e  mov     [rsi+0Ch], eax
0x180011a81  mov     eax, edx
0x180011a83  shr     eax, 0Eh
0x180011a86  shr     ecx, 4
0x180011a89  and     eax, 3
0x180011a8c  and     ecx, 3
0x180011a8f  mov     [rsi+8], eax
0x180011a92  mov     [rsi], ecx
0x180011a94  mov     eax, edx
0x180011a96  mov     ecx, edx
0x180011a98  shr     eax, 6
0x180011a9b  shr     ecx, 8
0x180011a9e  and     eax, ebx
0x180011aa0  and     cl, 3Fh
0x180011aa3  shr     edx, 7
0x180011aa6  and     edx, ebx
0x180011aa8  mov     [rsi+4], cl
0x180011aab  mov     [rsi+10h], edx
0x180011aae  mov     [rsi+14h], eax
0x180011ab1  jmp     loc_180011A22
0x180011ab6  cmp     eax, 117h
0x180011abb  jnz     loc_180011A20
0x180011ac1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180011ac5  shr     eax, 7
0x180011ac8  and     eax, ebx
0x180011aca  mov     [rsi+10h], eax
0x180011acd  jmp     loc_180011A22
```
