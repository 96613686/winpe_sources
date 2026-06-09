# PersistXmlStore::SetListOrder(ushort * *,ulong)

- ea: `0x180037480`
- end: `0x180037661`
- name: `?SetListOrder@PersistXmlStore@@UEAAJPEAPEAGK@Z`
- size: `481`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800064ae`
- `0x180035c24`
- `0x180035dd8`
- `0x180036f3c`
- `0x180037480`
- `0x180037d04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037504`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037504`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800374f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800374f7`
- `DMCmnUtils!InvStrCmpW` at `0x180037510`
- `DMCmnUtils!InvStrCmpW` at `0x180037510`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistXmlStore::SetListOrder(PersistXmlStore *this, unsigned __int16 **a2, unsigned int a3)
{
  __int64 v4; // rax
  void **v5; // r14
  __int64 v6; // r15
  __int64 v7; // r12
  const unsigned __int16 *v8; // rsi
  __int64 v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  const unsigned __int16 *v11; // rbx
  _QWORD *v13; // r8
  _BYTE *v14; // r15
  char *v15; // r12
  unsigned __int64 v16; // rbx
  char *v17; // rdi
  char *v18; // rdx
  size_t v19; // rbx
  unsigned int v20; // ebx
  unsigned __int64 v22; // r15
  __int128 Src; // [rsp+20h] [rbp-58h] BYREF
  __int64 v24; // [rsp+30h] [rbp-48h]
  unsigned int v25; // [rsp+80h] [rbp+8h]
  unsigned __int16 **v26; // [rsp+88h] [rbp+10h]
  unsigned int v27; // [rsp+90h] [rbp+18h]

  v27 = a3;
  v26 = a2;
  Src = 0;
  v24 = 0;
  v4 = 0;
  while ( 1 )
  {
    v25 = v4;
    v5 = (void **)((char *)this + 88);
    if ( (unsigned int)v4 >= a3 )
      break;
    v6 = (__int64)(*((_QWORD *)this + 12) - *((_QWORD *)this + 11)) >> 3;
    v7 = 0;
    while ( (unsigned int)v7 < (unsigned int)v6 )
    {
      v8 = a2[v4];
      v9 = *((_QWORD *)*v5 + v7);
      v10 = (struct _RTL_CRITICAL_SECTION *)(v9 + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 32));
      v11 = *(const unsigned __int16 **)(v9 + 24);
      LeaveCriticalSection(v10);
      if ( !InvStrCmpW(v11, v8) )
      {
        try
        {
          v13 = (char *)*v5 + 8 * (unsigned int)v7;
          if ( *((_QWORD *)&Src + 1) == v24 )
          {
            std::vector<PersistObject *>::_Emplace_reallocate<PersistObject * const &>(&Src, *((_QWORD *)&Src + 1), v13);
          }
          else
          {
            **((_QWORD **)&Src + 1) = *v13;
            *((_QWORD *)&Src + 1) += 8LL;
          }
          memmove_0(
            (char *)*v5 + 8 * (unsigned int)v7,
            (char *)*v5 + 8 * (unsigned int)v7 + 8,
            *((_QWORD *)this + 12) - ((_QWORD)*v5 + 8 * (unsigned int)v7 + 8));
          *((_QWORD *)this + 12) -= 8LL;
          LODWORD(v4) = v25;
          a2 = v26;
        }
        catch ( std::bad_alloc )
        {
          v20 = -2147024882;
          goto LABEL_20;
        }
        break;
      }
      v7 = (unsigned int)(v7 + 1);
      v4 = v25;
      a2 = v26;
    }
    v4 = (unsigned int)(v4 + 1);
    a3 = v27;
  }
  v14 = *v5;
  if ( *((_QWORD *)this + 11) == *((_QWORD *)this + 12) )
    v14 = (_BYTE *)*((_QWORD *)this + 12);
  else
    *((_QWORD *)this + 12) = v14;
  v15 = (char *)Src;
  v16 = (__int64)(*((_QWORD *)&Src + 1) - Src) >> 3;
  v17 = (char *)*v5;
  if ( v16 <= (__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 11)) >> 3 )
  {
    v22 = (v14 - v17) >> 3;
    if ( v16 > v22 )
    {
      memmove_0(*v5, (const void *)Src, 8 * v22);
      v17 = (char *)*((_QWORD *)this + 12);
      v16 -= v22;
      v18 = &v15[8 * v22];
      goto LABEL_19;
    }
  }
  else
  {
    std::vector<PersistObject *>::_Clear_and_reserve_geometric(
      (char *)this + 88,
      (__int64)(*((_QWORD *)&Src + 1) - Src) >> 3);
    v17 = (char *)*v5;
  }
  v18 = v15;
LABEL_19:
  v19 = 8 * v16;
  memmove_0(v17, v18, v19);
  *((_QWORD *)this + 12) = &v17[v19];
  v20 = PersistXmlStore::PersistAll(this);
LABEL_20:
  std::vector<PersistObject *>::~vector<PersistObject *>(&Src);
  return v20;
}

```

