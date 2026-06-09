# CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(CmsTransactionContext *,uchar)

- ea: `0x140078bd0`
- end: `0x140078f3d`
- name: `?ReleasePinnedContainersAtEndOfTransaction@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@E@Z`
- size: `877`
- prototype: `void __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400340e0`
- `0x140035300`

## callees

- `0x140048a70`
- `0x140078bd0`
- `0x140098c60`
- `0x140136640`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078d9d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078de5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078e2d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078e75`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078d9d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078de5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078e2d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140078e75`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078c52`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078ca0`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078cee`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078d3c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078c52`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078ca0`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078cee`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078d3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f71f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f71f8`

## pseudocode

```c
void __fastcall CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(
        CmsVolumeContainer *this,
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
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 488), 0, 0x20u);
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
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 488), 0, 0x20u);
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
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 488), 0, 0x20u);
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
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 488), 0, 0x20u);
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
      CmsVolumeContainer::ReleaseContainerReference(this, a2, *((struct SmsContainer **)v11 + 1));
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
    CmsVolumeContainer::RequeryWH(this, a2, v17);
    CmsVolumeContainer::ReleaseContainerReference(this, a2, *((struct SmsContainer **)a2 + 37));
    *((_QWORD *)a2 + 37) = 0;
    *((_DWORD *)a2 + 84) = 0;
  }
  v19 = (struct SmsContainer *)*((_QWORD *)a2 + 38);
  if ( v19 )
  {
    CmsVolumeContainer::RequeryWH(this, a2, v19);
    CmsVolumeContainer::ReleaseContainerReference(this, a2, *((struct SmsContainer **)a2 + 38));
    *((_QWORD *)a2 + 38) = 0;
    *((_DWORD *)a2 + 85) = 0;
  }
  v20 = (struct SmsContainer *)*((_QWORD *)a2 + 39);
  if ( v20 )
  {
    CmsVolumeContainer::RequeryWH(this, a2, v20);
    CmsVolumeContainer::ReleaseContainerReference(this, a2, *((struct SmsContainer **)a2 + 39));
    *((_QWORD *)a2 + 39) = 0;
    *((_DWORD *)a2 + 86) = 0;
  }
  v21 = (struct SmsContainer *)*((_QWORD *)a2 + 40);
  if ( v21 )
  {
    CmsVolumeContainer::RequeryWH(this, a2, v21);
    CmsVolumeContainer::ReleaseContainerReference(this, a2, *((struct SmsContainer **)a2 + 40));
    *((_QWORD *)a2 + 40) = 0;
    *((_DWORD *)a2 + 87) = 0;
  }
  for ( i = (struct SmsContainer **)*((_QWORD *)a2 + 41); i; i = (struct SmsContainer **)*((_QWORD *)a2 + 41) )
  {
    v23 = i[1];
    if ( v23 )
    {
      CmsVolumeContainer::RequeryWH(this, a2, v23);
      CmsVolumeContainer::ReleaseContainerReference(this, a2, i[1]);
    }
    *((_QWORD *)a2 + 41) = **((_QWORD **)a2 + 41);
    ExFreePoolWithTag(i, 0);
  }
}

