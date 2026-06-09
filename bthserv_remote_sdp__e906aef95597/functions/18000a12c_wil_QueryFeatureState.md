# wil_QueryFeatureState

- ea: `0x18000a12c`
- end: `0x18000a292`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005fb4`
- `0x180034480`

## callees

- `0x1800017a0`
- `0x18000a12c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1c8`

## string_xrefs

- `0x18000a1a4`: `ntdll.dll`
- `0x18000a1be`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  int v6; // ebx
  BOOL v9; // r14d
  unsigned int v10; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ecx
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  int v18; // [rsp+40h] [rbp-38h]

  v6 = 0;
  if ( a5 )
    *a5 = 0;
  *a6 = 1;
  v16 = 0;
  v9 = a3 == 0;
  v10 = 0;
  v17 = 0;
  v18 = 0;
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
      v13 = -1073741511;
      goto LABEL_13;
    }
  }
  v13 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v16, &v17);
  if ( v13 )
  {
    if ( v13 != 279 )
      goto LABEL_13;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v14 = HIDWORD(v17);
    *(_DWORD *)a1 = (HIDWORD(v17) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v14) & 0x3F;
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)(a1 + 20) = (v14 >> 6) & 1;
    *(_DWORD *)(a1 + 16) = (v14 >> 7) & 1;
  }
  v10 = 1;
LABEL_13:
  if ( a5 )
  {
    LOBYTE(v6) = v13 != -2147483614;
    *a5 = v6;
  }
  return v10;
}

```

## disassembly

```asm
0x18000a12c  mov     [rsp+arg_10], rbx
0x18000a131  push    rbp
0x18000a132  push    rsi
0x18000a133  push    rdi
0x18000a134  push    r14
0x18000a136  push    r15
0x18000a138  sub     rsp, 50h
0x18000a13c  mov     rax, cs:__security_cookie
0x18000a143  xor     rax, rsp
0x18000a146  mov     [rsp+78h+var_30], rax
0x18000a14b  mov     rdi, [rsp+78h+arg_20]
0x18000a153  xor     ebx, ebx
0x18000a155  mov     rax, [rsp+78h+arg_28]
0x18000a15d  mov     r15d, edx
0x18000a160  mov     rsi, rcx
0x18000a163  test    rdi, rdi
0x18000a166  jz      short loc_18000A16A
0x18000a168  mov     [rdi], ebx
0x18000a16a  test    r8d, r8d
0x18000a16d  mov     dword ptr [rax], 1
0x18000a173  mov     r14d, ebx
0x18000a176  mov     [rsp+78h+var_48], rbx
0x18000a17b  setz    r14b
0x18000a17f  mov     ebp, ebx
0x18000a181  xor     eax, eax
0x18000a183  mov     [rsp+78h+var_40], rax
0x18000a188  mov     [rsp+78h+var_38], eax
0x18000a18c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a193  test    rax, rax
0x18000a196  jnz     short loc_18000A1E7
0x18000a198  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a19f  test    rax, rax
0x18000a1a2  jnz     short loc_18000A1BE
0x18000a1a4  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000a1ab  call    cs:__imp_GetModuleHandleW
0x18000a1b2  nop     dword ptr [rax+rax+00h]
0x18000a1b7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1be  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a1c5  mov     rcx, rax; hModule
0x18000a1c8  call    cs:__imp_GetProcAddress
0x18000a1cf  nop     dword ptr [rax+rax+00h]
0x18000a1d4  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a1db  test    rax, rax
0x18000a1de  jnz     short loc_18000A1E7
0x18000a1e0  mov     edx, 0C0000139h
0x18000a1e5  jmp     short loc_18000A25E
0x18000a1e7  lea     r9, [rsp+78h+var_40]
0x18000a1ec  mov     edx, r14d
0x18000a1ef  lea     r8, [rsp+78h+var_48]
0x18000a1f4  mov     ecx, r15d
0x18000a1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fc  mov     edx, eax
0x18000a1fe  mov     ecx, eax
0x18000a200  test    eax, eax
0x18000a202  jnz     short loc_18000A244
0x18000a204  mov     ecx, dword ptr [rsp+78h+var_40+4]
0x18000a208  mov     eax, ecx
0x18000a20a  shr     eax, 4
0x18000a20d  and     eax, 3
0x18000a210  mov     [rsi], eax
0x18000a212  mov     eax, ecx
0x18000a214  shr     eax, 8
0x18000a217  and     al, 3Fh
0x18000a219  mov     [rsi+4], al
0x18000a21c  mov     eax, [rsp+78h+var_38]
0x18000a220  mov     [rsi+0Ch], eax
0x18000a223  mov     eax, ecx
0x18000a225  shr     eax, 0Eh
0x18000a228  and     eax, 3
0x18000a22b  mov     [rsi+8], eax
0x18000a22e  mov     eax, ecx
0x18000a230  shr     eax, 6
0x18000a233  and     eax, 1
0x18000a236  shr     ecx, 7
0x18000a239  and     ecx, 1
0x18000a23c  mov     [rsi+14h], eax
0x18000a23f  mov     [rsi+10h], ecx
0x18000a242  jmp     short loc_18000A259
0x18000a244  cmp     ecx, 117h
0x18000a24a  jnz     short loc_18000A25E
0x18000a24c  mov     eax, dword ptr [rsp+78h+var_40+4]
0x18000a250  shr     eax, 7
0x18000a253  and     eax, 1
0x18000a256  mov     [rsi+10h], eax
0x18000a259  mov     ebp, 1
0x18000a25e  test    rdi, rdi
0x18000a261  jz      short loc_18000A26E
0x18000a263  cmp     edx, 80000022h
0x18000a269  setnz   bl
0x18000a26c  mov     [rdi], ebx
0x18000a26e  mov     eax, ebp
0x18000a270  mov     rcx, [rsp+78h+var_30]
0x18000a275  xor     rcx, rsp; StackCookie
0x18000a278  call    __security_check_cookie
0x18000a27d  mov     rbx, [rsp+78h+arg_10]
0x18000a285  add     rsp, 50h
0x18000a289  pop     r15
0x18000a28b  pop     r14
0x18000a28d  pop     rdi
0x18000a28e  pop     rsi
0x18000a28f  pop     rbp
0x18000a290  retn
```
