# wil::last_error_context::~last_error_context(void)

- ea: `0x1800032ec`
- end: `0x180003303`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c7c`
- `0x180003098`
- `0x180003140`
- `0x18000321c`
- `0x1800033b0`
- `0x180006854`
- `0x18000a09c`
- `0x18000a0f0`

## callees

- `0x1800032ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032f8`

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
0x1800032ec  sub     rsp, 28h
0x1800032f0  cmp     byte ptr [rcx], 0
0x1800032f3  jnz     short loc_1800032FE
0x1800032f5  mov     ecx, [rcx+4]; dwErrCode
0x1800032f8  call    cs:__imp_SetLastError
0x1800032fe  add     rsp, 28h
0x180003302  retn
```
