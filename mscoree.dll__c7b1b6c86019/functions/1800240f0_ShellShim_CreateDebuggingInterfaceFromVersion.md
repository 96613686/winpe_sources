# ShellShim_CreateDebuggingInterfaceFromVersion

- ea: `0x1800240f0`
- end: `0x1800241f1`
- name: `ShellShim_CreateDebuggingInterfaceFromVersion`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800240f0`
- `0x18002fde8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024160`
- `KERNEL32!GetProcAddress` at `0x1800241ad`
- `KERNEL32!GetProcAddress` at `0x180024160`
- `KERNEL32!GetProcAddress` at `0x1800241ad`

## string_xrefs

- `0x180024159`: `CreateDebuggingInterfaceFromVersion_RetAddr`
- `0x1800241a6`: `CreateDebuggingInterfaceFromVersion`

## pseudocode

```c
__int64 __fastcall ShellShim_CreateDebuggingInterfaceFromVersion(unsigned int a1, wchar_t *a2, _QWORD *a3)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return CreateDebuggingInterfaceFromVersion(a1, a2, a3);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfCreateDebuggingInterfaceFromVersion_RetAddr == (int (*)(int, const unsigned __int16 *, struct IUnknown **, void *))-1LL )
    g_pfCreateDebuggingInterfaceFromVersion_RetAddr = (int (*)(int, const unsigned __int16 *, struct IUnknown **, void *))GetProcAddress(hModule, "CreateDebuggingInterfaceFromVersion_RetAddr");
  if ( g_pfCreateDebuggingInterfaceFromVersion_RetAddr )
    return ((__int64 (__fastcall *)(_QWORD, wchar_t *, _QWORD *, void *))g_pfCreateDebuggingInterfaceFromVersion_RetAddr)(
             a1,
             a2,
             a3,
             retaddr);
  if ( g_pfCreateDebuggingInterfaceFromVersion == (int (*)(int, const unsigned __int16 *, struct IUnknown **))-1LL )
    g_pfCreateDebuggingInterfaceFromVersion = (int (*)(int, const unsigned __int16 *, struct IUnknown **))GetProcAddress(hModule, "CreateDebuggingInterfaceFromVersion");
  if ( !g_pfCreateDebuggingInterfaceFromVersion )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(_QWORD, wchar_t *, _QWORD *))g_pfCreateDebuggingInterfaceFromVersion)(a1, a2, a3);
}

```

## disassembly

```asm
0x1800240f0  mov     rax, rsp
0x1800240f3  mov     [rax+8], rbx
0x1800240f7  mov     [rax+10h], rsi
0x1800240fb  push    rdi
0x1800240fc  sub     rsp, 30h
0x180024100  mov     esi, ecx
0x180024102  mov     qword ptr [rax+20h], 0
0x18002410a  lea     rcx, [rax+20h]
0x18002410e  mov     rbx, r8
0x180024111  mov     rdi, rdx
0x180024114  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180024119  cmp     eax, 1
0x18002411c  jz      loc_1800241DC
0x180024122  cmp     eax, 3
0x180024125  jnz     short loc_180024139
0x180024127  mov     r8, rbx
0x18002412a  mov     rdx, rdi
0x18002412d  mov     ecx, esi
0x18002412f  call    CreateDebuggingInterfaceFromVersion
0x180024134  jmp     loc_1800241E1
0x180024139  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x18002413f  test    eax, eax
0x180024141  jnz     loc_1800241DC
0x180024147  mov     rax, cs:?g_pfCreateDebuggingInterfaceFromVersion_RetAddr@@3R6AJHPEBGPEAPEAUIUnknown@@PEAX@ZEA; long (*g_pfCreateDebuggingInterfaceFromVersion_RetAddr)(int,ushort const *,IUnknown * *,void *)
0x18002414e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024152  jnz     short loc_18002416D
0x180024154  mov     rcx, [rsp+38h+hModule]; hModule
0x180024159  lea     rdx, aCreatedebuggin_0; "CreateDebuggingInterfaceFromVersion_Ret"...
0x180024160  call    cs:__imp_GetProcAddress
0x180024166  mov     cs:?g_pfCreateDebuggingInterfaceFromVersion_RetAddr@@3R6AJHPEBGPEAPEAUIUnknown@@PEAX@ZEA, rax; long (*g_pfCreateDebuggingInterfaceFromVersion_RetAddr)(int,ushort const *,IUnknown * *,void *)
0x18002416d  mov     rax, cs:?g_pfCreateDebuggingInterfaceFromVersion_RetAddr@@3R6AJHPEBGPEAPEAUIUnknown@@PEAX@ZEA; long (*g_pfCreateDebuggingInterfaceFromVersion_RetAddr)(int,ushort const *,IUnknown * *,void *)
0x180024174  test    rax, rax
0x180024177  jz      short loc_180024194
0x180024179  mov     rax, cs:?g_pfCreateDebuggingInterfaceFromVersion_RetAddr@@3R6AJHPEBGPEAPEAUIUnknown@@PEAX@ZEA; long (*g_pfCreateDebuggingInterfaceFromVersion_RetAddr)(int,ushort const *,IUnknown * *,void *)
0x180024180  mov     r8, rbx
0x180024183  mov     r9, [rsp+38h]
0x180024188  mov     rdx, rdi
0x18002418b  mov     ecx, esi
0x18002418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024192  jmp     short loc_1800241E1
0x180024194  mov     rax, cs:?g_pfCreateDebuggingInterfaceFromVersion@@3R6AJHPEBGPEAPEAUIUnknown@@@ZEA; long (*g_pfCreateDebuggingInterfaceFromVersion)(int,ushort const *,IUnknown * *)
0x18002419b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002419f  jnz     short loc_1800241BA
0x1800241a1  mov     rcx, [rsp+38h+hModule]; hModule
0x1800241a6  lea     rdx, aCreatedebuggin_1; "CreateDebuggingInterfaceFromVersion"
0x1800241ad  call    cs:__imp_GetProcAddress
0x1800241b3  mov     cs:?g_pfCreateDebuggingInterfaceFromVersion@@3R6AJHPEBGPEAPEAUIUnknown@@@ZEA, rax; long (*g_pfCreateDebuggingInterfaceFromVersion)(int,ushort const *,IUnknown * *)
0x1800241ba  mov     rax, cs:?g_pfCreateDebuggingInterfaceFromVersion@@3R6AJHPEBGPEAPEAUIUnknown@@@ZEA; long (*g_pfCreateDebuggingInterfaceFromVersion)(int,ushort const *,IUnknown * *)
0x1800241c1  test    rax, rax
0x1800241c4  jz      short loc_1800241DC
0x1800241c6  mov     rax, cs:?g_pfCreateDebuggingInterfaceFromVersion@@3R6AJHPEBGPEAPEAUIUnknown@@@ZEA; long (*g_pfCreateDebuggingInterfaceFromVersion)(int,ushort const *,IUnknown * *)
0x1800241cd  mov     r8, rbx
0x1800241d0  mov     rdx, rdi
0x1800241d3  mov     ecx, esi
0x1800241d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241da  jmp     short loc_1800241E1
0x1800241dc  mov     eax, 80131701h
0x1800241e1  mov     rbx, [rsp+38h+arg_0]
0x1800241e6  mov     rsi, [rsp+38h+arg_8]
0x1800241eb  add     rsp, 30h
0x1800241ef  pop     rdi
0x1800241f0  retn
```
