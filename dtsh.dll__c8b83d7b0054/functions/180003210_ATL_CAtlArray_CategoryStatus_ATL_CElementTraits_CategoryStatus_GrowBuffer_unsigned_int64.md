# ATL::CAtlArray<_CategoryStatus,ATL::CElementTraits<_CategoryStatus>>::GrowBuffer(unsigned __int64)

- ea: `0x180003210`
- end: `0x18000330a`
- name: `?GrowBuffer@?$CAtlArray@U_CategoryStatus@@V?$CElementTraits@U_CategoryStatus@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003410`

## callees

- `0x1800025a0`
- `0x180003210`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800032a9`
- `msvcrt!memmove_s` at `0x1800032a9`
- `msvcrt!calloc` at `0x18000324b`
- `msvcrt!calloc` at `0x180003286`
- `msvcrt!calloc` at `0x18000324b`
- `msvcrt!calloc` at `0x180003286`
- `msvcrt!free` at `0x1800032ca`
- `msvcrt!free` at `0x1800032ca`

## pseudocode

```c
char __fastcall ATL::CAtlArray<_CategoryStatus,ATL::CElementTraits<_CategoryStatus>>::GrowBuffer(__int64 a1, size_t a2)
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
  if ( *(_QWORD *)a1 )
  {
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
    if ( v7 )
    {
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
      if ( v10 )
      {
        if ( v10 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v10 == 22 || v10 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v10 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      goto LABEL_20;
    }
    return 0;
  }
  if ( v5 > a2 )
    a2 = v5;
  v6 = calloc(a2, 8u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_20:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180003210  mov     [rsp+arg_0], rbx
0x180003215  mov     [rsp+arg_8], rsi
0x18000321a  push    rdi
0x18000321b  sub     rsp, 20h
0x18000321f  mov     rdi, rdx
0x180003222  mov     rbx, rcx
0x180003225  mov     rdx, [rcx+10h]
0x180003229  cmp     rdi, rdx
0x18000322c  jbe     loc_1800032D7
0x180003232  cmp     qword ptr [rbx], 0
0x180003236  movsxd  rcx, dword ptr [rcx+18h]
0x18000323a  jnz     short loc_18000325B
0x18000323c  cmp     rcx, rdi
0x18000323f  mov     edx, 8; Size
0x180003244  cmova   rdi, rcx
0x180003248  mov     rcx, rdi; Count
0x18000324b  call    cs:__imp_calloc
0x180003251  mov     [rbx], rax
0x180003254  test    rax, rax
0x180003257  jz      short loc_180003294
0x180003259  jmp     short loc_1800032D3
0x18000325b  test    rcx, rcx
0x18000325e  jnz     short loc_180003273
0x180003260  mov     rcx, rdx
0x180003263  mov     rax, rdi
0x180003266  shr     rcx, 1
0x180003269  sub     rax, rdx
0x18000326c  cmp     rax, rcx
0x18000326f  cmova   rcx, rax
0x180003273  lea     rax, [rdx+rcx]
0x180003277  mov     edx, 8; Size
0x18000327c  cmp     rdi, rax
0x18000327f  cmovb   rdi, rax
0x180003283  mov     rcx, rdi; Count
0x180003286  call    cs:__imp_calloc
0x18000328c  mov     rsi, rax
0x18000328f  test    rax, rax
0x180003292  jnz     short loc_180003298
0x180003294  xor     al, al
0x180003296  jmp     short loc_1800032D9
0x180003298  mov     rdx, [rbx+8]
0x18000329c  mov     rcx, rsi; Destination
0x18000329f  mov     r8, [rbx]; Source
0x1800032a2  shl     rdx, 3; DestinationSize
0x1800032a6  mov     r9, rdx; SourceSize
0x1800032a9  call    cs:__imp_memmove_s
0x1800032af  test    eax, eax
0x1800032b1  jz      short loc_1800032C7
0x1800032b3  cmp     eax, 0Ch
0x1800032b6  jz      short loc_1800032FF
0x1800032b8  cmp     eax, 16h
0x1800032bb  jz      short loc_1800032F4
0x1800032bd  cmp     eax, 22h ; '"'
0x1800032c0  jz      short loc_1800032F4
0x1800032c2  cmp     eax, 50h ; 'P'
0x1800032c5  jnz     short loc_1800032E9
0x1800032c7  mov     rcx, [rbx]; Block
0x1800032ca  call    cs:__imp_free
0x1800032d0  mov     [rbx], rsi
0x1800032d3  mov     [rbx+10h], rdi
0x1800032d7  mov     al, 1
0x1800032d9  mov     rbx, [rsp+28h+arg_0]
0x1800032de  mov     rsi, [rsp+28h+arg_8]
0x1800032e3  add     rsp, 20h
0x1800032e7  pop     rdi
0x1800032e8  retn
0x1800032e9  mov     ecx, 80004005h; int
0x1800032ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800032f4  mov     ecx, 80070057h; int
0x1800032f9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800032ff  mov     ecx, 8007000Eh; int
0x180003304  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
