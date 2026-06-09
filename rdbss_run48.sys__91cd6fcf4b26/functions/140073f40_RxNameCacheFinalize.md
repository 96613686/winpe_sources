# RxNameCacheFinalize

- ea: `0x140073f40`
- end: `0x1400741d1`
- name: `RxNameCacheFinalize`
- size: `657`
- prototype: `void __stdcall(PNAME_CACHE_CONTROL NameCacheCtl)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140014e40`
- `0x140025d00`
- `0x140073f40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140074026`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007403b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007407c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007414d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074162`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074026`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007403b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007407c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007414d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074162`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140073f57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400740b1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140073f57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400740b1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007409c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400740ec`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007409c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400740ec`

## pseudocode

```c
void __stdcall RxNameCacheFinalize(PNAME_CACHE_CONTROL NameCacheCtl)
{
  LIST_ENTRY *p_ActiveList; // rdi
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v4; // rcx
  struct _LIST_ENTRY *v5; // rsi
  __int64 v6; // rax
  struct _LIST_ENTRY *v7; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  void (__fastcall *v9)(PVOID, struct _LIST_ENTRY *); // rax
  struct _LIST_ENTRY *v10; // rcx
  LIST_ENTRY *p_FreeList; // rdi
  struct _LIST_ENTRY *v12; // rax
  struct _NAME_CACHE_CONTROL_ *v13; // rcx
  struct _LIST_ENTRY *v14; // rdx
  LIST_ENTRY *p_WaitListHead; // rbx
  struct _LIST_ENTRY *v16; // rax
  struct _LIST_ENTRY *v17; // rcx
  struct _LIST_ENTRY *v18; // rsi
  struct _LIST_ENTRY *v19; // rcx

  ExAcquirePushLockExclusiveEx(&NameCacheCtl->NameCacheLock.OldIrql, 0);
  p_ActiveList = &NameCacheCtl->ActiveList;
  while ( 1 )
  {
    Flink = p_ActiveList->Flink;
    if ( p_ActiveList->Flink == p_ActiveList )
      break;
    if ( Flink->Blink != p_ActiveList )
      goto LABEL_29;
    v4 = Flink->Flink;
    if ( Flink->Flink->Blink != Flink )
      goto LABEL_29;
    p_ActiveList->Flink = v4;
    v5 = Flink - 4;
    v4->Blink = p_ActiveList;
    Flink->Blink = Flink;
    Flink->Flink = Flink;
    v6 = (__int64)&Flink[2];
    v7 = *(struct _LIST_ENTRY **)v6;
    if ( *(_QWORD *)(*(_QWORD *)v6 + 8LL) != v6 )
      goto LABEL_29;
    Blink = v5[6].Blink;
    if ( Blink->Flink != (struct _LIST_ENTRY *)v6 )
      goto LABEL_29;
    Blink->Flink = v7;
    v7->Blink = Blink;
    v5[6].Blink = (struct _LIST_ENTRY *)v6;
    *(_QWORD *)v6 = v6;
    if ( LOWORD(v5->Flink) != 0xEBAA )
    {
      v9 = *(void (__fastcall **)(PVOID, struct _LIST_ENTRY *))&NameCacheCtl[1].NameCacheLock.Count;
      if ( v9 )
      {
        v9(NameCacheCtl[1].NameCacheLock.Owner, v5);
        v5[2].Blink = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, &v5[5]);
      }
      v10 = v5[5].Blink;
      if ( v10 )
      {
        ExFreePoolWithTag(v10, 0);
        v5[5].Blink = 0;
      }
      ExFreePoolWithTag(v5, 0);
      _InterlockedDecrement((volatile signed __int32 *)&NameCacheCtl->EntryCount);
      _InterlockedDecrement(&dword_140038AD8);
    }
  }
  p_FreeList = &NameCacheCtl->FreeList;
  while ( 1 )
  {
    v12 = p_FreeList->Flink;
    if ( p_FreeList->Flink == p_FreeList )
      break;
    if ( v12->Blink != p_FreeList )
      goto LABEL_29;
    v17 = v12->Flink;
    if ( v12->Flink->Blink != v12 )
      goto LABEL_29;
    p_FreeList->Flink = v17;
    v18 = v12 - 4;
    v17->Blink = p_FreeList;
    v12->Blink = v12;
    v12->Flink = v12;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, &v18[5]);
    }
    v19 = v18[5].Blink;
    if ( v19 )
    {
      ExFreePoolWithTag(v19, 0);
      v18[5].Blink = 0;
    }
    ExFreePoolWithTag(v18, 0);
    _InterlockedDecrement((volatile signed __int32 *)&NameCacheCtl->EntryCount);
    _InterlockedDecrement(&dword_140038AD8);
  }
  v13 = (struct _NAME_CACHE_CONTROL_ *)NameCacheCtl[1].NameCacheLock.Event.Header.WaitListHead.Blink;
  if ( v13 != (struct _NAME_CACHE_CONTROL_ *)&NameCacheCtl[1].NameCacheLock.Contention )
    ExFreePoolWithTag(v13, 0);
  NameCacheCtl[1].NameCacheLock.Event.Header.WaitListHead.Blink = 0;
  LODWORD(NameCacheCtl[1].NameCacheLock.Event.Header.WaitListHead.Flink) = 0;
  ExReleasePushLockExclusiveEx(&NameCacheCtl->NameCacheLock.OldIrql, 0);
  ExAcquirePushLockExclusiveEx(&RxNameCacheGlobalConfig, 0);
  v14 = NameCacheCtl->NameCacheLock.Event.Header.WaitListHead.Flink;
  p_WaitListHead = &NameCacheCtl->NameCacheLock.Event.Header.WaitListHead;
  if ( v14->Blink != p_WaitListHead || (v16 = p_WaitListHead->Blink, v16->Flink != p_WaitListHead) )
