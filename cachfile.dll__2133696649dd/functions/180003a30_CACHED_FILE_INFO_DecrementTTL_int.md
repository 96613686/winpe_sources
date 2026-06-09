# CACHED_FILE_INFO::DecrementTTL(int *)

- ea: `0x180003a30`
- end: `0x180003a37`
- name: `?DecrementTTL@CACHED_FILE_INFO@@UEAAXPEAH@Z`
- size: `7`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::DecrementTTL(CACHED_FILE_INFO *this, int *a2)
{
  *a2 = 0;
}

```

## disassembly

```asm
0x180003a30  mov     dword ptr [rdx], 0
0x180003a36  retn
```
