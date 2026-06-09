# Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &)

- ea: `0x18002ba5c`
- end: `0x18002bae6`
- name: `?CompareOrdinal@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002be1c`

## callees

- `0x18002ba5c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002badb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002badb`

## pseudocode

```c
int __fastcall Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::CompareOrdinal(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 v4; // rdx
  const WCHAR *v5; // r8
  __int64 v6; // r10
  const WCHAR *v7; // rcx

  v2 = *(_QWORD *)(a2 + 8);
  v4 = -1;
  if ( v2 != -1 )
  {
    v5 = *(const WCHAR **)a2;
    if ( v5 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !*(_QWORD *)a2 )
  {
    LODWORD(v2) = 0;
LABEL_8:
    v5 = &String1;
    goto LABEL_9;
  }
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v2) );
  v5 = *(const WCHAR **)a2;
LABEL_9:
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 != -1 )
  {
    v7 = *(const WCHAR **)a1;
    LODWORD(v4) = v6;
    if ( v7 )
      return CompareStringOrdinal(v7, v4, v5, v2, 0);
LABEL_15:
    v7 = &String1;
    return CompareStringOrdinal(v7, v4, v5, v2, 0);
  }
  if ( !*(_QWORD *)a1 )
  {
    LODWORD(v4) = 0;
    goto LABEL_15;
  }
  do
    ++v4;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v4) );
  v7 = *(const WCHAR **)a1;
  return CompareStringOrdinal(v7, v4, v5, v2, 0);
}

```

## disassembly

```asm
0x18002ba5c  sub     rsp, 38h
0x18002ba60  mov     r9, [rdx+8]; cchCount2
0x18002ba64  mov     r8, rdx
0x18002ba67  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002ba6b  xor     eax, eax
0x18002ba6d  cmp     r9, rdx
0x18002ba70  jnz     short loc_18002BA91
0x18002ba72  mov     r10, [r8]
0x18002ba75  test    r10, r10
0x18002ba78  jz      short loc_18002BA8C
0x18002ba7a  mov     r9, rdx
0x18002ba7d  inc     r9
0x18002ba80  cmp     [r10+r9*2], ax
0x18002ba85  jnz     short loc_18002BA7D
0x18002ba87  mov     r8, r10
0x18002ba8a  jmp     short loc_18002BAA0
0x18002ba8c  mov     r9, rax
0x18002ba8f  jmp     short loc_18002BA99
0x18002ba91  mov     r8, [r8]
0x18002ba94  test    r8, r8
0x18002ba97  jnz     short loc_18002BAA0
0x18002ba99  lea     r8, String1; lpString2
0x18002baa0  mov     r10, [rcx+8]
0x18002baa4  cmp     r10, rdx
0x18002baa7  jnz     short loc_18002BAC5
0x18002baa9  mov     r10, [rcx]
0x18002baac  test    r10, r10
0x18002baaf  jz      short loc_18002BAC0
0x18002bab1  inc     rdx
0x18002bab4  cmp     [r10+rdx*2], ax
0x18002bab9  jnz     short loc_18002BAB1
0x18002babb  mov     rcx, r10
0x18002babe  jmp     short loc_18002BAD7
0x18002bac0  mov     rdx, rax
0x18002bac3  jmp     short loc_18002BAD0
0x18002bac5  mov     rcx, [rcx]
0x18002bac8  mov     rdx, r10; cchCount1
0x18002bacb  test    rcx, rcx
0x18002bace  jnz     short loc_18002BAD7
0x18002bad0  lea     rcx, String1; lpString1
0x18002bad7  mov     [rsp+38h+bIgnoreCase], eax; bIgnoreCase
0x18002badb  call    cs:__imp_CompareStringOrdinal
0x18002bae1  add     rsp, 38h
0x18002bae5  retn
```
