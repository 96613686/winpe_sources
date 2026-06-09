# ATL::CAtlArray<ushort,ATL::CElementTraits<ushort>>::GrowBuffer(unsigned __int64)

- ea: `0x1800558d0`
- end: `0x1800559c9`
- name: `?GrowBuffer@?$CAtlArray@GV?$CElementTraits@G@ATL@@@ATL@@AEAA_N_K@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180055c84`

## callees

- `0x18000ec4c`
- `0x1800558d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180055968`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180055968`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005590b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180055946`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005590b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180055946`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055989`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055989`

## pseudocode

```c
char __fastcall ATL::CAtlArray<unsigned short,ATL::CElementTraits<unsigned short>>::GrowBuffer(__int64 a1, size_t a2)
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
    v7 = calloc(a2, 2u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 2LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 2LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 2u);
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
0x1800558d0  mov     [rsp+arg_0], rbx
0x1800558d5  mov     [rsp+arg_8], rsi
0x1800558da  push    rdi
0x1800558db  sub     rsp, 20h
0x1800558df  mov     rdi, rdx
0x1800558e2  mov     rbx, rcx
0x1800558e5  mov     rdx, [rcx+10h]
0x1800558e9  cmp     rdi, rdx
0x1800558ec  jbe     loc_180055996
0x1800558f2  cmp     qword ptr [rbx], 0
0x1800558f6  movsxd  rcx, dword ptr [rcx+18h]
0x1800558fa  jnz     short loc_18005591B
0x1800558fc  cmp     rcx, rdi
0x1800558ff  mov     edx, 2; Size
0x180055904  cmova   rdi, rcx
0x180055908  mov     rcx, rdi; Count
0x18005590b  call    cs:__imp_calloc
0x180055911  mov     [rbx], rax
0x180055914  test    rax, rax
0x180055917  jz      short loc_180055954
0x180055919  jmp     short loc_180055992
0x18005591b  test    rcx, rcx
0x18005591e  jnz     short loc_180055933
0x180055920  mov     rcx, rdx
0x180055923  mov     rax, rdi
0x180055926  shr     rcx, 1
0x180055929  sub     rax, rdx
0x18005592c  cmp     rax, rcx
0x18005592f  cmova   rcx, rax
0x180055933  lea     rax, [rdx+rcx]
0x180055937  mov     edx, 2; Size
0x18005593c  cmp     rdi, rax
0x18005593f  cmovb   rdi, rax
0x180055943  mov     rcx, rdi; Count
0x180055946  call    cs:__imp_calloc
0x18005594c  mov     rsi, rax
0x18005594f  test    rax, rax
0x180055952  jnz     short loc_180055958
0x180055954  xor     al, al
0x180055956  jmp     short loc_180055998
0x180055958  mov     rdx, [rbx+8]
0x18005595c  mov     rcx, rsi; Destination
0x18005595f  mov     r8, [rbx]; Source
0x180055962  add     rdx, rdx; DestinationSize
0x180055965  mov     r9, rdx; SourceSize
0x180055968  call    cs:__imp_memmove_s
0x18005596e  test    eax, eax
0x180055970  jz      short loc_180055986
0x180055972  cmp     eax, 0Ch
0x180055975  jz      short loc_1800559BE
0x180055977  cmp     eax, 16h
0x18005597a  jz      short loc_1800559B3
0x18005597c  cmp     eax, 22h ; '"'
0x18005597f  jz      short loc_1800559B3
0x180055981  cmp     eax, 50h ; 'P'
0x180055984  jnz     short loc_1800559A8
0x180055986  mov     rcx, [rbx]; Block
0x180055989  call    cs:__imp_free
0x18005598f  mov     [rbx], rsi
0x180055992  mov     [rbx+10h], rdi
0x180055996  mov     al, 1
0x180055998  mov     rbx, [rsp+28h+arg_0]
0x18005599d  mov     rsi, [rsp+28h+arg_8]
0x1800559a2  add     rsp, 20h
0x1800559a6  pop     rdi
0x1800559a7  retn
0x1800559a8  mov     ecx, 80004005h; int
0x1800559ad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800559b3  mov     ecx, 80070057h; int
0x1800559b8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800559be  mov     ecx, 8007000Eh; int
0x1800559c3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
