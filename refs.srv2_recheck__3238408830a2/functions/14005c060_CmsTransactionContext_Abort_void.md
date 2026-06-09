# CmsTransactionContext::Abort(void)

- ea: `0x14005c060`
- end: `0x14005c33a`
- name: `?Abort@CmsTransactionContext@@QEAAXXZ`
- size: `730`
- prototype: `void __fastcall(CmsTransactionContext *__hidden this)`
- caller_count: `46`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140008ed4`
- `0x140014100`
- `0x1400206c0`
- `0x14002ff00`
- `0x140030130`
- `0x140030ec0`
- `0x1400568e0`
- `0x14005af00`
- `0x14005afa0`
- `0x14005c048`
- `0x140086420`
- `0x1400b27b8`
- `0x1400d2d14`
- `0x1400d8664`
- `0x1400d9408`
- `0x14011dd40`
- `0x14012073c`
- `0x140124ff4`
- `0x140126a70`
- `0x14012743c`
- `0x14012b35c`
- `0x14012ced4`
- `0x14012ec7c`
- `0x14012f080`
- `0x14012f71c`
- `0x1401300bc`
- `0x140131a08`
- `0x14013a718`
- `0x1401403f0`
- `0x140140534`
- `0x140143ccc`
- `0x140143d94`
- `0x140144320`
- `0x140147c6c`
- `0x140154420`
- `0x14015b0c0`
- `0x14015b1b0`
- `0x14015cf70`
- `0x14016112c`
- `0x1401738fc`
- `0x140175290`
- `0x140175440`
- `0x140175840`
- `0x140176118`
- `0x1401767e0`
- `0x140177bd0`

## callees

- `0x140016230`
- `0x140049050`
- `0x140051210`
- `0x14005c060`
- `0x1400c2a04`
- `0x1400cbe48`
- `0x1400d1a90`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14005c245`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005c25b`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005c271`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005c287`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005c29d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c11c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c199`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c11c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c199`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c176`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c1f3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c176`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c1f3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdce8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdd03`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdce8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdd03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c132`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c1af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c132`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c1af`

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
  _InterlockedAdd((volatile signed __int32 *)(v4 + 3104), -v19);
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
0x14005c060  push    rbx
0x14005c062  push    rbp
0x14005c063  push    rsi
0x14005c064  push    rdi
0x14005c065  push    r12
0x14005c067  push    r14
0x14005c069  push    r15
0x14005c06b  sub     rsp, 20h
0x14005c06f  or      qword ptr [rcx], 2
0x14005c073  mov     rbx, rcx
0x14005c076  mov     rax, [rcx]
0x14005c079  mov     r15, [rcx+8]
0x14005c07d  test    al, 4
0x14005c07f  jnz     loc_14005C2B3
0x14005c085  lea     rcx, [rbx+338h]; this
0x14005c08c  mov     eax, [rcx+24h]
0x14005c08f  add     eax, [rcx+20h]
0x14005c092  jz      short loc_14005C0A2
0x14005c094  xor     r9d, r9d; struct _LIST_ENTRY *
0x14005c097  xor     r8d, r8d; struct CmsBPlusTable *
0x14005c09a  mov     rdx, rbx; struct CmsTransactionContext *
0x14005c09d  call    ?DoomCachedPinsForTable@CmsPinCache@@QEAAXPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DoomCachedPinsForTable(CmsTransactionContext *,CmsBPlusTable *,_LIST_ENTRY *)
0x14005c0a2  mov     al, [rbx+82h]
0x14005c0a8  xor     r12d, r12d
0x14005c0ab  mov     [rbx+0C8h], r12
0x14005c0b2  cmp     [rbx+83h], al
0x14005c0b8  jnz     loc_14005C245
0x14005c0be  cmp     [rbx+83h], r12b
0x14005c0c5  jnz     loc_14005C25B
0x14005c0cb  cmp     [rbx+84h], r12b
0x14005c0d2  jnz     loc_14005C271
0x14005c0d8  cmp     [rbx+82h], r12b
0x14005c0df  jnz     loc_14005C287
0x14005c0e5  cmp     [rbx+0D4h], r12w
0x14005c0ed  jnz     loc_14005C29D
0x14005c0f3  mov     [rbx+83h], r12w
0x14005c0fb  mov     [rbx+82h], r12b
0x14005c102  cmp     [rbx+90h], r12
0x14005c109  jnz     loc_14005C2C8
0x14005c10f  mov     r14, [rbx+1A0h]
0x14005c116  mov     rsi, [r14+18h]
0x14005c11a  jmp     short loc_14005C13E
0x14005c11c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005c123  nop     dword ptr [rax+rax+00h]
0x14005c128  test    rbp, rbp
0x14005c12b  jz      short loc_14005C13E
0x14005c12d  xor     edx, edx; Tag
0x14005c12f  mov     rcx, rbp; P
0x14005c132  call    cs:__imp_ExFreePoolWithTag
0x14005c139  nop     dword ptr [rax+rax+00h]
0x14005c13e  test    rsi, rsi
0x14005c141  jz      short loc_14005C184
0x14005c143  mov     rdx, [rsi]
0x14005c146  mov     rbp, rsi
0x14005c149  mov     rsi, [rsi+30h]
0x14005c14d  test    rdx, rdx
0x14005c150  jz      short loc_14005C12D
0x14005c152  add     rdx, 0FFFFFFFFFFFFFFF0h; ListEntry
0x14005c156  mov     rdi, [rdx]
0x14005c159  test    rdi, rdi
0x14005c15c  jz      loc_14005C2F3
0x14005c162  cmp     [rdi+8], r12b
0x14005c166  jz      loc_14005C2D7
0x14005c16c  lea     rcx, [rdi+40h]; Lookaside
0x14005c170  cmp     [rdi+9], r12b
0x14005c174  jnz     short loc_14005C11C
0x14005c176  call    cs:__imp_ExFreeToPagedLookasideList
0x14005c17d  nop     dword ptr [rax+rax+00h]
0x14005c182  jmp     short loc_14005C128
0x14005c184  mov     rsi, [r14+10h]
0x14005c188  mov     [r14+18h], r12
0x14005c18c  mov     [r14+20h], r12
0x14005c190  mov     [r14], r12
0x14005c193  mov     [r14+8], r12
0x14005c197  jmp     short loc_14005C1BB
0x14005c199  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005c1a0  nop     dword ptr [rax+rax+00h]
0x14005c1a5  test    rbp, rbp
0x14005c1a8  jz      short loc_14005C1BB
0x14005c1aa  xor     edx, edx; Tag
0x14005c1ac  mov     rcx, rbp; P
0x14005c1af  call    cs:__imp_ExFreePoolWithTag
0x14005c1b6  nop     dword ptr [rax+rax+00h]
0x14005c1bb  test    rsi, rsi
0x14005c1be  jz      short loc_14005C201
0x14005c1c0  mov     rdx, [rsi]
0x14005c1c3  mov     rbp, rsi
0x14005c1c6  mov     rsi, [rsi+30h]
0x14005c1ca  test    rdx, rdx
0x14005c1cd  jz      short loc_14005C1AA
0x14005c1cf  add     rdx, 0FFFFFFFFFFFFFFF0h; ListEntry
0x14005c1d3  mov     rdi, [rdx]
0x14005c1d6  test    rdi, rdi
0x14005c1d9  jz      loc_14005C31C
0x14005c1df  cmp     [rdi+8], r12b
0x14005c1e3  jz      loc_14005C300
0x14005c1e9  lea     rcx, [rdi+40h]; Lookaside
0x14005c1ed  cmp     [rdi+9], r12b
0x14005c1f1  jnz     short loc_14005C199
0x14005c1f3  call    cs:__imp_ExFreeToPagedLookasideList
0x14005c1fa  nop     dword ptr [rax+rax+00h]
0x14005c1ff  jmp     short loc_14005C1A5
0x14005c201  mov     eax, [r14+30h]
0x14005c205  mov     [r14+10h], r12
0x14005c209  neg     eax
0x14005c20b  nop
0x14005c20c  lock add [r15+0C20h], eax
0x14005c214  nop
0x14005c215  mov     rcx, rbx; this
0x14005c218  mov     [r14+30h], r12d
0x14005c21c  mov     [r14+28h], r12
0x14005c220  call    ?ReuseTransaction@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::ReuseTransaction(void)
0x14005c225  mov     rcx, [rbx+0B8h]
0x14005c22c  test    rcx, rcx
0x14005c22f  jnz     loc_14005C329
0x14005c235  add     rsp, 20h
0x14005c239  pop     r15
0x14005c23b  pop     r14
0x14005c23d  pop     r12
0x14005c23f  pop     rdi
0x14005c240  pop     rsi
0x14005c241  pop     rbp
0x14005c242  pop     rbx
0x14005c243  retn
0x14005c245  mov     rax, cs:KdDebuggerEnabled
0x14005c24c  cmp     [rax], r12b
0x14005c24f  jz      loc_14005C0BE
0x14005c255  int     3; Trap to Debugger
0x14005c256  jmp     loc_14005C0BE
0x14005c25b  mov     rax, cs:KdDebuggerEnabled
0x14005c262  cmp     [rax], r12b
0x14005c265  jz      loc_14005C0CB
0x14005c26b  int     3; Trap to Debugger
0x14005c26c  jmp     loc_14005C0CB
0x14005c271  mov     rax, cs:KdDebuggerEnabled
0x14005c278  cmp     [rax], r12b
0x14005c27b  jz      loc_14005C0D8
0x14005c281  int     3; Trap to Debugger
0x14005c282  jmp     loc_14005C0D8
0x14005c287  mov     rax, cs:KdDebuggerEnabled
0x14005c28e  cmp     [rax], r12b
0x14005c291  jz      loc_14005C0E5
0x14005c297  int     3; Trap to Debugger
0x14005c298  jmp     loc_14005C0E5
0x14005c29d  mov     rax, cs:KdDebuggerEnabled
0x14005c2a4  cmp     [rax], r12b
0x14005c2a7  jz      loc_14005C0F3
0x14005c2ad  int     3; Trap to Debugger
0x14005c2ae  jmp     loc_14005C0F3
0x14005c2b3  mov     r8b, 1
0x14005c2b6  mov     edx, 20000000h
0x14005c2bb  mov     rcx, r15
0x14005c2be  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x14005c2c3  jmp     loc_14005C085
0x14005c2c8  xor     edx, edx; struct SmsUndoRecord *
0x14005c2ca  mov     rcx, rbx; struct CmsTransactionContext *
0x14005c2cd  call    ?AbortUndoRecords@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@@Z; CmsBPlusTable::AbortUndoRecords(CmsTransactionContext *,SmsUndoRecord *)
0x14005c2d2  jmp     loc_14005C10F
0x14005c2d7  mov     rcx, [rdi+58h]
0x14005c2db  cmp     ecx, [rdi+50h]
0x14005c2de  jl      loc_1401FDCE4
0x14005c2e4  mov     rax, rcx
0x14005c2e7  sar     rax, 20h
0x14005c2eb  cmp     eax, ecx
0x14005c2ed  jge     loc_1401FDCE4
0x14005c2f3  mov     rcx, rdx; void *
0x14005c2f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c2fb  jmp     loc_14005C128
0x14005c300  mov     rcx, [rdi+58h]
0x14005c304  cmp     ecx, [rdi+50h]
0x14005c307  jl      loc_1401FDCFF
0x14005c30d  mov     rax, rcx
0x14005c310  sar     rax, 20h
0x14005c314  cmp     eax, ecx
0x14005c316  jge     loc_1401FDCFF
0x14005c31c  mov     rcx, rdx; void *
0x14005c31f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c324  jmp     loc_14005C1A5
0x14005c329  call    MsTriageDeleteContext
0x14005c32e  mov     [rbx+0B8h], r12
0x14005c335  jmp     loc_14005C235
0x1401fdce4  lea     rcx, [rdi+40h]; ListHead
0x1401fdce8  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fdcef  nop     dword ptr [rax+rax+00h]
0x1401fdcf4  nop
0x1401fdcf5  lock inc dword ptr [rdi+58h]
0x1401fdcf9  nop
0x1401fdcfa  jmp     loc_14005C128
0x1401fdcff  lea     rcx, [rdi+40h]; ListHead
0x1401fdd03  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fdd0a  nop     dword ptr [rax+rax+00h]
0x1401fdd0f  nop
0x1401fdd10  lock inc dword ptr [rdi+58h]
0x1401fdd14  nop
0x1401fdd15  jmp     loc_14005C1A5
```
