# ConvertPathToUNC(ushort const *,ushort *,ulong)

- ea: `0x18001f084`
- end: `0x18001f127`
- name: `?ConvertPathToUNC@@YAJPEBGPEAGK@Z`
- size: `163`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *Destination, rsize_t SizeInWords)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d690`
- `0x18000e824`
- `0x18001f4ec`

## callees

- `0x1800036b2`
- `0x18001f084`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001f0fd`
- `msvcrt!wcscpy_s` at `0x18001f10d`
- `msvcrt!wcscpy_s` at `0x18001f0fd`
- `msvcrt!wcscpy_s` at `0x18001f10d`

## pseudocode

```c
__int64 __fastcall ConvertPathToUNC(wchar_t *Source, wchar_t *Destination, rsize_t SizeInWords)
{
  rsize_t v3; // rbp
  __int64 v5; // r8
  __int64 v7; // rbx
  __int64 result; // rax

  v3 = (unsigned int)SizeInWords;
  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( Source[v7] );
  do
    ++v5;
  while ( Destination[v5] );
  if ( v5 + v7 + 4 > v3 )
    return 2147500037LL;
  if ( Destination[1] != 58 )
    return 2147942487LL;
  Destination[1] = 36;
  memmove_0(&Destination[v7 + 3], Destination, 2 * v5 + 2);
  wcscpy_s(Destination, v3, L"\\\\");
  wcscpy_s(Destination + 2, (unsigned int)(v3 - 2), Source);
  result = 0;
  Destination[v7 + 2] = 92;
  return result;
}

```

## disassembly

```asm
0x18001f084  push    rbx
0x18001f086  push    rbp
0x18001f087  push    rsi
0x18001f088  push    rdi
0x18001f089  push    r14
0x18001f08b  sub     rsp, 20h
0x18001f08f  mov     ebp, r8d
0x18001f092  mov     rdi, rdx
0x18001f095  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f099  mov     r14, rcx
0x18001f09c  mov     rbx, r8
0x18001f09f  inc     rbx
0x18001f0a2  cmp     word ptr [rcx+rbx*2], 0
0x18001f0a7  jnz     short loc_18001F09F
0x18001f0a9  inc     r8
0x18001f0ac  cmp     word ptr [rdx+r8*2], 0
0x18001f0b2  jnz     short loc_18001F0A9
0x18001f0b4  lea     rax, [rbx+4]
0x18001f0b8  add     rax, r8
0x18001f0bb  cmp     rax, rbp
0x18001f0be  jbe     short loc_18001F0C7
0x18001f0c0  mov     eax, 80004005h
0x18001f0c5  jmp     short loc_18001F11C
0x18001f0c7  cmp     word ptr [rdx+2], 3Ah ; ':'
0x18001f0cc  jz      short loc_18001F0D5
0x18001f0ce  mov     eax, 80070057h
0x18001f0d3  jmp     short loc_18001F11C
0x18001f0d5  lea     rcx, [rdx+6]
0x18001f0d9  mov     word ptr [rdx+2], 24h ; '$'
0x18001f0df  lea     rcx, [rcx+rbx*2]; void *
0x18001f0e3  lea     r8, ds:2[r8*2]; Size
0x18001f0eb  call    memmove_0
0x18001f0f0  lea     r8, asc_180029A74; "\\\\"
0x18001f0f7  mov     rdx, rbp; SizeInWords
0x18001f0fa  mov     rcx, rdi; Destination
0x18001f0fd  call    cs:__imp_wcscpy_s
0x18001f103  lea     edx, [rbp-2]; SizeInWords
0x18001f106  mov     r8, r14; Source
0x18001f109  lea     rcx, [rdi+4]; Destination
0x18001f10d  call    cs:__imp_wcscpy_s
0x18001f113  xor     eax, eax
0x18001f115  mov     word ptr [rdi+rbx*2+4], 5Ch ; '\'
0x18001f11c  add     rsp, 20h
0x18001f120  pop     r14
0x18001f122  pop     rdi
0x18001f123  pop     rsi
0x18001f124  pop     rbp
0x18001f125  pop     rbx
0x18001f126  retn
```
