# CMediaServerEnum::`vector deleting destructor'(uint)

- ea: `0x1800088b0`
- end: `0x180008970`
- name: `??_ECMediaServerEnum@@UEAAPEAXI@Z`
- size: `192`
- prototype: `void *__fastcall(CMediaServerEnum *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800088b0`
- `0x180011df4`
- `0x1800140e4`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800088fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008942`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800088fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008942`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800088e5`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800088e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008918`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008918`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CMediaServerEnum *__fastcall CMediaServerEnum::`vector deleting destructor'(CMediaServerEnum *this, char a2)
{
  unsigned __int64 i; // rbp
  LPITEMIDLIST *v5; // rax
  void *v6; // rcx
  struct _TP_TIMER *v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx

  *(_QWORD *)this = &CMediaServerEnum::`vftable';
  for ( i = 0; i < *((_QWORD *)this + 5); ++i )
  {
    v5 = (LPITEMIDLIST *)ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt((char *)this + 32);
    ILFree(*v5);
  }
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 4) = 0;
  }
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v7 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
  if ( v7 )
    CloseThreadpoolTimer(v7);
  v8 = *((_QWORD *)this + 8);
  if ( v8 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = (void *)*((_QWORD *)this + 4);
  if ( v9 )
    free(v9);
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800088b0  push    rbx
0x1800088b2  push    rbp
0x1800088b3  push    rsi
0x1800088b4  push    rdi
0x1800088b5  push    r14
0x1800088b7  sub     rsp, 20h
0x1800088bb  mov     esi, edx
0x1800088bd  mov     rbx, rcx
0x1800088c0  lea     rax, ??_7CMediaServerEnum@@6B@; const CMediaServerEnum::`vftable'
0x1800088c7  mov     [rcx], rax
0x1800088ca  xor     r14d, r14d
0x1800088cd  mov     ebp, r14d
0x1800088d0  cmp     [rcx+28h], r14
0x1800088d4  jbe     short loc_1800088F4
0x1800088d6  mov     rdx, rbp
0x1800088d9  lea     rcx, [rbx+20h]
0x1800088dd  call    ?GetAt@?$CAtlArray@PEAUIPropertyStore@@V?$CElementTraits@PEAUIPropertyStore@@@ATL@@@ATL@@QEAAAEAPEAUIPropertyStore@@_K@Z; ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(unsigned __int64)
0x1800088e2  mov     rcx, [rax]; pidl
0x1800088e5  call    cs:__imp_ILFree
0x1800088eb  inc     rbp
0x1800088ee  cmp     rbp, [rbx+28h]
0x1800088f2  jb      short loc_1800088D6
0x1800088f4  mov     rcx, [rbx+20h]; Block
0x1800088f8  test    rcx, rcx
0x1800088fb  jz      short loc_180008907
0x1800088fd  call    cs:__imp_free
0x180008903  mov     [rbx+20h], r14
0x180008907  mov     [rbx+28h], r14
0x18000890b  mov     [rbx+30h], r14
0x18000890f  mov     rcx, [rbx+48h]; pti
0x180008913  test    rcx, rcx
0x180008916  jz      short loc_18000891F
0x180008918  call    cs:__imp_CloseThreadpoolTimer
0x18000891e  nop
0x18000891f  mov     rcx, [rbx+40h]
0x180008923  test    rcx, rcx
0x180008926  jz      short loc_180008939
0x180008928  mov     [rbx+40h], r14
0x18000892c  mov     rax, [rcx]
0x18000892f  mov     rax, [rax+10h]
0x180008933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008938  nop
0x180008939  mov     rcx, [rbx+20h]; Block
0x18000893d  test    rcx, rcx
0x180008940  jz      short loc_180008948
0x180008942  call    cs:__imp_free
0x180008948  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000894f  test    sil, 1
0x180008953  jz      short loc_180008962
0x180008955  mov     edx, 50h ; 'P'
0x18000895a  mov     rcx, rbx; Block
0x18000895d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008962  mov     rax, rbx
0x180008965  add     rsp, 20h
0x180008969  pop     r14
0x18000896b  pop     rdi
0x18000896c  pop     rsi
0x18000896d  pop     rbp
0x18000896e  pop     rbx
0x18000896f  retn
```
