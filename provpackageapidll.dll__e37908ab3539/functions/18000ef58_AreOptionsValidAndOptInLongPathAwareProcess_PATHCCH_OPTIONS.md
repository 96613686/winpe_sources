# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x18000ef58`
- end: `0x18000f000`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `168`
- prototype: `char __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000741c`
- `0x18000f040`

## callees

- `0x18000ef58`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efcf`

## string_xrefs

- `0x18000efb8`: `ntdll.dll`
- `0x18000efc8`: `RtlAreLongPathsEnabled`

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
0x18000ef58  push    rbx
0x18000ef5a  sub     rsp, 20h
0x18000ef5e  mov     r9d, [rcx]
0x18000ef61  mov     rbx, rcx
0x18000ef64  mov     edx, r9d
0x18000ef67  mov     r8d, r9d
0x18000ef6a  and     edx, 6
0x18000ef6d  and     r8d, 1
0x18000ef71  jz      short loc_18000EF84
0x18000ef73  test    edx, edx
0x18000ef75  jz      short loc_18000EF8D
0x18000ef77  mov     ecx, edx
0x18000ef79  lea     rax, [rdx-1]
0x18000ef7d  test    rcx, rax
0x18000ef80  jnz     short loc_18000EF9F
0x18000ef82  jmp     short loc_18000EF8D
0x18000ef84  test    edx, edx
0x18000ef86  jz      short loc_18000EF8D
0x18000ef88  test    r8d, r8d
0x18000ef8b  jz      short loc_18000EF9F
0x18000ef8d  and     r9d, 11h
0x18000ef91  jz      short loc_18000EFA3
0x18000ef93  mov     ecx, r9d
0x18000ef96  lea     rax, [r9-1]
0x18000ef9a  test    rcx, rax
0x18000ef9d  jz      short loc_18000EFA3
0x18000ef9f  xor     al, al
0x18000efa1  jmp     short loc_18000EFEA
0x18000efa3  test    r8d, r8d
0x18000efa6  jz      short loc_18000EFE8
0x18000efa8  test    edx, edx
0x18000efaa  jnz     short loc_18000EFE8
0x18000efac  mov     rax, cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x18000efb3  test    rax, rax
0x18000efb6  jnz     short loc_18000EFF0
0x18000efb8  lea     rcx, ModuleName; "ntdll.dll"
0x18000efbf  call    cs:__imp_GetModuleHandleW
0x18000efc5  mov     rcx, rax; hModule
0x18000efc8  lea     rdx, aRtlarelongpath; "RtlAreLongPathsEnabled"
0x18000efcf  call    cs:__imp_GetProcAddress
0x18000efd5  mov     cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA, rax; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x18000efdc  test    rax, rax
0x18000efdf  jnz     short loc_18000EFF0
0x18000efe1  mov     ecx, [rbx]
0x18000efe3  or      ecx, 4
0x18000efe6  mov     [rbx], ecx
0x18000efe8  mov     al, 1
0x18000efea  add     rsp, 20h
0x18000efee  pop     rbx
0x18000efef  retn
0x18000eff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff5  mov     ecx, [rbx]
0x18000eff7  test    al, al
0x18000eff9  jz      short loc_18000EFE3
0x18000effb  or      ecx, 2
0x18000effe  jmp     short loc_18000EFE6
```
