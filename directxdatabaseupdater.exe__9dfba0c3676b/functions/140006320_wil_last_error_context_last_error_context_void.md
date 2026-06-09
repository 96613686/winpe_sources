# wil::last_error_context::~last_error_context(void)

- ea: `0x140006320`
- end: `0x140006337`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140004094`
- `0x140004110`
- `0x140006d68`
- `0x14000e538`
- `0x14000e638`
- `0x14000e68c`
- `0x14000e6e0`
- `0x140010ce8`
- `0x140014900`

## callees

- `0x140006320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000632c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000632c`

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
0x140006320  sub     rsp, 28h
0x140006324  cmp     byte ptr [rcx], 0
0x140006327  jnz     short loc_140006332
0x140006329  mov     ecx, [rcx+4]; dwErrCode
0x14000632c  call    cs:__imp_SetLastError
0x140006332  add     rsp, 28h
0x140006336  retn
```
