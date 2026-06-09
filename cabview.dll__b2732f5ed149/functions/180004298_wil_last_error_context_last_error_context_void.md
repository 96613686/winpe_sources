# wil::last_error_context::~last_error_context(void)

- ea: `0x180004298`
- end: `0x1800042af`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031ac`
- `0x180003228`
- `0x180005484`
- `0x180007694`
- `0x180009eec`
- `0x180009f94`
- `0x180009fe8`
- `0x18000a03c`

## callees

- `0x180004298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042a4`

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
0x180004298  sub     rsp, 28h
0x18000429c  cmp     byte ptr [rcx], 0
0x18000429f  jnz     short loc_1800042AA
0x1800042a1  mov     ecx, [rcx+4]; dwErrCode
0x1800042a4  call    cs:__imp_SetLastError
0x1800042aa  add     rsp, 28h
0x1800042ae  retn
```
