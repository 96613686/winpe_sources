# ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)

- ea: `0x180044b14`
- end: `0x180044bdc`
- name: `?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180047878`

## callees

- `0x180011ac4`
- `0x180044b14`

## import_xrefs

- `msvcrt!memmove_s` at `0x180044bad`
- `msvcrt!memmove_s` at `0x180044bad`
- `msvcrt!calloc` at `0x180044b4f`
- `msvcrt!calloc` at `0x180044b8a`
- `msvcrt!calloc` at `0x180044b4f`
- `msvcrt!calloc` at `0x180044b8a`
- `msvcrt!free` at `0x180044bbd`
- `msvcrt!free` at `0x180044bbd`

## pseudocode

```c
char __fastcall ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(__int64 a1, size_t a2)
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
0x180044b14  mov     [rsp+arg_0], rbx
0x180044b19  mov     [rsp+arg_8], rsi
0x180044b1e  push    rdi
0x180044b1f  sub     rsp, 20h
0x180044b23  mov     rbx, rdx
0x180044b26  mov     rdi, rcx
0x180044b29  mov     rdx, [rcx+10h]
0x180044b2d  cmp     rbx, rdx
0x180044b30  jbe     loc_180044BCA
0x180044b36  cmp     qword ptr [rdi], 0
0x180044b3a  movsxd  rcx, dword ptr [rcx+18h]
0x180044b3e  jnz     short loc_180044B5F
0x180044b40  cmp     rcx, rbx
0x180044b43  mov     edx, 8; Size
0x180044b48  cmova   rbx, rcx
0x180044b4c  mov     rcx, rbx; Count
0x180044b4f  call    cs:__imp_calloc
0x180044b55  mov     [rdi], rax
0x180044b58  test    rax, rax
0x180044b5b  jz      short loc_180044B98
0x180044b5d  jmp     short loc_180044BC6
0x180044b5f  test    rcx, rcx
0x180044b62  jnz     short loc_180044B77
0x180044b64  mov     rcx, rdx
0x180044b67  mov     rax, rbx
0x180044b6a  shr     rcx, 1
0x180044b6d  sub     rax, rdx
0x180044b70  cmp     rax, rcx
0x180044b73  cmova   rcx, rax
0x180044b77  lea     rax, [rdx+rcx]
0x180044b7b  mov     edx, 8; Size
0x180044b80  cmp     rbx, rax
0x180044b83  cmovb   rbx, rax
0x180044b87  mov     rcx, rbx; Count
0x180044b8a  call    cs:__imp_calloc
0x180044b90  mov     rsi, rax
0x180044b93  test    rax, rax
0x180044b96  jnz     short loc_180044B9C
0x180044b98  xor     al, al
0x180044b9a  jmp     short loc_180044BCC
0x180044b9c  mov     rdx, [rdi+8]
0x180044ba0  mov     rcx, rsi; Destination
0x180044ba3  mov     r8, [rdi]; Source
0x180044ba6  shl     rdx, 3; DestinationSize
0x180044baa  mov     r9, rdx; SourceSize
0x180044bad  call    cs:__imp_memmove_s
0x180044bb3  mov     ecx, eax; int
0x180044bb5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180044bba  mov     rcx, [rdi]; Block
0x180044bbd  call    cs:__imp_free
0x180044bc3  mov     [rdi], rsi
0x180044bc6  mov     [rdi+10h], rbx
0x180044bca  mov     al, 1
0x180044bcc  mov     rbx, [rsp+28h+arg_0]
0x180044bd1  mov     rsi, [rsp+28h+arg_8]
0x180044bd6  add     rsp, 20h
0x180044bda  pop     rdi
0x180044bdb  retn
```
