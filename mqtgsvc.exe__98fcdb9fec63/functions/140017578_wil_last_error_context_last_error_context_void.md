# wil::last_error_context::~last_error_context(void)

- ea: `0x140017578`
- end: `0x140017590`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140017bc4`
- `0x140019638`
- `0x140019a0c`
- `0x14001bcc0`
- `0x14001bd6c`
- `0x14001bdc0`
- `0x14001be14`
- `0x14001efc0`

## callees

- `0x140017578`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140017584`
- `KERNEL32!SetLastError` at `0x140017584`

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
0x140017578  sub     rsp, 28h
0x14001757c  cmp     byte ptr [rcx], 0
0x14001757f  jnz     short loc_14001758B
0x140017581  mov     ecx, [rcx+4]; dwErrCode
0x140017584  call    cs:__imp_SetLastError
0x14001758a  nop
0x14001758b  add     rsp, 28h
0x14001758f  retn
```
