# ODBC_PARAMETER::CopyValue(ulong)

- ea: `0x180001cb0`
- end: `0x180001ce3`
- name: `?CopyValue@ODBC_PARAMETER@@QEAAHK@Z`
- size: `51`
- prototype: `__int64 __fastcall(ODBC_PARAMETER *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001cb0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001ccd`
- `KERNEL32!SetLastError` at `0x180001ccd`

## pseudocode

```c
_BOOL8 __fastcall ODBC_PARAMETER::CopyValue(ODBC_PARAMETER *this, int a2)
{
  if ( *((__int64 *)this + 3) < 4 )
    SetLastError(0x7Au);
  else
    **((_DWORD **)this + 2) = a2;
  return *((_QWORD *)this + 3) >= 4LL;
}

```

## disassembly

```asm
0x180001cb0  push    rbx
0x180001cb2  sub     rsp, 20h
0x180001cb6  cmp     qword ptr [rcx+18h], 4
0x180001cbb  mov     rbx, rcx
0x180001cbe  jl      short loc_180001CC8
0x180001cc0  mov     rax, [rcx+10h]
0x180001cc4  mov     [rax], edx
0x180001cc6  jmp     short loc_180001CD3
0x180001cc8  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180001ccd  call    cs:__imp_SetLastError
0x180001cd3  xor     eax, eax
0x180001cd5  cmp     qword ptr [rbx+18h], 4
0x180001cda  setnl   al
0x180001cdd  add     rsp, 20h
0x180001ce1  pop     rbx
0x180001ce2  retn
```
