# CmsTransactionContext::Abort(void)

- ea: `0x140012b30`
- end: `0x140012e0a`
- name: `?Abort@CmsTransactionContext@@QEAAXXZ`
- size: `730`
- prototype: `void __fastcall(CmsTransactionContext *__hidden this)`
- caller_count: `46`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140012b18`
- `0x14001395c`
- `0x140033b60`
- `0x14004b0a8`
- `0x140056ee0`
- `0x14005b1a0`
- `0x140064250`
- `0x140064480`
- `0x140065210`
- `0x140083174`
- `0x14008de10`
- `0x1400ac0c0`
- `0x1400cd030`
- `0x1400d26b8`
- `0x1400d3b58`
- `0x1400d4788`
- `0x1401186f0`
- `0x14011b264`
- `0x14011f2c8`
- `0x140121058`
- `0x140121a00`
- `0x140125fd8`
- `0x14012a85c`
- `0x14012ac60`
- `0x14012b2fc`
- `0x14012bc9c`
- `0x14012d594`
- `0x140135058`
- `0x14013a9f8`
- `0x14013ab64`
- `0x14013de04`
- `0x14013decc`
- `0x14013e3ec`
- `0x14013ff9c`
- `0x14014b564`
- `0x140151be0`
- `0x140151cd0`
- `0x140153770`
- `0x140157364`
- `0x1401696ec`
- `0x14016b060`
- `0x14016b208`
- `0x14016b608`
- `0x14016bea8`
- `0x14016c4d8`
- `0x14016d860`

## callees

- `0x140012b30`
- `0x1400137a0`
- `0x140035300`
- `0x140072970`
- `0x1400c0cb4`
- `0x1400c4acc`
- `0x1400cb474`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140012d15`
- `ntoskrnl!KdDebuggerEnabled` at `0x140012d2b`
- `ntoskrnl!KdDebuggerEnabled` at `0x140012d41`
- `ntoskrnl!KdDebuggerEnabled` at `0x140012d57`
- `ntoskrnl!KdDebuggerEnabled` at `0x140012d6d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012bec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012c69`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012bec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012c69`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012c46`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012cc3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012c46`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012cc3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ee8b4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ee8cf`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ee8b4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ee8cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c7f`

## pseudocode

```c
void __fastcall CmsTransactionContext::Abort(CmsTransactionContext *this, __int64 a2, __int64 a3)
{
  __int64 v4; // r15
  char v5; // al
  __int64 v6; // r14
  __int64 *v7; // rsi
  __int64 v8; // rdx
  __int64 *v9; // rbp
  struct _SLIST_ENTRY *v10; // rdx
  struct _SLIST_ENTRY *Next; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v12; // rcx
  __int64 *v13; // rsi
  __int64 v14; // rdx
  __int64 *v15; // rbp
  struct _SLIST_ENTRY *v16; // rdx
  struct _SLIST_ENTRY *v17; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx

  *(_QWORD *)this |= 2uLL;
  v4 = *((_QWORD *)this + 1);
  if ( (*(_QWORD *)this & 4) != 0 )
  {
    LOBYTE(a3) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)this + 1), 0x20000000, a3);
  }
  if ( *((_DWORD *)this + 214) + *((_DWORD *)this + 215) )
    CmsPinCache::DoomCachedPinsForTable((CmsTransactionContext *)((char *)this + 824), this, 0, 0);
  v5 = *((_BYTE *)this + 130);
  *((_QWORD *)this + 25) = 0;
  if ( *((_BYTE *)this + 131) != v5 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_BYTE *)this + 131) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_BYTE *)this + 132) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_BYTE *)this + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_WORD *)this + 106) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *(_WORD *)((char *)this + 131) = 0;
  *((_BYTE *)this + 130) = 0;
  if ( *((_QWORD *)this + 18) )
    CmsBPlusTable::AbortUndoRecords(this, 0);
  v6 = *((_QWORD *)this + 52);
  v7 = *(__int64 **)(v6 + 24);
  while ( v7 )
  {
    v8 = *v7;
    v9 = v7;
    v7 = (__int64 *)v7[6];
    if ( !v8 )
      goto LABEL_14;
    v10 = (struct _SLIST_ENTRY *)(v8 - 16);
    Next = v10->Next;
    if ( !v10->Next )
    {
LABEL_44:
      operator delete(v10);
      goto LABEL_14;
    }
    if ( *((_BYTE *)&Next->Next + 8) )
    {
      v12 = (struct _NPAGED_LOOKASIDE_LIST *)&Next[4];
      if ( *((_BYTE *)&Next->Next + 9) )
        ExFreeToNPagedLookasideList(v12, v10);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v12, v10);
    }
    else
    {
      v20 = *((_QWORD *)&Next[5].Next + 1);
      if ( (int)v20 >= SLODWORD(Next[5].Next) && SHIDWORD(v20) < (int)v20 )
        goto LABEL_44;
      ExpInterlockedPushEntrySList((PSLIST_HEADER)&Next[4], v10);
      _InterlockedIncrement((volatile signed __int32 *)&Next[5].Next + 2);
    }
