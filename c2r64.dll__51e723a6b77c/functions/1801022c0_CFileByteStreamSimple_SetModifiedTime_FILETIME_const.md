# CFileByteStreamSimple::SetModifiedTime(_FILETIME const *)

- ea: `0x1801022c0`
- end: `0x180102305`
- name: `?SetModifiedTime@CFileByteStreamSimple@@UEAAJPEBU_FILETIME@@@Z`
- size: `69`
- prototype: `int(CFileByteStreamSimple *__hidden this, const struct _FILETIME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180052cd0`
- `0x1801022c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801022ea`
- `KERNEL32!GetLastError` at `0x1801022ea`
- `KERNEL32!SetFileTime` at `0x1801022e0`
- `KERNEL32!SetFileTime` at `0x1801022e0`

## pseudocode

```c
int __fastcall CFileByteStreamSimple::SetModifiedTime(HANDLE *this, const struct _FILETIME *a2)
{
  int result; // eax

  if ( !a2 )
    CrashWithRecovery(0x222DC8DCu, 0);
  if ( SetFileTime(this[2], 0, 0, a2) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801022c0  sub     rsp, 28h
0x1801022c4  test    rdx, rdx
0x1801022c7  jnz     short loc_1801022D4
0x1801022c9  mov     ecx, 222DC8DCh; unsigned int
0x1801022ce  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801022d4  mov     r9, rdx; lpLastWriteTime
0x1801022d7  xor     r8d, r8d; lpLastAccessTime
0x1801022da  xor     edx, edx; lpCreationTime
0x1801022dc  mov     rcx, [rcx+10h]; hFile
0x1801022e0  call    cs:__imp_SetFileTime
0x1801022e6  test    eax, eax
0x1801022e8  jnz     short loc_1801022FE
0x1801022ea  call    cs:__imp_GetLastError
0x1801022f0  test    eax, eax
0x1801022f2  jle     short loc_180102300
0x1801022f4  movzx   eax, ax
0x1801022f7  or      eax, 80070000h
0x1801022fc  jmp     short loc_180102300
0x1801022fe  xor     eax, eax
0x180102300  add     rsp, 28h
0x180102304  retn
```
