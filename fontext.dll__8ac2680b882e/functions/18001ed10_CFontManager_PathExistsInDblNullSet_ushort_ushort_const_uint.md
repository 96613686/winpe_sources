# CFontManager::_PathExistsInDblNullSet(ushort *,ushort const *,uint)

- ea: `0x18001ed10`
- end: `0x18001eda2`
- name: `?_PathExistsInDblNullSet@CFontManager@@AEAAHPEAGPEBGI@Z`
- size: `146`
- prototype: `int(CFontManager *__hidden this, unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ee80`

## callees

- `0x18001d928`
- `0x18001ed10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ed6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ed6d`

## pseudocode

```c
__int64 __fastcall CFontManager::_PathExistsInDblNullSet(
        CFontManager *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // rsi
  unsigned int v5; // edi
  int v6; // ebp
  unsigned __int64 v10; // [rsp+70h] [rbp+8h] BYREF

  v4 = a4;
  v5 = 0;
  v10 = 0;
  v6 = 0;
  while ( *a3 && v6 >= 0 )
  {
    v6 = StringCchLengthW(a3, v4, &v10);
    if ( v6 >= 0 )
    {
      if ( CompareStringOrdinal(a2, -1, a3, -1, 1) == 2 )
        return 1;
      v4 -= ++v10;
      a3 += v10;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001ed10  mov     [rsp+arg_0], rcx
0x18001ed15  push    rbx
0x18001ed16  push    rbp
0x18001ed17  push    rsi
0x18001ed18  push    rdi
0x18001ed19  push    r14
0x18001ed1b  push    r15
0x18001ed1d  sub     rsp, 38h
0x18001ed21  xor     r15d, r15d
0x18001ed24  mov     esi, r9d
0x18001ed27  mov     edi, r15d
0x18001ed2a  mov     [rsp+68h+arg_0], r15
0x18001ed2f  mov     ebp, r15d
0x18001ed32  mov     rbx, r8
0x18001ed35  mov     r14, rdx
0x18001ed38  cmp     [rbx], r15w
0x18001ed3c  jz      short loc_18001ED93
0x18001ed3e  test    ebp, ebp
0x18001ed40  js      short loc_18001ED93
0x18001ed42  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x18001ed47  mov     rdx, rsi; unsigned __int64
0x18001ed4a  mov     rcx, rbx; unsigned __int16 *
0x18001ed4d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ed52  mov     ebp, eax
0x18001ed54  test    eax, eax
0x18001ed56  js      short loc_18001ED38
0x18001ed58  or      r9d, 0FFFFFFFFh; cchCount2
0x18001ed5c  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18001ed64  or      edx, r9d; cchCount1
0x18001ed67  mov     r8, rbx; lpString2
0x18001ed6a  mov     rcx, r14; lpString1
0x18001ed6d  call    cs:__imp_CompareStringOrdinal
0x18001ed73  cmp     eax, 2
0x18001ed76  jz      short loc_18001ED8E
0x18001ed78  mov     rax, [rsp+68h+arg_0]
0x18001ed7d  inc     rax
0x18001ed80  mov     [rsp+68h+arg_0], rax
0x18001ed85  sub     rsi, rax
0x18001ed88  lea     rbx, [rbx+rax*2]
0x18001ed8c  jmp     short loc_18001ED38
0x18001ed8e  mov     edi, 1
0x18001ed93  mov     eax, edi
0x18001ed95  add     rsp, 38h
0x18001ed99  pop     r15
0x18001ed9b  pop     r14
0x18001ed9d  pop     rdi
0x18001ed9e  pop     rsi
0x18001ed9f  pop     rbp
0x18001eda0  pop     rbx
0x18001eda1  retn
```
