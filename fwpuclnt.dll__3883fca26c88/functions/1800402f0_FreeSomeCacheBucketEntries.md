# FreeSomeCacheBucketEntries

- ea: `0x1800402f0`
- end: `0x180040388`
- name: `FreeSomeCacheBucketEntries`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180040390`

## callees

- `0x180040190`
- `0x1800402f0`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180040349`
- `ntdll!RtlRemoveEntryHashTable` at `0x180040349`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004037c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040309`

## pseudocode

```c
void __fastcall FreeSomeCacheBucketEntries(__int64 a1, _QWORD **a2)
{
  unsigned int v3; // ebp
  _QWORD *v5; // rbx
  _QWORD *v6; // rax

  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 24) + 8LL));
  while ( 1 )
  {
    v5 = *a2;
    if ( *a2 == a2 || v3 >= 0x32 )
      break;
    if ( (_QWORD **)v5[1] != a2 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *a2 = v6;
    v6[1] = a2;
    *(_OWORD *)v5 = 0;
    RtlRemoveEntryHashTable(*(_QWORD *)(a1 + 8), v5 - 4, 0);
    FreeCacheEntry(a1, v5 - 4);
    ++v3;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 24) + 8LL));
}

```

## disassembly

```asm
0x1800402f0  push    rbx
0x1800402f2  push    rbp
0x1800402f3  push    rsi
0x1800402f4  push    rdi
0x1800402f5  sub     rsp, 28h
0x1800402f9  mov     rsi, rcx
0x1800402fc  xor     ebp, ebp
0x1800402fe  mov     rcx, [rcx+18h]
0x180040302  mov     rdi, rdx
0x180040305  add     rcx, 8; lpCriticalSection
0x180040309  call    cs:__imp_EnterCriticalSection
0x180040310  nop     dword ptr [rax+rax+00h]
0x180040315  mov     rbx, [rdi]
0x180040318  cmp     rbx, rdi
0x18004031b  jz      short loc_18004036C
0x18004031d  cmp     ebp, 32h ; '2'
0x180040320  jnb     short loc_18004036C
0x180040322  cmp     [rbx+8], rdi
0x180040326  jnz     short loc_180040365
0x180040328  mov     rax, [rbx]
0x18004032b  cmp     [rax+8], rbx
0x18004032f  jnz     short loc_180040365
0x180040331  mov     [rdi], rax
0x180040334  lea     rdx, [rbx-20h]
0x180040338  mov     [rax+8], rdi
0x18004033c  xorps   xmm0, xmm0
0x18004033f  movups  xmmword ptr [rbx], xmm0
0x180040342  mov     rcx, [rsi+8]
0x180040346  xor     r8d, r8d
0x180040349  call    cs:__imp_RtlRemoveEntryHashTable
0x180040350  nop     dword ptr [rax+rax+00h]
0x180040355  lea     rdx, [rbx-20h]
0x180040359  mov     rcx, rsi
0x18004035c  call    FreeCacheEntry
0x180040361  inc     ebp
0x180040363  jmp     short loc_180040315
0x180040365  mov     ecx, 3
0x18004036a  int     29h; Win8: RtlFailFast(ecx)
0x18004036c  mov     rcx, [rsi+18h]
0x180040370  add     rcx, 8
0x180040374  add     rsp, 28h
0x180040378  pop     rdi
0x180040379  pop     rsi
0x18004037a  pop     rbp
0x18004037b  pop     rbx
0x18004037c  jmp     cs:__imp_LeaveCriticalSection
```
