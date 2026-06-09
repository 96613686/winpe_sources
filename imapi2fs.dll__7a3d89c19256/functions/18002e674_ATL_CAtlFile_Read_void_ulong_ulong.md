# ATL::CAtlFile::Read(void *,ulong,ulong &)

- ea: `0x18002e674`
- end: `0x18002e69e`
- name: `?Read@CAtlFile@ATL@@QEAAJPEAXKAEAK@Z`
- size: `42`
- prototype: `__int64 __fastcall(ATL::CAtlFile *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001de88`
- `0x18002e31c`
- `0x18002e820`
- `0x18005ba70`

## callees

- `0x180019034`
- `0x18002e674`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18002e684`
- `KERNEL32!ReadFile` at `0x18002e684`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFile::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  if ( ReadFile(*this, a2, a3, a4, 0) )
    return 0;
  else
    return ATL::AtlHresultFromLastError();
}

```

## disassembly

```asm
0x18002e674  sub     rsp, 38h
0x18002e678  mov     rcx, [rcx]; hFile
0x18002e67b  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18002e684  call    cs:__imp_ReadFile
0x18002e68a  test    eax, eax
0x18002e68c  jnz     short loc_18002E697
0x18002e68e  add     rsp, 38h
0x18002e692  jmp     ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002e697  xor     eax, eax
0x18002e699  add     rsp, 38h
0x18002e69d  retn
```
