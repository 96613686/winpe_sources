# wil::last_error_context::~last_error_context(void)

- ea: `0x14000e938`
- end: `0x14000e94f`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d6e4`
- `0x14000e504`
- `0x14000e8b0`
- `0x14000ec00`
- `0x14001373c`
- `0x140019b34`

## callees

- `0x14000e938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e944`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e944`

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
0x14000e938  sub     rsp, 28h
0x14000e93c  cmp     byte ptr [rcx], 0
0x14000e93f  jnz     short loc_14000E94A
0x14000e941  mov     ecx, [rcx+4]; dwErrCode
0x14000e944  call    cs:__imp_SetLastError
0x14000e94a  add     rsp, 28h
0x14000e94e  retn
```
