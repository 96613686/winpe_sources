# wil_QueryFeatureState

- ea: `0x18000b378`
- end: `0x18000b4de`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007950`

## callees

- `0x1800024e0`
- `0x18000b378`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b414`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b414`

## string_xrefs

- `0x18000b3f6`: `ntdll.dll`
- `0x18000b40a`: `RtlQueryFeatureConfiguration`

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
0x18000b378  mov     [rsp+arg_10], rbx
0x18000b37d  mov     [rsp+arg_18], rbp
0x18000b382  push    rsi
0x18000b383  push    rdi
0x18000b384  push    r14
0x18000b386  sub     rsp, 50h
0x18000b38a  mov     rax, cs:__security_cookie
0x18000b391  xor     rax, rsp
0x18000b394  mov     [rsp+68h+var_20], rax
0x18000b399  mov     rdi, [rsp+68h+arg_20]
0x18000b3a1  mov     r14d, edx
0x18000b3a4  mov     rax, [rsp+68h+arg_28]
0x18000b3ac  mov     rsi, rcx
0x18000b3af  test    rdi, rdi
0x18000b3b2  jz      short loc_18000B3BA
0x18000b3b4  mov     dword ptr [rdi], 0
0x18000b3ba  xor     ebp, ebp
0x18000b3bc  mov     [rsp+68h+var_38], 0
0x18000b3c5  test    r8d, r8d
0x18000b3c8  mov     ebx, 1
0x18000b3cd  mov     [rax], ebx
0x18000b3cf  setz    bpl
0x18000b3d3  xor     eax, eax
0x18000b3d5  mov     [rsp+68h+var_30], rax
0x18000b3da  mov     [rsp+68h+var_28], eax
0x18000b3de  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b3e5  test    rax, rax
0x18000b3e8  jnz     short loc_18000B465
0x18000b3ea  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b3f1  test    rax, rax
0x18000b3f4  jnz     short loc_18000B40A
0x18000b3f6  lea     rcx, ModuleName; "ntdll.dll"
0x18000b3fd  call    cs:__imp_GetModuleHandleW
0x18000b403  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b40a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b411  mov     rcx, rax; hModule
0x18000b414  call    cs:__imp_GetProcAddress
0x18000b41a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b421  test    rax, rax
0x18000b424  jnz     short loc_18000B465
0x18000b426  mov     r8d, 0C0000139h
0x18000b42c  xor     ebx, ebx
0x18000b42e  test    rdi, rdi
0x18000b431  jz      short loc_18000B441
0x18000b433  xor     ecx, ecx
0x18000b435  cmp     r8d, 80000022h
0x18000b43c  setnz   cl
0x18000b43f  mov     [rdi], ecx
0x18000b441  mov     eax, ebx
0x18000b443  mov     rcx, [rsp+68h+var_20]
0x18000b448  xor     rcx, rsp; StackCookie
0x18000b44b  call    __security_check_cookie
0x18000b450  lea     r11, [rsp+68h+var_18]
0x18000b455  mov     rbx, [r11+30h]
0x18000b459  mov     rbp, [r11+38h]
0x18000b45d  mov     rsp, r11
0x18000b460  pop     r14
0x18000b462  pop     rdi
0x18000b463  pop     rsi
0x18000b464  retn
0x18000b465  lea     r9, [rsp+68h+var_30]
0x18000b46a  mov     edx, ebp
0x18000b46c  lea     r8, [rsp+68h+var_38]
0x18000b471  mov     ecx, r14d
0x18000b474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b479  mov     r8d, eax
0x18000b47c  test    eax, eax
0x18000b47e  jnz     short loc_18000B4C2
0x18000b480  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b484  mov     ecx, edx
0x18000b486  mov     eax, [rsp+68h+var_28]
0x18000b48a  mov     [rsi+0Ch], eax
0x18000b48d  mov     eax, edx
0x18000b48f  shr     eax, 0Eh
0x18000b492  shr     ecx, 4
0x18000b495  and     eax, 3
0x18000b498  and     ecx, 3
0x18000b49b  mov     [rsi+8], eax
0x18000b49e  mov     [rsi], ecx
0x18000b4a0  mov     eax, edx
0x18000b4a2  mov     ecx, edx
0x18000b4a4  shr     eax, 6
0x18000b4a7  shr     ecx, 8
0x18000b4aa  and     eax, ebx
0x18000b4ac  and     cl, 3Fh
0x18000b4af  shr     edx, 7
0x18000b4b2  and     edx, ebx
0x18000b4b4  mov     [rsi+4], cl
0x18000b4b7  mov     [rsi+10h], edx
0x18000b4ba  mov     [rsi+14h], eax
0x18000b4bd  jmp     loc_18000B42E
0x18000b4c2  cmp     eax, 117h
0x18000b4c7  jnz     loc_18000B42C
0x18000b4cd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b4d1  shr     eax, 7
0x18000b4d4  and     eax, ebx
0x18000b4d6  mov     [rsi+10h], eax
0x18000b4d9  jmp     loc_18000B42E
```
