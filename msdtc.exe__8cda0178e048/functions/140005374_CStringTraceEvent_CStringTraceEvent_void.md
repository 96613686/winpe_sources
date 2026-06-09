# CStringTraceEvent::~CStringTraceEvent(void)

- ea: `0x140005374`
- end: `0x1400053cc`
- name: `??1CStringTraceEvent@@UEAA@XZ`
- size: `88`
- prototype: `void __fastcall(CStringTraceEvent *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400053f0`
- `0x1400056c0`
- `0x14000713e`

## callees

- `0x140005374`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400053ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400053ae`

## pseudocode

```c
void __fastcall CStringTraceEvent::~CStringTraceEvent(CStringTraceEvent *this)
{
  wchar_t *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CStringTraceEvent::`vftable';
  v2 = (wchar_t *)*((_QWORD *)this + 9);
  if ( v2 != L"[[Unable to format message]]" )
  {
    LocalFree(v2);
    *((_QWORD *)this + 9) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 10) = 0;
  }
  *(_QWORD *)this = &CTraceEvent::`vftable';
}

```

## disassembly

```asm
0x140005374  push    rbx
0x140005376  sub     rsp, 20h
0x14000537a  mov     rbx, rcx
0x14000537d  lea     rax, ??_7CStringTraceEvent@@6B@; const CStringTraceEvent::`vftable'
0x140005384  mov     [rcx], rax
0x140005387  mov     rcx, [rcx+48h]; hMem
0x14000538b  lea     rax, aUnableToFormat; "[[Unable to format message]]"
0x140005392  cmp     rcx, rax
0x140005395  jz      short loc_1400053A5
0x140005397  call    cs:__imp_LocalFree
0x14000539d  mov     qword ptr [rbx+48h], 0
0x1400053a5  mov     rcx, [rbx+50h]; hMem
0x1400053a9  test    rcx, rcx
0x1400053ac  jz      short loc_1400053BC
0x1400053ae  call    cs:__imp_LocalFree
0x1400053b4  mov     qword ptr [rbx+50h], 0
0x1400053bc  lea     rax, ??_7CTraceEvent@@6B@; const CTraceEvent::`vftable'
0x1400053c3  mov     [rbx], rax
0x1400053c6  add     rsp, 20h
0x1400053ca  pop     rbx
0x1400053cb  retn
```