```

## disassembly

```asm
0x140078bd0  push    rbx
0x140078bd2  push    rbp
0x140078bd3  push    rsi
0x140078bd4  push    rdi
0x140078bd5  push    r14
0x140078bd7  sub     rsp, 20h
0x140078bdb  mov     r14, rcx
0x140078bde  xor     sil, sil
0x140078be1  mov     rcx, [rdx+128h]
0x140078be8  movzx   ebp, r8b
0x140078bec  mov     rbx, rdx
0x140078bef  test    rcx, rcx
0x140078bf2  jnz     short loc_140078C49
0x140078bf4  mov     rcx, [rbx+130h]
0x140078bfb  test    rcx, rcx
0x140078bfe  jnz     loc_140078C97
0x140078c04  mov     rcx, [rbx+138h]
0x140078c0b  test    rcx, rcx
0x140078c0e  jnz     loc_140078CE5
0x140078c14  mov     rcx, [rbx+140h]; this
0x140078c1b  test    rcx, rcx
0x140078c1e  jnz     loc_140078D33
0x140078c24  mov     rdi, [rbx+148h]
0x140078c2b  test    rdi, rdi
0x140078c2e  jnz     loc_140078EA1
0x140078c34  test    sil, sil
0x140078c37  jnz     loc_140078EF9
0x140078c3d  add     rsp, 20h
0x140078c41  pop     r14
0x140078c43  pop     rdi
0x140078c44  pop     rsi
0x140078c45  pop     rbp
0x140078c46  pop     rbx
0x140078c47  retn
0x140078c49  add     rcx, 78h ; 'x'
0x140078c4d  mov     edx, 2
0x140078c52  call    cs:__imp_ExReleasePushLockEx
0x140078c59  nop     dword ptr [rax+rax+00h]
0x140078c5e  dec     dword ptr [rbx+164h]
0x140078c64  test    bpl, bpl
0x140078c67  jz      loc_140078D81
0x140078c6d  lfence
0x140078c70  mov     rax, [rbx+128h]
0x140078c77  cmp     [rax+18h], sil
0x140078c7b  jge     loc_140078D81
0x140078c81  movzx   eax, byte ptr [rax+19h]
0x140078c85  and     al, 3
0x140078c87  cmp     al, 3
0x140078c89  jnz     loc_140078D81
0x140078c8f  mov     sil, 1
0x140078c92  jmp     loc_140078BF4
0x140078c97  add     rcx, 78h ; 'x'
0x140078c9b  mov     edx, 2
0x140078ca0  call    cs:__imp_ExReleasePushLockEx
0x140078ca7  nop     dword ptr [rax+rax+00h]
0x140078cac  dec     dword ptr [rbx+164h]
0x140078cb2  test    bpl, bpl
0x140078cb5  jz      loc_140078DC9
0x140078cbb  lfence
0x140078cbe  mov     rax, [rbx+130h]
0x140078cc5  cmp     byte ptr [rax+18h], 0
0x140078cc9  jge     loc_140078DC9
0x140078ccf  movzx   eax, byte ptr [rax+19h]
0x140078cd3  and     al, 3
0x140078cd5  cmp     al, 3
0x140078cd7  jnz     loc_140078DC9
0x140078cdd  mov     sil, 1
0x140078ce0  jmp     loc_140078C04
0x140078ce5  add     rcx, 78h ; 'x'
0x140078ce9  mov     edx, 2
0x140078cee  call    cs:__imp_ExReleasePushLockEx
0x140078cf5  nop     dword ptr [rax+rax+00h]
0x140078cfa  dec     dword ptr [rbx+164h]
0x140078d00  test    bpl, bpl
0x140078d03  jz      loc_140078E11
0x140078d09  lfence
0x140078d0c  mov     rax, [rbx+138h]
0x140078d13  cmp     byte ptr [rax+18h], 0
0x140078d17  jge     loc_140078E11
0x140078d1d  movzx   eax, byte ptr [rax+19h]
0x140078d21  and     al, 3
0x140078d23  cmp     al, 3
0x140078d25  jnz     loc_140078E11
0x140078d2b  mov     sil, 1
0x140078d2e  jmp     loc_140078C14
0x140078d33  add     rcx, 78h ; 'x'
0x140078d37  mov     edx, 2
0x140078d3c  call    cs:__imp_ExReleasePushLockEx
0x140078d43  nop     dword ptr [rax+rax+00h]
0x140078d48  dec     dword ptr [rbx+164h]
0x140078d4e  test    bpl, bpl
0x140078d51  jz      loc_140078E59
0x140078d57  lfence
0x140078d5a  mov     rax, [rbx+140h]
0x140078d61  cmp     byte ptr [rax+18h], 0
0x140078d65  jge     loc_140078E59
0x140078d6b  movzx   eax, byte ptr [rax+19h]
0x140078d6f  and     al, 3
0x140078d71  cmp     al, 3
0x140078d73  jnz     loc_140078E59
0x140078d79  mov     sil, 1
0x140078d7c  jmp     loc_140078C24
0x140078d81  mov     rax, [rbx+128h]
0x140078d88  lea     rcx, [r14+1E8h]; RemoveLock
0x140078d8f  nop
0x140078d90  xor     edx, edx; Tag
0x140078d92  mov     r8d, 20h ; ' '; RemlockSize
0x140078d98  lock dec dword ptr [rax+5Ch]
0x140078d9c  nop
0x140078d9d  call    cs:__imp_IoReleaseRemoveLockEx
0x140078da4  nop     dword ptr [rax+rax+00h]
0x140078da9  dec     dword ptr [rbx+160h]
0x140078daf  mov     qword ptr [rbx+128h], 0
0x140078dba  mov     dword ptr [rbx+150h], 0
0x140078dc4  jmp     loc_140078BF4
0x140078dc9  mov     rax, [rbx+130h]
0x140078dd0  lea     rcx, [r14+1E8h]; RemoveLock
0x140078dd7  nop
0x140078dd8  xor     edx, edx; Tag
0x140078dda  mov     r8d, 20h ; ' '; RemlockSize
0x140078de0  lock dec dword ptr [rax+5Ch]
0x140078de4  nop
0x140078de5  call    cs:__imp_IoReleaseRemoveLockEx
0x140078dec  nop     dword ptr [rax+rax+00h]
0x140078df1  dec     dword ptr [rbx+160h]
0x140078df7  mov     qword ptr [rbx+130h], 0
0x140078e02  mov     dword ptr [rbx+154h], 0
0x140078e0c  jmp     loc_140078C04
0x140078e11  mov     rax, [rbx+138h]
0x140078e18  lea     rcx, [r14+1E8h]; RemoveLock
0x140078e1f  nop
0x140078e20  xor     edx, edx; Tag
0x140078e22  mov     r8d, 20h ; ' '; RemlockSize
0x140078e28  lock dec dword ptr [rax+5Ch]
0x140078e2c  nop
0x140078e2d  call    cs:__imp_IoReleaseRemoveLockEx
0x140078e34  nop     dword ptr [rax+rax+00h]
0x140078e39  dec     dword ptr [rbx+160h]
0x140078e3f  mov     qword ptr [rbx+138h], 0
0x140078e4a  mov     dword ptr [rbx+158h], 0
0x140078e54  jmp     loc_140078C14
0x140078e59  mov     rax, [rbx+140h]
0x140078e60  lea     rcx, [r14+1E8h]; RemoveLock
0x140078e67  nop
0x140078e68  xor     edx, edx; Tag
0x140078e6a  mov     r8d, 20h ; ' '; RemlockSize
0x140078e70  lock dec dword ptr [rax+5Ch]
0x140078e74  nop
0x140078e75  call    cs:__imp_IoReleaseRemoveLockEx
0x140078e7c  nop     dword ptr [rax+rax+00h]
0x140078e81  dec     dword ptr [rbx+160h]
0x140078e87  mov     qword ptr [rbx+140h], 0
0x140078e92  mov     dword ptr [rbx+15Ch], 0
0x140078e9c  jmp     loc_140078C24
0x140078ea1  mov     r8, [rdi+8]; struct SmsContainer *
0x140078ea5  test    r8, r8
0x140078ea8  jnz     short loc_140078ED1
0x140078eaa  mov     rax, [rbx+148h]
0x140078eb1  mov     rcx, rdi; P
0x140078eb4  mov     rdx, [rax]
0x140078eb7  mov     [rbx+148h], rdx
0x140078ebe  xor     edx, edx; Tag
0x140078ec0  call    cs:__imp_ExFreePoolWithTag
0x140078ec7  nop     dword ptr [rax+rax+00h]
0x140078ecc  jmp     loc_140078C24
0x140078ed1  test    bpl, bpl
0x140078ed4  jz      loc_1401F70C6
0x140078eda  cmp     byte ptr [r8+18h], 0
0x140078edf  jge     loc_1401F70C6
0x140078ee5  movzx   eax, byte ptr [r8+19h]
0x140078eea  and     al, 3
0x140078eec  cmp     al, 3
0x140078eee  jnz     loc_1401F70C6
0x140078ef4  jmp     loc_1401F70E3
0x140078ef9  mov     r8, [rbx+128h]; struct SmsContainer *
0x140078f00  test    r8, r8
0x140078f03  jz      loc_1401F7101
0x140078f09  mov     rcx, r14; this
0x140078f0c  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x140078f11  mov     r8, [rbx+128h]; struct SmsContainer *
0x140078f18  mov     rdx, rbx; struct CmsTransactionContext *
0x140078f1b  mov     rcx, r14; this
0x140078f1e  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x140078f23  mov     qword ptr [rbx+128h], 0
0x140078f2e  mov     dword ptr [rbx+150h], 0
0x140078f38  jmp     loc_1401F7101
0x1401f70c6  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f70c9  call    ?UnlockContainerShared@CmsVolumeContainer@@AEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::UnlockContainerShared(CmsTransactionContext *,SmsContainer *)
0x1401f70ce  mov     r8, [rdi+8]; struct SmsContainer *
0x1401f70d2  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f70d5  mov     rcx, r14; this
0x1401f70d8  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401f70dd  nop
0x1401f70de  jmp     loc_140078EAA
0x1401f70e3  mov     r8, [rdi+8]; struct SmsContainer *
0x1401f70e7  test    r8, r8
0x1401f70ea  jz      short loc_1401F70F4
0x1401f70ec  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f70ef  call    ?UnlockContainerShared@CmsVolumeContainer@@AEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::UnlockContainerShared(CmsTransactionContext *,SmsContainer *)
0x1401f70f4  mov     rdi, [rdi]
0x1401f70f7  test    rdi, rdi
0x1401f70fa  jnz     short loc_1401F70E3
0x1401f70fc  jmp     loc_140078EF9
0x1401f7101  mov     r8, [rbx+130h]; struct SmsContainer *
0x1401f7108  test    r8, r8
0x1401f710b  jz      short loc_1401F713C
0x1401f710d  mov     rcx, r14; this
0x1401f7110  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401f7115  mov     r8, [rbx+130h]; struct SmsContainer *
0x1401f711c  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f711f  mov     rcx, r14; this
0x1401f7122  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401f7127  mov     qword ptr [rbx+130h], 0
0x1401f7132  mov     dword ptr [rbx+154h], 0
0x1401f713c  mov     r8, [rbx+138h]; struct SmsContainer *
0x1401f7143  test    r8, r8
0x1401f7146  jz      short loc_1401F7177
0x1401f7148  mov     rcx, r14; this
0x1401f714b  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401f7150  mov     r8, [rbx+138h]; struct SmsContainer *
0x1401f7157  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f715a  mov     rcx, r14; this
0x1401f715d  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401f7162  mov     qword ptr [rbx+138h], 0
0x1401f716d  mov     dword ptr [rbx+158h], 0
0x1401f7177  mov     r8, [rbx+140h]; struct SmsContainer *
0x1401f717e  test    r8, r8
0x1401f7181  jz      short loc_1401F71B2
0x1401f7183  mov     rcx, r14; this
0x1401f7186  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401f718b  mov     r8, [rbx+140h]; struct SmsContainer *
0x1401f7192  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f7195  mov     rcx, r14; this
0x1401f7198  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401f719d  mov     qword ptr [rbx+140h], 0
0x1401f71a8  mov     dword ptr [rbx+15Ch], 0
0x1401f71b2  mov     rdi, [rbx+148h]
0x1401f71b9  test    rdi, rdi
0x1401f71bc  jz      loc_140078C3D
0x1401f71c2  mov     r8, [rdi+8]; struct SmsContainer *
0x1401f71c6  test    r8, r8
0x1401f71c9  jz      short loc_1401F71E2
0x1401f71cb  mov     rcx, r14; this
0x1401f71ce  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1401f71d3  mov     r8, [rdi+8]; struct SmsContainer *
0x1401f71d7  mov     rdx, rbx; struct CmsTransactionContext *
0x1401f71da  mov     rcx, r14; this
0x1401f71dd  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1401f71e2  mov     rax, [rbx+148h]
0x1401f71e9  mov     rcx, rdi; P
0x1401f71ec  mov     rdx, [rax]
0x1401f71ef  mov     [rbx+148h], rdx
0x1401f71f6  xor     edx, edx; Tag
0x1401f71f8  call    cs:__imp_ExFreePoolWithTag
0x1401f71ff  nop     dword ptr [rax+rax+00h]
0x1401f7204  mov     rdi, [rbx+148h]
0x1401f720b  test    rdi, rdi
0x1401f720e  jnz     short loc_1401F71C2
0x1401f7210  jmp     loc_140078C3D
```
