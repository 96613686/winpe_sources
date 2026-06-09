# dlMFCreateVideoSampleAllocatorEx

- ea: `0x18007355c`
- end: `0x1800735be`
- name: `dlMFCreateVideoSampleAllocatorEx`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002135c`
- `0x18004c980`
- `0x1800b72bc`

## callees

- `0x18005a110`
- `0x18007355c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180073573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180073573`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073583`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073583`

## string_xrefs

- `0x18007356c`: `MFPlat.dll`
- `0x18007357c`: `MFCreateVideoSampleAllocatorEx`
- `0x18007358e`: `Invalid pointer: MFCREATEVIDEOSAMPLEALLOCATOREX`
- `0x18007359a`: `dlMFCreateVideoSampleAllocatorEx`

## pseudocode

```c
__int64 __fastcall dlMFCreateVideoSampleAllocatorEx(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"MFPlat.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "MFCreateVideoSampleAllocatorEx");
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
  else
    return XvpOriginateError<48>(
             "dlMFCreateVideoSampleAllocatorEx",
             2147500037LL,
             L"Invalid pointer: MFCREATEVIDEOSAMPLEALLOCATOREX");
}

```

## disassembly

```asm
0x18007355c  mov     [rsp+arg_0], rbx
0x180073561  push    rdi
0x180073562  sub     rsp, 20h
0x180073566  mov     rdi, rcx
0x180073569  mov     rbx, rdx
0x18007356c  lea     rcx, aMfplatDll; "MFPlat.dll"
0x180073573  call    cs:__imp_GetModuleHandleW
0x180073579  mov     rcx, rax; hModule
0x18007357c  lea     rdx, aMfcreatevideos_0; "MFCreateVideoSampleAllocatorEx"
0x180073583  call    cs:__imp_GetProcAddress
0x180073589  test    rax, rax
0x18007358c  jnz     short loc_1800735A8
0x18007358e  lea     r8, aInvalidPointer_0; "Invalid pointer: MFCREATEVIDEOSAMPLEALL"...
0x180073595  mov     edx, 80004005h
0x18007359a  lea     rcx, aDlmfcreatevide; "dlMFCreateVideoSampleAllocatorEx"
0x1800735a1  call    ??$XvpOriginateError@$0DA@@@YAJQEADJAEAY0DA@$$CBG@Z; XvpOriginateError<48>(char * const,long,ushort const (&)[48])
0x1800735a6  jmp     short loc_1800735B3
0x1800735a8  mov     rdx, rbx
0x1800735ab  mov     rcx, rdi
0x1800735ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735b3  mov     rbx, [rsp+28h+arg_0]
0x1800735b8  add     rsp, 20h
0x1800735bc  pop     rdi
0x1800735bd  retn
```
