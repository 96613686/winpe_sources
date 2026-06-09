# CACHED_FILE_INFO::GetLastModifiedTime(_FILETIME *)

- ea: `0x180002880`
- end: `0x18000288b`
- name: `?GetLastModifiedTime@CACHED_FILE_INFO@@UEBAXPEAU_FILETIME@@@Z`
- size: `11`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::GetLastModifiedTime(CACHED_FILE_INFO *this, struct _FILETIME *a2)
{
  *a2 = *(struct _FILETIME *)((char *)this + 344);
}

```

## disassembly

```asm
0x180002880  mov     rax, [rcx+158h]
0x180002887  mov     [rdx], rax
0x18000288a  retn
```
