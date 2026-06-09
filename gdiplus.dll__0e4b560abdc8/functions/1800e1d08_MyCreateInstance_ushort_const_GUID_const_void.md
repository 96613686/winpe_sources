# MyCreateInstance(ushort const *,_GUID const &,void * *)

- ea: `0x1800e1d08`
- end: `0x1800e1d67`
- name: `?MyCreateInstance@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18014dcd4`
- `0x18014ddf4`

## callees

- `0x1800e1d08`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1d38`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e1d1d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e1d1d`

## string_xrefs

- `0x1800e1d2e`: `CreateCodecInstance`

## pseudocode

```c
__int64 __fastcall MyCreateInstance(const unsigned __int16 *a1, const struct _GUID *a2, void **a3)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(a1, 0, 0);
  if ( Library && (ProcAddress = GetProcAddress(Library, "CreateCodecInstance")) != 0 )
    return ((__int64 (__fastcall *)(const struct _GUID *, void **))ProcAddress)(a2, a3);
  else
    return 2289762313LL;
}

```

## disassembly

```asm
0x1800e1d08  mov     [rsp+arg_0], rbx
0x1800e1d0d  push    rdi
0x1800e1d0e  sub     rsp, 20h
0x1800e1d12  mov     rbx, r8
0x1800e1d15  mov     rdi, rdx
0x1800e1d18  xor     r8d, r8d; dwFlags
0x1800e1d1b  xor     edx, edx; hFile
0x1800e1d1d  call    cs:__imp_LoadLibraryExW
0x1800e1d24  nop     dword ptr [rax+rax+00h]
0x1800e1d29  test    rax, rax
0x1800e1d2c  jz      short loc_1800E1D56
0x1800e1d2e  lea     rdx, ProcName; "CreateCodecInstance"
0x1800e1d35  mov     rcx, rax; hModule
0x1800e1d38  call    cs:__imp_GetProcAddress
0x1800e1d3f  nop     dword ptr [rax+rax+00h]
0x1800e1d44  test    rax, rax
0x1800e1d47  jz      short loc_1800E1D56
0x1800e1d49  mov     rdx, rbx
0x1800e1d4c  mov     rcx, rdi
0x1800e1d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1d54  jmp     short loc_1800E1D5B
0x1800e1d56  mov     eax, 887B0009h
0x1800e1d5b  mov     rbx, [rsp+28h+arg_0]
0x1800e1d60  add     rsp, 20h
0x1800e1d64  pop     rdi
0x1800e1d65  retn
```
