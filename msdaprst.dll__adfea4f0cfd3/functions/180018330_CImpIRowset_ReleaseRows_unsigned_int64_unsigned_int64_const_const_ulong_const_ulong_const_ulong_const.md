# CImpIRowset::ReleaseRows(unsigned __int64,unsigned __int64 const * const,ulong * const,ulong * const,ulong * const)

- ea: `0x180018330`
- end: `0x1800186ab`
- name: `?ReleaseRows@CImpIRowset@@UEAAJ_KQEB_KQEAK22@Z`
- size: `891`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64, const unsigned __int64 *const, unsigned int *const, unsigned int *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800023c0`
- `0x180011788`
- `0x180016584`
- `0x180017978`
- `0x180018330`
- `0x18001b008`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180018382`
- `KERNEL32!GetCurrentThreadId` at `0x180018382`
- `KERNEL32!LeaveCriticalSection` at `0x1800183e3`
- `KERNEL32!LeaveCriticalSection` at `0x180018684`
- `KERNEL32!LeaveCriticalSection` at `0x1800183e3`
- `KERNEL32!LeaveCriticalSection` at `0x180018684`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800183a7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800183a7`
- `MSDART!UMSEnterCSWraper` at `0x180018367`
- `MSDART!UMSEnterCSWraper` at `0x180018367`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CImpIRowset::ReleaseRows(
        CImpIRowset *this,
        unsigned __int64 a2,
        const unsigned __int64 *const a3,
        unsigned int *const a4,
        unsigned int *const a5,
        unsigned int *const a6)
{
  unsigned __int64 v7; // r13
  __int64 v9; // rdi
  DWORD *v10; // r14
  unsigned int v11; // ebx
  bool v12; // zf
  __int64 v13; // rcx
  int v15; // r12d
  __int64 v16; // rbx
  __int64 v17; // r15
  unsigned __int64 v18; // r8
  int v19; // r9d
  __int64 v20; // r10
  unsigned int *v21; // r12
  __int64 v22; // r9
  unsigned int v23; // r13d
  __int64 v24; // rcx
  unsigned int BidObjectID; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rcx
  int v29; // [rsp+30h] [rbp-58h]
  DWORD *v30; // [rsp+38h] [rbp-50h]
  int v31; // [rsp+90h] [rbp+8h]

  v7 = a2;
  v9 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v9);
  v10 = (DWORD *)(v9 + 8);
  v30 = (DWORD *)(v9 + 8);
  if ( *(_DWORD *)(v9 + 12) )
    v30 = (DWORD *)(v9 + 8);
  else
    *v10 = GetCurrentThreadId();
  ++*(_DWORD *)(v9 + 12);
  ++*(_DWORD *)(v9 + 16);
  SetErrorInfo(0, 0);
  if ( v7 && !a3 )
  {
    v11 = Exit(-2147024809, 0);
    --*(_DWORD *)(v9 + 16);
    v12 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v12 )
      *v10 = -1;
LABEL_8:
    v13 = *(_QWORD *)v9;
    --*(_DWORD *)(v13 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
    return v11;
  }
  v29 = 0;
  v15 = 0;
  v16 = 0;
  v31 = 0;
  if ( v7 )
  {
    do
    {
      v17 = (unsigned int)v16;
      if ( (unsigned int)CBitArray::IsSlotSet(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL), a3[v16]) )
      {
        v29 = 1;
        if ( (bidGblFlags & 2) != 0 && off_180049B00[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049278[0], 375808, off_180049B00[0], BidObjectID, v16);
        }
        if ( a5 )
          a5[v16] = 0;
        if ( a6 )
          a6[v16] = 12;
      }
      else
      {
        v21 = (unsigned int *)(*(_QWORD *)(v20 + 224) + (unsigned int)(*(_DWORD *)(v20 + 220) * v19));
        --*v21;
        --*(_DWORD *)(*((_QWORD *)this + 3) + 264LL);
        if ( a5 )
          a5[v16] = *v21;
        if ( !*v21 )
        {
          v22 = *((_QWORD *)this + 3);
          if ( *(_DWORD *)(v22 + 152) )
          {
            v23 = 1;
            do
            {
              (*(void (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v22 + 80LL))(
                v22,
                (char *)v21 + *(unsigned int *)(*(_QWORD *)(v22 + 160) + 4LL * v23),
                v23);
              v24 = *((_QWORD *)this + 3);
              v18 = *(unsigned int *)(v24 + 216)
                  + (unsigned __int64)*(unsigned int *)(*(_QWORD *)(v24 + 160) + 4LL * v23);
              if ( *(unsigned int *)((char *)v21 + v18 + 4) != 8 )
                (*(void (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v24 + 80LL))(v24, (char *)v21 + v18, v23);
              ++v23;
              v22 = *((_QWORD *)this + 3);
            }
            while ( v23 <= *(_DWORD *)(v22 + 152) );
            LODWORD(v16) = v31;
            v7 = a2;
          }
          ReleaseSlots(*(struct tagLSTSLOT **)(v22 + 200), a3[v17], v18);
        }
        if ( a6 )
          a6[v17] = 0;
        v15 = 1;
      }
      v16 = (unsigned int)(v16 + 1);
      v31 = v16;
    }
    while ( (unsigned int)v16 < v7 );
    v10 = v30;
    if ( v29 )
    {
      if ( v15 )
      {
        v11 = 265946;
        if ( (bidGblFlags & 2) != 0 && off_180049AF8[0] )
        {
          v26 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049270[0], 388096, off_180049AF8[0], v26, 265946);
        }
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 && off_180049AF0[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049268[0], 393216, off_180049AF0[0], v27, -2147217887);
        }
        v11 = Exit(-2147217887, 0);
      }
      --*(_DWORD *)(v9 + 16);
      v12 = (*(_DWORD *)(v9 + 12))-- == 1;
      if ( v12 )
        *(_DWORD *)(v9 + 8) = -1;
      goto LABEL_8;
    }
  }
  --*(_DWORD *)(v9 + 16);
  v12 = (*(_DWORD *)(v9 + 12))-- == 1;
  if ( v12 )
    *v10 = -1;
  v28 = *(_QWORD *)v9;
  --*(_DWORD *)(v28 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 8));
  return 0;
}

```

