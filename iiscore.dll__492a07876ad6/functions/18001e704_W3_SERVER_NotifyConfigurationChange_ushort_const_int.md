# W3_SERVER::NotifyConfigurationChange(ushort const *,int)

- ea: `0x18001e704`
- end: `0x18001e915`
- name: `?NotifyConfigurationChange@W3_SERVER@@AEAAXPEBGH@Z`
- size: `529`
- prototype: `void __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18001e920`
- `0x18001fba0`

## callees

- `0x180009030`
- `0x18000ac10`
- `0x18001d2ec`
- `0x18001e704`
- `0x18001efac`
- `0x18003773a`
- `0x18003775e`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18001e791`
- `msvcrt!_wcsupr` at `0x18001e791`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e8e5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e8e5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001e86e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001e86e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e7b8`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e7b8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e782`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e7a2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e782`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e7a2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8d4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e769`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e769`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001e882`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001e882`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e755`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e755`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001e83b`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001e851`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001e83b`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001e851`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18001e894`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18001e894`

## pseudocode

```c
void __fastcall W3_SERVER::NotifyConfigurationChange(W3_SERVER *this, const unsigned __int16 *a2, int a3)
{
  wchar_t *Str; // rax
  const unsigned __int16 *v7; // rbx
  const struct _GUID *v8; // rdx
  unsigned int CCH; // eax
  CLKRHashTable *v10; // rcx
  _QWORD v11[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+30h] [rbp-D0h]
  _BYTE v13[56]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v14[128]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v14, 0, sizeof(v14));
  STRU::STRU((STRU *)v13, v14, 0x80u);
  if ( (int)STRU::Copy((STRU *)v13, a2) >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v13);
    _wcsupr(Str);
    v7 = STRU::QueryStr((STRU *)v13);
    CReaderWriterLock3::WriteLock((W3_SERVER *)((char *)this + 44));
    if ( !*((_DWORD *)this + 5)
      && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(
                         ((unsigned __int64)this + 8) & -(__int64)(this != 0),
                         0,
                         4) )
    {
      IISGeneralEvents::CONFIG_CHANGE_NOTIFICATION::RaiseEvent(
        (struct IHttpTraceContext *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
        v8,
        v7);
    }
    if ( !wcscmp_0(v7, L"MACHINE/WEBROOT/APPHOST") && (unsigned int)W3_SERVER::HasGlobalModulesListChanged(this) )
    {
      (*(void (__fastcall **)(W3_SERVER *, const wchar_t *))(*(_QWORD *)this + 48LL))(
        this,
        L"Global modules has changed");
    }
    else
    {
      TREE_HASH_TABLE::DeletePath((W3_SERVER *)((char *)this + 1424), v7);
      TREE_HASH_TABLE::DeletePath((W3_SERVER *)((char *)this + 1384), v7);
      if ( a3 )
      {
        CCH = STRU::QueryCCH((STRU *)v13);
        v10 = (W3_SERVER *)((char *)this + 1312);
        if ( CCH >= 0x18 )
          CLKRHashTable::DeleteKey(v10, v7 + 24);
        else
          CLKRHashTable::Clear(v10);
      }
      if ( !*((_DWORD *)this + 5) )
      {
        v11[1] = v7;
        v11[0] = &MetaChangeProvider::`vftable';
        v12 = 0;
        W3_SERVER::GlobalNotify(this, 64, v11);
      }
    }
    CReaderWriterLock3::WriteUnlock((W3_SERVER *)((char *)this + 44));
  }
  STRU::~STRU((STRU *)v13);
}

