# CSafeCacheHandle::Set(ushort const *)

- ea: `0x18000c4a8`
- end: `0x18000c4e9`
- name: `?Set@CSafeCacheHandle@@QEAAJPEBG@Z`
- size: `65`
- prototype: `__int64 __fastcall(CSafeCacheHandle *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c368`

## callees

- `0x18000c4a8`
- `0x18002134c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c4c7`
- `KERNEL32!GetLastError` at `0x18000c4c7`

## pseudocode

```c
__int64 __fastcall CSafeCacheHandle::Set(CSafeCacheHandle *this, unsigned __int16 *a2)
{
  unsigned int v3; // edi
  __int64 Library; // rax
  signed int LastError; // eax

  v3 = 0;
  Library = UtilLoadLibraryExWrapper(a2);
  *(_QWORD *)this = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c4a8  mov     [rsp+arg_0], rbx
0x18000c4ad  push    rdi
0x18000c4ae  sub     rsp, 20h
0x18000c4b2  mov     rbx, rcx
0x18000c4b5  xor     edi, edi
0x18000c4b7  mov     rcx, rdx; unsigned __int16 *
0x18000c4ba  call    UtilLoadLibraryExWrapper
0x18000c4bf  mov     [rbx], rax
0x18000c4c2  test    rax, rax
0x18000c4c5  jnz     short loc_18000C4DC
0x18000c4c7  call    cs:__imp_GetLastError
0x18000c4cd  mov     edi, eax
0x18000c4cf  test    eax, eax
0x18000c4d1  jle     short loc_18000C4DC
0x18000c4d3  movzx   edi, ax
0x18000c4d6  or      edi, 80070000h
0x18000c4dc  mov     rbx, [rsp+28h+arg_0]
0x18000c4e1  mov     eax, edi
0x18000c4e3  add     rsp, 20h
0x18000c4e7  pop     rdi
0x18000c4e8  retn
```
