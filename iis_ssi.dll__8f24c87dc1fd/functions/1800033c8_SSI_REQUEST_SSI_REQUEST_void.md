# SSI_REQUEST::~SSI_REQUEST(void)

- ea: `0x1800033c8`
- end: `0x18000346b`
- name: `??1SSI_REQUEST@@QEAA@XZ`
- size: `163`
- prototype: `void __fastcall(SSI_REQUEST *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000231c`
- `0x180003480`

## callees

- `0x1800033c8`
- `0x180003b7c`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000344b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000344b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003464`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000343e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000343e`
- `iisutil!??1CHUNK_BUFFER@@QEAA@XZ` at `0x180003431`
- `iisutil!??1CHUNK_BUFFER@@QEAA@XZ` at `0x180003431`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000341b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000341b`

## pseudocode

```c
void __fastcall SSI_REQUEST::~SSI_REQUEST(SSI_REQUEST *this)
{
  SSI_INCLUDE_FILE **v2; // rsi
  SSI_INCLUDE_FILE *v3; // rdi
  SSI_INCLUDE_FILE *v4; // rax

  *(_QWORD *)this = &SSI_REQUEST::`vftable';
  v2 = (SSI_INCLUDE_FILE **)((char *)this + 1104);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (SSI_INCLUDE_FILE *)v2 )
      break;
    if ( *((SSI_INCLUDE_FILE ***)v3 + 1) != v2
      || (v4 = *(SSI_INCLUDE_FILE **)v3, *(SSI_INCLUDE_FILE **)(*(_QWORD *)v3 + 8LL) != v3) )
    {
      __fastfail(3u);
    }
    *v2 = v4;
    *((_QWORD *)v4 + 1) = v2;
    SSI_INCLUDE_FILE::~SSI_INCLUDE_FILE(v3);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles, v3);
  }
  CHUNK_BUFFER::~CHUNK_BUFFER((SSI_REQUEST *)((char *)this + 800));
  STRA::~STRA((SSI_REQUEST *)((char *)this + 656));
  STRU::~STRU((SSI_REQUEST *)((char *)this + 336));
  STRU::~STRU((SSI_REQUEST *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800033c8  mov     [rsp+arg_0], rbx
0x1800033cd  mov     [rsp+arg_8], rsi
0x1800033d2  push    rdi
0x1800033d3  sub     rsp, 20h
0x1800033d7  lea     rax, ??_7SSI_REQUEST@@6B@; const SSI_REQUEST::`vftable'
0x1800033de  mov     rbx, rcx
0x1800033e1  mov     [rcx], rax
0x1800033e4  lea     rsi, [rcx+450h]
0x1800033eb  mov     rdi, [rsi]
0x1800033ee  cmp     rdi, rsi
0x1800033f1  jz      short loc_18000342A
0x1800033f3  cmp     [rdi+8], rsi
0x1800033f7  jnz     short loc_180003423
0x1800033f9  mov     rax, [rdi]
0x1800033fc  cmp     [rax+8], rdi
0x180003400  jnz     short loc_180003423
0x180003402  mov     [rsi], rax
0x180003405  mov     rcx, rdi; this
0x180003408  mov     [rax+8], rsi
0x18000340c  call    ??1SSI_INCLUDE_FILE@@QEAA@XZ; SSI_INCLUDE_FILE::~SSI_INCLUDE_FILE(void)
0x180003411  mov     rcx, cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x180003418  mov     rdx, rdi
0x18000341b  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180003421  jmp     short loc_1800033EB
0x180003423  mov     ecx, 3
0x180003428  int     29h; Win8: RtlFailFast(ecx)
0x18000342a  lea     rcx, [rbx+320h]
0x180003431  call    cs:__imp_??1CHUNK_BUFFER@@QEAA@XZ; CHUNK_BUFFER::~CHUNK_BUFFER(void)
0x180003437  lea     rcx, [rbx+290h]
0x18000343e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003444  lea     rcx, [rbx+150h]
0x18000344b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003451  lea     rcx, [rbx+10h]
0x180003455  mov     rbx, [rsp+28h+arg_0]
0x18000345a  mov     rsi, [rsp+28h+arg_8]
0x18000345f  add     rsp, 20h
0x180003463  pop     rdi
0x180003464  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