## disassembly

```asm
0x180037480  mov     rax, rsp
0x180037483  mov     [rax+18h], r8d
0x180037487  mov     [rax+10h], rdx
0x18003748b  push    rbx
0x18003748c  push    rsi
0x18003748d  push    rdi
0x18003748e  push    r12
0x180037490  push    r13
0x180037492  push    r14
0x180037494  push    r15
0x180037496  sub     rsp, 40h
0x18003749a  mov     r13, rcx
0x18003749d  xorps   xmm0, xmm0
0x1800374a0  movdqu  xmmword ptr [rax-58h], xmm0
0x1800374a5  mov     qword ptr [rax-48h], 0
0x1800374ad  xor     eax, eax
0x1800374af  mov     [rsp+78h+arg_0], eax
0x1800374b6  lea     r14, [r13+58h]
0x1800374ba  cmp     eax, r8d
0x1800374bd  jnb     loc_1800375AC
0x1800374c3  mov     r15, [r14+8]
0x1800374c7  sub     r15, [r14]
0x1800374ca  sar     r15, 3
0x1800374ce  xor     r12d, r12d
0x1800374d1  cmp     r12d, r15d
0x1800374d4  jnb     loc_18003759D
0x1800374da  mov     rsi, [rdx+rax*8]
0x1800374de  mov     ecx, r12d
0x1800374e1  mov     [rsp+78h+arg_18], rcx
0x1800374e9  mov     rax, [r14]
0x1800374ec  mov     rbx, [rax+r12*8]
0x1800374f0  lea     rdi, [rbx+20h]
0x1800374f4  mov     rcx, rdi; lpCriticalSection
0x1800374f7  call    cs:__imp_EnterCriticalSection
0x1800374fd  mov     rbx, [rbx+18h]
0x180037501  mov     rcx, rdi; lpCriticalSection
0x180037504  call    cs:__imp_LeaveCriticalSection
0x18003750a  mov     rdx, rsi
0x18003750d  mov     rcx, rbx
0x180037510  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180037516  test    eax, eax
0x180037518  jnz     short loc_180037586
0x18003751a  mov     rax, [r14]
0x18003751d  mov     rbx, [rsp+78h+arg_18]
0x180037525  lea     r8, [rax+rbx*8]
0x180037529  mov     rdx, [rsp+78h+var_50]
0x18003752e  cmp     rdx, [rsp+78h+var_48]
0x180037533  jz      short loc_180037543
0x180037535  mov     rax, [r8]
0x180037538  mov     [rdx], rax
0x18003753b  add     [rsp+78h+var_50], 8
0x180037541  jmp     short loc_18003754D
0x180037543  lea     rcx, [rsp+78h+Src]
0x180037548  call    ??$_Emplace_reallocate@AEBQEAVPersistObject@@@?$vector@PEAVPersistObject@@V?$allocator@PEAVPersistObject@@@std@@@std@@AEAAPEAPEAVPersistObject@@QEAPEAV2@AEBQEAV2@@Z; std::vector<PersistObject *>::_Emplace_reallocate<PersistObject * const &>(PersistObject * * const,PersistObject * const &)
0x18003754d  mov     rax, [r14]
0x180037550  lea     rcx, [rax+rbx*8]; void *
0x180037554  lea     rdx, [rcx+8]; Src
0x180037558  mov     r8, [r13+60h]
0x18003755c  sub     r8, rdx; Size
0x18003755f  call    memmove_0
0x180037564  add     qword ptr [r13+60h], 0FFFFFFFFFFFFFFF8h
0x180037569  mov     eax, [rsp+78h+arg_0]
0x180037570  mov     rdx, [rsp+78h+arg_8]
0x180037578  jmp     short loc_18003759D
0x18003757a  mov     ebx, [rsp+78h+arg_10]
0x180037581  jmp     loc_180037615
0x180037586  inc     r12d
0x180037589  mov     eax, [rsp+78h+arg_0]
0x180037590  mov     rdx, [rsp+78h+arg_8]
0x180037598  jmp     loc_1800374D1
0x18003759d  inc     eax
0x18003759f  mov     r8d, [rsp+78h+arg_10]
0x1800375a7  jmp     loc_1800374AF
0x1800375ac  mov     r15, [r14]
0x1800375af  cmp     r15, [r14+8]
0x1800375b3  jz      short loc_1800375BB
0x1800375b5  mov     [r14+8], r15
0x1800375b9  jmp     short loc_1800375BF
0x1800375bb  mov     r15, [r14+8]
0x1800375bf  mov     r12, [rsp+78h+Src]
0x1800375c4  mov     rbx, [rsp+78h+var_50]
0x1800375c9  sub     rbx, r12
0x1800375cc  sar     rbx, 3
0x1800375d0  mov     rdi, [r14]
0x1800375d3  mov     rax, [r14+10h]
0x1800375d7  sub     rax, rdi
0x1800375da  sar     rax, 3
0x1800375de  cmp     rbx, rax
0x1800375e1  jbe     short loc_180037631
0x1800375e3  mov     rdx, rbx
0x1800375e6  mov     rcx, r14
0x1800375e9  call    ?_Clear_and_reserve_geometric@?$vector@PEAVPersistObject@@V?$allocator@PEAVPersistObject@@@std@@@std@@AEAAX_K@Z; std::vector<PersistObject *>::_Clear_and_reserve_geometric(unsigned __int64)
0x1800375ee  mov     rdi, [r14]
0x1800375f1  mov     rdx, r12; Src
0x1800375f4  shl     rbx, 3
0x1800375f8  mov     r8, rbx; Size
0x1800375fb  mov     rcx, rdi; void *
0x1800375fe  call    memmove_0
0x180037603  lea     rax, [rbx+rdi]
0x180037607  mov     [r14+8], rax
0x18003760b  mov     rcx, r13; this
0x18003760e  call    ?PersistAll@PersistXmlStore@@AEAAJXZ; PersistXmlStore::PersistAll(void)
0x180037613  mov     ebx, eax
0x180037615  lea     rcx, [rsp+78h+Src]
0x18003761a  call    ??1?$vector@PEAVPersistObject@@V?$allocator@PEAVPersistObject@@@std@@@std@@QEAA@XZ; std::vector<PersistObject *>::~vector<PersistObject *>(void)
0x18003761f  mov     eax, ebx
0x180037621  add     rsp, 40h
0x180037625  pop     r15
0x180037627  pop     r14
0x180037629  pop     r13
0x18003762b  pop     r12
0x18003762d  pop     rdi
0x18003762e  pop     rsi
0x18003762f  pop     rbx
0x180037630  retn
0x180037631  sub     r15, rdi
0x180037634  sar     r15, 3
0x180037638  cmp     rbx, r15
0x18003763b  jbe     short loc_1800375F1
0x18003763d  lea     rsi, ds:0[r15*8]
0x180037645  mov     r8, rsi; Size
0x180037648  mov     rdx, r12; Src
0x18003764b  mov     rcx, rdi; void *
0x18003764e  call    memmove_0
0x180037653  mov     rdi, [r14+8]
0x180037657  sub     rbx, r15
0x18003765a  lea     rdx, [rsi+r12]
0x18003765e  jmp     short loc_1800375F4
```
