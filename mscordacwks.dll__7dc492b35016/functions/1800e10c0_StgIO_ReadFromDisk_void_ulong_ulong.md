# StgIO::ReadFromDisk(void *,ulong,ulong *)

- ea: `0x1800e10c0`
- end: `0x1800e112f`
- name: `?ReadFromDisk@StgIO@@AEAAJPEAXKPEAK@Z`
- size: `111`
- prototype: `int(StgIO *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800e06ac`
- `0x1800e0d2c`
- `0x1800e11e0`
- `0x1800e1528`
- `0x1800e1954`
- `0x1800e2050`

## callees

- `0x1800e10c0`
- `0x1800f0490`
- `0x180106100`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800e1103`
- `KERNEL32!ReadFile` at `0x1800e1103`
- `KERNEL32!GetLastError` at `0x1800e1111`
- `KERNEL32!GetLastError` at `0x1800e1111`

## pseudocode

```c
__int64 __fastcall StgIO::ReadFromDisk(StgIO *this, void *a2, __int64 a3, unsigned int *a4)
{
  int v4; // eax
  DWORD *v5; // r10
  signed int LastError; // eax
  __int64 v8; // rcx
  char v9; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 34);
  v5 = (DWORD *)&v9;
  if ( a4 )
    v5 = a4;
  if ( v4 != 1 && v4 != 6 )
    return (*(__int64 (__fastcall **)(_QWORD, void *, __int64, DWORD *))(**((_QWORD **)this + 10) + 24LL))(
             *((_QWORD *)this + 10),
             a2,
             a3,
             v5);
  if ( ReadFile(*((HANDLE *)this + 11), a2, a3, v5, 0) )
    return 0;
  LastError = GetLastError();
  v8 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v8 = (unsigned int)LastError;
  return PostError(v8);
}

```

## disassembly

```asm
0x1800e10c0  sub     rsp, 38h
0x1800e10c4  mov     eax, [rcx+88h]
0x1800e10ca  lea     r10, [rsp+38h+arg_0]
0x1800e10cf  test    r9, r9
0x1800e10d2  cmovnz  r10, r9
0x1800e10d6  cmp     eax, 1
0x1800e10d9  jz      short loc_1800E10F6
0x1800e10db  cmp     eax, 6
0x1800e10de  jz      short loc_1800E10F6
0x1800e10e0  mov     rcx, [rcx+50h]
0x1800e10e4  mov     r9, r10
0x1800e10e7  mov     rax, [rcx]
0x1800e10ea  mov     rax, [rax+18h]
0x1800e10ee  call    cs:__guard_dispatch_icall_fptr
0x1800e10f4  jmp     short loc_1800E112A
0x1800e10f6  mov     rcx, [rcx+58h]; hFile
0x1800e10fa  mov     r9, r10; lpNumberOfBytesRead
0x1800e10fd  and     [rsp+38h+var_18], 0
0x1800e1103  call    cs:__imp_ReadFile
0x1800e1109  test    eax, eax
0x1800e110b  jz      short loc_1800E1111
0x1800e110d  xor     eax, eax
0x1800e110f  jmp     short loc_1800E112A
0x1800e1111  call    cs:__imp_GetLastError
0x1800e1117  movzx   ecx, ax
0x1800e111a  or      ecx, 80070000h
0x1800e1120  test    eax, eax
0x1800e1122  cmovle  ecx, eax
0x1800e1125  call    PostError
0x1800e112a  add     rsp, 38h
0x1800e112e  retn
```
