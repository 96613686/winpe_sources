# wil::last_error_context::~last_error_context(void)

- ea: `0x14000afe4`
- end: `0x14000affb`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b318`
- `0x14000cadc`
- `0x14000cb84`

## callees

- `0x14000afe4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000aff0`
- `KERNEL32!SetLastError` at `0x14000aff0`

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
0x14000afe4  sub     rsp, 28h
0x14000afe8  cmp     byte ptr [rcx], 0
0x14000afeb  jnz     short loc_14000AFF6
0x14000afed  mov     ecx, [rcx+4]; dwErrCode
0x14000aff0  call    cs:__imp_SetLastError
0x14000aff6  add     rsp, 28h
0x14000affa  retn
```
