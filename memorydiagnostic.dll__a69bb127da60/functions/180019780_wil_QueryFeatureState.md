# wil_QueryFeatureState

- ea: `0x180019780`
- end: `0x1800198e6`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000dbf4`
- `0x18002046c`

## callees

- `0x180002e50`
- `0x180019780`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180019805`
- `KERNEL32!GetModuleHandleW` at `0x180019805`
- `KERNEL32!GetProcAddress` at `0x18001981c`
- `KERNEL32!GetProcAddress` at `0x18001981c`

## string_xrefs

- `0x1800197fe`: `ntdll.dll`
- `0x180019812`: `RtlQueryFeatureConfiguration`

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
0x180019780  mov     [rsp+arg_10], rbx
0x180019785  mov     [rsp+arg_18], rbp
0x18001978a  push    rsi
0x18001978b  push    rdi
0x18001978c  push    r14
0x18001978e  sub     rsp, 50h
0x180019792  mov     rax, cs:__security_cookie
0x180019799  xor     rax, rsp
0x18001979c  mov     [rsp+68h+var_20], rax
0x1800197a1  mov     rdi, [rsp+68h+arg_20]
0x1800197a9  mov     r14d, edx
0x1800197ac  mov     rax, [rsp+68h+arg_28]
0x1800197b4  mov     rsi, rcx
0x1800197b7  test    rdi, rdi
0x1800197ba  jz      short loc_1800197C2
0x1800197bc  mov     dword ptr [rdi], 0
0x1800197c2  xor     ebp, ebp
0x1800197c4  mov     [rsp+68h+var_38], 0
0x1800197cd  test    r8d, r8d
0x1800197d0  mov     ebx, 1
0x1800197d5  mov     [rax], ebx
0x1800197d7  setz    bpl
0x1800197db  xor     eax, eax
0x1800197dd  mov     [rsp+68h+var_30], rax
0x1800197e2  mov     [rsp+68h+var_28], eax
0x1800197e6  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800197ed  test    rax, rax
0x1800197f0  jnz     short loc_18001986D
0x1800197f2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800197f9  test    rax, rax
0x1800197fc  jnz     short loc_180019812
0x1800197fe  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180019805  call    cs:__imp_GetModuleHandleW
0x18001980b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019812  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180019819  mov     rcx, rax; hModule
0x18001981c  call    cs:__imp_GetProcAddress
0x180019822  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180019829  test    rax, rax
0x18001982c  jnz     short loc_18001986D
0x18001982e  mov     r8d, 0C0000139h
0x180019834  xor     ebx, ebx
0x180019836  test    rdi, rdi
0x180019839  jz      short loc_180019849
0x18001983b  xor     ecx, ecx
0x18001983d  cmp     r8d, 80000022h
0x180019844  setnz   cl
0x180019847  mov     [rdi], ecx
0x180019849  mov     eax, ebx
0x18001984b  mov     rcx, [rsp+68h+var_20]
0x180019850  xor     rcx, rsp; StackCookie
0x180019853  call    __security_check_cookie
0x180019858  lea     r11, [rsp+68h+var_18]
0x18001985d  mov     rbx, [r11+30h]
0x180019861  mov     rbp, [r11+38h]
0x180019865  mov     rsp, r11
0x180019868  pop     r14
0x18001986a  pop     rdi
0x18001986b  pop     rsi
0x18001986c  retn
0x18001986d  lea     r9, [rsp+68h+var_30]
0x180019872  mov     edx, ebp
0x180019874  lea     r8, [rsp+68h+var_38]
0x180019879  mov     ecx, r14d
0x18001987c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019881  mov     r8d, eax
0x180019884  test    eax, eax
0x180019886  jnz     short loc_1800198CA
0x180019888  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001988c  mov     ecx, edx
0x18001988e  mov     eax, [rsp+68h+var_28]
0x180019892  mov     [rsi+0Ch], eax
0x180019895  mov     eax, edx
0x180019897  shr     eax, 0Eh
0x18001989a  shr     ecx, 4
0x18001989d  and     eax, 3
0x1800198a0  and     ecx, 3
0x1800198a3  mov     [rsi+8], eax
0x1800198a6  mov     [rsi], ecx
0x1800198a8  mov     eax, edx
0x1800198aa  mov     ecx, edx
0x1800198ac  shr     eax, 6
0x1800198af  shr     ecx, 8
0x1800198b2  and     eax, ebx
0x1800198b4  and     cl, 3Fh
0x1800198b7  shr     edx, 7
0x1800198ba  and     edx, ebx
0x1800198bc  mov     [rsi+4], cl
0x1800198bf  mov     [rsi+10h], edx
0x1800198c2  mov     [rsi+14h], eax
0x1800198c5  jmp     loc_180019836
0x1800198ca  cmp     eax, 117h
0x1800198cf  jnz     loc_180019834
0x1800198d5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800198d9  shr     eax, 7
0x1800198dc  and     eax, ebx
0x1800198de  mov     [rsi+10h], eax
0x1800198e1  jmp     loc_180019836
```
