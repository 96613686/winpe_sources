# ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(unsigned __int64)

- ea: `0x14002bc44`
- end: `0x14002bd25`
- name: `?GrowBuffer@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@AEAA_N_K@Z`
- size: `225`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400327f0`

## callees

- `0x14002a6b0`
- `0x14002bc44`

## import_xrefs

- `msvcrt!calloc` at `0x14002bc7f`
- `msvcrt!calloc` at `0x14002bcc0`
- `msvcrt!calloc` at `0x14002bc7f`
- `msvcrt!calloc` at `0x14002bcc0`
- `msvcrt!memmove_s` at `0x14002bce9`
- `msvcrt!memmove_s` at `0x14002bce9`
- `msvcrt!free` at `0x14002bcff`
- `msvcrt!free` at `0x14002bcff`

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
0x14002bc44  mov     [rsp+arg_0], rbx
0x14002bc49  mov     [rsp+arg_8], rsi
0x14002bc4e  push    rdi
0x14002bc4f  sub     rsp, 20h
0x14002bc53  mov     rbx, rdx
0x14002bc56  mov     rdi, rcx
0x14002bc59  mov     rdx, [rcx+10h]
0x14002bc5d  cmp     rbx, rdx
0x14002bc60  jbe     loc_14002BD12
0x14002bc66  cmp     qword ptr [rdi], 0
0x14002bc6a  movsxd  rcx, dword ptr [rcx+18h]
0x14002bc6e  jnz     short loc_14002BC95
0x14002bc70  cmp     rcx, rbx
0x14002bc73  mov     edx, 10h; Size
0x14002bc78  cmova   rbx, rcx
0x14002bc7c  mov     rcx, rbx; Count
0x14002bc7f  call    cs:__imp_calloc
0x14002bc86  nop     dword ptr [rax+rax+00h]
0x14002bc8b  mov     [rdi], rax
0x14002bc8e  test    rax, rax
0x14002bc91  jz      short loc_14002BCD4
0x14002bc93  jmp     short loc_14002BD0E
0x14002bc95  test    rcx, rcx
0x14002bc98  jnz     short loc_14002BCAD
0x14002bc9a  mov     rcx, rdx
0x14002bc9d  mov     rax, rbx
0x14002bca0  shr     rcx, 1
0x14002bca3  sub     rax, rdx
0x14002bca6  cmp     rax, rcx
0x14002bca9  cmova   rcx, rax
0x14002bcad  lea     rax, [rdx+rcx]
0x14002bcb1  mov     edx, 10h; Size
0x14002bcb6  cmp     rbx, rax
0x14002bcb9  cmovb   rbx, rax
0x14002bcbd  mov     rcx, rbx; Count
0x14002bcc0  call    cs:__imp_calloc
0x14002bcc7  nop     dword ptr [rax+rax+00h]
0x14002bccc  mov     rsi, rax
0x14002bccf  test    rax, rax
0x14002bcd2  jnz     short loc_14002BCD8
0x14002bcd4  xor     al, al
0x14002bcd6  jmp     short loc_14002BD14
0x14002bcd8  mov     rdx, [rdi+8]
0x14002bcdc  mov     rcx, rsi; Destination
0x14002bcdf  mov     r8, [rdi]; Source
0x14002bce2  shl     rdx, 4; DestinationSize
0x14002bce6  mov     r9, rdx; SourceSize
0x14002bce9  call    cs:__imp_memmove_s
0x14002bcf0  nop     dword ptr [rax+rax+00h]
0x14002bcf5  mov     ecx, eax; int
0x14002bcf7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14002bcfc  mov     rcx, [rdi]; Block
0x14002bcff  call    cs:__imp_free
0x14002bd06  nop     dword ptr [rax+rax+00h]
0x14002bd0b  mov     [rdi], rsi
0x14002bd0e  mov     [rdi+10h], rbx
0x14002bd12  mov     al, 1
0x14002bd14  mov     rbx, [rsp+28h+arg_0]
0x14002bd19  mov     rsi, [rsp+28h+arg_8]
0x14002bd1e  add     rsp, 20h
0x14002bd22  pop     rdi
0x14002bd23  retn
```
