# CMDBaseObject::CopyDataObjectsToBufferByType(ulong,ulong,void * *,ulong &,int,int)

- ea: `0x180001130`
- end: `0x18000132f`
- name: `?CopyDataObjectsToBufferByType@CMDBaseObject@@AEAAXKKPEAPEAXAEAKHH@Z`
- size: `511`
- prototype: `void __fastcall(CMDBaseObject *__hidden this, unsigned int, unsigned int, void **, unsigned int *, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001340`
- `0x180007574`
- `0x180007bd0`

## callees

- `0x180001130`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000128e`
- `KERNEL32!SetLastError` at `0x180001311`
- `KERNEL32!SetLastError` at `0x18000128e`
- `KERNEL32!SetLastError` at `0x180001311`
- `IisRTL!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800011f0`
- `IisRTL!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800011f0`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001229`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001229`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800011c8`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800011c8`

## pseudocode

```c
void __fastcall CMDBaseObject::CopyDataObjectsToBufferByType(
        CMDBaseObject *this,
        int a2,
        int a3,
        void **a4,
        unsigned int *a5,
        int a6,
        int a7)
{
  char *v7; // rsi
  CMDBaseObject *v9; // rbx
  int v10; // edi
  int v11; // eax
  char *v12; // rbx
  int v13; // r12d
  int v14; // r13d
  __int64 v15; // rdx
  char *v16; // rcx
  int v17; // r14d
  char *v18; // rbp
  _QWORD *v19; // rdi
  char *v20; // rsi
  int inserted; // eax
  char **v22; // rcx
  char *v23; // rbx
  bool v24; // zf
  DWORD v25; // ecx
  char *v26; // [rsp+20h] [rbp-48h]
  __int64 v27; // [rsp+70h] [rbp+8h] BYREF
  int v28; // [rsp+78h] [rbp+10h]
  int v29; // [rsp+80h] [rbp+18h]

  v29 = a3;
  v28 = a2;
  v7 = (char *)this + 264;
  v9 = (CMDBaseObject *)*((_QWORD *)this + 33);
  v10 = a3;
  v26 = (char *)this + 264;
  v11 = a2;
  if ( (CMDBaseObject *)((char *)this + 264) == v9 )
    v12 = 0;
  else
    v12 = (char *)v9 - 40;
  v13 = a7;
  v14 = a6;
  while ( v12 )
  {
    if ( !v11 || v11 == *((_DWORD *)v12 + 7) )
    {
      if ( !v10 || (v24 = v10 == (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12), v11 = v28, v24) )
      {
        if ( !v14 || (v12[24] & 1) != 0 )
        {
          if ( !v13 || (*((_DWORD *)v12 + 6) & 4) == 0 )
          {
            v15 = *((unsigned int *)v12 + 2);
            v16 = (char *)*a4 + 8;
            v27 = 0;
            if ( (unsigned int)CLKRHashTable::FindKey(v16, v15, &v27) || !*(_QWORD *)(v27 + 8) )
            {
              v17 = *((_DWORD *)v12 + 2);
              v18 = (char *)*a4;
              v19 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)HASH_BUFFER_ENTRY::sm_pach);
              if ( !v19 )
              {
                SetLastError(0xEu);
                return;
              }
              *v19 = &HASH_BUFFER_ENTRY::`vftable';
              v20 = (char *)(v19 + 3);
              v19[4] = v19 + 3;
              v19[3] = v19 + 3;
              *((_DWORD *)v19 + 4) = v17;
              v19[1] = v12;
              inserted = CLKRHashTable::InsertRecord(v18 + 8, v19, 0);
              if ( inserted == 1 )
              {
                v25 = 13;
                goto LABEL_34;
              }
              if ( inserted )
              {
                v25 = 14;
LABEL_34:
                SetLastError(v25);
                (*(void (__fastcall **)(_QWORD *, __int64))*v19)(v19, 1);
                return;
              }
              v22 = (char **)*((_QWORD *)v18 + 11);
              if ( *v22 != v18 + 80 )
                __fastfail(3u);
              v10 = v29;
              *(_QWORD *)v20 = v18 + 80;
              *((_QWORD *)v20 + 1) = v22;
              *v22 = v20;
              *((_QWORD *)v18 + 11) = v20;
              v7 = v26;
              ++*a5;
            }
          }
          v11 = v28;
        }
      }
    }
    v23 = (char *)*((_QWORD *)v12 + 5);
    if ( v7 == v23 )
      v12 = 0;
    else
      v12 = v23 - 40;
  }
}

```

## disassembly

```asm
0x180001130  mov     [rsp+arg_10], r8d
0x180001135  mov     [rsp+arg_8], edx
0x180001139  push    rbx
0x18000113a  push    rsi
0x18000113b  push    rdi
0x18000113c  push    r12
0x18000113e  push    r13
0x180001140  push    r15
0x180001142  sub     rsp, 38h
0x180001146  lea     rsi, [rcx+108h]
0x18000114d  mov     r15, r9
0x180001150  mov     rbx, [rsi]
0x180001153  mov     edi, r8d
0x180001156  mov     [rsp+68h+var_48], rsi
0x18000115b  mov     eax, edx
0x18000115d  cmp     rsi, rbx
0x180001160  jnz     loc_1800012AF
0x180001166  xor     ebx, ebx
0x180001168  mov     r12d, [rsp+68h+arg_30]
0x180001170  mov     r13d, [rsp+68h+arg_28]
0x180001178  mov     [rsp+68h+arg_18], rbp
0x180001180  mov     [rsp+68h+var_38], r14
0x180001185  test    rbx, rbx
0x180001188  jz      loc_180001294
0x18000118e  test    eax, eax
0x180001190  jnz     loc_1800012B8
0x180001196  test    edi, edi
0x180001198  jnz     loc_1800012C2
0x18000119e  test    r13d, r13d
0x1800011a1  jnz     loc_1800012DE
0x1800011a7  test    r12d, r12d
0x1800011aa  jnz     loc_1800012E9
0x1800011b0  mov     rcx, [r15]
0x1800011b3  lea     r8, [rsp+68h+arg_0]
0x1800011b8  mov     edx, [rbx+8]
0x1800011bb  add     rcx, 8
0x1800011bf  mov     [rsp+68h+arg_0], 0
0x1800011c8  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800011ce  test    eax, eax
0x1800011d0  jnz     short loc_1800011E2
0x1800011d2  mov     rax, [rsp+68h+arg_0]
0x1800011d7  cmp     qword ptr [rax+8], 0
0x1800011dc  jnz     loc_180001275
0x1800011e2  mov     rcx, cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x1800011e9  mov     r14d, [rbx+8]
0x1800011ed  mov     rbp, [r15]
0x1800011f0  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800011f6  mov     rdi, rax
0x1800011f9  test    rax, rax
0x1800011fc  jz      loc_180001289
0x180001202  lea     rax, ??_7HASH_BUFFER_ENTRY@@6B@; const HASH_BUFFER_ENTRY::`vftable'
0x180001209  xor     r8d, r8d
0x18000120c  mov     [rdi], rax
0x18000120f  lea     rsi, [rdi+18h]
0x180001213  mov     [rdi+20h], rsi
0x180001217  lea     rcx, [rbp+8]
0x18000121b  mov     [rsi], rsi
0x18000121e  mov     rdx, rdi
0x180001221  mov     [rdi+10h], r14d
0x180001225  mov     [rdi+8], rbx
0x180001229  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000122f  cmp     eax, 1
0x180001232  jz      loc_18000130C
0x180001238  test    eax, eax
0x18000123a  jnz     loc_180001305
0x180001240  mov     rcx, [rbp+58h]
0x180001244  lea     rax, [rbp+50h]
0x180001248  cmp     [rcx], rax
0x18000124b  jnz     loc_1800012FE
0x180001251  mov     edi, [rsp+68h+arg_10]
0x180001258  mov     [rsi], rax
0x18000125b  mov     [rsi+8], rcx
0x18000125f  mov     [rcx], rsi
0x180001262  mov     [rax+8], rsi
0x180001266  mov     rax, [rsp+68h+arg_20]
0x18000126e  mov     rsi, [rsp+68h+var_48]
0x180001273  inc     dword ptr [rax]
0x180001275  mov     eax, [rsp+68h+arg_8]
0x180001279  mov     rbx, [rbx+28h]
0x18000127d  cmp     rsi, rbx
0x180001280  jnz     short loc_1800012F5
0x180001282  xor     ebx, ebx
0x180001284  jmp     loc_180001185
0x180001289  mov     ecx, 0Eh; dwErrCode
0x18000128e  call    cs:__imp_SetLastError
0x180001294  mov     r14, [rsp+68h+var_38]
0x180001299  mov     rbp, [rsp+68h+arg_18]
0x1800012a1  add     rsp, 38h
0x1800012a5  pop     r15
0x1800012a7  pop     r13
0x1800012a9  pop     r12
0x1800012ab  pop     rdi
0x1800012ac  pop     rsi
0x1800012ad  pop     rbx
0x1800012ae  retn
0x1800012af  add     rbx, 0FFFFFFFFFFFFFFD8h
0x1800012b3  jmp     loc_180001168
0x1800012b8  cmp     eax, [rbx+1Ch]
0x1800012bb  jnz     short loc_180001279
0x1800012bd  jmp     loc_180001196
0x1800012c2  mov     rax, [rbx]
0x1800012c5  mov     rcx, rbx
0x1800012c8  mov     rax, [rax+8]
0x1800012cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d1  cmp     edi, eax
0x1800012d3  mov     eax, [rsp+68h+arg_8]
0x1800012d7  jnz     short loc_180001279
0x1800012d9  jmp     loc_18000119E
0x1800012de  test    byte ptr [rbx+18h], 1
0x1800012e2  jz      short loc_180001279
0x1800012e4  jmp     loc_1800011A7
0x1800012e9  mov     eax, [rbx+18h]
0x1800012ec  test    al, 4
0x1800012ee  jnz     short loc_180001275
0x1800012f0  jmp     loc_1800011B0
0x1800012f5  add     rbx, 0FFFFFFFFFFFFFFD8h
0x1800012f9  jmp     loc_180001185
0x1800012fe  mov     ecx, 3
0x180001303  int     29h; Win8: RtlFailFast(ecx)
0x180001305  mov     ecx, 0Eh
0x18000130a  jmp     short loc_180001311
0x18000130c  mov     ecx, 0Dh; dwErrCode
0x180001311  call    cs:__imp_SetLastError
0x180001317  mov     rax, [rdi]
0x18000131a  mov     edx, 1
0x18000131f  mov     rcx, rdi
0x180001322  mov     rax, [rax]
0x180001325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000132a  jmp     loc_180001294
```