```

## disassembly

```asm
0x18001e704  mov     [rsp-8+arg_10], rbx
0x18001e709  push    rbp
0x18001e70a  push    rsi
0x18001e70b  push    rdi
0x18001e70c  push    r14
0x18001e70e  push    r15
0x18001e710  lea     rbp, [rsp-80h]
0x18001e715  sub     rsp, 180h
0x18001e71c  mov     rax, cs:__security_cookie
0x18001e723  xor     rax, rsp
0x18001e726  mov     [rbp+0A0h+var_30], rax
0x18001e72a  mov     r15d, r8d
0x18001e72d  mov     rbx, rdx
0x18001e730  mov     rdi, rcx
0x18001e733  xor     edx, edx; Val
0x18001e735  mov     r8d, 100h; Size
0x18001e73b  lea     rcx, [rsp+1A0h+var_130]; void *
0x18001e740  call    memset_0
0x18001e745  mov     r8d, 80h
0x18001e74b  lea     rdx, [rsp+1A0h+var_130]
0x18001e750  lea     rcx, [rsp+1A0h+var_168]
0x18001e755  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e75c  nop     dword ptr [rax+rax+00h]
0x18001e761  mov     rdx, rbx
0x18001e764  lea     rcx, [rsp+1A0h+var_168]
0x18001e769  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e770  nop     dword ptr [rax+rax+00h]
0x18001e775  lea     rcx, [rsp+1A0h+var_168]
0x18001e77a  test    eax, eax
0x18001e77c  js      loc_18001E8E5
0x18001e782  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001e789  nop     dword ptr [rax+rax+00h]
0x18001e78e  mov     rcx, rax; String
0x18001e791  call    cs:__imp__wcsupr
0x18001e798  nop     dword ptr [rax+rax+00h]
0x18001e79d  lea     rcx, [rsp+1A0h+var_168]
0x18001e7a2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001e7a9  nop     dword ptr [rax+rax+00h]
0x18001e7ae  lea     r14, [rdi+2Ch]
0x18001e7b2  mov     rbx, rax
0x18001e7b5  mov     rcx, r14
0x18001e7b8  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001e7bf  nop     dword ptr [rax+rax+00h]
0x18001e7c4  cmp     dword ptr [rdi+14h], 0
0x18001e7c8  jnz     short loc_18001E7F7
0x18001e7ca  lea     rdx, [rdi+8]
0x18001e7ce  mov     rcx, rdi
0x18001e7d1  neg     rcx
0x18001e7d4  sbb     rsi, rsi
0x18001e7d7  and     rsi, rdx
0x18001e7da  xor     edx, edx
0x18001e7dc  mov     rcx, rsi
0x18001e7df  lea     r8d, [rdx+4]
0x18001e7e3  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18001e7e8  test    eax, eax
0x18001e7ea  jz      short loc_18001E7F7
0x18001e7ec  mov     r8, rbx; unsigned __int16 *
0x18001e7ef  mov     rcx, rsi; struct IHttpTraceContext *
0x18001e7f2  call    ?RaiseEvent@CONFIG_CHANGE_NOTIFICATION@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISGeneralEvents::CONFIG_CHANGE_NOTIFICATION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x18001e7f7  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001e7fe  mov     rcx, rbx; String1
0x18001e801  call    wcscmp_0
0x18001e806  test    eax, eax
0x18001e808  jnz     short loc_18001E831
0x18001e80a  mov     rcx, rdi; this
0x18001e80d  call    ?HasGlobalModulesListChanged@W3_SERVER@@QEAAHXZ; W3_SERVER::HasGlobalModulesListChanged(void)
0x18001e812  test    eax, eax
0x18001e814  jz      short loc_18001E831
0x18001e816  mov     rax, [rdi]
0x18001e819  lea     rdx, aGlobalModulesH; "Global modules has changed"
0x18001e820  mov     rcx, rdi
0x18001e823  mov     rax, [rax+30h]
0x18001e827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e82c  jmp     loc_18001E8D1
0x18001e831  lea     rcx, [rdi+590h]
0x18001e838  mov     rdx, rbx
0x18001e83b  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18001e842  nop     dword ptr [rax+rax+00h]
0x18001e847  lea     rcx, [rdi+568h]
0x18001e84e  mov     rdx, rbx
0x18001e851  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18001e858  nop     dword ptr [rax+rax+00h]
0x18001e85d  test    r15d, r15d
0x18001e860  jz      short loc_18001E8A0
0x18001e862  lea     rcx, [rsp+1A0h+var_168]
0x18001e867  lea     rsi, [rdi+520h]
0x18001e86e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001e875  nop     dword ptr [rax+rax+00h]
0x18001e87a  mov     rcx, rsi
0x18001e87d  cmp     eax, 18h
0x18001e880  jnb     short loc_18001E890
0x18001e882  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18001e889  nop     dword ptr [rax+rax+00h]
0x18001e88e  jmp     short loc_18001E8A0
0x18001e890  lea     rdx, [rbx+30h]
0x18001e894  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x18001e89b  nop     dword ptr [rax+rax+00h]
0x18001e8a0  cmp     dword ptr [rdi+14h], 0
0x18001e8a4  jnz     short loc_18001E8D1
0x18001e8a6  lea     rax, ??_7MetaChangeProvider@@6B@; const MetaChangeProvider::`vftable'
0x18001e8ad  mov     [rsp+1A0h+var_178], rbx
0x18001e8b2  lea     r8, [rsp+1A0h+var_180]
0x18001e8b7  mov     [rsp+1A0h+var_180], rax
0x18001e8bc  mov     edx, 40h ; '@'
0x18001e8c1  mov     [rsp+1A0h+var_170], 0
0x18001e8c9  mov     rcx, rdi
0x18001e8cc  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001e8d1  mov     rcx, r14
0x18001e8d4  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001e8db  nop     dword ptr [rax+rax+00h]
0x18001e8e0  lea     rcx, [rsp+1A0h+var_168]
0x18001e8e5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001e8ec  nop     dword ptr [rax+rax+00h]
0x18001e8f1  mov     rcx, [rbp+0A0h+var_30]
0x18001e8f5  xor     rcx, rsp; StackCookie
0x18001e8f8  call    __security_check_cookie
0x18001e8fd  mov     rbx, [rsp+1A0h+arg_10]
0x18001e905  add     rsp, 180h
0x18001e90c  pop     r15
0x18001e90e  pop     r14
0x18001e910  pop     rdi
0x18001e911  pop     rsi
0x18001e912  pop     rbp
0x18001e913  retn
```