## disassembly

```asm
0x180018330  mov     [rsp+arg_18], rbx
0x180018335  mov     [rsp+arg_10], r8
0x18001833a  mov     [rsp+arg_8], rdx
0x18001833f  push    rbp
0x180018340  push    rsi
0x180018341  push    rdi
0x180018342  push    r12
0x180018344  push    r13
0x180018346  push    r14
0x180018348  push    r15
0x18001834a  sub     rsp, 50h
0x18001834e  mov     rbx, r8
0x180018351  mov     r13, rdx
0x180018354  mov     rbp, rcx
0x180018357  mov     rdi, [rcx+18h]
0x18001835b  sub     rdi, 0FFFFFFFFFFFFFF80h
0x18001835f  mov     [rsp+88h+var_48], rdi
0x180018364  mov     rcx, rdi
0x180018367  call    cs:__imp_UMSEnterCSWraper
0x18001836e  nop     dword ptr [rax+rax+00h]
0x180018373  lea     r14, [rdi+8]
0x180018377  mov     [rsp+88h+var_50], r14
0x18001837c  cmp     dword ptr [rdi+0Ch], 0
0x180018380  jnz     short loc_180018393
0x180018382  call    cs:__imp_GetCurrentThreadId
0x180018389  nop     dword ptr [rax+rax+00h]
0x18001838e  mov     [r14], eax
0x180018391  jmp     short loc_180018398
0x180018393  mov     [rsp+88h+var_50], r14
0x180018398  inc     dword ptr [rdi+0Ch]
0x18001839b  inc     dword ptr [rdi+10h]
0x18001839e  mov     [rsp+88h+var_40], rdi
0x1800183a3  xor     edx, edx; perrinfo
0x1800183a5  xor     ecx, ecx; dwReserved
0x1800183a7  call    cs:__imp_SetErrorInfo
0x1800183ae  nop     dword ptr [rax+rax+00h]
0x1800183b3  test    r13, r13
0x1800183b6  jz      short loc_1800183F6
0x1800183b8  test    rbx, rbx
0x1800183bb  jnz     short loc_1800183F6
0x1800183bd  xor     edx, edx; unsigned int
0x1800183bf  mov     ecx, 80070057h; int
0x1800183c4  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800183c9  mov     ebx, eax
0x1800183cb  or      esi, 0FFFFFFFFh
0x1800183ce  add     [rdi+10h], esi
0x1800183d1  add     [rdi+0Ch], esi
0x1800183d4  jnz     short loc_1800183D9
0x1800183d6  mov     [r14], esi
0x1800183d9  mov     rcx, [rdi]
0x1800183dc  dec     dword ptr [rcx+30h]
0x1800183df  add     rcx, 8; lpCriticalSection
0x1800183e3  call    cs:__imp_LeaveCriticalSection
0x1800183ea  nop     dword ptr [rax+rax+00h]
0x1800183ef  mov     eax, ebx
0x1800183f1  jmp     loc_180018692
0x1800183f6  xor     eax, eax
0x1800183f8  mov     [rsp+88h+var_58], eax
0x1800183fc  xor     r12d, r12d
0x1800183ff  xor     ebx, ebx
0x180018401  mov     [rsp+88h+arg_0], ebx
0x180018408  or      esi, 0FFFFFFFFh
0x18001840b  test    r13, r13
0x18001840e  jz      loc_18001866E
0x180018414  mov     rdi, [rsp+88h+arg_28]
0x18001841c  mov     r14, [rsp+88h+arg_20]
0x180018424  mov     r10, [rbp+18h]
0x180018428  mov     r15d, ebx
0x18001842b  mov     rax, [rsp+88h+arg_10]
0x180018433  mov     r9d, [rax+rbx*8]
0x180018437  mov     edx, r9d; unsigned int
0x18001843a  mov     rcx, [r10+0D0h]; this
0x180018441  call    ?IsSlotSet@CBitArray@@QEAAJK@Z; CBitArray::IsSlotSet(ulong)
0x180018446  test    eax, eax
0x180018448  jnz     loc_18001853B
0x18001844e  imul    r9d, [r10+0DCh]
0x180018456  mov     r12d, r9d
0x180018459  add     r12, [r10+0E0h]
0x180018460  add     [r12], esi
0x180018464  mov     rax, [rbp+18h]
0x180018468  add     [rax+108h], esi
0x18001846e  test    r14, r14
0x180018471  jz      short loc_18001847B
0x180018473  mov     eax, [r12]
0x180018477  mov     [r14+rbx*4], eax
0x18001847b  cmp     dword ptr [r12], 0
0x180018480  jnz     loc_180018526
0x180018486  mov     r9, [rbp+18h]
0x18001848a  cmp     dword ptr [r9+98h], 1
0x180018492  jb      short loc_18001850E
0x180018494  mov     r13d, 1
0x18001849a  mov     ebx, r13d
0x18001849d  mov     rcx, [r9]
0x1800184a0  mov     rax, [r9+0A0h]
0x1800184a7  mov     edx, [rax+rbx*4]
0x1800184aa  add     rdx, r12
0x1800184ad  mov     rax, [rcx+50h]
0x1800184b1  mov     r8d, r13d
0x1800184b4  mov     rcx, r9
0x1800184b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184bc  mov     rcx, [rbp+18h]
0x1800184c0  mov     rax, [rcx+0A0h]
0x1800184c7  mov     r8d, [rax+rbx*4]
0x1800184cb  mov     eax, [rcx+0D8h]
0x1800184d1  add     r8, rax
0x1800184d4  cmp     dword ptr [r8+r12+4], 8
0x1800184da  jz      short loc_1800184EF
0x1800184dc  mov     rax, [rcx]
0x1800184df  lea     rdx, [r8+r12]
0x1800184e3  mov     r8d, r13d
0x1800184e6  mov     rax, [rax+50h]
0x1800184ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ef  inc     r13d
0x1800184f2  mov     r9, [rbp+18h]
0x1800184f6  cmp     r13d, [r9+98h]
0x1800184fd  jbe     short loc_18001849A
0x1800184ff  mov     ebx, [rsp+88h+arg_0]
0x180018506  mov     r13, [rsp+88h+arg_8]
0x18001850e  mov     rax, [rsp+88h+arg_10]
0x180018516  mov     edx, [rax+r15*8]; unsigned int
0x18001851a  mov     rcx, [r9+0C8h]; struct tagLSTSLOT *
0x180018521  call    ?ReleaseSlots@@YAJPEAUtagLSTSLOT@@KK@Z; ReleaseSlots(tagLSTSLOT *,ulong,ulong)
0x180018526  test    rdi, rdi
0x180018529  jz      short loc_180018533
0x18001852b  mov     dword ptr [rdi+r15*4], 0
0x180018533  mov     r12d, 1
0x180018539  jmp     short loc_180018599
0x18001853b  mov     [rsp+88h+var_58], 1
0x180018543  test    byte ptr cs:_bidGblFlags, 2
0x18001854a  jz      short loc_180018580
0x18001854c  mov     rax, cs:off_180049B00; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180018553  test    rax, rax
0x180018556  jz      short loc_180018580
0x180018558  lea     rcx, [rbp+20h]; this
0x18001855c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180018561  mov     r8, cs:off_180049B00; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180018568  mov     rcx, cs:off_180049278; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001856f  mov     [rsp+88h+var_68], ebx
0x180018573  mov     r9d, eax
0x180018576  mov     edx, 5BC00h
0x18001857b  call    _bidTraceW
0x180018580  test    r14, r14
0x180018583  jz      short loc_18001858D
0x180018585  mov     dword ptr [r14+rbx*4], 0
0x18001858d  test    rdi, rdi
0x180018590  jz      short loc_180018599
0x180018592  mov     dword ptr [rdi+rbx*4], 0Ch
0x180018599  inc     ebx
0x18001859b  mov     [rsp+88h+arg_0], ebx
0x1800185a2  mov     eax, ebx
0x1800185a4  cmp     rax, r13
0x1800185a7  jb      loc_180018424
0x1800185ad  cmp     [rsp+88h+var_58], 0
0x1800185b2  mov     rdi, [rsp+88h+var_48]
0x1800185b7  mov     r14, [rsp+88h+var_50]
0x1800185bc  jz      loc_18001866E
0x1800185c2  test    r12d, r12d
0x1800185c5  jz      short loc_18001861F
0x1800185c7  mov     ebx, 40EDAh
0x1800185cc  test    byte ptr cs:_bidGblFlags, 2
0x1800185d3  jz      short loc_18001860A
0x1800185d5  mov     rax, cs:off_180049AF8; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x1800185dc  test    rax, rax
0x1800185df  jz      short loc_18001860A
0x1800185e1  lea     rcx, [rbp+20h]; this
0x1800185e5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800185ea  mov     r8, cs:off_180049AF8; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x1800185f1  mov     rcx, cs:off_180049270; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800185f8  mov     [rsp+88h+var_68], ebx
0x1800185fc  mov     r9d, eax
0x1800185ff  mov     edx, 5EC00h
0x180018604  call    _bidTraceW
0x180018609  nop
0x18001860a  dec     dword ptr [rdi+10h]
0x18001860d  sub     dword ptr [rdi+0Ch], 1
0x180018611  jnz     loc_1800183D9
0x180018617  mov     [rdi+8], esi
0x18001861a  jmp     loc_1800183D9
0x18001861f  mov     ebx, 80040E21h
0x180018624  test    byte ptr cs:_bidGblFlags, 2
0x18001862b  jz      short loc_180018661
0x18001862d  mov     rax, cs:off_180049AF0; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180018634  test    rax, rax
0x180018637  jz      short loc_180018661
0x180018639  lea     rcx, [rbp+20h]; this
0x18001863d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180018642  mov     r8, cs:off_180049AF0; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180018649  mov     rcx, cs:off_180049268; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180018650  mov     [rsp+88h+var_68], ebx
0x180018654  mov     r9d, eax
0x180018657  mov     edx, 60000h
0x18001865c  call    _bidTraceW
0x180018661  xor     edx, edx; unsigned int
0x180018663  mov     ecx, ebx; int
0x180018665  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001866a  mov     ebx, eax
0x18001866c  jmp     short loc_18001860A
0x18001866e  dec     dword ptr [rdi+10h]
0x180018671  sub     dword ptr [rdi+0Ch], 1
0x180018675  jnz     short loc_18001867A
0x180018677  mov     [r14], esi
0x18001867a  mov     rcx, [rdi]
0x18001867d  dec     dword ptr [rcx+30h]
0x180018680  add     rcx, 8; lpCriticalSection
0x180018684  call    cs:__imp_LeaveCriticalSection
0x18001868b  nop     dword ptr [rax+rax+00h]
0x180018690  xor     eax, eax
0x180018692  mov     rbx, [rsp+88h+arg_18]
0x18001869a  add     rsp, 50h
0x18001869e  pop     r15
0x1800186a0  pop     r14
0x1800186a2  pop     r13
0x1800186a4  pop     r12
0x1800186a6  pop     rdi
0x1800186a7  pop     rsi
0x1800186a8  pop     rbp
0x1800186a9  retn
```
