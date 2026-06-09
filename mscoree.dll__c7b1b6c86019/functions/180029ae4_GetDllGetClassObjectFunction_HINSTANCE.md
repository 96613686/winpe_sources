# GetDllGetClassObjectFunction(HINSTANCE__ *)

- ea: `0x180029ae4`
- end: `0x180029b32`
- name: `?GetDllGetClassObjectFunction@@YAP6AJAEBU_GUID@@0PEAPEAX@ZPEAUHINSTANCE__@@@Z`
- size: `78`
- prototype: `int (*__fastcall(HINSTANCE hModule))(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d134`
- `0x18002e680`

## callees

- `0x180029ae4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180029af8`
- `KERNEL32!GetProcAddress` at `0x180029b1b`
- `KERNEL32!GetProcAddress` at `0x180029af8`
- `KERNEL32!GetProcAddress` at `0x180029b1b`
- `KERNEL32!GetLastError` at `0x180029b06`
- `KERNEL32!GetLastError` at `0x180029b06`

## string_xrefs

- `0x180029b11`: `DllGetClassObject`
- `0x180029aee`: `DllGetClassObjectInternal`

## pseudocode

```c
int (*__fastcall GetDllGetClassObjectFunction(HINSTANCE hModule))(const struct _GUID *, const struct _GUID *, void **)
{
  FARPROC ProcAddress; // rbx

  ProcAddress = GetProcAddress(hModule, "DllGetClassObjectInternal");
  if ( !ProcAddress && GetLastError() == 127 )
    return (int (*)(const struct _GUID *, const struct _GUID *, void **))GetProcAddress(hModule, "DllGetClassObject");
  return (int (*)(const struct _GUID *, const struct _GUID *, void **))ProcAddress;
}

```

## disassembly

```asm
0x180029ae4  mov     [rsp+arg_0], rbx
0x180029ae9  push    rdi
0x180029aea  sub     rsp, 20h
0x180029aee  lea     rdx, aDllgetclassobj_1; "DllGetClassObjectInternal"
0x180029af5  mov     rdi, rcx
0x180029af8  call    cs:__imp_GetProcAddress
0x180029afe  mov     rbx, rax
0x180029b01  test    rax, rax
0x180029b04  jnz     short loc_180029B24
0x180029b06  call    cs:__imp_GetLastError
0x180029b0c  cmp     eax, 7Fh
0x180029b0f  jnz     short loc_180029B24
0x180029b11  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180029b18  mov     rcx, rdi; hModule
0x180029b1b  call    cs:__imp_GetProcAddress
0x180029b21  mov     rbx, rax
0x180029b24  mov     rax, rbx
0x180029b27  mov     rbx, [rsp+28h+arg_0]
0x180029b2c  add     rsp, 20h
0x180029b30  pop     rdi
0x180029b31  retn
```
