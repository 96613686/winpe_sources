# FIPfFileOpenRemove

- ea: `0x140015460`
- end: `0x1400156cd`
- name: `FIPfFileOpenRemove`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400153a0`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140002d64`
- `0x14000f9b8`
- `0x140015460`
- `0x140015950`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001554d`
- `ntoskrnl!KeSetEvent` at `0x14001554d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015695`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015695`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001566f`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001566f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001563a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001563a`
- `FLTMGR!FltReleaseContext` at `0x140015684`
- `FLTMGR!FltReleaseContext` at `0x140015684`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140015490`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140015490`

## pseudocode

```c
__int64 __fastcall FIPfFileOpenRemove(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  struct _FLT_FILE_NAME_INFORMATION *v7; // rbp
  struct _FLT_FILE_NAME_INFORMATION *v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // r12
  char *v11; // rax
  char *v12; // rbx
  int v13; // r14d
  struct _KEVENT *i; // rdi
  __int64 v15; // r8
  wchar_t *Buffer; // rcx
  unsigned __int16 v17; // dx
  char *v18; // rax
  void **v19; // rcx
  signed __int64 v20; // rax
  bool v21; // cc
  signed __int64 v22; // rax
  struct _FLT_GENERIC_WORKITEM *v23; // rcx
  void *v24; // rcx
  __int64 v26; // [rsp+70h] [rbp+8h] BYREF
  __int64 v27; // [rsp+88h] [rbp+20h]

  v3 = a1 + 40;
  v7 = 0;
  FILockSharedAcquire(a1 + 40);
  v8 = *(struct _FLT_FILE_NAME_INFORMATION **)(a1 + 48);
  if ( v8 )
  {
    v7 = *(struct _FLT_FILE_NAME_INFORMATION **)(a1 + 48);
    FltReferenceFileNameInformation(v8);
  }
  if ( v3 )
  {
    v9 = *(_QWORD *)(a1 + 72);
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 20));
  }
  else
  {
    FILockSharedAcquire(0);
    v9 = *(_QWORD *)(a1 + 72);
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 20));
    FILockExclusiveRelease(0);
  }
  v10 = v9;
  FILockExclusiveRelease(v3);
  v27 = v9 + 24;
  FILockExclusiveAcquire(v9 + 24);
  v11 = (char *)(v9 + 32);
  v12 = *(char **)(v9 + 32);
  if ( v12 == v11 )
  {
LABEL_10:
    _InterlockedIncrement(&dword_1400097E8);
    v12 = 0;
  }
  else
  {
    while ( *((_QWORD *)v12 + 5) != a2 || *((_QWORD *)v12 + 3) != a3 )
    {
      v12 = *(char **)v12;
      if ( v12 == v11 )
        goto LABEL_10;
    }
    v18 = *(char **)v12;
    if ( *(char **)(*(_QWORD *)v12 + 8LL) != v12 || (v19 = (void **)*((_QWORD *)v12 + 1), *v19 != v12) )
      __fastfail(3u);
    *v19 = v18;
    *((_QWORD *)v18 + 1) = v19;
    --*(_DWORD *)(v10 + 48);
  }
  v13 = 2;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v12 + 16, 3, 1) != 1 )
  {
    *((_DWORD *)v12 + 16) = 3;
    for ( i = (struct _KEVENT *)*((_QWORD *)v12 + 9);
          i != (struct _KEVENT *)(v12 + 72);
          i = *(struct _KEVENT **)&i->Header.Lock )
    {
      KeSetEvent(i + 2, 2, 0);
      _InterlockedIncrement(&dword_1400097F4);
    }
  }
  FILockExclusiveRelease(v27);
  v15 = *((_QWORD *)v12 + 11);
  if ( v15 )
  {
    if ( v7 )
    {
      Buffer = v7->Name.Buffer;
      v17 = v7->Name.Length >> 1;
      v13 = 0;
    }
    else
    {
      Buffer = FIUnknown;
      v17 = 11;
    }
    v26 = 1;
    FIPfConflictTelemetryUpdate(
      Buffer,
      v17,
      v13,
      3u,
      (unsigned __int16 *)&v26,
      ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
    + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24)
    - v15);
  }
  if ( v7 )
    FltReleaseFileNameInformation(v7);
  FIPfFilePfLinkDereference(v10);
  v20 = _InterlockedExchangeAdd64((volatile signed __int64 *)v12 + 12, 0xFFFFFFFFFFFFFFFFuLL);
  v21 = v20 <= 1;
  v22 = v20 - 1;
  if ( v21 )
  {
    if ( v22 )
      __fastfail(0xEu);
    v23 = (struct _FLT_GENERIC_WORKITEM *)*((_QWORD *)v12 + 6);
    if ( v23 )
      FltFreeGenericWorkItem(v23);
    v24 = (void *)*((_QWORD *)v12 + 7);
    if ( v24 )
      FltReleaseContext(v24);
    ExFreePoolWithTag(v12, 0);
  }
  return FIPfFilePfContextDereference(v10, a1);
}

```

