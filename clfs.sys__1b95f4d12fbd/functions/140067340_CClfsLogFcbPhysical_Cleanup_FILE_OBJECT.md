# CClfsLogFcbPhysical::Cleanup(_FILE_OBJECT *)

- ea: `0x140067340`
- end: `0x14006741f`
- name: `?Cleanup@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005840`
- `0x14000e540`
- `0x140017f20`
- `0x140067340`
- `0x140067428`
- `0x140067458`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006739c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006739c`
- `ntoskrnl!IoRemoveShareAccess` at `0x1400673c6`
- `ntoskrnl!IoRemoveShareAccess` at `0x1400673c6`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::Cleanup(struct _SHARE_ACCESS *this, struct _FILE_OBJECT *a2)
{
  __int64 v4; // rax
  struct _ERESOURCE *p_Readers; // rbp
  unsigned int v6; // esi
  BOOLEAN v7; // r9
  int v9; // [rsp+50h] [rbp+8h] BYREF
  CLFS_LSN v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = CLFS_LSN_NULL;
  v4 = *(_QWORD *)&this->OpenCount;
  v9 = 0;
  p_Readers = (struct _ERESOURCE *)&this[7].Readers;
  v6 = (*(__int64 (__fastcall **)(struct _SHARE_ACCESS *, CLFS_LSN *, _QWORD, __int64, int *))(v4 + 192))(
         this,
         &v10,
         0,
         10,
         &v9);
  ExAcquireResourceExclusiveLite(p_Readers, 1u);
  if ( (a2->Flags & 2) == 0 )
    v6 = CClfsLogFcbPhysical::CleanupAsyncIo((CClfsLogFcbPhysical *)this, a2);
  IoRemoveShareAccess(a2, this + 12);
  a2->Flags |= 0x4000u;
  if ( !CClfsLogFcbCommon::ReleaseHandleRef((CClfsLogFcbCommon *)this) )
    CClfsLogFcbPhysical::PurgeCacheSection(
      (CClfsLogFcbPhysical *)this,
      (CLFS_LSN *)&CLFS_LSN_NULL,
      (CLFS_LSN *)&CLFS_LSN_NULL,
      v7);
  (*(void (__fastcall **)(struct _SHARE_ACCESS *, struct _FILE_OBJECT *))(*(_QWORD *)&this->OpenCount + 8LL))(this, a2);
  ClfsReleaseResourceLite((struct _ERESOURCE *)&this[7].Readers);
  return v6;
}

```

## disassembly

```asm
0x140067340  mov     r11, rsp
0x140067343  mov     [r11+18h], rbx
0x140067347  push    rbp
0x140067348  push    rsi
0x140067349  push    rdi
0x14006734a  sub     rsp, 30h
0x14006734e  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140067355  mov     rbx, rcx
0x140067358  mov     [r11+10h], rax
0x14006735c  mov     rdi, rdx
0x14006735f  mov     rax, [rcx]
0x140067362  lea     rdx, [r11+10h]
0x140067366  lea     rcx, [r11+8]
0x14006736a  mov     [rsp+48h+arg_0], 0
0x140067372  mov     [r11-28h], rcx
0x140067376  mov     r9d, 0Ah
0x14006737c  xor     r8d, r8d
0x14006737f  mov     rcx, rbx
0x140067382  mov     rax, [rax+0C0h]
0x140067389  call    _guard_dispatch_icall
0x14006738e  lea     rbp, [rbx+0C8h]
0x140067395  mov     dl, 1; Wait
0x140067397  mov     rcx, rbp; Resource
0x14006739a  mov     esi, eax
0x14006739c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400673a3  nop     dword ptr [rax+rax+00h]
0x1400673a8  mov     eax, [rdi+50h]
0x1400673ab  test    al, 2
0x1400673ad  jnz     short loc_1400673BC
0x1400673af  mov     rdx, rdi; struct _FILE_OBJECT *
0x1400673b2  mov     rcx, rbx; this
0x1400673b5  call    ?CleanupAsyncIo@CClfsLogFcbPhysical@@AEAAJQEAU_FILE_OBJECT@@@Z; CClfsLogFcbPhysical::CleanupAsyncIo(_FILE_OBJECT * const)
0x1400673ba  mov     esi, eax
0x1400673bc  lea     rdx, [rbx+150h]; ShareAccess
0x1400673c3  mov     rcx, rdi; FileObject
0x1400673c6  call    cs:__imp_IoRemoveShareAccess
0x1400673cd  nop     dword ptr [rax+rax+00h]
0x1400673d2  bts     dword ptr [rdi+50h], 0Eh
0x1400673d7  mov     rcx, rbx; this
0x1400673da  call    ?ReleaseHandleRef@CClfsLogFcbCommon@@QEAAKXZ; CClfsLogFcbCommon::ReleaseHandleRef(void)
0x1400673df  test    eax, eax
0x1400673e1  jnz     short loc_1400673F5
0x1400673e3  lea     rdx, CLFS_LSN_NULL; plsn
0x1400673ea  mov     rcx, rbx; this
0x1400673ed  mov     r8, rdx; CLFS_LSN *
0x1400673f0  call    ?PurgeCacheSection@CClfsLogFcbPhysical@@AEAAEAEBT_CLS_LSN@@0E@Z; CClfsLogFcbPhysical::PurgeCacheSection(_CLS_LSN const &,_CLS_LSN const &,uchar)
0x1400673f5  mov     rax, [rbx]
0x1400673f8  mov     rdx, rdi
0x1400673fb  mov     rcx, rbx
0x1400673fe  mov     rax, [rax+8]
0x140067402  call    _guard_dispatch_icall
0x140067407  mov     rcx, rbp
0x14006740a  call    ClfsReleaseResourceLite
0x14006740f  mov     rbx, [rsp+48h+arg_10]
0x140067414  mov     eax, esi
0x140067416  add     rsp, 30h
0x14006741a  pop     rdi
0x14006741b  pop     rsi
0x14006741c  pop     rbp
0x14006741d  retn
```
