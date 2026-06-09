# InsertItemIntoDataBuffer(void * *,void *,ulong,ulong &)

- ea: `0x1800045b0`
- end: `0x180004680`
- name: `?InsertItemIntoDataBuffer@@YAHPEAPEAXPEAXKAEAK@Z`
- size: `208`
- prototype: `__int64 __fastcall(void **, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015140`

## callees

- `0x1800045b0`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180004648`
- `KERNEL32!SetLastError` at `0x18000465e`
- `KERNEL32!SetLastError` at `0x180004648`
- `KERNEL32!SetLastError` at `0x18000465e`
- `IisRTL!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800045d0`
- `IisRTL!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800045d0`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004605`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004605`

## pseudocode

```c
__int64 __fastcall InsertItemIntoDataBuffer(void **a1, void *a2, int a3, unsigned int *a4)
{
  __int64 v4; // rbp
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  int inserted; // eax
  _QWORD *v11; // rcx
  DWORD v13; // ecx

  v4 = (__int64)*a1;
  v8 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)HASH_BUFFER_ENTRY::sm_pach);
  if ( !v8 )
  {
    SetLastError(0xEu);
    return 0;
  }
  *v8 = &HASH_BUFFER_ENTRY::`vftable';
  v9 = v8 + 3;
  v8[4] = v8 + 3;
  v8[3] = v8 + 3;
  *((_DWORD *)v8 + 4) = a3;
  v8[1] = a2;
  inserted = CLKRHashTable::InsertRecord(v4 + 8, v8, 0);
  if ( inserted == 1 )
  {
    v13 = 13;
LABEL_10:
    SetLastError(v13);
    (*(void (__fastcall **)(_QWORD *, __int64))*v8)(v8, 1);
    return 0;
  }
  if ( inserted )
  {
    v13 = 14;
    goto LABEL_10;
  }
  v11 = *(_QWORD **)(v4 + 88);
  if ( *v11 != v4 + 80 )
    __fastfail(3u);
  ++*a4;
  *v9 = v4 + 80;
  v8[4] = v11;
  *v11 = v9;
  *(_QWORD *)(v4 + 88) = v9;
  return 1;
}

```

## disassembly

```asm
0x1800045b0  push    rbx
0x1800045b2  push    rbp
0x1800045b3  push    rsi
0x1800045b4  push    rdi
0x1800045b5  push    r14
0x1800045b7  push    r15
0x1800045b9  sub     rsp, 28h
0x1800045bd  mov     rbp, [rcx]
0x1800045c0  mov     rsi, r9
0x1800045c3  mov     rcx, cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x1800045ca  mov     r14d, r8d
0x1800045cd  mov     r15, rdx
0x1800045d0  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800045d6  mov     rbx, rax
0x1800045d9  test    rax, rax
0x1800045dc  jz      short loc_180004643
0x1800045de  lea     rax, ??_7HASH_BUFFER_ENTRY@@6B@; const HASH_BUFFER_ENTRY::`vftable'
0x1800045e5  xor     r8d, r8d
0x1800045e8  mov     [rbx], rax
0x1800045eb  lea     rdi, [rbx+18h]
0x1800045ef  mov     [rdi+8], rdi
0x1800045f3  lea     rcx, [rbp+8]
0x1800045f7  mov     [rdi], rdi
0x1800045fa  mov     rdx, rbx
0x1800045fd  mov     [rbx+10h], r14d
0x180004601  mov     [rbx+8], r15
0x180004605  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000460b  cmp     eax, 1
0x18000460e  jz      short loc_180004652
0x180004610  test    eax, eax
0x180004612  jnz     short loc_180004659
0x180004614  mov     rcx, [rbp+58h]
0x180004618  lea     rax, [rbp+50h]
0x18000461c  cmp     [rcx], rax
0x18000461f  jnz     short loc_180004679
0x180004621  inc     dword ptr [rsi]
0x180004623  mov     [rdi], rax
0x180004626  mov     [rdi+8], rcx
0x18000462a  mov     [rcx], rdi
0x18000462d  mov     [rax+8], rdi
0x180004631  mov     eax, 1
0x180004636  add     rsp, 28h
0x18000463a  pop     r15
0x18000463c  pop     r14
0x18000463e  pop     rdi
0x18000463f  pop     rsi
0x180004640  pop     rbp
0x180004641  pop     rbx
0x180004642  retn
0x180004643  mov     ecx, 0Eh; dwErrCode
0x180004648  call    cs:__imp_SetLastError
0x18000464e  xor     eax, eax
0x180004650  jmp     short loc_180004636
0x180004652  mov     ecx, 0Dh
0x180004657  jmp     short loc_18000465E
0x180004659  mov     ecx, 0Eh; dwErrCode
0x18000465e  call    cs:__imp_SetLastError
0x180004664  mov     rax, [rbx]
0x180004667  mov     edx, 1
0x18000466c  mov     rcx, rbx
0x18000466f  mov     rax, [rax]
0x180004672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004677  jmp     short loc_18000464E
0x180004679  mov     ecx, 3
0x18000467e  int     29h; Win8: RtlFailFast(ecx)
```
