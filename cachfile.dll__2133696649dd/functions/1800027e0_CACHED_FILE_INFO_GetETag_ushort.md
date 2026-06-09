# CACHED_FILE_INFO::GetETag(ushort *)

- ea: `0x1800027e0`
- end: `0x1800027f7`
- name: `?GetETag@CACHED_FILE_INFO@@UEBAPEBDPEAG@Z`
- size: `23`
- prototype: `const char *__fastcall(CACHED_FILE_INFO *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800027e0`

## pseudocode

```c
const char *__fastcall CACHED_FILE_INFO::GetETag(CACHED_FILE_INFO *this, unsigned __int16 *a2)
{
  if ( a2 )
    *a2 = *((_WORD *)this + 184);
  return (char *)this + 370;
}

```

## disassembly

```asm
0x1800027e0  test    rdx, rdx
0x1800027e3  jz      short loc_1800027EF
0x1800027e5  movzx   eax, word ptr [rcx+170h]
0x1800027ec  mov     [rdx], ax
0x1800027ef  lea     rax, [rcx+172h]
0x1800027f6  retn
```
