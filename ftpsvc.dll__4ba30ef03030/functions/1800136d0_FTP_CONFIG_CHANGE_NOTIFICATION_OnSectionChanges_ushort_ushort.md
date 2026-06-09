# FTP_CONFIG_CHANGE_NOTIFICATION::OnSectionChanges(ushort *,ushort *)

- ea: `0x1800136d0`
- end: `0x1800137c9`
- name: `?OnSectionChanges@FTP_CONFIG_CHANGE_NOTIFICATION@@UEAAJPEAG0@Z`
- size: `249`
- prototype: `int(FTP_CONFIG_CHANGE_NOTIFICATION *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x18000cb74`
- `0x1800136d0`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800136ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1800136ef`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800136fc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001372d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800136fc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001372d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001370c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800137b8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001370c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800137b8`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x1800137af`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x1800137af`

## pseudocode

```c
__int64 __fastcall FTP_CONFIG_CHANGE_NOTIFICATION::OnSectionChanges(
        FTP_CONFIG_CHANGE_NOTIFICATION *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CReaderWriterLock3 *v5; // rsi
  FTP_SITE_MANAGER *v6; // rdi
  unsigned int v7; // ebx
  FTP_SERVERP *v8; // rcx
  __int64 v9; // rax
  CLKRHashTable *v10; // rax
  _QWORD v12[9]; // [rsp+20h] [rbp-48h] BYREF

  if ( a3 )
  {
    v5 = (FTP_CONFIG_CHANGE_NOTIFICATION *)((char *)this + 20);
    if ( SysStringLen(a3) )
    {
      CReaderWriterLock3::WriteLock(v5);
      if ( !*((_DWORD *)this + 3) )
      {
        v6 = (FTP_SITE_MANAGER *)(**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
        v7 = *((_DWORD *)v6 + 40) + 2 - (*((_DWORD *)v6 + 40) != -1);
        FTP_SITE_MANAGER::StartOrUpdateAllSites(v6, v7);
        v8 = g_pFtpServer;
        v12[0] = FTP_METADATA_TABLE::DeletePrefix;
        *((_DWORD *)v6 + 40) = v7;
        v12[1] = 0;
        v9 = *(_QWORD *)v8;
        v12[2] = a3;
        v10 = (CLKRHashTable *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(v9 + 96))(v8);
        CLKRHashTable::DeleteIf(
          v10,
          (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
          v12);
      }
      CReaderWriterLock3::WriteUnlock(v5);
    }
    else
    {
      CReaderWriterLock3::WriteLock(v5);
      *((_DWORD *)this + 3) = 1;
      CReaderWriterLock3::WriteUnlock(v5);
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 216LL))(g_pFtpServer);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800136d0  push    rbx
0x1800136d2  push    rbp
0x1800136d3  push    rsi
0x1800136d4  push    rdi
0x1800136d5  sub     rsp, 48h
0x1800136d9  mov     rbp, r8
0x1800136dc  mov     rbx, rcx
0x1800136df  test    r8, r8
0x1800136e2  jz      loc_1800137BE
0x1800136e8  lea     rsi, [rcx+14h]
0x1800136ec  mov     rcx, r8; pbstr
0x1800136ef  call    cs:__imp_SysStringLen
0x1800136f5  mov     rcx, rsi
0x1800136f8  test    eax, eax
0x1800136fa  jnz     short loc_18001372D
0x1800136fc  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180013702  mov     rcx, rsi
0x180013705  mov     dword ptr [rbx+0Ch], 1
0x18001370c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180013712  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180013719  mov     rax, [rcx]
0x18001371c  mov     rax, [rax+0D8h]
0x180013723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013728  jmp     loc_1800137BE
0x18001372d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180013733  cmp     dword ptr [rbx+0Ch], 0
0x180013737  jnz     short loc_1800137B5
0x180013739  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180013740  mov     rax, [rcx]
0x180013743  mov     rax, [rax]
0x180013746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001374b  mov     rdi, rax
0x18001374e  mov     r8d, [rax+0A0h]
0x180013755  lea     ecx, [r8+1]
0x180013759  neg     ecx
0x18001375b  mov     rcx, rax; this
0x18001375e  sbb     edx, edx
0x180013760  lea     ebx, [rdx+2]
0x180013763  add     ebx, r8d
0x180013766  mov     edx, ebx; unsigned int
0x180013768  call    ?StartOrUpdateAllSites@FTP_SITE_MANAGER@@AEAAJK@Z; FTP_SITE_MANAGER::StartOrUpdateAllSites(ulong)
0x18001376d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180013774  lea     rax, ?DeletePrefix@FTP_METADATA_TABLE@@SA?AW4LK_PREDICATE@@PEAVFTP_METADATA@@PEAX@Z; FTP_METADATA_TABLE::DeletePrefix(FTP_METADATA *,void *)
0x18001377b  mov     [rsp+68h+var_48], rax
0x180013780  mov     [rdi+0A0h], ebx
0x180013786  mov     [rsp+68h+var_40], 0
0x18001378f  mov     rax, [rcx]
0x180013792  mov     [rsp+68h+var_38], rbp
0x180013797  mov     rax, [rax+60h]
0x18001379b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137a0  mov     rcx, rax
0x1800137a3  lea     r8, [rsp+68h+var_48]
0x1800137a8  lea     rdx, ?_Pred@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x1800137af  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x1800137b5  mov     rcx, rsi
0x1800137b8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800137be  xor     eax, eax
0x1800137c0  add     rsp, 48h
0x1800137c4  pop     rdi
0x1800137c5  pop     rsi
0x1800137c6  pop     rbp
0x1800137c7  pop     rbx
0x1800137c8  retn
```
