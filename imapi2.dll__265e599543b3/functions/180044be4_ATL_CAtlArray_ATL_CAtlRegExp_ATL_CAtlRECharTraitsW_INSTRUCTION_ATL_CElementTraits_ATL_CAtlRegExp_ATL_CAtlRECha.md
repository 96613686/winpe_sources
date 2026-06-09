# ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(unsigned __int64)

- ea: `0x180044be4`
- end: `0x180044cac`
- name: `?GrowBuffer@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800478e0`

## callees

- `0x180011ac4`
- `0x180044be4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180044c7d`
- `msvcrt!memmove_s` at `0x180044c7d`
- `msvcrt!calloc` at `0x180044c1f`
- `msvcrt!calloc` at `0x180044c5a`
- `msvcrt!calloc` at `0x180044c1f`
- `msvcrt!calloc` at `0x180044c5a`
- `msvcrt!free` at `0x180044c8d`
- `msvcrt!free` at `0x180044c8d`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 0x10u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 0x10u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180044be4  mov     [rsp+arg_0], rbx
0x180044be9  mov     [rsp+arg_8], rsi
0x180044bee  push    rdi
0x180044bef  sub     rsp, 20h
0x180044bf3  mov     rbx, rdx
0x180044bf6  mov     rdi, rcx
0x180044bf9  mov     rdx, [rcx+10h]
0x180044bfd  cmp     rbx, rdx
0x180044c00  jbe     loc_180044C9A
0x180044c06  cmp     qword ptr [rdi], 0
0x180044c0a  movsxd  rcx, dword ptr [rcx+18h]
0x180044c0e  jnz     short loc_180044C2F
0x180044c10  cmp     rcx, rbx
0x180044c13  mov     edx, 10h; Size
0x180044c18  cmova   rbx, rcx
0x180044c1c  mov     rcx, rbx; Count
0x180044c1f  call    cs:__imp_calloc
0x180044c25  mov     [rdi], rax
0x180044c28  test    rax, rax
0x180044c2b  jz      short loc_180044C68
0x180044c2d  jmp     short loc_180044C96
0x180044c2f  test    rcx, rcx
0x180044c32  jnz     short loc_180044C47
0x180044c34  mov     rcx, rdx
0x180044c37  mov     rax, rbx
0x180044c3a  shr     rcx, 1
0x180044c3d  sub     rax, rdx
0x180044c40  cmp     rax, rcx
0x180044c43  cmova   rcx, rax
0x180044c47  lea     rax, [rdx+rcx]
0x180044c4b  mov     edx, 10h; Size
0x180044c50  cmp     rbx, rax
0x180044c53  cmovb   rbx, rax
0x180044c57  mov     rcx, rbx; Count
0x180044c5a  call    cs:__imp_calloc
0x180044c60  mov     rsi, rax
0x180044c63  test    rax, rax
0x180044c66  jnz     short loc_180044C6C
0x180044c68  xor     al, al
0x180044c6a  jmp     short loc_180044C9C
0x180044c6c  mov     rdx, [rdi+8]
0x180044c70  mov     rcx, rsi; Destination
0x180044c73  mov     r8, [rdi]; Source
0x180044c76  shl     rdx, 4; DestinationSize
0x180044c7a  mov     r9, rdx; SourceSize
0x180044c7d  call    cs:__imp_memmove_s
0x180044c83  mov     ecx, eax; int
0x180044c85  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180044c8a  mov     rcx, [rdi]; Block
0x180044c8d  call    cs:__imp_free
0x180044c93  mov     [rdi], rsi
0x180044c96  mov     [rdi+10h], rbx
0x180044c9a  mov     al, 1
0x180044c9c  mov     rbx, [rsp+28h+arg_0]
0x180044ca1  mov     rsi, [rsp+28h+arg_8]
0x180044ca6  add     rsp, 20h
0x180044caa  pop     rdi
0x180044cab  retn
```
