# wil_QueryFeatureState

- ea: `0x18001a748`
- end: `0x18001a8ae`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e634`
- `0x180021adc`

## callees

- `0x1800026b0`
- `0x18001a748`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001a7c7`
- `KERNEL32!GetModuleHandleW` at `0x18001a7c7`
- `KERNEL32!GetProcAddress` at `0x18001a7e4`
- `KERNEL32!GetProcAddress` at `0x18001a7e4`

## string_xrefs

- `0x18001a7c0`: `ntdll.dll`
- `0x18001a7da`: `RtlQueryFeatureConfiguration`

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
0x18001a748  mov     [rsp+arg_10], rbx
0x18001a74d  push    rbp
0x18001a74e  push    rsi
0x18001a74f  push    rdi
0x18001a750  push    r14
0x18001a752  push    r15
0x18001a754  sub     rsp, 50h
0x18001a758  mov     rax, cs:__security_cookie
0x18001a75f  xor     rax, rsp
0x18001a762  mov     [rsp+78h+var_30], rax
0x18001a767  mov     rdi, [rsp+78h+arg_20]
0x18001a76f  xor     ebx, ebx
0x18001a771  mov     rax, [rsp+78h+arg_28]
0x18001a779  mov     r15d, edx
0x18001a77c  mov     rsi, rcx
0x18001a77f  test    rdi, rdi
0x18001a782  jz      short loc_18001A786
0x18001a784  mov     [rdi], ebx
0x18001a786  test    r8d, r8d
0x18001a789  mov     dword ptr [rax], 1
0x18001a78f  mov     r14d, ebx
0x18001a792  mov     [rsp+78h+var_48], rbx
0x18001a797  setz    r14b
0x18001a79b  mov     ebp, ebx
0x18001a79d  xor     eax, eax
0x18001a79f  mov     [rsp+78h+var_40], rax
0x18001a7a4  mov     [rsp+78h+var_38], eax
0x18001a7a8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001a7af  test    rax, rax
0x18001a7b2  jnz     short loc_18001A803
0x18001a7b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a7bb  test    rax, rax
0x18001a7be  jnz     short loc_18001A7DA
0x18001a7c0  lea     rcx, ModuleName; "ntdll.dll"
0x18001a7c7  call    cs:__imp_GetModuleHandleW
0x18001a7ce  nop     dword ptr [rax+rax+00h]
0x18001a7d3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a7da  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001a7e1  mov     rcx, rax; hModule
0x18001a7e4  call    cs:__imp_GetProcAddress
0x18001a7eb  nop     dword ptr [rax+rax+00h]
0x18001a7f0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001a7f7  test    rax, rax
0x18001a7fa  jnz     short loc_18001A803
0x18001a7fc  mov     edx, 0C0000139h
0x18001a801  jmp     short loc_18001A87A
0x18001a803  lea     r9, [rsp+78h+var_40]
0x18001a808  mov     edx, r14d
0x18001a80b  lea     r8, [rsp+78h+var_48]
0x18001a810  mov     ecx, r15d
0x18001a813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a818  mov     edx, eax
0x18001a81a  mov     ecx, eax
0x18001a81c  test    eax, eax
0x18001a81e  jnz     short loc_18001A860
0x18001a820  mov     ecx, dword ptr [rsp+78h+var_40+4]
0x18001a824  mov     eax, ecx
0x18001a826  shr     eax, 4
0x18001a829  and     eax, 3
0x18001a82c  mov     [rsi], eax
0x18001a82e  mov     eax, ecx
0x18001a830  shr     eax, 8
0x18001a833  and     al, 3Fh
0x18001a835  mov     [rsi+4], al
0x18001a838  mov     eax, [rsp+78h+var_38]
0x18001a83c  mov     [rsi+0Ch], eax
0x18001a83f  mov     eax, ecx
0x18001a841  shr     eax, 0Eh
0x18001a844  and     eax, 3
0x18001a847  mov     [rsi+8], eax
0x18001a84a  mov     eax, ecx
0x18001a84c  shr     eax, 6
0x18001a84f  and     eax, 1
0x18001a852  shr     ecx, 7
0x18001a855  and     ecx, 1
0x18001a858  mov     [rsi+14h], eax
0x18001a85b  mov     [rsi+10h], ecx
0x18001a85e  jmp     short loc_18001A875
0x18001a860  cmp     ecx, 117h
0x18001a866  jnz     short loc_18001A87A
0x18001a868  mov     eax, dword ptr [rsp+78h+var_40+4]
0x18001a86c  shr     eax, 7
0x18001a86f  and     eax, 1
0x18001a872  mov     [rsi+10h], eax
0x18001a875  mov     ebp, 1
0x18001a87a  test    rdi, rdi
0x18001a87d  jz      short loc_18001A88A
0x18001a87f  cmp     edx, 80000022h
0x18001a885  setnz   bl
0x18001a888  mov     [rdi], ebx
0x18001a88a  mov     eax, ebp
0x18001a88c  mov     rcx, [rsp+78h+var_30]
0x18001a891  xor     rcx, rsp; StackCookie
0x18001a894  call    __security_check_cookie
0x18001a899  mov     rbx, [rsp+78h+arg_10]
0x18001a8a1  add     rsp, 50h
0x18001a8a5  pop     r15
0x18001a8a7  pop     r14
0x18001a8a9  pop     rdi
0x18001a8aa  pop     rsi
0x18001a8ab  pop     rbp
0x18001a8ac  retn
```
