# UL_RESPONSE_CACHE::CacheFlushByMetadata(UL_RESPONSE_CACHE_ENTRY *,void *)

- ea: `0x180006430`
- end: `0x1800064a3`
- name: `?CacheFlushByMetadata@UL_RESPONSE_CACHE@@SA?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006430`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000647f`
- `msvcrt!_wcsnicmp` at `0x18000647f`
- `msvcrt!_wcsicmp` at `0x18000645c`
- `msvcrt!_wcsicmp` at `0x18000645c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006450`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006470`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006450`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006470`

## pseudocode

```c
__int64 __fastcall UL_RESPONSE_CACHE::CacheFlushByMetadata(__int64 a1, __int64 a2)
{
  const wchar_t *v2; // rbx
  STRU *v3; // rsi
  const wchar_t *Str; // rax
  unsigned int v6; // ebx
  const wchar_t *v7; // rdi
  const wchar_t *v8; // rax

  v2 = *(const wchar_t **)a2;
  v3 = (STRU *)(a1 + 16);
  Str = STRU::QueryStr((STRU *)(a1 + 200));
  if ( _wcsicmp(Str, v2) )
    return 2;
  v6 = *(_DWORD *)(a2 + 16);
  v7 = *(const wchar_t **)(a2 + 8);
  v8 = STRU::QueryStr(v3);
  return 3 - (unsigned int)(_wcsnicmp(v8, v7, v6) != 0);
}

```

## disassembly

```asm
0x180006430  mov     [rsp+arg_0], rbx
0x180006435  mov     [rsp+arg_8], rsi
0x18000643a  push    rdi
0x18000643b  sub     rsp, 20h
0x18000643f  mov     rbx, [rdx]
0x180006442  lea     rsi, [rcx+10h]
0x180006446  lea     rcx, [rsi+0B8h]
0x18000644d  mov     rdi, rdx
0x180006450  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180006456  mov     rcx, rax; String1
0x180006459  mov     rdx, rbx; String2
0x18000645c  call    cs:__imp__wcsicmp
0x180006462  test    eax, eax
0x180006464  jnz     short loc_18000648E
0x180006466  mov     ebx, [rdi+10h]
0x180006469  mov     rcx, rsi
0x18000646c  mov     rdi, [rdi+8]
0x180006470  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180006476  mov     r8d, ebx; MaxCount
0x180006479  mov     rdx, rdi; String2
0x18000647c  mov     rcx, rax; String1
0x18000647f  call    cs:__imp__wcsnicmp
0x180006485  neg     eax
0x180006487  sbb     eax, eax
0x180006489  add     eax, 3
0x18000648c  jmp     short loc_180006493
0x18000648e  mov     eax, 2
0x180006493  mov     rbx, [rsp+28h+arg_0]
0x180006498  mov     rsi, [rsp+28h+arg_8]
0x18000649d  add     rsp, 20h
0x1800064a1  pop     rdi
0x1800064a2  retn
```
