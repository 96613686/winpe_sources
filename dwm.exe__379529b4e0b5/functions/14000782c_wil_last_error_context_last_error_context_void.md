# wil::last_error_context::~last_error_context(void)

- ea: `0x14000782c`
- end: `0x140007843`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140004330`
- `0x140006b6c`
- `0x140006be8`
- `0x140007ff8`
- `0x14000baec`
- `0x14000bb94`
- `0x14000bbe8`
- `0x14000d124`

## callees

- `0x14000782c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007838`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007838`

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
0x14000782c  sub     rsp, 28h
0x140007830  cmp     byte ptr [rcx], 0
0x140007833  jnz     short loc_14000783E
0x140007835  mov     ecx, [rcx+4]; dwErrCode
0x140007838  call    cs:__imp_SetLastError
0x14000783e  add     rsp, 28h
0x140007842  retn
```
