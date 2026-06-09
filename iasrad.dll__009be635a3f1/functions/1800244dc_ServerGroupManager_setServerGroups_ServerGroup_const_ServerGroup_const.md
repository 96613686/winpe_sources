# ServerGroupManager::setServerGroups(ServerGroup * const *,ServerGroup * const *)

- ea: `0x1800244dc`
- end: `0x1800248d8`
- name: `?setServerGroups@ServerGroupManager@@QEAA_NPEBQEAVServerGroup@@0@Z`
- size: `1020`
- prototype: `bool __fastcall(ServerGroupManager *__hidden this, struct ServerGroup *const *, struct ServerGroup *const *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001dad0`

## callees

- `0x18001d6c4`
- `0x18001d6e8`
- `0x18001da98`
- `0x18001fb5c`
- `0x18001fbb8`
- `0x1800212b8`
- `0x1800214f4`
- `0x180023ab8`
- `0x1800244dc`
- `0x180029d20`
- `0x180029ee4`

## import_xrefs

- `msvcrt!qsort` at `0x18002457d`
- `msvcrt!qsort` at `0x180024724`
- `msvcrt!qsort` at `0x180024770`
- `msvcrt!qsort` at `0x18002457d`
- `msvcrt!qsort` at `0x180024724`
- `msvcrt!qsort` at `0x180024770`
- `KERNEL32!GetCurrentThreadId` at `0x180024776`
- `KERNEL32!GetCurrentThreadId` at `0x180024875`
- `KERNEL32!GetCurrentThreadId` at `0x180024776`
- `KERNEL32!GetCurrentThreadId` at `0x180024875`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall ServerGroupManager::setServerGroups(
        ServerGroupManager *this,
        struct ServerGroup *const *a2,
        struct ServerGroup *const *a3)
{
  ServerGroupManager *v5; // r13
  struct ServerGroup *const *v6; // rcx
  struct ServerGroup **i; // r12
  struct ServerGroup *v8; // rax
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  struct ServerGroup *const *j; // r8
  __int64 k; // rdx
  unsigned int v13; // ecx
  __int64 v14; // r8
  __int64 *v15; // r13
  char *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // r14
  void *v20; // r15
  void *v21; // r14
  void *v22; // rdi
  void *v23; // rbx
  DWORD CurrentThreadId; // eax
  void *v25; // r8
  void *v26; // rdx
  __int64 v27; // rcx
  void *v28; // r8
  void *v29; // rdx
  __int64 v30; // rcx
  void *v31; // r8
  void *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rcx
  DWORD v37; // eax
  bool result; // al
  void *Base[2]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v40; // [rsp+30h] [rbp-78h]
  __int128 v41; // [rsp+38h] [rbp-70h] BYREF
  __int64 v42; // [rsp+48h] [rbp-60h]
  void *v43[2]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v44; // [rsp+60h] [rbp-48h]
  void *v45[2]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v46; // [rsp+78h] [rbp-30h]

