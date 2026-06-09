# OUTPUT_CACHE::CacheFlushByMetadata(OUTPUT_ENTRY *,void *)

- ea: `0x180008310`
- end: `0x180008383`
- name: `?CacheFlushByMetadata@OUTPUT_CACHE@@SA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008310`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000835f`
- `msvcrt!_wcsnicmp` at `0x18000835f`
- `msvcrt!_wcsicmp` at `0x180008338`
- `msvcrt!_wcsicmp` at `0x180008338`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000832c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008350`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000832c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008350`

## pseudocode

```c
__int64 __fastcall OUTPUT_CACHE::CacheFlushByMetadata(__int64 a1, __int64 a2)
{
  const wchar_t *v2; // rbx
  const wchar_t *Str; // rax
  unsigned int v6; // ebx
  const wchar_t *v7; // rdi
  const wchar_t *v8; // rax

  v2 = *(const wchar_t **)a2;
  Str = STRU::QueryStr((STRU *)(a1 + 64));
  if ( _wcsicmp(Str, v2) )
    return 2;
  v6 = *(_DWORD *)(a2 + 16);
  v7 = *(const wchar_t **)(a2 + 8);
  v8 = STRU::QueryStr((STRU *)(a1 + 184));
  return 3 - (unsigned int)(_wcsnicmp(v8, v7, v6) != 0);
}

```

## disassembly

```asm
0x180008310  mov     [rsp+arg_0], rbx
0x180008315  mov     [rsp+arg_8], rsi
0x18000831a  push    rdi
0x18000831b  sub     rsp, 20h
0x18000831f  mov     rbx, [rdx]
0x180008322  mov     rsi, rcx
0x180008325  add     rcx, 40h ; '@'
0x180008329  mov     rdi, rdx
0x18000832c  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180008332  mov     rcx, rax; String1
0x180008335  mov     rdx, rbx; String2
0x180008338  call    cs:__imp__wcsicmp
0x18000833e  test    eax, eax
0x180008340  jnz     short loc_18000836E
0x180008342  mov     ebx, [rdi+10h]
0x180008345  lea     rcx, [rsi+0B8h]
0x18000834c  mov     rdi, [rdi+8]
0x180008350  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180008356  mov     r8d, ebx; MaxCount
0x180008359  mov     rdx, rdi; String2
0x18000835c  mov     rcx, rax; String1
0x18000835f  call    cs:__imp__wcsnicmp
0x180008365  neg     eax
0x180008367  sbb     eax, eax
0x180008369  add     eax, 3
0x18000836c  jmp     short loc_180008373
0x18000836e  mov     eax, 2
0x180008373  mov     rbx, [rsp+28h+arg_0]
0x180008378  mov     rsi, [rsp+28h+arg_8]
0x18000837d  add     rsp, 20h
0x180008381  pop     rdi
0x180008382  retn
```
