# ATL::CAtlFile::Write(void const *,ulong,ulong *)

- ea: `0x18002eea4`
- end: `0x18002eee3`
- name: `?Write@CAtlFile@ATL@@QEAAJPEBXKPEAK@Z`
- size: `63`
- prototype: `int(ATL::CAtlFile *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001de88`
- `0x18002e538`

## callees

- `0x180019034`
- `0x18002eea4`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002eecb`
- `KERNEL32!WriteFile` at `0x18002eecb`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFile::Write(void **this, const void *a2, DWORD a3, unsigned int *a4)
{
  void *v4; // rcx
  bool v6; // zf
  DWORD *v7; // r9
  int v9; // [rsp+58h] [rbp+20h] BYREF

  v4 = *this;
  v6 = a4 == 0;
  v9 = 0;
  v7 = (DWORD *)&v9;
  if ( !v6 )
    v7 = a4;
  if ( WriteFile(v4, a2, a3, v7, 0) )
    return 0;
  else
    return ATL::AtlHresultFromLastError();
}

```

## disassembly

```asm
0x18002eea4  sub     rsp, 38h
0x18002eea8  mov     rcx, [rcx]; hFile
0x18002eeab  mov     rax, r9
0x18002eeae  test    rax, rax
0x18002eeb1  mov     [rsp+38h+arg_18], 0
0x18002eeb9  lea     r9, [rsp+38h+arg_18]
0x18002eebe  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18002eec7  cmovnz  r9, rax; lpNumberOfBytesWritten
0x18002eecb  call    cs:__imp_WriteFile
0x18002eed1  test    eax, eax
0x18002eed3  jnz     short loc_18002EEDC
0x18002eed5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002eeda  jmp     short loc_18002EEDE
0x18002eedc  xor     eax, eax
0x18002eede  add     rsp, 38h
0x18002eee2  retn
```
