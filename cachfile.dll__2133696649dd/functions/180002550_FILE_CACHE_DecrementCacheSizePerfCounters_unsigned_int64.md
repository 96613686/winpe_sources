# FILE_CACHE::DecrementCacheSizePerfCounters(unsigned __int64)

- ea: `0x180002550`
- end: `0x1800025c3`
- name: `?DecrementCacheSizePerfCounters@FILE_CACHE@@AEAAX_K@Z`
- size: `115`
- prototype: `void __fastcall(FILE_CACHE *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ab0`

## callees

- `0x180002550`
- `0x180004010`

## pseudocode

```c
void __fastcall FILE_CACHE::DecrementCacheSizePerfCounters(FILE_CACHE *this, unsigned __int64 a2)
{
  __int64 i; // rdi
  void (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // rax

  for ( i = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo); a2; a2 -= v5 )
  {
    v4 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)i + 8LL);
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
0x180002550  mov     [rsp+arg_8], rbx
0x180002555  push    rdi
0x180002556  sub     rsp, 20h
0x18000255a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002561  mov     rbx, rdx
0x180002564  mov     rax, [rcx]
0x180002567  mov     rax, [rax+60h]
0x18000256b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002570  mov     rdi, rax
0x180002573  test    rbx, rbx
0x180002576  jz      short loc_1800025AB
0x180002578  mov     [rsp+28h+arg_0], rsi
0x18000257d  mov     esi, 0FFFFFFFFh
0x180002582  mov     rcx, [rdi]
0x180002585  mov     edx, 19h
0x18000258a  mov     rax, [rcx+8]
0x18000258e  mov     rcx, rdi
0x180002591  cmp     rbx, rsi
0x180002594  ja      short loc_1800025B6
0x180002596  mov     r8d, ebx
0x180002599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259e  mov     rax, rbx
0x1800025a1  sub     rbx, rax
0x1800025a4  jnz     short loc_180002582
0x1800025a6  mov     rsi, [rsp+28h+arg_0]
0x1800025ab  mov     rbx, [rsp+28h+arg_8]
0x1800025b0  add     rsp, 20h
0x1800025b4  pop     rdi
0x1800025b5  retn
0x1800025b6  mov     r8d, esi
0x1800025b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025be  mov     rax, rsi
0x1800025c1  jmp     short loc_1800025A1
```
