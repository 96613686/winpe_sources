# wil::last_error_context::~last_error_context(void)

- ea: `0x18000398c`
- end: `0x1800039a3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000525c`
- `0x1800060e0`
- `0x180008058`
- `0x18000808c`
- `0x180008afc`
- `0x180008c58`
- `0x180008e1c`

## callees

- `0x18000398c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003998`

## pseudocode

```c
void __fastcall wil::last_error_context::~last_error_context(wil::last_error_context *this)
{
  if ( !*(_BYTE *)this )
    SetLastError(*((_DWORD *)this + 1));
}

```

## disassembly

```asm
0x18000398c  sub     rsp, 28h
0x180003990  cmp     byte ptr [rcx], 0
0x180003993  jnz     short loc_18000399E
0x180003995  mov     ecx, [rcx+4]; dwErrCode
0x180003998  call    cs:__imp_SetLastError
0x18000399e  add     rsp, 28h
0x1800039a2  retn
```
