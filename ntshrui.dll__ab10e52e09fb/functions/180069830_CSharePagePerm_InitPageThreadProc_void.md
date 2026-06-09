# CSharePagePerm::InitPageThreadProc(void *)

- ea: `0x180069830`
- end: `0x1800699fb`
- name: `?InitPageThreadProc@CSharePagePerm@@SAKPEAX@Z`
- size: `459`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800098dc`
- `0x1800104f0`
- `0x180053fd4`
- `0x180065e18`
- `0x180069830`
- `0x18006a258`
- `0x18006a53c`
- `0x18006f2b8`
- `0x18006f368`
- `0x18007047c`
- `0x180070720`
- `0x180070808`
- `0x180070970`
- `0x1800743c4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800698a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800698a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069885`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180069966`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180069966`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006994b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006994b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069996`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069996`
- `SHCORE!IsOS` at `0x1800698f2`
- `SHCORE!IsOS` at `0x1800698f2`
- `USER32!PostMessageW` at `0x1800699d5`
- `USER32!PostMessageW` at `0x1800699d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSharePagePerm::InitPageThreadProc(PVOID Parameter)
{
  unsigned int v2; // edx
  __int64 v3; // rsi
  CUserObjectList *v4; // rcx
  HDPA v5; // rax
  struct _DPA *v6; // rcx
  CUserObject *v7; // rbx
  HLOCAL v8; // rax
  void *v9; // rbp
  CSidResolver *v10; // rcx
  int Error; // esi
  unsigned int v12; // edx
  void **cbSid; // [rsp+60h] [rbp+8h] BYREF
  struct CUserObject *v15; // [rsp+68h] [rbp+10h] BYREF
  void **v16; // [rsp+70h] [rbp+18h]

  if ( !(unsigned int)CUserObjectList::IsResolved(*(CUserObjectList **)(*((_QWORD *)Parameter + 2) + 40LL)) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)Parameter + 2) + 40LL);
    if ( (unsigned int)CUserObjectList::_InitLock((CUserObjectList *)v3) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 32));
      cbSid = &CNameResolver::`vftable';
      CSidResolver::ResolveSids(
        (CSidResolver *)&cbSid,
        (struct CUserObjectList *)v3,
        (struct IShareProgressSink *)(((unsigned __int64)Parameter + 40) & -(__int64)(Parameter != 0)));
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 32));
    }
  }
  v4 = *(CUserObjectList **)(*((_QWORD *)Parameter + 2) + 48LL);
  if ( v4 )
    CUserObjectList::`scalar deleting destructor'(v4, v2);
  CUserObjectList::Clone(
    *(CUserObjectList **)(*((_QWORD *)Parameter + 2) + 40LL),
    (struct CUserObjectList **)(*((_QWORD *)Parameter + 2) + 48LL));
  if ( !*((_QWORD *)Parameter + 30) )
  {
    v5 = DPA_Create(5);
    *((_QWORD *)Parameter + 30) = v5;
    if ( v5 )
    {
      if ( !IsOS(0x1Cu) )
      {
        CSharePagePerm::_AddUserNames((CSharePagePerm *)Parameter);
        CSharePagePerm::_AddOnlineUserNames((CSharePagePerm *)Parameter);
      }
      v6 = (struct _DPA *)*((_QWORD *)Parameter + 30);
      if ( v6 )
        DPA_Sort(v6, (PFNDACOMPARE)ComboNamesSortCallback, 0);
    }
  }
  if ( !*((_WORD *)Parameter + 36) )
  {
    v16 = &CNameResolver::`vftable';
    v7 = 0;
    v15 = 0;
    LODWORD(cbSid) = 68;
    v8 = LocalAlloc(0x40u, 0x44u);
    v9 = v8;
    if ( v8 )
    {
      if ( CreateWellKnownSid(WinWorldSid, 0, v8, (DWORD *)&cbSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        Error = CSidResolver::SingletonSidLookup(v10, v9, SHARE_ROLE_INVALID, &v15);
        v7 = v15;
      }
      LocalFree(v9);
      if ( Error >= 0 )
      {
        CUserObject::GetDisplayName(v7, (unsigned __int16 *)Parameter + 36, 0x51u);
        if ( v7 )
          CUserObject::`scalar deleting destructor'(v7, v12);
      }
    }
  }
  if ( *((_DWORD *)Parameter + 8) )
    PostMessageW(*((HWND *)Parameter + 1), 0x65Au, 0, 0);
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Parameter + 16LL))(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180069830  push    rbx
0x180069832  push    rbp
0x180069833  push    rsi
0x180069834  push    rdi
0x180069835  push    r12
0x180069837  push    r14
0x180069839  push    r15
0x18006983b  sub     rsp, 20h
0x18006983f  mov     rdi, rcx
0x180069842  mov     rcx, [rcx+10h]
0x180069846  mov     rcx, [rcx+28h]; this
0x18006984a  call    ?IsResolved@CUserObjectList@@QEAAHXZ; CUserObjectList::IsResolved(void)
0x18006984f  lea     r12, ??_7CNameResolver@@6B@; const CNameResolver::`vftable'
0x180069856  xor     r15d, r15d
0x180069859  test    eax, eax
0x18006985b  jnz     short loc_1800698AB
0x18006985d  mov     rax, [rdi+10h]
0x180069861  mov     rsi, [rax+28h]
0x180069865  mov     rax, rdi
0x180069868  lea     rcx, [rdi+28h]
0x18006986c  neg     rax
0x18006986f  sbb     rbp, rbp
0x180069872  and     rbp, rcx
0x180069875  mov     rcx, rsi; this
0x180069878  call    ?_InitLock@CUserObjectList@@AEAAHXZ; CUserObjectList::_InitLock(void)
0x18006987d  test    eax, eax
0x18006987f  jz      short loc_1800698AB
0x180069881  lea     rcx, [rsi+20h]; lpCriticalSection
0x180069885  call    cs:__imp_EnterCriticalSection
0x18006988b  mov     [rsp+58h+cbSid], r12
0x180069890  mov     r8, rbp; struct IShareProgressSink *
0x180069893  mov     rdx, rsi; struct CUserObjectList *
0x180069896  lea     rcx, [rsp+58h+cbSid]; this
0x18006989b  call    ?ResolveSids@CSidResolver@@QEAAJPEAVCUserObjectList@@PEAUIShareProgressSink@@@Z; CSidResolver::ResolveSids(CUserObjectList *,IShareProgressSink *)
0x1800698a0  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800698a4  call    cs:__imp_LeaveCriticalSection
0x1800698aa  nop
0x1800698ab  mov     rax, [rdi+10h]
0x1800698af  mov     rcx, [rax+30h]; this
0x1800698b3  test    rcx, rcx
0x1800698b6  jz      short loc_1800698BD
0x1800698b8  call    ??_GCUserObjectList@@QEAAPEAXI@Z; CUserObjectList::`scalar deleting destructor'(uint)
0x1800698bd  mov     rcx, [rdi+10h]
0x1800698c1  lea     rdx, [rcx+30h]; struct CUserObjectList **
0x1800698c5  mov     rcx, [rcx+28h]; this
0x1800698c9  call    ?Clone@CUserObjectList@@QEAAJPEAPEAV1@@Z; CUserObjectList::Clone(CUserObjectList * *)
0x1800698ce  cmp     [rdi+0F0h], r15
0x1800698d5  jnz     short loc_180069927
0x1800698d7  mov     ecx, 5; cItemGrow
0x1800698dc  call    DPA_Create
0x1800698e1  mov     [rdi+0F0h], rax
0x1800698e8  test    rax, rax
0x1800698eb  jz      short loc_180069927
0x1800698ed  mov     ecx, 1Ch; dwOS
0x1800698f2  call    cs:__imp_IsOS
0x1800698f8  test    eax, eax
0x1800698fa  jnz     short loc_18006990C
0x1800698fc  mov     rcx, rdi; this
0x1800698ff  call    ?_AddUserNames@CSharePagePerm@@AEAAJXZ; CSharePagePerm::_AddUserNames(void)
0x180069904  mov     rcx, rdi; this
0x180069907  call    ?_AddOnlineUserNames@CSharePagePerm@@AEAAJXZ; CSharePagePerm::_AddOnlineUserNames(void)
0x18006990c  mov     rcx, [rdi+0F0h]; hdpa
0x180069913  test    rcx, rcx
0x180069916  jz      short loc_180069927
0x180069918  xor     r8d, r8d; lParam
0x18006991b  lea     rdx, ?ComboNamesSortCallback@@YAHPEBVCAccountInfo@@0PEAX@Z; pfnCompare
0x180069922  call    DPA_Sort
0x180069927  cmp     [rdi+48h], r15w
0x18006992c  jnz     loc_1800699C0
0x180069932  mov     [rsp+58h+arg_10], r12
0x180069937  mov     rbx, r15
0x18006993a  mov     [rsp+58h+arg_8], rbx
0x18006993f  mov     edx, 44h ; 'D'; uBytes
0x180069944  mov     dword ptr [rsp+58h+cbSid], edx
0x180069948  lea     ecx, [rdx-4]; uFlags
0x18006994b  call    cs:__imp_LocalAlloc
0x180069951  mov     rbp, rax
0x180069954  test    rax, rax
0x180069957  jz      short loc_1800699C0
0x180069959  lea     r9, [rsp+58h+cbSid]; cbSid
0x18006995e  mov     r8, rax; pSid
0x180069961  xor     edx, edx; DomainSid
0x180069963  lea     ecx, [rdx+1]; WellKnownSidType
0x180069966  call    cs:__imp_CreateWellKnownSid
0x18006996c  test    eax, eax
0x18006996e  jnz     short loc_18006997B
0x180069970  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180069975  mov     esi, eax
0x180069977  test    eax, eax
0x180069979  js      short loc_180069993
0x18006997b  lea     r9, [rsp+58h+arg_8]; struct CUserObject **
0x180069980  or      r8d, 0FFFFFFFFh; enum SHARE_ROLE
0x180069984  mov     rdx, rbp; void *
0x180069987  call    ?SingletonSidLookup@CSidResolver@@QEAAJPEAXW4SHARE_ROLE@@PEAPEAVCUserObject@@@Z; CSidResolver::SingletonSidLookup(void *,SHARE_ROLE,CUserObject * *)
0x18006998c  mov     esi, eax
0x18006998e  mov     rbx, [rsp+58h+arg_8]
0x180069993  mov     rcx, rbp; hMem
0x180069996  call    cs:__imp_LocalFree
0x18006999c  test    esi, esi
0x18006999e  js      short loc_1800699C0
0x1800699a0  mov     r8d, 51h ; 'Q'; unsigned int
0x1800699a6  lea     rdx, [rdi+48h]; unsigned __int16 *
0x1800699aa  mov     rcx, rbx; this
0x1800699ad  call    ?GetDisplayName@CUserObject@@QEAAJPEAGK@Z; CUserObject::GetDisplayName(ushort *,ulong)
0x1800699b2  test    rbx, rbx
0x1800699b5  jz      short loc_1800699C0
0x1800699b7  mov     rcx, rbx; this
0x1800699ba  call    ??_GCUserObject@@QEAAPEAXI@Z; CUserObject::`scalar deleting destructor'(uint)
0x1800699bf  nop
0x1800699c0  cmp     [rdi+20h], r15d
0x1800699c4  jz      short loc_1800699DB
0x1800699c6  xor     r9d, r9d; lParam
0x1800699c9  xor     r8d, r8d; wParam
0x1800699cc  mov     edx, 65Ah; Msg
0x1800699d1  mov     rcx, [rdi+8]; hWnd
0x1800699d5  call    cs:__imp_PostMessageW
0x1800699db  mov     rax, [rdi]
0x1800699de  mov     rcx, rdi
0x1800699e1  mov     rax, [rax+10h]
0x1800699e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699ea  xor     eax, eax
0x1800699ec  add     rsp, 20h
0x1800699f0  pop     r15
0x1800699f2  pop     r14
0x1800699f4  pop     r12
0x1800699f6  pop     rdi
0x1800699f7  pop     rsi
0x1800699f8  pop     rbp
0x1800699f9  pop     rbx
0x1800699fa  retn
```
