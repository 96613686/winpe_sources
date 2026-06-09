# ODBC_PARAMETER::CopyValue(void *,long)

- ea: `0x180001cf0`
- end: `0x180001d33`
- name: `?CopyValue@ODBC_PARAMETER@@QEAAHPEAXJ@Z`
- size: `67`
- prototype: `__int64 __fastcall(ODBC_PARAMETER *__hidden this, void *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001cf0`
- `0x18000ec56`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001d19`
- `KERNEL32!SetLastError` at `0x180001d19`

## pseudocode

```c
_BOOL8 __fastcall ODBC_PARAMETER::CopyValue(void **this, void *a2, int a3)
{
  __int64 v3; // rdi

  v3 = a3;
  if ( a3 > (__int64)this[3] )
    SetLastError(0x7Au);
  else
    memcpy_0(this[2], a2, a3);
  return v3 <= (__int64)this[3];
}

```

## disassembly

```asm
0x180001cf0  mov     [rsp+arg_0], rbx
0x180001cf5  push    rdi
0x180001cf6  sub     rsp, 20h
0x180001cfa  movsxd  rdi, r8d
0x180001cfd  mov     rbx, rcx
0x180001d00  cmp     rdi, [rcx+18h]
0x180001d04  jg      short loc_180001D14
0x180001d06  mov     rcx, [rcx+10h]; void *
0x180001d0a  mov     r8, rdi; Size
0x180001d0d  call    memcpy_0
0x180001d12  jmp     short loc_180001D1F
0x180001d14  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180001d19  call    cs:__imp_SetLastError
0x180001d1f  xor     eax, eax
0x180001d21  cmp     rdi, [rbx+18h]
0x180001d25  mov     rbx, [rsp+28h+arg_0]
0x180001d2a  setle   al
0x180001d2d  add     rsp, 20h
0x180001d31  pop     rdi
0x180001d32  retn
```
