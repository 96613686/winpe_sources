# wil::last_error_context::~last_error_context(void)

- ea: `0x14000418c`
- end: `0x1400041a3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140006694`
- `0x1400066e8`
- `0x14000747c`
- `0x140008584`
- `0x140008670`
- `0x140008b28`
- `0x14000a7cc`
- `0x14000a874`

## callees

- `0x14000418c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004198`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004198`

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
0x14000418c  sub     rsp, 28h
0x140004190  cmp     byte ptr [rcx], 0
0x140004193  jnz     short loc_14000419E
0x140004195  mov     ecx, [rcx+4]; dwErrCode
0x140004198  call    cs:__imp_SetLastError
0x14000419e  add     rsp, 28h
0x1400041a2  retn
```
