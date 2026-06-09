# wil::last_error_context::~last_error_context(void)

- ea: `0x1800035bc`
- end: `0x1800035d3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003354`
- `0x1800033fc`
- `0x1800034f4`
- `0x18000378c`
- `0x180006164`
- `0x180009e80`
- `0x180009ed4`

## callees

- `0x1800035bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035c8`

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
0x1800035bc  sub     rsp, 28h
0x1800035c0  cmp     byte ptr [rcx], 0
0x1800035c3  jnz     short loc_1800035CE
0x1800035c5  mov     ecx, [rcx+4]; dwErrCode
0x1800035c8  call    cs:__imp_SetLastError
0x1800035ce  add     rsp, 28h
0x1800035d2  retn
```
