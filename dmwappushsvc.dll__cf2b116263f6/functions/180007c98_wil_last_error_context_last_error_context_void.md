# wil::last_error_context::~last_error_context(void)

- ea: `0x180007c98`
- end: `0x180007caf`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083e4`
- `0x180009dd8`
- `0x180009ec4`
- `0x18000a504`
- `0x18000caa4`
- `0x18000cb4c`
- `0x18000cba4`
- `0x18000cbf8`
- `0x18000cc4c`
- `0x18000cca0`
- `0x18000eecc`

## callees

- `0x180007c98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ca4`

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
0x180007c98  sub     rsp, 28h
0x180007c9c  cmp     byte ptr [rcx], 0
0x180007c9f  jnz     short loc_180007CAA
0x180007ca1  mov     ecx, [rcx+4]; dwErrCode
0x180007ca4  call    cs:__imp_SetLastError
0x180007caa  add     rsp, 28h
0x180007cae  retn
```