  v5 = this;
  *(_OWORD *)Base = 0;
  v40 = 0;
  try
  {
    ((void (*)(void))ObjectVector<ServerGroup>::reserve)();
    ObjectVector<ServerGroup>::clear(Base);
    v6 = a2;
    for ( i = (struct ServerGroup **)Base[1]; v6 != a3; ++v6 )
    {
      v8 = *v6;
      *i++ = *v6;
      Base[1] = i;
      _InterlockedAdd((volatile signed __int32 *)v8, 1u);
    }
    qsort(Base[0], ((char *)i - (char *)Base[0]) >> 3, 8u, sortGroupsByName);
    v9 = 0;
    v10 = 0;
    for ( j = a2; j != a3; ++j )
    {
      for ( k = *((_QWORD *)*j + 1); k != *((_QWORD *)*j + 2); k += 8 )
      {
        ++v9;
        v13 = v10 + 1;
        if ( !*(_BYTE *)(*(_QWORD *)k + 380LL) )
          v13 = v10;
        v10 = v13;
      }
    }
    *(_OWORD *)v43 = 0;
    v44 = 0;
    ObjectVector<ServerGroup>::reserve(v43, v9, j);
    v41 = 0;
    v42 = 0;
    ObjectVector<ServerGroup>::reserve(&v41, v10, v14);
    if ( a2 != a3 )
    {
      do
      {
        v15 = (__int64 *)*((_QWORD *)*a2 + 1);
        if ( v15 != *((__int64 **)*a2 + 2) )
        {
          v16 = (char *)this + 144;
          do
          {
            v17 = *v15;
            v18 = ObjectVector<RemoteServer>::search(v16, *v15 + 12, findServerByGUID);
            v19 = v18;
            if ( v18 )
            {
              if ( (unsigned __int8)RemoteServer::operator==(v18, v17) )
              {
                v17 = v19;
              }
              else
              {
                *(_DWORD *)(v17 + 64) = *(_DWORD *)(v19 + 64);
                *(_DWORD *)(v17 + 216) = *(_DWORD *)(v19 + 216);
                *(_BYTE *)(v17 + 424) = *(_BYTE *)(v19 + 424);
                *(_BYTE *)(v17 + 425) = *(_BYTE *)(v19 + 425);
                *(_DWORD *)(v17 + 428) = *(_DWORD *)(v19 + 428);
                *(_QWORD *)(v17 + 432) = *(_QWORD *)(v19 + 432);
              }
            }
            ObjectVector<RemoteServer>::push_back(v43, v17);
            if ( *(_BYTE *)(v17 + 380) )
              ObjectVector<RemoteServer>::push_back(&v41, v17);
            ++v15;
            v16 = (char *)this + 144;
          }
          while ( v15 != *((__int64 **)*a2 + 2) );
        }
        ++a2;
      }
      while ( a2 != a3 );
      v5 = this;
    }
    v20 = v43[1];
    v21 = v43[0];
    qsort(v43[0], ((char *)v43[1] - (char *)v43[0]) >> 3, 8u, sortServersByAddress);
    *(_OWORD *)v45 = 0;
    v46 = 0;
    ObjectVector<RemoteServer>::assign(v45, v21, v20);
    v22 = v45[1];
    v23 = v45[0];
    qsort(v45[0], ((char *)v45[1] - (char *)v45[0]) >> 3, 8u, sortServersByGUID);
    CurrentThreadId = GetCurrentThreadId();
    Perimeter::LockExclusive(v5, CurrentThreadId);
    v25 = (void *)*((_QWORD *)v5 + 12);
    v26 = (void *)*((_QWORD *)v5 + 13);
    v27 = *((_QWORD *)v5 + 14);
    *((void **)v5 + 12) = Base[0];
    *((_QWORD *)v5 + 13) = i;
    *((_QWORD *)v5 + 14) = v40;
    Base[0] = v25;
    Base[1] = v26;
    v40 = v27;
    v28 = (void *)*((_QWORD *)v5 + 15);
    v29 = (void *)*((_QWORD *)v5 + 16);
    v30 = *((_QWORD *)v5 + 17);
    *((_QWORD *)v5 + 15) = v21;
    *((_QWORD *)v5 + 16) = v20;
    *((_QWORD *)v5 + 17) = v44;
    v43[0] = v28;
    v43[1] = v29;
    v44 = v30;
    v31 = (void *)*((_QWORD *)v5 + 18);
    v32 = (void *)*((_QWORD *)v5 + 19);
    v33 = *((_QWORD *)v5 + 20);
    *((_QWORD *)v5 + 18) = v23;
    *((_QWORD *)v5 + 19) = v22;
    *((_QWORD *)v5 + 20) = v46;
    v45[0] = v31;
    v45[1] = v32;
    v46 = v33;
    v34 = *((_QWORD *)v5 + 21);
    v35 = *((_QWORD *)v5 + 22);
    v36 = *((_QWORD *)v5 + 23);
    *(_OWORD *)((char *)v5 + 168) = v41;
    *((_QWORD *)v5 + 23) = v42;
    *(_QWORD *)&v41 = v34;
    *((_QWORD *)&v41 + 1) = v35;
    v42 = v36;
    v37 = GetCurrentThreadId();
    Perimeter::Unlock(v5, v37);
    ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(v45);
    ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(&v41);
    ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(v43);
    ObjectVector<ServerGroup>::~ObjectVector<ServerGroup>(Base);
    result = 1;
  }
  catch ( std::bad_alloc )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800244dc  mov     [rsp+arg_10], rbx
0x1800244e1  mov     [rsp+arg_0], rcx
0x1800244e6  push    rdi
0x1800244e7  push    r12
0x1800244e9  push    r13
0x1800244eb  push    r14
0x1800244ed  push    r15
0x1800244ef  sub     rsp, 80h
0x1800244f6  mov     r15, r8
0x1800244f9  mov     rdi, rdx
0x1800244fc  mov     r13, rcx
0x1800244ff  xorps   xmm0, xmm0
0x180024502  movdqu  xmmword ptr [rsp+0A8h+Base], xmm0
0x180024508  mov     [rsp+0A8h+var_78], 0
0x180024511  mov     rdx, r8
0x180024514  sub     rdx, rdi
0x180024517  sar     rdx, 3
0x18002451b  lea     rcx, [rsp+0A8h+Base]
0x180024520  call    ?reserve@?$ObjectVector@VServerGroup@@@@QEAAX_K@Z; ObjectVector<ServerGroup>::reserve(unsigned __int64)
0x180024525  lea     rcx, [rsp+0A8h+Base]
0x18002452a  call    ?clear@?$ObjectVector@VServerGroup@@@@QEAAXXZ; ObjectVector<ServerGroup>::clear(void)
0x18002452f  mov     rcx, rdi
0x180024532  mov     r14d, 1
0x180024538  mov     r12, [rsp+0A8h+Base+8]
0x18002453d  cmp     rdi, r15
0x180024540  jz      short loc_18002455F
0x180024542  mov     rax, [rcx]
0x180024545  mov     [r12], rax
0x180024549  add     r12, 8
0x18002454d  mov     [rsp+0A8h+Base+8], r12
0x180024552  lock add [rax], r14d
0x180024556  add     rcx, 8
0x18002455a  cmp     rcx, r15
0x18002455d  jnz     short loc_180024542
0x18002455f  mov     rdx, r12
0x180024562  sub     rdx, [rsp+0A8h+Base]
0x180024567  sar     rdx, 3; NumOfElements
0x18002456b  lea     r9, ?sortGroupsByName@@YAHPEBQEBVServerGroup@@0@Z; CompareFunction
0x180024572  mov     r8d, 8; SizeOfElements
0x180024578  mov     rcx, [rsp+0A8h+Base]; Base
0x18002457d  call    cs:__imp_qsort
0x180024583  xor     r9d, r9d
0x180024586  xor     ebx, ebx
0x180024588  mov     r8, rdi
0x18002458b  cmp     rdi, r15
0x18002458e  jz      short loc_1800245C4
0x180024590  mov     rax, [r8]
0x180024593  mov     r10, [rax+10h]
0x180024597  mov     rdx, [rax+8]
0x18002459b  jmp     short loc_1800245B6
0x18002459d  add     r9d, r14d
0x1800245a0  mov     rax, [rdx]
0x1800245a3  lea     ecx, [rbx+1]
0x1800245a6  cmp     byte ptr [rax+17Ch], 0
0x1800245ad  cmovz   ecx, ebx
0x1800245b0  mov     ebx, ecx
0x1800245b2  add     rdx, 8
0x1800245b6  cmp     rdx, r10
0x1800245b9  jnz     short loc_18002459D
0x1800245bb  add     r8, 8
0x1800245bf  cmp     r8, r15
0x1800245c2  jnz     short loc_180024590
0x1800245c4  xorps   xmm0, xmm0
0x1800245c7  movdqu  xmmword ptr [rsp+0A8h+var_58], xmm0
0x1800245cd  mov     [rsp+0A8h+var_48], 0
0x1800245d6  mov     edx, r9d
0x1800245d9  lea     rcx, [rsp+0A8h+var_58]
0x1800245de  call    ?reserve@?$ObjectVector@VServerGroup@@@@QEAAX_K@Z; ObjectVector<ServerGroup>::reserve(unsigned __int64)
0x1800245e3  nop
0x1800245e4  xorps   xmm0, xmm0
0x1800245e7  movdqu  [rsp+0A8h+var_70], xmm0
0x1800245ed  mov     [rsp+0A8h+var_60], 0
0x1800245f6  mov     edx, ebx
0x1800245f8  lea     rcx, [rsp+0A8h+var_70]
0x1800245fd  call    ?reserve@?$ObjectVector@VServerGroup@@@@QEAAX_K@Z; ObjectVector<ServerGroup>::reserve(unsigned __int64)
0x180024602  nop
0x180024603  cmp     rdi, r15
0x180024606  jz      loc_180024700
0x18002460c  mov     rax, [rdi]
0x18002460f  mov     r13, [rax+8]
0x180024613  cmp     r13, [rax+10h]
0x180024617  jz      loc_1800246EB
0x18002461d  mov     rax, [rsp+0A8h+arg_0]
0x180024625  add     rax, 90h
0x18002462b  mov     [rsp+0A8h+arg_8], rax
0x180024633  mov     rbx, [r13+0]
0x180024637  lea     rdx, [rbx+0Ch]
0x18002463b  lea     r8, ?findServerByGUID@@YAHPEBXPEBQEBVRemoteServer@@@Z; findServerByGUID(void const *,RemoteServer const * const *)
0x180024642  mov     rcx, rax
0x180024645  call    ?search@?$ObjectVector@VRemoteServer@@@@QEBAPEAVRemoteServer@@PEBXP6AH0PEBQEBV2@@_E@Z; ObjectVector<RemoteServer>::search(void const *,int (*)(void const *,RemoteServer const * const *),...)
0x18002464a  mov     r14, rax
0x18002464d  test    rax, rax
0x180024650  jz      short loc_1800246AF
0x180024652  mov     rdx, rbx
0x180024655  mov     rcx, rax
0x180024658  call    ??8RemoteServer@@QEBA_NAEBV0@@Z; RemoteServer::operator==(RemoteServer const &)
0x18002465d  test    al, al
0x18002465f  jz      short loc_180024666
0x180024661  mov     rbx, r14
0x180024664  jmp     short loc_1800246AF
0x180024666  mov     eax, [r14+40h]
0x18002466a  mov     [rbx+40h], eax
0x18002466d  mov     eax, [r14+0D8h]
0x180024674  mov     [rbx+0D8h], eax
0x18002467a  mov     al, [r14+1A8h]
0x180024681  mov     [rbx+1A8h], al
0x180024687  mov     al, [r14+1A9h]
0x18002468e  mov     [rbx+1A9h], al
0x180024694  mov     eax, [r14+1ACh]
0x18002469b  mov     [rbx+1ACh], eax
0x1800246a1  mov     rax, [r14+1B0h]
0x1800246a8  mov     [rbx+1B0h], rax
0x1800246af  mov     rdx, rbx
0x1800246b2  lea     rcx, [rsp+0A8h+var_58]
0x1800246b7  call    ?push_back@?$ObjectVector@VRemoteServer@@@@QEAAXPEAVRemoteServer@@@Z; ObjectVector<RemoteServer>::push_back(RemoteServer *)
0x1800246bc  cmp     byte ptr [rbx+17Ch], 0
0x1800246c3  jz      short loc_1800246D2
0x1800246c5  mov     rdx, rbx
0x1800246c8  lea     rcx, [rsp+0A8h+var_70]
0x1800246cd  call    ?push_back@?$ObjectVector@VRemoteServer@@@@QEAAXPEAVRemoteServer@@@Z; ObjectVector<RemoteServer>::push_back(RemoteServer *)
0x1800246d2  add     r13, 8
0x1800246d6  mov     rax, [rdi]
0x1800246d9  cmp     r13, [rax+10h]
0x1800246dd  mov     rax, [rsp+0A8h+arg_8]
0x1800246e5  jnz     loc_180024633
0x1800246eb  add     rdi, 8
0x1800246ef  cmp     rdi, r15
0x1800246f2  jnz     loc_18002460C
0x1800246f8  mov     r13, [rsp+0A8h+arg_0]
0x180024700  mov     r15, [rsp+0A8h+var_58+8]
0x180024705  mov     rdx, r15
0x180024708  mov     r14, [rsp+0A8h+var_58]
0x18002470d  sub     rdx, r14
0x180024710  sar     rdx, 3; NumOfElements
0x180024714  lea     r9, ?sortServersByAddress@@YAHPEBQEBVRemoteServer@@0@Z; CompareFunction
0x18002471b  mov     r8d, 8; SizeOfElements
0x180024721  mov     rcx, r14; Base
0x180024724  call    cs:__imp_qsort
0x18002472a  xorps   xmm0, xmm0
0x18002472d  movdqu  xmmword ptr [rsp+0A8h+var_40], xmm0
0x180024733  mov     [rsp+0A8h+var_30], 0
0x18002473c  mov     r8, r15
0x18002473f  mov     rdx, r14
0x180024742  lea     rcx, [rsp+0A8h+var_40]
0x180024747  call    ?assign@?$ObjectVector@VRemoteServer@@@@QEAAXPEBQEAVRemoteServer@@0@Z; ObjectVector<RemoteServer>::assign(RemoteServer * const *,RemoteServer * const *)
0x18002474c  mov     rdi, [rsp+0A8h+var_40+8]
0x180024751  mov     rdx, rdi
0x180024754  mov     rbx, [rsp+0A8h+var_40]
0x180024759  sub     rdx, rbx
0x18002475c  sar     rdx, 3; NumOfElements
0x180024760  lea     r9, ?sortServersByGUID@@YAHPEBQEBVRemoteServer@@0@Z; CompareFunction
0x180024767  mov     r8d, 8; SizeOfElements
0x18002476d  mov     rcx, rbx; Base
0x180024770  call    cs:__imp_qsort
0x180024776  call    cs:__imp_GetCurrentThreadId
0x18002477c  mov     edx, eax; unsigned int
0x18002477e  mov     rcx, r13; this
0x180024781  call    ?LockExclusive@Perimeter@@QEAAXK@Z; Perimeter::LockExclusive(ulong)
0x180024786  mov     r8, [r13+60h]
0x18002478a  mov     rdx, [r13+68h]
0x18002478e  mov     rcx, [r13+70h]
0x180024792  mov     rax, [rsp+0A8h+Base]
0x180024797  mov     [r13+60h], rax
0x18002479b  mov     [r13+68h], r12
0x18002479f  mov     rax, [rsp+0A8h+var_78]
0x1800247a4  mov     [r13+70h], rax
0x1800247a8  mov     [rsp+0A8h+Base], r8
0x1800247ad  mov     [rsp+0A8h+Base+8], rdx
0x1800247b2  mov     [rsp+0A8h+var_78], rcx
0x1800247b7  mov     r8, [r13+78h]
0x1800247bb  mov     rdx, [r13+80h]
0x1800247c2  mov     rcx, [r13+88h]
0x1800247c9  mov     [r13+78h], r14
0x1800247cd  mov     [r13+80h], r15
0x1800247d4  mov     rax, [rsp+0A8h+var_48]
0x1800247d9  mov     [r13+88h], rax
0x1800247e0  mov     [rsp+0A8h+var_58], r8
0x1800247e5  mov     [rsp+0A8h+var_58+8], rdx
0x1800247ea  mov     [rsp+0A8h+var_48], rcx
0x1800247ef  mov     r8, [r13+90h]
0x1800247f6  mov     rdx, [r13+98h]
0x1800247fd  mov     rcx, [r13+0A0h]
0x180024804  mov     [r13+90h], rbx
0x18002480b  mov     [r13+98h], rdi
0x180024812  mov     rax, [rsp+0A8h+var_30]
0x180024817  mov     [r13+0A0h], rax
0x18002481e  mov     [rsp+0A8h+var_40], r8
0x180024823  mov     [rsp+0A8h+var_40+8], rdx
0x180024828  mov     [rsp+0A8h+var_30], rcx
0x18002482d  mov     r8, [r13+0A8h]
0x180024834  mov     rdx, [r13+0B0h]
0x18002483b  mov     rcx, [r13+0B8h]
0x180024842  mov     rax, qword ptr [rsp+0A8h+var_70]
0x180024847  mov     [r13+0A8h], rax
0x18002484e  mov     rax, qword ptr [rsp+0A8h+var_70+8]
0x180024853  mov     [r13+0B0h], rax
0x18002485a  mov     rax, [rsp+0A8h+var_60]
0x18002485f  mov     [r13+0B8h], rax
0x180024866  mov     qword ptr [rsp+0A8h+var_70], r8
0x18002486b  mov     qword ptr [rsp+0A8h+var_70+8], rdx
0x180024870  mov     [rsp+0A8h+var_60], rcx
0x180024875  call    cs:__imp_GetCurrentThreadId
0x18002487b  mov     edx, eax; unsigned int
0x18002487d  mov     rcx, r13; this
0x180024880  call    ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
0x180024885  lea     rcx, [rsp+0A8h+var_40]
0x18002488a  call    ??1?$ObjectVector@VRemoteServer@@@@QEAA@XZ; ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(void)
0x18002488f  nop
0x180024890  lea     rcx, [rsp+0A8h+var_70]
0x180024895  call    ??1?$ObjectVector@VRemoteServer@@@@QEAA@XZ; ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(void)
0x18002489a  nop
0x18002489b  lea     rcx, [rsp+0A8h+var_58]
0x1800248a0  call    ??1?$ObjectVector@VRemoteServer@@@@QEAA@XZ; ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(void)
0x1800248a5  nop
0x1800248a6  lea     rcx, [rsp+0A8h+Base]
0x1800248ab  call    ??1?$ObjectVector@VServerGroup@@@@QEAA@XZ; ObjectVector<ServerGroup>::~ObjectVector<ServerGroup>(void)
0x1800248b0  nop
0x1800248b1  mov     eax, 1
0x1800248b6  jmp     short loc_1800248BF
0x1800248b8  mov     al, byte ptr [rsp+0A8h+arg_8]
0x1800248bf  mov     rbx, [rsp+0A8h+arg_10]
0x1800248c7  add     rsp, 80h
0x1800248ce  pop     r15
0x1800248d0  pop     r14
0x1800248d2  pop     r13
0x1800248d4  pop     r12
0x1800248d6  pop     rdi
0x1800248d7  retn
```
