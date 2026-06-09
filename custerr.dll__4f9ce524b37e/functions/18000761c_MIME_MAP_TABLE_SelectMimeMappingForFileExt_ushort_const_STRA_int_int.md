# MIME_MAP_TABLE::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)

- ea: `0x18000761c`
- end: `0x180007708`
- name: `?SelectMimeMappingForFileExt@MIME_MAP_TABLE@@QEAAJPEBGPEAVSTRA@@PEAH2@Z`
- size: `236`
- prototype: `int(MIME_MAP_TABLE *__hidden this, const unsigned __int16 *, struct STRA *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800012c0`

## callees

- `0x180007428`
- `0x18000761c`

## import_xrefs

- `msvcrt!wcschr` at `0x180007680`
- `msvcrt!wcschr` at `0x1800076b7`
- `msvcrt!wcschr` at `0x180007680`
- `msvcrt!wcschr` at `0x1800076b7`
- `msvcrt!wcsrchr` at `0x180007655`
- `msvcrt!wcsrchr` at `0x180007665`
- `msvcrt!wcsrchr` at `0x180007655`
- `msvcrt!wcsrchr` at `0x180007665`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x1800076df`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x1800076df`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800076eb`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800076eb`

## pseudocode

```c
int __fastcall MIME_MAP_TABLE::SelectMimeMappingForFileExt(MIME_MAP_TABLE *this, wchar_t *a2, struct STRA *a3, int *a4)
{
  wchar_t *v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rax
  int v11; // r8d
  const unsigned __int16 *v12; // rbx
  STATIC_WSTRING_HASH *v13; // rcx
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  wchar_t *v15; // rax
  const char *Str; // rax
  int result; // eax

  *a4 = 0;
  if ( !a2 || !*a2 )
    return 0;
  v8 = wcsrchr(a2, 0x2Fu);
  v9 = wcsrchr(a2, 0x5Cu);
  if ( v8 > v9 )
    v9 = v8;
  if ( !v9 )
    v9 = a2;
  v10 = wcschr(v9, 0x2Eu);
  if ( v10 )
    v12 = v10 + 1;
  else
    v12 = &::Str;
  while ( 1 )
  {
    v13 = (MIME_MAP_TABLE *)((char *)this + 8);
    if ( !v12 )
      break;
    Key = STATIC_WSTRING_HASH::FindKey(v13, v12, v11);
    if ( Key )
      goto LABEL_16;
    v15 = wcschr(v12, 0x2Eu);
    v12 = v15 + 1;
    if ( !v15 )
      v12 = 0;
  }
  Key = STATIC_WSTRING_HASH::FindKey(v13, L"*", v11);
  if ( !Key )
    return 0;
LABEL_16:
  Str = STRA::QueryStr((struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 80));
  result = STRA::Copy(a3, Str);
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x18000761c  push    rbx
0x18000761e  push    rbp
0x18000761f  push    rsi
0x180007620  push    rdi
0x180007621  push    r14
0x180007623  push    r15
0x180007625  sub     rsp, 28h
0x180007629  xor     r15d, r15d
0x18000762c  mov     rsi, r9
0x18000762f  mov     [r9], r15d
0x180007632  mov     r14, r8
0x180007635  mov     rdi, rdx
0x180007638  mov     rbp, rcx
0x18000763b  test    rdx, rdx
0x18000763e  jz      loc_1800076F9
0x180007644  cmp     [rdx], r15w
0x180007648  jz      loc_1800076F9
0x18000764e  lea     edx, [r15+2Fh]; Ch
0x180007652  mov     rcx, rdi; Str
0x180007655  call    cs:__imp_wcsrchr
0x18000765b  lea     edx, [r15+5Ch]; Ch
0x18000765f  mov     rcx, rdi; Str
0x180007662  mov     rbx, rax
0x180007665  call    cs:__imp_wcsrchr
0x18000766b  cmp     rbx, rax
0x18000766e  lea     edx, [r15+2Eh]; Ch
0x180007672  cmova   rax, rbx
0x180007676  test    rax, rax
0x180007679  cmovz   rax, rdi
0x18000767d  mov     rcx, rax; Str
0x180007680  call    cs:__imp_wcschr
0x180007686  mov     rbx, rax
0x180007689  test    rax, rax
0x18000768c  jnz     short loc_180007697
0x18000768e  lea     rbx, Str
0x180007695  jmp     short loc_18000769B
0x180007697  add     rbx, 2
0x18000769b  lea     rcx, [rbp+8]; this
0x18000769f  test    rbx, rbx
0x1800076a2  jz      short loc_1800076CA
0x1800076a4  mov     rdx, rbx; unsigned __int16 *
0x1800076a7  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x1800076ac  test    rax, rax
0x1800076af  jnz     short loc_1800076DB
0x1800076b1  lea     edx, [rax+2Eh]; Ch
0x1800076b4  mov     rcx, rbx; Str
0x1800076b7  call    cs:__imp_wcschr
0x1800076bd  test    rax, rax
0x1800076c0  lea     rbx, [rax+2]
0x1800076c4  cmovz   rbx, rax
0x1800076c8  jmp     short loc_18000769B
0x1800076ca  lea     rdx, asc_18000A684; "*"
0x1800076d1  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x1800076d6  test    rax, rax
0x1800076d9  jz      short loc_1800076F9
0x1800076db  lea     rcx, [rax+50h]
0x1800076df  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x1800076e5  mov     rdx, rax
0x1800076e8  mov     rcx, r14
0x1800076eb  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800076f1  mov     dword ptr [rsi], 1
0x1800076f7  jmp     short loc_1800076FB
0x1800076f9  xor     eax, eax
0x1800076fb  add     rsp, 28h
0x1800076ff  pop     r15
0x180007701  pop     r14
0x180007703  pop     rdi
0x180007704  pop     rsi
0x180007705  pop     rbp
0x180007706  pop     rbx
0x180007707  retn
```
