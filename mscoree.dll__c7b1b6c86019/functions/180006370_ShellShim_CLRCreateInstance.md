# ShellShim_CLRCreateInstance

- ea: `0x180006370`
- end: `0x18000640f`
- name: `ShellShim_CLRCreateInstance`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002a90`
- `0x180006370`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800063d1`
- `KERNEL32!GetProcAddress` at `0x1800063d1`

## string_xrefs

- `0x1800063c7`: `CLRCreateInstance`

## pseudocode

```c
__int64 __fastcall ShellShim_CLRCreateInstance(__int64 a1, int (*a2)(unsigned __int16 *, void *), __int64 a3)
{
  HMODULE v3; // rbx
  int (*ProcAddress)(const struct _GUID *, const struct _GUID *, void **); // rax

  v3 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl(a1, a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v3 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return 2148734721LL;
  if ( (_DWORD)g_shimImplStatus != 3 )
  {
    if ( !g_bShimImplDllUninitialized )
    {
      ProcAddress = g_pfCLRCreateInstance;
      if ( g_pfCLRCreateInstance == (int (*)(const struct _GUID *, const struct _GUID *, void **))-1LL )
      {
        ProcAddress = (int (*)(const struct _GUID *, const struct _GUID *, void **))GetProcAddress(
                                                                                      v3,
                                                                                      "CLRCreateInstance");
        g_pfCLRCreateInstance = ProcAddress;
      }
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(__int64, int (*)(unsigned __int16 *, void *), __int64))ProcAddress)(a1, a2, a3);
    }
    return 2148734721LL;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180006370  push    rbx
0x180006372  push    rbp
0x180006373  push    rsi
0x180006374  push    rdi
0x180006375  sub     rsp, 28h
0x180006379  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x18000637f  xor     ebx, ebx
0x180006381  mov     rdi, r8
0x180006384  mov     rsi, rdx
0x180006387  mov     rbp, rcx
0x18000638a  test    eax, eax
0x18000638c  jz      short loc_180006401
0x18000638e  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180006394  cmp     eax, 2
0x180006397  jnz     short loc_1800063A0
0x180006399  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x1800063a0  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800063a6  cmp     eax, 1
0x1800063a9  jz      short loc_1800063FA
0x1800063ab  cmp     eax, 3
0x1800063ae  jz      short loc_180006408
0x1800063b0  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800063b6  test    eax, eax
0x1800063b8  jnz     short loc_1800063FA
0x1800063ba  mov     rax, cs:?g_pfCLRCreateInstance@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*g_pfCLRCreateInstance)(_GUID const &,_GUID const &,void * *)
0x1800063c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800063c5  jnz     short loc_1800063DE
0x1800063c7  lea     rdx, aClrcreateinsta_0; "CLRCreateInstance"
0x1800063ce  mov     rcx, rbx; hModule
0x1800063d1  call    cs:__imp_GetProcAddress
0x1800063d7  mov     cs:?g_pfCLRCreateInstance@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA, rax; long (*g_pfCLRCreateInstance)(_GUID const &,_GUID const &,void * *)
0x1800063de  test    rax, rax
0x1800063e1  jz      short loc_1800063FA
0x1800063e3  mov     r8, rdi
0x1800063e6  mov     rdx, rsi
0x1800063e9  mov     rcx, rbp
0x1800063ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f1  add     rsp, 28h
0x1800063f5  pop     rdi
0x1800063f6  pop     rsi
0x1800063f7  pop     rbp
0x1800063f8  pop     rbx
0x1800063f9  retn
0x1800063fa  mov     eax, 80131701h
0x1800063ff  jmp     short loc_1800063F1
0x180006401  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180006406  jmp     short loc_18000638E
0x180006408  mov     eax, 80004001h
0x18000640d  jmp     short loc_1800063F1
```
