# ShellShim_GetXMLObject

- ea: `0x180025c30`
- end: `0x180025d11`
- name: `ShellShim_GetXMLObject`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c10`
- `0x180025c30`
- `0x1800352d8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025c8e`
- `KERNEL32!GetProcAddress` at `0x180025cd9`
- `KERNEL32!GetProcAddress` at `0x180025c8e`
- `KERNEL32!GetProcAddress` at `0x180025cd9`

## string_xrefs

- `0x180025c87`: `GetXMLObject_RetAddr`
- `0x180025cd2`: `GetXMLObject`

## pseudocode

```c
__int64 __fastcall ShellShim_GetXMLObject(__int64 a1)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+38h] [rbp+10h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return GetXMLObject(a1);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfGetXMLObject_RetAddr == (int (*)(struct IXMLParser **, void *))-1LL )
    g_pfGetXMLObject_RetAddr = (int (*)(struct IXMLParser **, void *))GetProcAddress(hModule, "GetXMLObject_RetAddr");
  if ( g_pfGetXMLObject_RetAddr )
    return ((__int64 (__fastcall *)(__int64, void *))g_pfGetXMLObject_RetAddr)(a1, retaddr);
  if ( g_pfGetXMLObject == (int (*)(struct IXMLParser **))-1LL )
    g_pfGetXMLObject = (int (*)(struct IXMLParser **))GetProcAddress(hModule, "GetXMLObject");
  if ( !g_pfGetXMLObject )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64))g_pfGetXMLObject)(a1);
}

```

## disassembly

```asm
0x180025c30  push    rbx
0x180025c32  sub     rsp, 20h
0x180025c36  mov     rbx, rcx
0x180025c39  mov     [rsp+28h+hModule], 0
0x180025c42  lea     rcx, [rsp+28h+hModule]
0x180025c47  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180025c4c  cmp     eax, 1
0x180025c4f  jz      loc_180025D06
0x180025c55  cmp     eax, 3
0x180025c58  jnz     short loc_180025C67
0x180025c5a  mov     rcx, rbx
0x180025c5d  add     rsp, 20h
0x180025c61  pop     rbx
0x180025c62  jmp     GetXMLObject
0x180025c67  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180025c6d  test    eax, eax
0x180025c6f  jnz     loc_180025D06
0x180025c75  mov     rax, cs:?g_pfGetXMLObject_RetAddr@@3R6AJPEAPEAUIXMLParser@@PEAX@ZEA; long (*g_pfGetXMLObject_RetAddr)(IXMLParser * *,void *)
0x180025c7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025c80  jnz     short loc_180025C9B
0x180025c82  mov     rcx, [rsp+28h+hModule]; hModule
0x180025c87  lea     rdx, aGetxmlobjectRe; "GetXMLObject_RetAddr"
0x180025c8e  call    cs:__imp_GetProcAddress
0x180025c94  mov     cs:?g_pfGetXMLObject_RetAddr@@3R6AJPEAPEAUIXMLParser@@PEAX@ZEA, rax; long (*g_pfGetXMLObject_RetAddr)(IXMLParser * *,void *)
0x180025c9b  mov     rax, cs:?g_pfGetXMLObject_RetAddr@@3R6AJPEAPEAUIXMLParser@@PEAX@ZEA; long (*g_pfGetXMLObject_RetAddr)(IXMLParser * *,void *)
0x180025ca2  test    rax, rax
0x180025ca5  jz      short loc_180025CC0
0x180025ca7  mov     rax, cs:?g_pfGetXMLObject_RetAddr@@3R6AJPEAPEAUIXMLParser@@PEAX@ZEA; long (*g_pfGetXMLObject_RetAddr)(IXMLParser * *,void *)
0x180025cae  mov     rcx, rbx
0x180025cb1  mov     rdx, [rsp+28h]
0x180025cb6  add     rsp, 20h
0x180025cba  pop     rbx
0x180025cbb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180025cc0  mov     rax, cs:?g_pfGetXMLObject@@3R6AJPEAPEAUIXMLParser@@@ZEA; long (*g_pfGetXMLObject)(IXMLParser * *)
0x180025cc7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025ccb  jnz     short loc_180025CE6
0x180025ccd  mov     rcx, [rsp+28h+hModule]; hModule
0x180025cd2  lea     rdx, aGetxmlobject_0; "GetXMLObject"
0x180025cd9  call    cs:__imp_GetProcAddress
0x180025cdf  mov     cs:?g_pfGetXMLObject@@3R6AJPEAPEAUIXMLParser@@@ZEA, rax; long (*g_pfGetXMLObject)(IXMLParser * *)
0x180025ce6  mov     rax, cs:?g_pfGetXMLObject@@3R6AJPEAPEAUIXMLParser@@@ZEA; long (*g_pfGetXMLObject)(IXMLParser * *)
0x180025ced  test    rax, rax
0x180025cf0  jz      short loc_180025D06
0x180025cf2  mov     rax, cs:?g_pfGetXMLObject@@3R6AJPEAPEAUIXMLParser@@@ZEA; long (*g_pfGetXMLObject)(IXMLParser * *)
0x180025cf9  mov     rcx, rbx
0x180025cfc  add     rsp, 20h
0x180025d00  pop     rbx
0x180025d01  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180025d06  mov     eax, 80131701h
0x180025d0b  add     rsp, 20h
0x180025d0f  pop     rbx
0x180025d10  retn
```
