# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x180095308`
- end: `0x1800953bd`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `181`
- prototype: `bool __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180095444`

## callees

- `0x180095308`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180095385`
- `KERNEL32!GetProcAddress` at `0x180095385`
- `KERNEL32!GetModuleHandleW` at `0x18009536f`
- `KERNEL32!GetModuleHandleW` at `0x18009536f`

## string_xrefs

- `0x180095368`: `ntdll.dll`
- `0x18009537e`: `RtlAreLongPathsEnabled`

## pseudocode

```c
char __fastcall AreOptionsValidAndOptInLongPathAwareProcess(enum PATHCCH_OPTIONS *a1)
{
  __int64 v2; // rdx
  unsigned __int32 v3; // r9d
  __int64 (*ProcAddress)(void); // rax
  HMODULE ModuleHandleW; // rax
  int v7; // ecx
  enum PATHCCH_OPTIONS v8; // ecx
  char v9; // al

  v2 = *a1 & 6;
  if ( (*a1 & 1) != 0 )
  {
    if ( (_DWORD)v2 && ((v2 - 1) & (unsigned int)v2) != 0 )
      return 0;
  }
  else if ( (_DWORD)v2 )
  {
    return 0;
  }
  v3 = *a1 & 0x11;
  if ( v3 && ((v3 - 1LL) & v3) != 0 )
    return 0;
  if ( (*a1 & 1) != 0 && !(_DWORD)v2 )
  {
    ProcAddress = (__int64 (*)(void))`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled;
    if ( `RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled
      || (ModuleHandleW = GetModuleHandleW(L"ntdll.dll"),
          ProcAddress = GetProcAddress(ModuleHandleW, "RtlAreLongPathsEnabled"),
          (`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled = (__int64)ProcAddress) != 0) )
    {
      v9 = ProcAddress();
      v7 = *a1;
      if ( v9 )
      {
        v8 = v7 | 2;
        goto LABEL_15;
      }
    }
    else
    {
      v7 = *a1;
    }
    v8 = v7 | 4;
LABEL_15:
    *a1 = v8;
  }
  return 1;
}

```

## disassembly

```asm
0x180095308  push    rbx
0x18009530a  sub     rsp, 20h
0x18009530e  mov     r9d, [rcx]
0x180095311  mov     rbx, rcx
0x180095314  mov     edx, r9d
0x180095317  mov     r8d, r9d
0x18009531a  and     edx, 6
0x18009531d  and     r8d, 1
0x180095321  jz      short loc_180095334
0x180095323  test    edx, edx
0x180095325  jz      short loc_18009533D
0x180095327  mov     ecx, edx
0x180095329  lea     rax, [rdx-1]
0x18009532d  test    rcx, rax
0x180095330  jnz     short loc_18009534F
0x180095332  jmp     short loc_18009533D
0x180095334  test    edx, edx
0x180095336  jz      short loc_18009533D
0x180095338  test    r8d, r8d
0x18009533b  jz      short loc_18009534F
0x18009533d  and     r9d, 11h
0x180095341  jz      short loc_180095353
0x180095343  mov     ecx, r9d
0x180095346  lea     rax, [r9-1]
0x18009534a  test    rcx, rax
0x18009534d  jz      short loc_180095353
0x18009534f  xor     al, al
0x180095351  jmp     short loc_1800953A6
0x180095353  test    r8d, r8d
0x180095356  jz      short loc_1800953A4
0x180095358  test    edx, edx
0x18009535a  jnz     short loc_1800953A4
0x18009535c  mov     rax, cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180095363  test    rax, rax
0x180095366  jnz     short loc_1800953AD
0x180095368  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18009536f  call    cs:__imp_GetModuleHandleW
0x180095376  nop     dword ptr [rax+rax+00h]
0x18009537b  mov     rcx, rax; hModule
0x18009537e  lea     rdx, aRtlarelongpath; "RtlAreLongPathsEnabled"
0x180095385  call    cs:__imp_GetProcAddress
0x18009538c  nop     dword ptr [rax+rax+00h]
0x180095391  mov     cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA, rax; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180095398  test    rax, rax
0x18009539b  jnz     short loc_1800953AD
0x18009539d  mov     ecx, [rbx]
0x18009539f  or      ecx, 4
0x1800953a2  mov     [rbx], ecx
0x1800953a4  mov     al, 1
0x1800953a6  add     rsp, 20h
0x1800953aa  pop     rbx
0x1800953ab  retn
0x1800953ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800953b2  mov     ecx, [rbx]
0x1800953b4  test    al, al
0x1800953b6  jz      short loc_18009539F
0x1800953b8  or      ecx, 2
0x1800953bb  jmp     short loc_1800953A2
```
