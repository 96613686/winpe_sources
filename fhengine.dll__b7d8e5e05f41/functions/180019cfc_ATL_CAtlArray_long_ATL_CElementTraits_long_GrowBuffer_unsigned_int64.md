# ATL::CAtlArray<long,ATL::CElementTraits<long>>::GrowBuffer(unsigned __int64)

- ea: `0x180019cfc`
- end: `0x180019dc4`
- name: `?GrowBuffer@?$CAtlArray@JV?$CElementTraits@J@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cb74`

## callees

- `0x180004184`
- `0x180019cfc`

## import_xrefs

- `msvcrt!calloc` at `0x180019d37`
- `msvcrt!calloc` at `0x180019d72`
- `msvcrt!calloc` at `0x180019d37`
- `msvcrt!calloc` at `0x180019d72`
- `msvcrt!memmove_s` at `0x180019d95`
- `msvcrt!memmove_s` at `0x180019d95`
- `msvcrt!free` at `0x180019da5`
- `msvcrt!free` at `0x180019da5`

## pseudocode

```c
char __fastcall ATL::CAtlArray<long,ATL::CElementTraits<long>>::GrowBuffer(__int64 a1, size_t a2)
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
    v6 = calloc(a2, 4u);
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
  v7 = calloc(a2, 4u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 4LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 4LL * *(_QWORD *)(a1 + 8));
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
0x180019cfc  mov     [rsp+arg_0], rbx
0x180019d01  mov     [rsp+arg_8], rsi
0x180019d06  push    rdi
0x180019d07  sub     rsp, 20h
0x180019d0b  mov     rbx, rdx
0x180019d0e  mov     rdi, rcx
0x180019d11  mov     rdx, [rcx+10h]
0x180019d15  cmp     rbx, rdx
0x180019d18  jbe     loc_180019DB2
0x180019d1e  cmp     qword ptr [rdi], 0
0x180019d22  movsxd  rcx, dword ptr [rcx+18h]
0x180019d26  jnz     short loc_180019D47
0x180019d28  cmp     rcx, rbx
0x180019d2b  mov     edx, 4; Size
0x180019d30  cmova   rbx, rcx
0x180019d34  mov     rcx, rbx; Count
0x180019d37  call    cs:__imp_calloc
0x180019d3d  mov     [rdi], rax
0x180019d40  test    rax, rax
0x180019d43  jz      short loc_180019D80
0x180019d45  jmp     short loc_180019DAE
0x180019d47  test    rcx, rcx
0x180019d4a  jnz     short loc_180019D5F
0x180019d4c  mov     rcx, rdx
0x180019d4f  mov     rax, rbx
0x180019d52  shr     rcx, 1
0x180019d55  sub     rax, rdx
0x180019d58  cmp     rax, rcx
0x180019d5b  cmova   rcx, rax
0x180019d5f  lea     rax, [rdx+rcx]
0x180019d63  mov     edx, 4; Size
0x180019d68  cmp     rbx, rax
0x180019d6b  cmovb   rbx, rax
0x180019d6f  mov     rcx, rbx; Count
0x180019d72  call    cs:__imp_calloc
0x180019d78  mov     rsi, rax
0x180019d7b  test    rax, rax
0x180019d7e  jnz     short loc_180019D84
0x180019d80  xor     al, al
0x180019d82  jmp     short loc_180019DB4
0x180019d84  mov     rdx, [rdi+8]
0x180019d88  mov     rcx, rsi; Destination
0x180019d8b  mov     r8, [rdi]; Source
0x180019d8e  shl     rdx, 2; DestinationSize
0x180019d92  mov     r9, rdx; SourceSize
0x180019d95  call    cs:__imp_memmove_s
0x180019d9b  mov     ecx, eax; int
0x180019d9d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019da2  mov     rcx, [rdi]; Block
0x180019da5  call    cs:__imp_free
0x180019dab  mov     [rdi], rsi
0x180019dae  mov     [rdi+10h], rbx
0x180019db2  mov     al, 1
0x180019db4  mov     rbx, [rsp+28h+arg_0]
0x180019db9  mov     rsi, [rsp+28h+arg_8]
0x180019dbe  add     rsp, 20h
0x180019dc2  pop     rdi
0x180019dc3  retn
```
