# FILE_CACHE::IncrementCacheSizePerfCounters(unsigned __int64)

- ea: `0x180001cc0`
- end: `0x180001d32`
- name: `?IncrementCacheSizePerfCounters@FILE_CACHE@@AEAAX_K@Z`
- size: `114`
- prototype: `void __fastcall(FILE_CACHE *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ab0`

## callees

- `0x180001cc0`
- `0x180004010`

## pseudocode

```c
void __fastcall FILE_CACHE::IncrementCacheSizePerfCounters(FILE_CACHE *this, unsigned __int64 a2)
{
  void (__fastcall ***i)(_QWORD, __int64, __int64); // rdi
  void (__fastcall *v4)(_QWORD, __int64, __int64); // rax
  __int64 v5; // rax

  for ( i = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
        a2;
        a2 -= v5 )
  {
    v4 = **i;
    if ( a2 > 0xFFFFFFFF )
    {
      v4(i, 25, 0xFFFFFFFFLL);
      v5 = 0xFFFFFFFFLL;
    }
    else
    {
      v4(i, 25, (unsigned int)a2);
      v5 = a2;
    }
  }
}

```

## disassembly

```asm
0x180001cc0  mov     [rsp+arg_8], rbx
0x180001cc5  push    rdi
0x180001cc6  sub     rsp, 20h
0x180001cca  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001cd1  mov     rbx, rdx
0x180001cd4  mov     rax, [rcx]
0x180001cd7  mov     rax, [rax+60h]
0x180001cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ce0  mov     rdi, rax
0x180001ce3  test    rbx, rbx
0x180001ce6  jz      short loc_180001D1A
0x180001ce8  mov     [rsp+28h+arg_0], rsi
0x180001ced  mov     esi, 0FFFFFFFFh
0x180001cf2  mov     rcx, [rdi]
0x180001cf5  mov     edx, 19h
0x180001cfa  mov     rax, [rcx]
0x180001cfd  mov     rcx, rdi
0x180001d00  cmp     rbx, rsi
0x180001d03  ja      short loc_180001D25
0x180001d05  mov     r8d, ebx
0x180001d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0d  mov     rax, rbx
0x180001d10  sub     rbx, rax
0x180001d13  jnz     short loc_180001CF2
0x180001d15  mov     rsi, [rsp+28h+arg_0]
0x180001d1a  mov     rbx, [rsp+28h+arg_8]
0x180001d1f  add     rsp, 20h
0x180001d23  pop     rdi
0x180001d24  retn
0x180001d25  mov     r8d, esi
0x180001d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d2d  mov     rax, rsi
0x180001d30  jmp     short loc_180001D10
```
