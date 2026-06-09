# ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)

- ea: `0x14002bb5c`
- end: `0x14002bc3d`
- name: `?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140032784`

## callees

- `0x14002a6b0`
- `0x14002bb5c`

## import_xrefs

- `msvcrt!calloc` at `0x14002bb97`
- `msvcrt!calloc` at `0x14002bbd8`
- `msvcrt!calloc` at `0x14002bb97`
- `msvcrt!calloc` at `0x14002bbd8`
- `msvcrt!memmove_s` at `0x14002bc01`
- `msvcrt!memmove_s` at `0x14002bc01`
- `msvcrt!free` at `0x14002bc17`
- `msvcrt!free` at `0x14002bc17`

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
0x14002bb5c  mov     [rsp+arg_0], rbx
0x14002bb61  mov     [rsp+arg_8], rsi
0x14002bb66  push    rdi
0x14002bb67  sub     rsp, 20h
0x14002bb6b  mov     rbx, rdx
0x14002bb6e  mov     rdi, rcx
0x14002bb71  mov     rdx, [rcx+10h]
0x14002bb75  cmp     rbx, rdx
0x14002bb78  jbe     loc_14002BC2A
0x14002bb7e  cmp     qword ptr [rdi], 0
0x14002bb82  movsxd  rcx, dword ptr [rcx+18h]
0x14002bb86  jnz     short loc_14002BBAD
0x14002bb88  cmp     rcx, rbx
0x14002bb8b  mov     edx, 8; Size
0x14002bb90  cmova   rbx, rcx
0x14002bb94  mov     rcx, rbx; Count
0x14002bb97  call    cs:__imp_calloc
0x14002bb9e  nop     dword ptr [rax+rax+00h]
0x14002bba3  mov     [rdi], rax
0x14002bba6  test    rax, rax
0x14002bba9  jz      short loc_14002BBEC
0x14002bbab  jmp     short loc_14002BC26
0x14002bbad  test    rcx, rcx
0x14002bbb0  jnz     short loc_14002BBC5
0x14002bbb2  mov     rcx, rdx
0x14002bbb5  mov     rax, rbx
0x14002bbb8  shr     rcx, 1
0x14002bbbb  sub     rax, rdx
0x14002bbbe  cmp     rax, rcx
0x14002bbc1  cmova   rcx, rax
0x14002bbc5  lea     rax, [rdx+rcx]
0x14002bbc9  mov     edx, 8; Size
0x14002bbce  cmp     rbx, rax
0x14002bbd1  cmovb   rbx, rax
0x14002bbd5  mov     rcx, rbx; Count
0x14002bbd8  call    cs:__imp_calloc
0x14002bbdf  nop     dword ptr [rax+rax+00h]
0x14002bbe4  mov     rsi, rax
0x14002bbe7  test    rax, rax
0x14002bbea  jnz     short loc_14002BBF0
0x14002bbec  xor     al, al
0x14002bbee  jmp     short loc_14002BC2C
0x14002bbf0  mov     rdx, [rdi+8]
0x14002bbf4  mov     rcx, rsi; Destination
0x14002bbf7  mov     r8, [rdi]; Source
0x14002bbfa  shl     rdx, 3; DestinationSize
0x14002bbfe  mov     r9, rdx; SourceSize
0x14002bc01  call    cs:__imp_memmove_s
0x14002bc08  nop     dword ptr [rax+rax+00h]
0x14002bc0d  mov     ecx, eax; int
0x14002bc0f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14002bc14  mov     rcx, [rdi]; Block
0x14002bc17  call    cs:__imp_free
0x14002bc1e  nop     dword ptr [rax+rax+00h]
0x14002bc23  mov     [rdi], rsi
0x14002bc26  mov     [rdi+10h], rbx
0x14002bc2a  mov     al, 1
0x14002bc2c  mov     rbx, [rsp+28h+arg_0]
0x14002bc31  mov     rsi, [rsp+28h+arg_8]
0x14002bc36  add     rsp, 20h
0x14002bc3a  pop     rdi
0x14002bc3b  retn
```
