# ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::RemoveAt(int)

- ea: `0x180016450`
- end: `0x180016538`
- name: `?RemoveAt@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEAAHH@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014190`

## callees

- `0x1800026b0`
- `0x180006b34`
- `0x180016450`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001649a`
- `msvcrt!memmove_s` at `0x1800164c8`
- `msvcrt!memmove_s` at `0x18001649a`
- `msvcrt!memmove_s` at `0x1800164c8`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::RemoveAt(
        __int64 a1,
        int a2)
{
  __int64 v2; // rbp
  _DWORD *v4; // rdi
  int v5; // edx
  errno_t v6; // eax
  errno_t v7; // eax
  _DWORD *v8; // rbx
  void *v9; // rax
  void *v10; // rax

  v2 = a2;
  if ( a2 < 0 )
    return 0;
  v4 = (_DWORD *)(a1 + 16);
  v5 = *(_DWORD *)(a1 + 16);
  if ( (int)v2 >= v5 )
    return 0;
  if ( (_DWORD)v2 == v5 - 1 )
  {
    v8 = (_DWORD *)(a1 + 16);
  }
  else
  {
    v6 = memmove_s(
           (void *const)(*(_QWORD *)a1 + 4 * v2),
           4LL * (v5 - (int)v2),
           (const void *const)(*(_QWORD *)a1 + 4 * v2 + 4),
           4LL * (v5 - (int)v2 - 1));
    ATL::AtlCrtErrorCheck(v6);
    v7 = memmove_s(
           (void *const)(*(_QWORD *)(a1 + 8) + 8 * v2),
           8LL * (*v4 - (int)v2),
           (const void *const)(*(_QWORD *)(a1 + 8) + 8 * v2 + 8),
           8LL * (*v4 - (int)v2 - 1));
    ATL::AtlCrtErrorCheck(v7);
    v8 = (_DWORD *)(a1 + 16);
  }
  v9 = _recalloc(*(void **)a1, *v4 - 1, 4u);
  if ( v9 || *v4 == 1 )
    *(_QWORD *)a1 = v9;
  v10 = _recalloc(*(void **)(a1 + 8), *v4 - 1, 8u);
  if ( v10 || *v8 == 1 )
    *(_QWORD *)(a1 + 8) = v10;
  --*v4;
  return 1;
}

```

## disassembly

```asm
0x180016450  push    rbx
0x180016452  push    rbp
0x180016453  push    rsi
0x180016454  push    rdi
0x180016455  sub     rsp, 28h
0x180016459  movsxd  rbp, edx
0x18001645c  mov     rsi, rcx
0x18001645f  test    edx, edx
0x180016461  js      loc_18001652D
0x180016467  lea     rdi, [rcx+10h]
0x18001646b  mov     edx, [rdi]
0x18001646d  cmp     ebp, edx
0x18001646f  jge     loc_18001652D
0x180016475  lea     eax, [rdx-1]
0x180016478  cmp     ebp, eax
0x18001647a  jz      short loc_1800164DB
0x18001647c  mov     rax, [rcx]
0x18001647f  sub     edx, ebp
0x180016481  lea     rcx, [rax+rbp*4]; Destination
0x180016485  lea     eax, [rdx-1]
0x180016488  movsxd  rdx, edx
0x18001648b  movsxd  r9, eax
0x18001648e  lea     r8, [rcx+4]; Source
0x180016492  shl     r9, 2; SourceSize
0x180016496  shl     rdx, 2; DestinationSize
0x18001649a  call    cs:__imp_memmove_s
0x1800164a0  mov     ecx, eax; int
0x1800164a2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800164a7  mov     edx, [rdi]
0x1800164a9  mov     rax, [rsi+8]
0x1800164ad  sub     edx, ebp
0x1800164af  lea     rcx, [rax+rbp*8]; Destination
0x1800164b3  lea     eax, [rdx-1]
0x1800164b6  movsxd  rdx, edx
0x1800164b9  movsxd  r9, eax
0x1800164bc  lea     r8, [rcx+8]; Source
0x1800164c0  shl     r9, 3; SourceSize
0x1800164c4  shl     rdx, 3; DestinationSize
0x1800164c8  call    cs:__imp_memmove_s
0x1800164ce  mov     ecx, eax; int
0x1800164d0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800164d5  lea     rbx, [rsi+10h]
0x1800164d9  jmp     short loc_1800164DE
0x1800164db  mov     rbx, rdi
0x1800164de  mov     eax, [rdi]
0x1800164e0  mov     ebp, 1
0x1800164e5  mov     rcx, [rsi]; Block
0x1800164e8  sub     eax, ebp
0x1800164ea  movsxd  rdx, eax; Count
0x1800164ed  lea     r8d, [rbp+3]; Size
0x1800164f1  call    cs:__imp__recalloc
0x1800164f7  test    rax, rax
0x1800164fa  jnz     short loc_180016500
0x1800164fc  cmp     [rdi], ebp
0x1800164fe  jnz     short loc_180016503
0x180016500  mov     [rsi], rax
0x180016503  mov     eax, [rdi]
0x180016505  mov     r8d, 8; Size
0x18001650b  mov     rcx, [rsi+8]; Block
0x18001650f  sub     eax, ebp
0x180016511  movsxd  rdx, eax; Count
0x180016514  call    cs:__imp__recalloc
0x18001651a  test    rax, rax
0x18001651d  jnz     short loc_180016523
0x18001651f  cmp     [rbx], ebp
0x180016521  jnz     short loc_180016527
0x180016523  mov     [rsi+8], rax
0x180016527  dec     dword ptr [rdi]
0x180016529  mov     eax, ebp
0x18001652b  jmp     short loc_18001652F
0x18001652d  xor     eax, eax
0x18001652f  add     rsp, 28h
0x180016533  pop     rdi
0x180016534  pop     rsi
0x180016535  pop     rbp
0x180016536  pop     rbx
0x180016537  retn
```
