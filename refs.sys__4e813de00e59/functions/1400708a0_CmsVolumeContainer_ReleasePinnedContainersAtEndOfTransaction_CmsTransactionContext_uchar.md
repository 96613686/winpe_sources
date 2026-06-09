# CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(CmsTransactionContext *,uchar)

- ea: `0x1400708a0`
- end: `0x140070c0d`
- name: `?ReleasePinnedContainersAtEndOfTransaction@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@E@Z`
- size: `877`
- prototype: `void __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140016230`

## callees

- `0x1400708a0`
- `0x140090250`
- `0x140093550`
- `0x14013bf80`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070a6d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070ab5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070afd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070b45`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070a6d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070ab5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070afd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140070b45`
- `ntoskrnl!ExReleasePushLockEx` at `0x140070922`
- `ntoskrnl!ExReleasePushLockEx` at `0x140070970`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400709be`
- `ntoskrnl!ExReleasePushLockEx` at `0x140070a0c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140070922`
- `ntoskrnl!ExReleasePushLockEx` at `0x140070970`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400709be`
- `ntoskrnl!ExReleasePushLockEx` at `0x140070a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070b90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401fea72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070b90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401fea72`

## pseudocode

```c
void __fastcall CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(
        struct _IO_REMOVE_LOCK *this,
        struct CmsTransactionContext *a2,
        char a3)
{
  char v4; // si
  __int64 v5; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  CmsVolumeContainer *v10; // rcx
  void *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // r8
  struct SmsContainer *v17; // r8
  struct SmsContainer *v18; // r8
  struct SmsContainer *v19; // r8
  struct SmsContainer *v20; // r8
  struct SmsContainer *v21; // r8
  struct SmsContainer **i; // rdi
  struct SmsContainer *v23; // r8

  v4 = 0;
  v5 = *((_QWORD *)a2 + 37);
  if ( v5 )
  {
    ExReleasePushLockEx(v5 + 120, 2);
    --*((_DWORD *)a2 + 89);
    if ( a3 && (_mm_lfence(), v12 = *((_QWORD *)a2 + 37), *(char *)(v12 + 24) < 0) && (*(_BYTE *)(v12 + 25) & 3) == 3 )
    {
      v4 = 1;
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 37) + 92LL));
      IoReleaseRemoveLockEx(this + 15, 0, 0x20u);
      --*((_DWORD *)a2 + 88);
      *((_QWORD *)a2 + 37) = 0;
      *((_DWORD *)a2 + 84) = 0;
    }
  }
  v8 = *((_QWORD *)a2 + 38);
  if ( v8 )
  {
    ExReleasePushLockEx(v8 + 120, 2);
    --*((_DWORD *)a2 + 89);
    if ( a3 && (_mm_lfence(), v13 = *((_QWORD *)a2 + 38), *(char *)(v13 + 24) < 0) && (*(_BYTE *)(v13 + 25) & 3) == 3 )
    {
      v4 = 1;
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 38) + 92LL));
      IoReleaseRemoveLockEx(this + 15, 0, 0x20u);
      --*((_DWORD *)a2 + 88);
      *((_QWORD *)a2 + 38) = 0;
      *((_DWORD *)a2 + 85) = 0;
    }
  }
  v9 = *((_QWORD *)a2 + 39);
  if ( v9 )
  {
    ExReleasePushLockEx(v9 + 120, 2);
    --*((_DWORD *)a2 + 89);
    if ( a3 && (_mm_lfence(), v14 = *((_QWORD *)a2 + 39), *(char *)(v14 + 24) < 0) && (*(_BYTE *)(v14 + 25) & 3) == 3 )
    {
      v4 = 1;
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 39) + 92LL));
      IoReleaseRemoveLockEx(this + 15, 0, 0x20u);
      --*((_DWORD *)a2 + 88);
      *((_QWORD *)a2 + 39) = 0;
      *((_DWORD *)a2 + 86) = 0;
    }
  }
  v10 = (CmsVolumeContainer *)*((_QWORD *)a2 + 40);
  if ( v10 )
  {
    ExReleasePushLockEx((char *)v10 + 120, 2);
    --*((_DWORD *)a2 + 89);
    if ( a3 && (_mm_lfence(), v15 = *((_QWORD *)a2 + 40), *(char *)(v15 + 24) < 0) && (*(_BYTE *)(v15 + 25) & 3) == 3 )
    {
      v4 = 1;
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 40) + 92LL));
      IoReleaseRemoveLockEx(this + 15, 0, 0x20u);
      --*((_DWORD *)a2 + 88);
      *((_QWORD *)a2 + 40) = 0;
      *((_DWORD *)a2 + 87) = 0;
    }
  }
  while ( 1 )
  {
    v11 = (void *)*((_QWORD *)a2 + 41);
    if ( !v11 )
      break;
    v16 = (char *)*((_QWORD *)v11 + 1);
    if ( v16 )
    {
      if ( a3 && v16[24] < 0 && (v16[25] & 3) == 3 )
      {
        do
        {
          v18 = (struct SmsContainer *)*((_QWORD *)v11 + 1);
          if ( v18 )
            CmsVolumeContainer::UnlockContainerShared(v10, a2, v18);
          v11 = *(void **)v11;
        }
        while ( v11 );
        goto LABEL_34;
      }
      CmsVolumeContainer::UnlockContainerShared(v10, a2, (struct SmsContainer *)v16);
      CmsVolumeContainer::ReleaseContainerReference((CmsVolumeContainer *)this, a2, *((struct SmsContainer **)v11 + 1));
    }
    *((_QWORD *)a2 + 41) = **((_QWORD **)a2 + 41);
    ExFreePoolWithTag(v11, 0);
  }
  if ( !v4 )
    return;
LABEL_34:
  v17 = (struct SmsContainer *)*((_QWORD *)a2 + 37);
  if ( v17 )
  {
    CmsVolumeContainer::RequeryWH((CmsVolumeContainer *)this, a2, v17);
    CmsVolumeContainer::ReleaseContainerReference((CmsVolumeContainer *)this, a2, *((struct SmsContainer **)a2 + 37));
    *((_QWORD *)a2 + 37) = 0;
    *((_DWORD *)a2 + 84) = 0;
  }
  v19 = (struct SmsContainer *)*((_QWORD *)a2 + 38);
  if ( v19 )
  {
    CmsVolumeContainer::RequeryWH((CmsVolumeContainer *)this, a2, v19);
    CmsVolumeContainer::ReleaseContainerReference((CmsVolumeContainer *)this, a2, *((struct SmsContainer **)a2 + 38));
    *((_QWORD *)a2 + 38) = 0;
    *((_DWORD *)a2 + 85) = 0;
  }
  v20 = (struct SmsContainer *)*((_QWORD *)a2 + 39);
  if ( v20 )
  {
    CmsVolumeContainer::RequeryWH((CmsVolumeContainer *)this, a2, v20);
    CmsVolumeContainer::ReleaseContainerReference((CmsVolumeContainer *)this, a2, *((struct SmsContainer **)a2 + 39));
    *((_QWORD *)a2 + 39) = 0;
    *((_DWORD *)a2 + 86) = 0;
  }
  v21 = (struct SmsContainer *)*((_QWORD *)a2 + 40);
  if ( v21 )
  {
    CmsVolumeContainer::RequeryWH((CmsVolumeContainer *)this, a2, v21);
    CmsVolumeContainer::ReleaseContainerReference((CmsVolumeContainer *)this, a2, *((struct SmsContainer **)a2 + 40));
    *((_QWORD *)a2 + 40) = 0;
    *((_DWORD *)a2 + 87) = 0;
  }
  for ( i = (struct SmsContainer **)*((_QWORD *)a2 + 41); i; i = (struct SmsContainer **)*((_QWORD *)a2 + 41) )
  {
    v23 = i[1];
    if ( v23 )
    {
      CmsVolumeContainer::RequeryWH((CmsVolumeContainer *)this, a2, v23);
      CmsVolumeContainer::ReleaseContainerReference((CmsVolumeContainer *)this, a2, i[1]);
    }
    *((_QWORD *)a2 + 41) = **((_QWORD **)a2 + 41);
    ExFreePoolWithTag(i, 0);
  }
}

```