LABEL_29:
    __fastfail(3u);
  v16->Flink = v14;
  v14->Blink = v16;
  ExReleasePushLockExclusiveEx(&RxNameCacheGlobalConfig, 0);
}

```

## disassembly

```asm
0x140073f40  push    rbx
0x140073f42  push    rbp
0x140073f43  push    rdi
0x140073f44  push    r12
0x140073f46  push    r14
0x140073f48  push    r15
0x140073f4a  sub     rsp, 28h
0x140073f4e  mov     rbx, rcx
0x140073f51  xor     edx, edx
0x140073f53  add     rcx, 30h ; '0'
0x140073f57  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140073f5e  nop     dword ptr [rax+rax+00h]
0x140073f63  xor     r14d, r14d
0x140073f66  mov     [rsp+58h+arg_0], rsi
0x140073f6b  lea     rdi, [rbx+38h]
0x140073f6f  mov     r15d, 0EBAAh
0x140073f75  lea     r12, WPP_GLOBAL_Control
0x140073f7c  mov     rax, [rdi]
0x140073f7f  cmp     rax, rdi
0x140073f82  jz      loc_140074057
0x140073f88  cmp     [rax+8], rdi
0x140073f8c  jnz     loc_14007417E
0x140073f92  mov     rcx, [rax]
0x140073f95  cmp     [rcx+8], rax
0x140073f99  jnz     loc_14007417E
0x140073f9f  mov     [rdi], rcx
0x140073fa2  lea     rsi, [rax-40h]
0x140073fa6  mov     [rcx+8], rdi
0x140073faa  mov     [rax+8], rax
0x140073fae  mov     [rax], rax
0x140073fb1  lea     rax, [rsi+60h]
0x140073fb5  mov     rdx, [rax]
0x140073fb8  cmp     [rdx+8], rax
0x140073fbc  jnz     loc_14007417E
0x140073fc2  mov     rcx, [rsi+68h]
0x140073fc6  cmp     [rcx], rax
0x140073fc9  jnz     loc_14007417E
0x140073fcf  mov     [rcx], rdx
0x140073fd2  mov     [rdx+8], rcx
0x140073fd6  mov     [rsi+68h], rax
0x140073fda  mov     [rax], rax
0x140073fdd  cmp     [rsi], r15w
0x140073fe1  jz      short loc_140073F7C
0x140073fe3  mov     rax, [rbx+88h]
0x140073fea  test    rax, rax
0x140073fed  jz      short loc_140074002
0x140073fef  mov     rcx, [rbx+90h]
0x140073ff6  mov     rdx, rsi
0x140073ff9  call    _guard_dispatch_icall
0x140073ffe  mov     [rsi+28h], r14
0x140074002  mov     rcx, cs:WPP_GLOBAL_Control
0x140074009  cmp     rcx, r12
0x14007400c  jz      short loc_14007401B
0x14007400e  test    dword ptr [rcx+2Ch], 800h
0x140074015  jnz     loc_140074185
0x14007401b  mov     rcx, [rsi+58h]; P
0x14007401f  test    rcx, rcx
0x140074022  jz      short loc_140074036
0x140074024  xor     edx, edx; Tag
0x140074026  call    cs:__imp_ExFreePoolWithTag
0x14007402d  nop     dword ptr [rax+rax+00h]
0x140074032  mov     [rsi+58h], r14
0x140074036  xor     edx, edx; Tag
0x140074038  mov     rcx, rsi; P
0x14007403b  call    cs:__imp_ExFreePoolWithTag
0x140074042  nop     dword ptr [rax+rax+00h]
0x140074047  lock dec dword ptr [rbx+58h]
0x14007404b  lock dec cs:dword_140038AD8
0x140074052  jmp     loc_140073F7C
0x140074057  lea     rdi, [rbx+48h]
0x14007405b  mov     rax, [rdi]
0x14007405e  cmp     rax, rdi
0x140074061  jnz     loc_14007410C
0x140074067  mov     rcx, [rbx+0B0h]; P
0x14007406e  lea     rax, [rbx+98h]
0x140074075  cmp     rcx, rax
0x140074078  jz      short loc_140074088
0x14007407a  xor     edx, edx; Tag
0x14007407c  call    cs:__imp_ExFreePoolWithTag
0x140074083  nop     dword ptr [rax+rax+00h]
0x140074088  xor     edx, edx
0x14007408a  mov     [rbx+0B0h], r14
0x140074091  lea     rcx, [rbx+30h]
0x140074095  mov     [rbx+0A8h], r14d
0x14007409c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400740a3  nop     dword ptr [rax+rax+00h]
0x1400740a8  xor     edx, edx
0x1400740aa  lea     rcx, RxNameCacheGlobalConfig
0x1400740b1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400740b8  nop     dword ptr [rax+rax+00h]
0x1400740bd  mov     rdx, [rbx+20h]
0x1400740c1  add     rbx, 20h ; ' '
0x1400740c5  cmp     [rdx+8], rbx
0x1400740c9  jnz     loc_14007417E
0x1400740cf  mov     rax, [rbx+8]
0x1400740d3  cmp     [rax], rbx
0x1400740d6  jnz     loc_14007417E
0x1400740dc  mov     [rax], rdx
0x1400740df  lea     rcx, RxNameCacheGlobalConfig
0x1400740e6  mov     [rdx+8], rax
0x1400740ea  xor     edx, edx
0x1400740ec  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400740f3  nop     dword ptr [rax+rax+00h]
0x1400740f8  mov     rsi, [rsp+58h+arg_0]
0x1400740fd  add     rsp, 28h
0x140074101  pop     r15
0x140074103  pop     r14
0x140074105  pop     r12
0x140074107  pop     rdi
0x140074108  pop     rbp
0x140074109  pop     rbx
0x14007410a  retn
0x14007410c  cmp     [rax+8], rdi
0x140074110  jnz     short loc_14007417E
0x140074112  mov     rcx, [rax]
0x140074115  cmp     [rcx+8], rax
0x140074119  jnz     short loc_14007417E
0x14007411b  mov     [rdi], rcx
0x14007411e  lea     rsi, [rax-40h]
0x140074122  mov     [rcx+8], rdi
0x140074126  mov     [rax+8], rax
0x14007412a  mov     [rax], rax
0x14007412d  mov     rcx, cs:WPP_GLOBAL_Control
0x140074134  cmp     rcx, r12
0x140074137  jz      short loc_140074142
0x140074139  test    dword ptr [rcx+2Ch], 800h
0x140074140  jnz     short loc_1400741AD
0x140074142  mov     rcx, [rsi+58h]; P
0x140074146  test    rcx, rcx
0x140074149  jz      short loc_14007415D
0x14007414b  xor     edx, edx; Tag
0x14007414d  call    cs:__imp_ExFreePoolWithTag
0x140074154  nop     dword ptr [rax+rax+00h]
0x140074159  mov     [rsi+58h], r14
0x14007415d  xor     edx, edx; Tag
0x14007415f  mov     rcx, rsi; P
0x140074162  call    cs:__imp_ExFreePoolWithTag
0x140074169  nop     dword ptr [rax+rax+00h]
0x14007416e  lock dec dword ptr [rbx+58h]
0x140074172  lock dec cs:dword_140038AD8
0x140074179  jmp     loc_14007405B
0x14007417e  mov     ecx, 3
0x140074183  int     29h; Win8: RtlFailFast(ecx)
0x140074185  cmp     byte ptr [rcx+29h], 4
0x140074189  jb      loc_14007401B
0x14007418f  mov     rcx, [rcx+18h]
0x140074193  lea     r9, [rsi+50h]
0x140074197  mov     edx, 1Ah
0x14007419c  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x1400741a3  call    WPP_SF_Z
0x1400741a8  jmp     loc_14007401B
0x1400741ad  cmp     byte ptr [rcx+29h], 4
0x1400741b1  jb      short loc_140074142
0x1400741b3  mov     rcx, [rcx+18h]
0x1400741b7  lea     r9, [rsi+50h]
0x1400741bb  mov     edx, 1Ah
0x1400741c0  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x1400741c7  call    WPP_SF_Z
0x1400741cc  jmp     loc_140074142
```
