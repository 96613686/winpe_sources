# GetPathFromIDList

- ea: `0x1800109f4`
- end: `0x180010a45`
- name: `GetPathFromIDList`
- size: `81`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64))(__int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ffac`
- `0x180010140`
- `0x180010828`
- `0x180010978`

## callees

- `0x1800109f4`
- `0x180010cdc`
- `0x180015010`

## string_xrefs

- `0x180010a10`: `SHGetPathFromIDListW`
- `0x180010a17`: `SHGetPathFromIDListW`

## pseudocode

```c
__int64 (__fastcall *__fastcall GetPathFromIDList(__int64 a1, __int64 a2))(__int64, __int64)
{
  __int64 (__fastcall *result)(__int64, __int64); // rax

  result = (__int64 (__fastcall *)(__int64, __int64))g_pfnSHGetPathFromIDListW;
  if ( g_pfnSHGetPathFromIDListW )
    return (__int64 (__fastcall *)(__int64, __int64))result(a1, a2);
  result = (__int64 (__fastcall *)(__int64, __int64))GetShell32Procs("SHGetPathFromIDListW");
  g_pfnSHGetPathFromIDListW = (__int64)result;
  if ( result )
    return (__int64 (__fastcall *)(__int64, __int64))result(a1, a2);
  return result;
}

```

## disassembly

```asm
0x1800109f4  mov     [rsp+arg_0], rbx
0x1800109f9  push    rdi
0x1800109fa  sub     rsp, 20h
0x1800109fe  mov     rax, cs:g_pfnSHGetPathFromIDListW
0x180010a05  mov     rbx, rdx
0x180010a08  mov     rdi, rcx
0x180010a0b  test    rax, rax
0x180010a0e  jnz     short loc_180010A2F
0x180010a10  lea     rdx, aShgetpathfromi_0; "SHGetPathFromIDListW"
0x180010a17  lea     rcx, aShgetpathfromi; "SHGetPathFromIDListW"
0x180010a1e  call    GetShell32Procs
0x180010a23  mov     cs:g_pfnSHGetPathFromIDListW, rax
0x180010a2a  test    rax, rax
0x180010a2d  jz      short loc_180010A3A
0x180010a2f  mov     rdx, rbx
0x180010a32  mov     rcx, rdi
0x180010a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a3a  mov     rbx, [rsp+28h+arg_0]
0x180010a3f  add     rsp, 20h
0x180010a43  pop     rdi
0x180010a44  retn
```
