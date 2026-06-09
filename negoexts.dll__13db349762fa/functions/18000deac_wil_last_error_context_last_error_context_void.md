# wil::last_error_context::~last_error_context(void)

- ea: `0x18000deac`
- end: `0x18000dec3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dc48`
- `0x18000dcf0`
- `0x18000dde4`
- `0x18000e07c`
- `0x180011024`
- `0x180012fe0`
- `0x1800152e0`
- `0x180015334`

## callees

- `0x18000deac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000deb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000deb8`

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
0x18000deac  sub     rsp, 28h
0x18000deb0  cmp     byte ptr [rcx], 0
0x18000deb3  jnz     short loc_18000DEBE
0x18000deb5  mov     ecx, [rcx+4]; dwErrCode
0x18000deb8  call    cs:__imp_SetLastError
0x18000debe  add     rsp, 28h
0x18000dec2  retn
```
