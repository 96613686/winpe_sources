# wil::last_error_context::~last_error_context(void)

- ea: `0x180011b84`
- end: `0x180011b9c`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fae4`
- `0x18000fc7c`
- `0x18000fd30`
- `0x1800117f8`
- `0x180011934`
- `0x180011abc`
- `0x180011c0c`
- `0x18001fb50`
- `0x180022f0c`
- `0x180022f60`

## callees

- `0x180011b84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b90`

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
0x180011b84  sub     rsp, 28h
0x180011b88  cmp     byte ptr [rcx], 0
0x180011b8b  jnz     short loc_180011B97
0x180011b8d  mov     ecx, [rcx+4]; dwErrCode
0x180011b90  call    cs:__imp_SetLastError
0x180011b96  nop
0x180011b97  add     rsp, 28h
0x180011b9b  retn
```
