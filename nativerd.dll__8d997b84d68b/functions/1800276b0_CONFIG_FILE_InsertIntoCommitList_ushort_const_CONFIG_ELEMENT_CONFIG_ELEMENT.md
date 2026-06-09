# CONFIG_FILE::InsertIntoCommitList(ushort const *,CONFIG_ELEMENT *,CONFIG_ELEMENT * *)

- ea: `0x1800276b0`
- end: `0x18002787f`
- name: `?InsertIntoCommitList@CONFIG_FILE@@QEAAJPEBGPEAVCONFIG_ELEMENT@@PEAPEAV2@@Z`
- size: `463`
- prototype: `int(CONFIG_FILE *__hidden this, const unsigned __int16 *, struct CONFIG_ELEMENT *, struct CONFIG_ELEMENT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004c940`

## callees

- `0x180011130`
- `0x180014b08`
- `0x18001c250`
- `0x1800276b0`
- `0x18005b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800277b1`
- `msvcrt!_wcsicmp` at `0x1800277b1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002773b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002773b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180027747`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180027759`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180027747`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180027759`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027728`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027728`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800277a5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800277a5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027775`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027775`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002783f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002783f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002770c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002770c`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180027765`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180027765`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::InsertIntoCommitList(
        CONFIG_FILE *this,
        const unsigned __int16 *a2,
        struct CONFIG_ELEMENT *a3,
        struct CONFIG_ELEMENT **a4)
{
  _QWORD *v8; // rdi
  int v9; // ebx
  unsigned __int16 *Str; // rbx
  unsigned int CCH; // eax
  __int64 i; // rbx
  const wchar_t *v13; // rax
  const WCHAR *v14; // r9
  const WCHAR *v15; // rcx
  struct CONFIG_ELEMENT *v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  signed __int64 v19; // r9
  int v20; // eax
  int v21; // edx
  CONFIG_ELEMENT *v22; // rcx
  __int64 v24; // [rsp+80h] [rbp+18h]

