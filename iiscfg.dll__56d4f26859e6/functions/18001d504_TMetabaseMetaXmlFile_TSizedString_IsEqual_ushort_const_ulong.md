# TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)

- ea: `0x18001d504`
- end: `0x18001d531`
- name: `?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z`
- size: `45`
- prototype: `bool(TMetabaseMetaXmlFile::TSizedString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001c240`
- `0x18001c814`

## callees

- `0x18001d504`
- `0x18002e0a6`

## pseudocode

```c
bool __fastcall TMetabaseMetaXmlFile::TSizedString::IsEqual(const void **this, const unsigned __int16 *a2, int a3)
{
  return *(_DWORD *)this == a3 && !memcmp_0(a2, this[1], 2LL * *(unsigned int *)this);
}

```

## disassembly

```asm
0x18001d504  sub     rsp, 28h
0x18001d508  mov     rax, rdx
0x18001d50b  cmp     [rcx], r8d
0x18001d50e  jnz     short loc_18001D52A
0x18001d510  mov     r8d, [rcx]
0x18001d513  mov     rdx, [rcx+8]; Buf2
0x18001d517  add     r8, r8; Size
0x18001d51a  mov     rcx, rax; Buf1
0x18001d51d  call    memcmp_0
0x18001d522  test    eax, eax
0x18001d524  jnz     short loc_18001D52A
0x18001d526  mov     al, 1
0x18001d528  jmp     short loc_18001D52C
0x18001d52a  xor     al, al
0x18001d52c  add     rsp, 28h
0x18001d530  retn
```
