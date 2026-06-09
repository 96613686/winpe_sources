# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x180092f54`
- end: `0x180092ffc`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `168`
- prototype: `bool __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180093084`

## callees

- `0x180092f54`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180092fcb`
- `KERNEL32!GetProcAddress` at `0x180092fcb`
- `KERNEL32!GetModuleHandleW` at `0x180092fbb`
- `KERNEL32!GetModuleHandleW` at `0x180092fbb`

## string_xrefs

- `0x180092fb4`: `ntdll.dll`
- `0x180092fc4`: `RtlAreLongPathsEnabled`

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
0x180092f54  push    rbx
0x180092f56  sub     rsp, 20h
0x180092f5a  mov     r9d, [rcx]
0x180092f5d  mov     rbx, rcx
0x180092f60  mov     edx, r9d
0x180092f63  mov     r8d, r9d
0x180092f66  and     edx, 6
0x180092f69  and     r8d, 1
0x180092f6d  jz      short loc_180092F80
0x180092f6f  test    edx, edx
0x180092f71  jz      short loc_180092F89
0x180092f73  mov     ecx, edx
0x180092f75  lea     rax, [rdx-1]
0x180092f79  test    rcx, rax
0x180092f7c  jnz     short loc_180092F9B
0x180092f7e  jmp     short loc_180092F89
0x180092f80  test    edx, edx
0x180092f82  jz      short loc_180092F89
0x180092f84  test    r8d, r8d
0x180092f87  jz      short loc_180092F9B
0x180092f89  and     r9d, 11h
0x180092f8d  jz      short loc_180092F9F
0x180092f8f  mov     ecx, r9d
0x180092f92  lea     rax, [r9-1]
0x180092f96  test    rcx, rax
0x180092f99  jz      short loc_180092F9F
0x180092f9b  xor     al, al
0x180092f9d  jmp     short loc_180092FE6
0x180092f9f  test    r8d, r8d
0x180092fa2  jz      short loc_180092FE4
0x180092fa4  test    edx, edx
0x180092fa6  jnz     short loc_180092FE4
0x180092fa8  mov     rax, cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180092faf  test    rax, rax
0x180092fb2  jnz     short loc_180092FEC
0x180092fb4  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180092fbb  call    cs:__imp_GetModuleHandleW
0x180092fc1  mov     rcx, rax; hModule
0x180092fc4  lea     rdx, aRtlarelongpath; "RtlAreLongPathsEnabled"
0x180092fcb  call    cs:__imp_GetProcAddress
0x180092fd1  mov     cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA, rax; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180092fd8  test    rax, rax
0x180092fdb  jnz     short loc_180092FEC
0x180092fdd  mov     ecx, [rbx]
0x180092fdf  or      ecx, 4
0x180092fe2  mov     [rbx], ecx
0x180092fe4  mov     al, 1
0x180092fe6  add     rsp, 20h
0x180092fea  pop     rbx
0x180092feb  retn
0x180092fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ff1  mov     ecx, [rbx]
0x180092ff3  test    al, al
0x180092ff5  jz      short loc_180092FDF
0x180092ff7  or      ecx, 2
0x180092ffa  jmp     short loc_180092FE2
```
