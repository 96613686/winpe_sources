# _ReleaseInitMutex

- ea: `0x18000740c`
- end: `0x180007450`
- name: `_ReleaseInitMutex`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800031c0`
- `0x180007458`

## callees

- `0x18000740c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180007445`
- `KERNEL32!SetEvent` at `0x180007445`

## pseudocode

```c
int __fastcall ReleaseInitMutex(signed __int64 a1)
{
  signed __int64 v1; // rax
  __int64 v2; // rcx

  v1 = _InterlockedCompareExchange64(&qword_180011768, 0, a1);
  if ( a1 != v1 )
  {
    if ( !*(_QWORD *)(a1 + 16) )
    {
      do
      {
        *(_QWORD *)(*(_QWORD *)(v1 + 8) + 16LL) = v1;
        v1 = *(_QWORD *)(v1 + 8);
      }
      while ( v1 != a1 );
    }
    v2 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(v2 + 8) = 0;
    LODWORD(v1) = SetEvent(*(HANDLE *)v2);
  }
  return v1;
}

```

## disassembly

```asm
0x18000740c  sub     rsp, 28h
0x180007410  mov     r8, rcx
0x180007413  xor     edx, edx
0x180007415  mov     rax, rcx
0x180007418  lock cmpxchg cs:qword_180011768, rdx
0x180007421  jz      short loc_18000744B
0x180007423  cmp     [rcx+10h], rdx
0x180007427  jnz     short loc_18000743A
0x180007429  mov     rcx, [rax+8]
0x18000742d  mov     [rcx+10h], rax
0x180007431  mov     rax, [rax+8]
0x180007435  cmp     rax, r8
0x180007438  jnz     short loc_180007429
0x18000743a  mov     rcx, [r8+10h]
0x18000743e  mov     [rcx+8], rdx
0x180007442  mov     rcx, [rcx]; hEvent
0x180007445  call    cs:__imp_SetEvent
0x18000744b  add     rsp, 28h
0x18000744f  retn
```
