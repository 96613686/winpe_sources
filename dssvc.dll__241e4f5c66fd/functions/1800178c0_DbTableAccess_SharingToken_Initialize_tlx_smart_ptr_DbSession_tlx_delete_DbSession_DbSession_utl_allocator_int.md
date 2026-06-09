# DbTableAccess<SharingToken>::Initialize(tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> const &)

- ea: `0x1800178c0`
- end: `0x1800179c3`
- name: `?Initialize@?$DbTableAccess@VSharingToken@@@@UEAAJAEBV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800179d0`

## callees

- `0x180002ac8`
- `0x18000f120`
- `0x180014a18`
- `0x180015814`
- `0x1800178c0`
- `0x180017ea0`

## pseudocode

```c
__int64 __fastcall DbTableAccess<SharingToken>::Initialize(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rcx
  utl::_RefCountBase *v5; // rcx
  int TableDefinition; // edx
  _QWORD *v7; // rax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2[1];
  v4 = *a2;
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *(_QWORD *)(a1 + 24) = v4;
  v5 = *(utl::_RefCountBase **)(a1 + 32);
  *(_QWORD *)(a1 + 32) = v2;
  if ( v5 )
    utl::_RefCountBase::_DecStrong(v5);
  if ( !*(_QWORD *)(a1 + 24) )
    return (unsigned int)-2147024882;
  v7 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    *v7 = 0;
    v7[1] = 0;
    *((_DWORD *)v7 + 4) = 0;
    v7[3] = 0;
    *((_DWORD *)v7 + 8) = 0;
    v7[7] = 0;
    v7[8] = 0;
    v7[10] = 0;
  }
  if ( (unsigned __int8)tlx::smart_xxx<DbTable *,void (*)(DbTable *),&void tlx::_delete<DbTable>(DbTable *),0,utl::allocator<int>>::reset(
                          a1 + 8,
                          v7) )
  {
    v9 = 0;
    TableDefinition = DbTableDescription<SharingToken>::GetTableDefinition((__int64)&v9);
    if ( TableDefinition >= 0 )
    {
      _InterlockedCompareExchange(&DbTableAccess<SharingToken>::s_fIndexCorrupted, 0, 0);
      TableDefinition = DbTable::Initialize(*(DbTable **)(a1 + 8));
      if ( TableDefinition >= 0 )
        _InterlockedCompareExchange(&DbTableAccess<SharingToken>::s_fIndexCorrupted, 0, 1);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)TableDefinition;
}

```

## disassembly

```asm
0x1800178c0  mov     [rsp+arg_8], rbx
0x1800178c5  push    rdi
0x1800178c6  sub     rsp, 20h
0x1800178ca  mov     rax, [rdx+8]
0x1800178ce  mov     rbx, rcx
0x1800178d1  mov     rcx, [rdx]
0x1800178d4  mov     rdi, rdx
0x1800178d7  test    rax, rax
0x1800178da  jz      short loc_1800178E0
0x1800178dc  lock inc dword ptr [rax+8]
0x1800178e0  mov     [rbx+18h], rcx
0x1800178e4  mov     rcx, [rbx+20h]; this
0x1800178e8  mov     [rbx+20h], rax
0x1800178ec  test    rcx, rcx
0x1800178ef  jz      short loc_1800178F6
0x1800178f1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800178f6  cmp     qword ptr [rbx+18h], 0
0x1800178fb  jnz     short loc_180017907
0x1800178fd  mov     edx, 8007000Eh
0x180017902  jmp     loc_1800179B6
0x180017907  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001790e  mov     ecx, 58h ; 'X'; unsigned __int64
0x180017913  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017918  test    rax, rax
0x18001791b  jz      short loc_18001795A
0x18001791d  mov     qword ptr [rax], 0
0x180017924  mov     qword ptr [rax+8], 0
0x18001792c  mov     dword ptr [rax+10h], 0
0x180017933  mov     qword ptr [rax+18h], 0
0x18001793b  mov     dword ptr [rax+20h], 0
0x180017942  mov     qword ptr [rax+38h], 0
0x18001794a  mov     qword ptr [rax+40h], 0
0x180017952  mov     qword ptr [rax+50h], 0
0x18001795a  mov     rdx, rax
0x18001795d  lea     rcx, [rbx+8]
0x180017961  call    ?reset@?$smart_xxx@PEAVDbTable@@P6AXPEAV1@@Z$1??$_delete@VDbTable@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVDbTable@@@Z; tlx::smart_xxx<DbTable *,void (*)(DbTable *),&tlx::_delete<DbTable>(DbTable *),0,utl::allocator<int>>::reset(DbTable *)
0x180017966  test    al, al
0x180017968  jz      short loc_1800178FD
0x18001796a  lea     rcx, [rsp+28h+arg_0]
0x18001796f  mov     [rsp+28h+arg_0], 0
0x180017978  call    ?GetTableDefinition@?$DbTableDescription@VSharingToken@@@@SAJPEAPEAUtagJET_TABLECREATE_W@@@Z; DbTableDescription<SharingToken>::GetTableDefinition(tagJET_TABLECREATE_W * *)
0x18001797d  mov     edx, eax
0x18001797f  test    eax, eax
0x180017981  js      short loc_1800179B6
0x180017983  xor     edx, edx
0x180017985  xor     eax, eax
0x180017987  lock cmpxchg cs:?s_fIndexCorrupted@?$DbTableAccess@VSharingToken@@@@0JA, edx; long DbTableAccess<SharingToken>::s_fIndexCorrupted
0x18001798f  mov     rdx, [rsp+28h+arg_0]
0x180017994  mov     r9d, eax
0x180017997  mov     rcx, [rbx+8]; this
0x18001799b  mov     r8, rdi
0x18001799e  call    ?Initialize@DbTable@@QEAAJPEAUtagJET_TABLECREATE_W@@AEBV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@H@Z; DbTable::Initialize(tagJET_TABLECREATE_W *,tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> const &,int)
0x1800179a3  mov     edx, eax
0x1800179a5  test    eax, eax
0x1800179a7  js      short loc_1800179B6
0x1800179a9  xor     ecx, ecx
0x1800179ab  lea     eax, [rcx+1]
0x1800179ae  lock cmpxchg cs:?s_fIndexCorrupted@?$DbTableAccess@VSharingToken@@@@0JA, ecx; long DbTableAccess<SharingToken>::s_fIndexCorrupted
0x1800179b6  mov     rbx, [rsp+28h+arg_8]
0x1800179bb  mov     eax, edx
0x1800179bd  add     rsp, 20h
0x1800179c1  pop     rdi
0x1800179c2  retn
```