## disassembly

```asm
0x140015460  push    rbx
0x140015462  push    rbp
0x140015463  push    rsi
0x140015464  push    rdi
0x140015465  push    r13
0x140015467  push    r14
0x140015469  sub     rsp, 38h
0x14001546d  lea     r14, [rcx+28h]
0x140015471  mov     r13, rcx
0x140015474  mov     rcx, r14
0x140015477  mov     rdi, r8
0x14001547a  mov     rsi, rdx
0x14001547d  xor     ebp, ebp
0x14001547f  call    FILockSharedAcquire
0x140015484  mov     rcx, [r13+30h]; FileNameInformation
0x140015488  test    rcx, rcx
0x14001548b  jz      short loc_14001549C
0x14001548d  mov     rbp, rcx
0x140015490  call    cs:__imp_FltReferenceFileNameInformation
0x140015497  nop     dword ptr [rax+rax+00h]
0x14001549c  mov     [rsp+68h+arg_8], r12
0x1400154a1  test    r14, r14
0x1400154a4  jnz     short loc_1400154BE
0x1400154a6  xor     ecx, ecx
0x1400154a8  call    FILockSharedAcquire
0x1400154ad  mov     rbx, [r13+48h]
0x1400154b1  lock inc dword ptr [rbx+14h]
0x1400154b5  xor     ecx, ecx
0x1400154b7  call    FILockExclusiveRelease
0x1400154bc  jmp     short loc_1400154C6
0x1400154be  mov     rbx, [r13+48h]
0x1400154c2  lock inc dword ptr [rbx+14h]
0x1400154c6  mov     rcx, r14
0x1400154c9  mov     [rsp+68h+var_38], r15
0x1400154ce  mov     r12, rbx
0x1400154d1  call    FILockExclusiveRelease
0x1400154d6  lea     rax, [rbx+18h]
0x1400154da  mov     rcx, rax
0x1400154dd  mov     [rsp+68h+arg_18], rax
0x1400154e5  call    FILockExclusiveAcquire
0x1400154ea  lea     rax, [rbx+20h]
0x1400154ee  mov     rbx, [rbx+20h]
0x1400154f2  cmp     rbx, rax
0x1400154f5  jz      short loc_14001550F
0x1400154f7  cmp     [rbx+28h], rsi
0x1400154fb  jnz     short loc_140015507
0x1400154fd  cmp     [rbx+18h], rdi
0x140015501  jz      loc_14001559C
0x140015507  mov     rbx, [rbx]
0x14001550a  cmp     rbx, rax
0x14001550d  jnz     short loc_1400154F7
0x14001550f  lock inc cs:dword_1400097E8
0x140015516  xor     ebx, ebx
0x140015518  mov     edi, 1
0x14001551d  mov     r15d, 3
0x140015523  mov     eax, edi
0x140015525  mov     r14d, 2
0x14001552b  lock cmpxchg [rbx+40h], r15d
0x140015531  jz      short loc_14001556D
0x140015533  lea     rsi, [rbx+48h]
0x140015537  mov     [rbx+40h], r15d
0x14001553b  mov     rdi, [rsi]
0x14001553e  cmp     rdi, rsi
0x140015541  jz      short loc_140015568
0x140015543  lea     rcx, [rdi+30h]; Event
0x140015547  xor     r8d, r8d; Wait
0x14001554a  mov     edx, r14d; Increment
0x14001554d  call    cs:__imp_KeSetEvent
0x140015554  nop     dword ptr [rax+rax+00h]
0x140015559  lock inc cs:dword_1400097F4
0x140015560  mov     rdi, [rdi]
0x140015563  cmp     rdi, rsi
0x140015566  jnz     short loc_140015543
0x140015568  mov     edi, 1
0x14001556d  mov     rcx, [rsp+68h+arg_18]
0x140015575  call    FILockExclusiveRelease
0x14001557a  mov     r8, [rbx+58h]
0x14001557e  test    r8, r8
0x140015581  jz      loc_140015632
0x140015587  test    rbp, rbp
0x14001558a  jz      short loc_1400155C6
0x14001558c  movzx   edx, word ptr [rbp+8]
0x140015590  mov     rcx, [rbp+10h]
0x140015594  shr     dx, 1
0x140015597  xor     r14d, r14d
0x14001559a  jmp     short loc_1400155D2
0x14001559c  mov     rax, [rbx]
0x14001559f  cmp     [rax+8], rbx
0x1400155a3  jnz     short loc_1400155BF
0x1400155a5  mov     rcx, [rbx+8]
0x1400155a9  cmp     [rcx], rbx
0x1400155ac  jnz     short loc_1400155BF
0x1400155ae  mov     [rcx], rax
0x1400155b1  mov     [rax+8], rcx
0x1400155b5  dec     dword ptr [r12+30h]
0x1400155ba  jmp     loc_140015518
0x1400155bf  mov     ecx, 3
0x1400155c4  int     29h; Win8: RtlFailFast(ecx)
0x1400155c6  lea     rcx, FIUnknown; "\\FI_UNKNOWN"
0x1400155cd  mov     edx, 0Bh
0x1400155d2  mov     [rsp+68h+arg_0], 0
0x1400155db  mov     r9, 0FFFFF78000000320h
0x1400155e5  mov     word ptr [rsp+68h+arg_0+6], di
0x1400155ea  mov     word ptr [rsp+68h+arg_0], di
0x1400155ef  mov     r9, [r9]
0x1400155f2  mov     eax, ds:0FFFFF78000000004h
0x1400155fb  mov     r10d, r9d
0x1400155fe  imul    r10, rax
0x140015602  shr     r9, 20h
0x140015606  imul    r9d, eax
0x14001560a  lea     rax, [rsp+68h+arg_0]
0x14001560f  shr     r10, 18h
0x140015613  shl     r9d, 8
0x140015617  add     r10d, r9d
0x14001561a  mov     r9d, r15d
0x14001561d  sub     r10d, r8d
0x140015620  mov     r8d, r14d
0x140015623  mov     [rsp+68h+var_40], r10d
0x140015628  mov     [rsp+68h+var_48], rax
0x14001562d  call    FIPfConflictTelemetryUpdate
0x140015632  test    rbp, rbp
0x140015635  jz      short loc_140015646
0x140015637  mov     rcx, rbp; FileNameInformation
0x14001563a  call    cs:__imp_FltReleaseFileNameInformation
0x140015641  nop     dword ptr [rax+rax+00h]
0x140015646  mov     rcx, r12
0x140015649  call    FIPfFilePfLinkDereference
0x14001564e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140015655  lock xadd [rbx+60h], rax
0x14001565b  sub     rax, 1
0x14001565f  jg      short loc_1400156AA
0x140015661  test    rax, rax
0x140015664  jnz     short loc_1400156A3
0x140015666  mov     rcx, [rbx+30h]; FltWorkItem
0x14001566a  test    rcx, rcx
0x14001566d  jz      short loc_14001567B
0x14001566f  call    cs:__imp_FltFreeGenericWorkItem
0x140015676  nop     dword ptr [rax+rax+00h]
0x14001567b  mov     rcx, [rbx+38h]; Context
0x14001567f  test    rcx, rcx
0x140015682  jz      short loc_140015690
0x140015684  call    cs:__imp_FltReleaseContext
0x14001568b  nop     dword ptr [rax+rax+00h]
0x140015690  xor     edx, edx; Tag
0x140015692  mov     rcx, rbx; P
0x140015695  call    cs:__imp_ExFreePoolWithTag
0x14001569c  nop     dword ptr [rax+rax+00h]
0x1400156a1  jmp     short loc_1400156AA
0x1400156a3  mov     ecx, 0Eh
0x1400156a8  int     29h; Win8: RtlFailFast(ecx)
0x1400156aa  mov     rdx, r13
0x1400156ad  mov     rcx, r12
0x1400156b0  call    FIPfFilePfContextDereference
0x1400156b5  mov     r15, [rsp+68h+var_38]
0x1400156ba  mov     r12, [rsp+68h+arg_8]
0x1400156bf  add     rsp, 38h
0x1400156c3  pop     r14
0x1400156c5  pop     r13
0x1400156c7  pop     rdi
0x1400156c8  pop     rsi
0x1400156c9  pop     rbp
0x1400156ca  pop     rbx
0x1400156cb  retn
```
