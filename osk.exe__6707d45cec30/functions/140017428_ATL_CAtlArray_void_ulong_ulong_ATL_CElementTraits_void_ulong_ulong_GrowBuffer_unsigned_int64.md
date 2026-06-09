# ATL::CAtlArray<void (*)(ulong,ulong),ATL::CElementTraits<void (*)(ulong,ulong)>>::GrowBuffer(unsigned __int64)

- ea: `0x140017428`
- end: `0x1400174f0`
- name: `?GrowBuffer@?$CAtlArray@P6AXKK@ZV?$CElementTraits@P6AXKK@Z@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f54`

## callees

- `0x140005b04`
- `0x140017428`

## import_xrefs

- `msvcrt!free` at `0x1400174d1`
- `msvcrt!free` at `0x1400174d1`
- `msvcrt!calloc` at `0x140017463`
- `msvcrt!calloc` at `0x14001749e`
- `msvcrt!calloc` at `0x140017463`
- `msvcrt!calloc` at `0x14001749e`
- `msvcrt!memmove_s` at `0x1400174c1`
- `msvcrt!memmove_s` at `0x1400174c1`

## pseudocode

```c
char __fastcall ATL::CAtlArray<void (*)(unsigned long,unsigned long),ATL::CElementTraits<void (*)(unsigned long,unsigned long)>>::GrowBuffer(
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
0x140017428  mov     [rsp+arg_0], rbx
0x14001742d  mov     [rsp+arg_8], rsi
0x140017432  push    rdi
0x140017433  sub     rsp, 20h
0x140017437  mov     rbx, rdx
0x14001743a  mov     rdi, rcx
0x14001743d  mov     rdx, [rcx+10h]
0x140017441  cmp     rbx, rdx
0x140017444  jbe     loc_1400174DE
0x14001744a  cmp     qword ptr [rdi], 0
0x14001744e  movsxd  rcx, dword ptr [rcx+18h]
0x140017452  jnz     short loc_140017473
0x140017454  cmp     rcx, rbx
0x140017457  mov     edx, 8; Size
0x14001745c  cmova   rbx, rcx
0x140017460  mov     rcx, rbx; Count
0x140017463  call    cs:__imp_calloc
0x140017469  mov     [rdi], rax
0x14001746c  test    rax, rax
0x14001746f  jz      short loc_1400174AC
0x140017471  jmp     short loc_1400174DA
0x140017473  test    rcx, rcx
0x140017476  jnz     short loc_14001748B
0x140017478  mov     rcx, rdx
0x14001747b  mov     rax, rbx
0x14001747e  shr     rcx, 1
0x140017481  sub     rax, rdx
0x140017484  cmp     rax, rcx
0x140017487  cmova   rcx, rax
0x14001748b  lea     rax, [rdx+rcx]
0x14001748f  mov     edx, 8; Size
0x140017494  cmp     rbx, rax
0x140017497  cmovb   rbx, rax
0x14001749b  mov     rcx, rbx; Count
0x14001749e  call    cs:__imp_calloc
0x1400174a4  mov     rsi, rax
0x1400174a7  test    rax, rax
0x1400174aa  jnz     short loc_1400174B0
0x1400174ac  xor     al, al
0x1400174ae  jmp     short loc_1400174E0
0x1400174b0  mov     rdx, [rdi+8]
0x1400174b4  mov     rcx, rsi; Destination
0x1400174b7  mov     r8, [rdi]; Source
0x1400174ba  shl     rdx, 3; DestinationSize
0x1400174be  mov     r9, rdx; SourceSize
0x1400174c1  call    cs:__imp_memmove_s
0x1400174c7  mov     ecx, eax; int
0x1400174c9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400174ce  mov     rcx, [rdi]; Block
0x1400174d1  call    cs:__imp_free
0x1400174d7  mov     [rdi], rsi
0x1400174da  mov     [rdi+10h], rbx
0x1400174de  mov     al, 1
0x1400174e0  mov     rbx, [rsp+28h+arg_0]
0x1400174e5  mov     rsi, [rsp+28h+arg_8]
0x1400174ea  add     rsp, 20h
0x1400174ee  pop     rdi
0x1400174ef  retn
```
