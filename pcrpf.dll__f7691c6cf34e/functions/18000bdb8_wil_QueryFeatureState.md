# wil_QueryFeatureState

- ea: `0x18000bdb8`
- end: `0x18000bf2f`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800077dc`
- `0x180029548`

## callees

- `0x180003270`
- `0x18000bdb8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000be5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000be5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be41`

## string_xrefs

- `0x18000be3a`: `ntdll.dll`
- `0x18000be54`: `RtlQueryFeatureConfiguration`

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
0x18000bdb8  mov     [rsp+arg_10], rbx
0x18000bdbd  mov     [rsp+arg_18], rbp
0x18000bdc2  push    rsi
0x18000bdc3  push    rdi
0x18000bdc4  push    r14
0x18000bdc6  sub     rsp, 50h
0x18000bdca  mov     rax, cs:__security_cookie
0x18000bdd1  xor     rax, rsp
0x18000bdd4  mov     [rsp+68h+var_20], rax
0x18000bdd9  mov     rdi, [rsp+68h+arg_20]
0x18000bde1  mov     r14d, edx
0x18000bde4  mov     rax, [rsp+68h+arg_28]
0x18000bdec  mov     rsi, rcx
0x18000bdef  test    rdi, rdi
0x18000bdf2  jz      short loc_18000BDFA
0x18000bdf4  mov     dword ptr [rdi], 0
0x18000bdfa  xor     ebp, ebp
0x18000bdfc  mov     [rsp+68h+var_38], 0
0x18000be05  test    r8d, r8d
0x18000be08  mov     ebx, 1
0x18000be0d  mov     [rax], ebx
0x18000be0f  setz    bpl
0x18000be13  xor     eax, eax
0x18000be15  mov     [rsp+68h+var_30], rax
0x18000be1a  mov     [rsp+68h+var_28], eax
0x18000be1e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000be25  test    rax, rax
0x18000be28  jnz     loc_18000BEB6
0x18000be2e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be35  test    rax, rax
0x18000be38  jnz     short loc_18000BE54
0x18000be3a  lea     rcx, ModuleName; "ntdll.dll"
0x18000be41  call    cs:__imp_GetModuleHandleW
0x18000be48  nop     dword ptr [rax+rax+00h]
0x18000be4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be54  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000be5b  mov     rcx, rax; hModule
0x18000be5e  call    cs:__imp_GetProcAddress
0x18000be65  nop     dword ptr [rax+rax+00h]
0x18000be6a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000be71  test    rax, rax
0x18000be74  jnz     short loc_18000BEB6
0x18000be76  mov     r8d, 0C0000139h
0x18000be7c  xor     ebx, ebx
0x18000be7e  test    rdi, rdi
0x18000be81  jz      short loc_18000BE91
0x18000be83  xor     ecx, ecx
0x18000be85  cmp     r8d, 80000022h
0x18000be8c  setnz   cl
0x18000be8f  mov     [rdi], ecx
0x18000be91  mov     eax, ebx
0x18000be93  mov     rcx, [rsp+68h+var_20]
0x18000be98  xor     rcx, rsp; StackCookie
0x18000be9b  call    __security_check_cookie
0x18000bea0  lea     r11, [rsp+68h+var_18]
0x18000bea5  mov     rbx, [r11+30h]
0x18000bea9  mov     rbp, [r11+38h]
0x18000bead  mov     rsp, r11
0x18000beb0  pop     r14
0x18000beb2  pop     rdi
0x18000beb3  pop     rsi
0x18000beb4  retn
0x18000beb6  lea     r9, [rsp+68h+var_30]
0x18000bebb  mov     edx, ebp
0x18000bebd  lea     r8, [rsp+68h+var_38]
0x18000bec2  mov     ecx, r14d
0x18000bec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beca  mov     r8d, eax
0x18000becd  test    eax, eax
0x18000becf  jnz     short loc_18000BF13
0x18000bed1  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000bed5  mov     ecx, edx
0x18000bed7  mov     eax, [rsp+68h+var_28]
0x18000bedb  mov     [rsi+0Ch], eax
0x18000bede  mov     eax, edx
0x18000bee0  shr     eax, 0Eh
0x18000bee3  shr     ecx, 4
0x18000bee6  and     eax, 3
0x18000bee9  and     ecx, 3
0x18000beec  mov     [rsi+8], eax
0x18000beef  mov     [rsi], ecx
0x18000bef1  mov     eax, edx
0x18000bef3  mov     ecx, edx
0x18000bef5  shr     eax, 6
0x18000bef8  shr     ecx, 8
0x18000befb  and     eax, ebx
0x18000befd  and     cl, 3Fh
0x18000bf00  shr     edx, 7
0x18000bf03  and     edx, ebx
0x18000bf05  mov     [rsi+4], cl
0x18000bf08  mov     [rsi+10h], edx
0x18000bf0b  mov     [rsi+14h], eax
0x18000bf0e  jmp     loc_18000BE7E
0x18000bf13  cmp     eax, 117h
0x18000bf18  jnz     loc_18000BE7C
0x18000bf1e  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000bf22  shr     eax, 7
0x18000bf25  and     eax, ebx
0x18000bf27  mov     [rsi+10h], eax
0x18000bf2a  jmp     loc_18000BE7E
```
