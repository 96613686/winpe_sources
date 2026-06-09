# CBTree::RebuildCacheIfMissing(void)

- ea: `0x180029d4c`
- end: `0x180029e09`
- name: `?RebuildCacheIfMissing@CBTree@@AEAAKXZ`
- size: `189`
- prototype: `unsigned int __fastcall(CBTree *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d220`
- `0x180011904`
- `0x1800213c8`

## callees

- `0x1800012b8`
- `0x18000d7e0`
- `0x180029d4c`
- `0x180029fbc`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180029da9`
- `wbemcomn!GetMemLogObject` at `0x180029da9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029db4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029db4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029d66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBTree::RebuildCacheIfMissing(struct SIdxKeyTable **this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int IdxPage; // ebx
  CMemoryLog *MemLogObject; // rax
  _BYTE v6[8]; // [rsp+20h] [rbp-28h] BYREF
  void (__stdcall *v7)(LPCRITICAL_SECTION); // [rsp+28h] [rbp-20h]
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+30h] [rbp-18h]

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
  v6[0] = 0;
  v7 = LeaveCriticalSection;
  v8 = v2;
  if ( this[1] )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    IdxPage = CBTree::ReadIdxPage((CBTree *)this, *(_DWORD *)*this, 0, this + 1);
    if ( IdxPage )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, IdxPage);
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, IdxPage);
    }
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v6);
    return IdxPage;
  }
}

```

## disassembly

```asm
0x180029d4c  mov     [rsp+arg_0], rbx
0x180029d51  push    rdi
0x180029d52  sub     rsp, 40h
0x180029d56  mov     rbx, rcx
0x180029d59  lea     rdi, [rcx+10h]
0x180029d5d  mov     rcx, rdi; lpCriticalSection
0x180029d60  call    cs:__imp_EnterCriticalSection
0x180029d66  mov     rax, cs:__imp_LeaveCriticalSection
0x180029d6d  mov     [rsp+48h+var_28], 0
0x180029d72  mov     [rsp+48h+var_20], rax
0x180029d77  mov     [rsp+48h+var_18], rdi
0x180029d7c  lea     r9, [rbx+8]; struct SIdxKeyTable **
0x180029d80  cmp     qword ptr [r9], 0
0x180029d84  jz      short loc_180029D93
0x180029d86  mov     rcx, rdi
0x180029d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d8e  nop
0x180029d8f  xor     eax, eax
0x180029d91  jmp     short loc_180029DFE
0x180029d93  mov     rdx, [rbx]
0x180029d96  xor     r8d, r8d; bool
0x180029d99  mov     edx, [rdx]; unsigned int
0x180029d9b  mov     rcx, rbx; this
0x180029d9e  call    ?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z; CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)
0x180029da3  mov     ebx, eax
0x180029da5  test    eax, eax
0x180029da7  jz      short loc_180029DBA
0x180029da9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180029daf  mov     edx, ebx
0x180029db1  mov     rcx, rax
0x180029db4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180029dba  lea     rax, WPP_GLOBAL_Control
0x180029dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180029dc8  cmp     rcx, rax
0x180029dcb  jz      short loc_180029DF2
0x180029dcd  test    byte ptr [rcx+1Ch], 1
0x180029dd1  jz      short loc_180029DF2
0x180029dd3  cmp     byte ptr [rcx+19h], 2
0x180029dd7  jb      short loc_180029DF2
0x180029dd9  mov     edx, 0B3h
0x180029dde  mov     r9d, ebx
0x180029de1  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180029de8  mov     rcx, [rcx+10h]
0x180029dec  call    WPP_SF_d
0x180029df1  nop
0x180029df2  lea     rcx, [rsp+48h+var_28]
0x180029df7  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x180029dfc  mov     eax, ebx
0x180029dfe  mov     rbx, [rsp+48h+arg_0]
0x180029e03  add     rsp, 40h
0x180029e07  pop     rdi
0x180029e08  retn
```