LABEL_14:
    ExFreePoolWithTag(v9, 0);
  }
  v13 = *(__int64 **)(v6 + 16);
  *(_QWORD *)(v6 + 24) = 0;
  *(_QWORD *)(v6 + 32) = 0;
  *(_QWORD *)v6 = 0;
  *(_QWORD *)(v6 + 8) = 0;
  while ( v13 )
  {
    v14 = *v13;
    v15 = v13;
    v13 = (__int64 *)v13[6];
    if ( !v14 )
      goto LABEL_23;
    v16 = (struct _SLIST_ENTRY *)(v14 - 16);
    v17 = v16->Next;
    if ( !v16->Next )
    {
LABEL_47:
      operator delete(v16);
      goto LABEL_23;
    }
    if ( *((_BYTE *)&v17->Next + 8) )
    {
      v18 = (struct _NPAGED_LOOKASIDE_LIST *)&v17[4];
      if ( *((_BYTE *)&v17->Next + 9) )
        ExFreeToNPagedLookasideList(v18, v16);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18, v16);
    }
    else
    {
      v21 = *((_QWORD *)&v17[5].Next + 1);
      if ( (int)v21 >= SLODWORD(v17[5].Next) && SHIDWORD(v21) < (int)v21 )
        goto LABEL_47;
      ExpInterlockedPushEntrySList((PSLIST_HEADER)&v17[4], v16);
      _InterlockedIncrement((volatile signed __int32 *)&v17[5].Next + 2);
    }
LABEL_23:
    ExFreePoolWithTag(v15, 0);
  }
  v19 = *(_DWORD *)(v6 + 48);
  *(_QWORD *)(v6 + 16) = 0;
  _InterlockedAdd((volatile signed __int32 *)(v4 + 3168), -v19);
  *(_DWORD *)(v6 + 48) = 0;
  *(_QWORD *)(v6 + 40) = 0;
  CmsTransactionContext::ReuseTransaction(this);
  if ( *((_QWORD *)this + 23) )
  {
    MsTriageDeleteContext();
    *((_QWORD *)this + 23) = 0;
  }
}

