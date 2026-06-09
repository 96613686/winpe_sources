# CConnStrParsingManager::SearchConnStrParsingCacheItem(uchar * const,ulong)

- ea: `0x180060f88`
- end: `0x180060ffb`
- name: `?SearchConnStrParsingCacheItem@CConnStrParsingManager@@QEAAPEAVCConnStrParsingCacheItem@@QEAEK@Z`
- size: `115`
- prototype: `struct CConnStrParsingCacheItem *(CConnStrParsingManager *__hidden this, unsigned __int8 *const, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020d2c`

## callees

- `0x180060c78`
- `0x180060e94`
- `0x180060f88`

## import_xrefs

- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060fe7`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060fe7`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060fbe`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060fbe`

## pseudocode

```c
struct CConnStrParsingCacheItem *__fastcall CConnStrParsingManager::SearchConnStrParsingCacheItem(
        CConnStrParsingManager *this,
        unsigned __int8 *const a2,
        unsigned int a3)
{
  CConnStrParsingManager *v3; // rdi
  unsigned int v6; // ebx
  char *v7; // r14
  struct CConnStrParsingCacheItem *v8; // rax
  struct CConnStrParsingCacheItem *v9; // rbx

  v3 = _ConnStrParsingManager;
  v6 = CConnStrParsingManager::ComputeHash(a2, 0x20u);
  v7 = (char *)v3 + 12 * v6;
  CReaderWriterLock3AR::ReadLock((CReaderWriterLock3AR *)(v7 + 512));
  v8 = CConnStrParsingManager::InternalSearchConnStrParsingCacheItem(v3, v6, a2, a3);
  v9 = v8;
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)v8 + 9);
  CReaderWriterLock3AR::ReadUnlock((CReaderWriterLock3AR *)(v7 + 512));
  return v9;
}

```

## disassembly

```asm
0x180060f88  push    rbx
0x180060f8a  push    rbp
0x180060f8b  push    rsi
0x180060f8c  push    rdi
0x180060f8d  push    r14
0x180060f8f  sub     rsp, 20h
0x180060f93  mov     rdi, cs:?_ConnStrParsingManager@@3PEAVCConnStrParsingManager@@EA; CConnStrParsingManager * _ConnStrParsingManager
0x180060f9a  mov     rbp, rdx
0x180060f9d  mov     rcx, rbp; unsigned __int8 *
0x180060fa0  mov     edx, 20h ; ' '; unsigned __int64
0x180060fa5  mov     esi, r8d
0x180060fa8  call    ?ComputeHash@CConnStrParsingManager@@CAKQEAE_K@Z; CConnStrParsingManager::ComputeHash(uchar * const,unsigned __int64)
0x180060fad  mov     ebx, eax
0x180060faf  lea     r10, [rbx+rbx*2]
0x180060fb3  lea     r14, [rdi+r10*4]
0x180060fb7  lea     rcx, [r14+200h]
0x180060fbe  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x180060fc4  mov     r9d, esi; unsigned int
0x180060fc7  mov     r8, rbp; unsigned __int8 *
0x180060fca  mov     edx, ebx; unsigned int
0x180060fcc  mov     rcx, rdi; this
0x180060fcf  call    ?InternalSearchConnStrParsingCacheItem@CConnStrParsingManager@@AEAAPEAVCConnStrParsingCacheItem@@KPEAEK@Z; CConnStrParsingManager::InternalSearchConnStrParsingCacheItem(ulong,uchar *,ulong)
0x180060fd4  mov     rbx, rax
0x180060fd7  test    rax, rax
0x180060fda  jz      short loc_180060FE0
0x180060fdc  lock inc dword ptr [rax+24h]
0x180060fe0  lea     rcx, [r14+200h]
0x180060fe7  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x180060fed  mov     rax, rbx
0x180060ff0  add     rsp, 20h
0x180060ff4  pop     r14
0x180060ff6  pop     rdi
0x180060ff7  pop     rsi
0x180060ff8  pop     rbp
0x180060ff9  pop     rbx
0x180060ffa  retn
```
