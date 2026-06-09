# TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *)

- ea: `0x18001d4c0`
- end: `0x18001d4fc`
- name: `?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBG@Z`
- size: `60`
- prototype: `bool(TMetabaseMetaXmlFile::TSizedString *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017e84`
- `0x18001b82c`

## callees

- `0x18001d4c0`
- `0x18002e0a6`

## pseudocode

```c
bool __fastcall TMetabaseMetaXmlFile::TSizedString::IsEqual(const void **this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  bool v3; // zf
  bool result; // al

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  if ( *(_DWORD *)this != (_DWORD)v2 )
    return 0;
  v3 = memcmp_0(a2, this[1], 2LL * *(unsigned int *)this) == 0;
  result = 1;
  if ( !v3 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001d4c0  push    rbx
0x18001d4c2  sub     rsp, 20h
0x18001d4c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d4ca  mov     r9, rdx
0x18001d4cd  xor     ebx, ebx
0x18001d4cf  inc     rax
0x18001d4d2  cmp     [rdx+rax*2], bx
0x18001d4d6  jnz     short loc_18001D4CF
0x18001d4d8  cmp     [rcx], eax
0x18001d4da  jnz     short loc_18001D4F4
0x18001d4dc  mov     r8d, [rcx]
0x18001d4df  mov     rdx, [rcx+8]; Buf2
0x18001d4e3  add     r8, r8; Size
0x18001d4e6  mov     rcx, r9; Buf1
0x18001d4e9  call    memcmp_0
0x18001d4ee  test    eax, eax
0x18001d4f0  mov     al, 1
0x18001d4f2  jz      short loc_18001D4F6
0x18001d4f4  mov     al, bl
0x18001d4f6  add     rsp, 20h
0x18001d4fa  pop     rbx
0x18001d4fb  retn
```
