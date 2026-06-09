# W3_SERVER::NotifyConfigurationChange(ushort const *,int)

- ea: `0x18001cd9c`
- end: `0x18001cf5e`
- name: `?NotifyConfigurationChange@W3_SERVER@@AEAAXPEBGH@Z`
- size: `450`
- prototype: `void __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18001cf70`
- `0x18001e130`

## callees

- `0x180008930`
- `0x18000a340`
- `0x18001baac`
- `0x18001cd9c`
- `0x18001d57c`
- `0x18003439a`
- `0x1800343be`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18001ce17`
- `msvcrt!_wcsupr` at `0x18001ce17`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cf35`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cf35`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001ced6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001ced6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ce32`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ce32`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ce0e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ce22`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ce0e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ce22`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001cf2a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001cf2a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001cdfb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001cdfb`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001cee4`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001cee4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cded`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cded`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001ceaf`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001cebf`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001ceaf`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18001cebf`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18001cef0`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18001cef0`

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
0x18001cd9c  mov     [rsp-8+arg_10], rbx
0x18001cda1  push    rbp
0x18001cda2  push    rsi
0x18001cda3  push    rdi
0x18001cda4  push    r14
0x18001cda6  push    r15
0x18001cda8  lea     rbp, [rsp-80h]
0x18001cdad  sub     rsp, 180h
0x18001cdb4  mov     rax, cs:__security_cookie
0x18001cdbb  xor     rax, rsp
0x18001cdbe  mov     [rbp+0A0h+var_30], rax
0x18001cdc2  mov     r15d, r8d
0x18001cdc5  mov     rbx, rdx
0x18001cdc8  mov     rdi, rcx
0x18001cdcb  xor     edx, edx; Val
0x18001cdcd  mov     r8d, 100h; Size
0x18001cdd3  lea     rcx, [rsp+1A0h+var_130]; void *
0x18001cdd8  call    memset_0
0x18001cddd  mov     r8d, 80h
0x18001cde3  lea     rdx, [rsp+1A0h+var_130]
0x18001cde8  lea     rcx, [rsp+1A0h+var_168]
0x18001cded  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001cdf3  mov     rdx, rbx
0x18001cdf6  lea     rcx, [rsp+1A0h+var_168]
0x18001cdfb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ce01  lea     rcx, [rsp+1A0h+var_168]
0x18001ce06  test    eax, eax
0x18001ce08  js      loc_18001CF35
0x18001ce0e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ce14  mov     rcx, rax; String
0x18001ce17  call    cs:__imp__wcsupr
0x18001ce1d  lea     rcx, [rsp+1A0h+var_168]
0x18001ce22  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ce28  lea     r14, [rdi+2Ch]
0x18001ce2c  mov     rbx, rax
0x18001ce2f  mov     rcx, r14
0x18001ce32  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001ce38  cmp     dword ptr [rdi+14h], 0
0x18001ce3c  jnz     short loc_18001CE6B
0x18001ce3e  lea     rdx, [rdi+8]
0x18001ce42  mov     rcx, rdi
0x18001ce45  neg     rcx
0x18001ce48  sbb     rsi, rsi
0x18001ce4b  and     rsi, rdx
0x18001ce4e  xor     edx, edx
0x18001ce50  mov     rcx, rsi
0x18001ce53  lea     r8d, [rdx+4]
0x18001ce57  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18001ce5c  test    eax, eax
0x18001ce5e  jz      short loc_18001CE6B
0x18001ce60  mov     r8, rbx; unsigned __int16 *
0x18001ce63  mov     rcx, rsi; struct IHttpTraceContext *
0x18001ce66  call    ?RaiseEvent@CONFIG_CHANGE_NOTIFICATION@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISGeneralEvents::CONFIG_CHANGE_NOTIFICATION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x18001ce6b  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001ce72  mov     rcx, rbx; String1
0x18001ce75  call    wcscmp_0
0x18001ce7a  test    eax, eax
0x18001ce7c  jnz     short loc_18001CEA5
0x18001ce7e  mov     rcx, rdi; this
0x18001ce81  call    ?HasGlobalModulesListChanged@W3_SERVER@@QEAAHXZ; W3_SERVER::HasGlobalModulesListChanged(void)
0x18001ce86  test    eax, eax
0x18001ce88  jz      short loc_18001CEA5
0x18001ce8a  mov     rax, [rdi]
0x18001ce8d  lea     rdx, aGlobalModulesH; "Global modules has changed"
0x18001ce94  mov     rcx, rdi
0x18001ce97  mov     rax, [rax+30h]
0x18001ce9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cea0  jmp     loc_18001CF27
0x18001cea5  lea     rcx, [rdi+590h]
0x18001ceac  mov     rdx, rbx
0x18001ceaf  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18001ceb5  lea     rcx, [rdi+568h]
0x18001cebc  mov     rdx, rbx
0x18001cebf  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18001cec5  test    r15d, r15d
0x18001cec8  jz      short loc_18001CEF6
0x18001ceca  lea     rcx, [rsp+1A0h+var_168]
0x18001cecf  lea     rsi, [rdi+520h]
0x18001ced6  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001cedc  mov     rcx, rsi
0x18001cedf  cmp     eax, 18h
0x18001cee2  jnb     short loc_18001CEEC
0x18001cee4  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18001ceea  jmp     short loc_18001CEF6
0x18001ceec  lea     rdx, [rbx+30h]
0x18001cef0  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x18001cef6  cmp     dword ptr [rdi+14h], 0
0x18001cefa  jnz     short loc_18001CF27
0x18001cefc  lea     rax, ??_7MetaChangeProvider@@6B@; const MetaChangeProvider::`vftable'
0x18001cf03  mov     [rsp+1A0h+var_178], rbx
0x18001cf08  lea     r8, [rsp+1A0h+var_180]
0x18001cf0d  mov     [rsp+1A0h+var_180], rax
0x18001cf12  mov     edx, 40h ; '@'
0x18001cf17  mov     [rsp+1A0h+var_170], 0
0x18001cf1f  mov     rcx, rdi
0x18001cf22  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001cf27  mov     rcx, r14
0x18001cf2a  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001cf30  lea     rcx, [rsp+1A0h+var_168]
0x18001cf35  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001cf3b  mov     rcx, [rbp+0A0h+var_30]
0x18001cf3f  xor     rcx, rsp; StackCookie
0x18001cf42  call    __security_check_cookie
0x18001cf47  mov     rbx, [rsp+1A0h+arg_10]
0x18001cf4f  add     rsp, 180h
0x18001cf56  pop     r15
0x18001cf58  pop     r14
0x18001cf5a  pop     rdi
0x18001cf5b  pop     rsi
0x18001cf5c  pop     rbp
0x18001cf5d  retn
```