## disassembly

```asm
0x1400708a0  push    rbx
0x1400708a2  push    rbp
0x1400708a3  push    rsi
0x1400708a4  push    rdi
0x1400708a5  push    r14
0x1400708a7  sub     rsp, 20h
0x1400708ab  mov     r14, rcx
0x1400708ae  xor     sil, sil
0x1400708b1  mov     rcx, [rdx+128h]
0x1400708b8  movzx   ebp, r8b
0x1400708bc  mov     rbx, rdx
0x1400708bf  test    rcx, rcx
0x1400708c2  jnz     short loc_140070919
0x1400708c4  mov     rcx, [rbx+130h]
0x1400708cb  test    rcx, rcx
0x1400708ce  jnz     loc_140070967
0x1400708d4  mov     rcx, [rbx+138h]
0x1400708db  test    rcx, rcx
0x1400708de  jnz     loc_1400709B5
0x1400708e4  mov     rcx, [rbx+140h]; this
0x1400708eb  test    rcx, rcx
0x1400708ee  jnz     loc_140070A03
0x1400708f4  mov     rdi, [rbx+148h]
0x1400708fb  test    rdi, rdi
0x1400708fe  jnz     loc_140070B71
0x140070904  test    sil, sil
0x140070907  jnz     loc_140070BC9
0x14007090d  add     rsp, 20h
0x140070911  pop     r14
0x140070913  pop     rdi
0x140070914  pop     rsi
0x140070915  pop     rbp
0x140070916  pop     rbx
0x140070917  retn
0x140070919  add     rcx, 78h ; 'x'
0x14007091d  mov     edx, 2
0x140070922  call    cs:__imp_ExReleasePushLockEx
0x140070929  nop     dword ptr [rax+rax+00h]
0x14007092e  dec     dword ptr [rbx+164h]
0x140070934  test    bpl, bpl
0x140070937  jz      loc_140070A51
0x14007093d  lfence
0x140070940  mov     rax, [rbx+128h]
0x140070947  cmp     [rax+18h], sil
0x14007094b  jge     loc_140070A51
0x140070951  movzx   eax, byte ptr [rax+19h]
0x140070955  and     al, 3
0x140070957  cmp     al, 3
0x140070959  jnz     loc_140070A51
0x14007095f  mov     sil, 1
0x140070962  jmp     loc_1400708C4
0x140070967  add     rcx, 78h ; 'x'
0x14007096b  mov     edx, 2
0x140070970  call    cs:__imp_ExReleasePushLockEx
0x140070977  nop     dword ptr [rax+rax+00h]
0x14007097c  dec     dword ptr [rbx+164h]
0x140070982  test    bpl, bpl
0x140070985  jz      loc_140070A99
0x14007098b  lfence
0x14007098e  mov     rax, [rbx+130h]
0x140070995  cmp     byte ptr [rax+18h], 0
0x140070999  jge     loc_140070A99
0x14007099f  movzx   eax, byte ptr [rax+19h]
0x1400709a3  and     al, 3
0x1400709a5  cmp     al, 3
0x1400709a7  jnz     loc_140070A99
0x1400709ad  mov     sil, 1
0x1400709b0  jmp     loc_1400708D4
0x1400709b5  add     rcx, 78h ; 'x'
0x1400709b9  mov     edx, 2
0x1400709be  call    cs:__imp_ExReleasePushLockEx
0x1400709c5  nop     dword ptr [rax+rax+00h]
0x1400709ca  dec     dword ptr [rbx+164h]
0x1400709d0  test    bpl, bpl
0x1400709d3  jz      loc_140070AE1
0x1400709d9  lfence
0x1400709dc  mov     rax, [rbx+138h]
0x1400709e3  cmp     byte ptr [rax+18h], 0
0x1400709e7  jge     loc_140070AE1
0x1400709ed  movzx   eax, byte ptr [rax+19h]
0x1400709f1  and     al, 3
0x1400709f3  cmp     al, 3
0x1400709f5  jnz     loc_140070AE1
0x1400709fb  mov     sil, 1
0x1400709fe  jmp     loc_1400708E4
0x140070a03  add     rcx, 78h ; 'x'
0x140070a07  mov     edx, 2
0x140070a0c  call    cs:__imp_ExReleasePushLockEx
0x140070a13  nop     dword ptr [rax+rax+00h]
0x140070a18  dec     dword ptr [rbx+164h]
0x140070a1e  test    bpl, bpl
0x140070a21  jz      loc_140070B29
0x140070a27  lfence
0x140070a2a  mov     rax, [rbx+140h]
0x140070a31  cmp     byte ptr [rax+18h], 0
0x140070a35  jge     loc_140070B29
0x140070a3b  movzx   eax, byte ptr [rax+19h]
0x140070a3f  and     al, 3
0x140070a41  cmp     al, 3
0x140070a43  jnz     loc_140070B29
0x140070a49  mov     sil, 1
0x140070a4c  jmp     loc_1400708F4
0x140070a51  mov     rax, [rbx+128h]
0x140070a58  lea     rcx, [r14+1E0h]; RemoveLock
0x140070a5f  nop
0x140070a60  xor     edx, edx; Tag
0x140070a62  mov     r8d, 20h ; ' '; RemlockSize
0x140070a68  lock dec dword ptr [rax+5Ch]
0x140070a6c  nop
0x140070a6d  call    cs:__imp_IoReleaseRemoveLockEx
0x140070a74  nop     dword ptr [rax+rax+00h]
0x140070a79  dec     dword ptr [rbx+160h]
0x140070a7f  mov     qword ptr [rbx+128h], 0
0x140070a8a  mov     dword ptr [rbx+150h], 0
0x140070a94  jmp     loc_1400708C4
0x140070a99  mov     rax, [rbx+130h]
0x140070aa0  lea     rcx, [r14+1E0h]; RemoveLock
0x140070aa7  nop
0x140070aa8  xor     edx, edx; Tag
0x140070aaa  mov     r8d, 20h ; ' '; RemlockSize
0x140070ab0  lock dec dword ptr [rax+5Ch]
0x140070ab4  nop
0x140070ab5  call    cs:__imp_IoReleaseRemoveLockEx
0x140070abc  nop     dword ptr [rax+rax+00h]
0x140070ac1  dec     dword ptr [rbx+160h]
0x140070ac7  mov     qword ptr [rbx+130h], 0
0x140070ad2  mov     dword ptr [rbx+154h], 0
0x140070adc  jmp     loc_1400708D4
0x140070ae1  mov     rax, [rbx+138h]
0x140070ae8  lea     rcx, [r14+1E0h]; RemoveLock
0x140070aef  nop
0x140070af0  xor     edx, edx; Tag
0x140070af2  mov     r8d, 20h ; ' '; RemlockSize
0x140070af8  lock dec dword ptr [rax+5Ch]
0x140070afc  nop
0x140070afd  call    cs:__imp_IoReleaseRemoveLockEx
0x140070b04  nop     dword ptr [rax+rax+00h]
0x140070b09  dec     dword ptr [rbx+160h]
0x140070b0f  mov     qword ptr [rbx+138h], 0
0x140070b1a  mov     dword ptr [rbx+158h], 0
0x140070b24  jmp     loc_1400708E4
0x140070b29  mov     rax, [rbx+140h]
0x140070b30  lea     rcx, [r14+1E0h]; RemoveLock
0x140070b37  nop
0x140070b38  xor     edx, edx; Tag
0x140070b3a  mov     r8d, 20h ; ' '; RemlockSize
0x140070b40  lock dec dword ptr [rax+5Ch]
0x140070b44  nop
0x140070b45  call    cs:__imp_IoReleaseRemoveLockEx
0x140070b4c  nop     dword ptr [rax+rax+00h]
0x140070b51  dec     dword ptr [rbx+160h]
0x140070b57  mov     qword ptr [rbx+140h], 0
0x140070b62  mov     dword ptr [rbx+15Ch], 0
0x140070b6c  jmp     loc_1400708F4
0x140070b71  mov     r8, [rdi+8]; struct SmsContainer *
0x140070b75  test    r8, r8
0x140070b78  jnz     short loc_140070BA1
0x140070b7a  mov     rax, [rbx+148h]
0x140070b81  mov     rcx, rdi; P
0x140070b84  mov     rdx, [rax]
0x140070b87  mov     [rbx+148h], rdx
0x140070b8e  xor     edx, edx; Tag
0x140070b90  call    cs:__imp_ExFreePoolWithTag
0x140070b97  nop     dword ptr [rax+rax+00h]
0x140070b9c  jmp     loc_1400708F4
0x140070ba1  test    bpl, bpl
0x140070ba4  jz      loc_1401FE940
0x140070baa  cmp     byte ptr [r8+18h], 0
0x140070baf  jge     loc_1401FE940
0x140070bb5  movzx   eax, byte ptr [r8+19h]
0x140070bba  and     al, 3
0x140070bbc  cmp     al, 3
0x140070bbe  jnz     loc_1401FE940
0x140070bc4  jmp     loc_1401FE95D
0x140070bc9  mov     r8, [rbx+128h]; struct SmsContainer *
0x140070bd0  test    r8, r8
0x140070bd3  jz      loc_1401FE97B
0x140070bd9  mov     rcx, r14; this
0x140070bdc  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x140070be1  mov     r8, [rbx+128h]; struct SmsContainer *
0x140070be8  mov     rdx, rbx; struct CmsTransactionContext *
0x140070beb  mov     rcx, r14; this
0x140070bee  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x140070bf3  mov     qword ptr [rbx+128h], 0
0x140070bfe  mov     dword ptr [rbx+150h], 0
0x140070c08  jmp     loc_1401FE97B
0x1401fe940  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fe943  call    ?UnlockContainerShared@CmsVolumeContainer@@AEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::UnlockContainerShared(CmsTransactionContext *,SmsContainer *)
0x1401fe948  mov     r8, [rdi+8]; struct SmsContainer *
0x1401fe94c  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fe94f  mov     rcx, r14; this
0x1401fe952  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401fe957  nop
0x1401fe958  jmp     loc_140070B7A
0x1401fe95d  mov     r8, [rdi+8]; struct SmsContainer *
0x1401fe961  test    r8, r8
0x1401fe964  jz      short loc_1401FE96E
0x1401fe966  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fe969  call    ?UnlockContainerShared@CmsVolumeContainer@@AEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::UnlockContainerShared(CmsTransactionContext *,SmsContainer *)
0x1401fe96e  mov     rdi, [rdi]
0x1401fe971  test    rdi, rdi
0x1401fe974  jnz     short loc_1401FE95D
0x1401fe976  jmp     loc_140070BC9
0x1401fe97b  mov     r8, [rbx+130h]; struct SmsContainer *
0x1401fe982  test    r8, r8
0x1401fe985  jz      short loc_1401FE9B6
0x1401fe987  mov     rcx, r14; this
0x1401fe98a  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401fe98f  mov     r8, [rbx+130h]; struct SmsContainer *
0x1401fe996  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fe999  mov     rcx, r14; this
0x1401fe99c  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401fe9a1  mov     qword ptr [rbx+130h], 0
0x1401fe9ac  mov     dword ptr [rbx+154h], 0
0x1401fe9b6  mov     r8, [rbx+138h]; struct SmsContainer *
0x1401fe9bd  test    r8, r8
0x1401fe9c0  jz      short loc_1401FE9F1
0x1401fe9c2  mov     rcx, r14; this
0x1401fe9c5  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401fe9ca  mov     r8, [rbx+138h]; struct SmsContainer *
0x1401fe9d1  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fe9d4  mov     rcx, r14; this
0x1401fe9d7  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401fe9dc  mov     qword ptr [rbx+138h], 0
0x1401fe9e7  mov     dword ptr [rbx+158h], 0
0x1401fe9f1  mov     r8, [rbx+140h]; struct SmsContainer *
0x1401fe9f8  test    r8, r8
0x1401fe9fb  jz      short loc_1401FEA2C
0x1401fe9fd  mov     rcx, r14; this
0x1401fea00  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401fea05  mov     r8, [rbx+140h]; struct SmsContainer *
0x1401fea0c  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fea0f  mov     rcx, r14; this
0x1401fea12  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401fea17  mov     qword ptr [rbx+140h], 0
0x1401fea22  mov     dword ptr [rbx+15Ch], 0
0x1401fea2c  mov     rdi, [rbx+148h]
0x1401fea33  test    rdi, rdi
0x1401fea36  jz      loc_14007090D
0x1401fea3c  mov     r8, [rdi+8]; struct SmsContainer *
0x1401fea40  test    r8, r8
0x1401fea43  jz      short loc_1401FEA5C
0x1401fea45  mov     rcx, r14; this
0x1401fea48  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401fea4d  mov     r8, [rdi+8]; struct SmsContainer *
0x1401fea51  mov     rdx, rbx; struct CmsTransactionContext *
0x1401fea54  mov     rcx, r14; this
0x1401fea57  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401fea5c  mov     rax, [rbx+148h]
0x1401fea63  mov     rcx, rdi; P
0x1401fea66  mov     rdx, [rax]
0x1401fea69  mov     [rbx+148h], rdx
0x1401fea70  xor     edx, edx; Tag
0x1401fea72  call    cs:__imp_ExFreePoolWithTag
0x1401fea79  nop     dword ptr [rax+rax+00h]
0x1401fea7e  mov     rdi, [rbx+148h]
0x1401fea85  test    rdi, rdi
0x1401fea88  jnz     short loc_1401FEA3C
0x1401fea8a  jmp     loc_14007090D
```
