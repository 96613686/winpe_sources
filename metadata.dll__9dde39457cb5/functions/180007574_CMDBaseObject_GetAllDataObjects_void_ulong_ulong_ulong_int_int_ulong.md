# CMDBaseObject::GetAllDataObjects(void * *,ulong,ulong,ulong,int,int,ulong *)

- ea: `0x180007574`
- end: `0x1800077e2`
- name: `?GetAllDataObjects@CMDBaseObject@@QEAAKPEAPEAXKKKHHPEAK@Z`
- size: `622`
- prototype: `unsigned int(CMDBaseObject *__hidden this, void **, unsigned int, unsigned int, unsigned int, int, int, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800166b8`
- `0x180016bb4`
- `0x18001ca3c`
- `0x1800209e8`
- `0x180022ff0`

## callees

- `0x180001130`
- `0x180007574`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800076cc`
- `KERNEL32!SetLastError` at `0x180007764`
- `KERNEL32!SetLastError` at `0x1800076cc`
- `KERNEL32!SetLastError` at `0x180007764`
- `IisRTL!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000763b`
- `IisRTL!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000763b`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180007670`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180007670`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180007612`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180007612`

## pseudocode

```c
__int64 __fastcall CMDBaseObject::GetAllDataObjects(
        CMDBaseObject *this,
        void **a2,
        char a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        unsigned int *a8)
{
  unsigned int v8; // esi
  __int64 v9; // rbx
  char *v12; // rdx
  bool v13; // zf
  __int64 i; // rax
  __int64 v15; // rdx
  char *v16; // rcx
  int v17; // r14d
  _QWORD *v18; // rbp
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  int inserted; // eax
  void **v22; // rdx
  char *v23; // rcx
  DWORD v25; // ecx
  CMDBaseObject *v26; // rbx
  unsigned int v27; // [rsp+40h] [rbp-48h] BYREF
  char *v28; // [rsp+48h] [rbp-40h]
  __int64 v29; // [rsp+50h] [rbp-38h] BYREF

  v8 = 0;
  v9 = 0;
  v27 = 0;
  v28 = (char *)this + 264;
  v12 = (char *)this + 264;
  v13 = v28 == *(char **)v28;
  for ( i = *((_QWORD *)this + 33) - 40LL; ; i = (__int64)(v23 - 40) )
  {
    if ( !v13 )
      v9 = i;
    if ( !v9 )
      break;
    if ( !a4 || a4 == *(_DWORD *)(v9 + 28) )
    {
      if ( (!a5 || a5 == (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v9 + 8LL))(v9, v12))
        && (!a6 || (*(_BYTE *)(v9 + 24) & 1) != 0)
        && (!a7 || (*(_DWORD *)(v9 + 24) & 4) == 0) )
      {
        v15 = *(unsigned int *)(v9 + 8);
        v16 = (char *)*a2 + 8;
        v29 = 0;
        if ( (unsigned int)CLKRHashTable::FindKey(v16, v15, &v29) || !*(_QWORD *)(v29 + 8) )
        {
          v17 = *(_DWORD *)(v9 + 8);
          v18 = *a2;
          v19 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)HASH_BUFFER_ENTRY::sm_pach);
          v20 = v19;
          if ( !v19 )
          {
            SetLastError(0xEu);
            break;
          }
          *v19 = &HASH_BUFFER_ENTRY::`vftable';
          v19[4] = v19 + 3;
          v19[3] = v19 + 3;
          *((_DWORD *)v19 + 4) = v17;
          v19[1] = v9;
          inserted = CLKRHashTable::InsertRecord(v18 + 1, v19, 0);
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
            (*(void (__fastcall **)(_QWORD *, __int64))*v20)(v20, 1);
            break;
          }
          v22 = (void **)v18[11];
          if ( *v22 != v18 + 10 )
            __fastfail(3u);
          ++v8;
          v20[3] = v18 + 10;
          v20[4] = v22;
          *v22 = v20 + 3;
          v18[11] = v20 + 3;
          v27 = v8;
        }
      }
      v12 = v28;
    }
    v23 = *(char **)(v9 + 40);
    v9 = 0;
    v13 = v12 == v23;
  }
  if ( a8 )
    *a8 = v8;
  if ( (a3 & 1) != 0 )
  {
    v26 = (CMDBaseObject *)*((_QWORD *)this + 23);
    if ( v26 )
    {
      do
      {
        CMDBaseObject::CopyDataObjectsToBufferByType(v26, a4, a5, a2, &v27, 1, a7);
        v26 = (CMDBaseObject *)*((_QWORD *)v26 + 23);
      }
      while ( v26 );
      return v27;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180007574  mov     rax, rsp
0x180007577  mov     [rax+10h], rbx
0x18000757b  mov     [rax+20h], rbp
0x18000757f  mov     [rax+18h], r8d
0x180007583  mov     [rax+8], rcx
0x180007587  push    rsi
0x180007588  push    rdi
0x180007589  push    r13
0x18000758b  push    r14
0x18000758d  push    r15
0x18000758f  sub     rsp, 60h
0x180007593  add     rcx, 108h
0x18000759a  xor     esi, esi
0x18000759c  xor     ebx, ebx
0x18000759e  mov     [rax-48h], esi
0x1800075a1  mov     r13, rdx
0x1800075a4  mov     [rsp+88h+var_40], rcx
0x1800075a9  mov     r15d, r9d
0x1800075ac  mov     rdx, rcx
0x1800075af  mov     r10, [rcx]
0x1800075b2  cmp     rcx, r10
0x1800075b5  lea     rax, [r10-28h]
0x1800075b9  cmovnz  rbx, rax
0x1800075bd  test    rbx, rbx
0x1800075c0  jz      loc_1800076D2
0x1800075c6  test    r15d, r15d
0x1800075c9  jnz     loc_18000770A
0x1800075cf  cmp     [rsp+88h+arg_20], 0
0x1800075d7  jnz     loc_180007715
0x1800075dd  cmp     [rsp+88h+arg_28], 0
0x1800075e5  jnz     loc_180007732
0x1800075eb  cmp     [rsp+88h+arg_30], 0
0x1800075f3  jnz     loc_180007741
0x1800075f9  mov     rcx, [r13+0]
0x1800075fd  lea     r8, [rsp+88h+var_38]
0x180007602  mov     edx, [rbx+8]
0x180007605  add     rcx, 8
0x180007609  mov     [rsp+88h+var_38], 0
0x180007612  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180007618  test    eax, eax
0x18000761a  jnz     short loc_18000762C
0x18000761c  mov     rax, [rsp+88h+var_38]
0x180007621  cmp     qword ptr [rax+8], 0
0x180007626  jnz     loc_1800076B0
0x18000762c  mov     rcx, cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x180007633  mov     r14d, [rbx+8]
0x180007637  mov     rbp, [r13+0]
0x18000763b  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180007641  mov     rdi, rax
0x180007644  test    rax, rax
0x180007647  jz      short loc_1800076C7
0x180007649  lea     rax, ??_7HASH_BUFFER_ENTRY@@6B@; const HASH_BUFFER_ENTRY::`vftable'
0x180007650  xor     r8d, r8d
0x180007653  mov     [rdi], rax
0x180007656  lea     rcx, [rbp+8]
0x18000765a  lea     rax, [rdi+18h]
0x18000765e  mov     rdx, rdi
0x180007661  mov     [rdi+20h], rax
0x180007665  mov     [rax], rax
0x180007668  mov     [rdi+10h], r14d
0x18000766c  mov     [rdi+8], rbx
0x180007670  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180007676  cmp     eax, 1
0x180007679  jz      loc_18000775F
0x18000767f  test    eax, eax
0x180007681  jnz     loc_180007758
0x180007687  lea     rcx, [rbp+50h]
0x18000768b  mov     rdx, [rcx+8]
0x18000768f  cmp     [rdx], rcx
0x180007692  jnz     loc_180007751
0x180007698  lea     rax, [rdi+18h]
0x18000769c  inc     esi
0x18000769e  mov     [rax], rcx
0x1800076a1  mov     [rax+8], rdx
0x1800076a5  mov     [rdx], rax
0x1800076a8  mov     [rcx+8], rax
0x1800076ac  mov     [rsp+88h+var_48], esi
0x1800076b0  mov     rdx, [rsp+88h+var_40]
0x1800076b5  mov     rcx, [rbx+28h]
0x1800076b9  xor     ebx, ebx
0x1800076bb  cmp     rdx, rcx
0x1800076be  lea     rax, [rcx-28h]
0x1800076c2  jmp     loc_1800075B9
0x1800076c7  mov     ecx, 0Eh; dwErrCode
0x1800076cc  call    cs:__imp_SetLastError
0x1800076d2  mov     rax, [rsp+88h+arg_38]
0x1800076da  test    rax, rax
0x1800076dd  jz      short loc_1800076E1
0x1800076df  mov     [rax], esi
0x1800076e1  test    [rsp+88h+arg_10], 1
0x1800076e9  jnz     loc_180007782
0x1800076ef  lea     r11, [rsp+88h+var_28]
0x1800076f4  mov     eax, esi
0x1800076f6  mov     rbx, [r11+38h]
0x1800076fa  mov     rbp, [r11+48h]
0x1800076fe  mov     rsp, r11
0x180007701  pop     r15
0x180007703  pop     r14
0x180007705  pop     r13
0x180007707  pop     rdi
0x180007708  pop     rsi
0x180007709  retn
0x18000770a  cmp     r15d, [rbx+1Ch]
0x18000770e  jnz     short loc_1800076B5
0x180007710  jmp     loc_1800075CF
0x180007715  mov     rax, [rbx]
0x180007718  mov     rcx, rbx
0x18000771b  mov     rax, [rax+8]
0x18000771f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007724  cmp     [rsp+88h+arg_20], eax
0x18000772b  jnz     short loc_1800076B0
0x18000772d  jmp     loc_1800075DD
0x180007732  test    byte ptr [rbx+18h], 1
0x180007736  jz      loc_1800076B0
0x18000773c  jmp     loc_1800075EB
0x180007741  mov     eax, [rbx+18h]
0x180007744  test    al, 4
0x180007746  jnz     loc_1800076B0
0x18000774c  jmp     loc_1800075F9
0x180007751  mov     ecx, 3
0x180007756  int     29h; Win8: RtlFailFast(ecx)
0x180007758  mov     ecx, 0Eh
0x18000775d  jmp     short loc_180007764
0x18000775f  mov     ecx, 0Dh; dwErrCode
0x180007764  call    cs:__imp_SetLastError
0x18000776a  mov     rax, [rdi]
0x18000776d  mov     edx, 1
0x180007772  mov     rcx, rdi
0x180007775  mov     rax, [rax]
0x180007778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000777d  jmp     loc_1800076D2
0x180007782  mov     rbx, [rsp+88h+arg_0]
0x18000778a  mov     rbx, [rbx+0B8h]
0x180007791  test    rbx, rbx
0x180007794  jz      loc_1800076EF
0x18000779a  mov     eax, [rsp+88h+arg_30]
0x1800077a1  mov     r9, r13; void **
0x1800077a4  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x1800077ac  mov     edx, r15d; unsigned int
0x1800077af  mov     [rsp+88h+var_58], eax; int
0x1800077b3  mov     rcx, rbx; this
0x1800077b6  lea     rax, [rsp+88h+var_48]
0x1800077bb  mov     [rsp+88h+var_60], 1; int
0x1800077c3  mov     [rsp+88h+var_68], rax; unsigned int *
0x1800077c8  call    ?CopyDataObjectsToBufferByType@CMDBaseObject@@AEAAXKKPEAPEAXAEAKHH@Z; CMDBaseObject::CopyDataObjectsToBufferByType(ulong,ulong,void * *,ulong &,int,int)
0x1800077cd  mov     rbx, [rbx+0B8h]
0x1800077d4  test    rbx, rbx
0x1800077d7  jnz     short loc_18000779A
0x1800077d9  mov     esi, [rsp+88h+var_48]
0x1800077dd  jmp     loc_1800076EF
```
