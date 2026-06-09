# CAggregateeDispMgr::~CAggregateeDispMgr(void)

- ea: `0x1800049a0`
- end: `0x1800049ea`
- name: `??1CAggregateeDispMgr@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CAggregateeDispMgr *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f98`
- `0x180005310`
- `0x1800064a0`
- `0x1800065a0`
- `0x180007020`
- `0x1800072a0`
- `0x180007fd0`
- `0x1800080d0`
- `0x1800085f0`
- `0x180008834`
- `0x180009b20`
- `0x180009c20`
- `0x18000a65c`
- `0x18000a94c`

## callees

- `0x1800049a0`
- `0x180012010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800049d4`
- `KERNEL32!LocalFree` at `0x1800049d4`

## pseudocode

```c
void __fastcall CAggregateeDispMgr::~CAggregateeDispMgr(CAggregateeDispMgr *this)
{
  __int64 v1; // rdi
  void *v2; // rbx

  v1 = *((_QWORD *)this + 2);
  *(_QWORD *)this = &CAggregateeDispMgr::`vftable';
  while ( v1 )
  {
    v2 = (void *)v1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 16LL))(*(_QWORD *)(v1 + 8));
    v1 = *(_QWORD *)(v1 + 24);
    LocalFree(v2);
  }
}

```

## disassembly

```asm
0x1800049a0  mov     [rsp+arg_0], rbx
0x1800049a5  push    rdi
0x1800049a6  sub     rsp, 20h
0x1800049aa  mov     rdi, [rcx+10h]
0x1800049ae  lea     rax, ??_7CAggregateeDispMgr@@6B@; const CAggregateeDispMgr::`vftable'
0x1800049b5  mov     [rcx], rax
0x1800049b8  jmp     short loc_1800049DA
0x1800049ba  mov     rcx, [rdi+8]
0x1800049be  mov     rbx, rdi
0x1800049c1  mov     rax, [rcx]
0x1800049c4  mov     rax, [rax+10h]
0x1800049c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049cd  mov     rdi, [rdi+18h]
0x1800049d1  mov     rcx, rbx; hMem
0x1800049d4  call    cs:__imp_LocalFree
0x1800049da  test    rdi, rdi
0x1800049dd  jnz     short loc_1800049BA
0x1800049df  mov     rbx, [rsp+28h+arg_0]
0x1800049e4  add     rsp, 20h
0x1800049e8  pop     rdi
0x1800049e9  retn
```
