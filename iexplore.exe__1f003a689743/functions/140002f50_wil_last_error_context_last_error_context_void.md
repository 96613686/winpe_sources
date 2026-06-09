# wil::last_error_context::~last_error_context(void)

- ea: `0x140002f50`
- end: `0x140002f67`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000486c`
- `0x1400053e0`

## callees

- `0x140002f50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140002f5c`
- `KERNEL32!SetLastError` at `0x140002f5c`

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
0x140002f50  sub     rsp, 28h
0x140002f54  cmp     byte ptr [rcx], 0
0x140002f57  jnz     short loc_140002F62
0x140002f59  mov     ecx, [rcx+4]; dwErrCode
0x140002f5c  call    cs:__imp_SetLastError
0x140002f62  add     rsp, 28h
0x140002f66  retn
```
