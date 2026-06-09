# CmsVolumeContainer::PersistContainerCacheWorker(CmsTransactionContext *,SmsPersistContainerCacheWorkerInfo *)

- ea: `0x1c002d3a4`
- end: `0x1c002d96b`
- name: `?PersistContainerCacheWorker@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsPersistContainerCacheWorkerInfo@@@Z`
- size: `1479`
- prototype: `__int64 __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsPersistContainerCacheWorkerInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c005cf30`

## callees

- `0x1c0014760`
- `0x1c002bca4`
- `0x1c002d228`
- `0x1c002d3a4`
- `0x1c00538e8`
- `0x1c006a644`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00d75fc`
- `0x1c00fbb44`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c002d813`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002d813`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c002d4ca`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c002d4ca`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c002d541`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c002d541`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c002d52a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c002d52a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c002d83b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c002d83b`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::PersistContainerCacheWorker(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        struct SmsPersistContainerCacheWorkerInfo *a3)
{
  char v3; // r14
  unsigned int v4; // r13d
  char v5; // bp
  unsigned int v7; // edx
  __int64 v9; // rbx
  __int64 v10; // rcx
  ULONG_PTR v11; // r12
  unsigned __int8 v12; // al
  int v13; // eax
  char v14; // bp
  char v15; // al
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // r8
  int v19; // edx
  struct SmsContainer *v20; // rbx
  unsigned __int64 v21; // rdx
  _DWORD *v22; // r15
  int v23; // eax
  _BYTE *v24; // r14
  int v25; // r9d
  char *v26; // rdx
  __int64 v27; // rbx
  unsigned int v28; // eax
  bool v29; // zf
  __int64 *i; // rax
  __int64 v31; // rcx
  int v32; // eax
  CmsIntegrityState *v33; // rcx
  int v35; // [rsp+40h] [rbp-48h]
  struct SmsContainer *v36; // [rsp+48h] [rbp-40h] BYREF
  char v37; // [rsp+90h] [rbp+8h]
  unsigned int v38; // [rsp+A0h] [rbp+18h]
  char v39; // [rsp+A8h] [rbp+20h]

  v3 = *((_BYTE *)a3 + 88);
  v4 = *((_DWORD *)a3 + 20);
  v5 = 0;
  v39 = 0;
  v7 = *((_DWORD *)a3 + 21);
  v35 = 0;
  v38 = v7;
  v37 = v3;
LABEL_37:
  LODWORD(v18) = 1;
  while ( 1 )
  {
LABEL_2:
    v9 = 0;
    if ( v4 < v7 )
    {
      v10 = 8LL * v4;
      do
      {
        if ( v9 )
          break;
        v4 += v18;
        v9 = *(_QWORD *)(v10 + *((_QWORD *)this + 45));
        v10 += 8;
      }
      while ( v4 < v7 );
    }
    v36 = (struct SmsContainer *)v9;
    if ( !v9 )
    {
      v19 = v35;
      goto LABEL_94;
    }
    v11 = *(_QWORD *)(v9 + 552);
    if ( v3 )
    {
      if ( !*(_DWORD *)(v9 + 88) && !*(_DWORD *)(v9 + 84) )
      {
        v12 = *(_BYTE *)(v9 + 24);
        if ( (v12 & 0x20) == 0
          && (v12 & 4) == 0
          && !*(_DWORD *)(v9 + 96)
          && !*(_DWORD *)(v9 + 100)
          && (v12 & (unsigned __int8)v18) == 0
          && (v12 & 2) == 0
          && (v12 & 0x10) == 0
          && (*(_BYTE *)(v9 + 25) & 4) == 0 )
        {
          v13 = *(_DWORD *)(v9 + 572);
          if ( ((unsigned __int8)v13 & (unsigned __int8)v18) == 0 && (v13 & 0x200) == 0 )
          {
            *(_DWORD *)(v9 + 92) += v18;
            if ( *(int *)(v9 + 92) >= 10 )
            {
              v14 = 0;
              ExAcquireAutoExpandPushLockExclusive(*((_QWORD *)this + 7), 0);
              if ( !*(_DWORD *)(v9 + 88) && !*(_DWORD *)(v9 + 84) )
              {
                v15 = *(_BYTE *)(v9 + 24);
                if ( (v15 & 0x20) == 0
                  && (v15 & 4) == 0
                  && !*(_DWORD *)(v9 + 96)
                  && !*(_DWORD *)(v9 + 100)
                  && (v15 & 1) == 0
                  && (v15 & 2) == 0
                  && (v15 & 0x10) == 0
                  && (*(_BYTE *)(v9 + 25) & 4) == 0 )
                {
                  v16 = *(_DWORD *)(v9 + 572);
                  if ( (v16 & 1) == 0 && (v16 & 0x200) == 0 )
                  {
                    RtlRemoveEntryHashTable(
                      *((PRTL_DYNAMIC_HASH_TABLE *)this + 6),
                      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v9,
                      0);
                    v14 = 1;
                  }
                }
              }
              ExReleaseAutoExpandPushLockExclusive(*((_QWORD *)this + 7), 0);
              if ( v14 )
              {
                v17 = v4 - 1;
                *(_QWORD *)(*((_QWORD *)this + 45) + 8 * v17) = 0;
                SmsContainer::`scalar deleting destructor'((PVOID)v9, v17);
                v5 = v39;
LABEL_36:
                v7 = v38;
                goto LABEL_37;
              }
              v5 = v39;
              LOBYTE(v18) = 1;
            }
          }
        }
      }
    }
    v35 = CmsVolumeContainer::PinContainer((PRTL_DYNAMIC_HASH_TABLE *)this, a2, v11, &v36, 0, v18, v18);
    v19 = v35;
    if ( v35 < 0 )
      break;
    v20 = v36;
    v21 = *((_QWORD *)v36 + 73);
    if ( !v3 )
    {
      if ( v21 && (*((_BYTE *)v36 + 24) & 2) == 0
        || (*((_DWORD *)v36 + 143) & 8) == 0
        || *((_DWORD *)v36 + 21)
        || (*(_DWORD *)(*((_QWORD *)this + 1) + 3116LL) & 0x400) != 0 )
      {
        v32 = *((_DWORD *)v36 + 143);
        if ( (v32 & 0x100) != 0 && !v21 && (v32 & 8) == 0 )
        {
          v33 = *(CmsIntegrityState **)(*((_QWORD *)this + 1) + 3056LL);
          if ( !*((_BYTE *)v33 + 16)
            || (int)CmsIntegrityState::ResetIntegrityState(
                      v33,
                      a2,
                      (struct SmsContainer *)((char *)v36
                                            + (unsigned int)(*((_DWORD *)this + 58) * *((_DWORD *)this + 57))
                                            + 632)) >= 0 )
          {
            memset((char *)v20 + 632, 0, (unsigned int)(*((_DWORD *)this + 58) * *((_DWORD *)this + 57)));
            *((_DWORD *)v20 + 143) &= ~0x100u;
            *((_BYTE *)v20 + 24) |= 1u;
          }
        }
        CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
      }
      else
      {
        CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
        CmsVolumeContainer::DeleteContainer(this, a2, v11);
      }
      goto LABEL_36;
    }
    if ( v21 && (*((_BYTE *)v36 + 24) & 2) == 0 )
    {
      LODWORD(v18) = 1;
    }
    else
    {
      LODWORD(v18) = 1;
      if ( (*((_DWORD *)v36 + 143) & 8) != 0 )
      {
        if ( !*((_DWORD *)v36 + 21) )
          v5 = 1;
        v39 = v5;
      }
    }
    v22 = (_DWORD *)((char *)v36 + 572);
    v23 = *((_DWORD *)v36 + 143);
    if ( (v23 & 0x100) != 0 && !v21 )
    {
      if ( (v23 & 8) == 0 )
        v5 = 1;
      v39 = v5;
    }
    v24 = (char *)v36 + 24;
    if ( (*((_BYTE *)v36 + 24) & 0x20) != 0 && *((_QWORD *)v36 + 4) <= *(_QWORD *)(*((_QWORD *)this + 1) + 1840LL) )
    {
      *((_DWORD *)v36 + 153) = 0;
      *v24 = *v24 & 0xDE | 1;
      SmsContainer::LogActivity(v20, 11, *(_QWORD *)(*((_QWORD *)this + 1) + 1840LL), 0);
      _InterlockedDecrement((volatile signed __int32 *)this + 76);
      _InterlockedExchangeAdd64(
        (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3400LL),
        *(unsigned int *)(*((_QWORD *)this + 1) + 80LL));
      v18 = (unsigned int)(v25 + 1);
      _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)this + 1) + 3384LL), v18);
      _InterlockedExchangeAdd64(
        (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3416LL),
        -*(_DWORD *)(*((_QWORD *)this + 1) + 80LL));
      v21 = *((_QWORD *)v20 + 73);
      v20 = v36;
    }
    if ( v21 < *((_QWORD *)v20 + 74) )
      *((_QWORD *)v20 + 74) = v21;
    if ( ((unsigned __int8)v18 & *v24) == 0 )
    {
      v26 = (char *)a2 + 2776;
      v27 = 0;
      v28 = 0;
      while ( !*(_QWORD *)v26 || *(_QWORD *)(*(_QWORD *)v26 + 552LL) != v11 )
      {
        v28 += v18;
        v26 += 8;
        v29 = v28 == 4;
        if ( v28 >= 4 )
          goto LABEL_70;
      }
      v3 = v37;
      v27 = *(_QWORD *)v26;
      v7 = v38;
      v29 = (*((_DWORD *)a2 + v28 + 702))-- == 1;
      if ( !v29 )
        continue;
      *((_QWORD *)a2 + v28 + 347) = 0;
      v29 = v28 == 4;
LABEL_70:
      if ( v29 )
      {
        for ( i = (__int64 *)*((_QWORD *)a2 + 328); i; i = (__int64 *)*i )
        {
          v31 = i[1];
          if ( v31 && *(_QWORD *)(v31 + 552) == v11 )
          {
            v29 = (*((_DWORD *)i + 4))-- == 1;
            v27 = v31;
            v3 = v37;
            v7 = v38;
            if ( !v29 )
              goto LABEL_2;
            i[1] = 0;
            break;
          }
        }
      }
      ExReleasePushLockEx(v27 + 104, 2);
      --*((_DWORD *)a2 + 707);
      _InterlockedDecrement((volatile signed __int32 *)(v27 + 88));
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 328), 0, 0x20u);
      --*((_DWORD *)a2 + 706);
      v3 = v37;
      goto LABEL_36;
    }
    CmsVolumeContainer::UnpinContainer(this, a2, v11, 0);
    v3 = v37;
    v19 = CmsVolumeContainer::PersistContainer(this, a2, v11);
    v35 = v19;
    LODWORD(v18) = 1;
    if ( v19 < 0 )
      goto LABEL_94;
    v7 = v38;
    if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 3056LL) + 16LL) && (*v22 & 8) == 0 )
    {
      memmove(*((void **)v20 + 68), (char *)v20 + 632, (unsigned int)(*((_DWORD *)this + 57) * *((_DWORD *)this + 58)));
      goto LABEL_36;
    }
  }
  LOBYTE(v18) = 1;
LABEL_94:
  if ( v3 && v5 )
    *((_BYTE *)this + 121) = v18;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1c002d3a4  mov     [rsp+arg_8], rbx
0x1c002d3a9  push    rbp
0x1c002d3aa  push    rsi
0x1c002d3ab  push    rdi
0x1c002d3ac  push    r12
0x1c002d3ae  push    r13
0x1c002d3b0  push    r14
0x1c002d3b2  push    r15
0x1c002d3b4  sub     rsp, 50h
0x1c002d3b8  mov     r14b, [r8+58h]
0x1c002d3bc  xor     r15d, r15d
0x1c002d3bf  mov     r13d, [r8+50h]
0x1c002d3c3  mov     bpl, r15b
0x1c002d3c6  mov     rsi, rdx
0x1c002d3c9  mov     [rsp+88h+arg_18], ebp
0x1c002d3d0  mov     edx, [r8+54h]
0x1c002d3d4  mov     rdi, rcx
0x1c002d3d7  mov     [rsp+88h+var_48], r15d
0x1c002d3dc  mov     [rsp+88h+arg_10], edx
0x1c002d3e3  mov     [rsp+88h+arg_0], r14b
0x1c002d3eb  jmp     loc_1C002D577
0x1c002d3f0  xor     r15d, r15d
0x1c002d3f3  mov     rbx, r15
0x1c002d3f6  cmp     r13d, edx
0x1c002d3f9  jnb     short loc_1C002D41E
0x1c002d3fb  mov     ecx, r13d
0x1c002d3fe  shl     rcx, 3
0x1c002d402  test    rbx, rbx
0x1c002d405  jnz     short loc_1C002D41E
0x1c002d407  mov     rax, [rdi+168h]
0x1c002d40e  add     r13d, r8d
0x1c002d411  mov     rbx, [rcx+rax]
0x1c002d415  add     rcx, 8
0x1c002d419  cmp     r13d, edx
0x1c002d41c  jb      short loc_1C002D402
0x1c002d41e  mov     [rsp+88h+var_40], rbx
0x1c002d423  test    rbx, rbx
0x1c002d426  jz      loc_1C002D936
0x1c002d42c  mov     r12, [rbx+228h]
0x1c002d433  test    r14b, r14b
0x1c002d436  jz      loc_1C002D58F
0x1c002d43c  cmp     [rbx+58h], r15d
0x1c002d440  jnz     loc_1C002D58F
0x1c002d446  cmp     [rbx+54h], r15d
0x1c002d44a  jnz     loc_1C002D58F
0x1c002d450  mov     al, [rbx+18h]
0x1c002d453  test    al, 20h
0x1c002d455  jnz     loc_1C002D58F
0x1c002d45b  test    al, 4
0x1c002d45d  jnz     loc_1C002D58F
0x1c002d463  cmp     [rbx+60h], r15d
0x1c002d467  jnz     loc_1C002D58F
0x1c002d46d  cmp     [rbx+64h], r15d
0x1c002d471  jnz     loc_1C002D58F
0x1c002d477  test    r8b, al
0x1c002d47a  jnz     loc_1C002D58F
0x1c002d480  test    al, 2
0x1c002d482  jnz     loc_1C002D58F
0x1c002d488  test    al, 10h
0x1c002d48a  jnz     loc_1C002D58F
0x1c002d490  test    byte ptr [rbx+19h], 4
0x1c002d494  jnz     loc_1C002D58F
0x1c002d49a  mov     eax, [rbx+23Ch]
0x1c002d4a0  test    r8b, al
0x1c002d4a3  jnz     loc_1C002D58F
0x1c002d4a9  bt      eax, 9
0x1c002d4ad  jb      loc_1C002D58F
0x1c002d4b3  add     [rbx+5Ch], r8d
0x1c002d4b7  cmp     dword ptr [rbx+5Ch], 0Ah
0x1c002d4bb  jl      loc_1C002D58F
0x1c002d4c1  mov     rcx, [rdi+38h]
0x1c002d4c5  xor     edx, edx
0x1c002d4c7  mov     bpl, r15b
0x1c002d4ca  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x1c002d4d1  nop     dword ptr [rax+rax+00h]
0x1c002d4d6  cmp     [rbx+58h], r15d
0x1c002d4da  jnz     short loc_1C002D53B
0x1c002d4dc  cmp     [rbx+54h], r15d
0x1c002d4e0  jnz     short loc_1C002D53B
0x1c002d4e2  mov     al, [rbx+18h]
0x1c002d4e5  test    al, 20h
0x1c002d4e7  jnz     short loc_1C002D53B
0x1c002d4e9  test    al, 4
0x1c002d4eb  jnz     short loc_1C002D53B
0x1c002d4ed  cmp     [rbx+60h], r15d
0x1c002d4f1  jnz     short loc_1C002D53B
0x1c002d4f3  cmp     [rbx+64h], r15d
0x1c002d4f7  jnz     short loc_1C002D53B
0x1c002d4f9  mov     ecx, 1
0x1c002d4fe  test    cl, al
0x1c002d500  jnz     short loc_1C002D53B
0x1c002d502  test    al, 2
0x1c002d504  jnz     short loc_1C002D53B
0x1c002d506  test    al, 10h
0x1c002d508  jnz     short loc_1C002D53B
0x1c002d50a  test    byte ptr [rbx+19h], 4
0x1c002d50e  jnz     short loc_1C002D53B
0x1c002d510  mov     eax, [rbx+23Ch]
0x1c002d516  test    cl, al
0x1c002d518  jnz     short loc_1C002D53B
0x1c002d51a  bt      eax, 9
0x1c002d51e  jb      short loc_1C002D53B
0x1c002d520  mov     rcx, [rdi+30h]; HashTable
0x1c002d524  xor     r8d, r8d; Context
0x1c002d527  mov     rdx, rbx; Entry
0x1c002d52a  call    cs:__imp_RtlRemoveEntryHashTable
0x1c002d531  nop     dword ptr [rax+rax+00h]
0x1c002d536  mov     ebp, 1
0x1c002d53b  mov     rcx, [rdi+38h]
0x1c002d53f  xor     edx, edx
0x1c002d541  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1c002d548  nop     dword ptr [rax+rax+00h]
0x1c002d54d  test    bpl, bpl
0x1c002d550  jz      short loc_1C002D582
0x1c002d552  mov     rax, [rdi+168h]
0x1c002d559  lea     edx, [r13-1]; unsigned int
0x1c002d55d  mov     rcx, rbx; P
0x1c002d560  mov     [rax+rdx*8], r15
0x1c002d564  call    ??_GSmsContainer@@QEAAPEAXI@Z; SmsContainer::`scalar deleting destructor'(uint)
0x1c002d569  mov     ebp, [rsp+88h+arg_18]
0x1c002d570  mov     edx, [rsp+88h+arg_10]
0x1c002d577  mov     r8d, 1
0x1c002d57d  jmp     loc_1C002D3F3
0x1c002d582  mov     ebp, [rsp+88h+arg_18]
0x1c002d589  mov     r8d, 1
0x1c002d58f  mov     [rsp+88h+var_58], r8b; unsigned __int8
0x1c002d594  lea     r9, [rsp+88h+var_40]; struct SmsContainer **
0x1c002d599  mov     [rsp+88h+var_60], r8b; unsigned __int8
0x1c002d59e  mov     rdx, rsi; struct CmsTransactionContext *
0x1c002d5a1  mov     r8, r12; unsigned __int64
0x1c002d5a4  mov     [rsp+88h+var_68], r15; struct _SmsContainerOverflowPinList *
0x1c002d5a9  mov     rcx, rdi; this
0x1c002d5ac  call    ?PinContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@PEAU_SmsContainerOverflowPinList@@EE@Z; CmsVolumeContainer::PinContainer(CmsTransactionContext *,unsigned __int64,SmsContainer * *,_SmsContainerOverflowPinList *,uchar,uchar)
0x1c002d5b1  mov     [rsp+88h+var_48], eax
0x1c002d5b5  mov     edx, eax
0x1c002d5b7  test    eax, eax
0x1c002d5b9  js      loc_1C002D93C
0x1c002d5bf  mov     rbx, [rsp+88h+var_40]
0x1c002d5c4  mov     rdx, [rbx+248h]
0x1c002d5cb  test    r14b, r14b
0x1c002d5ce  jz      loc_1C002D85B
0x1c002d5d4  test    rdx, rdx
0x1c002d5d7  jz      short loc_1C002D5DF
0x1c002d5d9  test    byte ptr [rbx+18h], 2
0x1c002d5dd  jz      short loc_1C002D604
0x1c002d5df  mov     eax, [rbx+23Ch]
0x1c002d5e5  mov     r8d, 1
0x1c002d5eb  test    al, 8
0x1c002d5ed  jz      short loc_1C002D60A
0x1c002d5ef  cmp     [rbx+54h], r15d
0x1c002d5f3  movzx   ebp, bpl
0x1c002d5f7  cmovz   ebp, r8d
0x1c002d5fb  mov     [rsp+88h+arg_18], ebp
0x1c002d602  jmp     short loc_1C002D60A
0x1c002d604  mov     r8d, 1
0x1c002d60a  lea     r15, [rbx+23Ch]
0x1c002d611  mov     eax, [r15]
0x1c002d614  bt      eax, 8
0x1c002d618  jnb     short loc_1C002D630
0x1c002d61a  test    rdx, rdx
0x1c002d61d  jnz     short loc_1C002D630
0x1c002d61f  test    al, 8
0x1c002d621  movzx   ebp, bpl
0x1c002d625  cmovz   ebp, r8d
0x1c002d629  mov     [rsp+88h+arg_18], ebp
0x1c002d630  lea     r14, [rbx+18h]
0x1c002d634  test    byte ptr [r14], 20h
0x1c002d638  jz      loc_1C002D6C3
0x1c002d63e  mov     rax, [rdi+8]
0x1c002d642  mov     rcx, [rax+730h]
0x1c002d649  cmp     [rbx+20h], rcx
0x1c002d64d  jg      short loc_1C002D6C3
0x1c002d64f  and     dword ptr [rbx+264h], 0
0x1c002d656  xor     r9d, r9d
0x1c002d659  mov     al, [r14]
0x1c002d65c  mov     rcx, rbx
0x1c002d65f  and     al, 0DFh
0x1c002d661  or      al, r8b
0x1c002d664  mov     [r14], al
0x1c002d667  lea     edx, [r9+0Bh]
0x1c002d66b  mov     r8, [rdi+8]
0x1c002d66f  mov     r8, [r8+730h]
0x1c002d676  call    ?LogActivity@SmsContainer@@QEAAXW4EMS_BAND_ACTIVITY@@_K1@Z; SmsContainer::LogActivity(EMS_BAND_ACTIVITY,unsigned __int64,unsigned __int64)
0x1c002d67b  lock dec dword ptr [rdi+130h]
0x1c002d682  mov     rcx, [rdi+8]
0x1c002d686  mov     eax, [rcx+50h]
0x1c002d689  lock xadd [rcx+0D48h], rax
0x1c002d692  mov     rcx, [rdi+8]
0x1c002d696  lea     r8d, [r9+1]
0x1c002d69a  lock add [rcx+0D38h], r8
0x1c002d6a2  mov     rdx, [rdi+8]
0x1c002d6a6  mov     eax, [rdx+50h]
0x1c002d6a9  neg     eax
0x1c002d6ab  movsxd  rcx, eax
0x1c002d6ae  lock xadd [rdx+0D58h], rcx
0x1c002d6b7  mov     rdx, [rbx+248h]
0x1c002d6be  mov     rbx, [rsp+88h+var_40]
0x1c002d6c3  cmp     rdx, [rbx+250h]
0x1c002d6ca  jnb     short loc_1C002D6D3
0x1c002d6cc  mov     [rbx+250h], rdx
0x1c002d6d3  test    [r14], r8b
0x1c002d6d6  jz      loc_1C002D769
0x1c002d6dc  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1c002d6df  mov     r8, r12; unsigned __int64
0x1c002d6e2  mov     rdx, rsi; struct CmsTransactionContext *
0x1c002d6e5  mov     rcx, rdi; this
0x1c002d6e8  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x1c002d6ed  mov     r8, r12; unsigned __int64
0x1c002d6f0  mov     rdx, rsi; struct CmsTransactionContext *
0x1c002d6f3  mov     rcx, rdi; this
0x1c002d6f6  call    ?PersistContainer@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@_K@Z; CmsVolumeContainer::PersistContainer(CmsTransactionContext *,unsigned __int64)
0x1c002d6fb  mov     r14b, [rsp+88h+arg_0]
0x1c002d703  mov     edx, eax
0x1c002d705  mov     [rsp+88h+var_48], eax
0x1c002d709  mov     r8d, 1
0x1c002d70f  test    eax, eax
0x1c002d711  js      loc_1C002D942
0x1c002d717  mov     rax, [rdi+8]
0x1c002d71b  mov     edx, [rsp+88h+arg_10]
0x1c002d722  mov     rcx, [rax+0BF0h]
0x1c002d729  cmp     byte ptr [rcx+10h], 0
0x1c002d72d  jz      loc_1C002D3F0
0x1c002d733  mov     eax, [r15]
0x1c002d736  lea     r15d, [r8-1]
0x1c002d73a  test    al, 8
0x1c002d73c  jnz     loc_1C002D3F3
0x1c002d742  mov     r8d, [rdi+0E8h]
0x1c002d749  lea     rdx, [rbx+278h]; Src
0x1c002d750  imul    r8d, [rdi+0E4h]; Size
0x1c002d758  mov     rcx, [rbx+220h]; void *
0x1c002d75f  call    memmove
0x1c002d764  jmp     loc_1C002D570
0x1c002d769  xor     r15d, r15d
0x1c002d76c  lea     rdx, [rsi+0AD8h]
0x1c002d773  mov     ebx, r15d
0x1c002d776  mov     eax, r15d
0x1c002d779  mov     rcx, [rdx]
0x1c002d77c  test    rcx, rcx
0x1c002d77f  jz      short loc_1C002D78A
0x1c002d781  cmp     [rcx+228h], r12
0x1c002d788  jz      short loc_1C002D798
0x1c002d78a  add     eax, r8d
0x1c002d78d  add     rdx, 8
0x1c002d791  cmp     eax, 4
0x1c002d794  jnb     short loc_1C002D7C5
0x1c002d796  jmp     short loc_1C002D779
0x1c002d798  mov     r14b, [rsp+88h+arg_0]
0x1c002d7a0  mov     rbx, rcx
0x1c002d7a3  mov     edx, [rsp+88h+arg_10]
0x1c002d7aa  mov     ecx, eax
0x1c002d7ac  add     dword ptr [rsi+rcx*4+0AF8h], 0FFFFFFFFh
0x1c002d7b4  jnz     loc_1C002D3F3
0x1c002d7ba  mov     [rsi+rcx*8+0AD8h], r15
0x1c002d7c2  cmp     eax, 4
0x1c002d7c5  jnz     short loc_1C002D80A
0x1c002d7c7  mov     rax, [rsi+0A40h]
0x1c002d7ce  test    rax, rax
0x1c002d7d1  jz      short loc_1C002D80A
0x1c002d7d3  mov     rcx, [rax+8]
0x1c002d7d7  test    rcx, rcx
0x1c002d7da  jz      short loc_1C002D7E5
0x1c002d7dc  cmp     [rcx+228h], r12
0x1c002d7e3  jz      short loc_1C002D7EA
0x1c002d7e5  mov     rax, [rax]
0x1c002d7e8  jmp     short loc_1C002D7CE
0x1c002d7ea  add     dword ptr [rax+10h], 0FFFFFFFFh
0x1c002d7ee  mov     rbx, rcx
0x1c002d7f1  mov     r14b, [rsp+88h+arg_0]
0x1c002d7f9  mov     edx, [rsp+88h+arg_10]
0x1c002d800  jnz     loc_1C002D3F3
0x1c002d806  mov     [rax+8], r15
0x1c002d80a  lea     rcx, [rbx+68h]
0x1c002d80e  mov     edx, 2
0x1c002d813  call    cs:__imp_ExReleasePushLockEx
0x1c002d81a  nop     dword ptr [rax+rax+00h]
0x1c002d81f  xor     edx, edx; Tag
0x1c002d821  lea     rcx, [rdi+148h]; RemoveLock
0x1c002d828  or      r14d, 0FFFFFFFFh
0x1c002d82c  add     [rsi+0B0Ch], r14d
0x1c002d833  lock dec dword ptr [rbx+58h]
0x1c002d837  lea     r8d, [rdx+20h]; RemlockSize
0x1c002d83b  call    cs:__imp_IoReleaseRemoveLockEx
0x1c002d842  nop     dword ptr [rax+rax+00h]
0x1c002d847  add     [rsi+0B08h], r14d
0x1c002d84e  mov     r14b, [rsp+88h+arg_0]
0x1c002d856  jmp     loc_1C002D570
0x1c002d85b  test    rdx, rdx
0x1c002d85e  jz      short loc_1C002D866
0x1c002d860  test    byte ptr [rbx+18h], 2
0x1c002d864  jz      short loc_1C002D8AA
0x1c002d866  mov     eax, [rbx+23Ch]
0x1c002d86c  test    al, 8
0x1c002d86e  jz      short loc_1C002D8AA
0x1c002d870  cmp     [rbx+54h], r15d
0x1c002d874  jnz     short loc_1C002D8AA
0x1c002d876  mov     rax, [rdi+8]
0x1c002d87a  test    dword ptr [rax+0C2Ch], 400h
0x1c002d884  jnz     short loc_1C002D8AA
0x1c002d886  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1c002d889  mov     r8, r12; unsigned __int64
  ... truncated ...
```
