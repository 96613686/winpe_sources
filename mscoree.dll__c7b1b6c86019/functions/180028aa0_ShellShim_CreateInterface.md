# ShellShim_CreateInterface

- ea: `0x180028aa0`
- end: `0x180028b35`
- name: `ShellShim_CreateInterface`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180028aa0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180028afe`
- `KERNEL32!GetProcAddress` at `0x180028afe`

## string_xrefs

- `0x180028af7`: `CreateInterface`

## pseudocode

```c
__int64 __fastcall ShellShim_CreateInterface(__int64 a1, __int64 a2, __int64 a3)
{
  int ShimImpl; // eax
  int (*ProcAddress)(const struct _GUID *, const struct _GUID *, void **); // rax
  HMODULE hModule; // [rsp+48h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return 2147500033LL;
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  ProcAddress = g_pfCreateInterface;
  if ( g_pfCreateInterface == (int (*)(const struct _GUID *, const struct _GUID *, void **))-1LL )
  {
    ProcAddress = (int (*)(const struct _GUID *, const struct _GUID *, void **))GetProcAddress(
                                                                                  hModule,
                                                                                  "CreateInterface");
    g_pfCreateInterface = ProcAddress;
  }
  if ( !ProcAddress )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, __int64, __int64))ProcAddress)(a1, a2, a3);
}

```

## disassembly

```asm
0x180028aa0  mov     rax, rsp
0x180028aa3  mov     [rax+8], rbx
0x180028aa7  mov     [rax+10h], rsi
0x180028aab  push    rdi
0x180028aac  sub     rsp, 20h
0x180028ab0  mov     rsi, rcx
0x180028ab3  mov     qword ptr [rax+20h], 0
0x180028abb  lea     rcx, [rax+20h]
0x180028abf  mov     rbx, r8
0x180028ac2  mov     rdi, rdx
0x180028ac5  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180028aca  cmp     eax, 1
0x180028acd  jz      short loc_180028B20
0x180028acf  cmp     eax, 3
0x180028ad2  jnz     short loc_180028ADB
0x180028ad4  mov     eax, 80004001h
0x180028ad9  jmp     short loc_180028B25
0x180028adb  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180028ae1  test    eax, eax
0x180028ae3  jnz     short loc_180028B20
0x180028ae5  mov     rax, cs:?g_pfCreateInterface@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*g_pfCreateInterface)(_GUID const &,_GUID const &,void * *)
0x180028aec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028af0  jnz     short loc_180028B0B
0x180028af2  mov     rcx, [rsp+28h+hModule]; hModule
0x180028af7  lea     rdx, aCreateinterfac_0; "CreateInterface"
0x180028afe  call    cs:__imp_GetProcAddress
0x180028b04  mov     cs:?g_pfCreateInterface@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA, rax; long (*g_pfCreateInterface)(_GUID const &,_GUID const &,void * *)
0x180028b0b  test    rax, rax
0x180028b0e  jz      short loc_180028B20
0x180028b10  mov     r8, rbx
0x180028b13  mov     rdx, rdi
0x180028b16  mov     rcx, rsi
0x180028b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b1e  jmp     short loc_180028B25
0x180028b20  mov     eax, 80131701h
0x180028b25  mov     rbx, [rsp+28h+arg_0]
0x180028b2a  mov     rsi, [rsp+28h+arg_8]
0x180028b2f  add     rsp, 20h
0x180028b33  pop     rdi
0x180028b34  retn
```
