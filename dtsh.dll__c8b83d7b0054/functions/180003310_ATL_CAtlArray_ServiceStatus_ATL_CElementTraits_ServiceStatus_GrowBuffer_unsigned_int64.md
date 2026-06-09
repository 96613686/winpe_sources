# ATL::CAtlArray<_ServiceStatus,ATL::CElementTraits<_ServiceStatus>>::GrowBuffer(unsigned __int64)

- ea: `0x180003310`
- end: `0x18000340a`
- name: `?GrowBuffer@?$CAtlArray@U_ServiceStatus@@V?$CElementTraits@U_ServiceStatus@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003410`

## callees

- `0x1800025a0`
- `0x180003310`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800033a9`
- `msvcrt!memmove_s` at `0x1800033a9`
- `msvcrt!calloc` at `0x18000334b`
- `msvcrt!calloc` at `0x180003386`
- `msvcrt!calloc` at `0x18000334b`
- `msvcrt!calloc` at `0x180003386`
- `msvcrt!free` at `0x1800033ca`
- `msvcrt!free` at `0x1800033ca`

## pseudocode

```c
char __fastcall ATL::CAtlArray<_ServiceStatus,ATL::CElementTraits<_ServiceStatus>>::GrowBuffer(__int64 a1, size_t a2)
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
    v7 = calloc(a2, 0x20u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 32LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 32LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 0x20u);
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
0x180003310  mov     [rsp+arg_0], rbx
0x180003315  mov     [rsp+arg_8], rsi
0x18000331a  push    rdi
0x18000331b  sub     rsp, 20h
0x18000331f  mov     rdi, rdx
0x180003322  mov     rbx, rcx
0x180003325  mov     rdx, [rcx+10h]
0x180003329  cmp     rdi, rdx
0x18000332c  jbe     loc_1800033D7
0x180003332  cmp     qword ptr [rbx], 0
0x180003336  movsxd  rcx, dword ptr [rcx+18h]
0x18000333a  jnz     short loc_18000335B
0x18000333c  cmp     rcx, rdi
0x18000333f  mov     edx, 20h ; ' '; Size
0x180003344  cmova   rdi, rcx
0x180003348  mov     rcx, rdi; Count
0x18000334b  call    cs:__imp_calloc
0x180003351  mov     [rbx], rax
0x180003354  test    rax, rax
0x180003357  jz      short loc_180003394
0x180003359  jmp     short loc_1800033D3
0x18000335b  test    rcx, rcx
0x18000335e  jnz     short loc_180003373
0x180003360  mov     rcx, rdx
0x180003363  mov     rax, rdi
0x180003366  shr     rcx, 1
0x180003369  sub     rax, rdx
0x18000336c  cmp     rax, rcx
0x18000336f  cmova   rcx, rax
0x180003373  lea     rax, [rdx+rcx]
0x180003377  mov     edx, 20h ; ' '; Size
0x18000337c  cmp     rdi, rax
0x18000337f  cmovb   rdi, rax
0x180003383  mov     rcx, rdi; Count
0x180003386  call    cs:__imp_calloc
0x18000338c  mov     rsi, rax
0x18000338f  test    rax, rax
0x180003392  jnz     short loc_180003398
0x180003394  xor     al, al
0x180003396  jmp     short loc_1800033D9
0x180003398  mov     rdx, [rbx+8]
0x18000339c  mov     rcx, rsi; Destination
0x18000339f  mov     r8, [rbx]; Source
0x1800033a2  shl     rdx, 5; DestinationSize
0x1800033a6  mov     r9, rdx; SourceSize
0x1800033a9  call    cs:__imp_memmove_s
0x1800033af  test    eax, eax
0x1800033b1  jz      short loc_1800033C7
0x1800033b3  cmp     eax, 0Ch
0x1800033b6  jz      short loc_1800033FF
0x1800033b8  cmp     eax, 16h
0x1800033bb  jz      short loc_1800033F4
0x1800033bd  cmp     eax, 22h ; '"'
0x1800033c0  jz      short loc_1800033F4
0x1800033c2  cmp     eax, 50h ; 'P'
0x1800033c5  jnz     short loc_1800033E9
0x1800033c7  mov     rcx, [rbx]; Block
0x1800033ca  call    cs:__imp_free
0x1800033d0  mov     [rbx], rsi
0x1800033d3  mov     [rbx+10h], rdi
0x1800033d7  mov     al, 1
0x1800033d9  mov     rbx, [rsp+28h+arg_0]
0x1800033de  mov     rsi, [rsp+28h+arg_8]
0x1800033e3  add     rsp, 20h
0x1800033e7  pop     rdi
0x1800033e8  retn
0x1800033e9  mov     ecx, 80004005h; int
0x1800033ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800033f4  mov     ecx, 80070057h; int
0x1800033f9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800033ff  mov     ecx, 8007000Eh; int
0x180003404  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
