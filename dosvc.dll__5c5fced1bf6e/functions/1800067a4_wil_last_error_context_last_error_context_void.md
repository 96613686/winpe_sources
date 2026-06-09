# wil::last_error_context::~last_error_context(void)

- ea: `0x1800067a4`
- end: `0x1800067bb`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033c8`
- `0x18000789c`
- `0x180008558`

## callees

- `0x1800067a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067b0`

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
0x1800067a4  sub     rsp, 28h
0x1800067a8  cmp     byte ptr [rcx], 0
0x1800067ab  jnz     short loc_1800067B6
0x1800067ad  mov     ecx, [rcx+4]; dwErrCode
0x1800067b0  call    cs:__imp_SetLastError
0x1800067b6  add     rsp, 28h
0x1800067ba  retn
```
