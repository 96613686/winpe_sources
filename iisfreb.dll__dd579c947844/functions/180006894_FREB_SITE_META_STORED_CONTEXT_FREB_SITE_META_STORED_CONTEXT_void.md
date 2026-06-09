# FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT(void)

- ea: `0x180006894`
- end: `0x180006900`
- name: `??1FREB_SITE_META_STORED_CONTEXT@@AEAA@XZ`
- size: `108`
- prototype: `void __fastcall(FREB_SITE_META_STORED_CONTEXT *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006910`
- `0x180006aec`
- `0x1800087a8`
- `0x180008958`
- `0x180009050`

## callees

- `0x180006894`
- `0x18000b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800068e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800068bc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800068e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800068f9`

## pseudocode

```c
void __fastcall FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT(FREB_SITE_META_STORED_CONTEXT *this)
{
  char *v2; // rsi
  __int64 v3; // rdi

  *(_QWORD *)this = &FREB_SITE_META_STORED_CONTEXT::`vftable';
  v2 = (char *)this + 744;
  v3 = 10;
  do
  {
    v2 -= 56;
    ((void (__fastcall *)(char *))STRU::~STRU)(v2);
    --v3;
  }
  while ( v3 );
  *((_QWORD *)this + 18) = 0;
  STRU::~STRU((FREB_SITE_META_STORED_CONTEXT *)((char *)this + 88));
  STRU::~STRU((FREB_SITE_META_STORED_CONTEXT *)((char *)this + 16));
}

```

## disassembly

```asm
0x180006894  mov     [rsp+arg_0], rbx
0x180006899  mov     [rsp+arg_8], rsi
0x18000689e  push    rdi
0x18000689f  sub     rsp, 20h
0x1800068a3  lea     rax, ??_7FREB_SITE_META_STORED_CONTEXT@@6B@; const FREB_SITE_META_STORED_CONTEXT::`vftable'
0x1800068aa  mov     rbx, rcx
0x1800068ad  mov     [rcx], rax
0x1800068b0  lea     rsi, [rcx+2E8h]
0x1800068b7  mov     edi, 0Ah
0x1800068bc  mov     rax, cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800068c3  sub     rsi, 38h ; '8'
0x1800068c7  mov     rcx, rsi
0x1800068ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068cf  sub     rdi, 1
0x1800068d3  jnz     short loc_1800068BC
0x1800068d5  lea     rcx, [rbx+58h]
0x1800068d9  mov     [rbx+90h], rdi
0x1800068e0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800068e6  lea     rcx, [rbx+10h]
0x1800068ea  mov     rbx, [rsp+28h+arg_0]
0x1800068ef  mov     rsi, [rsp+28h+arg_8]
0x1800068f4  add     rsp, 20h
0x1800068f8  pop     rdi
0x1800068f9  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
