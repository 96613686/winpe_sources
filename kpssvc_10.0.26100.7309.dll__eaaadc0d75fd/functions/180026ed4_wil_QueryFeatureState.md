# wil_QueryFeatureState

- ea: `0x180026ed4`
- end: `0x18002703a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001e3b8`

## callees

- `0x180026ed4`
- `0x180031040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026f70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026f70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026f53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026f53`

## string_xrefs

- `0x180026f4c`: `ntdll.dll`
- `0x180026f66`: `RtlQueryFeatureConfiguration`

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
0x180026ed4  mov     [rsp+arg_10], rbx
0x180026ed9  push    rbp
0x180026eda  push    rsi
0x180026edb  push    rdi
0x180026edc  push    r14
0x180026ede  push    r15
0x180026ee0  sub     rsp, 50h
0x180026ee4  mov     rax, cs:__security_cookie
0x180026eeb  xor     rax, rsp
0x180026eee  mov     [rsp+78h+var_30], rax
0x180026ef3  mov     rdi, [rsp+78h+arg_20]
0x180026efb  xor     ebx, ebx
0x180026efd  mov     rax, [rsp+78h+arg_28]
0x180026f05  mov     r15d, edx
0x180026f08  mov     rsi, rcx
0x180026f0b  test    rdi, rdi
0x180026f0e  jz      short loc_180026F12
0x180026f10  mov     [rdi], ebx
0x180026f12  test    r8d, r8d
0x180026f15  mov     dword ptr [rax], 1
0x180026f1b  mov     r14d, ebx
0x180026f1e  mov     [rsp+78h+var_48], rbx
0x180026f23  setz    r14b
0x180026f27  mov     ebp, ebx
0x180026f29  xor     eax, eax
0x180026f2b  mov     [rsp+78h+var_40], rax
0x180026f30  mov     [rsp+78h+var_38], eax
0x180026f34  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180026f3b  test    rax, rax
0x180026f3e  jnz     short loc_180026F8F
0x180026f40  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026f47  test    rax, rax
0x180026f4a  jnz     short loc_180026F66
0x180026f4c  lea     rcx, ModuleName; "ntdll.dll"
0x180026f53  call    cs:__imp_GetModuleHandleW
0x180026f5a  nop     dword ptr [rax+rax+00h]
0x180026f5f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026f66  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180026f6d  mov     rcx, rax; hModule
0x180026f70  call    cs:__imp_GetProcAddress
0x180026f77  nop     dword ptr [rax+rax+00h]
0x180026f7c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180026f83  test    rax, rax
0x180026f86  jnz     short loc_180026F8F
0x180026f88  mov     edx, 0C0000139h
0x180026f8d  jmp     short loc_180027006
0x180026f8f  lea     r9, [rsp+78h+var_40]
0x180026f94  mov     edx, r14d
0x180026f97  lea     r8, [rsp+78h+var_48]
0x180026f9c  mov     ecx, r15d
0x180026f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa4  mov     edx, eax
0x180026fa6  mov     ecx, eax
0x180026fa8  test    eax, eax
0x180026faa  jnz     short loc_180026FEC
0x180026fac  mov     ecx, dword ptr [rsp+78h+var_40+4]
0x180026fb0  mov     eax, ecx
0x180026fb2  shr     eax, 4
0x180026fb5  and     eax, 3
0x180026fb8  mov     [rsi], eax
0x180026fba  mov     eax, ecx
0x180026fbc  shr     eax, 8
0x180026fbf  and     al, 3Fh
0x180026fc1  mov     [rsi+4], al
0x180026fc4  mov     eax, [rsp+78h+var_38]
0x180026fc8  mov     [rsi+0Ch], eax
0x180026fcb  mov     eax, ecx
0x180026fcd  shr     eax, 0Eh
0x180026fd0  and     eax, 3
0x180026fd3  mov     [rsi+8], eax
0x180026fd6  mov     eax, ecx
0x180026fd8  shr     eax, 6
0x180026fdb  and     eax, 1
0x180026fde  shr     ecx, 7
0x180026fe1  and     ecx, 1
0x180026fe4  mov     [rsi+14h], eax
0x180026fe7  mov     [rsi+10h], ecx
0x180026fea  jmp     short loc_180027001
0x180026fec  cmp     ecx, 117h
0x180026ff2  jnz     short loc_180027006
0x180026ff4  mov     eax, dword ptr [rsp+78h+var_40+4]
0x180026ff8  shr     eax, 7
0x180026ffb  and     eax, 1
0x180026ffe  mov     [rsi+10h], eax
0x180027001  mov     ebp, 1
0x180027006  test    rdi, rdi
0x180027009  jz      short loc_180027016
0x18002700b  cmp     edx, 80000022h
0x180027011  setnz   bl
0x180027014  mov     [rdi], ebx
0x180027016  mov     eax, ebp
0x180027018  mov     rcx, [rsp+78h+var_30]
0x18002701d  xor     rcx, rsp; StackCookie
0x180027020  call    __security_check_cookie
0x180027025  mov     rbx, [rsp+78h+arg_10]
0x18002702d  add     rsp, 50h
0x180027031  pop     r15
0x180027033  pop     r14
0x180027035  pop     rdi
0x180027036  pop     rsi
0x180027037  pop     rbp
0x180027038  retn
```
