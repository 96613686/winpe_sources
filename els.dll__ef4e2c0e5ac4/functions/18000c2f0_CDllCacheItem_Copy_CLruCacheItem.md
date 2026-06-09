# CDllCacheItem::Copy(CLruCacheItem *)

- ea: `0x18000c2f0`
- end: `0x18000c35f`
- name: `?Copy@CDllCacheItem@@UEAAJPEAVCLruCacheItem@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(CDllCacheItem *__hidden this, struct CLruCacheItem *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x18000c2f0`
- `0x18002134c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000c337`
- `msvcrt!wcscpy_s` at `0x18000c337`
- `KERNEL32!GetLastError` at `0x18000c33f`
- `KERNEL32!GetLastError` at `0x18000c33f`
- `KERNEL32!FreeLibrary` at `0x18000c31e`
- `KERNEL32!FreeLibrary` at `0x18000c31e`

## pseudocode

```c
__int64 __fastcall CDllCacheItem::Copy(CDllCacheItem *this, struct CLruCacheItem *a2)
{
  const wchar_t *v2; // rsi
  __int64 Library; // rbp
  HMODULE v5; // rcx
  unsigned int v6; // ebx
  signed int LastError; // eax

  v2 = (const wchar_t *)((char *)a2 + 32);
  Library = UtilLoadLibraryExWrapper((unsigned __int16 *)a2 + 16);
  if ( Library )
  {
    v5 = (HMODULE)*((_QWORD *)this + 69);
    v6 = 0;
    if ( v5 )
      FreeLibrary(v5);
    *((_QWORD *)this + 69) = Library;
    wcscpy_s((wchar_t *)this + 16, 0x104u, v2);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c2f0  push    rbx
0x18000c2f2  push    rbp
0x18000c2f3  push    rsi
0x18000c2f4  push    rdi
0x18000c2f5  sub     rsp, 28h
0x18000c2f9  lea     rsi, [rdx+20h]
0x18000c2fd  mov     rdi, rcx
0x18000c300  mov     rcx, rsi; unsigned __int16 *
0x18000c303  call    UtilLoadLibraryExWrapper
0x18000c308  mov     rbp, rax
0x18000c30b  test    rax, rax
0x18000c30e  jz      short loc_18000C33F
0x18000c310  mov     rcx, [rdi+228h]; hLibModule
0x18000c317  xor     ebx, ebx
0x18000c319  test    rcx, rcx
0x18000c31c  jz      short loc_18000C324
0x18000c31e  call    cs:__imp_FreeLibrary
0x18000c324  lea     rcx, [rdi+20h]; Destination
0x18000c328  mov     [rdi+228h], rbp
0x18000c32f  mov     r8, rsi; Source
0x18000c332  mov     edx, 104h; SizeInWords
0x18000c337  call    cs:__imp_wcscpy_s
0x18000c33d  jmp     short loc_18000C354
0x18000c33f  call    cs:__imp_GetLastError
0x18000c345  mov     ebx, eax
0x18000c347  test    eax, eax
0x18000c349  jle     short loc_18000C354
0x18000c34b  movzx   ebx, ax
0x18000c34e  or      ebx, 80070000h
0x18000c354  mov     eax, ebx
0x18000c356  add     rsp, 28h
0x18000c35a  pop     rdi
0x18000c35b  pop     rsi
0x18000c35c  pop     rbp
0x18000c35d  pop     rbx
0x18000c35e  retn
```
