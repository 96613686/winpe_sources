# COMPRESSION_CONTEXT::~COMPRESSION_CONTEXT(void)

- ea: `0x180001f10`
- end: `0x180001f79`
- name: `??1COMPRESSION_CONTEXT@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001f10`
- `0x180009010`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180006a08`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180006a08`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a39`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180006a23`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180006a23`

## pseudocode

```c
void __fastcall COMPRESSION_CONTEXT::~COMPRESSION_CONTEXT(COMPRESSION_CONTEXT *this)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rdx
  void *v4; // rcx
  void *v5; // rcx
  _QWORD *v6; // rax
  ALLOC_CACHE_HANDLER *v7; // rcx

  *(_QWORD *)this = &COMPRESSION_CONTEXT::`vftable';
  v2 = (_QWORD **)((char *)this + 144);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v6 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    v7 = (ALLOC_CACHE_HANDLER *)COMPRESSION_BUFFER::allocHandler;
    *v2 = v6;
    v6[1] = v2;
    ALLOC_CACHE_HANDLER::Free(v7, v3 - 500);
  }
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    VirtualFree(v4, 0, 0x8000u);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 15) = 0;
  }
  if ( *((_QWORD *)this + 4) )
  {
    (*(void (**)(void))(*((_QWORD *)this + 1) + 216LL))();
    *((_QWORD *)this + 4) = 0;
  }
  BUFFER::~BUFFER((COMPRESSION_CONTEXT *)((char *)this + 40));
}

```

## disassembly

```asm
0x180001f10  mov     [rsp+arg_0], rbx
0x180001f15  push    rdi
0x180001f16  sub     rsp, 20h
0x180001f1a  lea     rax, ??_7COMPRESSION_CONTEXT@@6B@; const COMPRESSION_CONTEXT::`vftable'
0x180001f21  mov     rbx, rcx
0x180001f24  mov     [rcx], rax
0x180001f27  lea     rdi, [rcx+90h]
0x180001f2e  mov     rdx, [rdi]
0x180001f31  cmp     rdx, rdi
0x180001f34  jnz     loc_1800069E4
0x180001f3a  mov     rcx, [rbx+80h]; lpAddress
0x180001f41  test    rcx, rcx
0x180001f44  jnz     loc_180006A1B
0x180001f4a  mov     rcx, [rbx+78h]; hObject
0x180001f4e  test    rcx, rcx
0x180001f51  jnz     loc_180006A39
0x180001f57  mov     rcx, [rbx+20h]
0x180001f5b  test    rcx, rcx
0x180001f5e  jnz     loc_180006A4C
0x180001f64  lea     rcx, [rbx+28h]
0x180001f68  mov     rbx, [rsp+28h+arg_0]
0x180001f6d  add     rsp, 20h
0x180001f71  pop     rdi
0x180001f72  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800069e4  cmp     [rdx+8], rdi
0x1800069e8  jnz     short loc_180006A14
0x1800069ea  mov     rax, [rdx]
0x1800069ed  cmp     [rax+8], rdx
0x1800069f1  jnz     short loc_180006A14
0x1800069f3  mov     rcx, cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * COMPRESSION_BUFFER::allocHandler
0x1800069fa  add     rdx, 0FFFFFFFFFFFFF060h
0x180006a01  mov     [rdi], rax
0x180006a04  mov     [rax+8], rdi
0x180006a08  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180006a0e  nop
0x180006a0f  jmp     loc_180001F2E
0x180006a14  mov     ecx, 3
0x180006a19  int     29h; Win8: RtlFailFast(ecx)
0x180006a1b  xor     edx, edx; dwSize
0x180006a1d  mov     r8d, 8000h; dwFreeType
0x180006a23  call    cs:__imp_VirtualFree
0x180006a29  mov     qword ptr [rbx+80h], 0
0x180006a34  jmp     loc_180001F4A
0x180006a39  call    cs:__imp_CloseHandle
0x180006a3f  mov     qword ptr [rbx+78h], 0
0x180006a47  jmp     loc_180001F57
0x180006a4c  mov     rax, [rbx+8]
0x180006a50  mov     rax, [rax+0D8h]
0x180006a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a5c  mov     qword ptr [rbx+20h], 0
0x180006a64  jmp     loc_180001F64
```
