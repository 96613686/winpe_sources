# CSurfaceProducer::~CSurfaceProducer(void)

- ea: `0x1800c15e4`
- end: `0x1800c16c3`
- name: `??1CSurfaceProducer@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(CSurfaceProducer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800c171c`

## callees

- `0x180073d00`
- `0x1800c15e4`
- `0x1800c2e70`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c16a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c16a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1636`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1619`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1619`

## pseudocode

```c
void __fastcall CSurfaceProducer::~CSurfaceProducer(CSurfaceProducer *this)
{
  __int64 v1; // rdi
  bool v3; // zf
  __int64 i; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx

  v1 = *((_QWORD *)this + 2);
  *(_QWORD *)this = &CSurfaceProducer::`vftable';
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 12) )
      AcquireSRWLockExclusive((PSRWLOCK)(v1 + 128));
    v3 = *(_DWORD *)(v1 + 12) == 0;
    *(_QWORD *)(v1 + 48) = 0;
    if ( !v3 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v1 + 128));
    CSurfaceQueue::Release(*((CSurfaceQueue **)this + 2));
  }
  if ( *((_QWORD *)this + 10) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); i = (unsigned int)(i + 1) )
    {
      v5 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * i);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    operator delete(*((void **)this + 10));
  }
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 64LL))(v6, 1);
  if ( *((_DWORD *)this + 3) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
}

```

## disassembly

```asm
0x1800c15e4  mov     [rsp+arg_0], rbx
0x1800c15e9  mov     [rsp+arg_8], rsi
0x1800c15ee  push    rdi
0x1800c15ef  sub     rsp, 20h
0x1800c15f3  mov     rdi, [rcx+10h]
0x1800c15f7  lea     rax, ??_7CSurfaceProducer@@6B@; const CSurfaceProducer::`vftable'
0x1800c15fe  mov     [rcx], rax
0x1800c1601  mov     rbx, rcx
0x1800c1604  test    rdi, rdi
0x1800c1607  jz      short loc_1800C164B
0x1800c1609  cmp     dword ptr [rdi+0Ch], 0
0x1800c160d  lea     rsi, [rdi+80h]
0x1800c1614  jz      short loc_1800C1625
0x1800c1616  mov     rcx, rsi; SRWLock
0x1800c1619  call    cs:__imp_AcquireSRWLockExclusive
0x1800c1620  nop     dword ptr [rax+rax+00h]
0x1800c1625  cmp     dword ptr [rdi+0Ch], 0
0x1800c1629  mov     qword ptr [rdi+30h], 0
0x1800c1631  jz      short loc_1800C1642
0x1800c1633  mov     rcx, rsi; SRWLock
0x1800c1636  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c163d  nop     dword ptr [rax+rax+00h]
0x1800c1642  mov     rcx, [rbx+10h]; this
0x1800c1646  call    ?Release@CSurfaceQueue@@UEAAKXZ; CSurfaceQueue::Release(void)
0x1800c164b  cmp     qword ptr [rbx+50h], 0
0x1800c1650  jz      short loc_1800C1682
0x1800c1652  xor     edi, edi
0x1800c1654  cmp     [rbx+48h], edi
0x1800c1657  jbe     short loc_1800C1679
0x1800c1659  mov     rax, [rbx+50h]
0x1800c165d  mov     rcx, [rax+rdi*8]
0x1800c1661  test    rcx, rcx
0x1800c1664  jz      short loc_1800C1672
0x1800c1666  mov     rax, [rcx]
0x1800c1669  mov     rax, [rax+10h]
0x1800c166d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1672  inc     edi
0x1800c1674  cmp     edi, [rbx+48h]
0x1800c1677  jb      short loc_1800C1659
0x1800c1679  mov     rcx, [rbx+50h]; Block
0x1800c167d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c1682  mov     rcx, [rbx+18h]
0x1800c1686  test    rcx, rcx
0x1800c1689  jz      short loc_1800C169C
0x1800c168b  mov     rax, [rcx]
0x1800c168e  mov     edx, 1
0x1800c1693  mov     rax, [rax+40h]
0x1800c1697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c169c  cmp     dword ptr [rbx+0Ch], 0
0x1800c16a0  jz      short loc_1800C16B2
0x1800c16a2  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800c16a6  call    cs:__imp_DeleteCriticalSection
0x1800c16ad  nop     dword ptr [rax+rax+00h]
0x1800c16b2  mov     rbx, [rsp+28h+arg_0]
0x1800c16b7  mov     rsi, [rsp+28h+arg_8]
0x1800c16bc  add     rsp, 20h
0x1800c16c0  pop     rdi
0x1800c16c1  retn
```
