# wil_QueryFeatureState

- ea: `0x180012388`
- end: `0x1800124ee`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a3d0`

## callees

- `0x180002490`
- `0x180012388`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001240d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001240d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012424`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012424`

## string_xrefs

- `0x180012406`: `ntdll.dll`
- `0x18001241a`: `RtlQueryFeatureConfiguration`

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
0x180012388  mov     [rsp+arg_10], rbx
0x18001238d  mov     [rsp+arg_18], rbp
0x180012392  push    rsi
0x180012393  push    rdi
0x180012394  push    r14
0x180012396  sub     rsp, 50h
0x18001239a  mov     rax, cs:__security_cookie
0x1800123a1  xor     rax, rsp
0x1800123a4  mov     [rsp+68h+var_20], rax
0x1800123a9  mov     rdi, [rsp+68h+arg_20]
0x1800123b1  mov     r14d, edx
0x1800123b4  mov     rax, [rsp+68h+arg_28]
0x1800123bc  mov     rsi, rcx
0x1800123bf  test    rdi, rdi
0x1800123c2  jz      short loc_1800123CA
0x1800123c4  mov     dword ptr [rdi], 0
0x1800123ca  xor     ebp, ebp
0x1800123cc  mov     [rsp+68h+var_38], 0
0x1800123d5  test    r8d, r8d
0x1800123d8  mov     ebx, 1
0x1800123dd  mov     [rax], ebx
0x1800123df  setz    bpl
0x1800123e3  xor     eax, eax
0x1800123e5  mov     [rsp+68h+var_30], rax
0x1800123ea  mov     [rsp+68h+var_28], eax
0x1800123ee  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800123f5  test    rax, rax
0x1800123f8  jnz     short loc_180012475
0x1800123fa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012401  test    rax, rax
0x180012404  jnz     short loc_18001241A
0x180012406  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001240d  call    cs:__imp_GetModuleHandleW
0x180012413  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001241a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180012421  mov     rcx, rax; hModule
0x180012424  call    cs:__imp_GetProcAddress
0x18001242a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180012431  test    rax, rax
0x180012434  jnz     short loc_180012475
0x180012436  mov     r8d, 0C0000139h
0x18001243c  xor     ebx, ebx
0x18001243e  test    rdi, rdi
0x180012441  jz      short loc_180012451
0x180012443  xor     ecx, ecx
0x180012445  cmp     r8d, 80000022h
0x18001244c  setnz   cl
0x18001244f  mov     [rdi], ecx
0x180012451  mov     eax, ebx
0x180012453  mov     rcx, [rsp+68h+var_20]
0x180012458  xor     rcx, rsp; StackCookie
0x18001245b  call    __security_check_cookie
0x180012460  lea     r11, [rsp+68h+var_18]
0x180012465  mov     rbx, [r11+30h]
0x180012469  mov     rbp, [r11+38h]
0x18001246d  mov     rsp, r11
0x180012470  pop     r14
0x180012472  pop     rdi
0x180012473  pop     rsi
0x180012474  retn
0x180012475  lea     r9, [rsp+68h+var_30]
0x18001247a  mov     edx, ebp
0x18001247c  lea     r8, [rsp+68h+var_38]
0x180012481  mov     ecx, r14d
0x180012484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012489  mov     r8d, eax
0x18001248c  test    eax, eax
0x18001248e  jnz     short loc_1800124D2
0x180012490  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180012494  mov     ecx, edx
0x180012496  mov     eax, [rsp+68h+var_28]
0x18001249a  mov     [rsi+0Ch], eax
0x18001249d  mov     eax, edx
0x18001249f  shr     eax, 0Eh
0x1800124a2  shr     ecx, 4
0x1800124a5  and     eax, 3
0x1800124a8  and     ecx, 3
0x1800124ab  mov     [rsi+8], eax
0x1800124ae  mov     [rsi], ecx
0x1800124b0  mov     eax, edx
0x1800124b2  mov     ecx, edx
0x1800124b4  shr     eax, 6
0x1800124b7  shr     ecx, 8
0x1800124ba  and     eax, ebx
0x1800124bc  and     cl, 3Fh
0x1800124bf  shr     edx, 7
0x1800124c2  and     edx, ebx
0x1800124c4  mov     [rsi+4], cl
0x1800124c7  mov     [rsi+10h], edx
0x1800124ca  mov     [rsi+14h], eax
0x1800124cd  jmp     loc_18001243E
0x1800124d2  cmp     eax, 117h
0x1800124d7  jnz     loc_18001243C
0x1800124dd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800124e1  shr     eax, 7
0x1800124e4  and     eax, ebx
0x1800124e6  mov     [rsi+10h], eax
0x1800124e9  jmp     loc_18001243E
```
