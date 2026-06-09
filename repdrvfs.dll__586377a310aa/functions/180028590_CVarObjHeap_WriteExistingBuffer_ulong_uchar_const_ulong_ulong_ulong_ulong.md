# CVarObjHeap::WriteExistingBuffer(ulong,uchar const *,ulong,ulong,ulong *,ulong *)

- ea: `0x180028590`
- end: `0x1800286e4`
- name: `?WriteExistingBuffer@CVarObjHeap@@QEAAKKPEBEKKPEAK1@Z`
- size: `340`
- prototype: `unsigned int __fastcall(CVarObjHeap *__hidden this, unsigned int, const unsigned __int8 *Buf2, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800203a0`

## callees

- `0x1800012b8`
- `0x1800136b8`
- `0x180020b38`
- `0x180028590`
- `0x18002bf30`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800285c1`
- `wbemcomn!GetMemLogObject` at `0x18002868d`
- `wbemcomn!GetMemLogObject` at `0x1800285c1`
- `wbemcomn!GetMemLogObject` at `0x18002868d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800285d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028698`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800285d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028698`

## pseudocode

```c
__int64 __fastcall CVarObjHeap::WriteExistingBuffer(
        CPageFile **this,
        unsigned int a2,
        const unsigned __int8 *Buf2,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v12; // ebx
  CVarObjHeap *v13; // rcx
  __int64 v14; // rdx
  CMemoryLog *v15; // rax

  if ( !a5 )
  {
    CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
    MemLogObject = GetMemLogObject();
    v12 = 1359;
    CMemoryLog::Write(MemLogObject, 1359);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = a5 + 16;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, v12);
      return v12;
    }
    return v12;
  }
  if ( !CVarObjHeap::IsIdenticalBlock((CVarObjHeap *)this, a4, a5, a2, Buf2) )
  {
    v12 = CVarObjHeap::DeleteBuffer(this, a4, a5);
    if ( !v12 )
      v12 = CVarObjHeap::WriteNewBuffer(this, a2, Buf2, a6, a7);
    if ( *a7 )
    {
      if ( !v12 )
        goto LABEL_14;
    }
    else
    {
      CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
      v12 = 1359;
    }
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, v12);
    goto LABEL_14;
  }
  v12 = 0;
  *a6 = a4;
  *a7 = a5;
LABEL_14:
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 17;
    goto LABEL_18;
  }
  return v12;
}

```

## disassembly

```asm
0x180028590  push    rbx
0x180028592  push    rbp
0x180028593  push    rsi
0x180028594  push    rdi
0x180028595  push    r14
0x180028597  push    r15
0x180028599  sub     rsp, 38h
0x18002859d  mov     edi, [rsp+68h+arg_20]
0x1800285a4  mov     esi, r9d
0x1800285a7  mov     r14, r8
0x1800285aa  mov     r15d, edx
0x1800285ad  mov     rbp, rcx
0x1800285b0  test    edi, edi
0x1800285b2  jnz     short loc_18002860A
0x1800285b4  xor     r8d, r8d; unsigned int
0x1800285b7  lea     ecx, [rdi+2]; int
0x1800285ba  xor     edx, edx; bool
0x1800285bc  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x1800285c1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800285c7  mov     ebx, 54Fh
0x1800285cc  mov     rcx, rax
0x1800285cf  mov     edx, ebx
0x1800285d1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800285d7  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800285de  lea     rax, WPP_GLOBAL_Control
0x1800285e5  cmp     rcx, rax
0x1800285e8  jz      loc_1800286D5
0x1800285ee  test    byte ptr [rcx+1Ch], 1
0x1800285f2  jz      loc_1800286D5
0x1800285f8  cmp     byte ptr [rcx+19h], 2
0x1800285fc  jb      loc_1800286D5
0x180028602  lea     edx, [rdi+10h]
0x180028605  jmp     loc_1800286C2
0x18002860a  mov     r9d, r15d; unsigned int
0x18002860d  mov     [rsp+68h+var_48], r14; Buf2
0x180028612  mov     r8d, edi; unsigned int
0x180028615  mov     edx, esi; unsigned int
0x180028617  call    ?IsIdenticalBlock@CVarObjHeap@@QEAA_NKKKPEBE@Z; CVarObjHeap::IsIdenticalBlock(ulong,ulong,ulong,uchar const *)
0x18002861c  test    al, al
0x18002861e  jz      short loc_180028638
0x180028620  mov     rax, [rsp+68h+arg_28]
0x180028628  xor     ebx, ebx
0x18002862a  mov     [rax], esi
0x18002862c  mov     rax, [rsp+68h+arg_30]
0x180028634  mov     [rax], edi
0x180028636  jmp     short loc_18002869E
0x180028638  mov     r8d, edi; unsigned int
0x18002863b  mov     edx, esi; unsigned int
0x18002863d  mov     rcx, rbp; this
0x180028640  call    ?DeleteBuffer@CVarObjHeap@@QEAAKKK@Z; CVarObjHeap::DeleteBuffer(ulong,ulong)
0x180028645  mov     rdi, [rsp+68h+arg_30]
0x18002864d  mov     ebx, eax
0x18002864f  test    eax, eax
0x180028651  jnz     short loc_180028670
0x180028653  mov     r9, [rsp+68h+arg_28]; unsigned int *
0x18002865b  mov     r8, r14; unsigned __int8 *
0x18002865e  mov     edx, r15d; unsigned int
0x180028661  mov     [rsp+68h+var_48], rdi; unsigned int *
0x180028666  mov     rcx, rbp; this
0x180028669  call    ?WriteNewBuffer@CVarObjHeap@@QEAAKKPEBEPEAK1@Z; CVarObjHeap::WriteNewBuffer(ulong,uchar const *,ulong *,ulong *)
0x18002866e  mov     ebx, eax
0x180028670  cmp     dword ptr [rdi], 0
0x180028673  jnz     short loc_180028689
0x180028675  xor     edx, edx; bool
0x180028677  xor     r8d, r8d; unsigned int
0x18002867a  lea     ecx, [rdx+2]; int
0x18002867d  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180028682  mov     ebx, 54Fh
0x180028687  jmp     short loc_18002868D
0x180028689  test    ebx, ebx
0x18002868b  jz      short loc_18002869E
0x18002868d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028693  mov     rcx, rax
0x180028696  mov     edx, ebx
0x180028698  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002869e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286a5  lea     rax, WPP_GLOBAL_Control
0x1800286ac  cmp     rcx, rax
0x1800286af  jz      short loc_1800286D5
0x1800286b1  test    byte ptr [rcx+1Ch], 1
0x1800286b5  jz      short loc_1800286D5
0x1800286b7  cmp     byte ptr [rcx+19h], 2
0x1800286bb  jb      short loc_1800286D5
0x1800286bd  mov     edx, 11h
0x1800286c2  mov     rcx, [rcx+10h]
0x1800286c6  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x1800286cd  mov     r9d, ebx
0x1800286d0  call    WPP_SF_d
0x1800286d5  mov     eax, ebx
0x1800286d7  add     rsp, 38h
0x1800286db  pop     r15
0x1800286dd  pop     r14
0x1800286df  pop     rdi
0x1800286e0  pop     rsi
0x1800286e1  pop     rbp
0x1800286e2  pop     rbx
0x1800286e3  retn
```
