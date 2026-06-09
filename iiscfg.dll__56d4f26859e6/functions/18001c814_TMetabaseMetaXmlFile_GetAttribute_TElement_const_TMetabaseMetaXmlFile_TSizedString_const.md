# TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)

- ea: `0x18001c814`
- end: `0x18001c863`
- name: `?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z`
- size: `79`
- prototype: `const struct TMetabaseMetaXmlFile::TAttr *(TMetabaseMetaXmlFile *__hidden this, const struct TElement *, const struct TMetabaseMetaXmlFile::TSizedString *)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019554`
- `0x1800199c8`
- `0x18001b354`
- `0x18001b628`
- `0x18001bc88`
- `0x18001c240`
- `0x18001c86c`
- `0x18001d604`

## callees

- `0x18001c814`
- `0x18001d504`

## pseudocode

```c
const struct TMetabaseMetaXmlFile::TAttr *__fastcall TMetabaseMetaXmlFile::GetAttribute(
        TMetabaseMetaXmlFile *this,
        const struct TElement *a2,
        const struct TMetabaseMetaXmlFile::TSizedString *a3)
{
  unsigned int i; // ebx
  char *v6; // rsi

  for ( i = 0; i < *((_DWORD *)a2 + 5); ++i )
  {
    v6 = (char *)a2 + 32 * i;
    if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(a3, *((const unsigned __int16 **)v6 + 5), *((_DWORD *)v6 + 8)) )
      return (const struct TMetabaseMetaXmlFile::TAttr *)(v6 + 32);
  }
  return (const struct TMetabaseMetaXmlFile::TAttr *)qword_180042780;
}

```

## disassembly

```asm
0x18001c814  push    rbx
0x18001c816  push    rbp
0x18001c817  push    rsi
0x18001c818  push    rdi
0x18001c819  sub     rsp, 28h
0x18001c81d  mov     rbp, r8
0x18001c820  mov     rdi, rdx
0x18001c823  xor     ebx, ebx
0x18001c825  cmp     ebx, [rdi+14h]
0x18001c828  jnb     short loc_18001C853
0x18001c82a  mov     edx, ebx
0x18001c82c  mov     rcx, rbp; this
0x18001c82f  shl     rdx, 5
0x18001c833  lea     rsi, [rdx+rdi]
0x18001c837  mov     rdx, [rdx+rdi+28h]; unsigned __int16 *
0x18001c83c  mov     r8d, [rsi+20h]; unsigned int
0x18001c840  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c845  test    al, al
0x18001c847  jnz     short loc_18001C84D
0x18001c849  inc     ebx
0x18001c84b  jmp     short loc_18001C825
0x18001c84d  lea     rax, [rsi+20h]
0x18001c851  jmp     short loc_18001C85A
0x18001c853  lea     rax, qword_180042780
0x18001c85a  add     rsp, 28h
0x18001c85e  pop     rdi
0x18001c85f  pop     rsi
0x18001c860  pop     rbp
0x18001c861  pop     rbx
0x18001c862  retn
```
