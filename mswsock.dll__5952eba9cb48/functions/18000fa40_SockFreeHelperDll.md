# SockFreeHelperDll

- ea: `0x18000fa40`
- end: `0x18000fa94`
- name: `SockFreeHelperDll`
- size: `84`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008250`
- `0x18000a6b0`
- `0x18000d000`
- `0x18000f25c`
- `0x180010440`
- `0x180010570`
- `0x180010f4c`
- `0x1800248fc`

## callees

- `0x18000fa40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000fa6b`
- `ntdll!RtlFreeHeap` at `0x18000fa6b`
- `ntdll!RtlFreeHeap` at `0x18000fa88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fa52`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fa52`

## pseudocode

```c
BOOLEAN __fastcall SockFreeHelperDll(__int64 a1)
{
  HMODULE v2; // rcx

  v2 = *(HMODULE *)(a1 + 24);
  if ( v2 )
    FreeLibrary(v2);
  RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(a1 + 56));
  return RtlFreeHeap(SockPrivateHeap, 0, (PVOID)a1);
}

```

## disassembly

```asm
0x18000fa40  push    rbx
0x18000fa42  sub     rsp, 20h
0x18000fa46  mov     rbx, rcx
0x18000fa49  mov     rcx, [rcx+18h]; hLibModule
0x18000fa4d  test    rcx, rcx
0x18000fa50  jz      short loc_18000FA5E
0x18000fa52  call    cs:__imp_FreeLibrary
0x18000fa59  nop     dword ptr [rax+rax+00h]
0x18000fa5e  mov     r8, [rbx+38h]; P
0x18000fa62  xor     edx, edx; Flags
0x18000fa64  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000fa6b  call    cs:__imp_RtlFreeHeap
0x18000fa72  nop     dword ptr [rax+rax+00h]
0x18000fa77  mov     rcx, cs:SockPrivateHeap
0x18000fa7e  mov     r8, rbx
0x18000fa81  xor     edx, edx
0x18000fa83  add     rsp, 20h
0x18000fa87  pop     rbx
0x18000fa88  jmp     cs:__imp_RtlFreeHeap
```
