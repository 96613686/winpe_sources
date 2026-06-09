# CACHED_FILE_INFO::~CACHED_FILE_INFO(void)

- ea: `0x180002300`
- end: `0x1800023db`
- name: `??1CACHED_FILE_INFO@@AEAA@XZ`
- size: `219`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002290`

## callees

- `0x180002300`
- `0x1800023f0`
- `0x180004010`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800023c0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800023c0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023d4`

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::~CACHED_FILE_INFO(CACHED_FILE_INFO *this)
{
  bool v1; // zf
  __int64 v3; // rax
  void *v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v1 = *((_BYTE *)this + 320) == 0;
  *(_QWORD *)this = &CACHED_FILE_INFO::`vftable';
  *((_DWORD *)this + 64) = 1818846819;
  if ( !v1 )
  {
    v3 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 3, 1);
  }
  v4 = (void *)*((_QWORD *)this + 45);
  if ( v4 )
  {
    FILE_CACHE::ReleaseFromMemoryCache(this, v4, *((_QWORD *)this + 44));
    *((_QWORD *)this + 45) = 0;
  }
  v5 = *((_QWORD *)this + 41);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    *((_QWORD *)this + 41) = 0;
  }
  v6 = *((_QWORD *)this + 103);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 103) = 0;
  }
  BUFFER::~BUFFER((CACHED_FILE_INFO *)((char *)this + 432));
  STRU::~STRU((CACHED_FILE_INFO *)((char *)this + 16));
}

```

## disassembly

```asm
0x180002300  mov     [rsp+arg_0], rbx
0x180002305  push    rdi
0x180002306  sub     rsp, 20h
0x18000230a  cmp     byte ptr [rcx+140h], 0
0x180002311  lea     rax, ??_7CACHED_FILE_INFO@@6B@; const CACHED_FILE_INFO::`vftable'
0x180002318  mov     [rcx], rax
0x18000231b  mov     rbx, rcx
0x18000231e  mov     dword ptr [rcx+100h], 6C696663h
0x180002328  jz      short loc_18000235A
0x18000232a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002331  mov     rax, [rcx]
0x180002334  mov     rax, [rax+60h]
0x180002338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233d  mov     r9, rax
0x180002340  mov     edx, 3
0x180002345  mov     r8d, 1
0x18000234b  mov     rcx, [rax]
0x18000234e  mov     rax, [rcx+8]
0x180002352  mov     rcx, r9
0x180002355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000235a  mov     rdx, [rbx+168h]; void *
0x180002361  xor     edi, edi
0x180002363  test    rdx, rdx
0x180002366  jz      short loc_18000237B
0x180002368  mov     r8, [rbx+160h]; unsigned __int64
0x18000236f  call    ?ReleaseFromMemoryCache@FILE_CACHE@@QEAAJPEAX_K@Z; FILE_CACHE::ReleaseFromMemoryCache(void *,unsigned __int64)
0x180002374  mov     [rbx+168h], rdi
0x18000237b  mov     rcx, [rbx+148h]
0x180002382  test    rcx, rcx
0x180002385  jz      short loc_18000239A
0x180002387  mov     rax, [rcx]
0x18000238a  mov     rax, [rax+8]
0x18000238e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002393  mov     [rbx+148h], rdi
0x18000239a  mov     rcx, [rbx+338h]
0x1800023a1  test    rcx, rcx
0x1800023a4  jz      short loc_1800023B9
0x1800023a6  mov     rax, [rcx]
0x1800023a9  mov     rax, [rax+10h]
0x1800023ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b2  mov     [rbx+338h], rdi
0x1800023b9  lea     rcx, [rbx+1B0h]
0x1800023c0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800023c6  lea     rcx, [rbx+10h]
0x1800023ca  mov     rbx, [rsp+28h+arg_0]
0x1800023cf  add     rsp, 20h
0x1800023d3  pop     rdi
0x1800023d4  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