```

## disassembly

```asm
0x140012b30  push    rbx
0x140012b32  push    rbp
0x140012b33  push    rsi
0x140012b34  push    rdi
0x140012b35  push    r12
0x140012b37  push    r14
0x140012b39  push    r15
0x140012b3b  sub     rsp, 20h
0x140012b3f  or      qword ptr [rcx], 2
0x140012b43  mov     rbx, rcx
0x140012b46  mov     rax, [rcx]
0x140012b49  mov     r15, [rcx+8]
0x140012b4d  test    al, 4
0x140012b4f  jnz     loc_140012D83
0x140012b55  lea     rcx, [rbx+338h]; this
0x140012b5c  mov     eax, [rcx+24h]
0x140012b5f  add     eax, [rcx+20h]
0x140012b62  jz      short loc_140012B72
0x140012b64  xor     r9d, r9d; struct _LIST_ENTRY *
0x140012b67  xor     r8d, r8d; struct CmsBPlusTable *
0x140012b6a  mov     rdx, rbx; struct CmsTransactionContext *
0x140012b6d  call    ?DoomCachedPinsForTable@CmsPinCache@@QEAAXPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DoomCachedPinsForTable(CmsTransactionContext *,CmsBPlusTable *,_LIST_ENTRY *)
0x140012b72  mov     al, [rbx+82h]
0x140012b78  xor     r12d, r12d
0x140012b7b  mov     [rbx+0C8h], r12
0x140012b82  cmp     [rbx+83h], al
0x140012b88  jnz     loc_140012D15
0x140012b8e  cmp     [rbx+83h], r12b
0x140012b95  jnz     loc_140012D2B
0x140012b9b  cmp     [rbx+84h], r12b
0x140012ba2  jnz     loc_140012D41
0x140012ba8  cmp     [rbx+82h], r12b
0x140012baf  jnz     loc_140012D57
0x140012bb5  cmp     [rbx+0D4h], r12w
0x140012bbd  jnz     loc_140012D6D
0x140012bc3  mov     [rbx+83h], r12w
0x140012bcb  mov     [rbx+82h], r12b
0x140012bd2  cmp     [rbx+90h], r12
0x140012bd9  jnz     loc_140012D98
0x140012bdf  mov     r14, [rbx+1A0h]
0x140012be6  mov     rsi, [r14+18h]
0x140012bea  jmp     short loc_140012C0E
0x140012bec  call    cs:__imp_ExFreeToNPagedLookasideList
0x140012bf3  nop     dword ptr [rax+rax+00h]
0x140012bf8  test    rbp, rbp
0x140012bfb  jz      short loc_140012C0E
0x140012bfd  xor     edx, edx; Tag
0x140012bff  mov     rcx, rbp; P
0x140012c02  call    cs:__imp_ExFreePoolWithTag
0x140012c09  nop     dword ptr [rax+rax+00h]
0x140012c0e  test    rsi, rsi
0x140012c11  jz      short loc_140012C54
0x140012c13  mov     rdx, [rsi]
0x140012c16  mov     rbp, rsi
0x140012c19  mov     rsi, [rsi+30h]
0x140012c1d  test    rdx, rdx
0x140012c20  jz      short loc_140012BFD
0x140012c22  add     rdx, 0FFFFFFFFFFFFFFF0h; ListEntry
0x140012c26  mov     rdi, [rdx]
0x140012c29  test    rdi, rdi
0x140012c2c  jz      loc_140012DC3
0x140012c32  cmp     [rdi+8], r12b
0x140012c36  jz      loc_140012DA7
0x140012c3c  lea     rcx, [rdi+40h]; Lookaside
0x140012c40  cmp     [rdi+9], r12b
0x140012c44  jnz     short loc_140012BEC
0x140012c46  call    cs:__imp_ExFreeToPagedLookasideList
0x140012c4d  nop     dword ptr [rax+rax+00h]
0x140012c52  jmp     short loc_140012BF8
0x140012c54  mov     rsi, [r14+10h]
0x140012c58  mov     [r14+18h], r12
0x140012c5c  mov     [r14+20h], r12
0x140012c60  mov     [r14], r12
0x140012c63  mov     [r14+8], r12
0x140012c67  jmp     short loc_140012C8B
0x140012c69  call    cs:__imp_ExFreeToNPagedLookasideList
0x140012c70  nop     dword ptr [rax+rax+00h]
0x140012c75  test    rbp, rbp
0x140012c78  jz      short loc_140012C8B
0x140012c7a  xor     edx, edx; Tag
0x140012c7c  mov     rcx, rbp; P
0x140012c7f  call    cs:__imp_ExFreePoolWithTag
0x140012c86  nop     dword ptr [rax+rax+00h]
0x140012c8b  test    rsi, rsi
0x140012c8e  jz      short loc_140012CD1
0x140012c90  mov     rdx, [rsi]
0x140012c93  mov     rbp, rsi
0x140012c96  mov     rsi, [rsi+30h]
0x140012c9a  test    rdx, rdx
0x140012c9d  jz      short loc_140012C7A
0x140012c9f  add     rdx, 0FFFFFFFFFFFFFFF0h; ListEntry
0x140012ca3  mov     rdi, [rdx]
0x140012ca6  test    rdi, rdi
0x140012ca9  jz      loc_140012DEC
0x140012caf  cmp     [rdi+8], r12b
0x140012cb3  jz      loc_140012DD0
0x140012cb9  lea     rcx, [rdi+40h]; Lookaside
0x140012cbd  cmp     [rdi+9], r12b
0x140012cc1  jnz     short loc_140012C69
0x140012cc3  call    cs:__imp_ExFreeToPagedLookasideList
0x140012cca  nop     dword ptr [rax+rax+00h]
0x140012ccf  jmp     short loc_140012C75
0x140012cd1  mov     eax, [r14+30h]
0x140012cd5  mov     [r14+10h], r12
0x140012cd9  neg     eax
0x140012cdb  nop
0x140012cdc  lock add [r15+0C60h], eax
0x140012ce4  nop
0x140012ce5  mov     rcx, rbx; this
0x140012ce8  mov     [r14+30h], r12d
0x140012cec  mov     [r14+28h], r12
0x140012cf0  call    ?ReuseTransaction@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::ReuseTransaction(void)
0x140012cf5  mov     rcx, [rbx+0B8h]
0x140012cfc  test    rcx, rcx
0x140012cff  jnz     loc_140012DF9
0x140012d05  add     rsp, 20h
0x140012d09  pop     r15
0x140012d0b  pop     r14
0x140012d0d  pop     r12
0x140012d0f  pop     rdi
0x140012d10  pop     rsi
0x140012d11  pop     rbp
0x140012d12  pop     rbx
0x140012d13  retn
0x140012d15  mov     rax, cs:KdDebuggerEnabled
0x140012d1c  cmp     [rax], r12b
0x140012d1f  jz      loc_140012B8E
0x140012d25  int     3; Trap to Debugger
0x140012d26  jmp     loc_140012B8E
0x140012d2b  mov     rax, cs:KdDebuggerEnabled
0x140012d32  cmp     [rax], r12b
0x140012d35  jz      loc_140012B9B
0x140012d3b  int     3; Trap to Debugger
0x140012d3c  jmp     loc_140012B9B
0x140012d41  mov     rax, cs:KdDebuggerEnabled
0x140012d48  cmp     [rax], r12b
0x140012d4b  jz      loc_140012BA8
0x140012d51  int     3; Trap to Debugger
0x140012d52  jmp     loc_140012BA8
0x140012d57  mov     rax, cs:KdDebuggerEnabled
0x140012d5e  cmp     [rax], r12b
0x140012d61  jz      loc_140012BB5
0x140012d67  int     3; Trap to Debugger
0x140012d68  jmp     loc_140012BB5
0x140012d6d  mov     rax, cs:KdDebuggerEnabled
0x140012d74  cmp     [rax], r12b
0x140012d77  jz      loc_140012BC3
0x140012d7d  int     3; Trap to Debugger
0x140012d7e  jmp     loc_140012BC3
0x140012d83  mov     r8b, 1
0x140012d86  mov     edx, 20000000h
0x140012d8b  mov     rcx, r15
0x140012d8e  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140012d93  jmp     loc_140012B55
0x140012d98  xor     edx, edx; struct SmsUndoRecord *
0x140012d9a  mov     rcx, rbx; struct CmsTransactionContext *
0x140012d9d  call    ?AbortUndoRecords@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@@Z; CmsBPlusTable::AbortUndoRecords(CmsTransactionContext *,SmsUndoRecord *)
0x140012da2  jmp     loc_140012BDF
0x140012da7  mov     rcx, [rdi+58h]
0x140012dab  cmp     ecx, [rdi+50h]
0x140012dae  jl      loc_1401EE8B0
0x140012db4  mov     rax, rcx
0x140012db7  sar     rax, 20h
0x140012dbb  cmp     eax, ecx
0x140012dbd  jge     loc_1401EE8B0
0x140012dc3  mov     rcx, rdx; void *
0x140012dc6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012dcb  jmp     loc_140012BF8
0x140012dd0  mov     rcx, [rdi+58h]
0x140012dd4  cmp     ecx, [rdi+50h]
0x140012dd7  jl      loc_1401EE8CB
0x140012ddd  mov     rax, rcx
0x140012de0  sar     rax, 20h
0x140012de4  cmp     eax, ecx
0x140012de6  jge     loc_1401EE8CB
0x140012dec  mov     rcx, rdx; void *
0x140012def  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012df4  jmp     loc_140012C75
0x140012df9  call    MsTriageDeleteContext
0x140012dfe  mov     [rbx+0B8h], r12
0x140012e05  jmp     loc_140012D05
0x1401ee8b0  lea     rcx, [rdi+40h]; ListHead
0x1401ee8b4  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401ee8bb  nop     dword ptr [rax+rax+00h]
0x1401ee8c0  nop
0x1401ee8c1  lock inc dword ptr [rdi+58h]
0x1401ee8c5  nop
0x1401ee8c6  jmp     loc_140012BF8
0x1401ee8cb  lea     rcx, [rdi+40h]; ListHead
0x1401ee8cf  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401ee8d6  nop     dword ptr [rax+rax+00h]
0x1401ee8db  nop
0x1401ee8dc  lock inc dword ptr [rdi+58h]
0x1401ee8e0  nop
0x1401ee8e1  jmp     loc_140012C75
```
