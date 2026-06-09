# wil::last_error_context::~last_error_context(void)

- ea: `0x180004be4`
- end: `0x180004bfb`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180005248`
- `0x180006bb0`
- `0x18000705c`
- `0x180008d14`
- `0x180008dbc`
- `0x180008e10`
- `0x180008e64`

## callees

- `0x180004be4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004bf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004bf0`

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
0x180004be4  sub     rsp, 28h
0x180004be8  cmp     byte ptr [rcx], 0
0x180004beb  jnz     short loc_180004BF6
0x180004bed  mov     ecx, [rcx+4]; dwErrCode
0x180004bf0  call    cs:__imp_SetLastError
0x180004bf6  add     rsp, 28h
0x180004bfa  retn
```
