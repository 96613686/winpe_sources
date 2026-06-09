# EngComputeGlyphSet

- ea: `0x180059000`
- end: `0x180059069`
- name: `EngComputeGlyphSet`
- size: `105`
- prototype: `FD_GLYPHSET *__stdcall(INT nCodePage, INT nFirstChar, INT cChars)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180059000`
- `0x180059070`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180059029`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180059029`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005905f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005905f`
- `win32u!NtGdiEngComputeGlyphSet` at `0x180059011`
- `win32u!NtGdiEngComputeGlyphSet` at `0x180059011`

## pseudocode

```c
FD_GLYPHSET *__stdcall EngComputeGlyphSet(INT nCodePage, INT nFirstChar, INT cChars)
{
  FD_GLYPHSET *v3; // rbx
  _DWORD *v4; // rax
  _DWORD *v5; // rsi
  unsigned int v6; // edi
  FD_GLYPHSET *v7; // rax

  v3 = 0;
  v4 = (_DWORD *)NtGdiEngComputeGlyphSet(nCodePage, nFirstChar, cChars);
  v5 = v4;
  if ( v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      v7 = (FD_GLYPHSET *)GlobalAlloc(0, v6);
      v3 = v7;
      if ( v7 )
      {
        if ( !(unsigned int)CopyFD_GLYPHSET(v7, v5, v6) )
        {
          GlobalFree(v3);
          return 0;
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180059000  mov     [rsp+arg_0], rbx
0x180059005  mov     [rsp+arg_8], rsi
0x18005900a  push    rdi
0x18005900b  sub     rsp, 20h
0x18005900f  xor     ebx, ebx
0x180059011  call    cs:__imp_NtGdiEngComputeGlyphSet
0x180059017  mov     rsi, rax
0x18005901a  test    rax, rax
0x18005901d  jz      short loc_180059049
0x18005901f  mov     edi, [rax]
0x180059021  test    edi, edi
0x180059023  jz      short loc_180059049
0x180059025  mov     edx, edi; dwBytes
0x180059027  xor     ecx, ecx; uFlags
0x180059029  call    cs:__imp_GlobalAlloc
0x18005902f  mov     rbx, rax
0x180059032  test    rax, rax
0x180059035  jz      short loc_180059049
0x180059037  mov     r8d, edi
0x18005903a  mov     rdx, rsi
0x18005903d  mov     rcx, rax
0x180059040  call    CopyFD_GLYPHSET
0x180059045  test    eax, eax
0x180059047  jz      short loc_18005905C
0x180059049  mov     rsi, [rsp+28h+arg_8]
0x18005904e  mov     rax, rbx
0x180059051  mov     rbx, [rsp+28h+arg_0]
0x180059056  add     rsp, 20h
0x18005905a  pop     rdi
0x18005905b  retn
0x18005905c  mov     rcx, rbx; hMem
0x18005905f  call    cs:__imp_GlobalFree
0x180059065  xor     ebx, ebx
0x180059067  jmp     short loc_180059049
```