  if ( a3 && a2 && a4 )
  {
    v8 = operator new(0x48u);
    if ( v8 )
    {
      *v8 = &COMMIT_ENTRY::`vftable';
      STRU::STRU((STRU *)(v8 + 1));
      v8[8] = a3;
      CONFIG_ELEMENT::ReferenceConfigElement(a3);
      v9 = STRU::Copy((STRU *)(v8 + 1), a2);
      if ( v9 < 0 )
        goto LABEL_24;
      Str = STRU::QueryStr((STRU *)(v8 + 1));
      if ( Str[STRU::QueryCCH((STRU *)(v8 + 1)) - 1] == 47 )
      {
        CCH = STRU::QueryCCH((STRU *)(v8 + 1));
        STRU::SetLen((STRU *)(v8 + 1), CCH - 1);
      }
      CReaderWriterLock3::WriteLock((CONFIG_FILE *)((char *)this + 344));
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 84); i = (unsigned int)(i + 1) )
      {
        v24 = *(_QWORD *)(*((_QWORD *)this + 41) + 8 * i);
        v13 = STRU::QueryStr((STRU *)(v24 + 8));
        if ( !_wcsicmp(a2, v13) )
        {
          v14 = &szDomain;
          v15 = &szDomain;
          v16 = *(struct CONFIG_ELEMENT **)(v24 + 64);
          v17 = *((_QWORD *)v16 + 10);
          if ( *(_QWORD *)(v17 + 24) )
            v14 = *(const WCHAR **)(v17 + 24);
          v18 = *((_QWORD *)a3 + 10);
          if ( *(_QWORD *)(v18 + 24) )
            v15 = *(const WCHAR **)(v18 + 24);
          v19 = (char *)v14 - (char *)v15;
          do
          {
            v20 = *(const WCHAR *)((char *)v15 + v19);
            v21 = *v15 - v20;
            if ( v21 )
              break;
            ++v15;
          }
          while ( v20 );
          if ( !v21 )
          {
            v22 = *(CONFIG_ELEMENT **)(v24 + 64);
            *a4 = v16;
            CONFIG_ELEMENT::ReferenceConfigElement(v22);
            v9 = 0;
            goto LABEL_23;
          }
        }
      }
      v9 = ARRAY_LIST::AddEntry((CONFIG_FILE *)((char *)this + 328), (struct IArrayListEntry *)v8, 0xFFFFFFFF);
      if ( v9 >= 0 )
        v8 = 0;
LABEL_23:
      CReaderWriterLock3::WriteUnlock((CONFIG_FILE *)((char *)this + 344));
      if ( v8 )
LABEL_24:
        (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 8LL))(v8, 1);
    }
    else
    {
      return (unsigned int)-2147024888;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800276b0  push    rbx
0x1800276b2  push    rbp
0x1800276b3  push    rsi
0x1800276b4  push    rdi
0x1800276b5  push    r12
0x1800276b7  push    r13
0x1800276b9  push    r14
0x1800276bb  push    r15
0x1800276bd  sub     rsp, 28h
0x1800276c1  mov     r12, r9
0x1800276c4  mov     rbp, r8
0x1800276c7  mov     r14, rdx
0x1800276ca  mov     r15, rcx
0x1800276cd  test    r8, r8
0x1800276d0  jz      loc_180027867
0x1800276d6  test    rdx, rdx
0x1800276d9  jz      loc_180027867
0x1800276df  test    r9, r9
0x1800276e2  jz      loc_180027867
0x1800276e8  mov     ecx, 48h ; 'H'; Size
0x1800276ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800276f2  mov     rdi, rax
0x1800276f5  test    rax, rax
0x1800276f8  jz      loc_180027860
0x1800276fe  lea     rax, ??_7COMMIT_ENTRY@@6B@; const COMMIT_ENTRY::`vftable'
0x180027705  lea     rcx, [rdi+8]
0x180027709  mov     [rdi], rax
0x18002770c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027712  mov     rcx, rbp; this
0x180027715  mov     [rdi+40h], rbp
0x180027719  call    ?ReferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ReferenceConfigElement(void)
0x18002771e  lea     rsi, [rdi+8]
0x180027722  mov     rdx, r14
0x180027725  mov     rcx, rsi
0x180027728  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002772e  mov     ebx, eax
0x180027730  test    eax, eax
0x180027732  js      loc_18002784A
0x180027738  mov     rcx, rsi
0x18002773b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180027741  mov     rcx, rsi
0x180027744  mov     rbx, rax
0x180027747  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002774d  dec     eax
0x18002774f  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x180027754  jnz     short loc_18002776B
0x180027756  mov     rcx, rsi
0x180027759  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002775f  mov     rcx, rsi
0x180027762  lea     edx, [rax-1]
0x180027765  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18002776b  lea     rsi, [r15+158h]
0x180027772  mov     rcx, rsi
0x180027775  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002777b  xor     ebx, ebx
0x18002777d  lea     r13, [r15+148h]
0x180027784  cmp     ebx, [r15+150h]
0x18002778b  jnb     loc_180027823
0x180027791  mov     rax, [r13+0]
0x180027795  mov     rax, [rax+rbx*8]
0x180027799  mov     [rsp+68h+arg_10], rax
0x1800277a1  lea     rcx, [rax+8]
0x1800277a5  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800277ab  mov     rdx, rax; String2
0x1800277ae  mov     rcx, r14; String1
0x1800277b1  call    cs:__imp__wcsicmp
0x1800277b7  test    eax, eax
0x1800277b9  jnz     short loc_18002780C
0x1800277bb  mov     r8, [rsp+68h+arg_10]
0x1800277c3  lea     r9, szDomain
0x1800277ca  lea     rcx, szDomain
0x1800277d1  mov     r8, [r8+40h]
0x1800277d5  mov     rax, [r8+50h]
0x1800277d9  cmp     qword ptr [rax+18h], 0
0x1800277de  cmovnz  r9, [rax+18h]
0x1800277e3  mov     rax, [rbp+50h]
0x1800277e7  cmp     qword ptr [rax+18h], 0
0x1800277ec  cmovnz  rcx, [rax+18h]
0x1800277f1  sub     r9, rcx
0x1800277f4  movzx   edx, word ptr [rcx]
0x1800277f7  movzx   eax, word ptr [rcx+r9]
0x1800277fc  sub     edx, eax
0x1800277fe  jnz     short loc_180027808
0x180027800  add     rcx, 2
0x180027804  test    eax, eax
0x180027806  jnz     short loc_1800277F4
0x180027808  test    edx, edx
0x18002780a  jz      short loc_180027813
0x18002780c  inc     ebx
0x18002780e  jmp     loc_180027784
0x180027813  mov     rcx, r8; this
0x180027816  mov     [r12], r8
0x18002781a  call    ?ReferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ReferenceConfigElement(void)
0x18002781f  xor     ebx, ebx
0x180027821  jmp     short loc_18002783C
0x180027823  or      r8d, 0FFFFFFFFh; unsigned int
0x180027827  mov     rdx, rdi; struct IArrayListEntry *
0x18002782a  mov     rcx, r13; this
0x18002782d  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180027832  xor     edx, edx
0x180027834  mov     ebx, eax
0x180027836  test    eax, eax
0x180027838  cmovns  rdi, rdx
0x18002783c  mov     rcx, rsi
0x18002783f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180027845  test    rdi, rdi
0x180027848  jz      short loc_18002786C
0x18002784a  mov     rax, [rdi]
0x18002784d  mov     edx, 1
0x180027852  mov     rcx, rdi
0x180027855  mov     rax, [rax+8]
0x180027859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002785e  jmp     short loc_18002786C
0x180027860  mov     ebx, 80070008h
0x180027865  jmp     short loc_18002786C
0x180027867  mov     ebx, 80070057h
0x18002786c  mov     eax, ebx
0x18002786e  add     rsp, 28h
0x180027872  pop     r15
0x180027874  pop     r14
0x180027876  pop     r13
0x180027878  pop     r12
0x18002787a  pop     rdi
0x18002787b  pop     rsi
0x18002787c  pop     rbp
0x18002787d  pop     rbx
0x18002787e  retn
```
