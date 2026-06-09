# ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GrowBuffer(unsigned __int64)

- ea: `0x180024410`
- end: `0x1800244d8`
- name: `?GrowBuffer@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800244e0`

## callees

- `0x180004184`
- `0x180024410`

## import_xrefs

- `msvcrt!calloc` at `0x18002444b`
- `msvcrt!calloc` at `0x180024486`
- `msvcrt!calloc` at `0x18002444b`
- `msvcrt!calloc` at `0x180024486`
- `msvcrt!memmove_s` at `0x1800244a9`
- `msvcrt!memmove_s` at `0x1800244a9`
- `msvcrt!free` at `0x1800244b9`
- `msvcrt!free` at `0x1800244b9`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GrowBuffer(
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
    v6 = calloc(a2, 8u);
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
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
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
0x180024410  mov     [rsp+arg_0], rbx
0x180024415  mov     [rsp+arg_8], rsi
0x18002441a  push    rdi
0x18002441b  sub     rsp, 20h
0x18002441f  mov     rbx, rdx
0x180024422  mov     rdi, rcx
0x180024425  mov     rdx, [rcx+10h]
0x180024429  cmp     rbx, rdx
0x18002442c  jbe     loc_1800244C6
0x180024432  cmp     qword ptr [rdi], 0
0x180024436  movsxd  rcx, dword ptr [rcx+18h]
0x18002443a  jnz     short loc_18002445B
0x18002443c  cmp     rcx, rbx
0x18002443f  mov     edx, 8; Size
0x180024444  cmova   rbx, rcx
0x180024448  mov     rcx, rbx; Count
0x18002444b  call    cs:__imp_calloc
0x180024451  mov     [rdi], rax
0x180024454  test    rax, rax
0x180024457  jz      short loc_180024494
0x180024459  jmp     short loc_1800244C2
0x18002445b  test    rcx, rcx
0x18002445e  jnz     short loc_180024473
0x180024460  mov     rcx, rdx
0x180024463  mov     rax, rbx
0x180024466  shr     rcx, 1
0x180024469  sub     rax, rdx
0x18002446c  cmp     rax, rcx
0x18002446f  cmova   rcx, rax
0x180024473  lea     rax, [rdx+rcx]
0x180024477  mov     edx, 8; Size
0x18002447c  cmp     rbx, rax
0x18002447f  cmovb   rbx, rax
0x180024483  mov     rcx, rbx; Count
0x180024486  call    cs:__imp_calloc
0x18002448c  mov     rsi, rax
0x18002448f  test    rax, rax
0x180024492  jnz     short loc_180024498
0x180024494  xor     al, al
0x180024496  jmp     short loc_1800244C8
0x180024498  mov     rdx, [rdi+8]
0x18002449c  mov     rcx, rsi; Destination
0x18002449f  mov     r8, [rdi]; Source
0x1800244a2  shl     rdx, 3; DestinationSize
0x1800244a6  mov     r9, rdx; SourceSize
0x1800244a9  call    cs:__imp_memmove_s
0x1800244af  mov     ecx, eax; int
0x1800244b1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800244b6  mov     rcx, [rdi]; Block
0x1800244b9  call    cs:__imp_free
0x1800244bf  mov     [rdi], rsi
0x1800244c2  mov     [rdi+10h], rbx
0x1800244c6  mov     al, 1
0x1800244c8  mov     rbx, [rsp+28h+arg_0]
0x1800244cd  mov     rsi, [rsp+28h+arg_8]
0x1800244d2  add     rsp, 20h
0x1800244d6  pop     rdi
0x1800244d7  retn
```
